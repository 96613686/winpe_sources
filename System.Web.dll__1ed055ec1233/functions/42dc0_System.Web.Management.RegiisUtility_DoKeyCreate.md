# System.Web.Management.RegiisUtility::DoKeyCreate

- ea: `0x42dc0`
- end: `0x42e55`
- name: `System.Web.Management.RegiisUtility::DoKeyCreate`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x428f0`

## callees

- `0x30d00`
- `0x34fa0`
- `0x42dc0`
- `0x42ff0`

## string_xrefs

- `0x42dcc`: `NetFrameworkConfigurationKey`
- `0x42e01`: `RSA_Key_Container_already_exists`
- `0x42e3e`: `RSA_Key_Container_access_denied`

## pseudocode

```c

```

## disassembly

```asm
0x42dc0  ldarg.1
0x42dc1  brfalse.s loc_42DCC
0x42dc3  ldarg.1
0x42dc4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x42dc9  ldc.i4.1
0x42dca  bge.s    loc_42DD3
0x42dcc  ldstr    aNetframeworkco// "NetFrameworkConfigurationKey"
0x42dd1  starg.s  1
0x42dd3  ldarg.1
0x42dd4  ldarg.2
0x42dd5  ldarg.3
0x42dd6  ldc.i8   0x100000000000
0x42ddf  and
0x42de0  brfalse.s loc_42DE5
0x42de2  ldc.i4.0
0x42de3  br.s     loc_42DE6
0x42de5  ldc.i4.1
0x42de6  call     int32 System.Web.UnsafeNativeMethods::DoesKeyContainerExist(string containerName, string provider, int32 useMachineContainer)
0x42deb  stloc.0
0x42dec  ldloc.0
0x42ded  brfalse.s loc_42E01
0x42def  ldloc.0
0x42df0  ldc.i4   0x80070005
0x42df5  beq.s    loc_42E3E
0x42df7  ldloc.0
0x42df8  ldc.i4   0x80090016
0x42dfd  beq.s    loc_42E11
0x42dff  br.s     loc_42E4E
0x42e01  ldstr    aRsaKeyContaine// "RSA_Key_Container_already_exists"
0x42e06  call     string System.Web.SR::GetString(string name)
0x42e0b  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x42e10  throw
0x42e11  ldarg.0
0x42e12  ldarg.1
0x42e13  ldarg.2
0x42e14  ldarg.3
0x42e15  call     instance class [System.Configuration]System.Configuration.RsaProtectedConfigurationProvider System.Web.Management.RegiisUtility::CreateRSAProvider(string containerName, string csp, int64 options)
0x42e1a  stloc.1
0x42e1b  ldloc.1
0x42e1c  ldarg.s  4
0x42e1e  ldarg.3
0x42e1f  ldc.i8   0x400000000000
0x42e28  and
0x42e29  ldc.i4.0
0x42e2a  conv.i8
0x42e2b  cgt.un
0x42e2d  callvirt instance void [System.Configuration]System.Configuration.RsaProtectedConfigurationProvider::AddKey(int32, bool)
0x42e32  leave.s  loc_42E3D
0x42e34  pop
0x42e35  ldloc.1
0x42e36  callvirt instance void [System.Configuration]System.Configuration.RsaProtectedConfigurationProvider::DeleteKey()
0x42e3b  rethrow
0x42e3d  ret
0x42e3e  ldstr    aRsaKeyContaine_0// "RSA_Key_Container_access_denied"
0x42e43  call     string System.Web.SR::GetString(string name)
0x42e48  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x42e4d  throw
0x42e4e  ldloc.0
0x42e4f  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x42e54  ret
```
