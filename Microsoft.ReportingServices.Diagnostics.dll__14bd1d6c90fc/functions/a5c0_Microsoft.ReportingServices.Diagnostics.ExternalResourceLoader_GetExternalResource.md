# Microsoft.ReportingServices.Diagnostics.ExternalResourceLoader::GetExternalResource

- ea: `0xa5c0`
- end: `0xa6f9`
- name: `Microsoft.ReportingServices.Diagnostics.ExternalResourceLoader::GetExternalResource`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa5c0`
- `0xa720`
- `0xa760`

## pseudocode

```c

```

## disassembly

```asm
0xa5c0  ldnull
0xa5c1  stloc.0
0xa5c2  ldarg.s  8
0xa5c4  ldnull
0xa5c5  stind.ref
0xa5c6  ldarg.0
0xa5c7  newobj   instance void [System]System.Uri::.ctor(string)
0xa5cc  stloc.1
0xa5cd  ldloc.1
0xa5ce  callvirt instance bool [System]System.Uri::get_IsFile()
0xa5d3  brfalse.s loc_A5E3
0xa5d5  ldloc.1
0xa5d6  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0xa5db  castclass [System]System.Net.FileWebRequest
0xa5e0  stloc.2
0xa5e1  br.s     loc_A5EF
0xa5e3  ldloc.1
0xa5e4  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0xa5e9  castclass [System]System.Net.HttpWebRequest
0xa5ee  stloc.2
0xa5ef  ldc.i4   0x927C0
0xa5f4  stloc.3
0xa5f5  ldarg.s  5
0xa5f7  ldc.i4.0
0xa5f8  ble.s    loc_A613
0xa5fa  ldarg.s  5
0xa5fc  ldc.i4   0x20C49B
0xa601  bge.s    loc_A613
0xa603  ldloc.2
0xa604  ldarg.s  5
0xa606  ldc.i4   0x3E8
0xa60b  mul
0xa60c  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0xa611  br.s     loc_A61A
0xa613  ldloc.2
0xa614  ldloc.3
0xa615  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0xa61a  ldarg.2
0xa61b  brfalse.s loc_A62E
0xa61d  ldloc.2
0xa61e  ldarg.2
0xa61f  ldarg.3
0xa620  ldarg.s  4
0xa622  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string, string)
0xa627  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0xa62c  br.s     loc_A645
0xa62e  ldarg.1
0xa62f  brfalse.s loc_A63E
0xa631  ldloc.2
0xa632  call     class [System]System.Net.ICredentials [System]System.Net.CredentialCache::get_DefaultCredentials()
0xa637  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0xa63c  br.s     loc_A645
0xa63e  ldloc.2
0xa63f  ldnull
0xa640  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0xa645  ldarg.s  9
0xa647  ldc.i4.0
0xa648  stind.i1
0xa649  ldloc.2
0xa64a  ldarg.s  7
0xa64c  call     class [System]System.Net.WebResponse Microsoft.ReportingServices.Diagnostics.ExternalResourceLoader::RequestExternalResource(class [System]System.Net.WebRequest request, class Microsoft.ReportingServices.Diagnostics.ExternalResourceAbortHelper abortHelper)
0xa651  stloc.s  4
0xa653  ldarg.s  8
0xa655  ldloc.s  4
0xa657  callvirt instance string [System]System.Net.WebResponse::get_ContentType()
0xa65c  stind.ref
0xa65d  ldloc.s  4
0xa65f  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0xa664  stloc.s  5
0xa666  ldarg.s  6
0xa668  ldsfld   int32 Microsoft.ReportingServices.Diagnostics.ExternalResourceLoader::MaxResourceSizeUnlimited
0xa66d  bne.un.s loc_A67E
0xa66f  ldloc.s  5
0xa671  ldc.i4   0x400
0xa676  call     unsigned int8[] [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport::ReadToEndNotUsingLength(class [mscorlib]System.IO.Stream, int32)
0xa67b  stloc.0
0xa67c  leave.s  loc_A6A9
0xa67e  ldloc.s  5
0xa680  ldc.i4   0x400
0xa685  ldarg.s  6
0xa687  ldarg.s  9
0xa689  call     unsigned int8[] [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport::ReadToEndNotUsingLength(class [mscorlib]System.IO.Stream, int32, int32, bool&)
0xa68e  stloc.0
0xa68f  leave.s  loc_A6A9
0xa691  ldloc.s  5
0xa693  brfalse.s loc_A69C
0xa695  ldloc.s  5
0xa697  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa69c  endfinally
0xa69d  ldloc.s  4
0xa69f  brfalse.s loc_A6A8
0xa6a1  ldloc.s  4
0xa6a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6a8  endfinally
0xa6a9  ldloc.1
0xa6aa  callvirt instance bool [System]System.Uri::get_IsFile()
0xa6af  brfalse.s loc_A6F7
0xa6b1  ldarg.s  9
0xa6b3  ldind.u1
0xa6b4  brtrue.s loc_A6F7
0xa6b6  ldloc.1
0xa6b7  callvirt instance string [System]System.Uri::get_LocalPath()
0xa6bc  call     string [mscorlib]System.IO.Path::GetExtension(string)
0xa6c1  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xa6c6  stloc.s  6
0xa6c8  ldloc.s  6
0xa6ca  brfalse.s loc_A6E5
0xa6cc  ldloc.s  6
0xa6ce  ldstr    asc_122DC// "."
0xa6d3  ldc.i4.4
0xa6d4  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xa6d9  brfalse.s loc_A6E5
0xa6db  ldloc.s  6
0xa6dd  ldc.i4.1
0xa6de  callvirt instance string [mscorlib]System.String::Substring(int32)
0xa6e3  stloc.s  6
0xa6e5  ldloc.s  6
0xa6e7  call     string Microsoft.ReportingServices.Diagnostics.ExternalResourceLoader::GetMimeTypeByRegistryLookup(string extension)
0xa6ec  stloc.s  7
0xa6ee  ldloc.s  7
0xa6f0  brfalse.s loc_A6F7
0xa6f2  ldarg.s  8
0xa6f4  ldloc.s  7
0xa6f6  stind.ref
0xa6f7  ldloc.0
0xa6f8  ret
```
