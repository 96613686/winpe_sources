# NGenTask.ExcludeList::SetFilename

- ea: `0x220`
- end: `0x2ac`
- name: `NGenTask.ExcludeList::SetFilename`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x10`

## callees

- `0x220`
- `0x1cf0`
- `0x2c60`

## string_xrefs

- `0x299`: `Unable to set path for NGenDisable.txt`

## pseudocode

```c

```

## disassembly

```asm
0x220  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x225  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x22a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x22f  stloc.0
0x230  ldarg.1
0x231  brfalse.s loc_237
0x233  ldloc.0
0x234  stloc.1
0x235  br.s     loc_281
0x237  ldloc.0
0x238  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x23d  stloc.2
0x23e  ldloc.2
0x23f  call     string NGenTask.TaskExecutive::ComputeShortVersionString(string version)
0x244  stloc.3
0x245  ldloc.3
0x246  brtrue.s loc_24A
0x248  ldloc.2
0x249  stloc.3
0x24a  ldstr    aMicrosoftClr// "Microsoft\\CLR_"
0x24f  ldloc.3
0x250  call     string [mscorlib]System.String::Concat(string, string)
0x255  stloc.s  4
0x257  ldstr    aLocalappdata// "LOCALAPPDATA"
0x25c  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x261  stloc.1
0x262  ldloc.1
0x263  brtrue.s loc_269
0x265  ldloc.0
0x266  stloc.1
0x267  br.s     loc_281
0x269  ldloc.1
0x26a  ldloc.s  4
0x26c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x271  stloc.1
0x272  ldloc.1
0x273  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x278  brtrue.s loc_281
0x27a  ldloc.1
0x27b  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x280  pop
0x281  ldarg.0
0x282  ldloc.1
0x283  ldstr    aNgendisableTxt// "NGenDisable.txt"
0x288  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28d  stfld    string NGenTask.ExcludeList::filename
0x292  leave.s  loc_2AB
0x294  stloc.s  5
0x296  ldc.i4.0
0x297  ldloc.s  5
0x299  ldstr    aUnableToSetPat// "Unable to set path for NGenDisable.txt"
0x29e  ldc.i4.0
0x29f  newarr   [mscorlib]System.Object
0x2a4  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2a9  leave.s  loc_2AB
0x2ab  ret
```
