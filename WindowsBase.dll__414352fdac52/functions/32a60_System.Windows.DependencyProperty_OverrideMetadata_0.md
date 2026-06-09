# System.Windows.DependencyProperty::OverrideMetadata_0

- ea: `0x32a60`
- end: `0x32ace`
- name: `System.Windows.DependencyProperty::OverrideMetadata_0`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x32550`
- `0x33250`

## callees

- `0x2c100`
- `0x2c130`
- `0x32950`
- `0x32a60`
- `0x32ad0`
- `0x32df0`
- `0x32f10`
- `0x32f30`
- `0x33230`

## string_xrefs

- `0x32a8b`: `ReadOnlyOverrideKeyNotAuthorized`
- `0x32ab3`: `PropertyNotReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x32a60  ldarg.0
0x32a61  ldarg.1
0x32a62  ldarg.2
0x32a63  ldloca.s 0
0x32a65  ldloca.s 1
0x32a67  call     instance void System.Windows.DependencyProperty::SetupOverrideMetadata(class [mscorlib]System.Type forType, class System.Windows.PropertyMetadata typeMetadata, [out] class System.Windows.DependencyObjectType& dType, [out] class System.Windows.PropertyMetadata& baseMetadata)
0x32a6c  ldarg.3
0x32a6d  brtrue.s loc_32A7A
0x32a6f  ldstr    aKey// "key"
0x32a74  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32a79  throw
0x32a7a  ldarg.0
0x32a7b  call     instance bool System.Windows.DependencyProperty::get_ReadOnly()
0x32a80  brfalse.s loc_32AB3
0x32a82  ldarg.3
0x32a83  callvirt instance class System.Windows.DependencyProperty System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x32a88  ldarg.0
0x32a89  beq.s    loc_32AAA
0x32a8b  ldstr    aReadonlyoverri_0// "ReadOnlyOverrideKeyNotAuthorized"
0x32a90  ldc.i4.1
0x32a91  newarr   [mscorlib]System.Object
0x32a96  dup
0x32a97  ldc.i4.0
0x32a98  ldarg.0
0x32a99  call     instance string System.Windows.DependencyProperty::get_Name()
0x32a9e  stelem.ref
0x32a9f  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x32aa4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32aa9  throw
0x32aaa  ldarg.0
0x32aab  ldarg.3
0x32aac  call     instance void System.Windows.DependencyProperty::VerifyReadOnlyKey(class System.Windows.DependencyPropertyKey candidateKey)
0x32ab1  br.s     loc_32AC3
0x32ab3  ldstr    aPropertynotrea// "PropertyNotReadOnly"
0x32ab8  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x32abd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x32ac2  throw
0x32ac3  ldarg.0
0x32ac4  ldarg.1
0x32ac5  ldarg.2
0x32ac6  ldloc.0
0x32ac7  ldloc.1
0x32ac8  call     instance void System.Windows.DependencyProperty::ProcessOverrideMetadata(class [mscorlib]System.Type forType, class System.Windows.PropertyMetadata typeMetadata, class System.Windows.DependencyObjectType dType, class System.Windows.PropertyMetadata baseMetadata)
0x32acd  ret
```
