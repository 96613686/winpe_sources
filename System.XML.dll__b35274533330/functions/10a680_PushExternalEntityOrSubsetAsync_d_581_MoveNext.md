# <PushExternalEntityOrSubsetAsync>d__581::MoveNext

- ea: `0x10a680`
- end: `0x10a8cd`
- name: `<PushExternalEntityOrSubsetAsync>d__581::MoveNext`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x127e0`
- `0x136f0`
- `0x29770`
- `0x29840`
- `0x298d0`
- `0x35030`
- `0x10a680`

## string_xrefs

- `0x10a7fd`: `Xml_ErrorOpeningExternalEntity`
- `0x10a804`: `Xml_ErrorOpeningExternalDtd`
- `0x10a83b`: `Xml_CannotResolveExternalSubset`
- `0x10a879`: `Xml_CannotResolveEntity`
- `0x10a880`: `Xml_CannotResolveEntityDtdIgnored`

## pseudocode

```c

```

## disassembly

```asm
0x10a680  ldarg.0
0x10a681  ldfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a686  stloc.0
0x10a687  ldarg.0
0x10a688  ldfld    class System.Xml.XmlTextReaderImpl <PushExternalEntityOrSubsetAsync>d__581::<>4__this
0x10a68d  stloc.1
0x10a68e  ldloc.0
0x10a68f  brfalse.s loc_10A6A8
0x10a691  ldloc.0
0x10a692  ldc.i4.1
0x10a693  beq      loc_10A75F
0x10a698  ldarg.0
0x10a699  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::publicId
0x10a69e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10a6a3  brtrue   loc_10A742
0x10a6a8  nop
0x10a6a9  ldloc.0
0x10a6aa  brfalse.s loc_10A711
0x10a6ac  ldarg.0
0x10a6ad  ldloc.1
0x10a6ae  ldfld    class System.Xml.XmlResolver System.Xml.XmlTextReaderImpl::xmlResolver
0x10a6b3  ldarg.0
0x10a6b4  ldfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::baseUri
0x10a6b9  ldarg.0
0x10a6ba  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::publicId
0x10a6bf  callvirt instance class [System]System.Uri System.Xml.XmlResolver::ResolveUri(class [System]System.Uri baseUri, string relativeUri)
0x10a6c4  stfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a6c9  ldloc.1
0x10a6ca  ldarg.0
0x10a6cb  ldfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a6d0  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::OpenAndPushAsync(class [System]System.Uri uri)
0x10a6d5  ldc.i4.0
0x10a6d6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x10a6db  stloc.s  4
0x10a6dd  ldloca.s 4
0x10a6df  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x10a6e4  stloc.3
0x10a6e5  ldloca.s 3
0x10a6e7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x10a6ec  brtrue.s loc_10A72D
0x10a6ee  ldarg.0
0x10a6ef  ldc.i4.0
0x10a6f0  dup
0x10a6f1  stloc.0
0x10a6f2  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a6f7  ldarg.0
0x10a6f8  ldloc.3
0x10a6f9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a6fe  ldarg.0
0x10a6ff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PushExternalEntityOrSubsetAsync>d__581::<>t__builder
0x10a704  ldloca.s 3
0x10a706  ldarg.0
0x10a707  call     T0x2B000221
0x10a70c  leave    loc_10A8CC
0x10a711  ldarg.0
0x10a712  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a717  stloc.3
0x10a718  ldarg.0
0x10a719  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a71e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x10a724  ldarg.0
0x10a725  ldc.i4.m1
0x10a726  dup
0x10a727  stloc.0
0x10a728  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a72d  ldloca.s 3
0x10a72f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x10a734  stloc.2
0x10a735  ldloc.2
0x10a736  brfalse.s loc_10A73D
0x10a738  leave    loc_10A8B2
0x10a73d  leave.s  loc_10A742
0x10a73f  pop
0x10a740  leave.s  loc_10A742
0x10a742  ldarg.0
0x10a743  ldloc.1
0x10a744  ldfld    class System.Xml.XmlResolver System.Xml.XmlTextReaderImpl::xmlResolver
0x10a749  ldarg.0
0x10a74a  ldfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::baseUri
0x10a74f  ldarg.0
0x10a750  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::systemId
0x10a755  callvirt instance class [System]System.Uri System.Xml.XmlResolver::ResolveUri(class [System]System.Uri baseUri, string relativeUri)
0x10a75a  stfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a75f  nop
0x10a760  ldloc.0
0x10a761  ldc.i4.1
0x10a762  beq.s    loc_10A7AE
0x10a764  ldloc.1
0x10a765  ldarg.0
0x10a766  ldfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a76b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.XmlTextReaderImpl::OpenAndPushAsync(class [System]System.Uri uri)
0x10a770  ldc.i4.0
0x10a771  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x10a776  stloc.s  4
0x10a778  ldloca.s 4
0x10a77a  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x10a77f  stloc.s  6
0x10a781  ldloca.s 6
0x10a783  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x10a788  brtrue.s loc_10A7CB
0x10a78a  ldarg.0
0x10a78b  ldc.i4.1
0x10a78c  dup
0x10a78d  stloc.0
0x10a78e  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a793  ldarg.0
0x10a794  ldloc.s  6
0x10a796  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a79b  ldarg.0
0x10a79c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PushExternalEntityOrSubsetAsync>d__581::<>t__builder
0x10a7a1  ldloca.s 6
0x10a7a3  ldarg.0
0x10a7a4  call     T0x2B000221
0x10a7a9  leave    loc_10A8CC
0x10a7ae  ldarg.0
0x10a7af  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a7b4  stloc.s  6
0x10a7b6  ldarg.0
0x10a7b7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <PushExternalEntityOrSubsetAsync>d__581::<>u__1
0x10a7bc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x10a7c2  ldarg.0
0x10a7c3  ldc.i4.m1
0x10a7c4  dup
0x10a7c5  stloc.0
0x10a7c6  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a7cb  ldloca.s 6
0x10a7cd  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x10a7d2  stloc.s  5
0x10a7d4  ldloc.s  5
0x10a7d6  brfalse.s loc_10A7DD
0x10a7d8  leave    loc_10A8B2
0x10a7dd  leave.s  loc_10A832
0x10a7df  stloc.s  7
0x10a7e1  ldloc.1
0x10a7e2  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x10a7e7  brfalse.s loc_10A7EB
0x10a7e9  rethrow
0x10a7eb  ldloc.s  7
0x10a7ed  callvirt instance string [mscorlib]System.Exception::get_Message()
0x10a7f2  stloc.s  8
0x10a7f4  ldloc.1
0x10a7f5  ldarg.0
0x10a7f6  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::entityName
0x10a7fb  brfalse.s loc_10A804
0x10a7fd  ldstr    aXmlErroropenin// "Xml_ErrorOpeningExternalEntity"
0x10a802  br.s     loc_10A809
0x10a804  ldstr    aXmlErroropenin_0// "Xml_ErrorOpeningExternalDtd"
0x10a809  ldc.i4.2
0x10a80a  newarr   [mscorlib]System.String
0x10a80f  dup
0x10a810  ldc.i4.0
0x10a811  ldarg.0
0x10a812  ldfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a817  callvirt instance string [mscorlib]System.Object::ToString()
0x10a81c  stelem.ref
0x10a81d  dup
0x10a81e  ldc.i4.1
0x10a81f  ldloc.s  8
0x10a821  stelem.ref
0x10a822  ldloc.s  7
0x10a824  ldc.i4.0
0x10a825  ldc.i4.0
0x10a826  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args, class [mscorlib]System.Exception innerException, int32 lineNumber, int32 linePosition)
0x10a82b  call     instance void System.Xml.XmlTextReaderImpl::Throw(class [mscorlib]System.Exception e)
0x10a830  leave.s  loc_10A832
0x10a832  ldarg.0
0x10a833  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::entityName
0x10a838  brtrue.s loc_10A86F
0x10a83a  ldloc.1
0x10a83b  ldstr    aXmlCannotresol_0// "Xml_CannotResolveExternalSubset"
0x10a840  ldc.i4.2
0x10a841  newarr   [mscorlib]System.String
0x10a846  dup
0x10a847  ldc.i4.0
0x10a848  ldarg.0
0x10a849  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::publicId
0x10a84e  brtrue.s loc_10A857
0x10a850  ldsfld   string [mscorlib]System.String::Empty
0x10a855  br.s     loc_10A85D
0x10a857  ldarg.0
0x10a858  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::publicId
0x10a85d  stelem.ref
0x10a85e  dup
0x10a85f  ldc.i4.1
0x10a860  ldarg.0
0x10a861  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::systemId
0x10a866  stelem.ref
0x10a867  ldnull
0x10a868  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string[] args, class [mscorlib]System.Exception innerException)
0x10a86d  br.s     loc_10A890
0x10a86f  ldloc.1
0x10a870  ldloc.1
0x10a871  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x10a876  ldc.i4.1
0x10a877  beq.s    loc_10A880
0x10a879  ldstr    aXmlCannotresol_1// "Xml_CannotResolveEntity"
0x10a87e  br.s     loc_10A885
0x10a880  ldstr    aXmlCannotresol_2// "Xml_CannotResolveEntityDtdIgnored"
0x10a885  ldarg.0
0x10a886  ldfld    string <PushExternalEntityOrSubsetAsync>d__581::entityName
0x10a88b  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x10a890  leave.s  loc_10A8B2
0x10a892  stloc.s  9
0x10a894  ldarg.0
0x10a895  ldc.i4.s 0xFE
0x10a897  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a89c  ldarg.0
0x10a89d  ldnull
0x10a89e  stfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a8a3  ldarg.0
0x10a8a4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PushExternalEntityOrSubsetAsync>d__581::<>t__builder
0x10a8a9  ldloc.s  9
0x10a8ab  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x10a8b0  leave.s  loc_10A8CC
0x10a8b2  ldarg.0
0x10a8b3  ldc.i4.s 0xFE
0x10a8b5  stfld    int32 <PushExternalEntityOrSubsetAsync>d__581::<>1__state
0x10a8ba  ldarg.0
0x10a8bb  ldnull
0x10a8bc  stfld    class [System]System.Uri <PushExternalEntityOrSubsetAsync>d__581::<uri>5__2
0x10a8c1  ldarg.0
0x10a8c2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PushExternalEntityOrSubsetAsync>d__581::<>t__builder
0x10a8c7  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x10a8cc  ret
```
