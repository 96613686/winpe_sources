# FilePathValidator::Validate_Path

- ea: `0x4100`
- end: `0x4143`
- name: `FilePathValidator::Validate_Path`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18e0`
- `0x36f0`
- `0x4100`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.0
0x4101  ldarg.1
0x4102  castclass [System.Web]System.Web.UI.WebControls.CustomValidator
0x4107  callvirt instance string [System.Web]System.Web.UI.WebControls.BaseValidator::get_ControlToValidate()
0x410c  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0x4111  castclass [System.Web]System.Web.UI.WebControls.TextBox
0x4116  dup
0x4117  dup
0x4118  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x411d  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath(string filePathOriginal)
0x4122  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0x4127  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x412c  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidPath(string pathname)
0x4131  brfalse.s loc_413B
0x4133  ldarg.2
0x4134  ldc.i4.1
0x4135  callvirt instance void [System.Web]System.Web.UI.WebControls.ServerValidateEventArgs::set_IsValid(bool)
0x413a  ret
0x413b  ldarg.2
0x413c  ldc.i4.0
0x413d  callvirt instance void [System.Web]System.Web.UI.WebControls.ServerValidateEventArgs::set_IsValid(bool)
0x4142  ret
```
