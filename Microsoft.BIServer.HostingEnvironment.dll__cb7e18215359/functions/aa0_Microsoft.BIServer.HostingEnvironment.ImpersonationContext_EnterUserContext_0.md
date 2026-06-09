# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterUserContext_0

- ea: `0xaa0`
- end: `0xabf`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterUserContext_0`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xaa0`
- `0xb20`

## string_xrefs

- `0xaad`: `[0] is not a valid USER token.  If you want to revert to service credentials, use EnterServiceAccountContext()`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xaa6  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0xaab  brfalse.s loc_AB8
0xaad  ldstr    a0IsNotAValidUs// "[0] is not a valid USER token.  If you "...
0xab2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xab7  throw
0xab8  ldarg.0
0xab9  newobj   instance void Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor(native int userToken)
0xabe  ret
```
