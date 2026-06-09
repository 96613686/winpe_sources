# System.Web.UI.WebControls.CompareValidator::AddAttributesToRender

- ea: `0x9c7e0`
- end: `0x9c8c2`
- name: `System.Web.UI.WebControls.CompareValidator::AddAttributesToRender`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x5ef10`
- `0x5f770`
- `0x7b640`
- `0x8fe80`
- `0x8fed0`
- `0x8ff10`
- `0x90890`
- `0x91600`
- `0x917f0`
- `0x91a60`
- `0x91a70`
- `0x91c00`
- `0x9c6f0`
- `0x9c740`
- `0x9c790`
- `0x9c7e0`

## string_xrefs

- `0x9c816`: `CompareValidatorEvaluateIsValid`
- `0x9c83f`: `controltocompare`
- `0x9c886`: `valuetocompare`

## pseudocode

```c

```

## disassembly

```asm
0x9c7e0  ldarg.0
0x9c7e1  ldarg.1
0x9c7e2  call     instance void System.Web.UI.WebControls.BaseCompareValidator::AddAttributesToRender(class System.Web.UI.HtmlTextWriter writer)
0x9c7e7  ldarg.0
0x9c7e8  call     instance bool System.Web.UI.WebControls.BaseValidator::get_RenderUplevel()
0x9c7ed  brfalse  loc_9C8C1
0x9c7f2  ldarg.0
0x9c7f3  callvirt instance string System.Web.UI.Control::get_ClientID()
0x9c7f8  stloc.0
0x9c7f9  ldarg.0
0x9c7fa  call     instance bool System.Web.UI.Control::get_EnableLegacyRendering()
0x9c7ff  brtrue.s loc_9C80C
0x9c801  ldarg.0
0x9c802  call     instance bool System.Web.UI.WebControls.BaseValidator::get_IsUnobtrusive()
0x9c807  brtrue.s loc_9C80C
0x9c809  ldnull
0x9c80a  br.s     loc_9C80D
0x9c80c  ldarg.1
0x9c80d  stloc.1
0x9c80e  ldarg.0
0x9c80f  ldloc.1
0x9c810  ldloc.0
0x9c811  ldstr    aEvaluationfunc// "evaluationfunction"
0x9c816  ldstr    aComparevalidat// "CompareValidatorEvaluateIsValid"
0x9c81b  ldc.i4.0
0x9c81c  call     instance void System.Web.UI.WebControls.BaseValidator::AddExpandoAttribute(class System.Web.UI.HtmlTextWriter writer, string controlId, string attributeName, string attributeValue, bool encode)
0x9c821  ldarg.0
0x9c822  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c827  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9c82c  ldc.i4.0
0x9c82d  ble.s    loc_9C858
0x9c82f  ldarg.0
0x9c830  ldarg.0
0x9c831  call     instance string System.Web.UI.WebControls.CompareValidator::get_ControlToCompare()
0x9c836  call     instance string System.Web.UI.WebControls.BaseValidator::GetControlRenderID(string name)
0x9c83b  stloc.2
0x9c83c  ldarg.0
0x9c83d  ldloc.1
0x9c83e  ldloc.0
0x9c83f  ldstr    aControltocompa_0// "controltocompare"
0x9c844  ldloc.2
0x9c845  call     instance void System.Web.UI.WebControls.BaseValidator::AddExpandoAttribute(class System.Web.UI.HtmlTextWriter writer, string controlId, string attributeName, string attributeValue)
0x9c84a  ldarg.0
0x9c84b  ldloc.1
0x9c84c  ldloc.0
0x9c84d  ldstr    aControlhookup// "controlhookup"
0x9c852  ldloc.2
0x9c853  call     instance void System.Web.UI.WebControls.BaseValidator::AddExpandoAttribute(class System.Web.UI.HtmlTextWriter writer, string controlId, string attributeName, string attributeValue)
0x9c858  ldarg.0
0x9c859  call     instance string System.Web.UI.WebControls.CompareValidator::get_ValueToCompare()
0x9c85e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9c863  ldc.i4.0
0x9c864  ble.s    loc_9C891
0x9c866  ldarg.0
0x9c867  call     instance string System.Web.UI.WebControls.CompareValidator::get_ValueToCompare()
0x9c86c  stloc.3
0x9c86d  ldarg.0
0x9c86e  call     instance bool System.Web.UI.WebControls.BaseCompareValidator::get_CultureInvariantValues()
0x9c873  brfalse.s loc_9C883
0x9c875  ldarg.0
0x9c876  ldloc.3
0x9c877  ldarg.0
0x9c878  call     instance valuetype System.Web.UI.WebControls.ValidationDataType System.Web.UI.WebControls.BaseCompareValidator::get_Type()
0x9c87d  call     instance string System.Web.UI.WebControls.BaseCompareValidator::ConvertCultureInvariantToCurrentCultureFormat(string valueInString, valuetype System.Web.UI.WebControls.ValidationDataType type)
0x9c882  stloc.3
0x9c883  ldarg.0
0x9c884  ldloc.1
0x9c885  ldloc.0
0x9c886  ldstr    aValuetocompare_0// "valuetocompare"
0x9c88b  ldloc.3
0x9c88c  call     instance void System.Web.UI.WebControls.BaseValidator::AddExpandoAttribute(class System.Web.UI.HtmlTextWriter writer, string controlId, string attributeName, string attributeValue)
0x9c891  ldarg.0
0x9c892  call     instance valuetype System.Web.UI.WebControls.ValidationCompareOperator System.Web.UI.WebControls.CompareValidator::get_Operator()
0x9c897  brfalse.s loc_9C8C1
0x9c899  ldarg.0
0x9c89a  ldloc.1
0x9c89b  ldloc.0
0x9c89c  ldstr    aOperator_0// "operator"
0x9c8a1  ldtoken  System.Web.UI.WebControls.ValidationCompareOperator
0x9c8a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9c8ab  ldarg.0
0x9c8ac  call     instance valuetype System.Web.UI.WebControls.ValidationCompareOperator System.Web.UI.WebControls.CompareValidator::get_Operator()
0x9c8b1  box      System.Web.UI.WebControls.ValidationCompareOperator
0x9c8b6  call     string System.Web.UI.PropertyConverter::EnumToString(class [mscorlib]System.Type enumType, object enumValue)
0x9c8bb  ldc.i4.0
0x9c8bc  call     instance void System.Web.UI.WebControls.BaseValidator::AddExpandoAttribute(class System.Web.UI.HtmlTextWriter writer, string controlId, string attributeName, string attributeValue, bool encode)
0x9c8c1  ret
```
