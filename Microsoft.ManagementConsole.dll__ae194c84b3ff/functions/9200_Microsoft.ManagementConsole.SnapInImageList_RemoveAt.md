# Microsoft.ManagementConsole.SnapInImageList::RemoveAt

- ea: `0x9200`
- end: `0x9218`
- name: `Microsoft.ManagementConsole.SnapInImageList::RemoveAt`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x9220`

## pseudocode

```c

```

## disassembly

```asm
0x9200  ldarg.0
0x9201  ldfld    class [System.Windows.Forms]System.Windows.Forms.ImageList Microsoft.ManagementConsole.SnapInImageList::_innerList
0x9206  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x920b  ldarg.1
0x920c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::RemoveAt(int32)
0x9211  ldarg.0
0x9212  call     instance void Microsoft.ManagementConsole.SnapInImageList::Notify()
0x9217  ret
```
