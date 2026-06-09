# System.Xml.XmlTextReaderImpl::PushExternalEntityOrSubset

- ea: `0x30250`
- end: `0x30323`
- name: `System.Xml.XmlTextReaderImpl::PushExternalEntityOrSubset`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x29570`
- `0x303c0`

## callees

- `0x127e0`
- `0x136f0`
- `0x29770`
- `0x29840`
- `0x298d0`
- `0x30250`
- `0x30330`

## string_xrefs

- `0x302ae`: `Xml_ErrorOpeningExternalEntity`
- `0x302b5`: `Xml_ErrorOpeningExternalDtd`
- `0x302e1`: `Xml_CannotResolveExternalSubset`
- `0x3030f`: `Xml_CannotResolveEntity`
- `0x30316`: `Xml_CannotResolveEntityDtdIgnored`

## pseudocode

```c

```

## disassembly

```asm
0x30250  ldarg.1
0x30251  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30256  brtrue.s loc_30279
0x30258  ldarg.0
0x30259  ldfld    class System.Xml.XmlResolver System.Xml.XmlTextReaderImpl::xmlResolver
0x3025e  ldarg.3
0x3025f  ldarg.1
0x30260  callvirt instance class [System]System.Uri System.Xml.XmlResolver::ResolveUri(class [System]System.Uri baseUri, string relativeUri)
0x30265  stloc.0
0x30266  ldarg.0
0x30267  ldloc.0
0x30268  call     instance bool System.Xml.XmlTextReaderImpl::OpenAndPush(class [System]System.Uri uri)
0x3026d  brfalse.s loc_30274
0x3026f  leave    loc_30322
0x30274  leave.s  loc_30279
0x30276  pop
0x30277  leave.s  loc_30279
0x30279  ldarg.0
0x3027a  ldfld    class System.Xml.XmlResolver System.Xml.XmlTextReaderImpl::xmlResolver
0x3027f  ldarg.3
0x30280  ldarg.2
0x30281  callvirt instance class [System]System.Uri System.Xml.XmlResolver::ResolveUri(class [System]System.Uri baseUri, string relativeUri)
0x30286  stloc.0
0x30287  ldarg.0
0x30288  ldloc.0
0x30289  call     instance bool System.Xml.XmlTextReaderImpl::OpenAndPush(class [System]System.Uri uri)
0x3028e  brfalse.s loc_30295
0x30290  leave    loc_30322
0x30295  leave.s  loc_302DC
0x30297  stloc.1
0x30298  ldarg.0
0x30299  ldfld    bool System.Xml.XmlTextReaderImpl::v1Compat
0x3029e  brfalse.s loc_302A2
0x302a0  rethrow
0x302a2  ldloc.1
0x302a3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x302a8  stloc.2
0x302a9  ldarg.0
0x302aa  ldarg.s  4
0x302ac  brfalse.s loc_302B5
0x302ae  ldstr    aXmlErroropenin// "Xml_ErrorOpeningExternalEntity"
0x302b3  br.s     loc_302BA
0x302b5  ldstr    aXmlErroropenin_0// "Xml_ErrorOpeningExternalDtd"
0x302ba  ldc.i4.2
0x302bb  newarr   [mscorlib]System.String
0x302c0  dup
0x302c1  ldc.i4.0
0x302c2  ldloc.0
0x302c3  callvirt instance string [mscorlib]System.Object::ToString()
0x302c8  stelem.ref
0x302c9  dup
0x302ca  ldc.i4.1
0x302cb  ldloc.2
0x302cc  stelem.ref
0x302cd  ldloc.1
0x302ce  ldc.i4.0
0x302cf  ldc.i4.0
0x302d0  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args, class [mscorlib]System.Exception innerException, int32 lineNumber, int32 linePosition)
0x302d5  call     instance void System.Xml.XmlTextReaderImpl::Throw(class [mscorlib]System.Exception e)
0x302da  leave.s  loc_302DC
0x302dc  ldarg.s  4
0x302de  brtrue.s loc_30305
0x302e0  ldarg.0
0x302e1  ldstr    aXmlCannotresol_0// "Xml_CannotResolveExternalSubset"
0x302e6  ldc.i4.2
0x302e7  newarr   [mscorlib]System.String
0x302ec  dup
0x302ed  ldc.i4.0
0x302ee  ldarg.1
0x302ef  brtrue.s loc_302F8
0x302f1  ldsfld   string [mscorlib]System.String::Empty
0x302f6  br.s     loc_302F9
0x302f8  ldarg.1
0x302f9  stelem.ref
0x302fa  dup
0x302fb  ldc.i4.1
0x302fc  ldarg.2
0x302fd  stelem.ref
0x302fe  ldnull
0x302ff  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res, string[] args, class [mscorlib]System.Exception innerException)
0x30304  ret
0x30305  ldarg.0
0x30306  ldarg.0
0x30307  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlTextReaderImpl::dtdProcessing
0x3030c  ldc.i4.1
0x3030d  beq.s    loc_30316
0x3030f  ldstr    aXmlCannotresol_1// "Xml_CannotResolveEntity"
0x30314  br.s     loc_3031B
0x30316  ldstr    aXmlCannotresol_2// "Xml_CannotResolveEntityDtdIgnored"
0x3031b  ldarg.s  4
0x3031d  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x30322  ret
```
