# System.Web.Script.Services.ClientProxyGenerator::GenerateRegisterClass

- ea: `0x2fd30`
- end: `0x2fd60`
- name: `System.Web.Script.Services.ClientProxyGenerator::GenerateRegisterClass`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x2fcc0`

## callees

- `0x30ca0`

## string_xrefs

- `0x2fd54`: `',Sys.Net.WebServiceProxy);\n`

## pseudocode

```c

```

## disassembly

```asm
0x2fd30  ldarg.0
0x2fd31  ldarg.1
0x2fd32  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetProxyTypeName(class System.Web.Script.Services.WebServiceData data)
0x2fd37  stloc.0
0x2fd38  ldarg.0
0x2fd39  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x2fd3e  ldloc.0
0x2fd3f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fd44  ldstr    aRegisterclass// ".registerClass('"
0x2fd49  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fd4e  ldloc.0
0x2fd4f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fd54  ldstr    aSysNetWebservi// "',Sys.Net.WebServiceProxy);\r\n"
0x2fd59  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2fd5e  pop
0x2fd5f  ret
```
