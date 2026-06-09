# Microsoft.VisualStudio.Setup.DismUtility::InstallMSU

- ea: `0x1ca40`
- end: `0x1ca7d`
- name: `Microsoft.VisualStudio.Setup.DismUtility::InstallMSU`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6cf10`

## callees

- `0x1cb40`

## string_xrefs

- `0x1ca41`: `msuPath`
- `0x1ca53`: `/online /quiet /norestart /add-package /packagepath:"`
- `0x1ca5f`: `" /logPath:"`

## pseudocode

```c

```

## disassembly

```asm
0x1ca40  ldarg.0
0x1ca41  ldstr    aMsupath// "msuPath"
0x1ca46  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1ca4b  ldc.i4.5
0x1ca4c  newarr   [mscorlib]System.String
0x1ca51  dup
0x1ca52  ldc.i4.0
0x1ca53  ldstr    aOnlineQuietNor// "/online /quiet /norestart /add-package "...
0x1ca58  stelem.ref
0x1ca59  dup
0x1ca5a  ldc.i4.1
0x1ca5b  ldarg.0
0x1ca5c  stelem.ref
0x1ca5d  dup
0x1ca5e  ldc.i4.2
0x1ca5f  ldstr    aLogpath_0// "\" /logPath:\""
0x1ca64  stelem.ref
0x1ca65  dup
0x1ca66  ldc.i4.3
0x1ca67  ldarg.1
0x1ca68  stelem.ref
0x1ca69  dup
0x1ca6a  ldc.i4.4
0x1ca6b  ldstr    aLoglevel4// "\" /LogLevel:4"
0x1ca70  stelem.ref
0x1ca71  call     string [mscorlib]System.String::Concat(string[])
0x1ca76  ldarg.2
0x1ca77  call     class Microsoft.VisualStudio.Setup.Result Microsoft.VisualStudio.Setup.DismUtility::Install(string arguments, class [mscorlib]System.IServiceProvider serviceProvider)
0x1ca7c  ret
```
