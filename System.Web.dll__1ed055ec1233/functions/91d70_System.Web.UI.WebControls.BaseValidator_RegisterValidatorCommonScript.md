# System.Web.UI.WebControls.BaseValidator::RegisterValidatorCommonScript

- ea: `0x91d70`
- end: `0x91e66`
- name: `System.Web.UI.WebControls.BaseValidator::RegisterValidatorCommonScript`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x91d20`

## callees

- `0x5d500`
- `0x5da90`
- `0x5db70`
- `0x5ddd0`
- `0x5f680`
- `0x71aa0`
- `0x77250`
- `0x91600`
- `0x91d70`
- `0xe9bb0`
- `0xe9c30`
- `0xe9c70`

## string_xrefs

- `0x91e07`: `\nvar Page_ValidationActive = false;\nif (typeof(ValidatorOnLoad) == "function") {\n    ValidatorOnLoad();\n}\n\nfunction ValidatorOnSubmit() {\n    if (Page_ValidationActive) {\n        return ValidatorCommonOnSubmit();\n    }\n    else {\n        return true;\n    }\n}\n        `
- `0x91e5a`: `\nvar Page_ValidationActive = false;\nif (typeof(ValidatorOnLoad) == "function") {\n    ValidatorOnLoad();\n}\n\nfunction ValidatorOnSubmit() {\n    if (Page_ValidationActive) {\n        return ValidatorCommonOnSubmit();\n    }\n    else {\n        return true;\n    }\n}\n        `

## pseudocode

```c

```

## disassembly

```asm
0x91d70  ldarg.0
0x91d71  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x91d76  callvirt instance bool System.Web.UI.Page::get_IsPartialRenderingSupported()
0x91d7b  brtrue   loc_91E13
0x91d80  ldarg.0
0x91d81  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x91d86  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0x91d8b  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91d90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91d95  ldstr    aValidatorinclu// "ValidatorIncludeScript"
0x91d9a  callvirt instance bool System.Web.UI.ClientScriptManager::IsClientScriptBlockRegistered(class [mscorlib]System.Type type, string key)
0x91d9f  brfalse.s loc_91DA2
0x91da1  ret
0x91da2  ldarg.0
0x91da3  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x91da8  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0x91dad  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91db2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91db7  ldstr    aWebuivalidatio// "WebUIValidation.js"
0x91dbc  callvirt instance void System.Web.UI.ClientScriptManager::RegisterClientScriptResource(class [mscorlib]System.Type type, string resourceName)
0x91dc1  ldarg.0
0x91dc2  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x91dc7  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0x91dcc  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91dd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91dd6  ldstr    aValidatoronsub// "ValidatorOnSubmit"
0x91ddb  ldstr    aIfTypeofValida// "if (typeof(ValidatorOnSubmit) == \"func"...
0x91de0  callvirt instance void System.Web.UI.ClientScriptManager::RegisterOnSubmitStatement(class [mscorlib]System.Type type, string key, string script)
0x91de5  ldarg.0
0x91de6  call     instance bool System.Web.UI.WebControls.BaseValidator::get_IsUnobtrusive()
0x91deb  brtrue.s loc_91E65
0x91ded  ldarg.0
0x91dee  callvirt instance class System.Web.UI.Page System.Web.UI.Control::get_Page()
0x91df3  callvirt instance class System.Web.UI.ClientScriptManager System.Web.UI.Page::get_ClientScript()
0x91df8  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91dfd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91e02  ldstr    aValidatorinclu// "ValidatorIncludeScript"
0x91e07  ldstr    aVarPageValidat// "\r\nvar Page_ValidationActive = false;"...
0x91e0c  ldc.i4.1
0x91e0d  callvirt instance void System.Web.UI.ClientScriptManager::RegisterStartupScript(class [mscorlib]System.Type type, string key, string script, bool addScriptTags)
0x91e12  ret
0x91e13  ldarg.0
0x91e14  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91e19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91e1e  ldstr    aWebuivalidatio// "WebUIValidation.js"
0x91e23  call     void System.Web.UI.WebControls.ValidatorCompatibilityHelper::RegisterClientScriptResource(class System.Web.UI.Control control, class [mscorlib]System.Type type, string resourceName)
0x91e28  ldarg.0
0x91e29  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91e2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91e33  ldstr    aValidatoronsub// "ValidatorOnSubmit"
0x91e38  ldstr    aIfTypeofValida// "if (typeof(ValidatorOnSubmit) == \"func"...
0x91e3d  call     void System.Web.UI.WebControls.ValidatorCompatibilityHelper::RegisterOnSubmitStatement(class System.Web.UI.Control control, class [mscorlib]System.Type type, string key, string script)
0x91e42  ldarg.0
0x91e43  call     instance bool System.Web.UI.WebControls.BaseValidator::get_IsUnobtrusive()
0x91e48  brtrue.s loc_91E65
0x91e4a  ldarg.0
0x91e4b  ldtoken  System.Web.UI.WebControls.BaseValidator
0x91e50  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x91e55  ldstr    aValidatorinclu// "ValidatorIncludeScript"
0x91e5a  ldstr    aVarPageValidat// "\r\nvar Page_ValidationActive = false;"...
0x91e5f  ldc.i4.1
0x91e60  call     void System.Web.UI.WebControls.ValidatorCompatibilityHelper::RegisterStartupScript(class System.Web.UI.Control control, class [mscorlib]System.Type type, string key, string script, bool addScriptTags)
0x91e65  ret
```
