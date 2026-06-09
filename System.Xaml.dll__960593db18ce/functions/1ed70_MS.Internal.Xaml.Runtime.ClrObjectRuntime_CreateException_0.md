# MS.Internal.Xaml.Runtime.ClrObjectRuntime::CreateException_0

- ea: `0x1ed70`
- end: `0x1eda1`
- name: `MS.Internal.Xaml.Runtime.ClrObjectRuntime::CreateException_0`
- size: `49`
- prototype: ``
- caller_count: `22`
- callee_count: `5`
- tags: ``

## callers

- `0x1e300`
- `0x1e3a0`
- `0x1e510`
- `0x1e560`
- `0x1e5b0`
- `0x1e5f0`
- `0x1e640`
- `0x1e6a0`
- `0x1e720`
- `0x1e780`
- `0x1e7c0`
- `0x1e800`
- `0x1e850`
- `0x1e9f0`
- `0x1ea30`
- `0x1ea80`
- `0x1eac0`
- `0x1eb00`
- `0x1ebb0`
- `0x1ec30`
- `0x1ed60`
- `0x1edb0`

## callees

- `0x85a0`
- `0x8820`
- `0x1ed70`
- `0x201c0`
- `0x201e0`

## pseudocode

```c

```

## disassembly

```asm
0x1ed70  ldarg.0
0x1ed71  ldfld    bool MS.Internal.Xaml.Runtime.ClrObjectRuntime::_isWriter
0x1ed76  brfalse.s loc_1ED82
0x1ed78  ldarg.1
0x1ed79  ldarg.2
0x1ed7a  newobj   instance void System.Xaml.XamlObjectWriterException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x1ed7f  stloc.0
0x1ed80  br.s     loc_1ED8A
0x1ed82  ldarg.1
0x1ed83  ldarg.2
0x1ed84  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x1ed89  stloc.0
0x1ed8a  ldarg.0
0x1ed8b  callvirt instance class MS.Internal.Xaml.Runtime.IAddLineInfo MS.Internal.Xaml.Runtime.XamlRuntime::get_LineInfo()
0x1ed90  brtrue.s loc_1ED94
0x1ed92  ldloc.0
0x1ed93  ret
0x1ed94  ldarg.0
0x1ed95  callvirt instance class MS.Internal.Xaml.Runtime.IAddLineInfo MS.Internal.Xaml.Runtime.XamlRuntime::get_LineInfo()
0x1ed9a  ldloc.0
0x1ed9b  callvirt instance class System.Xaml.XamlException MS.Internal.Xaml.Runtime.IAddLineInfo::WithLineInfo(class System.Xaml.XamlException ex)
0x1eda0  ret
```
