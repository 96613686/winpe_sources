# Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::BuildEntityTypeName

- ea: `0x2e70`
- end: `0x2eaa`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::BuildEntityTypeName`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e10`

## callees

- `0x2d20`
- `0x2e70`

## pseudocode

```c

```

## disassembly

```asm
0x2e70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2e75  stloc.0
0x2e76  ldarg.2
0x2e77  brfalse.s loc_2E8F
0x2e79  ldloc.0
0x2e7a  ldarg.0
0x2e7b  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::get_SchemaNamespace()
0x2e80  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2e85  pop
0x2e86  ldloc.0
0x2e87  ldc.i4.s 0x2E
0x2e89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2e8e  pop
0x2e8f  ldloc.0
0x2e90  ldarg.1
0x2e91  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2e96  pop
0x2e97  ldloc.0
0x2e98  ldstr    aItem// "Item"
0x2e9d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ea2  pop
0x2ea3  ldloc.0
0x2ea4  callvirt instance string [mscorlib]System.Object::ToString()
0x2ea9  ret
```
