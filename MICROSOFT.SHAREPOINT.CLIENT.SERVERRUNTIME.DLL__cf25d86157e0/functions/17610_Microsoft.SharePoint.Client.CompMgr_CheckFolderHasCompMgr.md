# Microsoft.SharePoint.Client.CompMgr::CheckFolderHasCompMgr

- ea: `0x17610`
- end: `0x17635`
- name: `Microsoft.SharePoint.Client.CompMgr::CheckFolderHasCompMgr`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x17640`

## callees

- `0x17750`

## string_xrefs

- `0x17611`: `CheckFolderHasCompMgr:Checking `
- `0x17623`: `compmgr.dll`

## pseudocode

```c

```

## disassembly

```asm
0x17610  ldarg.0
0x17611  ldstr    aCheckfolderhas// "CheckFolderHasCompMgr:Checking "
0x17616  ldarg.1
0x17617  call     string [mscorlib]System.String::Concat(string, string)
0x1761c  ldc.i4.3
0x1761d  call     instance void Microsoft.SharePoint.Client.CompMgr::LogWrapper(string s, valuetype [System]System.Diagnostics.TraceLevel level)
0x17622  ldarg.1
0x17623  ldstr    aCompmgrDll// "compmgr.dll"
0x17628  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1762d  stloc.0
0x1762e  ldloc.0
0x1762f  call     bool [mscorlib]System.IO.File::Exists(string)
0x17634  ret
```
