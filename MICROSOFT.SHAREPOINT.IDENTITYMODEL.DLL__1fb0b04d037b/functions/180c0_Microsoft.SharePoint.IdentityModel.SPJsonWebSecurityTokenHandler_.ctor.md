# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::.ctor

- ea: `0x180c0`
- end: `0x18177`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::.ctor`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x7190`

## callees

- `0x15ac0`
- `0x16940`
- `0x180c0`
- `0x18180`

## string_xrefs

- `0x180f4`: `Setup an SPJsonAudienceValidator. Mode: '{0}'.`
- `0x18129`: `Setup an SPJsonAudienceValidator. Mode: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x180c0  ldarg.0
0x180c1  ldarg.1
0x180c2  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode mode)
0x180c7  ldarg.1
0x180c8  stloc.0
0x180c9  ldloc.0
0x180ca  ldc.i4.1
0x180cb  sub
0x180cc  switch   loc_180DB, loc_18110
0x180d9  br.s     loc_18145
0x180db  ldarg.0
0x180dc  ldc.i4.s 0x1A
0x180de  newobj   instance void Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x180e3  stfld    class Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::m_AudienceValidator
0x180e8  ldc.i4   0x809359
0x180ed  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x180f2  ldc.i4.s 0x32
0x180f4  ldstr    aSetupAnSpjsona// "Setup an SPJsonAudienceValidator. Mode:"...
0x180f9  ldc.i4.1
0x180fa  newarr   [mscorlib]System.Object
0x180ff  stloc.1
0x18100  ldloc.1
0x18101  ldc.i4.0
0x18102  ldarg.1
0x18103  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x18108  stelem.ref
0x18109  ldloc.1
0x1810a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1810f  ret
0x18110  ldarg.0
0x18111  ldc.i4.s 0x10
0x18113  newobj   instance void Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x18118  stfld    class Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::m_AudienceValidator
0x1811d  ldc.i4   0x80935A
0x18122  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18127  ldc.i4.s 0x32
0x18129  ldstr    aSetupAnSpjsona// "Setup an SPJsonAudienceValidator. Mode:"...
0x1812e  ldc.i4.1
0x1812f  newarr   [mscorlib]System.Object
0x18134  stloc.2
0x18135  ldloc.2
0x18136  ldc.i4.0
0x18137  ldarg.1
0x18138  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x1813d  stelem.ref
0x1813e  ldloc.2
0x1813f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x18144  ret
0x18145  ldc.i4   0x80935B
0x1814a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1814f  ldc.i4.s 0xA
0x18151  ldstr    aTheModeIsUnkno// "The mode is unknown. Mode: '{0}'."
0x18156  ldc.i4.1
0x18157  newarr   [mscorlib]System.Object
0x1815c  stloc.3
0x1815d  ldloc.3
0x1815e  ldc.i4.0
0x1815f  ldarg.1
0x18160  box      Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandlerMode
0x18165  stelem.ref
0x18166  ldloc.3
0x18167  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1816c  ldstr    aMode// "mode"
0x18171  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x18176  throw
```
