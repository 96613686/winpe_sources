# System.Xaml.Permissions.XamlLoadPermission::.ctor_0

- ea: `0x12670`
- end: `0x12696`
- name: `System.Xaml.Permissions.XamlLoadPermission::.ctor_0`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1ef00`

## callees

- `0x12670`
- `0x12730`

## string_xrefs

- `0x12679`: `allowedAccess`

## pseudocode

```c

```

## disassembly

```asm
0x12670  ldarg.0
0x12671  call     instance void [mscorlib]System.Security.CodeAccessPermission::.ctor()
0x12676  ldarg.1
0x12677  brtrue.s loc_12684
0x12679  ldstr    aAllowedaccess// "allowedAccess"
0x1267e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12683  throw
0x12684  ldarg.0
0x12685  ldc.i4.0
0x12686  ldc.i4.1
0x12687  newarr   System.Xaml.Permissions.XamlAccessLevel
0x1268c  dup
0x1268d  ldc.i4.0
0x1268e  ldarg.1
0x1268f  stelem.ref
0x12690  call     instance void System.Xaml.Permissions.XamlLoadPermission::Init(bool isUnrestricted, class [mscorlib]System.Collections.Generic.IList`1<class System.Xaml.Permissions.XamlAccessLevel> allowedAccess)
0x12695  ret
```
