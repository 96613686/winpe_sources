# <>c::<ReadApplications>b__60_1

- ea: `0x6fc0`
- end: `0x6fea`
- name: `<>c::<ReadApplications>b__60_1`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1610`
- `0x48f0`

## string_xrefs

- `0x6fd9`: `AccountSid`

## pseudocode

```c

```

## disassembly

```asm
0x6fc0  ldarg.1
0x6fc1  ldstr    aUrlstring// "UrlString"
0x6fc6  ldc.i4.1
0x6fc7  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x6fcc  ldarg.1
0x6fcd  ldstr    aAccountname// "AccountName"
0x6fd2  ldc.i4.0
0x6fd3  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x6fd8  ldarg.1
0x6fd9  ldstr    aAccountsid// "AccountSid"
0x6fde  ldc.i4.1
0x6fdf  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x6fe4  call     class Microsoft.BIServer.Configuration.URL Microsoft.BIServer.Configuration.URL::Create(string urlString, string accountName, string accountSecurityIdentifier)
0x6fe9  ret
```
