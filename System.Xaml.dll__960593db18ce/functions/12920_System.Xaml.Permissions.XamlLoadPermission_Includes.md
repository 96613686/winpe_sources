# System.Xaml.Permissions.XamlLoadPermission::Includes

- ea: `0x12920`
- end: `0x12972`
- name: `System.Xaml.Permissions.XamlLoadPermission::Includes`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x12980`
- `0x12a20`
- `0x12b30`

## callees

- `0x12570`
- `0x12770`
- `0x12920`

## string_xrefs

- `0x12923`: `requestedAccess`

## pseudocode

```c

```

## disassembly

```asm
0x12920  ldarg.1
0x12921  brtrue.s loc_1292E
0x12923  ldstr    aRequestedacces// "requestedAccess"
0x12928  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1292d  throw
0x1292e  ldarg.0
0x1292f  ldfld    bool System.Xaml.Permissions.XamlLoadPermission::_isUnrestricted
0x12934  brfalse.s loc_12938
0x12936  ldc.i4.1
0x12937  ret
0x12938  ldarg.0
0x12939  call     instance class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.Permissions.XamlAccessLevel> System.Xaml.Permissions.XamlLoadPermission::get_AllowedAccess()
0x1293e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Xaml.Permissions.XamlAccessLevel>::GetEnumerator()
0x12943  stloc.0
0x12944  br.s     loc_1295A
0x12946  ldloc.0
0x12947  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xaml.Permissions.XamlAccessLevel>::get_Current()
0x1294c  stloc.1
0x1294d  ldloc.1
0x1294e  ldarg.1
0x1294f  callvirt instance bool System.Xaml.Permissions.XamlAccessLevel::Includes(class System.Xaml.Permissions.XamlAccessLevel other)
0x12954  brfalse.s loc_1295A
0x12956  ldc.i4.1
0x12957  stloc.2
0x12958  leave.s  loc_12970
0x1295a  ldloc.0
0x1295b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12960  brtrue.s loc_12946
0x12962  leave.s  loc_1296E
0x12964  ldloc.0
0x12965  brfalse.s loc_1296D
0x12967  ldloc.0
0x12968  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1296d  endfinally
0x1296e  ldc.i4.0
0x1296f  ret
0x12970  ldloc.2
0x12971  ret
```
