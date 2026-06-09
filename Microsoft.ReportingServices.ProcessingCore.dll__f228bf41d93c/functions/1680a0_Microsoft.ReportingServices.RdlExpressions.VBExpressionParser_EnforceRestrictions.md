# Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::EnforceRestrictions

- ea: `0x1680a0`
- end: `0x1690f3`
- name: `Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::EnforceRestrictions`
- size: `4179`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x167a80`

## callees

- `0xba260`
- `0x117ae0`
- `0x117b00`
- `0x1680a0`
- `0x1697d0`
- `0x1697e0`
- `0x169820`
- `0x1767c0`
- `0x232bf0`
- `0x232c10`
- `0x232c30`
- `0x232c50`
- `0x232c60`
- `0x232c70`
- `0x232c80`
- `0x232c90`
- `0x232ce0`
- `0x23c620`
- `0x23c640`
- `0x23c660`
- `0x23c680`

## string_xrefs

- `0x168228`: `CreateDrillthroughContext`

## pseudocode

```c

```

## disassembly

```asm
0x1680a0  ldarg.3
0x1680a1  ldc.i4   0x8000
0x1680a6  and
0x1680a7  brfalse.s loc_1680F6
0x1680a9  ldarg.0
0x1680aa  ldarg.1
0x1680ab  ldind.ref
0x1680ac  ldarg.0
0x1680ad  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x1680b2  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::RenderFormatAnyDetection
0x1680b7  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x1680bc  brfalse.s loc_1680F6
0x1680be  ldarg.0
0x1680bf  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x1680c4  ldc.i4   0x1DA
0x1680c9  ldc.i4.0
0x1680ca  ldarg.0
0x1680cb  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1680d0  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x1680d5  ldarg.0
0x1680d6  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1680db  call     instance string ExpressionContext::get_ObjectName()
0x1680e0  ldarg.0
0x1680e1  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1680e6  call     instance string ExpressionContext::get_PropertyName()
0x1680eb  call     T0x2B000001
0x1680f0  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1680f5  pop
0x1680f6  ldarg.0
0x1680f7  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1680fc  call     instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning ExpressionContext::get_PublishingVersioning()
0x168101  ldc.i4.s 0xE
0x168103  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0x168108  brfalse.s loc_168160
0x16810a  ldarg.0
0x16810b  ldarg.1
0x16810c  ldind.ref
0x16810d  ldarg.0
0x16810e  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x168113  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::InScope
0x168118  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x16811d  brfalse.s loc_168160
0x16811f  ldarg.0
0x168120  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x168125  ldc.i4   0x206
0x16812a  ldc.i4.0
0x16812b  ldarg.0
0x16812c  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168131  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x168136  ldarg.0
0x168137  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16813c  call     instance string ExpressionContext::get_ObjectName()
0x168141  ldarg.0
0x168142  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168147  call     instance string ExpressionContext::get_PropertyName()
0x16814c  ldc.i4.1
0x16814d  newarr   [mscorlib]System.String
0x168152  dup
0x168153  ldc.i4.0
0x168154  ldstr    aInscope// "InScope"
0x168159  stelem.ref
0x16815a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x16815f  pop
0x168160  ldarg.0
0x168161  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168166  call     instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning ExpressionContext::get_PublishingVersioning()
0x16816b  ldc.i4.s 0xF
0x16816d  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0x168172  brfalse.s loc_1681CA
0x168174  ldarg.0
0x168175  ldarg.1
0x168176  ldind.ref
0x168177  ldarg.0
0x168178  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x16817d  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::Level
0x168182  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x168187  brfalse.s loc_1681CA
0x168189  ldarg.0
0x16818a  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x16818f  ldc.i4   0x206
0x168194  ldc.i4.0
0x168195  ldarg.0
0x168196  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16819b  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x1681a0  ldarg.0
0x1681a1  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1681a6  call     instance string ExpressionContext::get_ObjectName()
0x1681ab  ldarg.0
0x1681ac  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1681b1  call     instance string ExpressionContext::get_PropertyName()
0x1681b6  ldc.i4.1
0x1681b7  newarr   [mscorlib]System.String
0x1681bc  dup
0x1681bd  ldc.i4.0
0x1681be  ldstr    aLevel// "Level"
0x1681c3  stelem.ref
0x1681c4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1681c9  pop
0x1681ca  ldarg.0
0x1681cb  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1681d0  call     instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning ExpressionContext::get_PublishingVersioning()
0x1681d5  ldc.i4.s 0x10
0x1681d7  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0x1681dc  brfalse.s loc_168234
0x1681de  ldarg.0
0x1681df  ldarg.1
0x1681e0  ldind.ref
0x1681e1  ldarg.0
0x1681e2  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x1681e7  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::CreateDrillthroughContext
0x1681ec  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x1681f1  brfalse.s loc_168234
0x1681f3  ldarg.0
0x1681f4  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x1681f9  ldc.i4   0x206
0x1681fe  ldc.i4.0
0x1681ff  ldarg.0
0x168200  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168205  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x16820a  ldarg.0
0x16820b  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168210  call     instance string ExpressionContext::get_ObjectName()
0x168215  ldarg.0
0x168216  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16821b  call     instance string ExpressionContext::get_PropertyName()
0x168220  ldc.i4.1
0x168221  newarr   [mscorlib]System.String
0x168226  dup
0x168227  ldc.i4.0
0x168228  ldstr    aCreatedrillthr// "CreateDrillthroughContext"
0x16822d  stelem.ref
0x16822e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x168233  pop
0x168234  ldarg.0
0x168235  ldarg.1
0x168236  ldind.ref
0x168237  ldarg.0
0x168238  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x16823d  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ScopesDetection
0x168242  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x168247  stloc.0
0x168248  ldloc.0
0x168249  brfalse.s loc_1682A0
0x16824b  ldarg.0
0x16824c  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168251  call     instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning ExpressionContext::get_PublishingVersioning()
0x168256  ldc.i4.s 0x1E
0x168258  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0x16825d  brfalse.s loc_1682A0
0x16825f  ldarg.0
0x168260  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x168265  ldc.i4   0x206
0x16826a  ldc.i4.0
0x16826b  ldarg.0
0x16826c  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168271  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x168276  ldarg.0
0x168277  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16827c  call     instance string ExpressionContext::get_ObjectName()
0x168281  ldarg.0
0x168282  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168287  call     instance string ExpressionContext::get_PropertyName()
0x16828c  ldc.i4.1
0x16828d  newarr   [mscorlib]System.String
0x168292  dup
0x168293  ldc.i4.0
0x168294  ldstr    aScopes// "Scopes"
0x168299  stelem.ref
0x16829a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x16829f  pop
0x1682a0  ldloc.0
0x1682a1  brfalse.s loc_1682E4
0x1682a3  ldarg.3
0x1682a4  ldc.i4   0x10000
0x1682a9  and
0x1682aa  brfalse.s loc_1682E4
0x1682ac  ldarg.0
0x1682ad  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x1682b2  ldc.i4   0x24E
0x1682b7  ldc.i4.0
0x1682b8  ldarg.0
0x1682b9  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1682be  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x1682c3  ldarg.0
0x1682c4  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1682c9  call     instance string ExpressionContext::get_ObjectName()
0x1682ce  ldarg.0
0x1682cf  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1682d4  call     instance string ExpressionContext::get_PropertyName()
0x1682d9  call     T0x2B000001
0x1682de  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1682e3  pop
0x1682e4  ldarg.3
0x1682e5  ldc.i4.8
0x1682e6  and
0x1682e7  brfalse  loc_16843C
0x1682ec  ldarg.0
0x1682ed  ldarg.1
0x1682ee  ldind.ref
0x1682ef  ldarg.0
0x1682f0  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x1682f5  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::FieldDetection
0x1682fa  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::Detected(string expression, class [System]System.Text.RegularExpressions.Regex detectionRegex)
0x1682ff  brfalse  loc_16843C
0x168304  ldarg.0
0x168305  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16830a  call     instance valuetype Microsoft.ReportingServices.ReportPublishing.LocationFlags ExpressionContext::get_Location()
0x16830f  ldc.i4.s 0x40
0x168311  and
0x168312  brfalse.s loc_16834E
0x168314  ldarg.0
0x168315  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x16831a  ldc.i4.s 0x4F
0x16831c  ldc.i4.0
0x16831d  ldarg.0
0x16831e  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168323  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x168328  ldarg.0
0x168329  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16832e  call     instance string ExpressionContext::get_ObjectName()
0x168333  ldarg.0
0x168334  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168339  call     instance string ExpressionContext::get_PropertyName()
0x16833e  call     T0x2B000001
0x168343  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x168348  pop
0x168349  br       loc_16843C
0x16834e  ldc.i4.3
0x16834f  ldarg.0
0x168350  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168355  call     instance valuetype ExpressionType ExpressionContext::get_ExpressionType()
0x16835a  bne.un.s loc_1683A5
0x16835c  ldarg.0
0x16835d  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x168362  ldc.i4.s 0x50
0x168364  ldc.i4.0
0x168365  ldarg.0
0x168366  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16836b  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x168370  ldarg.0
0x168371  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168376  call     instance string ExpressionContext::get_ObjectName()
0x16837b  ldarg.0
0x16837c  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168381  call     instance string ExpressionContext::get_PropertyName()
0x168386  ldc.i4.1
0x168387  newarr   [mscorlib]System.String
0x16838c  dup
0x16838d  ldc.i4.0
0x16838e  ldarg.0
0x16838f  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168394  call     instance string ExpressionContext::get_DataSetName()
0x168399  stelem.ref
0x16839a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x16839f  pop
0x1683a0  br       loc_16843C
0x1683a5  ldc.i4.2
0x1683a6  ldarg.0
0x1683a7  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1683ac  call     instance valuetype ExpressionType ExpressionContext::get_ExpressionType()
0x1683b1  bne.un.s loc_1683EA
0x1683b3  ldarg.0
0x1683b4  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x1683b9  ldc.i4.s 0x52
0x1683bb  ldc.i4.0
0x1683bc  ldarg.0
0x1683bd  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1683c2  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x1683c7  ldarg.0
0x1683c8  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1683cd  call     instance string ExpressionContext::get_ObjectName()
0x1683d2  ldarg.0
0x1683d3  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1683d8  call     instance string ExpressionContext::get_PropertyName()
0x1683dd  call     T0x2B000001
0x1683e2  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1683e7  pop
0x1683e8  br.s     loc_16843C
0x1683ea  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1683ef  ldc.i4.1
0x1683f0  ldarg.0
0x1683f1  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x1683f6  call     instance valuetype ExpressionType ExpressionContext::get_ExpressionType()
0x1683fb  ceq
0x1683fd  ldstr    aExpressiontype// "(ExpressionType.ReportParameter == m_co"...
0x168402  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x168407  ldarg.0
0x168408  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x16840d  ldc.i4.s 0x51
0x16840f  ldc.i4.0
0x168410  ldarg.0
0x168411  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168416  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x16841b  ldarg.0
0x16841c  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x168421  call     instance string ExpressionContext::get_ObjectName()
0x168426  ldarg.0
0x168427  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16842c  call     instance string ExpressionContext::get_PropertyName()
0x168431  call     T0x2B000001
  ... truncated ...
```
