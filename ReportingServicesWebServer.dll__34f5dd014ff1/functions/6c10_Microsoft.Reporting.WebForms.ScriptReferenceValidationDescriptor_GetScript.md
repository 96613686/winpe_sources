# Microsoft.Reporting.WebForms.ScriptReferenceValidationDescriptor::GetScript

- ea: `0x6c10`
- end: `0x6c41`
- name: `Microsoft.Reporting.WebForms.ScriptReferenceValidationDescriptor::GetScript`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x229a0`

## string_xrefs

- `0x6c15`: `\nif ((document.compatMode && document.compatMode == 'BackCompat') ||\n    (document.compatMode && document.compatMode == 'CSS1Compat' && document.documentMode && (document.documentMode <= 8 && document.documentMode > 0))) {{\n    Sys.UI.DomElement.setVisible($get('{2}'), true);\n    Sys.UI.DomElement.setVisible($get('{1}_fixedTable'), false);    \n}} else if (typeof Microsoft == 'undefined' ||\n            typeof Microsoft.Reporting == 'undefined' ||\n            typeof Microsoft.Reporti`

## pseudocode

```c

```

## disassembly

```asm
0x6c10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c15  ldstr    aIfDocumentComp// "\r\nif ((document.compatMode && documen"...
0x6c1a  ldarg.0
0x6c1b  ldfld    string Microsoft.Reporting.WebForms.ScriptReferenceValidationDescriptor::m_errorMessageDivID
0x6c20  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::StringEscapeSingleQuote(string input)
0x6c25  ldarg.0
0x6c26  ldfld    string Microsoft.Reporting.WebForms.ScriptReferenceValidationDescriptor::m_viewerControlID
0x6c2b  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::StringEscapeSingleQuote(string input)
0x6c30  ldarg.0
0x6c31  ldfld    string Microsoft.Reporting.WebForms.ScriptReferenceValidationDescriptor::m_browserNotSupportedErrorMessageDivID
0x6c36  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::StringEscapeSingleQuote(string input)
0x6c3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x6c40  ret
```
