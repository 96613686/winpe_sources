# System.Web.ApplicationServices.ApplicationServiceHelper::EnsureRoleServiceEnabled

- ea: `0x39320`
- end: `0x3934b`
- name: `System.Web.ApplicationServices.ApplicationServiceHelper::EnsureRoleServiceEnabled`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x2bb40`
- `0x2bb50`
- `0x38f40`
- `0x38f80`

## callees

- `0x280f0`
- `0x39150`
- `0x39320`

## string_xrefs

- `0x39339`: `RoleService`

## pseudocode

```c

```

## disassembly

```asm
0x39320  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_RoleServiceEnabled()
0x39325  brtrue.s loc_3934A
0x39327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3932c  call     string System.Web.Resources.AtlasWeb::get_AppService_Disabled()
0x39331  ldc.i4.1
0x39332  newarr   [mscorlib]System.Object
0x39337  dup
0x39338  ldc.i4.0
0x39339  ldstr    aRoleservice_0// "RoleService"
0x3933e  stelem.ref
0x3933f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39344  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x39349  throw
0x3934a  ret
```
