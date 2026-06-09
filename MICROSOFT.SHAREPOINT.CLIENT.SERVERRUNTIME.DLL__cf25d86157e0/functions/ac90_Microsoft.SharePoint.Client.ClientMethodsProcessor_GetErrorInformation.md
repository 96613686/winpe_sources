# Microsoft.SharePoint.Client.ClientMethodsProcessor::GetErrorInformation

- ea: `0xac90`
- end: `0xafce`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::GetErrorInformation`
- size: `830`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0xaba0`
- `0x271f0`

## callees

- `0xac90`
- `0xafd0`
- `0xb040`
- `0xe000`
- `0xe010`
- `0xe520`
- `0xe6a0`
- `0xe8c0`
- `0xe8e0`
- `0xe900`
- `0xe920`
- `0xe930`
- `0xe940`
- `0xe9d0`
- `0xed20`
- `0x124d0`
- `0x125c0`
- `0x12720`
- `0x128a0`
- `0x128b0`
- `0x16f00`

## string_xrefs

- `0xaf15`: `AccessDenied`

## pseudocode

```c

```

## disassembly

```asm
0xac90  ldnull
0xac91  stloc.0
0xac92  ldarg.1
0xac93  brfalse.s loc_ACB1
0xac95  ldarg.1
0xac96  ldc.i4   0x18C24F
0xac9b  ldc.i4.2
0xac9c  ldstr    aOriginalError// "Original error: "
0xaca1  ldarg.0
0xaca2  callvirt instance string [mscorlib]System.Object::ToString()
0xaca7  call     string [mscorlib]System.String::Concat(string, string)
0xacac  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0xacb1  ldarg.0
0xacb2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xacb7  call     bool Microsoft.SharePoint.Client.ErrorCodeMap::ShouldHideExceptionDetails(class [mscorlib]System.Type exceptionType)
0xacbc  brfalse.s loc_AD36
0xacbe  ldarg.1
0xacbf  brfalse.s loc_ACFE
0xacc1  ldarg.1
0xacc2  ldc.i4   0x61B460
0xacc7  ldc.i4.2
0xacc8  ldstr    aMaskingInterna// "Masking internal Exception '{0}' and se"...
0xaccd  ldc.i4.3
0xacce  newarr   [mscorlib]System.Object
0xacd3  stloc.s  8
0xacd5  ldloc.s  8
0xacd7  ldc.i4.0
0xacd8  ldarg.0
0xacd9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xacde  callvirt instance string [mscorlib]System.Object::ToString()
0xace3  stelem.ref
0xace4  ldloc.s  8
0xace6  ldc.i4.1
0xace7  ldstr    aMicrosoftShare_2// "Microsoft.SharePoint.Client.UnknownErro"...
0xacec  stelem.ref
0xaced  ldloc.s  8
0xacef  ldc.i4.2
0xacf0  ldc.i4.m1
0xacf1  box      [mscorlib]System.Int32
0xacf6  stelem.ref
0xacf7  ldloc.s  8
0xacf9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xacfe  newobj   instance void Microsoft.SharePoint.Client.ErrorInformation::.ctor()
0xad03  stloc.0
0xad04  ldloc.0
0xad05  ldc.i4.m1
0xad06  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xad0b  ldloc.0
0xad0c  ldstr    aUnknownerror// "UnknownError"
0xad11  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xad16  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_Message(string value)
0xad1b  ldloc.0
0xad1c  ldstr    aMicrosoftShare_2// "Microsoft.SharePoint.Client.UnknownErro"...
0xad21  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorTypeName(string value)
0xad26  ldloc.0
0xad27  ldc.i4   0x1F4
0xad2c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0xad31  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0xad36  ldloc.0
0xad37  brtrue.s loc_AD75
0xad39  ldarg.1
0xad3a  brfalse.s loc_AD75
0xad3c  ldarg.1
0xad3d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler> Microsoft.SharePoint.Client.ClientServiceHost::get_RequestHandlers()
0xad42  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler>::GetEnumerator()
0xad47  stloc.s  9
0xad49  br.s     loc_AD5E
0xad4b  ldloc.s  9
0xad4d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.ClientServiceProcessingHandler>::get_Current()
0xad52  stloc.1
0xad53  ldloc.1
0xad54  ldarg.0
0xad55  ldloca.s 0
0xad57  callvirt instance bool Microsoft.SharePoint.Client.ClientServiceProcessingHandler::TryGetErrorInformation(class [mscorlib]System.Exception ex, [out] class Microsoft.SharePoint.Client.ErrorInformation& errorInformation)
0xad5c  brtrue.s loc_AD67
0xad5e  ldloc.s  9
0xad60  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xad65  brtrue.s loc_AD4B
0xad67  leave.s  loc_AD75
0xad69  ldloc.s  9
0xad6b  brfalse.s loc_AD74
0xad6d  ldloc.s  9
0xad6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad74  endfinally
0xad75  ldloc.0
0xad76  brtrue.s loc_AD8D
0xad78  ldnull
0xad79  stloc.2
0xad7a  ldarg.0
0xad7b  call     class Microsoft.SharePoint.Client.ClientServiceException Microsoft.SharePoint.Client.ClientMethodsProcessor::GetClientServiceException(class [mscorlib]System.Exception ex)
0xad80  stloc.3
0xad81  ldloc.3
0xad82  brfalse.s loc_AD8B
0xad84  ldloc.3
0xad85  callvirt instance class Microsoft.SharePoint.Client.ErrorInformation Microsoft.SharePoint.Client.ClientServiceException::get_ErrorInformation()
0xad8a  stloc.2
0xad8b  ldloc.2
0xad8c  stloc.0
0xad8d  ldloc.0
0xad8e  brtrue.s loc_AD9B
0xad90  ldarg.1
0xad91  brfalse.s loc_AD9B
0xad93  ldarg.1
0xad94  ldarg.0
0xad95  callvirt instance class Microsoft.SharePoint.Client.ErrorInformation Microsoft.SharePoint.Client.ClientServiceHost::GetErrorInformation(class [mscorlib]System.Exception ex)
0xad9a  stloc.0
0xad9b  ldloc.0
0xad9c  brtrue   loc_AED7
0xada1  newobj   instance void Microsoft.SharePoint.Client.ErrorInformation::.ctor()
0xada6  stloc.0
0xada7  ldarg.0
0xada8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xadad  ldloca.s 4
0xadaf  call     bool Microsoft.SharePoint.Client.ErrorCodeMap::TryGetErrorCode(class [mscorlib]System.Type exceptionType, [out] int32& errorCode)
0xadb4  brfalse.s loc_ADC3
0xadb6  ldloc.0
0xadb7  ldloc.s  4
0xadb9  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xadbe  br       loc_AED7
0xadc3  ldarg.0
0xadc4  isinst   [mscorlib]System.Runtime.InteropServices.COMException
0xadc9  brfalse.s loc_ADE1
0xadcb  ldloc.0
0xadcc  ldarg.0
0xadcd  castclass [mscorlib]System.Runtime.InteropServices.COMException
0xadd2  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xadd7  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xaddc  br       loc_AED7
0xade1  ldarg.0
0xade2  isinst   Microsoft.SharePoint.Client.VersionConflictException
0xade7  brfalse.s loc_ADF9
0xade9  ldloc.0
0xadea  ldc.i4   0x81020015
0xadef  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xadf4  br       loc_AED7
0xadf9  ldarg.0
0xadfa  isinst   Microsoft.SharePoint.Client.ApiBlockedException
0xadff  brfalse.s loc_AE11
0xae01  ldloc.0
0xae02  ldc.i4   0x80070032
0xae07  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xae0c  br       loc_AED7
0xae11  ldarg.0
0xae12  isinst   Microsoft.SharePoint.Client.ClientServiceTimeoutException
0xae17  brfalse.s loc_AE29
0xae19  ldloc.0
0xae1a  ldc.i4   0x80131505
0xae1f  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xae24  br       loc_AED7
0xae29  ldarg.0
0xae2a  isinst   Microsoft.SharePoint.Client.RedirectException
0xae2f  brfalse.s loc_AE52
0xae31  ldloc.0
0xae32  ldc.i4   0x810200D0
0xae37  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xae3c  ldloc.0
0xae3d  ldarg.0
0xae3e  castclass Microsoft.SharePoint.Client.RedirectException
0xae43  callvirt instance string Microsoft.SharePoint.Client.RedirectException::get_RedirectUrl()
0xae48  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorValue(string value)
0xae4d  br       loc_AED7
0xae52  ldarg.0
0xae53  isinst   Microsoft.SharePoint.Client.NotSupportedRequestVersionException
0xae58  brfalse.s loc_AED7
0xae5a  ldloc.0
0xae5b  ldc.i4   0x810200D1
0xae60  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorCode(int32 value)
0xae65  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xae6a  stloc.s  5
0xae6c  ldarg.0
0xae6d  castclass Microsoft.SharePoint.Client.NotSupportedRequestVersionException
0xae72  stloc.s  6
0xae74  ldloc.s  6
0xae76  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Version> Microsoft.SharePoint.Client.NotSupportedRequestVersionException::get_SupportedRequestVersions()
0xae7b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Version>::GetEnumerator()
0xae80  stloc.s  0xA
0xae82  br.s     loc_AEB3
0xae84  ldloc.s  0xA
0xae86  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Version>::get_Current()
0xae8b  stloc.s  7
0xae8d  ldloc.s  5
0xae8f  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0xae94  ldc.i4.0
0xae95  ble.s    loc_AEA4
0xae97  ldloc.s  5
0xae99  ldstr    asc_40BB2// ", "
0xae9e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xaea3  pop
0xaea4  ldloc.s  5
0xaea6  ldloc.s  7
0xaea8  callvirt instance string [mscorlib]System.Object::ToString()
0xaead  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xaeb2  pop
0xaeb3  ldloc.s  0xA
0xaeb5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xaeba  brtrue.s loc_AE84
0xaebc  leave.s  loc_AECA
0xaebe  ldloc.s  0xA
0xaec0  brfalse.s loc_AEC9
0xaec2  ldloc.s  0xA
0xaec4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaec9  endfinally
0xaeca  ldloc.0
0xaecb  ldloc.s  5
0xaecd  callvirt instance string [mscorlib]System.Object::ToString()
0xaed2  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_ErrorValue(string value)
0xaed7  ldarg.0
0xaed8  isinst   [mscorlib]System.IO.FileNotFoundException
0xaedd  brtrue.s loc_AEE7
0xaedf  ldarg.0
0xaee0  isinst   [mscorlib]System.IO.DirectoryNotFoundException
0xaee5  brfalse.s loc_AF0C
0xaee7  ldloc.0
0xaee8  ldstr    aFilenotfound// "FileNotFound"
0xaeed  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xaef2  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_Message(string value)
0xaef7  ldloc.0
0xaef8  ldc.i4   0x194
0xaefd  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0xaf02  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0xaf07  br       loc_AFC5
0xaf0c  ldarg.0
0xaf0d  isinst   [mscorlib]System.UnauthorizedAccessException
0xaf12  brfalse.s loc_AF4A
0xaf14  ldloc.0
0xaf15  ldstr    aAccessdenied// "AccessDenied"
0xaf1a  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xaf1f  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_Message(string value)
0xaf24  ldloc.0
0xaf25  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0xaf2a  stloc.s  0xB
0xaf2c  ldloca.s 0xB
0xaf2e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0xaf33  brtrue   loc_AFC5
0xaf38  ldloc.0
0xaf39  ldc.i4   0x191
0xaf3e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0xaf43  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0xaf48  br.s     loc_AFC5
0xaf4a  ldarg.0
0xaf4b  isinst   [mscorlib]System.InvalidOperationException
0xaf50  brfalse.s loc_AF75
0xaf52  ldloc.0
0xaf53  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0xaf58  stloc.s  0xC
0xaf5a  ldloca.s 0xC
0xaf5c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0xaf61  brtrue.s loc_AFC5
0xaf63  ldloc.0
0xaf64  ldc.i4   0x190
0xaf69  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0xaf6e  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0xaf73  br.s     loc_AFC5
0xaf75  ldarg.0
0xaf76  isinst   [mscorlib]System.ArgumentNullException
0xaf7b  brtrue.s loc_AFA4
0xaf7d  ldarg.0
0xaf7e  isinst   [mscorlib]System.ArgumentOutOfRangeException
0xaf83  brtrue.s loc_AFA4
0xaf85  ldarg.0
0xaf86  isinst   [System]System.ComponentModel.InvalidEnumArgumentException
0xaf8b  brtrue.s loc_AFA4
0xaf8d  ldarg.0
0xaf8e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xaf93  ldtoken  [mscorlib]System.ArgumentException
0xaf98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaf9d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xafa2  brfalse.s loc_AFC5
0xafa4  ldloc.0
0xafa5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.SharePoint.Client.ErrorInformation::get_HttpStatusCode()
0xafaa  stloc.s  0xD
0xafac  ldloca.s 0xD
0xafae  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::get_HasValue()
0xafb3  brtrue.s loc_AFC5
0xafb5  ldloc.0
0xafb6  ldc.i4   0x190
0xafbb  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0xafc0  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0xafc5  ldloc.0
0xafc6  ldarg.0
0xafc7  call     void Microsoft.SharePoint.Client.ClientMethodsProcessor::FillErrorInformation(class Microsoft.SharePoint.Client.ErrorInformation errorInfo, class [mscorlib]System.Exception ex)
0xafcc  ldloc.0
0xafcd  ret
```
