# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::ModifySettingsFile

- ea: `0xa610`
- end: `0xa6a0`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.ContentTypeExportHelper::ModifySettingsFile`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9f50`

## callees

- `0xa610`

## string_xrefs

- `0xa611`: `SystemData.xml`
- `0xa644`: `ManifestFile`
- `0xa661`: `ManifestFiles`

## pseudocode

```c

```

## disassembly

```asm
0xa610  ldarg.0
0xa611  ldstr    aSystemdataXml// "SystemData.xml"
0xa616  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa61b  stloc.0
0xa61c  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xa621  stloc.1
0xa622  ldloc.0
0xa623  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(string)
0xa628  stloc.2
0xa629  ldloc.2
0xa62a  ldc.i4.0
0xa62b  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0xa630  ldloc.1
0xa631  ldloc.2
0xa632  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xa637  leave.s  loc_A643
0xa639  ldloc.2
0xa63a  brfalse.s loc_A642
0xa63c  ldloc.2
0xa63d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa642  endfinally
0xa643  ldloc.1
0xa644  ldstr    aManifestfile// "ManifestFile"
0xa649  ldstr    aUrnDeploymentS// "urn:deployment-systemdata-schema"
0xa64e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa653  stloc.3
0xa654  ldloc.3
0xa655  ldstr    aName// "Name"
0xa65a  ldarg.1
0xa65b  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa660  ldloc.1
0xa661  ldstr    aManifestfiles// "ManifestFiles"
0xa666  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0xa66b  stloc.s  4
0xa66d  ldloc.s  4
0xa66f  ldc.i4.0
0xa670  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xa675  ldloc.3
0xa676  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xa67b  pop
0xa67c  ldloc.0
0xa67d  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xa682  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(string, class [mscorlib]System.Text.Encoding)
0xa687  stloc.s  5
0xa689  ldloc.1
0xa68a  ldloc.s  5
0xa68c  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(class [System.Xml]System.Xml.XmlWriter)
0xa691  leave.s  loc_A69F
0xa693  ldloc.s  5
0xa695  brfalse.s loc_A69E
0xa697  ldloc.s  5
0xa699  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa69e  endfinally
0xa69f  ret
```
