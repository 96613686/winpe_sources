# Microsoft.ReportingServices.Modeling.FunctionNode::CloneFor

- ea: `0x1b080`
- end: `0x1b0c4`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::CloneFor`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x19ab0`
- `0x1a360`
- `0x1b080`

## string_xrefs

- `0x1b088`: `FunctionNode is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x1b080  ldarg.0
0x1b081  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1b086  brtrue.s loc_1B093
0x1b088  ldstr    aFunctionnodeIs// "FunctionNode is not compiled"
0x1b08d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b092  throw
0x1b093  ldarg.0
0x1b094  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1b099  ldarg.1
0x1b09a  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.ExpressionCollection::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x1b09f  stloc.0
0x1b0a0  ldloc.0
0x1b0a1  brtrue.s loc_1B0A5
0x1b0a3  ldnull
0x1b0a4  ret
0x1b0a5  ldarg.0
0x1b0a6  ldfld    valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::m_functionName
0x1b0ab  ldloc.0
0x1b0ac  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.ExpressionCollection arguments)
0x1b0b1  dup
0x1b0b2  ldarg.0
0x1b0b3  ldfld    class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionNode::m_compiledFunctionInfo
0x1b0b8  stfld    class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionNode::m_compiledFunctionInfo
0x1b0bd  dup
0x1b0be  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x1b0c3  ret
```
