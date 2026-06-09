# Microsoft.SharePoint.Client.CompMgr::LogWrapper

- ea: `0x17750`
- end: `0x17771`
- name: `Microsoft.SharePoint.Client.CompMgr::LogWrapper`
- size: `33`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17610`
- `0x17640`
- `0x176c0`
- `0x176e0`
- `0x177c0`

## callees

- `0x17750`

## string_xrefs

- `0x1775e`: `Init Component Manager: `

## pseudocode

```c

```

## disassembly

```asm
0x17750  ldarg.0
0x17751  ldfld    class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.LoggerDelegate Microsoft.SharePoint.Client.CompMgr::logger
0x17756  brfalse.s loc_17770
0x17758  ldarg.0
0x17759  ldfld    class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.LoggerDelegate Microsoft.SharePoint.Client.CompMgr::logger
0x1775e  ldstr    aInitComponentM// "Init Component Manager: "
0x17763  ldarg.1
0x17764  call     string [mscorlib]System.String::Concat(string, string)
0x17769  ldarg.2
0x1776a  conv.i2
0x1776b  callvirt instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.LoggerDelegate::Invoke(string, int16)
0x17770  ret
```
