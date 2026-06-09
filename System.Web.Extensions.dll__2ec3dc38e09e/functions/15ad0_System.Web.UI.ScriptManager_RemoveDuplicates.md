# System.Web.UI.ScriptManager::RemoveDuplicates

- ea: `0x15ad0`
- end: `0x15e52`
- name: `System.Web.UI.ScriptManager::RemoveDuplicates`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x15720`

## callees

- `0xfa50`
- `0x14ed0`
- `0x15aa0`
- `0x15ad0`
- `0x16710`
- `0x16750`
- `0x16770`
- `0x16990`
- `0x17000`
- `0x17050`
- `0x17140`
- `0x2abd0`

## string_xrefs

- `0x15c9b`: `MicrosoftAjaxApplicationServices.`
- `0x15ddc`: `MicrosoftAjaxApplicationServices.`

## pseudocode

```c

```

## disassembly

```asm
0x15ad0  ldarg.1
0x15ad1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::get_Count()
0x15ad6  stloc.0
0x15ad7  ldarg.2
0x15ad8  brtrue   loc_15BBE
0x15add  ldloc.0
0x15ade  ldc.i4.1
0x15adf  bne.un.s loc_15B1B
0x15ae1  ldarg.1
0x15ae2  ldc.i4.0
0x15ae3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::get_Item(!!T0)
0x15ae8  isinst   System.Web.UI.ScriptReference
0x15aed  stloc.3
0x15aee  ldloc.3
0x15aef  brfalse  loc_15BBE
0x15af4  ldarg.s  4
0x15af6  brfalse.s loc_15B19
0x15af8  ldloc.3
0x15af9  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15afe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15b03  brtrue.s loc_15B19
0x15b05  ldarg.s  4
0x15b07  ldloc.3
0x15b08  ldarg.0
0x15b09  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.UI.ScriptReference::GetAssembly(class System.Web.UI.ScriptManager scriptManager)
0x15b0e  ldloc.3
0x15b0f  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b14  call     void System.Web.UI.ScriptManager::RegisterResourceWithClientScriptManager(class System.Web.UI.IClientScriptManager clientScriptManager, class [mscorlib]System.Reflection.Assembly assembly, string key)
0x15b19  ldarg.1
0x15b1a  ret
0x15b1b  ldloc.0
0x15b1c  ldc.i4.2
0x15b1d  bne.un   loc_15BBE
0x15b22  ldarg.1
0x15b23  ldc.i4.0
0x15b24  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::get_Item(!!T0)
0x15b29  isinst   System.Web.UI.ScriptReference
0x15b2e  stloc.s  4
0x15b30  ldarg.1
0x15b31  ldc.i4.1
0x15b32  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::get_Item(!!T0)
0x15b37  isinst   System.Web.UI.ScriptReference
0x15b3c  stloc.s  5
0x15b3e  ldloc.s  4
0x15b40  brfalse.s loc_15BBE
0x15b42  ldloc.s  5
0x15b44  brfalse.s loc_15BBE
0x15b46  ldloc.s  4
0x15b48  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b4d  ldloc.s  5
0x15b4f  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b54  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x15b59  brtrue.s loc_15B70
0x15b5b  ldloc.s  4
0x15b5d  callvirt instance string System.Web.UI.ScriptReference::get_Assembly()
0x15b62  ldloc.s  5
0x15b64  callvirt instance string System.Web.UI.ScriptReference::get_Assembly()
0x15b69  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x15b6e  brfalse.s loc_15BBE
0x15b70  ldarg.s  4
0x15b72  brfalse.s loc_15BBC
0x15b74  ldloc.s  4
0x15b76  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b7b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15b80  brtrue.s loc_15B98
0x15b82  ldarg.s  4
0x15b84  ldloc.s  4
0x15b86  ldarg.0
0x15b87  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.UI.ScriptReference::GetAssembly(class System.Web.UI.ScriptManager scriptManager)
0x15b8c  ldloc.s  4
0x15b8e  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b93  call     void System.Web.UI.ScriptManager::RegisterResourceWithClientScriptManager(class System.Web.UI.IClientScriptManager clientScriptManager, class [mscorlib]System.Reflection.Assembly assembly, string key)
0x15b98  ldloc.s  5
0x15b9a  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15b9f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15ba4  brtrue.s loc_15BBC
0x15ba6  ldarg.s  4
0x15ba8  ldloc.s  5
0x15baa  ldarg.0
0x15bab  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.UI.ScriptReference::GetAssembly(class System.Web.UI.ScriptManager scriptManager)
0x15bb0  ldloc.s  5
0x15bb2  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15bb7  call     void System.Web.UI.ScriptManager::RegisterResourceWithClientScriptManager(class System.Web.UI.IClientScriptManager clientScriptManager, class [mscorlib]System.Reflection.Assembly assembly, string key)
0x15bbc  ldarg.1
0x15bbd  ret
0x15bbe  ldloc.0
0x15bbf  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor(int32)
0x15bc4  stloc.1
0x15bc5  ldloc.0
0x15bc6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::.ctor(int32)
0x15bcb  stloc.2
0x15bcc  ldarg.1
0x15bcd  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::GetEnumerator()
0x15bd2  stloc.s  6
0x15bd4  br       loc_15CEE
0x15bd9  ldloca.s 6
0x15bdb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.UI.ScriptReferenceBase>::get_Current()
0x15be0  stloc.s  7
0x15be2  ldloc.s  7
0x15be4  isinst   System.Web.UI.CompositeScriptReference
0x15be9  stloc.s  8
0x15beb  ldloc.s  8
0x15bed  brfalse  loc_15CEE
0x15bf2  ldc.i4.0
0x15bf3  stloc.s  9
0x15bf5  ldloc.s  8
0x15bf7  callvirt instance class System.Web.UI.ScriptReferenceCollection System.Web.UI.CompositeScriptReference::get_Scripts()
0x15bfc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Web.UI.ScriptReference>::GetEnumerator()
0x15c01  stloc.s  0xA
0x15c03  br       loc_15CD4
0x15c08  ldloc.s  0xA
0x15c0a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Web.UI.ScriptReference>::get_Current()
0x15c0f  stloc.s  0xB
0x15c11  ldloc.s  0xB
0x15c13  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15c18  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15c1d  brtrue.s loc_15C35
0x15c1f  ldloc.s  0xB
0x15c21  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15c26  ldloc.s  0xB
0x15c28  ldarg.0
0x15c29  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.UI.ScriptReference::GetAssembly(class System.Web.UI.ScriptManager scriptManager)
0x15c2e  newobj   instance void class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::.ctor(var<u1>, !!T0)
0x15c33  br.s     loc_15C42
0x15c35  ldloc.s  0xB
0x15c37  callvirt instance string System.Web.UI.ScriptReference::get_EffectivePath()
0x15c3c  ldnull
0x15c3d  newobj   instance void class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::.ctor(var<u1>, !!T0)
0x15c42  stloc.s  0xC
0x15c44  ldloc.1
0x15c45  ldloc.s  0xC
0x15c47  callvirt instance bool [System]System.Collections.Specialized.HybridDictionary::Contains(object)
0x15c4c  brfalse.s loc_15C59
0x15c4e  call     string System.Web.Resources.AtlasWeb::get_ScriptManager_CannotRegisterScriptInMultipleCompositeReferences()
0x15c53  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x15c58  throw
0x15c59  ldarg.s  4
0x15c5b  brfalse.s loc_15C81
0x15c5d  ldloc.s  0xC
0x15c5f  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::get_Item2()
0x15c64  ldnull
0x15c65  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x15c6a  brfalse.s loc_15C81
0x15c6c  ldarg.s  4
0x15c6e  ldloc.s  0xC
0x15c70  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::get_Item2()
0x15c75  ldloc.s  0xC
0x15c77  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::get_Item1()
0x15c7c  call     void System.Web.UI.ScriptManager::RegisterResourceWithClientScriptManager(class System.Web.UI.IClientScriptManager clientScriptManager, class [mscorlib]System.Reflection.Assembly assembly, string key)
0x15c81  ldarg.2
0x15c82  ldc.i4.2
0x15c83  bne.un.s loc_15CAD
0x15c85  ldloc.s  0xB
0x15c87  ldarg.0
0x15c88  callvirt instance bool System.Web.UI.ScriptReferenceBase::IsAjaxFrameworkScript(class System.Web.UI.ScriptManager scriptManager)
0x15c8d  brfalse.s loc_15CAD
0x15c8f  ldarg.s  5
0x15c91  ldind.ref
0x15c92  brtrue.s loc_15CAD
0x15c94  ldloc.s  0xB
0x15c96  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15c9b  ldstr    aMicrosoftajaxa_0// "MicrosoftAjaxApplicationServices."
0x15ca0  ldc.i4.4
0x15ca1  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x15ca6  brfalse.s loc_15CAD
0x15ca8  ldarg.s  5
0x15caa  ldloc.s  8
0x15cac  stind.ref
0x15cad  ldarg.3
0x15cae  brtrue.s loc_15CCA
0x15cb0  ldloc.s  9
0x15cb2  brtrue.s loc_15CCA
0x15cb4  ldarg.0
0x15cb5  ldloc.s  0xB
0x15cb7  ldarg.2
0x15cb8  call     instance bool System.Web.UI.ScriptManager::NeedToLoadBeforeUI(class System.Web.UI.ScriptReference script, valuetype System.Web.UI.AjaxFrameworkMode ajaxMode)
0x15cbd  brfalse.s loc_15CCA
0x15cbf  ldloc.s  8
0x15cc1  ldc.i4.1
0x15cc2  callvirt instance void System.Web.UI.ScriptReferenceBase::set_AlwaysLoadBeforeUI(bool value)
0x15cc7  ldc.i4.1
0x15cc8  stloc.s  9
0x15cca  ldloc.1
0x15ccb  ldloc.s  0xC
0x15ccd  ldloc.s  0xB
0x15ccf  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Add(object, object)
0x15cd4  ldloc.s  0xA
0x15cd6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15cdb  brtrue   loc_15C08
0x15ce0  leave.s  loc_15CEE
0x15ce2  ldloc.s  0xA
0x15ce4  brfalse.s loc_15CED
0x15ce6  ldloc.s  0xA
0x15ce8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ced  endfinally
0x15cee  ldloca.s 6
0x15cf0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.UI.ScriptReferenceBase>::MoveNext()
0x15cf5  brtrue   loc_15BD9
0x15cfa  leave.s  loc_15D0A
0x15cfc  ldloca.s 6
0x15cfe  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.UI.ScriptReferenceBase>
0x15d04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15d09  endfinally
0x15d0a  ldarg.1
0x15d0b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::GetEnumerator()
0x15d10  stloc.s  0xD
0x15d12  br       loc_15E34
0x15d17  ldloca.s 0xD
0x15d19  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Web.UI.ScriptReferenceBase>::get_Current()
0x15d1e  stloc.s  0xE
0x15d20  ldloc.s  0xE
0x15d22  isinst   System.Web.UI.CompositeScriptReference
0x15d27  stloc.s  0xF
0x15d29  ldloc.s  0xF
0x15d2b  brfalse.s loc_15D3A
0x15d2d  ldloc.2
0x15d2e  ldloc.s  0xF
0x15d30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.UI.ScriptReferenceBase>::Add(var<u1>)
0x15d35  br       loc_15E34
0x15d3a  ldloc.s  0xE
0x15d3c  isinst   System.Web.UI.ScriptReference
0x15d41  stloc.s  0x10
0x15d43  ldloc.s  0x10
0x15d45  brfalse  loc_15E34
0x15d4a  ldloc.s  0x10
0x15d4c  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15d51  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15d56  brtrue.s loc_15D6E
0x15d58  ldloc.s  0x10
0x15d5a  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15d5f  ldloc.s  0x10
0x15d61  ldarg.0
0x15d62  callvirt instance class [mscorlib]System.Reflection.Assembly System.Web.UI.ScriptReference::GetAssembly(class System.Web.UI.ScriptManager scriptManager)
0x15d67  newobj   instance void class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::.ctor(var<u1>, !!T0)
0x15d6c  br.s     loc_15D7B
0x15d6e  ldloc.s  0x10
0x15d70  callvirt instance string System.Web.UI.ScriptReference::get_EffectivePath()
0x15d75  ldnull
0x15d76  newobj   instance void class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::.ctor(var<u1>, !!T0)
0x15d7b  stloc.s  0x11
0x15d7d  ldarg.2
0x15d7e  ldc.i4.2
0x15d7f  bne.un.s loc_15DA2
0x15d81  ldloc.s  0x10
0x15d83  ldarg.0
0x15d84  callvirt instance bool System.Web.UI.ScriptReferenceBase::IsAjaxFrameworkScript(class System.Web.UI.ScriptManager scriptManager)
0x15d89  brfalse.s loc_15DA2
0x15d8b  ldloc.s  0x10
0x15d8d  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15d92  ldstr    aMicrosoftajax// "MicrosoftAjax."
0x15d97  ldc.i4.4
0x15d98  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x15d9d  brtrue   loc_15E34
0x15da2  ldloc.1
0x15da3  ldloc.s  0x11
0x15da5  callvirt instance bool [System]System.Collections.Specialized.HybridDictionary::Contains(object)
0x15daa  brtrue   loc_15E34
0x15daf  ldloc.s  0x10
0x15db1  callvirt instance bool System.Web.UI.ScriptReferenceBase::get_IsStaticReference()
0x15db6  brfalse.s loc_15DC2
0x15db8  ldloc.1
0x15db9  ldloc.s  0x11
0x15dbb  ldloc.s  0x10
0x15dbd  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Add(object, object)
0x15dc2  ldarg.2
0x15dc3  ldc.i4.2
0x15dc4  bne.un.s loc_15DEE
0x15dc6  ldloc.s  0x10
0x15dc8  ldarg.0
0x15dc9  callvirt instance bool System.Web.UI.ScriptReferenceBase::IsAjaxFrameworkScript(class System.Web.UI.ScriptManager scriptManager)
0x15dce  brfalse.s loc_15DEE
0x15dd0  ldarg.s  5
0x15dd2  ldind.ref
0x15dd3  brtrue.s loc_15DEE
0x15dd5  ldloc.s  0x10
0x15dd7  callvirt instance string System.Web.UI.ScriptReference::get_EffectiveResourceName()
0x15ddc  ldstr    aMicrosoftajaxa_0// "MicrosoftAjaxApplicationServices."
0x15de1  ldc.i4.4
0x15de2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x15de7  brfalse.s loc_15DEE
0x15de9  ldarg.s  5
0x15deb  ldloc.s  0x10
0x15ded  stind.ref
0x15dee  ldarg.3
0x15def  brtrue.s loc_15E04
0x15df1  ldarg.0
0x15df2  ldloc.s  0x10
0x15df4  ldarg.2
0x15df5  call     instance bool System.Web.UI.ScriptManager::NeedToLoadBeforeUI(class System.Web.UI.ScriptReference script, valuetype System.Web.UI.AjaxFrameworkMode ajaxMode)
0x15dfa  brfalse.s loc_15E04
0x15dfc  ldloc.s  0x10
0x15dfe  ldc.i4.1
0x15dff  callvirt instance void System.Web.UI.ScriptReferenceBase::set_AlwaysLoadBeforeUI(bool value)
0x15e04  ldarg.s  4
0x15e06  brfalse.s loc_15E2C
0x15e08  ldloc.s  0x11
0x15e0a  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, class [mscorlib]System.Reflection.Assembly>::get_Item2()
0x15e0f  ldnull
0x15e10  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x15e15  brfalse.s loc_15E2C
  ... truncated ...
```
