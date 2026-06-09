# Microsoft.SharePoint.Client.CompMgr::GetCompMgrName

- ea: `0x177b0`
- end: `0x177bc`
- name: `Microsoft.SharePoint.Client.CompMgr::GetCompMgrName`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x17780`

## string_xrefs

- `0x177b1`: `\compmgr.dll`

## pseudocode

```c

```

## disassembly

```asm
0x177b0  ldarg.1
0x177b1  ldstr    aCompmgrDll_0// "\\compmgr.dll"
0x177b6  call     string [mscorlib]System.String::Concat(string, string)
0x177bb  ret
```
