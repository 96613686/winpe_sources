# System.Web.Configuration.IdentitySection::ValidateCredentials

- ea: `0x14ae60`
- end: `0x14b05d`
- name: `System.Web.Configuration.IdentitySection::ValidateCredentials`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14ac20`

## callees

- `0x34f20`
- `0x34fa0`
- `0x143ea0`
- `0x14acc0`
- `0x14ad10`
- `0x14ad40`
- `0x14ae60`
- `0x14b150`

## string_xrefs

- `0x14ae86`: `Invalid_registry_config`
- `0x14aeba`: `Invalid_registry_config`

## pseudocode

```c

```

## disassembly

```asm
0x14ae60  ldarg.0
0x14ae61  ldarg.0
0x14ae62  call     instance string System.Web.Configuration.IdentitySection::get_UserName()
0x14ae67  stfld    string System.Web.Configuration.IdentitySection::_username
0x14ae6c  ldarg.0
0x14ae6d  ldarg.0
0x14ae6e  call     instance string System.Web.Configuration.IdentitySection::get_Password()
0x14ae73  stfld    string System.Web.Configuration.IdentitySection::_password
0x14ae78  ldarg.0
0x14ae79  ldflda   string System.Web.Configuration.IdentitySection::_username
0x14ae7e  ldc.i4.0
0x14ae7f  call     bool System.Web.Configuration.HandlerBase::CheckAndReadRegistryValue(string& value, bool throwIfError)
0x14ae84  brtrue.s loc_14AEAC
0x14ae86  ldstr    aInvalidRegistr// "Invalid_registry_config"
0x14ae8b  call     string System.Web.SR::GetString(string name)
0x14ae90  ldarg.0
0x14ae91  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14ae96  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x14ae9b  ldarg.0
0x14ae9c  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14aea1  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x14aea6  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x14aeab  throw
0x14aeac  ldarg.0
0x14aead  ldflda   string System.Web.Configuration.IdentitySection::_password
0x14aeb2  ldc.i4.0
0x14aeb3  call     bool System.Web.Configuration.HandlerBase::CheckAndReadRegistryValue(string& value, bool throwIfError)
0x14aeb8  brtrue.s loc_14AEE0
0x14aeba  ldstr    aInvalidRegistr// "Invalid_registry_config"
0x14aebf  call     string System.Web.SR::GetString(string name)
0x14aec4  ldarg.0
0x14aec5  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14aeca  callvirt instance string [System.Configuration]System.Configuration.ElementInformation::get_Source()
0x14aecf  ldarg.0
0x14aed0  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14aed5  callvirt instance int32 [System.Configuration]System.Configuration.ElementInformation::get_LineNumber()
0x14aeda  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x14aedf  throw
0x14aee0  ldarg.0
0x14aee1  ldfld    string System.Web.Configuration.IdentitySection::_username
0x14aee6  brfalse.s loc_14AEFD
0x14aee8  ldarg.0
0x14aee9  ldfld    string System.Web.Configuration.IdentitySection::_username
0x14aeee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14aef3  ldc.i4.1
0x14aef4  bge.s    loc_14AEFD
0x14aef6  ldarg.0
0x14aef7  ldnull
0x14aef8  stfld    string System.Web.Configuration.IdentitySection::_username
0x14aefd  ldarg.0
0x14aefe  ldfld    string System.Web.Configuration.IdentitySection::_username
0x14af03  brfalse.s loc_14AF22
0x14af05  ldarg.0
0x14af06  call     instance bool System.Web.Configuration.IdentitySection::get_Impersonate()
0x14af0b  brfalse.s loc_14AF22
0x14af0d  ldarg.0
0x14af0e  ldfld    string System.Web.Configuration.IdentitySection::_password
0x14af13  brtrue.s loc_14AF8C
0x14af15  ldarg.0
0x14af16  ldsfld   string [mscorlib]System.String::Empty
0x14af1b  stfld    string System.Web.Configuration.IdentitySection::_password
0x14af20  br.s     loc_14AF8C
0x14af22  ldarg.0
0x14af23  ldfld    string System.Web.Configuration.IdentitySection::_password
0x14af28  brfalse.s loc_14AF8C
0x14af2a  ldarg.0
0x14af2b  ldfld    string System.Web.Configuration.IdentitySection::_username
0x14af30  brtrue.s loc_14AF8C
0x14af32  ldarg.0
0x14af33  ldfld    string System.Web.Configuration.IdentitySection::_password
0x14af38  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14af3d  ldc.i4.0
0x14af3e  ble.s    loc_14AF8C
0x14af40  ldarg.0
0x14af41  call     instance bool System.Web.Configuration.IdentitySection::get_Impersonate()
0x14af46  brfalse.s loc_14AF8C
0x14af48  ldstr    aInvalidCredent// "Invalid_credentials"
0x14af4d  call     string System.Web.SR::GetString(string name)
0x14af52  ldarg.0
0x14af53  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14af58  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14af5d  ldstr    aPassword// "password"
0x14af62  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14af67  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x14af6c  ldarg.0
0x14af6d  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14af72  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14af77  ldstr    aPassword// "password"
0x14af7c  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14af81  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x14af86  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x14af8b  throw
0x14af8c  ldarg.0
0x14af8d  call     instance bool System.Web.Configuration.IdentitySection::get_Impersonate()
0x14af92  brfalse  loc_14B05C
0x14af97  ldarg.0
0x14af98  call     instance native int System.Web.Configuration.IdentitySection::get_ImpersonateToken()
0x14af9d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x14afa2  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x14afa7  brfalse  loc_14B05C
0x14afac  ldarg.0
0x14afad  ldfld    string System.Web.Configuration.IdentitySection::_username
0x14afb2  brfalse  loc_14B05C
0x14afb7  ldarg.0
0x14afb8  ldfld    string System.Web.Configuration.IdentitySection::error
0x14afbd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14afc2  ldc.i4.0
0x14afc3  ble.s    loc_14B018
0x14afc5  ldstr    aInvalidCredent_0// "Invalid_credentials_2"
0x14afca  ldc.i4.1
0x14afcb  newarr   [mscorlib]System.Object
0x14afd0  dup
0x14afd1  ldc.i4.0
0x14afd2  ldarg.0
0x14afd3  ldfld    string System.Web.Configuration.IdentitySection::error
0x14afd8  stelem.ref
0x14afd9  call     string System.Web.SR::GetString(string name, object[] args)
0x14afde  ldarg.0
0x14afdf  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14afe4  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14afe9  ldstr    aUsername_3// "userName"
0x14afee  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14aff3  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x14aff8  ldarg.0
0x14aff9  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14affe  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14b003  ldstr    aUsername_3// "userName"
0x14b008  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14b00d  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x14b012  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x14b017  throw
0x14b018  ldstr    aInvalidCredent// "Invalid_credentials"
0x14b01d  call     string System.Web.SR::GetString(string name)
0x14b022  ldarg.0
0x14b023  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14b028  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14b02d  ldstr    aUsername_3// "userName"
0x14b032  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14b037  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x14b03c  ldarg.0
0x14b03d  call     instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x14b042  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x14b047  ldstr    aUsername_3// "userName"
0x14b04c  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x14b051  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x14b056  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x14b05b  throw
0x14b05c  ret
```
