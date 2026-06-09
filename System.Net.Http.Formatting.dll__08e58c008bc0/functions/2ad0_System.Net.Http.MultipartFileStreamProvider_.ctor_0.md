# System.Net.Http.MultipartFileStreamProvider::.ctor_0

- ea: `0x2ad0`
- end: `0x2b29`
- name: `System.Net.Http.MultipartFileStreamProvider::.ctor_0`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x2ac0`
- `0x2c40`

## callees

- `0xad0`
- `0x2ad0`
- `0xb3c0`
- `0xb410`

## string_xrefs

- `0x2aef`: `rootPath`

## pseudocode

```c

```

## disassembly

```asm
0x2ad0  ldarg.0
0x2ad1  ldc.i4   0x1000
0x2ad6  stfld    int32 System.Net.Http.MultipartFileStreamProvider::_bufferSize
0x2adb  ldarg.0
0x2adc  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.MultipartFileData>::.ctor()
0x2ae1  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Net.Http.MultipartFileData> System.Net.Http.MultipartFileStreamProvider::_fileData
0x2ae6  ldarg.0
0x2ae7  call     instance void System.Net.Http.MultipartStreamProvider::.ctor()
0x2aec  ldarg.1
0x2aed  brtrue.s loc_2AFA
0x2aef  ldstr    aRootpath// "rootPath"
0x2af4  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x2af9  throw
0x2afa  ldarg.2
0x2afb  ldc.i4.1
0x2afc  bge.s    loc_2B15
0x2afe  ldstr    aBuffersize// "bufferSize"
0x2b03  ldarg.2
0x2b04  box      [mscorlib]System.Int32
0x2b09  ldc.i4.1
0x2b0a  box      [mscorlib]System.Int32
0x2b0f  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x2b14  throw
0x2b15  ldarg.0
0x2b16  ldarg.1
0x2b17  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x2b1c  stfld    string System.Net.Http.MultipartFileStreamProvider::_rootPath
0x2b21  ldarg.0
0x2b22  ldarg.2
0x2b23  stfld    int32 System.Net.Http.MultipartFileStreamProvider::_bufferSize
0x2b28  ret
```
