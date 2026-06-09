# System.Xaml.XamlBackgroundReader::StartThread_0

- ea: `0x70a0`
- end: `0x70e9`
- name: `System.Xaml.XamlBackgroundReader::StartThread_0`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x7090`

## callees

- `0x70a0`
- `0x11f20`

## string_xrefs

- `0x70a8`: `ThreadAlreadyStarted`

## pseudocode

```c

```

## disassembly

```asm
0x70a0  ldarg.0
0x70a1  ldfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x70a6  brfalse.s loc_70B8
0x70a8  ldstr    aThreadalreadys// "ThreadAlreadyStarted"
0x70ad  call     string System.Xaml.SR::Get(string id)
0x70b2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x70b7  throw
0x70b8  ldarg.0
0x70b9  ldftn    instance void System.Xaml.XamlBackgroundReader::XamlReaderThreadStart(object none)
0x70bf  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0x70c4  stloc.0
0x70c5  ldarg.0
0x70c6  ldloc.0
0x70c7  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0x70cc  stfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x70d1  ldarg.0
0x70d2  ldfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x70d7  ldarg.1
0x70d8  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0x70dd  ldarg.0
0x70de  ldfld    class [mscorlib]System.Threading.Thread System.Xaml.XamlBackgroundReader::_thread
0x70e3  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x70e8  ret
```
