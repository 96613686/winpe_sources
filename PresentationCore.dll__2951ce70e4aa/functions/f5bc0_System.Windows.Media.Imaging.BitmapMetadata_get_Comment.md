# System.Windows.Media.Imaging.BitmapMetadata::get_Comment

- ea: `0xf5bc0`
- end: `0xf5bd1`
- name: `System.Windows.Media.Imaging.BitmapMetadata::get_Comment`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf58f0`

## string_xrefs

- `0xf5bc1`: `System.Comment`

## pseudocode

```c

```

## disassembly

```asm
0xf5bc0  ldarg.0
0xf5bc1  ldstr    aSystemComment// "System.Comment"
0xf5bc6  call     instance object System.Windows.Media.Imaging.BitmapMetadata::GetQuery(string query)
0xf5bcb  isinst   [mscorlib]System.String
0xf5bd0  ret
```
