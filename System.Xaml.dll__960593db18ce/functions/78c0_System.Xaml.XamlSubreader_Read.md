# System.Xaml.XamlSubreader::Read

- ea: `0x78c0`
- end: `0x78eb`
- name: `System.Xaml.XamlSubreader::Read`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x78c0`
- `0x7a40`
- `0xb3f0`

## string_xrefs

- `0x78c8`: `XamlReader`

## pseudocode

```c

```

## disassembly

```asm
0x78c0  ldarg.0
0x78c1  call     instance bool System.Xaml.XamlReader::get_IsDisposed()
0x78c6  brfalse.s loc_78D3
0x78c8  ldstr    aXamlreader// "XamlReader"
0x78cd  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x78d2  throw
0x78d3  ldarg.0
0x78d4  ldfld    bool System.Xaml.XamlSubreader::_firstRead
0x78d9  brtrue.s loc_78E2
0x78db  ldarg.0
0x78dc  call     instance bool System.Xaml.XamlSubreader::LimitedRead()
0x78e1  ret
0x78e2  ldarg.0
0x78e3  ldc.i4.0
0x78e4  stfld    bool System.Xaml.XamlSubreader::_firstRead
0x78e9  ldc.i4.1
0x78ea  ret
```
