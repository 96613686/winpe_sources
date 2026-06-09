# Microsoft.ReportingServices.Diagnostics.Task::ReadMonthlyDOW

- ea: `0xe140`
- end: `0xe353`
- name: `Microsoft.ReportingServices.Diagnostics.Task::ReadMonthlyDOW`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xdd20`

## callees

- `0xd830`
- `0xe140`
- `0xe360`
- `0xe540`
- `0xf680`
- `0x100d0`

## pseudocode

```c

```

## disassembly

```asm
0xe140  ldc.i4.0
0xe141  stloc.0
0xe142  ldc.i4.0
0xe143  stloc.1
0xe144  ldc.i4.0
0xe145  stloc.2
0xe146  br       loc_E339
0xe14b  ldarg.1
0xe14c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe151  ldc.i4.s 0xF
0xe153  bne.un.s loc_E16F
0xe155  ldarg.1
0xe156  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe15b  ldstr    aMonthlydowrecu// "MonthlyDOWRecurrence"
0xe160  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe165  brfalse  loc_E339
0xe16a  br       loc_E344
0xe16f  ldarg.1
0xe170  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe175  ldstr    aDaysofweek// "DaysOfWeek"
0xe17a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe17f  brfalse.s loc_E18E
0xe181  ldarg.0
0xe182  ldarg.1
0xe183  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Task::ReadDaysOfWeek(class [System.Xml]System.Xml.XmlTextReader reader)
0xe188  stloc.1
0xe189  br       loc_E339
0xe18e  ldarg.1
0xe18f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe194  ldstr    aMonthsofyear// "MonthsOfYear"
0xe199  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe19e  brfalse.s loc_E1AD
0xe1a0  ldarg.0
0xe1a1  ldarg.1
0xe1a2  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Task::ReadMonthsOfYear(class [System.Xml]System.Xml.XmlTextReader reader)
0xe1a7  stloc.2
0xe1a8  br       loc_E339
0xe1ad  ldarg.1
0xe1ae  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe1b3  ldstr    aWhichweek// "WhichWeek"
0xe1b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe1bd  brfalse  loc_E333
0xe1c2  ldarg.1
0xe1c3  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xe1c8  stloc.3
0xe1c9  ldloc.3
0xe1ca  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xe1cf  stloc.s  4
0xe1d1  ldloc.s  4
0xe1d3  ldc.i4   0x7C837625
0xe1d8  bgt.un.s loc_E229
0xe1da  ldloc.s  4
0xe1dc  ldc.i4   0x30C533B1
0xe1e1  bgt.un.s loc_E200
0xe1e3  ldloc.s  4
0xe1e5  ldc.i4   0x10FF97E6
0xe1ea  beq      loc_E275
0xe1ef  ldloc.s  4
0xe1f1  ldc.i4   0x30C533B1
0xe1f6  beq      loc_E28A
0xe1fb  br       loc_E328
0xe200  ldloc.s  4
0xe202  ldc.i4   0x384C855A
0xe207  beq      loc_E29C
0xe20c  ldloc.s  4
0xe20e  ldc.i4   0x6270C6B3
0xe213  beq      loc_E2BA
0xe218  ldloc.s  4
0xe21a  ldc.i4   0x7C837625
0xe21f  beq      loc_E2AB
0xe224  br       loc_E328
0xe229  ldloc.s  4
0xe22b  ldc.i4   0xB4F6D341
0xe230  bgt.un.s loc_E24F
0xe232  ldloc.s  4
0xe234  ldc.i4   0x91FACE22
0xe239  beq      loc_E2C9
0xe23e  ldloc.s  4
0xe240  ldc.i4   0xB4F6D341
0xe245  beq      loc_E2E7
0xe24a  br       loc_E328
0xe24f  ldloc.s  4
0xe251  ldc.i4   0xE1FA636E
0xe256  beq      loc_E2F6
0xe25b  ldloc.s  4
0xe25d  ldc.i4   0xE6C06BD6
0xe262  beq.s    loc_E2D8
0xe264  ldloc.s  4
0xe266  ldc.i4   0xF6CBE079
0xe26b  beq      loc_E305
0xe270  br       loc_E328
0xe275  ldloc.3
0xe276  ldstr    aFirstWeek// "FIRST_WEEK"
0xe27b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe280  brtrue   loc_E314
0xe285  br       loc_E328
0xe28a  ldloc.3
0xe28b  ldstr    aFirstweek// "FirstWeek"
0xe290  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe295  brtrue.s loc_E314
0xe297  br       loc_E328
0xe29c  ldloc.3
0xe29d  ldstr    aSecondWeek// "SECOND_WEEK"
0xe2a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2a7  brtrue.s loc_E318
0xe2a9  br.s     loc_E328
0xe2ab  ldloc.3
0xe2ac  ldstr    aSecondweek// "SecondWeek"
0xe2b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2b6  brtrue.s loc_E318
0xe2b8  br.s     loc_E328
0xe2ba  ldloc.3
0xe2bb  ldstr    aThirdWeek// "THIRD_WEEK"
0xe2c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2c5  brtrue.s loc_E31C
0xe2c7  br.s     loc_E328
0xe2c9  ldloc.3
0xe2ca  ldstr    aThirdweek// "ThirdWeek"
0xe2cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2d4  brtrue.s loc_E31C
0xe2d6  br.s     loc_E328
0xe2d8  ldloc.3
0xe2d9  ldstr    aFourthWeek// "FOURTH_WEEK"
0xe2de  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2e3  brtrue.s loc_E320
0xe2e5  br.s     loc_E328
0xe2e7  ldloc.3
0xe2e8  ldstr    aFourthweek// "FourthWeek"
0xe2ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe2f2  brtrue.s loc_E320
0xe2f4  br.s     loc_E328
0xe2f6  ldloc.3
0xe2f7  ldstr    aLastWeek// "LAST_WEEK"
0xe2fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe301  brtrue.s loc_E324
0xe303  br.s     loc_E328
0xe305  ldloc.3
0xe306  ldstr    aLastweek// "LastWeek"
0xe30b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe310  brtrue.s loc_E324
0xe312  br.s     loc_E328
0xe314  ldc.i4.1
0xe315  stloc.0
0xe316  br.s     loc_E339
0xe318  ldc.i4.2
0xe319  stloc.0
0xe31a  br.s     loc_E339
0xe31c  ldc.i4.3
0xe31d  stloc.0
0xe31e  br.s     loc_E339
0xe320  ldc.i4.4
0xe321  stloc.0
0xe322  br.s     loc_E339
0xe324  ldc.i4.5
0xe325  stloc.0
0xe326  br.s     loc_E339
0xe328  ldstr    aWhichweek// "WhichWeek"
0xe32d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xe332  throw
0xe333  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xe338  throw
0xe339  ldarg.1
0xe33a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe33f  brtrue   loc_E14B
0xe344  ldarg.0
0xe345  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe34a  ldloc.0
0xe34b  ldloc.1
0xe34c  ldloc.2
0xe34d  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthlyDOW(unsigned int32 week, unsigned int32 daysOfWeek, unsigned int32 months)
0xe352  ret
```
