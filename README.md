## ch4

PRにおける必須項目は

```yaml
name: ch4-2-2
on:
  pull_request:
    paths: ['go/**/*.go']
jobs:
  ch4-2-2_test:
    name: ch4-2-2-test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-go@v5
        with:
          go-version: '1.22'
      - run: go test go/excellent/*.go
```

で"jobs"のそれぞれに全ワークフローの中で一意な"name"を付け，それを"Settings"から指定する必要がある．まずmainブランチのRulesetを作りmainブランチをTargetとするように設定する．その後"Require status checks to pass"で"name"を入力し（これは補完は効かない），タイプとして"Github Actions"を指定する．
