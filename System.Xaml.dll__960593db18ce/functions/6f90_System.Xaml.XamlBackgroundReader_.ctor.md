# System.Xaml.XamlBackgroundReader::.ctor

- ea: `0x6f90`
- end: `0x6fae`
- name: `System.Xaml.XamlBackgroundReader::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x6f90`
- `0x6fb0`
- `0xb470`

## string_xrefs

- `0x6f99`: `wrappedReader`

## pseudocode

```c

```

## disassembly

```asm
0x6f90  ldarg.0
0x6f91  call     instance void System.Xaml.XamlReader::.ctor()
0x6f96  ldarg.1
0x6f97  brtrue.s loc_6FA4
0x6f99  ldstr    aWrappedreader// "wrappedReader"
0x6f9e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6fa3  throw
0x6fa4  ldarg.0
0x6fa5  ldarg.1
0x6fa6  ldc.i4.s 0x40
0x6fa8  call     instance void System.Xaml.XamlBackgroundReader::Initialize(class System.Xaml.XamlReader wrappedReader, int32 bufferSize)
0x6fad  ret
```
