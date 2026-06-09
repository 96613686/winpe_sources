# <WriteDocTypeAsync>d__116::MoveNext

- ea: `0x1111e0`
- end: `0x111484`
- name: `<WriteDocTypeAsync>d__116::MoveNext`
- size: `676`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0xf1e0`
- `0xf280`
- `0xfc50`
- `0x128e0`
- `0x3fb50`
- `0x41140`
- `0x622f0`
- `0x62370`
- `0x1111e0`

## string_xrefs

- `0x111215`: `Xml_EmptyName`
- `0x111314`: `Xml_InvalidCharacter`
- `0x111357`: `Xml_InvalidCharacter`
- `0x11139a`: `Xml_InvalidCharacter`
- `0x11123b`: `Xml_DtdNotAllowedInFragment`
- `0x1112c1`: `Xml_DtdAlreadyWritten`
- `0x111371`: `sysid`

## pseudocode

```c

```

## disassembly

```asm
0x1111e0  ldarg.0
0x1111e1  ldfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x1111e6  stloc.0
0x1111e7  ldarg.0
0x1111e8  ldfld    class System.Xml.XmlWellFormedWriter <WriteDocTypeAsync>d__116::<>4__this
0x1111ed  stloc.1
0x1111ee  ldloc.0
0x1111ef  ldc.i4.1
0x1111f0  pop
0x1111f1  pop
0x1111f2  nop
0x1111f3  ldloc.0
0x1111f4  brfalse  loc_11128E
0x1111f9  ldloc.0
0x1111fa  ldc.i4.1
0x1111fb  beq      loc_11141D
0x111200  ldarg.0
0x111201  ldfld    string <WriteDocTypeAsync>d__116::name
0x111206  brfalse.s loc_111215
0x111208  ldarg.0
0x111209  ldfld    string <WriteDocTypeAsync>d__116::name
0x11120e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x111213  brtrue.s loc_111225
0x111215  ldstr    aXmlEmptyname// "Xml_EmptyName"
0x11121a  call     string System.Xml.Res::GetString(string name)
0x11121f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x111224  throw
0x111225  ldarg.0
0x111226  ldfld    string <WriteDocTypeAsync>d__116::name
0x11122b  ldc.i4.1
0x11122c  call     string System.Xml.XmlConvert::VerifyQName(string name, valuetype System.Xml.ExceptionType exceptionType)
0x111231  pop
0x111232  ldloc.1
0x111233  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x111238  ldc.i4.1
0x111239  bne.un.s loc_11124B
0x11123b  ldstr    aXmlDtdnotallow// "Xml_DtdNotAllowedInFragment"
0x111240  call     string System.Xml.Res::GetString(string name)
0x111245  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x11124a  throw
0x11124b  ldloc.1
0x11124c  ldc.i4.4
0x11124d  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWellFormedWriter::AdvanceStateAsync(valuetype Token token)
0x111252  ldc.i4.0
0x111253  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111258  stloc.s  4
0x11125a  ldloca.s 4
0x11125c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111261  stloc.3
0x111262  ldloca.s 3
0x111264  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111269  brtrue.s loc_1112AA
0x11126b  ldarg.0
0x11126c  ldc.i4.0
0x11126d  dup
0x11126e  stloc.0
0x11126f  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x111274  ldarg.0
0x111275  ldloc.3
0x111276  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x11127b  ldarg.0
0x11127c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDocTypeAsync>d__116::<>t__builder
0x111281  ldloca.s 3
0x111283  ldarg.0
0x111284  call     T0x2B00025D
0x111289  leave    loc_111483
0x11128e  ldarg.0
0x11128f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x111294  stloc.3
0x111295  ldarg.0
0x111296  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x11129b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x1112a1  ldarg.0
0x1112a2  ldc.i4.m1
0x1112a3  dup
0x1112a4  stloc.0
0x1112a5  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x1112aa  ldloca.s 3
0x1112ac  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x1112b1  ldloc.1
0x1112b2  ldfld    bool System.Xml.XmlWellFormedWriter::dtdWritten
0x1112b7  brfalse.s loc_1112D1
0x1112b9  ldloc.1
0x1112ba  ldc.i4.s 0x10
0x1112bc  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x1112c1  ldstr    aXmlDtdalreadyw// "Xml_DtdAlreadyWritten"
0x1112c6  call     string System.Xml.Res::GetString(string name)
0x1112cb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1112d0  throw
0x1112d1  ldloc.1
0x1112d2  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x1112d7  brtrue.s loc_1112EB
0x1112d9  ldloc.1
0x1112da  ldc.i4.2
0x1112db  stfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x1112e0  ldloc.1
0x1112e1  ldsfld   valuetype State[] System.Xml.XmlWellFormedWriter::StateTableDocument
0x1112e6  stfld    valuetype State[] System.Xml.XmlWellFormedWriter::stateTable
0x1112eb  ldloc.1
0x1112ec  ldfld    bool System.Xml.XmlWellFormedWriter::checkCharacters
0x1112f1  brfalse  loc_1113BF
0x1112f6  ldarg.0
0x1112f7  ldfld    string <WriteDocTypeAsync>d__116::pubid
0x1112fc  brfalse.s loc_111339
0x1112fe  ldloc.1
0x1112ff  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x111304  ldarg.0
0x111305  ldfld    string <WriteDocTypeAsync>d__116::pubid
0x11130a  call     instance int32 System.Xml.XmlCharType::IsPublicId(string str)
0x11130f  dup
0x111310  stloc.2
0x111311  ldc.i4.0
0x111312  blt.s    loc_111339
0x111314  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x111319  ldarg.0
0x11131a  ldfld    string <WriteDocTypeAsync>d__116::pubid
0x11131f  ldloc.2
0x111320  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x111325  stloc.s  5
0x111327  ldloc.s  5
0x111329  call     string System.Xml.Res::GetString(string name, object[] args)
0x11132e  ldstr    aPubid// "pubid"
0x111333  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x111338  throw
0x111339  ldarg.0
0x11133a  ldfld    string <WriteDocTypeAsync>d__116::sysid
0x11133f  brfalse.s loc_11137C
0x111341  ldloc.1
0x111342  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x111347  ldarg.0
0x111348  ldfld    string <WriteDocTypeAsync>d__116::sysid
0x11134d  call     instance int32 System.Xml.XmlCharType::IsOnlyCharData(string str)
0x111352  dup
0x111353  stloc.2
0x111354  ldc.i4.0
0x111355  blt.s    loc_11137C
0x111357  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x11135c  ldarg.0
0x11135d  ldfld    string <WriteDocTypeAsync>d__116::sysid
0x111362  ldloc.2
0x111363  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x111368  stloc.s  5
0x11136a  ldloc.s  5
0x11136c  call     string System.Xml.Res::GetString(string name, object[] args)
0x111371  ldstr    aSysid// "sysid"
0x111376  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x11137b  throw
0x11137c  ldarg.0
0x11137d  ldfld    string <WriteDocTypeAsync>d__116::subset
0x111382  brfalse.s loc_1113BF
0x111384  ldloc.1
0x111385  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x11138a  ldarg.0
0x11138b  ldfld    string <WriteDocTypeAsync>d__116::subset
0x111390  call     instance int32 System.Xml.XmlCharType::IsOnlyCharData(string str)
0x111395  dup
0x111396  stloc.2
0x111397  ldc.i4.0
0x111398  blt.s    loc_1113BF
0x11139a  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x11139f  ldarg.0
0x1113a0  ldfld    string <WriteDocTypeAsync>d__116::subset
0x1113a5  ldloc.2
0x1113a6  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x1113ab  stloc.s  5
0x1113ad  ldloc.s  5
0x1113af  call     string System.Xml.Res::GetString(string name, object[] args)
0x1113b4  ldstr    aSubset// "subset"
0x1113b9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1113be  throw
0x1113bf  ldloc.1
0x1113c0  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x1113c5  ldarg.0
0x1113c6  ldfld    string <WriteDocTypeAsync>d__116::name
0x1113cb  ldarg.0
0x1113cc  ldfld    string <WriteDocTypeAsync>d__116::pubid
0x1113d1  ldarg.0
0x1113d2  ldfld    string <WriteDocTypeAsync>d__116::sysid
0x1113d7  ldarg.0
0x1113d8  ldfld    string <WriteDocTypeAsync>d__116::subset
0x1113dd  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteDocTypeAsync(string name, string pubid, string sysid, string subset)
0x1113e2  ldc.i4.0
0x1113e3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x1113e8  stloc.s  4
0x1113ea  ldloca.s 4
0x1113ec  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x1113f1  stloc.s  6
0x1113f3  ldloca.s 6
0x1113f5  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x1113fa  brtrue.s loc_11143A
0x1113fc  ldarg.0
0x1113fd  ldc.i4.1
0x1113fe  dup
0x1113ff  stloc.0
0x111400  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x111405  ldarg.0
0x111406  ldloc.s  6
0x111408  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x11140d  ldarg.0
0x11140e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDocTypeAsync>d__116::<>t__builder
0x111413  ldloca.s 6
0x111415  ldarg.0
0x111416  call     T0x2B00025D
0x11141b  leave.s  loc_111483
0x11141d  ldarg.0
0x11141e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x111423  stloc.s  6
0x111425  ldarg.0
0x111426  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDocTypeAsync>d__116::<>u__1
0x11142b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111431  ldarg.0
0x111432  ldc.i4.m1
0x111433  dup
0x111434  stloc.0
0x111435  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x11143a  ldloca.s 6
0x11143c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111441  ldloc.1
0x111442  ldc.i4.1
0x111443  stfld    bool System.Xml.XmlWellFormedWriter::dtdWritten
0x111448  leave.s  loc_111455
0x11144a  pop
0x11144b  ldloc.1
0x11144c  ldc.i4.s 0x10
0x11144e  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x111453  rethrow
0x111455  leave.s  loc_111470
0x111457  stloc.s  7
0x111459  ldarg.0
0x11145a  ldc.i4.s 0xFE
0x11145c  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x111461  ldarg.0
0x111462  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDocTypeAsync>d__116::<>t__builder
0x111467  ldloc.s  7
0x111469  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x11146e  leave.s  loc_111483
0x111470  ldarg.0
0x111471  ldc.i4.s 0xFE
0x111473  stfld    int32 <WriteDocTypeAsync>d__116::<>1__state
0x111478  ldarg.0
0x111479  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDocTypeAsync>d__116::<>t__builder
0x11147e  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x111483  ret
```
