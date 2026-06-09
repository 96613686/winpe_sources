# System.Windows.DependencyProperty::AddOwner_0

- ea: `0x32d40`
- end: `0x32de9`
- name: `System.Windows.DependencyProperty::AddOwner_0`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x32d30`

## callees

- `0x2c130`
- `0x32a20`
- `0x32d40`
- `0x32df0`
- `0x586b0`

## string_xrefs

- `0x32d7e`: `PropertyAlreadyRegistered`

## pseudocode

```c

```

## disassembly

```asm
0x32d40  ldarg.1
0x32d41  ldnull
0x32d42  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x32d47  brfalse.s loc_32D54
0x32d49  ldstr    aOwnertype_0// "ownerType"
0x32d4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x32d53  throw
0x32d54  ldarg.0
0x32d55  call     instance string System.Windows.DependencyProperty::get_Name()
0x32d5a  ldarg.1
0x32d5b  newobj   instance void FromNameKey::.ctor(string name, class [mscorlib]System.Type ownerType)
0x32d60  stloc.0
0x32d61  ldsfld   object System.Windows.DependencyProperty::Synchronized
0x32d66  stloc.1
0x32d67  ldc.i4.0
0x32d68  stloc.2
0x32d69  ldloc.1
0x32d6a  ldloca.s 2
0x32d6c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x32d71  ldsfld   class [mscorlib]System.Collections.Hashtable System.Windows.DependencyProperty::PropertyFromName
0x32d76  ldloc.0
0x32d77  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x32d7c  brfalse.s loc_32DA6
0x32d7e  ldstr    aPropertyalread// "PropertyAlreadyRegistered"
0x32d83  ldc.i4.2
0x32d84  newarr   [mscorlib]System.Object
0x32d89  dup
0x32d8a  ldc.i4.0
0x32d8b  ldarg.0
0x32d8c  call     instance string System.Windows.DependencyProperty::get_Name()
0x32d91  stelem.ref
0x32d92  dup
0x32d93  ldc.i4.1
0x32d94  ldarg.1
0x32d95  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x32d9a  stelem.ref
0x32d9b  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x32da0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32da5  throw
0x32da6  leave.s  loc_32DB2
0x32da8  ldloc.2
0x32da9  brfalse.s loc_32DB1
0x32dab  ldloc.1
0x32dac  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x32db1  endfinally
0x32db2  ldarg.2
0x32db3  brfalse.s loc_32DBD
0x32db5  ldarg.0
0x32db6  ldarg.1
0x32db7  ldarg.2
0x32db8  call     instance void System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type forType, class System.Windows.PropertyMetadata typeMetadata)
0x32dbd  ldsfld   object System.Windows.DependencyProperty::Synchronized
0x32dc2  stloc.3
0x32dc3  ldc.i4.0
0x32dc4  stloc.s  4
0x32dc6  ldloc.3
0x32dc7  ldloca.s 4
0x32dc9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x32dce  ldsfld   class [mscorlib]System.Collections.Hashtable System.Windows.DependencyProperty::PropertyFromName
0x32dd3  ldloc.0
0x32dd4  ldarg.0
0x32dd5  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x32dda  leave.s  loc_32DE7
0x32ddc  ldloc.s  4
0x32dde  brfalse.s loc_32DE6
0x32de0  ldloc.3
0x32de1  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x32de6  endfinally
0x32de7  ldarg.0
0x32de8  ret
```
