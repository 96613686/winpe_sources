# System.Web.Script.Services.ProxyGenerator::GetClientProxyScript_0

- ea: `0x2d660`
- end: `0x2d786`
- name: `System.Web.Script.Services.ProxyGenerator::GetClientProxyScript_0`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x2d650`

## callees

- `0x2a710`
- `0x2d5a0`
- `0x2d660`
- `0x2d790`
- `0x2d7b0`
- `0x2d7d0`
- `0x2e3a0`
- `0x2e660`
- `0x2fcc0`

## string_xrefs

- `0x2d6cb`: `System.ServiceModel.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x2d6e0`: `System.ServiceModel.Description.WCFServiceClientProxyGenerator`

## pseudocode

```c

```

## disassembly

```asm
0x2d660  ldarg.0
0x2d661  ldnull
0x2d662  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d667  brfalse.s loc_2D674
0x2d669  ldstr    aType// "type"
0x2d66e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d673  throw
0x2d674  ldarg.1
0x2d675  brtrue.s loc_2D682
0x2d677  ldstr    aPath// "path"
0x2d67c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d681  throw
0x2d682  ldnull
0x2d683  stloc.0
0x2d684  ldnull
0x2d685  stloc.1
0x2d686  ldarg.0
0x2d687  call     bool System.Web.Script.Services.ProxyGenerator::IsWebServiceType(class [mscorlib]System.Type type)
0x2d68c  brfalse.s loc_2D6A3
0x2d68e  ldarg.1
0x2d68f  ldarg.2
0x2d690  newobj   instance void System.Web.Script.Services.WebServiceClientProxyGenerator::.ctor(string path, bool debug)
0x2d695  stloc.1
0x2d696  ldarg.0
0x2d697  ldc.i4.0
0x2d698  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2d69d  stloc.0
0x2d69e  br       loc_2D77E
0x2d6a3  ldarg.0
0x2d6a4  call     bool System.Web.Script.Services.ProxyGenerator::IsPageType(class [mscorlib]System.Type type)
0x2d6a9  brfalse.s loc_2D6C0
0x2d6ab  ldarg.1
0x2d6ac  ldarg.2
0x2d6ad  newobj   instance void System.Web.Script.Services.PageClientProxyGenerator::.ctor(string path, bool debug)
0x2d6b2  stloc.1
0x2d6b3  ldarg.0
0x2d6b4  ldc.i4.1
0x2d6b5  newobj   instance void System.Web.Script.Services.WebServiceData::.ctor(class [mscorlib]System.Type type, bool pageMethods)
0x2d6ba  stloc.0
0x2d6bb  br       loc_2D77E
0x2d6c0  ldarg.0
0x2d6c1  call     bool System.Web.Script.Services.ProxyGenerator::IsWCFServiceType(class [mscorlib]System.Type type)
0x2d6c6  brfalse  loc_2D75A
0x2d6cb  ldstr    aSystemServicem// "System.ServiceModel.Web, Version=4.0.0."...
0x2d6d0  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x2d6d5  stloc.2
0x2d6d6  ldloc.2
0x2d6d7  ldnull
0x2d6d8  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x2d6dd  brfalse.s loc_2D736
0x2d6df  ldloc.2
0x2d6e0  ldstr    aSystemServicem_0// "System.ServiceModel.Description.WCFServ"...
0x2d6e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x2d6ea  stloc.3
0x2d6eb  ldloc.3
0x2d6ec  ldnull
0x2d6ed  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d6f2  brfalse.s loc_2D736
0x2d6f4  ldloc.3
0x2d6f5  ldstr    aGetclientproxy// "GetClientProxyScript"
0x2d6fa  ldc.i4.s 0x28
0x2d6fc  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x2d701  stloc.s  4
0x2d703  ldloc.s  4
0x2d705  ldnull
0x2d706  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x2d70b  brfalse.s loc_2D736
0x2d70d  ldloc.s  4
0x2d70f  ldnull
0x2d710  ldc.i4.4
0x2d711  newarr   [mscorlib]System.Object
0x2d716  dup
0x2d717  ldc.i4.0
0x2d718  ldarg.0
0x2d719  stelem.ref
0x2d71a  dup
0x2d71b  ldc.i4.1
0x2d71c  ldarg.1
0x2d71d  stelem.ref
0x2d71e  dup
0x2d71f  ldc.i4.2
0x2d720  ldarg.2
0x2d721  box      [mscorlib]System.Boolean
0x2d726  stelem.ref
0x2d727  dup
0x2d728  ldc.i4.3
0x2d729  ldarg.3
0x2d72a  stelem.ref
0x2d72b  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x2d730  isinst   [mscorlib]System.String
0x2d735  ret
0x2d736  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x2d73b  call     string System.Web.Resources.AtlasWeb::get_ProxyGenerator_UnsupportedType()
0x2d740  ldc.i4.1
0x2d741  newarr   [mscorlib]System.Object
0x2d746  dup
0x2d747  ldc.i4.0
0x2d748  ldarg.0
0x2d749  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d74e  stelem.ref
0x2d74f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d754  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d759  throw
0x2d75a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x2d75f  call     string System.Web.Resources.AtlasWeb::get_ProxyGenerator_UnsupportedType()
0x2d764  ldc.i4.1
0x2d765  newarr   [mscorlib]System.Object
0x2d76a  dup
0x2d76b  ldc.i4.0
0x2d76c  ldarg.0
0x2d76d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d772  stelem.ref
0x2d773  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2d778  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d77d  throw
0x2d77e  ldloc.1
0x2d77f  ldloc.0
0x2d780  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetClientProxyScript(class System.Web.Script.Services.WebServiceData webServiceData)
0x2d785  ret
```
