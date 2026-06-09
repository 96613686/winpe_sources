# System.Web.Configuration.WebConfigurationHost::VerifyDefinitionAllowed

- ea: `0x15bbd0`
- end: `0x15bc53`
- name: `System.Web.Configuration.WebConfigurationHost::VerifyDefinitionAllowed`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x34fa0`
- `0x53a80`
- `0x15bbd0`

## string_xrefs

- `0x15bbed`: `Config_allow_definition_error_machine`
- `0x15bc0b`: `Config_allow_definition_error_webroot`
- `0x15bc29`: `Config_allow_definition_error_application`
- `0x15bc47`: `WebConfigurationHost::VerifyDefinitionAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x15bbd0  ldarg.0
0x15bbd1  ldarg.1
0x15bbd2  ldarg.2
0x15bbd3  ldarg.3
0x15bbd4  callvirt instance bool [System.Configuration]System.Configuration.Internal.DelegatingConfigHost::IsDefinitionAllowed(string, valuetype [System.Configuration]System.Configuration.ConfigurationAllowDefinition, valuetype [System.Configuration]System.Configuration.ConfigurationAllowExeDefinition)
0x15bbd9  brtrue.s loc_15BC52
0x15bbdb  ldarg.2
0x15bbdc  brfalse.s loc_15BBED
0x15bbde  ldarg.2
0x15bbdf  ldc.i4.s 0x64
0x15bbe1  beq.s    loc_15BC0B
0x15bbe3  ldarg.2
0x15bbe4  ldc.i4   0xC8
0x15bbe9  beq.s    loc_15BC29
0x15bbeb  br.s     loc_15BC47
0x15bbed  ldstr    aConfigAllowDef// "Config_allow_definition_error_machine"
0x15bbf2  call     string System.Web.SR::GetString(string name)
0x15bbf7  ldarg.s  4
0x15bbf9  callvirt instance string [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_Filename()
0x15bbfe  ldarg.s  4
0x15bc00  callvirt instance int32 [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_LineNumber()
0x15bc05  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x15bc0a  throw
0x15bc0b  ldstr    aConfigAllowDef_0// "Config_allow_definition_error_webroot"
0x15bc10  call     string System.Web.SR::GetString(string name)
0x15bc15  ldarg.s  4
0x15bc17  callvirt instance string [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_Filename()
0x15bc1c  ldarg.s  4
0x15bc1e  callvirt instance int32 [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_LineNumber()
0x15bc23  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x15bc28  throw
0x15bc29  ldstr    aConfigAllowDef_1// "Config_allow_definition_error_applicati"...
0x15bc2e  call     string System.Web.SR::GetString(string name)
0x15bc33  ldarg.s  4
0x15bc35  callvirt instance string [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_Filename()
0x15bc3a  ldarg.s  4
0x15bc3c  callvirt instance int32 [System.Configuration]System.Configuration.Internal.IConfigErrorInfo::get_LineNumber()
0x15bc41  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x15bc46  throw
0x15bc47  ldstr    aWebconfigurati_0// "WebConfigurationHost::VerifyDefinitionA"...
0x15bc4c  call     class [mscorlib]System.InvalidOperationException System.Web.Util.ExceptionUtil::UnexpectedError(string methodName)
0x15bc51  throw
0x15bc52  ret
```
