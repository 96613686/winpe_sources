# ObjectPicker::GetSelections

- ea: `0xa0ca0`
- end: `0xa1132`
- name: `ObjectPicker::GetSelections`
- size: `1170`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xa0a00`

## callees

- `0x11e10`
- `0x11f00`
- `0x35250`
- `0x356a0`
- `0xa0450`
- `0xa0460`
- `0xa0470`
- `0xa04d0`
- `0xa0570`
- `0xa0ca0`

## string_xrefs

- `0xa1001`: `Computer`
- `0xa104d`: `foreignSecurityPrincipal`

## pseudocode

```c

```

## disassembly

```asm
0xa0ca0  ldarg.1
0xa0ca1  brtrue.s loc_A0CA5
0xa0ca3  ldnull
0xa0ca4  ret
0xa0ca5  ldnull
0xa0ca6  stloc.0
0xa0ca7  ldloca.s 2
0xa0ca9  initobj  FORMATETC
0xa0caf  ldloca.s 2
0xa0cb1  ldstr    aCfstrDsopDsSel// "CFSTR_DSOP_DS_SELECTION_LIST"
0xa0cb6  call     class [System.Windows.Forms]System.Windows.Forms.DataFormats/Format [System.Windows.Forms]System.Windows.Forms.DataFormats::GetFormat(string)
0xa0cbb  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DataFormats/Format::get_Id()
0xa0cc0  stfld    int32 FORMATETC::cfFormat
0xa0cc5  ldloca.s 2
0xa0cc7  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa0ccc  stfld    native int FORMATETC::ptd
0xa0cd1  ldloca.s 2
0xa0cd3  ldc.i4.1
0xa0cd4  stfld    unsigned int32 FORMATETC::dwAspect
0xa0cd9  ldloca.s 2
0xa0cdb  ldc.i4.m1
0xa0cdc  stfld    int32 FORMATETC::lindex
0xa0ce1  ldloca.s 2
0xa0ce3  ldc.i4.1
0xa0ce4  stfld    unsigned int32 FORMATETC::tymed
0xa0ce9  ldarg.1
0xa0cea  ldloca.s 2
0xa0cec  ldloca.s 1
0xa0cee  callvirt instance void IDataObject::GetData(valuetype FORMATETC& pFormatetc, [out] valuetype STGMEDIUM& pmedium)
0xa0cf3  ldloc.1
0xa0cf4  ldfld    native int STGMEDIUM::hGlobal
0xa0cf9  call     native int PInvoke::GlobalLock(native int hMem)
0xa0cfe  stloc.3
0xa0cff  ldloc.3
0xa0d00  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReadInt32(native int)
0xa0d05  stloc.s  4
0xa0d07  ldloc.s  4
0xa0d09  newarr   PickerObject
0xa0d0e  stloc.0
0xa0d0f  ldloc.3
0xa0d10  ldtoken  [mscorlib]System.UInt32
0xa0d15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa0d1a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0xa0d1f  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0xa0d24  stloc.3
0xa0d25  ldloc.3
0xa0d26  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReadInt32(native int)
0xa0d2b  stloc.s  5
0xa0d2d  ldloc.3
0xa0d2e  ldtoken  [mscorlib]System.UInt32
0xa0d33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa0d38  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0xa0d3d  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0xa0d42  stloc.3
0xa0d43  ldtoken  DS_SELECTION
0xa0d48  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa0d4d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0xa0d52  stloc.s  6
0xa0d54  ldc.i4.0
0xa0d55  stloc.s  7
0xa0d57  br       loc_A1111
0xa0d5c  ldloc.3
0xa0d5d  ldtoken  DS_SELECTION
0xa0d62  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa0d67  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0xa0d6c  unbox.any DS_SELECTION
0xa0d71  stloc.s  8
0xa0d73  ldnull
0xa0d74  stloc.s  9
0xa0d76  ldloc.s  8
0xa0d78  ldfld    native int DS_SELECTION::pvarFetchedAttributes
0xa0d7d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa0d82  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0xa0d87  brfalse.s loc_A0D99
0xa0d89  ldloc.s  8
0xa0d8b  ldfld    native int DS_SELECTION::pvarFetchedAttributes
0xa0d90  ldloc.s  5
0xa0d92  call     object[] [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectsForNativeVariants(native int, int32)
0xa0d97  stloc.s  9
0xa0d99  ldc.i4.0
0xa0d9a  stloc.s  0xA
0xa0d9c  ldsfld   string [mscorlib]System.String::Empty
0xa0da1  stloc.s  0xB
0xa0da3  ldloc.s  9
0xa0da5  brfalse.s loc_A0DC9
0xa0da7  ldloc.s  9
0xa0da9  ldlen
0xa0daa  brfalse.s loc_A0DC9
0xa0dac  ldloc.s  9
0xa0dae  ldc.i4.0
0xa0daf  ldelem.ref
0xa0db0  castclass [mscorlib]System.String
0xa0db5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0dba  brtrue.s loc_A0DC9
0xa0dbc  ldloc.s  9
0xa0dbe  ldc.i4.0
0xa0dbf  ldelem.ref
0xa0dc0  castclass [mscorlib]System.String
0xa0dc5  stloc.s  0xB
0xa0dc7  br.s     loc_A0E06
0xa0dc9  ldloc.s  8
0xa0dcb  ldfld    string DS_SELECTION::pwzUPN
0xa0dd0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0dd5  brfalse.s loc_A0DE2
0xa0dd7  ldloc.s  8
0xa0dd9  ldfld    string DS_SELECTION::pwzName
0xa0dde  stloc.s  0xB
0xa0de0  br.s     loc_A0E06
0xa0de2  ldloc.s  8
0xa0de4  ldfld    string DS_SELECTION::pwzUPN
0xa0de9  ldc.i4.1
0xa0dea  newarr   [mscorlib]System.Char
0xa0def  dup
0xa0df0  ldc.i4.0
0xa0df1  ldc.i4.s 0x40
0xa0df3  stelem.i2
0xa0df4  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xa0df9  stloc.s  0x12
0xa0dfb  ldloc.s  0x12
0xa0dfd  ldlen
0xa0dfe  brfalse.s loc_A0E06
0xa0e00  ldloc.s  0x12
0xa0e02  ldc.i4.0
0xa0e03  ldelem.ref
0xa0e04  stloc.s  0xB
0xa0e06  ldc.i4.0
0xa0e07  stloc.s  0xC
0xa0e09  ldc.i4.0
0xa0e0a  stloc.s  0xD
0xa0e0c  ldsfld   string [mscorlib]System.String::Empty
0xa0e11  stloc.s  0xE
0xa0e13  ldloc.s  9
0xa0e15  brfalse.s loc_A0E36
0xa0e17  ldloc.s  9
0xa0e19  ldc.i4.1
0xa0e1a  ldelem.ref
0xa0e1b  castclass unsigned int8[]
0xa0e20  ldc.i4.0
0xa0e21  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0xa0e26  ldloca.s 0x13
0xa0e28  ldloca.s 0xE
0xa0e2a  ldloca.s 0x14
0xa0e2c  call     unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::LookupAccountSid(class [mscorlib]System.Security.Principal.SecurityIdentifier sid, [out] string& accountName, [out] string& domainName, [out] int32& use)
0xa0e31  brtrue.s loc_A0E36
0xa0e33  ldc.i4.1
0xa0e34  stloc.s  0xD
0xa0e36  ldloc.s  0xD
0xa0e38  brtrue   loc_A0EFC
0xa0e3d  ldloc.s  8
0xa0e3f  ldfld    string DS_SELECTION::pwzADsPath
0xa0e44  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0e49  brtrue   loc_A0EFC
0xa0e4e  ldloc.s  8
0xa0e50  ldfld    string DS_SELECTION::pwzADsPath
0xa0e55  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetNT4DomainFromFQDN(string fqdnPath)
0xa0e5a  stloc.s  0x15
0xa0e5c  ldloc.s  0x15
0xa0e5e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0e63  brtrue.s loc_A0E6E
0xa0e65  ldloc.s  0x15
0xa0e67  stloc.s  0xE
0xa0e69  br       loc_A0EFC
0xa0e6e  ldloc.s  8
0xa0e70  ldfld    string DS_SELECTION::pwzADsPath
0xa0e75  ldc.i4.1
0xa0e76  newarr   [mscorlib]System.Char
0xa0e7b  dup
0xa0e7c  ldc.i4.0
0xa0e7d  ldc.i4.s 0x2C
0xa0e7f  stelem.i2
0xa0e80  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xa0e85  stloc.s  0x16
0xa0e87  ldloc.s  0x16
0xa0e89  brfalse.s loc_A0EFC
0xa0e8b  ldloc.s  0x16
0xa0e8d  ldlen
0xa0e8e  brfalse.s loc_A0EFC
0xa0e90  ldc.i4.0
0xa0e91  stloc.s  0x17
0xa0e93  br.s     loc_A0EF4
0xa0e95  ldloc.s  0x16
0xa0e97  ldloc.s  0x17
0xa0e99  ldelem.ref
0xa0e9a  ldstr    aDc// "DC="
0xa0e9f  callvirt instance bool [mscorlib]System.String::Contains(string)
0xa0ea4  brfalse.s loc_A0EEE
0xa0ea6  ldloc.s  0x16
0xa0ea8  ldloc.s  0x17
0xa0eaa  ldelem.ref
0xa0eab  ldc.i4.1
0xa0eac  newarr   [mscorlib]System.Char
0xa0eb1  dup
0xa0eb2  ldc.i4.0
0xa0eb3  ldc.i4.s 0x3D
0xa0eb5  stelem.i2
0xa0eb6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xa0ebb  stloc.s  0x18
0xa0ebd  ldloc.s  0x18
0xa0ebf  ldlen
0xa0ec0  conv.i4
0xa0ec1  ldc.i4.2
0xa0ec2  bne.un.s loc_A0EEE
0xa0ec4  ldloc.s  0x18
0xa0ec6  ldc.i4.1
0xa0ec7  ldelem.ref
0xa0ec8  stloc.s  0xE
0xa0eca  ldloc.s  0xE
0xa0ecc  ldstr    asc_A98C0// "."
0xa0ed1  ldc.i4.4
0xa0ed2  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xa0ed7  brfalse.s loc_A0EFC
0xa0ed9  ldloc.s  0xE
0xa0edb  ldc.i4.0
0xa0edc  ldloc.s  0xE
0xa0ede  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa0ee3  ldc.i4.1
0xa0ee4  sub
0xa0ee5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xa0eea  stloc.s  0xE
0xa0eec  br.s     loc_A0EFC
0xa0eee  ldloc.s  0x17
0xa0ef0  ldc.i4.1
0xa0ef1  add
0xa0ef2  stloc.s  0x17
0xa0ef4  ldloc.s  0x17
0xa0ef6  ldloc.s  0x16
0xa0ef8  ldlen
0xa0ef9  conv.i4
0xa0efa  blt.s    loc_A0E95
0xa0efc  ldarg.0
0xa0efd  ldfld    string ObjectPicker::targetComputer
0xa0f02  call     bool Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::IsDomainController(string computerName)
0xa0f07  stloc.s  0xF
0xa0f09  ldc.i4.0
0xa0f0a  stloc.s  0x10
0xa0f0c  ldloc.s  0xF
0xa0f0e  brfalse.s loc_A0F65
0xa0f10  ldloc.s  8
0xa0f12  ldfld    string DS_SELECTION::pwzADsPath
0xa0f17  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0f1c  brtrue.s loc_A0F65
0xa0f1e  ldloc.s  8
0xa0f20  ldfld    string DS_SELECTION::pwzADsPath
0xa0f25  ldc.i4.1
0xa0f26  newarr   [mscorlib]System.Char
0xa0f2b  dup
0xa0f2c  ldc.i4.0
0xa0f2d  ldc.i4.s 0x2C
0xa0f2f  stelem.i2
0xa0f30  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xa0f35  stloc.s  0x19
0xa0f37  ldloc.s  0x19
0xa0f39  ldlen
0xa0f3a  brfalse.s loc_A0F65
0xa0f3c  ldc.i4.0
0xa0f3d  stloc.s  0x1A
0xa0f3f  br.s     loc_A0F5D
0xa0f41  ldloc.s  0x19
0xa0f43  ldloc.s  0x1A
0xa0f45  ldelem.ref
0xa0f46  ldstr    aCnBuiltin// "CN=Builtin"
0xa0f4b  callvirt instance bool [mscorlib]System.String::Equals(string)
0xa0f50  brfalse.s loc_A0F57
0xa0f52  ldc.i4.1
0xa0f53  stloc.s  0x10
0xa0f55  br.s     loc_A0F65
0xa0f57  ldloc.s  0x1A
0xa0f59  ldc.i4.1
0xa0f5a  add
0xa0f5b  stloc.s  0x1A
0xa0f5d  ldloc.s  0x1A
0xa0f5f  ldloc.s  0x19
0xa0f61  ldlen
0xa0f62  conv.i4
0xa0f63  blt.s    loc_A0F41
0xa0f65  ldloc.s  0xE
0xa0f67  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0f6c  brfalse.s loc_A0FAB
0xa0f6e  ldarg.0
0xa0f6f  ldfld    string ObjectPicker::targetComputer
0xa0f74  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa0f79  brtrue.s loc_A0F8E
0xa0f7b  ldarg.0
0xa0f7c  ldfld    string ObjectPicker::targetComputer
0xa0f81  ldstr    asc_A98C0// "."
0xa0f86  ldc.i4.5
0xa0f87  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xa0f8c  brtrue.s loc_A0F97
0xa0f8e  call     string [mscorlib]System.Environment::get_MachineName()
0xa0f93  stloc.s  0xE
0xa0f95  br.s     loc_A0F9F
0xa0f97  ldarg.0
0xa0f98  ldfld    string ObjectPicker::targetComputer
0xa0f9d  stloc.s  0xE
0xa0f9f  ldloc.s  8
0xa0fa1  ldfld    string DS_SELECTION::pwzName
0xa0fa6  stloc.s  0xB
0xa0fa8  ldc.i4.1
0xa0fa9  stloc.s  0xC
0xa0fab  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
  ... truncated ...
```
