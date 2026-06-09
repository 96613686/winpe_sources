# System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::ValidateUserByCallingLogin

- ea: `0x339a0`
- end: `0x33a1c`
- name: `System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider::ValidateUserByCallingLogin`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x33960`
- `0x33e40`

## callees

- `0x339a0`
- `0x36b00`

## string_xrefs

- `0x339cf`: `createPersistentCookie`

## pseudocode

```c

```

## disassembly

```asm
0x339a0  ldarg.s  4
0x339a2  brfalse.s loc_339AA
0x339a4  newobj   instance void [mscorlib]System.NotImplementedException::.ctor()
0x339a9  throw
0x339aa  ldarg.3
0x339ab  ldstr    aLogin// "/Login"
0x339b0  call     string [mscorlib]System.String::Concat(string, string)
0x339b5  starg.s  3
0x339b7  ldc.i4.3
0x339b8  newarr   [mscorlib]System.String
0x339bd  dup
0x339be  ldc.i4.0
0x339bf  ldstr    aUsername// "userName"
0x339c4  stelem.ref
0x339c5  dup
0x339c6  ldc.i4.1
0x339c7  ldstr    aPassword// "password"
0x339cc  stelem.ref
0x339cd  dup
0x339ce  ldc.i4.2
0x339cf  ldstr    aCreatepersiste// "createPersistentCookie"
0x339d4  stelem.ref
0x339d5  stloc.0
0x339d6  ldc.i4.3
0x339d7  newarr   [mscorlib]System.Object
0x339dc  dup
0x339dd  ldc.i4.0
0x339de  ldarg.0
0x339df  stelem.ref
0x339e0  dup
0x339e1  ldc.i4.1
0x339e2  ldarg.1
0x339e3  stelem.ref
0x339e4  dup
0x339e5  ldc.i4.2
0x339e6  ldarg.2
0x339e7  box      [mscorlib]System.Boolean
0x339ec  stelem.ref
0x339ed  stloc.1
0x339ee  ldarg.3
0x339ef  ldarg.s  5
0x339f1  ldarg.0
0x339f2  ldarg.s  6
0x339f4  ldarg.s  7
0x339f6  ldloc.0
0x339f7  ldloc.1
0x339f8  ldtoken  [mscorlib]System.Boolean
0x339fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33a02  call     object System.Web.ClientServices.Providers.ProxyHelper::CreateWebRequestAndGetResponse(string serverUri, class [System]System.Net.CookieContainer& cookies, string username, string connectionString, string connectionStringProvider, string[] paramNames, object[] paramValues, class [mscorlib]System.Type returnType)
0x33a07  stloc.2
0x33a08  ldloc.2
0x33a09  brfalse.s loc_33A1A
0x33a0b  ldloc.2
0x33a0c  isinst   [mscorlib]System.Boolean
0x33a11  brfalse.s loc_33A1A
0x33a13  ldloc.2
0x33a14  unbox.any [mscorlib]System.Boolean
0x33a19  ret
0x33a1a  ldc.i4.0
0x33a1b  ret
```
