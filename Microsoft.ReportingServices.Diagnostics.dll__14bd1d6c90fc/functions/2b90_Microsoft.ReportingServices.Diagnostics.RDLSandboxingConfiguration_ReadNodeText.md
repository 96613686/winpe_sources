# Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ReadNodeText

- ea: `0x2b90`
- end: `0x2c15`
- name: `Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration::ReadNodeText`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2970`
- `0x2a70`
- `0x3060`

## callees

- `0x2b90`

## pseudocode

```c

```

## disassembly

```asm
0x2b90  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2b95  stloc.0
0x2b96  ldarg.0
0x2b97  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x2b9c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2ba1  stloc.1
0x2ba2  br.s     loc_2BEB
0x2ba4  ldloc.1
0x2ba5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2baa  castclass [System.Xml]System.Xml.XmlNode
0x2baf  stloc.2
0x2bb0  ldloc.2
0x2bb1  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x2bb6  stloc.3
0x2bb7  ldloc.3
0x2bb8  ldc.i4.8
0x2bb9  bgt.s    loc_2BC7
0x2bbb  ldloc.3
0x2bbc  ldc.i4.3
0x2bbd  sub
0x2bbe  ldc.i4.1
0x2bbf  ble.un.s loc_2BD1
0x2bc1  ldloc.3
0x2bc2  ldc.i4.8
0x2bc3  beq.s    loc_2BEB
0x2bc5  br.s     loc_2BE0
0x2bc7  ldloc.3
0x2bc8  ldc.i4.s 0xD
0x2bca  beq.s    loc_2BEB
0x2bcc  ldloc.3
0x2bcd  ldc.i4.s 0xE
0x2bcf  bne.un.s loc_2BE0
0x2bd1  ldloc.0
0x2bd2  ldloc.2
0x2bd3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2bd8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2bdd  pop
0x2bde  br.s     loc_2BEB
0x2be0  ldloc.2
0x2be1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x2be6  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlParseExceptions::ThrowInvalidFormat(string)
0x2beb  ldloc.1
0x2bec  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2bf1  brtrue.s loc_2BA4
0x2bf3  leave.s  loc_2C09
0x2bf5  ldloc.1
0x2bf6  isinst   [mscorlib]System.IDisposable
0x2bfb  stloc.s  4
0x2bfd  ldloc.s  4
0x2bff  brfalse.s loc_2C08
0x2c01  ldloc.s  4
0x2c03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c08  endfinally
0x2c09  ldloc.0
0x2c0a  callvirt instance string [mscorlib]System.Object::ToString()
0x2c0f  callvirt instance string [mscorlib]System.String::Trim()
0x2c14  ret
```
