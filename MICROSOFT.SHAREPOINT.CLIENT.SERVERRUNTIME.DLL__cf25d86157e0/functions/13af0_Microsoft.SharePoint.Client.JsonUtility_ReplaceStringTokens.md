# Microsoft.SharePoint.Client.JsonUtility::ReplaceStringTokens

- ea: `0x13af0`
- end: `0x13b4c`
- name: `Microsoft.SharePoint.Client.JsonUtility::ReplaceStringTokens`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x13af6`: `$1SP.DataConvert.createUtcDateTime($2)`
- `0x13b08`: `$1SP.DataConvert.createLocalDateTime($2)`
- `0x13b1a`: `$1SP.DataConvert.createUnspecifiedDateTime($2)`

## pseudocode

```c

```

## disassembly

```asm
0x13af0  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Client.JsonUtility::s_dateUtcRegEx
0x13af5  ldarg.0
0x13af6  ldstr    a1spDataconvert// "$1SP.DataConvert.createUtcDateTime($2)"
0x13afb  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x13b00  starg.s  0
0x13b02  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Client.JsonUtility::s_dateLocalRegEx
0x13b07  ldarg.0
0x13b08  ldstr    a1spDataconvert_0// "$1SP.DataConvert.createLocalDateTime($2"...
0x13b0d  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x13b12  starg.s  0
0x13b14  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Client.JsonUtility::s_dateUnspecifiedRegEx
0x13b19  ldarg.0
0x13b1a  ldstr    a1spDataconvert_1// "$1SP.DataConvert.createUnspecifiedDateT"...
0x13b1f  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x13b24  starg.s  0
0x13b26  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Client.JsonUtility::s_guidRegEx
0x13b2b  ldarg.0
0x13b2c  ldstr    a1newSpGuid2// "$1new SP.Guid(\"$2\")"
0x13b31  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x13b36  starg.s  0
0x13b38  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.SharePoint.Client.JsonUtility::s_byteArrayRegEx
0x13b3d  ldarg.0
0x13b3e  ldstr    a1newSpBase64en// "$1new SP.Base64EncodedByteArray(\"$2\")"
0x13b43  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x13b48  starg.s  0
0x13b4a  ldarg.0
0x13b4b  ret
```
