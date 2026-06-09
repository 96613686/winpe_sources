# GenericConvertToTemplateHelper`2::ConvertToTemplate

- ea: `0xf92f0`
- end: `0xf93c7`
- name: `GenericConvertToTemplateHelper`2::ConvertToTemplate`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x2710`
- `0x2c50`
- `0x4e90`
- `0xf92f0`

## string_xrefs

- `0xf9322`: `ConvertToTemplate`
- `0xf93a3`: `ConvertToTemplate`

## pseudocode

```c

```

## disassembly

```asm
0xf92f0  ldnull
0xf92f1  stloc.0
0xf92f2  ldarg.0
0xf92f3  ldarg.0
0xf92f4  call     instance var<u1> class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::get_ViewControl()
0xf92f9  callvirt instance class [System.Web]System.Web.UI.ITemplate class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::GetTemplate(var<u1>)
0xf92fe  stloc.1
0xf92ff  ldloc.1
0xf9300  brfalse.s loc_F9309
0xf9302  ldloc.1
0xf9303  stloc.0
0xf9304  br       loc_F93C5
0xf9309  ldarg.0
0xf930a  ldfld    var<u1> class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::_designer
0xf930f  box      var<u1>
0xf9314  ldc.i4.0
0xf9315  callvirt instance void System.Web.UI.Design.ControlDesigner::set_ViewControlCreated(bool value)
0xf931a  ldc.i4.1
0xf931b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0xf9320  stloc.2
0xf9321  ldloc.2
0xf9322  ldstr    aConverttotempl// "ConvertToTemplate"
0xf9327  ldc.i4.1
0xf9328  box      [mscorlib]System.Boolean
0xf932d  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xf9332  ldarg.0
0xf9333  call     instance var<u1> class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::get_ViewControl()
0xf9338  box      var<u1>
0xf933d  ldloc.2
0xf933e  callvirt instance void [System.Web]System.Web.UI.IControlDesignerAccessor::SetDesignModeState(class [mscorlib]System.Collections.IDictionary)
0xf9343  ldarg.0
0xf9344  ldfld    var<u1> class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::_designer
0xf9349  box      var<u1>
0xf934e  callvirt instance string System.Web.UI.Design.ControlDesigner::GetDesignTimeHtml()
0xf9353  pop
0xf9354  ldarg.0
0xf9355  callvirt instance class [System.Web]System.Web.UI.Control class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::GetDefaultTemplateContents()
0xf935a  stloc.3
0xf935b  ldarg.0
0xf935c  ldloc.3
0xf935d  call     instance void class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::SetFailureTextStyle(class [System.Web]System.Web.UI.Control)
0xf9362  ldarg.0
0xf9363  ldloc.3
0xf9364  call     instance void class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::ConvertPersistedControlsToLiteralControls(class [System.Web]System.Web.UI.Control)
0xf9369  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xf936e  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xf9373  stloc.s  4
0xf9375  ldloc.s  4
0xf9377  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xf937c  stloc.s  5
0xf937e  ldloc.3
0xf937f  ldloc.s  5
0xf9381  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xf9386  ldarg.0
0xf9387  ldfld    class [System]System.ComponentModel.Design.IDesignerHost class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::_designerHost
0xf938c  ldloc.s  4
0xf938e  callvirt instance string [mscorlib]System.Object::ToString()
0xf9393  call     class [System.Web]System.Web.UI.ITemplate System.Web.UI.Design.ControlParser::ParseTemplate(class [System]System.ComponentModel.Design.IDesignerHost designerHost, string templateText)
0xf9398  stloc.0
0xf9399  ldc.i4.1
0xf939a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0xf939f  stloc.s  6
0xf93a1  ldloc.s  6
0xf93a3  ldstr    aConverttotempl// "ConvertToTemplate"
0xf93a8  ldc.i4.0
0xf93a9  box      [mscorlib]System.Boolean
0xf93ae  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xf93b3  ldarg.0
0xf93b4  call     instance var<u1> class GenericConvertToTemplateHelper`2<var<u1>, !!T0>::get_ViewControl()
0xf93b9  box      var<u1>
0xf93be  ldloc.s  6
0xf93c0  callvirt instance void [System.Web]System.Web.UI.IControlDesignerAccessor::SetDesignModeState(class [mscorlib]System.Collections.IDictionary)
0xf93c5  ldloc.0
0xf93c6  ret
```
