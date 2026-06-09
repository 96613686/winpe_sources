# MS.Internal.TraceMarkup::get_CreateMarkupExtension

- ea: `0x1ddaf0`
- end: `0x1ddb26`
- name: `MS.Internal.TraceMarkup::get_CreateMarkupExtension`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x8fda0`

## callees

- `0x1ddaf0`

## string_xrefs

- `0x1ddb10`: `MarkupExtension`
- `0x1ddb00`: `Create MarkupExtension`

## pseudocode

```c

```

## disassembly

```asm
0x1ddaf0  ldsfld   class [WindowsBase]MS.Internal.AvTraceDetails MS.Internal.TraceMarkup::_CreateMarkupExtension
0x1ddaf5  brtrue.s loc_1DDB20
0x1ddaf7  ldc.i4.6
0x1ddaf8  ldc.i4.3
0x1ddaf9  newarr   [mscorlib]System.String
0x1ddafe  dup
0x1ddaff  ldc.i4.0
0x1ddb00  ldstr    aCreateMarkupex// "Create MarkupExtension"
0x1ddb05  stelem.ref
0x1ddb06  dup
0x1ddb07  ldc.i4.1
0x1ddb08  ldstr    aType_3// "Type"
0x1ddb0d  stelem.ref
0x1ddb0e  dup
0x1ddb0f  ldc.i4.2
0x1ddb10  ldstr    aMarkupextensio_2// "MarkupExtension"
0x1ddb15  stelem.ref
0x1ddb16  newobj   instance void [WindowsBase]MS.Internal.AvTraceDetails::.ctor(int32, string[])
0x1ddb1b  stsfld   class [WindowsBase]MS.Internal.AvTraceDetails MS.Internal.TraceMarkup::_CreateMarkupExtension
0x1ddb20  ldsfld   class [WindowsBase]MS.Internal.AvTraceDetails MS.Internal.TraceMarkup::_CreateMarkupExtension
0x1ddb25  ret
```
