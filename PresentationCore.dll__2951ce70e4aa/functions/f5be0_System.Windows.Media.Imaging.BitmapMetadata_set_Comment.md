# System.Windows.Media.Imaging.BitmapMetadata::set_Comment

- ea: `0xf5be0`
- end: `0xf5bed`
- name: `System.Windows.Media.Imaging.BitmapMetadata::set_Comment`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf57d0`

## string_xrefs

- `0xf5be1`: `System.Comment`

## pseudocode

```c

```

## disassembly

```asm
0xf5be0  ldarg.0
0xf5be1  ldstr    aSystemComment// "System.Comment"
0xf5be6  ldarg.1
0xf5be7  call     instance void System.Windows.Media.Imaging.BitmapMetadata::SetQuery(string query, object value)
0xf5bec  ret
```
