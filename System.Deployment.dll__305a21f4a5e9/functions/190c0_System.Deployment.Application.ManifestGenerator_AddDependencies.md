# System.Deployment.Application.ManifestGenerator::AddDependencies

- ea: `0x190c0`
- end: `0x19176`
- name: `System.Deployment.Application.ManifestGenerator::AddDependencies`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18f40`
- `0x18fd0`

## callees

- `0xd960`
- `0x190c0`
- `0x191a0`
- `0x192f0`
- `0x24380`

## string_xrefs

- `0x19104`: `urn:schemas-microsoft-com:asm.v1`
- `0x1911f`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x190c0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x190c5  stloc.0
0x190c6  ldarg.0
0x190c7  call     class [System.Xml]System.Xml.XmlNamespaceManager System.Deployment.Application.ManifestGenerator::GetNamespaceMgr(class [System.Xml]System.Xml.XmlDocument document)
0x190cc  stloc.1
0x190cd  ldarg.0
0x190ce  ldstr    aAsmv1Assembly// "/asmv1:assembly"
0x190d3  ldloc.1
0x190d4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x190d9  castclass [System.Xml]System.Xml.XmlElement
0x190de  stloc.2
0x190df  ldarg.1
0x190e0  stloc.3
0x190e1  ldc.i4.0
0x190e2  stloc.s  4
0x190e4  br       loc_1916B
0x190e9  ldloc.3
0x190ea  ldloc.s  4
0x190ec  ldelem.ref
0x190ed  stloc.s  5
0x190ef  ldloc.0
0x190f0  ldloc.s  5
0x190f2  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x190f7  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x190fc  brtrue.s loc_19165
0x190fe  ldarg.0
0x190ff  ldstr    aDependency// "dependency"
0x19104  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x19109  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x1910e  stloc.s  6
0x19110  ldloc.2
0x19111  ldloc.s  6
0x19113  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x19118  pop
0x19119  ldarg.0
0x1911a  ldstr    aDependentassem// "dependentAssembly"
0x1911f  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x19124  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x19129  stloc.s  7
0x1912b  ldloc.s  6
0x1912d  ldloc.s  7
0x1912f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x19134  pop
0x19135  ldloc.s  5
0x19137  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x1913c  stloc.s  8
0x1913e  ldloc.s  8
0x19140  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x19145  stloc.s  9
0x19147  ldarg.0
0x19148  ldloc.s  9
0x1914a  call     class [System.Xml]System.Xml.XmlElement System.Deployment.Application.ManifestGenerator::CreateAssemblyIdentityElement(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.DefinitionIdentity asmId)
0x1914f  stloc.s  0xA
0x19151  ldloc.s  7
0x19153  ldloc.s  0xA
0x19155  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x1915a  pop
0x1915b  ldloc.0
0x1915c  ldloc.s  8
0x1915e  ldloc.s  9
0x19160  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x19165  ldloc.s  4
0x19167  ldc.i4.1
0x19168  add
0x19169  stloc.s  4
0x1916b  ldloc.s  4
0x1916d  ldloc.3
0x1916e  ldlen
0x1916f  conv.i4
0x19170  blt      loc_190E9
0x19175  ret
```
