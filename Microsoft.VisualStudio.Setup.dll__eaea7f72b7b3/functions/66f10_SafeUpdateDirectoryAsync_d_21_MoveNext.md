# <SafeUpdateDirectoryAsync>d__21::MoveNext

- ea: `0x66f10`
- end: `0x67889`
- name: `<SafeUpdateDirectoryAsync>d__21::MoveNext`
- size: `2425`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x6dc0`
- `0x6e10`
- `0x72f0`
- `0x7330`
- `0x7360`
- `0x101b0`
- `0x11090`
- `0x19dd0`
- `0x66f10`

## string_xrefs

- `0x66fbb`: `Attempt {0} updating {1} with {2}`
- `0x670f1`: `Moving old source directory {0} to {1}`
- `0x67135`: `{0} already exists, deleting before moving {1} to {0}`
- `0x67287`: `Failed to move old source directory: {0}, error: {1}`
- `0x673d8`: `Copying: {0}, destination: {1}`
- `0x674b7`: `Failed to copy the new content from {0} to {1}: {2}`
- `0x67714`: `Failed to delete directory: {0}, error: {1}`
- `0x677c4`: `Failed to hide directory: {0}, error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x66f10  ldarg.0
0x66f11  ldfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x66f16  stloc.0
0x66f17  ldarg.0
0x66f18  ldfld    class Microsoft.VisualStudio.Setup.Copier <SafeUpdateDirectoryAsync>d__21::<>4__this
0x66f1d  stloc.1
0x66f1e  ldloc.0
0x66f1f  switch   loc_6702B, loc_67096, loc_670D6, loc_670D6, loc_67312, loc_6738E, loc_673C4, loc_67532, loc_675AA, loc_67627, loc_6765D, loc_67737
0x66f54  ldarg.0
0x66f55  ldfld    string <SafeUpdateDirectoryAsync>d__21::source
0x66f5a  ldstr    aSource// "source"
0x66f5f  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x66f64  ldarg.0
0x66f65  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x66f6a  ldstr    aDestination// "destination"
0x66f6f  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x66f74  ldarg.0
0x66f75  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <SafeUpdateDirectoryAsync>d__21::cancellationToken
0x66f7a  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x66f7f  ldarg.0
0x66f80  ldarg.0
0x66f81  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x66f86  ldstr    aOld// ".old"
0x66f8b  call     string [mscorlib]System.String::Concat(string, string)
0x66f90  stfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x66f95  ldarg.0
0x66f96  ldnull
0x66f97  stfld    class [mscorlib]System.Exception <SafeUpdateDirectoryAsync>d__21::<lastException>5__3
0x66f9c  ldarg.0
0x66f9d  ldc.i4.0
0x66f9e  stfld    bool <SafeUpdateDirectoryAsync>d__21::<updateDestinationSuccessful>5__4
0x66fa3  ldarg.0
0x66fa4  ldc.i4.0
0x66fa5  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<i>5__5
0x66faa  br       loc_6780B
0x66faf  ldloc.1
0x66fb0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x66fb5  dup
0x66fb6  brtrue.s loc_66FBB
0x66fb8  pop
0x66fb9  br.s     loc_66FED
0x66fbb  ldstr    aAttempt0Updati// "Attempt {0} updating {1} with {2}"
0x66fc0  ldc.i4.3
0x66fc1  newarr   [mscorlib]System.Object
0x66fc6  dup
0x66fc7  ldc.i4.0
0x66fc8  ldarg.0
0x66fc9  ldfld    int32 <SafeUpdateDirectoryAsync>d__21::<i>5__5
0x66fce  ldc.i4.1
0x66fcf  add
0x66fd0  box      [mscorlib]System.Int32
0x66fd5  stelem.ref
0x66fd6  dup
0x66fd7  ldc.i4.1
0x66fd8  ldarg.0
0x66fd9  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x66fde  stelem.ref
0x66fdf  dup
0x66fe0  ldc.i4.2
0x66fe1  ldarg.0
0x66fe2  ldfld    string <SafeUpdateDirectoryAsync>d__21::source
0x66fe7  stelem.ref
0x66fe8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x66fed  ldloc.1
0x66fee  ldarg.0
0x66fef  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <SafeUpdateDirectoryAsync>d__21::relatedServices
0x66ff4  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Copier::ShutdownServicesAsync(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> services)
0x66ff9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x66ffe  stloc.2
0x66fff  ldloca.s 2
0x67001  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x67006  brtrue.s loc_67047
0x67008  ldarg.0
0x67009  ldc.i4.0
0x6700a  dup
0x6700b  stloc.0
0x6700c  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x67011  ldarg.0
0x67012  ldloc.2
0x67013  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__1
0x67018  ldarg.0
0x67019  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SafeUpdateDirectoryAsync>d__21::<>t__builder
0x6701e  ldloca.s 2
0x67020  ldarg.0
0x67021  call     T0x2B0002D4
0x67026  leave    loc_67888
0x6702b  ldarg.0
0x6702c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__1
0x67031  stloc.2
0x67032  ldarg.0
0x67033  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__1
0x67038  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x6703e  ldarg.0
0x6703f  ldc.i4.m1
0x67040  dup
0x67041  stloc.0
0x67042  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x67047  ldloca.s 2
0x67049  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x6704e  ldloc.1
0x6704f  ldarg.0
0x67050  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x67055  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Copier::ShutdownRunningProcesses(string directory)
0x6705a  ldc.i4.0
0x6705b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x67060  stloc.s  4
0x67062  ldloca.s 4
0x67064  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x67069  stloc.3
0x6706a  ldloca.s 3
0x6706c  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x67071  brtrue.s loc_670B2
0x67073  ldarg.0
0x67074  ldc.i4.1
0x67075  dup
0x67076  stloc.0
0x67077  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x6707c  ldarg.0
0x6707d  ldloc.3
0x6707e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x67083  ldarg.0
0x67084  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SafeUpdateDirectoryAsync>d__21::<>t__builder
0x67089  ldloca.s 3
0x6708b  ldarg.0
0x6708c  call     T0x2B0002D5
0x67091  leave    loc_67888
0x67096  ldarg.0
0x67097  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x6709c  stloc.3
0x6709d  ldarg.0
0x6709e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x670a3  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x670a9  ldarg.0
0x670aa  ldc.i4.m1
0x670ab  dup
0x670ac  stloc.0
0x670ad  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x670b2  ldloca.s 3
0x670b4  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x670b9  ldloc.1
0x670ba  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x670bf  ldarg.0
0x670c0  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x670c5  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x670ca  brfalse  loc_673BD
0x670cf  ldarg.0
0x670d0  ldc.i4.0
0x670d1  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>7__wrap6
0x670d6  nop
0x670d7  ldloc.0
0x670d8  ldc.i4.2
0x670d9  beq      loc_671A6
0x670de  ldloc.0
0x670df  ldc.i4.3
0x670e0  beq      loc_6721E
0x670e5  ldloc.1
0x670e6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x670eb  dup
0x670ec  brtrue.s loc_670F1
0x670ee  pop
0x670ef  br.s     loc_67113
0x670f1  ldstr    aMovingOldSourc// "Moving old source directory {0} to {1}"
0x670f6  ldc.i4.2
0x670f7  newarr   [mscorlib]System.Object
0x670fc  dup
0x670fd  ldc.i4.0
0x670fe  ldarg.0
0x670ff  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x67104  stelem.ref
0x67105  dup
0x67106  ldc.i4.1
0x67107  ldarg.0
0x67108  ldfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x6710d  stelem.ref
0x6710e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x67113  ldloc.1
0x67114  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x67119  ldarg.0
0x6711a  ldfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x6711f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x67124  brfalse  loc_671C9
0x67129  ldloc.1
0x6712a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x6712f  dup
0x67130  brtrue.s loc_67135
0x67132  pop
0x67133  br.s     loc_67157
0x67135  ldstr    a0AlreadyExists// "{0} already exists, deleting before mov"...
0x6713a  ldc.i4.2
0x6713b  newarr   [mscorlib]System.Object
0x67140  dup
0x67141  ldc.i4.0
0x67142  ldarg.0
0x67143  ldfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x67148  stelem.ref
0x67149  dup
0x6714a  ldc.i4.1
0x6714b  ldarg.0
0x6714c  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x67151  stelem.ref
0x67152  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x67157  ldloc.1
0x67158  ldarg.0
0x67159  ldfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x6715e  ldc.i4.0
0x6715f  ldarg.0
0x67160  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SafeUpdateDirectoryAsync>d__21::cancellationToken
0x67165  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Copier::DeleteDirectoryAsync(string path, [opt] bool rebootOK, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x6716a  ldc.i4.0
0x6716b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x67170  stloc.s  4
0x67172  ldloca.s 4
0x67174  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x67179  stloc.3
0x6717a  ldloca.s 3
0x6717c  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x67181  brtrue.s loc_671C2
0x67183  ldarg.0
0x67184  ldc.i4.2
0x67185  dup
0x67186  stloc.0
0x67187  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x6718c  ldarg.0
0x6718d  ldloc.3
0x6718e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x67193  ldarg.0
0x67194  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SafeUpdateDirectoryAsync>d__21::<>t__builder
0x67199  ldloca.s 3
0x6719b  ldarg.0
0x6719c  call     T0x2B0002D5
0x671a1  leave    loc_67888
0x671a6  ldarg.0
0x671a7  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x671ac  stloc.3
0x671ad  ldarg.0
0x671ae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x671b3  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x671b9  ldarg.0
0x671ba  ldc.i4.m1
0x671bb  dup
0x671bc  stloc.0
0x671bd  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x671c2  ldloca.s 3
0x671c4  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x671c9  ldloc.1
0x671ca  ldarg.0
0x671cb  ldfld    string <SafeUpdateDirectoryAsync>d__21::destination
0x671d0  ldarg.0
0x671d1  ldfld    string <SafeUpdateDirectoryAsync>d__21::<oldTempDestinationDirectory>5__2
0x671d6  ldc.i4.1
0x671d7  ldarg.0
0x671d8  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SafeUpdateDirectoryAsync>d__21::cancellationToken
0x671dd  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Copier::MoveDirectoryAsync(string source, string destination, [opt] bool atomicMove, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x671e2  ldc.i4.0
0x671e3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x671e8  stloc.s  4
0x671ea  ldloca.s 4
0x671ec  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x671f1  stloc.3
0x671f2  ldloca.s 3
0x671f4  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x671f9  brtrue.s loc_6723A
0x671fb  ldarg.0
0x671fc  ldc.i4.3
0x671fd  dup
0x671fe  stloc.0
0x671ff  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x67204  ldarg.0
0x67205  ldloc.3
0x67206  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x6720b  ldarg.0
0x6720c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SafeUpdateDirectoryAsync>d__21::<>t__builder
0x67211  ldloca.s 3
0x67213  ldarg.0
0x67214  call     T0x2B0002D5
0x67219  leave    loc_67888
0x6721e  ldarg.0
0x6721f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x67224  stloc.3
0x67225  ldarg.0
0x67226  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SafeUpdateDirectoryAsync>d__21::<>u__2
0x6722b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x67231  ldarg.0
0x67232  ldc.i4.m1
0x67233  dup
0x67234  stloc.0
0x67235  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>1__state
0x6723a  ldloca.s 3
0x6723c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x67241  leave.s  loc_67256
0x67243  stloc.s  5
0x67245  ldarg.0
0x67246  ldloc.s  5
0x67248  stfld    object <SafeUpdateDirectoryAsync>d__21::<>7__wrap5
0x6724d  ldarg.0
0x6724e  ldc.i4.1
0x6724f  stfld    int32 <SafeUpdateDirectoryAsync>d__21::<>7__wrap6
0x67254  leave.s  loc_67256
0x67256  ldarg.0
0x67257  ldfld    int32 <SafeUpdateDirectoryAsync>d__21::<>7__wrap6
  ... truncated ...
```
