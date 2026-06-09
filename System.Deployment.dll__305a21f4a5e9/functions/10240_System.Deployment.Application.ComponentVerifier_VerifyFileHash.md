# System.Deployment.Application.ComponentVerifier::VerifyFileHash

- ea: `0x10240`
- end: `0x102d4`
- name: `System.Deployment.Application.ComponentVerifier::VerifyFileHash`
- size: `148`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x10800`
- `0x13510`
- `0x15190`
- `0x28d50`

## callees

- `0x10160`
- `0x10170`
- `0x10240`
- `0x102e0`
- `0x147a0`
- `0x17cb0`
- `0x23020`
- `0x23300`
- `0x28c80`
- `0x28cb0`

## pseudocode

```c

```

## disassembly

```asm
0x10240  ldarg.0
0x10241  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x10246  stloc.0
0x10247  ldarg.1
0x10248  callvirt instance int32 System.Deployment.Application.HashCollection::get_Count()
0x1024d  brtrue.s loc_102A1
0x1024f  call     bool System.Deployment.Application.PolicyKeys::RequireHashInManifests()
0x10254  brtrue.s loc_1027B
0x10256  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1025b  ldstr    aNohashfile// "NoHashFile"
0x10260  call     string System.Deployment.Application.Resources::GetString(string s)
0x10265  ldc.i4.1
0x10266  newarr   [mscorlib]System.Object
0x1026b  dup
0x1026c  ldc.i4.0
0x1026d  ldloc.0
0x1026e  stelem.ref
0x1026f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10274  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x10279  br.s     loc_102A1
0x1027b  ldc.i4.s 0x19
0x1027d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x10282  ldstr    aExHashnotspeci// "Ex_HashNotSpecified"
0x10287  call     string System.Deployment.Application.Resources::GetString(string s)
0x1028c  ldc.i4.1
0x1028d  newarr   [mscorlib]System.Object
0x10292  dup
0x10293  ldc.i4.0
0x10294  ldloc.0
0x10295  stelem.ref
0x10296  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1029b  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x102a0  throw
0x102a1  ldarg.1
0x102a2  callvirt instance class HashEnumerator System.Deployment.Application.HashCollection::GetEnumerator()
0x102a7  stloc.1
0x102a8  br.s     loc_102B8
0x102aa  ldloc.1
0x102ab  callvirt instance class System.Deployment.Application.Hash HashEnumerator::get_Current()
0x102b0  stloc.2
0x102b1  ldarg.0
0x102b2  ldloc.2
0x102b3  call     void System.Deployment.Application.ComponentVerifier::VerifyFileHash(string filePath, class System.Deployment.Application.Hash hash)
0x102b8  ldloc.1
0x102b9  callvirt instance bool HashEnumerator::MoveNext()
0x102be  brtrue.s loc_102AA
0x102c0  leave.s  loc_102D3
0x102c2  ldloc.1
0x102c3  isinst   [mscorlib]System.IDisposable
0x102c8  stloc.3
0x102c9  ldloc.3
0x102ca  brfalse.s loc_102D2
0x102cc  ldloc.3
0x102cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x102d2  endfinally
0x102d3  ret
```
