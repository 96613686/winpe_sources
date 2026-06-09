# NGenTask.TaskExecutive::UsageError

- ea: `0x2540`
- end: `0x2592`
- name: `NGenTask.TaskExecutive::UsageError`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x310`
- `0x25a0`

## callees

- `0x2c30`

## string_xrefs

- `0x2563`: ` This tool reads from the usage log data produced by the runtime, and triggers NGen to occur.`
- `0x2572`: `   /RuntimeWide - Parse the fusion stream of the usage logs instead of the App stream. Task runs in machine-wide mode.`
- `0x2581`: `   /Critical - Runs as a critical idle task.`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldc.i4.0
0x2541  ldarg.0
0x2542  ldarg.1
0x2543  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2548  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x254d  ldstr    a0Options// "{0} [options...]"
0x2552  call     string[] [mscorlib]System.Environment::GetCommandLineArgs()
0x2557  ldc.i4.0
0x2558  ldelem.ref
0x2559  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object)
0x255e  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x2563  ldstr    aThisToolReadsF// " This tool reads from the usage log dat"...
0x2568  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x256d  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x2572  ldstr    aRuntimewidePar// "   /RuntimeWide - Parse the fusion stre"...
0x2577  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x257c  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x2581  ldstr    aCriticalRunsAs// "   /Critical - Runs as a critical idle "...
0x2586  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x258b  ldc.i4.m1
0x258c  call     void [mscorlib]System.Environment::Exit(int32)
0x2591  ret
```
