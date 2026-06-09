# Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::Remove

- ea: `0x151b0`
- end: `0x151c4`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::Remove`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x151d0`

## callees

- `0x15170`
- `0x151b0`
- `0x151e0`

## pseudocode

```c

```

## disassembly

```asm
0x151b0  ldarg.0
0x151b1  ldarg.1
0x151b2  call     instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::IndexOf(class Microsoft.SharePoint.Spx.WebSite.Controls.StockListItem item)
0x151b7  stloc.0
0x151b8  ldloc.0
0x151b9  ldc.i4.0
0x151ba  blt.s    loc_151C3
0x151bc  ldarg.0
0x151bd  ldloc.0
0x151be  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.StockListItemList::RemoveAt(int32 index)
0x151c3  ret
```
