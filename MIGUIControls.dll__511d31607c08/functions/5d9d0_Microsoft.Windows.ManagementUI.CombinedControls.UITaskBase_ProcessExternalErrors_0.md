# Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors_0

- ea: `0x5d9d0`
- end: `0x5de5f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors_0`
- size: `1167`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d9c0`
- `0x5de70`
- `0x673c0`

## callees

- `0x11f50`
- `0x12ed0`
- `0x5d760`
- `0x5d840`
- `0x5d9b0`
- `0x5d9d0`
- `0x67c50`

## string_xrefs

- `0x5dab5`: `MessageTaskExists`
- `0x5dae4`: `MessageTaskExists`
- `0x5dacd`: `ErrorForTask`
- `0x5db2a`: `ErrorForTask`
- `0x5db87`: `ErrorForTask`
- `0x5dbe4`: `ErrorForTask`
- `0x5dc41`: `ErrorForTask`
- `0x5dc9e`: `ErrorForTask`
- `0x5dcfb`: `ErrorForTask`
- `0x5dd88`: `ErrorForTask`
- `0x5de2f`: `ErrorForTask`
- `0x5db12`: `MessageTaskDoesNotExist`
- `0x5db41`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x5d9d0  ldc.i4.1
0x5d9d1  stloc.0
0x5d9d2  ldarg.0
0x5d9d3  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x5d9d8  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x5d9dd  brtrue   loc_5DE5D
0x5d9e2  ldarg.2
0x5d9e3  ldc.i4   0x80070490
0x5d9e8  bgt.un.s loc_5DA3E
0x5d9ea  ldarg.2
0x5d9eb  ldc.i4   0x8007006D
0x5d9f0  bgt.un.s loc_5DA18
0x5d9f2  ldarg.2
0x5d9f3  ldc.i4   0x80070050
0x5d9f8  beq      loc_5DAAA
0x5d9fd  ldarg.2
0x5d9fe  ldc.i4   0x80070057
0x5da03  beq      loc_5DC1E
0x5da08  ldarg.2
0x5da09  ldc.i4   0x8007006D
0x5da0e  beq      loc_5DD35
0x5da13  br       loc_5DDC2
0x5da18  ldarg.2
0x5da19  ldc.i4   0x800700B7
0x5da1e  beq      loc_5DAAA
0x5da23  ldarg.2
0x5da24  ldc.i4   0x800703E6
0x5da29  beq      loc_5DD59
0x5da2e  ldarg.2
0x5da2f  ldc.i4   0x80070490
0x5da34  beq      loc_5DB07
0x5da39  br       loc_5DDC2
0x5da3e  ldarg.2
0x5da3f  ldc.i4   0x8007052F
0x5da44  bgt.un.s loc_5DA6C
0x5da46  ldarg.2
0x5da47  ldc.i4   0x8007050F
0x5da4c  beq      loc_5DBC1
0x5da51  ldarg.2
0x5da52  ldc.i4   0x8007052E
0x5da57  beq      loc_5DC7B
0x5da5c  ldarg.2
0x5da5d  ldc.i4   0x8007052F
0x5da62  beq      loc_5DCD8
0x5da67  br       loc_5DDC2
0x5da6c  ldarg.2
0x5da6d  ldc.i4   0x800706B5
0x5da72  bgt.un.s loc_5DA8F
0x5da74  ldarg.2
0x5da75  ldc.i4   0x80070534
0x5da7a  beq      loc_5DB64
0x5da7f  ldarg.2
0x5da80  ldc.i4   0x800706B5
0x5da85  beq      loc_5DD41
0x5da8a  br       loc_5DDC2
0x5da8f  ldarg.2
0x5da90  ldc.i4   0x800706BE
0x5da95  beq      loc_5DD4D
0x5da9a  ldarg.2
0x5da9b  ldc.i4   0x80073A99
0x5daa0  beq      loc_5DD65
0x5daa5  br       loc_5DDC2
0x5daaa  ldarg.s  5
0x5daac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dab1  brfalse.s loc_5DACA
0x5dab3  ldarg.0
0x5dab4  ldarg.1
0x5dab5  ldstr    aMessagetaskexi// "MessageTaskExists"
0x5daba  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dabf  ldarg.3
0x5dac0  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dac5  br       loc_5DE5D
0x5daca  ldarg.0
0x5dacb  ldarg.1
0x5dacc  ldnull
0x5dacd  ldstr    aErrorfortask// "ErrorForTask"
0x5dad2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dad7  ldc.i4.3
0x5dad8  newarr   [mscorlib]System.Object
0x5dadd  dup
0x5dade  ldc.i4.0
0x5dadf  ldarg.s  5
0x5dae1  stelem.ref
0x5dae2  dup
0x5dae3  ldc.i4.1
0x5dae4  ldstr    aMessagetaskexi// "MessageTaskExists"
0x5dae9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5daee  stelem.ref
0x5daef  dup
0x5daf0  ldc.i4.2
0x5daf1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5daf6  stelem.ref
0x5daf7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dafc  ldarg.3
0x5dafd  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5db02  br       loc_5DE5D
0x5db07  ldarg.s  5
0x5db09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5db0e  brfalse.s loc_5DB27
0x5db10  ldarg.0
0x5db11  ldarg.1
0x5db12  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x5db17  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5db1c  ldarg.3
0x5db1d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5db22  br       loc_5DE5D
0x5db27  ldarg.0
0x5db28  ldarg.1
0x5db29  ldnull
0x5db2a  ldstr    aErrorfortask// "ErrorForTask"
0x5db2f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5db34  ldc.i4.3
0x5db35  newarr   [mscorlib]System.Object
0x5db3a  dup
0x5db3b  ldc.i4.0
0x5db3c  ldarg.s  5
0x5db3e  stelem.ref
0x5db3f  dup
0x5db40  ldc.i4.1
0x5db41  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x5db46  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5db4b  stelem.ref
0x5db4c  dup
0x5db4d  ldc.i4.2
0x5db4e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5db53  stelem.ref
0x5db54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5db59  ldarg.3
0x5db5a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5db5f  br       loc_5DE5D
0x5db64  ldarg.s  5
0x5db66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5db6b  brfalse.s loc_5DB84
0x5db6d  ldarg.0
0x5db6e  ldarg.1
0x5db6f  ldstr    aMessageinvalid_0// "MessageInvalidAccountName"
0x5db74  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5db79  ldarg.3
0x5db7a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5db7f  br       loc_5DE5D
0x5db84  ldarg.0
0x5db85  ldarg.1
0x5db86  ldnull
0x5db87  ldstr    aErrorfortask// "ErrorForTask"
0x5db8c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5db91  ldc.i4.3
0x5db92  newarr   [mscorlib]System.Object
0x5db97  dup
0x5db98  ldc.i4.0
0x5db99  ldarg.s  5
0x5db9b  stelem.ref
0x5db9c  dup
0x5db9d  ldc.i4.1
0x5db9e  ldstr    aMessageinvalid_0// "MessageInvalidAccountName"
0x5dba3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dba8  stelem.ref
0x5dba9  dup
0x5dbaa  ldc.i4.2
0x5dbab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5dbb0  stelem.ref
0x5dbb1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dbb6  ldarg.3
0x5dbb7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dbbc  br       loc_5DE5D
0x5dbc1  ldarg.s  5
0x5dbc3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dbc8  brfalse.s loc_5DBE1
0x5dbca  ldarg.0
0x5dbcb  ldarg.1
0x5dbcc  ldstr    aMessageaccount// "MessageAccountRestricted"
0x5dbd1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dbd6  ldarg.3
0x5dbd7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dbdc  br       loc_5DE5D
0x5dbe1  ldarg.0
0x5dbe2  ldarg.1
0x5dbe3  ldnull
0x5dbe4  ldstr    aErrorfortask// "ErrorForTask"
0x5dbe9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dbee  ldc.i4.3
0x5dbef  newarr   [mscorlib]System.Object
0x5dbf4  dup
0x5dbf5  ldc.i4.0
0x5dbf6  ldarg.s  5
0x5dbf8  stelem.ref
0x5dbf9  dup
0x5dbfa  ldc.i4.1
0x5dbfb  ldstr    aMessageaccount// "MessageAccountRestricted"
0x5dc00  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dc05  stelem.ref
0x5dc06  dup
0x5dc07  ldc.i4.2
0x5dc08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5dc0d  stelem.ref
0x5dc0e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dc13  ldarg.3
0x5dc14  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dc19  br       loc_5DE5D
0x5dc1e  ldarg.s  5
0x5dc20  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dc25  brfalse.s loc_5DC3E
0x5dc27  ldarg.0
0x5dc28  ldarg.1
0x5dc29  ldstr    aMessageinvalid_1// "MessageInvalidArgument"
0x5dc2e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dc33  ldarg.3
0x5dc34  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dc39  br       loc_5DE5D
0x5dc3e  ldarg.0
0x5dc3f  ldarg.1
0x5dc40  ldnull
0x5dc41  ldstr    aErrorfortask// "ErrorForTask"
0x5dc46  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dc4b  ldc.i4.3
0x5dc4c  newarr   [mscorlib]System.Object
0x5dc51  dup
0x5dc52  ldc.i4.0
0x5dc53  ldarg.s  5
0x5dc55  stelem.ref
0x5dc56  dup
0x5dc57  ldc.i4.1
0x5dc58  ldstr    aMessageinvalid_1// "MessageInvalidArgument"
0x5dc5d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dc62  stelem.ref
0x5dc63  dup
0x5dc64  ldc.i4.2
0x5dc65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5dc6a  stelem.ref
0x5dc6b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dc70  ldarg.3
0x5dc71  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dc76  br       loc_5DE5D
0x5dc7b  ldarg.s  5
0x5dc7d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dc82  brfalse.s loc_5DC9B
0x5dc84  ldarg.0
0x5dc85  ldarg.1
0x5dc86  ldstr    aMessagelogonfa// "MessageLogonFailure"
0x5dc8b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dc90  ldarg.3
0x5dc91  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dc96  br       loc_5DE5D
0x5dc9b  ldarg.0
0x5dc9c  ldarg.1
0x5dc9d  ldnull
0x5dc9e  ldstr    aErrorfortask// "ErrorForTask"
0x5dca3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dca8  ldc.i4.3
0x5dca9  newarr   [mscorlib]System.Object
0x5dcae  dup
0x5dcaf  ldc.i4.0
0x5dcb0  ldarg.s  5
0x5dcb2  stelem.ref
0x5dcb3  dup
0x5dcb4  ldc.i4.1
0x5dcb5  ldstr    aMessagelogonfa// "MessageLogonFailure"
0x5dcba  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dcbf  stelem.ref
0x5dcc0  dup
0x5dcc1  ldc.i4.2
0x5dcc2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5dcc7  stelem.ref
0x5dcc8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dccd  ldarg.3
0x5dcce  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dcd3  br       loc_5DE5D
0x5dcd8  ldarg.s  5
0x5dcda  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5dcdf  brfalse.s loc_5DCF8
0x5dce1  ldarg.0
0x5dce2  ldarg.1
0x5dce3  ldstr    aMessageaccount// "MessageAccountRestricted"
0x5dce8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dced  ldarg.3
0x5dcee  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dcf3  br       loc_5DE5D
0x5dcf8  ldarg.0
0x5dcf9  ldarg.1
0x5dcfa  ldnull
0x5dcfb  ldstr    aErrorfortask// "ErrorForTask"
0x5dd00  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dd05  ldc.i4.3
0x5dd06  newarr   [mscorlib]System.Object
0x5dd0b  dup
0x5dd0c  ldc.i4.0
0x5dd0d  ldarg.s  5
0x5dd0f  stelem.ref
0x5dd10  dup
0x5dd11  ldc.i4.1
0x5dd12  ldstr    aMessageaccount// "MessageAccountRestricted"
0x5dd17  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x5dd1c  stelem.ref
0x5dd1d  dup
0x5dd1e  ldc.i4.2
0x5dd1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5dd24  stelem.ref
0x5dd25  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dd2a  ldarg.3
0x5dd2b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x5dd30  br       loc_5DE5D
  ... truncated ...
```
