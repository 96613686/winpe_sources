# System.Deployment.Application.ApplicationActivator::DisplayActivationFailureReason

- ea: `0xa410`
- end: `0xa778`
- name: `System.Deployment.Application.ApplicationActivator::DisplayActivationFailureReason`
- size: `872`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa8c0`

## callees

- `0xa410`
- `0xc040`
- `0xc060`
- `0x14740`
- `0x17d90`
- `0x17e00`
- `0x21d40`
- `0x23020`

## string_xrefs

- `0xa41b`: `ErrorMessage_GenericLinkUrlMessage`
- `0xa57a`: `ErrorMessage_ManifestCannotBeLoaded`
- `0xa5ab`: `ErrorMessage_InvalidManifest`
- `0xa63c`: `ErrorMessage_ManifestExecutionLevelNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0xa410  ldstr    aErrormessageGe// "ErrorMessage_GenericActivationFailure"
0xa415  call     string System.Deployment.Application.Resources::GetString(string s)
0xa41a  stloc.0
0xa41b  ldstr    aErrormessageGe_0// "ErrorMessage_GenericLinkUrlMessage"
0xa420  call     string System.Deployment.Application.Resources::GetString(string s)
0xa425  stloc.1
0xa426  ldarg.0
0xa427  ldarg.1
0xa428  call     instance class [mscorlib]System.Exception System.Deployment.Application.ApplicationActivator::GetInnerMostException(class [mscorlib]System.Exception exception)
0xa42d  stloc.2
0xa42e  ldarg.1
0xa42f  isinst   System.Deployment.Application.DeploymentDownloadException
0xa434  brfalse  loc_A55C
0xa439  ldstr    aErrormessageNe// "ErrorMessage_NetworkError"
0xa43e  call     string System.Deployment.Application.Resources::GetString(string s)
0xa443  stloc.0
0xa444  ldarg.1
0xa445  castclass System.Deployment.Application.DeploymentDownloadException
0xa44a  stloc.s  5
0xa44c  ldloc.s  5
0xa44e  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa453  ldc.i4.s 0x17
0xa455  bne.un.s loc_A462
0xa457  ldstr    aErrormessageSi// "ErrorMessage_SizeLimitForPartialTrustOn"...
0xa45c  call     string System.Deployment.Application.Resources::GetString(string s)
0xa461  stloc.0
0xa462  ldloc.2
0xa463  isinst   [System]System.Net.WebException
0xa468  brfalse  loc_A4FD
0xa46d  ldloc.2
0xa46e  castclass [System]System.Net.WebException
0xa473  stloc.s  6
0xa475  ldloc.s  6
0xa477  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0xa47c  brfalse  loc_A6F0
0xa481  ldloc.s  6
0xa483  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0xa488  isinst   [System]System.Net.HttpWebResponse
0xa48d  brfalse  loc_A6F0
0xa492  ldloc.s  6
0xa494  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0xa499  castclass [System]System.Net.HttpWebResponse
0xa49e  stloc.s  7
0xa4a0  ldloc.s  7
0xa4a2  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xa4a7  ldc.i4   0x194
0xa4ac  bne.un.s loc_A4BE
0xa4ae  ldstr    aErrormessageFi// "ErrorMessage_FileMissing"
0xa4b3  call     string System.Deployment.Application.Resources::GetString(string s)
0xa4b8  stloc.0
0xa4b9  br       loc_A6F0
0xa4be  ldloc.s  7
0xa4c0  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xa4c5  ldc.i4   0x191
0xa4ca  bne.un.s loc_A4DC
0xa4cc  ldstr    aErrormessageAu// "ErrorMessage_AuthenticationError"
0xa4d1  call     string System.Deployment.Application.Resources::GetString(string s)
0xa4d6  stloc.0
0xa4d7  br       loc_A6F0
0xa4dc  ldloc.s  7
0xa4de  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0xa4e3  ldc.i4   0x193
0xa4e8  bne.un   loc_A6F0
0xa4ed  ldstr    aErrormessageFo// "ErrorMessage_Forbidden"
0xa4f2  call     string System.Deployment.Application.Resources::GetString(string s)
0xa4f7  stloc.0
0xa4f8  br       loc_A6F0
0xa4fd  ldloc.2
0xa4fe  isinst   [mscorlib]System.IO.FileNotFoundException
0xa503  brtrue.s loc_A50D
0xa505  ldloc.2
0xa506  isinst   [mscorlib]System.IO.DirectoryNotFoundException
0xa50b  brfalse.s loc_A51D
0xa50d  ldstr    aErrormessageFi// "ErrorMessage_FileMissing"
0xa512  call     string System.Deployment.Application.Resources::GetString(string s)
0xa517  stloc.0
0xa518  br       loc_A6F0
0xa51d  ldloc.2
0xa51e  isinst   [mscorlib]System.UnauthorizedAccessException
0xa523  brfalse.s loc_A535
0xa525  ldstr    aErrormessageAu// "ErrorMessage_AuthenticationError"
0xa52a  call     string System.Deployment.Application.Resources::GetString(string s)
0xa52f  stloc.0
0xa530  br       loc_A6F0
0xa535  ldloc.2
0xa536  isinst   [mscorlib]System.IO.IOException
0xa53b  brfalse  loc_A6F0
0xa540  ldarg.0
0xa541  ldarg.1
0xa542  call     instance bool System.Deployment.Application.ApplicationActivator::IsWebExceptionInExceptionStack(class [mscorlib]System.Exception exception)
0xa547  brtrue   loc_A6F0
0xa54c  ldstr    aErrormessageDo// "ErrorMessage_DownloadIOError"
0xa551  call     string System.Deployment.Application.Resources::GetString(string s)
0xa556  stloc.0
0xa557  br       loc_A6F0
0xa55c  ldarg.1
0xa55d  isinst   System.Deployment.Application.InvalidDeploymentException
0xa562  brfalse  loc_A64C
0xa567  ldarg.1
0xa568  castclass System.Deployment.Application.InvalidDeploymentException
0xa56d  stloc.s  8
0xa56f  ldloc.s  8
0xa571  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa576  ldc.i4.s 0xE
0xa578  bne.un.s loc_A58A
0xa57a  ldstr    aErrormessageMa// "ErrorMessage_ManifestCannotBeLoaded"
0xa57f  call     string System.Deployment.Application.Resources::GetString(string s)
0xa584  stloc.0
0xa585  br       loc_A6F0
0xa58a  ldloc.s  8
0xa58c  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa591  ldc.i4.s 0xD
0xa593  beq.s    loc_A5AB
0xa595  ldloc.s  8
0xa597  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa59c  ldc.i4.s 0xF
0xa59e  beq.s    loc_A5AB
0xa5a0  ldloc.s  8
0xa5a2  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5a7  ldc.i4.s 0x10
0xa5a9  bne.un.s loc_A5BB
0xa5ab  ldstr    aErrormessageIn// "ErrorMessage_InvalidManifest"
0xa5b0  call     string System.Deployment.Application.Resources::GetString(string s)
0xa5b5  stloc.0
0xa5b6  br       loc_A6F0
0xa5bb  ldloc.s  8
0xa5bd  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5c2  ldc.i4.s 0x18
0xa5c4  beq.s    loc_A61E
0xa5c6  ldloc.s  8
0xa5c8  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5cd  ldc.i4.s 0x19
0xa5cf  beq.s    loc_A61E
0xa5d1  ldloc.s  8
0xa5d3  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5d8  ldc.i4.s 0x1A
0xa5da  beq.s    loc_A61E
0xa5dc  ldloc.s  8
0xa5de  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5e3  ldc.i4.s 0x1B
0xa5e5  beq.s    loc_A61E
0xa5e7  ldloc.s  8
0xa5e9  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5ee  ldc.i4.s 0x1C
0xa5f0  beq.s    loc_A61E
0xa5f2  ldloc.s  8
0xa5f4  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa5f9  ldc.i4.s 0x1D
0xa5fb  beq.s    loc_A61E
0xa5fd  ldloc.s  8
0xa5ff  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa604  ldc.i4.s 0x1E
0xa606  beq.s    loc_A61E
0xa608  ldloc.s  8
0xa60a  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa60f  ldc.i4.s 0x1F
0xa611  beq.s    loc_A61E
0xa613  ldloc.s  8
0xa615  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa61a  ldc.i4.s 0x20
0xa61c  bne.un.s loc_A62E
0xa61e  ldstr    aErrormessageVa// "ErrorMessage_ValidationFailed"
0xa623  call     string System.Deployment.Application.Resources::GetString(string s)
0xa628  stloc.0
0xa629  br       loc_A6F0
0xa62e  ldloc.s  8
0xa630  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa635  ldc.i4.s 0x12
0xa637  bne.un   loc_A6F0
0xa63c  ldstr    aErrormessageMa_0// "ErrorMessage_ManifestExecutionLevelNotS"...
0xa641  call     string System.Deployment.Application.Resources::GetString(string s)
0xa646  stloc.0
0xa647  br       loc_A6F0
0xa64c  ldarg.1
0xa64d  isinst   System.Deployment.Application.DeploymentException
0xa652  brfalse  loc_A6F0
0xa657  ldarg.1
0xa658  castclass System.Deployment.Application.DeploymentException
0xa65d  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa662  ldc.i4.2
0xa663  bne.un.s loc_A672
0xa665  ldstr    aErrormessageSt// "ErrorMessage_StoreError"
0xa66a  call     string System.Deployment.Application.Resources::GetString(string s)
0xa66f  stloc.0
0xa670  br.s     loc_A6F0
0xa672  ldarg.1
0xa673  castclass System.Deployment.Application.DeploymentException
0xa678  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa67d  ldc.i4.s 9
0xa67f  bne.un.s loc_A68E
0xa681  ldstr    aErrormessageCo// "ErrorMessage_ConcurrentActivationLimitE"...
0xa686  call     string System.Deployment.Application.Resources::GetString(string s)
0xa68b  stloc.0
0xa68c  br.s     loc_A6F0
0xa68e  ldarg.1
0xa68f  castclass System.Deployment.Application.DeploymentException
0xa694  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa699  ldc.i4.s 0xA
0xa69b  bne.un.s loc_A6AA
0xa69d  ldstr    aErrormessageDi// "ErrorMessage_DiskIsFull"
0xa6a2  call     string System.Deployment.Application.Resources::GetString(string s)
0xa6a7  stloc.0
0xa6a8  br.s     loc_A6F0
0xa6aa  ldarg.1
0xa6ab  castclass System.Deployment.Application.DeploymentException
0xa6b0  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa6b5  ldc.i4.s 0x16
0xa6b7  bne.un.s loc_A6C2
0xa6b9  ldarg.1
0xa6ba  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa6bf  stloc.0
0xa6c0  br.s     loc_A6F0
0xa6c2  ldarg.1
0xa6c3  castclass System.Deployment.Application.DeploymentException
0xa6c8  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa6cd  ldc.i4.s 0xB
0xa6cf  bne.un.s loc_A6DA
0xa6d1  ldarg.1
0xa6d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa6d7  stloc.0
0xa6d8  br.s     loc_A6F0
0xa6da  ldarg.1
0xa6db  castclass System.Deployment.Application.DeploymentException
0xa6e0  callvirt instance valuetype System.Deployment.Application.ExceptionTypes System.Deployment.Application.DeploymentException::get_SubType()
0xa6e5  ldc.i4.s 0x21
0xa6e7  bne.un.s loc_A6F0
0xa6e9  ldarg.1
0xa6ea  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa6ef  stloc.0
0xa6f0  call     string System.Deployment.Application.Logger::GetLogFilePath()
0xa6f5  stloc.3
0xa6f6  call     bool System.Deployment.Application.Logger::FlushCurrentThreadLogs()
0xa6fb  brtrue.s loc_A6FF
0xa6fd  ldnull
0xa6fe  stloc.3
0xa6ff  ldnull
0xa700  stloc.s  4
0xa702  ldarg.2
0xa703  brfalse.s loc_A75D
0xa705  ldstr    a0Outer1Inner2M// "{0}?outer={1}&&inner={2}&&msg={3}"
0xa70a  ldc.i4.4
0xa70b  newarr   [mscorlib]System.Object
0xa710  dup
0xa711  ldc.i4.0
0xa712  ldarg.2
0xa713  stelem.ref
0xa714  dup
0xa715  ldc.i4.1
0xa716  ldarg.1
0xa717  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xa71c  callvirt instance string [mscorlib]System.Object::ToString()
0xa721  stelem.ref
0xa722  dup
0xa723  ldc.i4.2
0xa724  ldloc.2
0xa725  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xa72a  callvirt instance string [mscorlib]System.Object::ToString()
0xa72f  stelem.ref
0xa730  dup
0xa731  ldc.i4.3
0xa732  ldloc.2
0xa733  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa738  stelem.ref
0xa739  call     string [mscorlib]System.String::Format(string, object[])
0xa73e  stloc.s  4
0xa740  ldloc.s  4
0xa742  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa747  ldc.i4   0x800
0xa74c  ble.s    loc_A75D
0xa74e  ldloc.s  4
0xa750  ldc.i4.0
0xa751  ldc.i4   0x800
0xa756  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xa75b  stloc.s  4
0xa75d  ldarg.0
0xa75e  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xa763  ldstr    aUiErrortitle// "UI_ErrorTitle"
0xa768  call     string System.Deployment.Application.Resources::GetString(string s)
0xa76d  ldloc.0
0xa76e  ldloc.3
0xa76f  ldloc.s  4
0xa771  ldloc.1
0xa772  callvirt instance void System.Deployment.Application.UserInterface::ShowError(string title, string message, string logFileLocation, string linkUrl, string linkUrlMessage)
0xa777  ret
```
