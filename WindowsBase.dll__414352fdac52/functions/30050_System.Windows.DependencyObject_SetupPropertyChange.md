# System.Windows.DependencyObject::SetupPropertyChange

- ea: `0x30050`
- end: `0x30092`
- name: `System.Windows.DependencyObject::SetupPropertyChange`
- size: `66`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x2ff20`
- `0x2ff40`
- `0x2ff80`
- `0x2ffa0`
- `0x2ffc0`
- `0x2ffe0`
- `0x30000`
- `0x30460`

## callees

- `0x2c130`
- `0x2fb30`
- `0x30050`
- `0x32c60`
- `0x32df0`
- `0x32f10`

## string_xrefs

- `0x30068`: `ReadOnlyChangeNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x30050  ldarg.1
0x30051  brfalse.s loc_30087
0x30053  ldarg.1
0x30054  callvirt instance bool System.Windows.DependencyProperty::get_ReadOnly()
0x30059  brtrue.s loc_30068
0x3005b  ldarg.1
0x3005c  ldarg.0
0x3005d  call     instance class System.Windows.DependencyObjectType System.Windows.DependencyObject::get_DependencyObjectType()
0x30062  callvirt instance class System.Windows.PropertyMetadata System.Windows.DependencyProperty::GetMetadata(class System.Windows.DependencyObjectType dependencyObjectType)
0x30067  ret
0x30068  ldstr    aReadonlychange// "ReadOnlyChangeNotAllowed"
0x3006d  ldc.i4.1
0x3006e  newarr   [mscorlib]System.Object
0x30073  dup
0x30074  ldc.i4.0
0x30075  ldarg.1
0x30076  callvirt instance string System.Windows.DependencyProperty::get_Name()
0x3007b  stelem.ref
0x3007c  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x30081  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x30086  throw
0x30087  ldstr    aDp_0// "dp"
0x3008c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x30091  throw
```
