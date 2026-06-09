# System.Xaml.Permissions.XamlLoadPermission::.ctor_1

- ea: `0x126a0`
- end: `0x12710`
- name: `System.Xaml.Permissions.XamlLoadPermission::.ctor_1`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x12980`
- `0x12b30`

## callees

- `0x11f50`
- `0x126a0`
- `0x12730`

## string_xrefs

- `0x126a9`: `allowedAccess`
- `0x126db`: `allowedAccess`

## pseudocode

```c

```

## disassembly

```asm
0x126a0  ldarg.0
0x126a1  call     instance void [mscorlib]System.Security.CodeAccessPermission::.ctor()
0x126a6  ldarg.1
0x126a7  brtrue.s loc_126B4
0x126a9  ldstr    aAllowedaccess// "allowedAccess"
0x126ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x126b3  throw
0x126b4  ldarg.1
0x126b5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.Permissions.XamlAccessLevel>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x126ba  stloc.0
0x126bb  ldarg.1
0x126bc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.Permissions.XamlAccessLevel>::GetEnumerator()
0x126c1  stloc.1
0x126c2  br.s     loc_126F3
0x126c4  ldloc.1
0x126c5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.Permissions.XamlAccessLevel>::get_Current()
0x126ca  stloc.2
0x126cb  ldloc.2
0x126cc  brtrue.s loc_126EC
0x126ce  ldstr    aCollectioncann// "CollectionCannotContainNulls"
0x126d3  ldc.i4.1
0x126d4  newarr   [mscorlib]System.Object
0x126d9  dup
0x126da  ldc.i4.0
0x126db  ldstr    aAllowedaccess// "allowedAccess"
0x126e0  stelem.ref
0x126e1  call     string System.Xaml.SR::Get(string id, object[] args)
0x126e6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x126eb  throw
0x126ec  ldloc.0
0x126ed  ldloc.2
0x126ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Xaml.Permissions.XamlAccessLevel>::Add(var<u1>)
0x126f3  ldloc.1
0x126f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x126f9  brtrue.s loc_126C4
0x126fb  leave.s  loc_12707
0x126fd  ldloc.1
0x126fe  brfalse.s loc_12706
0x12700  ldloc.1
0x12701  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12706  endfinally
0x12707  ldarg.0
0x12708  ldc.i4.0
0x12709  ldloc.0
0x1270a  call     instance void System.Xaml.Permissions.XamlLoadPermission::Init(bool isUnrestricted, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.Permissions.XamlAccessLevel> allowedAccess)
0x1270f  ret
```
