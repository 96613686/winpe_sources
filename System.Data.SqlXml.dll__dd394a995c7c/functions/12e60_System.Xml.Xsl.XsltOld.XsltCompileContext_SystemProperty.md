# System.Xml.Xsl.XsltOld.XsltCompileContext::SystemProperty

- ea: `0x12e60`
- end: `0x12ee7`
- name: `System.Xml.Xsl.XsltOld.XsltCompileContext::SystemProperty`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x556d0`

## callees

- `0xc100`
- `0x12e60`

## string_xrefs

- `0x12ebc`: `http://www.microsoft.com`

## pseudocode

```c

```

## disassembly

```asm
0x12e60  ldsfld   string [mscorlib]System.String::Empty
0x12e65  stloc.0
0x12e66  ldarg.1
0x12e67  ldloca.s 1
0x12e69  ldloca.s 2
0x12e6b  call     void System.Xml.Xsl.XsltOld.PrefixQName::ParseQualifiedName(string qname, [out] string& prefix, [out] string& local)
0x12e70  ldarg.0
0x12e71  ldloc.1
0x12e72  callvirt instance string [System.Xml]System.Xml.XmlNamespaceManager::LookupNamespace(string)
0x12e77  stloc.3
0x12e78  ldloc.3
0x12e79  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x12e7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12e83  brfalse.s loc_12EC4
0x12e85  ldloc.2
0x12e86  ldstr    aVersion// "version"
0x12e8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12e90  brfalse.s loc_12E9A
0x12e92  ldstr    a1// "1"
0x12e97  stloc.0
0x12e98  br.s     loc_12EE5
0x12e9a  ldloc.2
0x12e9b  ldstr    aVendor// "vendor"
0x12ea0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12ea5  brfalse.s loc_12EAF
0x12ea7  ldstr    aMicrosoft// "Microsoft"
0x12eac  stloc.0
0x12ead  br.s     loc_12EE5
0x12eaf  ldloc.2
0x12eb0  ldstr    aVendorUrl// "vendor-url"
0x12eb5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12eba  brfalse.s loc_12EE5
0x12ebc  ldstr    aHttpWwwMicroso// "http://www.microsoft.com"
0x12ec1  stloc.0
0x12ec2  br.s     loc_12EE5
0x12ec4  ldloc.3
0x12ec5  brtrue.s loc_12EDF
0x12ec7  ldloc.1
0x12ec8  brfalse.s loc_12EDF
0x12eca  ldstr    aXsltInvalidpre// "Xslt_InvalidPrefix"
0x12ecf  ldc.i4.1
0x12ed0  newarr   [mscorlib]System.String
0x12ed5  dup
0x12ed6  ldc.i4.0
0x12ed7  ldloc.1
0x12ed8  stelem.ref
0x12ed9  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x12ede  throw
0x12edf  ldsfld   string [mscorlib]System.String::Empty
0x12ee4  ret
0x12ee5  ldloc.0
0x12ee6  ret
```
