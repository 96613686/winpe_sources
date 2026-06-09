# Microsoft.Reporting.WebForms.MultiValidValuesSelector::AddScriptDescriptors

- ea: `0xe9e0`
- end: `0xea04`
- name: `Microsoft.Reporting.WebForms.MultiValidValuesSelector::AddScriptDescriptors`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xe950`
- `0x3aa00`

## string_xrefs

- `0xe9ee`: `HiddenIndicesId`

## pseudocode

```c

```

## disassembly

```asm
0xe9e0  ldarg.0
0xe9e1  callvirt instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0xe9e6  ldarg.0
0xe9e7  ldarg.1
0xe9e8  call     instance void Microsoft.Reporting.WebForms.MultiValueSelector::AddScriptDescriptors(class [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor desc)
0xe9ed  ldarg.1
0xe9ee  ldstr    aHiddenindicesi// "HiddenIndicesId"
0xe9f3  ldarg.0
0xe9f4  ldfld    class SelectedIndicies Microsoft.Reporting.WebForms.MultiValidValuesSelector::m_selectedIndicies
0xe9f9  callvirt instance string SelectedIndicies::get_HiddenFieldForClientUpdates()
0xe9fe  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xea03  ret
```
