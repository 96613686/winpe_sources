# System.Web.Configuration.HandlerBase::CheckAndReadRegistryValue

- ea: `0x143ea0`
- end: `0x143ef1`
- name: `System.Web.Configuration.HandlerBase::CheckAndReadRegistryValue`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140250`
- `0x143f00`
- `0x14ae60`

## callees

- `0x30740`
- `0x34fa0`
- `0x58f20`
- `0x143ea0`

## string_xrefs

- `0x143edf`: `Invalid_registry_config`
- `0x143ea8`: `registry:`

## pseudocode

```c

```

## disassembly

```asm
0x143ea0  ldarg.0
0x143ea1  ldind.ref
0x143ea2  brtrue.s loc_143EA6
0x143ea4  ldc.i4.1
0x143ea5  ret
0x143ea6  ldarg.0
0x143ea7  ldind.ref
0x143ea8  ldstr    aRegistry// "registry:"
0x143ead  call     bool System.Web.Util.StringUtil::StringStartsWithIgnoreCase(string s1, string s2)
0x143eb2  brtrue.s loc_143EB6
0x143eb4  ldc.i4.1
0x143eb5  ret
0x143eb6  ldc.i4   0x400
0x143ebb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x143ec0  stloc.0
0x143ec1  ldarg.0
0x143ec2  ldind.ref
0x143ec3  ldloc.0
0x143ec4  ldc.i4   0x400
0x143ec9  call     int32 System.Web.UnsafeNativeMethods::GetCredentialFromRegistry(string strRegKey, class [mscorlib]System.Text.StringBuilder buffer, int32 size)
0x143ece  stloc.1
0x143ecf  ldloc.1
0x143ed0  brtrue.s loc_143EDC
0x143ed2  ldarg.0
0x143ed3  ldloc.0
0x143ed4  callvirt instance string [mscorlib]System.Object::ToString()
0x143ed9  stind.ref
0x143eda  ldc.i4.1
0x143edb  ret
0x143edc  ldarg.1
0x143edd  brfalse.s loc_143EEF
0x143edf  ldstr    aInvalidRegistr// "Invalid_registry_config"
0x143ee4  call     string System.Web.SR::GetString(string name)
0x143ee9  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string)
0x143eee  throw
0x143eef  ldc.i4.0
0x143ef0  ret
```
