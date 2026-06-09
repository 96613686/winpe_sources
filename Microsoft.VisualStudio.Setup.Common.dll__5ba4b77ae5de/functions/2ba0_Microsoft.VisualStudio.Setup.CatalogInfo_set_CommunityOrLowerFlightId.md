# Microsoft.VisualStudio.Setup.CatalogInfo::set_CommunityOrLowerFlightId

- ea: `0x2ba0`
- end: `0x2bad`
- name: `Microsoft.VisualStudio.Setup.CatalogInfo::set_CommunityOrLowerFlightId`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4df0`

## string_xrefs

- `0x2ba1`: `CommunityOrLowerFlightId`

## pseudocode

```c

```

## disassembly

```asm
0x2ba0  ldarg.0
0x2ba1  ldstr    aCommunityorlow// "CommunityOrLowerFlightId"
0x2ba6  ldarg.1
0x2ba7  call     instance void Microsoft.VisualStudio.Setup.ExtensibleObject::set_Item(string key, string value)
0x2bac  ret
```
