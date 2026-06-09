# System.Windows.DependencyProperty::OverrideMetadata

- ea: `0x32a20`
- end: `0x32a5e`
- name: `System.Windows.DependencyProperty::OverrideMetadata`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x32500`
- `0x32d40`

## callees

- `0x2c130`
- `0x32950`
- `0x32a20`
- `0x32ad0`
- `0x32df0`
- `0x32f10`

## string_xrefs

- `0x32a34`: `ReadOnlyOverrideNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x32a20  ldarg.0
0x32a21  ldarg.1
0x32a22  ldarg.2
0x32a23  ldloca.s 0
0x32a25  ldloca.s 1
0x32a27  call     instance void System.Windows.DependencyProperty::SetupOverrideMetadata(class [mscorlib]System.Type forType, class System.Windows.PropertyMetadata typeMetadata, [out] class System.Windows.DependencyObjectType& dType, [out] class System.Windows.PropertyMetadata& baseMetadata)
0x32a2c  ldarg.0
0x32a2d  call     instance bool System.Windows.DependencyProperty::get_ReadOnly()
0x32a32  brfalse.s loc_32A53
0x32a34  ldstr    aReadonlyoverri// "ReadOnlyOverrideNotAllowed"
0x32a39  ldc.i4.1
0x32a3a  newarr   [mscorlib]System.Object
0x32a3f  dup
0x32a40  ldc.i4.0
0x32a41  ldarg.0
0x32a42  call     instance string System.Windows.DependencyProperty::get_Name()
0x32a47  stelem.ref
0x32a48  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x32a4d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x32a52  throw
0x32a53  ldarg.0
0x32a54  ldarg.1
0x32a55  ldarg.2
0x32a56  ldloc.0
0x32a57  ldloc.1
0x32a58  call     instance void System.Windows.DependencyProperty::ProcessOverrideMetadata(class [mscorlib]System.Type forType, class System.Windows.PropertyMetadata typeMetadata, class System.Windows.DependencyObjectType dType, class System.Windows.PropertyMetadata baseMetadata)
0x32a5d  ret
```
