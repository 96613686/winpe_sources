# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::SetValidatorScript

- ea: `0x2870`
- end: `0x2881`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::SetValidatorScript`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## string_xrefs

- `0x2876`: `<script language='Javascript' type='text/Javascript'>\n\n                 // Check whether the password has changed.\n                 function IsPasswordChanged(source, args)\n                 {\n                    if(document.getElementById('ShadowPassWordChangedID').value!='false')\n                         args.IsValid =false;\n                    else\n                         args.IsValid =true;\n                 }\n\n                 // Validate the given filename.\n         `

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.0
0x2871  ldfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_validatorScript
0x2876  ldstr    aScriptLanguage// "<script language='Javascript' type='tex"...
0x287b  callvirt instance void [System.Web]System.Web.UI.LiteralControl::set_Text(string)
0x2880  ret
```
