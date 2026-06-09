# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::DeleteOldUploadedFiles

- ea: `0x9ea0`
- end: `0x9f17`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.FormDataFirstMultipartFormDataStreamProvider::DeleteOldUploadedFiles`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e70`

## callees

- `0x9ea0`
- `0xeff0`

## pseudocode

```c

```

## disassembly

```asm
0x9ea0  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x9ea5  stloc.0
0x9ea6  ldloc.0
0x9ea7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9eac  ldc.r8   10.0
0x9eb5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0x9eba  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x9ebf  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::deleteThreshold
0x9ec4  ldarg.0
0x9ec5  call     instance string [System.Net.Http.Formatting]System.Net.Http.MultipartFileStreamProvider::get_RootPath()
0x9eca  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x9ecf  ldstr    aPortalupload_0// "PortalUpload_*"
0x9ed4  call     instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x9ed9  ldloc.0
0x9eda  ldftn    instance bool <>c__DisplayClass17_0::<DeleteOldUploadedFiles>b__0(class [mscorlib]System.IO.FileInfo fileInfo)
0x9ee0  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.FileInfo, bool>::.ctor(object, native int)
0x9ee5  call     T0x2B0000DB
0x9eea  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.FileInfo>::GetEnumerator()
0x9eef  stloc.1
0x9ef0  br.s     loc_9F02
0x9ef2  ldloc.1
0x9ef3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.FileInfo>::get_Current()
0x9ef8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x9efd  call     void [mscorlib]System.IO.File::Delete(string)
0x9f02  ldloc.1
0x9f03  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9f08  brtrue.s loc_9EF2
0x9f0a  leave.s  loc_9F16
0x9f0c  ldloc.1
0x9f0d  brfalse.s loc_9F15
0x9f0f  ldloc.1
0x9f10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9f15  endfinally
0x9f16  ret
```
