# Microsoft.SharePoint.Taxonomy.TermStore::CommitAll

- ea: `0x53f80`
- end: `0x53fbe`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::CommitAll`
- size: `62`
- prototype: ``
- caller_count: `40`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2760`
- `0x2a00`
- `0x57c0`
- `0x63a0`
- `0x65a0`
- `0x6c50`
- `0x6d40`
- `0x6e60`
- `0x8350`
- `0x8cb0`
- `0x8ea0`
- `0x94d0`
- `0x95b0`
- `0x96c0`
- `0x145d0`
- `0x40140`
- `0x45790`
- `0x465b0`
- `0x48d90`
- `0x49a20`
- `0x4a280`
- `0x4aae0`
- `0x540c0`
- `0x55460`
- `0x57800`
- `0x62000`
- `0x62970`
- `0x69710`
- `0x69c00`
- `0x6d0b0`
- `0x6d360`
- `0x6d560`
- `0x6d8e0`
- `0x6dc20`
- `0x6e150`
- `0x6e3b0`
- `0x6e6e0`
- `0x6e7e0`
- `0x6e8d0`
- `0x6ebd0`

## callees

- `0x2b020`
- `0x56c30`
- `0x57230`

## string_xrefs

- `0x53f8c`: `Begin: TermStore.CommitAll()`
- `0x53fb3`: `End: TermStore.CommitAll()`

## pseudocode

```c

```

## disassembly

```asm
0x53f80  ldc.i4   0x3778736A
0x53f85  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x53f8a  ldc.i4.s 0x64
0x53f8c  ldstr    aBeginTermstore_0// "Begin: TermStore.CommitAll()"
0x53f91  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x53f96  ldarg.0
0x53f97  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::RequireOnline()
0x53f9c  ldarg.0
0x53f9d  call     instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x53fa2  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CommitSandbox()
0x53fa7  ldc.i4   0x3778736B
0x53fac  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x53fb1  ldc.i4.s 0x64
0x53fb3  ldstr    aEndTermstoreCo// "End: TermStore.CommitAll()"
0x53fb8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x53fbd  ret
```
