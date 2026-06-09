# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenLifetime

- ea: `0x16fb0`
- end: `0x1706a`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenLifetime`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x181f0`

## callees

- `0x169c0`
- `0x16fb0`
- `0x2c520`

## string_xrefs

- `0x16fbf`: `token`
- `0x16fe9`: `No valid ClockSkew configured.`
- `0x17008`: `Invalid JWT token. The token is expired.`
- `0x17030`: `Invalid JWT token. The token is not yet valid. Current time is `
- `0x17041`: ` and the token is Valid from `

## pseudocode

```c

```

## disassembly

```asm
0x16fb0  ldc.i4   0x231578F
0x16fb5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x16fba  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16fbf  ldstr    aToken// "token"
0x16fc4  ldarg.1
0x16fc5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x16fca  ldarg.0
0x16fcb  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x16fd0  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_MaxClockSkew()
0x16fd5  stloc.0
0x16fd6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x16fdb  stloc.1
0x16fdc  ldloc.0
0x16fdd  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x16fe2  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x16fe7  brfalse.s loc_16FF4
0x16fe9  ldstr    aNoValidClocksk// "No valid ClockSkew configured."
0x16fee  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x16ff3  throw
0x16ff4  ldarg.1
0x16ff5  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x16ffa  ldloc.1
0x16ffb  ldloc.0
0x16ffc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x17001  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x17006  brfalse.s loc_17013
0x17008  ldstr    aInvalidJwtToke// "Invalid JWT token. The token is expired"...
0x1700d  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenExpiredException::.ctor(string)
0x17012  throw
0x17013  ldarg.1
0x17014  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x17019  ldloc.1
0x1701a  ldloc.0
0x1701b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x17020  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x17025  brfalse.s loc_17069
0x17027  ldc.i4.5
0x17028  newarr   [mscorlib]System.Object
0x1702d  stloc.2
0x1702e  ldloc.2
0x1702f  ldc.i4.0
0x17030  ldstr    aInvalidJwtToke_0// "Invalid JWT token. The token is not yet"...
0x17035  stelem.ref
0x17036  ldloc.2
0x17037  ldc.i4.1
0x17038  ldloc.1
0x17039  box      [mscorlib]System.DateTime
0x1703e  stelem.ref
0x1703f  ldloc.2
0x17040  ldc.i4.2
0x17041  ldstr    aAndTheTokenIsV// " and the token is Valid from "
0x17046  stelem.ref
0x17047  ldloc.2
0x17048  ldc.i4.3
0x17049  ldarg.1
0x1704a  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x1704f  box      [mscorlib]System.DateTime
0x17054  stelem.ref
0x17055  ldloc.2
0x17056  ldc.i4.4
0x17057  ldstr    asc_530AA// "."
0x1705c  stelem.ref
0x1705d  ldloc.2
0x1705e  call     string [mscorlib]System.String::Concat(object[])
0x17063  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenExpiredException::.ctor(string)
0x17068  throw
0x17069  ret
```
