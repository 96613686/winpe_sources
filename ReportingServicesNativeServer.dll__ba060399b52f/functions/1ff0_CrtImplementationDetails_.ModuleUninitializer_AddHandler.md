# <CrtImplementationDetails>.ModuleUninitializer::AddHandler

- ea: `0x1ff0`
- end: `0x2026`
- name: `<CrtImplementationDetails>.ModuleUninitializer::AddHandler`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x3d0`

## callees

- `0x1ff0`

## pseudocode

```c

```

## disassembly

```asm
0x1ff0  ldc.i4.0
0x1ff1  stloc.0
0x1ff2  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x1ff7  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x1ffc  ldsfld   object <CrtImplementationDetails>.ModuleUninitializer::lock
0x2001  ldloca.s 0
0x2003  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2008  ldarg.1
0x2009  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareDelegate(class [mscorlib]System.Delegate)
0x200e  ldarg.0
0x200f  ldarg.1
0x2010  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x2015  leave.s  loc_2025
0x2017  ldloc.0
0x2018  brfalse.s loc_2024
0x201a  ldsfld   object <CrtImplementationDetails>.ModuleUninitializer::lock
0x201f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2024  endfinally
0x2025  ret
```
