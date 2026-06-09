# Microsoft.VisualStudio.Setup.CatalogInfo::get_CommunityOrLowerFlightId

- ea: `0x2b90`
- end: `0x2b9c`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::get_CommunityOrLowerFlightId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4dd0`

## string_xrefs

- `0x2b91`: `CommunityOrLowerFlightId`

## pseudocode

```c

```

## disassembly

```asm
0x2b90  ldarg.0
0x2b91  ldstr    aCommunityorlow// "CommunityOrLowerFlightId"
0x2b96  call     instance string Microsoft.VisualStudio.Setup.ExtensibleObject::get_Item(string key)
0x2b9b  ret
```
