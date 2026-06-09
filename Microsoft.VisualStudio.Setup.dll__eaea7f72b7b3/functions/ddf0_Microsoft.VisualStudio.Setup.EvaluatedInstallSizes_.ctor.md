# Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::.ctor

- ea: `0xddf0`
- end: `0xe150`
- name: `Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::.ctor`
- size: `864`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x20f20`
- `0x4f310`
- `0x5e690`

## callees

- `0xddd0`
- `0xddf0`
- `0xe170`
- `0xf100`
- `0x1cce0`
- `0x1ce70`
- `0x1f690`
- `0x1f6f0`
- `0x1f720`
- `0x1f740`
- `0x1f770`
- `0x1f860`
- `0x1f880`
- `0x1f8a0`
- `0x1f8b0`
- `0x280b0`
- `0x3ead0`
- `0x3eb70`

## string_xrefs

- `0xddfe`: `services`
- `0xdf9a`: `SharedInstall`

## pseudocode

```c

```

## disassembly

```asm
0xddf0  ldarg.0
0xddf1  ldc.i4.1
0xddf2  stfld    bool Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::<HasSufficientDiskSpace>k__BackingField
0xddf7  ldarg.0
0xddf8  call     instance void [mscorlib]System.Object::.ctor()
0xddfd  ldarg.1
0xddfe  ldstr    aServices// "services"
0xde03  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0xde08  ldarg.0
0xde09  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xde0e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xde13  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::<InstallSizes>k__BackingField
0xde18  ldarg.1
0xde19  ldc.i4.1
0xde1a  call     T0x2B00000C
0xde1f  stloc.0
0xde20  ldloc.0
0xde21  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SystemDirectory()
0xde26  call     string Microsoft.VisualStudio.Setup.Utility.IOUtil::GetPathRoot(string filePath)
0xde2b  stloc.1
0xde2c  ldarg.3
0xde2d  call     string Microsoft.VisualStudio.Setup.Utility.IOUtil::GetPathRoot(string filePath)
0xde32  stloc.2
0xde33  ldarg.s  6
0xde35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xde3a  brfalse.s loc_DE57
0xde3c  ldarg.1
0xde3d  ldarg.0
0xde3e  ldflda   class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::policyService
0xde43  ldc.i4.1
0xde44  call     T0x2B0000A6
0xde49  pop
0xde4a  ldarg.0
0xde4b  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::policyService
0xde50  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_SharedInstallationPath()
0xde55  starg.s  6
0xde57  ldarg.s  5
0xde59  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xde5e  brfalse.s loc_DE7B
0xde60  ldarg.1
0xde61  ldarg.0
0xde62  ldflda   class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::policyService
0xde67  ldc.i4.1
0xde68  call     T0x2B0000A6
0xde6d  pop
0xde6e  ldarg.0
0xde6f  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::policyService
0xde74  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CachePath()
0xde79  starg.s  5
0xde7b  ldarg.s  6
0xde7d  call     string Microsoft.VisualStudio.Setup.Utility.IOUtil::GetPathRoot(string filePath)
0xde82  stloc.3
0xde83  ldarg.s  5
0xde85  call     string Microsoft.VisualStudio.Setup.Utility.IOUtil::GetPathRoot(string filePath)
0xde8a  stloc.s  4
0xde8c  ldloc.1
0xde8d  brfalse  loc_E14F
0xde92  ldarg.0
0xde93  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xde98  ldloc.1
0xde99  ldarg.2
0xde9a  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_SystemDrive()
0xde9f  ldarg.2
0xdea0  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSystemDelta()
0xdea5  ldloc.1
0xdea6  newobj   instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation::.ctor(int64 currentInstallSize, int64 requestedDeltaSize, string driveName)
0xdeab  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::Add(var<u1>, !!T0)
0xdeb0  ldarg.0
0xdeb1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xdeb6  ldloc.1
0xdeb7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Item(void)
0xdebc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment> Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation::get_Segments()
0xdec1  newobj   instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment::.ctor()
0xdec6  dup
0xdec7  ldarg.2
0xdec8  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_SystemDrive()
0xdecd  callvirt instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment::set_Actual(int64 value)
0xded2  dup
0xded3  ldarg.2
0xded4  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSystemDelta()
0xded9  callvirt instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment::set_Requested(int64 value)
0xdede  dup
0xdedf  ldc.i4.2
0xdee0  callvirt instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment::set_Type(valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType value)
0xdee5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluationSegment>::Add(var<u1>)
0xdeea  ldarg.0
0xdeeb  ldarg.2
0xdeec  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_TargetDrive()
0xdef1  ldarg.2
0xdef2  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedDeltaTarget()
0xdef7  ldloc.2
0xdef8  ldc.i4.3
0xdef9  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xdefe  ldarg.0
0xdeff  ldarg.2
0xdf00  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_SharedDrive()
0xdf05  ldarg.2
0xdf06  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSharedDelta()
0xdf0b  ldloc.3
0xdf0c  ldc.i4.1
0xdf0d  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xdf12  ldarg.0
0xdf13  ldarg.2
0xdf14  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_CacheSize()
0xdf19  ldarg.2
0xdf1a  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedCacheDelta()
0xdf1f  ldloc.s  4
0xdf21  ldc.i4.0
0xdf22  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xdf27  ldloc.s  4
0xdf29  ldloc.1
0xdf2a  ldc.i4.5
0xdf2b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdf30  brtrue.s loc_DF46
0xdf32  ldarg.0
0xdf33  ldarg.2
0xdf34  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_CacheSize()
0xdf39  ldarg.2
0xdf3a  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::get_RequestedCacheDelta()
0xdf3f  ldloc.1
0xdf40  ldc.i4.4
0xdf41  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xdf46  ldarg.2
0xdf47  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSize::GetCustomActualAndRequestedSizes()
0xdf4c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>>::GetEnumerator()
0xdf51  stloc.s  5
0xdf53  br       loc_E081
0xdf58  ldloc.s  5
0xdf5a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>>::get_Current()
0xdf5f  stloc.s  6
0xdf61  ldloca.s 6
0xdf63  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Key()
0xdf68  stloc.s  7
0xdf6a  ldarg.s  4
0xdf6c  brfalse  loc_E02C
0xdf71  ldarg.s  4
0xdf73  ldloc.s  7
0xdf75  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0xdf7a  brfalse  loc_E02C
0xdf7f  ldarg.s  4
0xdf81  ldloc.s  7
0xdf83  callvirt instance string Microsoft.VisualStudio.Setup.VariableCollection::get_Item(string)
0xdf88  brfalse  loc_E02C
0xdf8d  ldarg.s  4
0xdf8f  ldloc.s  7
0xdf91  callvirt instance string Microsoft.VisualStudio.Setup.VariableCollection::get_Item(string)
0xdf96  stloc.s  8
0xdf98  ldloc.s  8
0xdf9a  ldstr    aSharedinstall// "SharedInstall"
0xdf9f  ldc.i4.0
0xdfa0  ldc.i4.5
0xdfa1  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0xdfa6  ldc.i4.0
0xdfa7  bge.s    loc_DFBF
0xdfa9  ldloc.s  8
0xdfab  ldstr    aShareddrive// "SharedDrive"
0xdfb0  ldc.i4.0
0xdfb1  ldc.i4.5
0xdfb2  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0xdfb7  ldc.i4.0
0xdfb8  clt
0xdfba  ldc.i4.0
0xdfbb  ceq
0xdfbd  br.s     loc_DFC0
0xdfbf  ldc.i4.1
0xdfc0  ldloc.s  8
0xdfc2  ldarg.s  4
0xdfc4  ldnull
0xdfc5  ldc.i4.0
0xdfc6  ldnull
0xdfc7  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, [opt] class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0xdfcc  call     string Microsoft.VisualStudio.Setup.Utility.IOUtil::GetPathRoot(string filePath)
0xdfd1  stloc.s  9
0xdfd3  ldc.i4.2
0xdfd4  stloc.s  0xA
0xdfd6  brfalse.s loc_DFE0
0xdfd8  ldloc.3
0xdfd9  stloc.s  9
0xdfdb  ldc.i4.1
0xdfdc  stloc.s  0xA
0xdfde  br.s     loc_E000
0xdfe0  ldloc.0
0xdfe1  ldloc.s  9
0xdfe3  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsDriveFixed(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string)
0xdfe8  brfalse.s loc_DFF5
0xdfea  ldloc.s  9
0xdfec  ldloc.1
0xdfed  ldc.i4.5
0xdfee  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdff3  brfalse.s loc_DFFD
0xdff5  ldloc.1
0xdff6  stloc.s  9
0xdff8  ldc.i4.2
0xdff9  stloc.s  0xA
0xdffb  br.s     loc_E000
0xdffd  ldc.i4.5
0xdffe  stloc.s  0xA
0xe000  ldarg.0
0xe001  ldloca.s 6
0xe003  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe008  stloc.s  0xB
0xe00a  ldloca.s 0xB
0xe00c  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Actual()
0xe011  ldloca.s 6
0xe013  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe018  stloc.s  0xB
0xe01a  ldloca.s 0xB
0xe01c  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Requested()
0xe021  ldloc.s  9
0xe023  ldloc.s  0xA
0xe025  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xe02a  br.s     loc_E054
0xe02c  ldarg.0
0xe02d  ldloca.s 6
0xe02f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe034  stloc.s  0xB
0xe036  ldloca.s 0xB
0xe038  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Actual()
0xe03d  ldloca.s 6
0xe03f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe044  stloc.s  0xB
0xe046  ldloca.s 0xB
0xe048  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Requested()
0xe04d  ldloc.1
0xe04e  ldc.i4.2
0xe04f  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xe054  leave.s  loc_E081
0xe056  pop
0xe057  ldarg.0
0xe058  ldloca.s 6
0xe05a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe05f  stloc.s  0xB
0xe061  ldloca.s 0xB
0xe063  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Actual()
0xe068  ldloca.s 6
0xe06a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Value()
0xe06f  stloc.s  0xB
0xe071  ldloca.s 0xB
0xe073  call     instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallSizePerDrive::get_Requested()
0xe078  ldloc.1
0xe079  ldc.i4.2
0xe07a  call     instance void Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::SetSizeMembers(int64 actual, int64 delta, string drivename, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType segmentType)
0xe07f  leave.s  loc_E081
0xe081  ldloc.s  5
0xe083  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe088  brtrue   loc_DF58
0xe08d  leave.s  loc_E09B
0xe08f  ldloc.s  5
0xe091  brfalse.s loc_E09A
0xe093  ldloc.s  5
0xe095  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe09a  endfinally
0xe09b  ldarg.0
0xe09c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xe0a1  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Keys()
0xe0a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xe0ab  stloc.s  0xC
0xe0ad  br       loc_E135
0xe0b2  ldloc.s  0xC
0xe0b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xe0b9  stloc.s  0xD
0xe0bb  ldloc.0
0xe0bc  ldloc.s  0xD
0xe0be  callvirt instance int64 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDriveFreeSpace(string)
0xe0c3  stloc.s  0xE
0xe0c5  ldarg.0
0xe0c6  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xe0cb  ldloc.s  0xD
0xe0cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Item(void)
0xe0d2  ldloc.s  0xE
0xe0d4  callvirt instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation::set_AvailableDiskSpace(int64 value)
0xe0d9  ldloc.s  0xE
0xe0db  ldarg.0
0xe0dc  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xe0e1  ldloc.s  0xD
0xe0e3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Item(void)
0xe0e8  callvirt instance int64 Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation::get_RequestedDeltaSize()
0xe0ed  ldarg.s  7
0xe0ef  add
0xe0f0  clt
0xe0f2  ldc.i4.0
0xe0f3  ceq
0xe0f5  stloc.s  0xF
0xe0f7  ldloc.s  0xF
0xe0f9  brtrue.s loc_E102
0xe0fb  ldarg.0
0xe0fc  ldc.i4.0
0xe0fd  stfld    bool Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::<HasSufficientDiskSpace>k__BackingField
0xe102  ldarg.0
0xe103  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xe108  ldloc.s  0xD
0xe10a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Item(void)
0xe10f  ldloc.s  0xF
0xe111  callvirt instance void Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation::set_HasSufficientDiskSpace(bool value)
0xe116  leave.s  loc_E135
0xe118  pop
0xe119  ldarg.0
0xe11a  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation> Microsoft.VisualStudio.Setup.EvaluatedInstallSizes::get_InstallSizes()
0xe11f  ldloc.s  0xD
0xe121  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Validation.DriveSpaceEvaluation>::get_Item(void)
  ... truncated ...
```
