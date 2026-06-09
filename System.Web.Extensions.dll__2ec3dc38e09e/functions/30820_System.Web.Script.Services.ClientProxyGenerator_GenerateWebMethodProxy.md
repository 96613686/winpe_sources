# System.Web.Script.Services.ClientProxyGenerator::GenerateWebMethodProxy

- ea: `0x30820`
- end: `0x3094a`
- name: `System.Web.Script.Services.ClientProxyGenerator::GenerateWebMethodProxy`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x2fdb0`

## callees

- `0x2f140`
- `0x2f1d0`
- `0x2f2a0`
- `0x306e0`
- `0x30820`
- `0x30ca0`

## string_xrefs

- `0x308ec`: `return this._invoke(this._get_path(), `

## pseudocode

```c

```

## disassembly

```asm
0x30820  ldarg.1
0x30821  callvirt instance string System.Web.Script.Services.WebServiceMethodData::get_MethodName()
0x30826  stloc.0
0x30827  ldarg.0
0x30828  ldarg.1
0x30829  callvirt instance class System.Web.Script.Services.WebServiceData System.Web.Script.Services.WebServiceMethodData::get_Owner()
0x3082e  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetProxyTypeName(class System.Web.Script.Services.WebServiceData data)
0x30833  stloc.1
0x30834  ldarg.1
0x30835  callvirt instance bool System.Web.Script.Services.WebServiceMethodData::get_UseGet()
0x3083a  brtrue.s loc_30843
0x3083c  ldstr    aFalse// "false"
0x30841  br.s     loc_30848
0x30843  ldstr    aTrue// "true"
0x30848  stloc.2
0x30849  ldarg.0
0x3084a  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3084f  ldloc.0
0x30850  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30855  ldc.i4.s 0x3A
0x30857  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x3085c  pop
0x3085d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x30862  stloc.3
0x30863  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x30868  stloc.s  4
0x3086a  ldnull
0x3086b  stloc.s  5
0x3086d  ldnull
0x3086e  stloc.s  6
0x30870  ldarg.0
0x30871  ldfld    bool System.Web.Script.Services.ClientProxyGenerator::_debugMode
0x30876  brfalse.s loc_3087F
0x30878  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3087d  stloc.s  5
0x3087f  ldarg.0
0x30880  ldarg.1
0x30881  ldloc.3
0x30882  ldloc.s  4
0x30884  ldloc.s  5
0x30886  call     instance void System.Web.Script.Services.ClientProxyGenerator::BuildArgsDictionary(class System.Web.Script.Services.WebServiceMethodData methodData, class [mscorlib]System.Text.StringBuilder args, class [mscorlib]System.Text.StringBuilder argsDict, class [mscorlib]System.Text.StringBuilder docComments)
0x3088b  ldarg.0
0x3088c  ldfld    bool System.Web.Script.Services.ClientProxyGenerator::_debugMode
0x30891  brfalse.s loc_308AA
0x30893  ldloc.s  5
0x30895  callvirt instance string [mscorlib]System.Object::ToString()
0x3089a  stloc.s  6
0x3089c  ldarg.0
0x3089d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> System.Web.Script.Services.ClientProxyGenerator::_docCommentCache
0x308a2  ldloc.0
0x308a3  ldloc.s  6
0x308a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x308aa  ldarg.0
0x308ab  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x308b0  ldstr    aFunction_1// "function("
0x308b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x308ba  ldloc.3
0x308bb  callvirt instance string [mscorlib]System.Object::ToString()
0x308c0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x308c5  ldstr    asc_4C4AE// ") {\r\n"
0x308ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x308cf  pop
0x308d0  ldarg.0
0x308d1  ldfld    bool System.Web.Script.Services.ClientProxyGenerator::_debugMode
0x308d6  brfalse.s loc_308E6
0x308d8  ldarg.0
0x308d9  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x308de  ldloc.s  6
0x308e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x308e5  pop
0x308e6  ldarg.0
0x308e7  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x308ec  ldstr    aReturnThisInvo// "return this._invoke(this._get_path(), "
0x308f1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x308f6  pop
0x308f7  ldarg.0
0x308f8  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x308fd  ldstr    asc_402C4// "'"
0x30902  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30907  ldloc.0
0x30908  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3090d  ldstr    asc_402C8// "',"
0x30912  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30917  pop
0x30918  ldarg.0
0x30919  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x3091e  ldloc.2
0x3091f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30924  ldc.i4.s 0x2C
0x30926  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x3092b  pop
0x3092c  ldarg.0
0x3092d  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30932  ldloc.s  4
0x30934  callvirt instance string [mscorlib]System.Object::ToString()
0x30939  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3093e  ldstr    aSucceededcallb_0// ",succeededCallback,failedCallback,userC"...
0x30943  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30948  pop
0x30949  ret
```
