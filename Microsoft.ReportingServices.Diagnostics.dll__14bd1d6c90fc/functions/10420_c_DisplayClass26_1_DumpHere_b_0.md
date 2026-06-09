# <>c__DisplayClass26_1::<DumpHere>b__0

- ea: `0x10420`
- end: `0x1087e`
- name: `<>c__DisplayClass26_1::<DumpHere>b__0`
- size: `1118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x9850`
- `0x98d0`
- `0x10420`

## string_xrefs

- `0x10575`: `Skipped creating a dump file for the error {0}, because a dump with the identical stack trace (with signature {1}) was already created.`

## pseudocode

```c

```

## disassembly

```asm
0x10420  ldarg.0
0x10421  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10426  ldfld    bool <>c__DisplayClass26_0::unhandledException
0x1042b  brfalse  loc_10512
0x10430  ldarg.0
0x10431  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10436  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1043b  brfalse  loc_10512
0x10440  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x10445  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1044a  brfalse  loc_10512
0x1044f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x10454  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x10459  brfalse  loc_10512
0x1045e  ldarg.0
0x1045f  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10464  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10469  isinst   [mscorlib]System.AppDomainUnloadedException
0x1046e  brtrue.s loc_10494
0x10470  ldarg.0
0x10471  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10476  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1047b  isinst   [mscorlib]System.OutOfMemoryException
0x10480  brtrue.s loc_10494
0x10482  ldarg.0
0x10483  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10488  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1048d  isinst   [mscorlib]System.Threading.ThreadAbortException
0x10492  brfalse.s loc_104DA
0x10494  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x10499  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1049e  brfalse.s loc_10512
0x104a0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x104a5  ldc.i4.4
0x104a6  ldstr    aUnhandledExcep// "Unhandled exception in Appdomain {0}: "
0x104ab  ldarg.0
0x104ac  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x104b1  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x104b6  callvirt instance string [mscorlib]System.Object::ToString()
0x104bb  call     string [mscorlib]System.String::Concat(string, string)
0x104c0  ldc.i4.1
0x104c1  newarr   [mscorlib]System.Object
0x104c6  dup
0x104c7  ldc.i4.0
0x104c8  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x104cd  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x104d2  stelem.ref
0x104d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x104d8  br.s     loc_10512
0x104da  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x104df  ldc.i4.1
0x104e0  ldstr    aUnhandledExcep// "Unhandled exception in Appdomain {0}: "
0x104e5  ldarg.0
0x104e6  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x104eb  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x104f0  callvirt instance string [mscorlib]System.Object::ToString()
0x104f5  call     string [mscorlib]System.String::Concat(string, string)
0x104fa  ldc.i4.1
0x104fb  newarr   [mscorlib]System.Object
0x10500  dup
0x10501  ldc.i4.0
0x10502  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x10507  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x1050c  stelem.ref
0x1050d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x10512  ldarg.0
0x10513  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10518  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1051d  call     bool Microsoft.ReportingServices.Diagnostics.Dumper::ShouldDump(class [mscorlib]System.Exception optionalException)
0x10522  brtrue.s loc_10525
0x10524  ret
0x10525  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventProvider::get_Current()
0x1052a  ldarg.0
0x1052b  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10530  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10535  ldarg.0
0x10536  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1053b  ldfld    string <>c__DisplayClass26_0::assertionMessage
0x10540  ldarg.0
0x10541  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10546  ldfld    bool <>c__DisplayClass26_0::unhandledException
0x1054b  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider::NotifyReportServerDumpEvent(class [mscorlib]System.Exception, string, bool)
0x10550  ldarg.0
0x10551  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10556  ldfld    class Microsoft.ReportingServices.Diagnostics.Dumper <>c__DisplayClass26_0::<>4__this
0x1055b  ldarg.0
0x1055c  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10561  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10566  ldloca.s 0
0x10568  call     instance bool Microsoft.ReportingServices.Diagnostics.Dumper::ExistsInCache(class [mscorlib]System.Exception optionalException, [out] int32& hash)
0x1056d  brfalse.s loc_105BB
0x1056f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x10574  ldc.i4.3
0x10575  ldstr    aSkippedCreatin// "Skipped creating a dump file for the er"...
0x1057a  ldc.i4.2
0x1057b  newarr   [mscorlib]System.Object
0x10580  dup
0x10581  ldc.i4.0
0x10582  ldarg.0
0x10583  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10588  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1058d  brtrue.s loc_10596
0x1058f  ldsfld   string [mscorlib]System.String::Empty
0x10594  br.s     loc_105AB
0x10596  ldarg.0
0x10597  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1059c  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x105a1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x105a6  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x105ab  stelem.ref
0x105ac  dup
0x105ad  ldc.i4.1
0x105ae  ldloc.0
0x105af  box      [mscorlib]System.UInt32
0x105b4  stelem.ref
0x105b5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x105ba  ret
0x105bb  ldc.i4   0x100
0x105c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x105c5  stloc.1
0x105c6  ldnull
0x105c7  stloc.2
0x105c8  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventProvider::get_Current()
0x105cd  ldarg.0
0x105ce  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x105d3  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x105d8  ldarg.0
0x105d9  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x105de  ldfld    string <>c__DisplayClass26_0::assertionMessage
0x105e3  ldarg.0
0x105e4  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x105e9  ldfld    bool <>c__DisplayClass26_0::unhandledException
0x105ee  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventProvider::NotifyReportServerUniqueDumpEvent(class [mscorlib]System.Exception, string, bool)
0x105f3  ldarg.0
0x105f4  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x105f9  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x105fe  brfalse  loc_1079D
0x10603  ldarg.0
0x10604  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10609  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1060e  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x10613  brfalse.s loc_10628
0x10615  ldarg.0
0x10616  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1061b  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10620  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x10625  stloc.2
0x10626  br.s     loc_10650
0x10628  ldarg.0
0x10629  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1062e  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10633  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x10638  brfalse.s loc_10650
0x1063a  ldarg.0
0x1063b  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10640  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10645  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1064a  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1064f  stloc.2
0x10650  ldarg.0
0x10651  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10656  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x1065b  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x10660  stloc.3
0x10661  ldloc.3
0x10662  brfalse  loc_10781
0x10667  ldloc.1
0x10668  ldstr    aExceptionMessa// "Exception message: {0}, additional mess"...
0x1066d  ldloc.3
0x1066e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x10673  ldloc.3
0x10674  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_AdditionalTraceMessage()
0x10679  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x1067e  pop
0x1067f  ldloc.3
0x10680  callvirt instance object[] [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ExceptionData()
0x10685  brfalse  loc_1079D
0x1068a  ldarg.0
0x1068b  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x10690  ldloc.3
0x10691  callvirt instance object[] [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ExceptionData()
0x10696  ldlen
0x10697  conv.i4
0x10698  newarr   [mscorlib]System.Runtime.InteropServices.GCHandle
0x1069d  stfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x106a2  ldc.i4.0
0x106a3  stloc.s  4
0x106a5  br       loc_10770
0x106aa  ldloc.3
0x106ab  callvirt instance object[] [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ExceptionData()
0x106b0  ldloc.s  4
0x106b2  ldelem.ref
0x106b3  stloc.s  5
0x106b5  ldc.i4.0
0x106b6  stloc.s  6
0x106b8  ldloc.s  5
0x106ba  isinst   [mscorlib]System.String
0x106bf  brfalse.s loc_106D3
0x106c1  ldloc.s  5
0x106c3  castclass [mscorlib]System.String
0x106c8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x106cd  ldc.i4.2
0x106ce  mul
0x106cf  stloc.s  6
0x106d1  br.s     loc_10723
0x106d3  ldloc.s  5
0x106d5  isinst   [mscorlib]System.Array
0x106da  brfalse.s loc_10723
0x106dc  ldloc.s  5
0x106de  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x106e3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x106e8  ldnull
0x106e9  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x106ee  brfalse.s loc_10723
0x106f0  ldloc.s  5
0x106f2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x106f7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x106fc  callvirt instance bool [mscorlib]System.Type::get_IsPrimitive()
0x10701  brfalse.s loc_10723
0x10703  ldloc.s  5
0x10705  castclass [mscorlib]System.Array
0x1070a  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x1070f  ldloc.s  5
0x10711  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10716  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetElementType()
0x1071b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x10720  mul
0x10721  stloc.s  6
0x10723  ldloc.s  6
0x10725  brfalse.s loc_1076A
0x10727  ldarg.0
0x10728  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1072d  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x10732  ldloc.s  4
0x10734  ldloc.s  5
0x10736  ldc.i4.3
0x10737  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0x1073c  stelem   [mscorlib]System.Runtime.InteropServices.GCHandle
0x10741  ldarg.0
0x10742  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x10747  ldarg.0
0x10748  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1074d  ldfld    valuetype [mscorlib]System.Runtime.InteropServices.GCHandle[] <>c__DisplayClass26_0::gcHandles
0x10752  ldloc.s  4
0x10754  ldelema  [mscorlib]System.Runtime.InteropServices.GCHandle
0x10759  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x1075e  ldloc.s  6
0x10760  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::AddMemoryRaw(native int, int32)
0x10765  leave.s  loc_1076A
0x10767  pop
0x10768  leave.s  loc_1076A
0x1076a  ldloc.s  4
0x1076c  ldc.i4.1
0x1076d  add
0x1076e  stloc.s  4
0x10770  ldloc.s  4
0x10772  ldloc.3
0x10773  callvirt instance object[] [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ExceptionData()
0x10778  ldlen
0x10779  conv.i4
0x1077a  blt      loc_106AA
0x1077f  br.s     loc_1079D
0x10781  ldloc.1
0x10782  ldstr    aExceptionMessa_0// "Exception message: {0}\r\n"
0x10787  ldarg.0
0x10788  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x1078d  ldfld    class [mscorlib]System.Exception <>c__DisplayClass26_0::optionalException
0x10792  callvirt instance string [mscorlib]System.Exception::get_Message()
0x10797  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1079c  pop
0x1079d  ldarg.0
0x1079e  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x107a3  ldfld    string <>c__DisplayClass26_0::assertionMessage
0x107a8  brfalse.s loc_107C1
0x107aa  ldloc.1
0x107ab  ldstr    aAssertionFaile// "Assertion failed: {0}\r\n"
0x107b0  ldarg.0
0x107b1  ldfld    class <>c__DisplayClass26_0 <>c__DisplayClass26_1::CS$<>8__locals1
0x107b6  ldfld    string <>c__DisplayClass26_0::assertionMessage
0x107bb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x107c0  pop
0x107c1  ldc.i4.0
0x107c2  ldloc.1
0x107c3  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x107c8  bge.s    loc_107DB
0x107ca  ldarg.0
0x107cb  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x107d0  ldloc.1
0x107d1  callvirt instance string [mscorlib]System.Object::ToString()
0x107d6  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetErrorText(string)
0x107db  ldloc.2
0x107dc  brfalse.s loc_107EA
0x107de  ldarg.0
0x107df  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x107e4  ldloc.2
0x107e5  callvirt instance void [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper::SetErrorText(string)
0x107ea  ldarg.0
0x107eb  ldfld    class [Microsoft.SqlServer.MgdSqlDumper]Microsoft.SqlServer.SqlDumper.Dumper <>c__DisplayClass26_1::sqlDumper
0x107f0  ldc.i4.s 0x10
0x107f2  ldc.i4.0
  ... truncated ...
```
