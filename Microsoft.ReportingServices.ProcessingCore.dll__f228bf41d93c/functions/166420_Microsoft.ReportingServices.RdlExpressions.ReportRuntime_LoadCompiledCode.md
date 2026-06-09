# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::LoadCompiledCode

- ea: `0x166420`
- end: `0x1665ca`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::LoadCompiledCode`
- size: `426`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fa830`
- `0x1fa9f0`
- `0x1fabb0`
- `0x201ca0`

## callees

- `0x11b320`
- `0x11b330`
- `0x11b340`
- `0x11b360`
- `0x11b380`
- `0x166420`
- `0x166630`
- `0x175d50`
- `0x175e20`
- `0x176790`
- `0x1767c0`
- `0x183aa0`
- `0x183ab0`
- `0x183ac0`
- `0x183af0`
- `0x232dd0`
- `0x232e20`

## string_xrefs

- `0x16645d`: `ProcessingCore, HasCompiledCode: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x166420  ldarg.1
0x166421  brtrue.s loc_166426
0x166423  ldc.i4.0
0x166424  br.s     loc_166457
0x166426  ldarg.1
0x166427  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CompiledCode()
0x16642c  dup
0x16642d  brtrue.s loc_16643B
0x16642f  pop
0x166430  ldloca.s 3
0x166432  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x166438  ldloc.3
0x166439  br.s     loc_166442
0x16643b  ldlen
0x16643c  conv.i4
0x16643d  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x166442  stloc.1
0x166443  ldc.i4.0
0x166444  stloc.2
0x166445  ldloca.s 1
0x166447  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x16644c  ldloc.2
0x16644d  cgt
0x16644f  ldloca.s 1
0x166451  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x166456  and
0x166457  stloc.0
0x166458  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x16645d  ldstr    aProcessingcore// "ProcessingCore, HasCompiledCode: {0}"
0x166462  ldloc.0
0x166463  box      [mscorlib]System.Boolean
0x166468  call     string [mscorlib]System.String::Format(string, object)
0x16646d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x166472  ldloc.0
0x166473  brfalse  loc_1665C9
0x166478  ldarg.0
0x166479  ldfld    bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_useSafeExpressions
0x16647e  brtrue   loc_1665C9
0x166483  ldarg.s  5
0x166485  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::get_RequireExpressionHostWithRefusedPermissions()
0x16648a  brfalse.s loc_1664BA
0x16648c  ldarg.1
0x16648d  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CompiledCodeGeneratedWithRefusedPermissions()
0x166492  brtrue.s loc_1664BA
0x166494  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x166499  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x16649e  brfalse.s loc_1664AF
0x1664a0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1664a5  ldstr    aExpressionHost_1// "Expression host generated with refused "...
0x1664aa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x1664af  ldc.i4   0xFC
0x1664b4  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x1664b9  throw
0x1664ba  ldarg.s  5
0x1664bc  callvirt instance class [mscorlib]System.AppDomain Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::get_ExprHostAppDomain()
0x1664c1  brfalse.s loc_1664D4
0x1664c3  ldarg.s  5
0x1664c5  callvirt instance class [mscorlib]System.AppDomain Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::get_ExprHostAppDomain()
0x1664ca  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1664cf  bne.un   loc_16657E
0x1664d4  ldarg.0
0x1664d5  ldc.i4.0
0x1664d6  stfld    bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_exprHostInSandboxAppDomain
0x1664db  ldarg.1
0x1664dc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x1664e1  brfalse.s loc_166554
0x1664e3  ldc.i4.0
0x1664e4  stloc.s  4
0x1664e6  br.s     loc_166545
0x1664e8  ldarg.s  5
0x1664ea  ldarg.1
0x1664eb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x1664f0  ldloc.s  4
0x1664f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1664f7  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::CheckCodeModuleIsTrustedInCurrentAppDomain(string assemblyName)
0x1664fc  brtrue.s loc_16653F
0x1664fe  ldarg.0
0x1664ff  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_errorContext
0x166504  ldc.i4   0x16F
0x166509  ldc.i4.0
0x16650a  ldarg.1
0x16650b  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_ObjectType()
0x166510  ldnull
0x166511  ldnull
0x166512  ldc.i4.1
0x166513  newarr   [mscorlib]System.String
0x166518  dup
0x166519  ldc.i4.0
0x16651a  ldarg.1
0x16651b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x166520  ldloc.s  4
0x166522  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x166527  stelem.ref
0x166528  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x16652d  pop
0x16652e  ldarg.0
0x16652f  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_errorContext
0x166534  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList Microsoft.ReportingServices.ReportProcessing.ErrorContext::get_Messages()
0x166539  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(class Microsoft.ReportingServices.ReportProcessing.ProcessingMessageList processingMessages)
0x16653e  throw
0x16653f  ldloc.s  4
0x166541  ldc.i4.1
0x166542  add
0x166543  stloc.s  4
0x166545  ldloc.s  4
0x166547  ldarg.1
0x166548  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x16654d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x166552  blt.s    loc_1664E8
0x166554  ldarg.0
0x166555  ldarg.1
0x166556  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CompiledCode()
0x16655b  ldarg.1
0x16655c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_ExprHostAssemblyName()
0x166561  ldarg.s  5
0x166563  callvirt instance class [mscorlib]System.Security.Policy.Evidence Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::get_ExprHostEvidence()
0x166568  ldarg.2
0x166569  ldarg.3
0x16656a  ldarg.s  4
0x16656c  ldarg.1
0x16656d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x166572  call     class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost ExpressionHostLoader::LoadExprHostIntoCurrentAppDomain(unsigned int8[] exprHostBytes, string exprHostAssemblyName, class [mscorlib]System.Security.Policy.Evidence evidence, bool includeParameters, bool parametersOnly, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel objectModel, class [mscorlib]System.Collections.Generic.List`1<string> codeModules)
0x166577  stfld    class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_reportExprHost
0x16657c  br.s     loc_1665AD
0x16657e  ldarg.0
0x16657f  ldc.i4.1
0x166580  stfld    bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_exprHostInSandboxAppDomain
0x166585  ldarg.0
0x166586  ldarg.1
0x166587  callvirt instance unsigned int8[] Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CompiledCode()
0x16658c  ldarg.1
0x16658d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_ExprHostAssemblyName()
0x166592  ldarg.2
0x166593  ldarg.3
0x166594  ldarg.s  4
0x166596  ldarg.1
0x166597  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_CodeModules()
0x16659c  ldarg.s  5
0x16659e  callvirt instance class [mscorlib]System.AppDomain Microsoft.ReportingServices.ReportProcessing.ReportRuntimeSetup::get_ExprHostAppDomain()
0x1665a3  call     class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost ExpressionHostLoader::LoadExprHost(unsigned int8[] exprHostBytes, string exprHostAssemblyName, bool includeParameters, bool parametersOnly, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel objectModel, class [mscorlib]System.Collections.Generic.List`1<string> codeModules, class [mscorlib]System.AppDomain targetAppDomain)
0x1665a8  stfld    class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost Microsoft.ReportingServices.RdlExpressions.ReportRuntime::m_reportExprHost
0x1665ad  leave.s  loc_1665C9
0x1665af  pop
0x1665b0  rethrow
0x1665b2  stloc.s  5
0x1665b4  ldarg.0
0x1665b5  ldarg.1
0x1665b6  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.IExpressionHostAssemblyHolder::get_ObjectType()
0x1665bb  ldloc.s  5
0x1665bd  ldc.i4   0x16D
0x1665c2  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessLoadingExprHostException(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType assemblyHolderObjectType, class [mscorlib]System.Exception e, valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode errorCode)
0x1665c7  leave.s  loc_1665C9
0x1665c9  ret
```
