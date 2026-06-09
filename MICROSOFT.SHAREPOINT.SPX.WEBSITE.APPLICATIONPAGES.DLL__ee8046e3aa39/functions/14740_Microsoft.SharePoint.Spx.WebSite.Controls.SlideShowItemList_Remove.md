# Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList::Remove

- ea: `0x14740`
- end: `0x14754`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList::Remove`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14760`

## callees

- `0x14700`
- `0x14740`
- `0x14770`

## pseudocode

```c

```

## disassembly

```asm
0x14740  ldarg.0
0x14741  ldarg.1
0x14742  call     instance int32 Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList::IndexOf(class Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItem item)
0x14747  stloc.0
0x14748  ldloc.0
0x14749  ldc.i4.0
0x1474a  blt.s    loc_14753
0x1474c  ldarg.0
0x1474d  ldloc.0
0x1474e  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.SlideShowItemList::RemoveAt(int32 index)
0x14753  ret
```
