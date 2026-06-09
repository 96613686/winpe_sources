# NGenTask.Program::Main

- ea: `0x2990`
- end: `0x29eb`
- name: `NGenTask.Program::Main`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c0`
- `0x2960`
- `0x2990`
- `0x29f0`
- `0x2b10`
- `0x2c30`
- `0x3220`

## string_xrefs

- `0x299e`: `NGen Task starting, command line: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2990  .entrypoint
0x2991  call     unsigned int32 NGenTask.Win32Native::WerSetFlags(unsigned int32 dwFlags)
0x2996  pop
0x2997  ldarg.0
0x2998  call     void NGenTask.Logger::Init(string[] args)
0x299d  ldc.i4.m1
0x299e  ldstr    aNgenTaskStarti// "NGen Task starting, command line: {0}"
0x29a3  ldc.i4.1
0x29a4  newarr   [mscorlib]System.Object
0x29a9  dup
0x29aa  ldc.i4.0
0x29ab  call     string [mscorlib]System.Environment::get_CommandLine()
0x29b0  stelem.ref
0x29b1  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x29b6  ldarg.0
0x29b7  stloc.0
0x29b8  ldc.i4.0
0x29b9  stloc.1
0x29ba  br.s     loc_29D9
0x29bc  ldloc.0
0x29bd  ldloc.1
0x29be  ldelem.ref
0x29bf  stloc.2
0x29c0  ldloc.2
0x29c1  ldstr    aRuntimewide// "/RuntimeWide"
0x29c6  ldc.i4.5
0x29c7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x29cc  brfalse.s loc_29D5
0x29ce  call     void NGenTask.Program::LockDependentFiles()
0x29d3  br.s     loc_29DF
0x29d5  ldloc.1
0x29d6  ldc.i4.1
0x29d7  add
0x29d8  stloc.1
0x29d9  ldloc.1
0x29da  ldloc.0
0x29db  ldlen
0x29dc  conv.i4
0x29dd  blt.s    loc_29BC
0x29df  newobj   instance void NGenTask.TaskExecutive::.ctor()
0x29e4  ldarg.0
0x29e5  call     instance int32 NGenTask.TaskExecutive::Run(string[] args)
0x29ea  ret
```
