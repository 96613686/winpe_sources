# Microsoft.Reporting.WebForms.ParametersArea::GetScriptDescriptors

- ea: `0xa390`
- end: `0xa4a2`
- name: `Microsoft.Reporting.WebForms.ParametersArea::GetScriptDescriptors`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xa390`
- `0xa540`
- `0xa960`
- `0xa9a0`
- `0xb980`
- `0xc300`

## string_xrefs

- `0xa3c6`: `CredentialsLinkId`

## pseudocode

```c

```

## disassembly

```asm
0xa390  ldarg.0
0xa391  callvirt instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0xa396  ldstr    aMicrosoftRepor_32// "Microsoft.Reporting.WebFormsClient._Pro"...
0xa39b  ldarg.0
0xa39c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa3a1  newobj   instance void [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor::.ctor(string, string)
0xa3a6  stloc.0
0xa3a7  ldarg.0
0xa3a8  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ParametersArea::m_viewer
0xa3ad  brfalse.s loc_A3C5
0xa3af  ldloc.0
0xa3b0  ldstr    aReportviewerid// "ReportViewerId"
0xa3b5  ldarg.0
0xa3b6  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ParametersArea::m_viewer
0xa3bb  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa3c0  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa3c5  ldloc.0
0xa3c6  ldstr    aCredentialslin// "CredentialsLinkId"
0xa3cb  ldarg.0
0xa3cc  ldfld    class Microsoft.Reporting.WebForms.TextButton Microsoft.Reporting.WebForms.ParametersArea::m_changeCredentials
0xa3d1  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa3d6  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa3db  ldloc.0
0xa3dc  ldstr    aParametersgrid// "ParametersGridID"
0xa3e1  ldarg.0
0xa3e2  callvirt instance string Microsoft.Reporting.WebForms.ParametersArea::get_ParametersGridID()
0xa3e7  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa3ec  ldloc.0
0xa3ed  ldstr    aViewreportbutt// "ViewReportButtonId"
0xa3f2  ldarg.0
0xa3f3  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0xa3f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa3fd  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa402  ldarg.0
0xa403  ldfld    class Microsoft.Reporting.WebForms.ParameterControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramControls
0xa408  brfalse.s loc_A471
0xa40a  ldarg.0
0xa40b  call     instance bool Microsoft.Reporting.WebForms.ParametersArea::get_RenderParameters()
0xa410  brfalse.s loc_A471
0xa412  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xa417  stloc.1
0xa418  ldarg.0
0xa419  ldfld    class Microsoft.Reporting.WebForms.ParameterControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramControls
0xa41e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Reporting.WebForms.BaseParameterInputControl>::get_Values()
0xa423  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class Microsoft.Reporting.WebForms.BaseParameterInputControl>::GetEnumerator()
0xa428  stloc.2
0xa429  br.s     loc_A447
0xa42b  ldloca.s 2
0xa42d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Reporting.WebForms.BaseParameterInputControl>::get_Current()
0xa432  stloc.3
0xa433  ldloc.3
0xa434  callvirt instance bool Microsoft.Reporting.WebForms.BaseParameterInputControl::get_Disabled()
0xa439  brtrue.s loc_A447
0xa43b  ldloc.1
0xa43c  ldloc.3
0xa43d  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa442  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xa447  ldloca.s 2
0xa449  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Reporting.WebForms.BaseParameterInputControl>::MoveNext()
0xa44e  brtrue.s loc_A42B
0xa450  leave.s  loc_A460
0xa452  ldloca.s 2
0xa454  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class Microsoft.Reporting.WebForms.BaseParameterInputControl>
0xa45a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa45f  endfinally
0xa460  ldloc.0
0xa461  ldstr    aParameteridlis// "ParameterIdList"
0xa466  ldloc.1
0xa467  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xa46c  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa471  ldarg.0
0xa472  ldfld    class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsControls
0xa477  brfalse.s loc_A497
0xa479  ldarg.0
0xa47a  call     instance bool Microsoft.Reporting.WebForms.ParametersArea::get_ShouldRenderCredentialsIfSupported()
0xa47f  brfalse.s loc_A497
0xa481  ldloc.0
0xa482  ldstr    aCredentialidli// "CredentialIdList"
0xa487  ldarg.0
0xa488  ldfld    class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsControls
0xa48d  callvirt instance string[] Microsoft.Reporting.WebForms.DataSourceControlCollection::get_DataSourceClientIds()
0xa492  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xa497  ldc.i4.1
0xa498  newarr   [System.Web.Extensions]System.Web.UI.ScriptDescriptor
0xa49d  dup
0xa49e  ldc.i4.0
0xa49f  ldloc.0
0xa4a0  stelem.ref
0xa4a1  ret
```
