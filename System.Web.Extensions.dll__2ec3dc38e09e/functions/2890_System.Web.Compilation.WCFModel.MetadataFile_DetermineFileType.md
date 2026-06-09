# System.Web.Compilation.WCFModel.MetadataFile::DetermineFileType

- ea: `0x2890`
- end: `0x291b`
- name: `System.Web.Compilation.WCFModel.MetadataFile::DetermineFileType`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2a70`

## callees

- `0x2890`

## string_xrefs

- `0x2896`: `http://schemas.xmlsoap.org/wsdl/`
- `0x28ac`: `http://www.w3.org/2001/XMLSchema`
- `0x28c2`: `http://schemas.xmlsoap.org/ws/2004/09/policy`
- `0x28ea`: `http://schemas.xmlsoap.org/disco/`
- `0x2900`: `http://schemas.microsoft.com/ado/2007/06/edmx`

## pseudocode

```c

```

## disassembly

```asm
0x2890  ldarg.1
0x2891  ldstr    aDefinitions// "definitions"
0x2896  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/wsdl/"
0x289b  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x28a0  brfalse.s loc_28A6
0x28a2  ldc.i4.2
0x28a3  stloc.0
0x28a4  leave.s  loc_2919
0x28a6  ldarg.1
0x28a7  ldstr    aSchema// "schema"
0x28ac  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x28b1  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x28b6  brfalse.s loc_28BC
0x28b8  ldc.i4.3
0x28b9  stloc.0
0x28ba  leave.s  loc_2919
0x28bc  ldarg.1
0x28bd  ldstr    aPolicy// "Policy"
0x28c2  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/ws/2004/09/p"...
0x28c7  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x28cc  brtrue.s loc_28E0
0x28ce  ldarg.1
0x28cf  ldstr    aPolicy// "Policy"
0x28d4  ldstr    aHttpWwwW3OrgNs// "http://www.w3.org/ns/ws-policy"
0x28d9  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x28de  brfalse.s loc_28E4
0x28e0  ldc.i4.4
0x28e1  stloc.0
0x28e2  leave.s  loc_2919
0x28e4  ldarg.1
0x28e5  ldstr    aDiscovery// "discovery"
0x28ea  ldstr    aHttpSchemasXml_1// "http://schemas.xmlsoap.org/disco/"
0x28ef  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x28f4  brfalse.s loc_28FA
0x28f6  ldc.i4.1
0x28f7  stloc.0
0x28f8  leave.s  loc_2919
0x28fa  ldarg.1
0x28fb  ldstr    aEdmx// "Edmx"
0x2900  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/ado/2007/0"...
0x2905  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x290a  brfalse.s loc_2910
0x290c  ldc.i4.6
0x290d  stloc.0
0x290e  leave.s  loc_2919
0x2910  ldc.i4.5
0x2911  stloc.0
0x2912  leave.s  loc_2919
0x2914  pop
0x2915  ldc.i4.0
0x2916  stloc.0
0x2917  leave.s  loc_2919
0x2919  ldloc.0
0x291a  ret
```
