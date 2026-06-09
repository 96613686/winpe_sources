# System.Windows.DependencyObject::ValidateSources

- ea: `0x316f0`
- end: `0x31736`
- name: `System.Windows.DependencyObject::ValidateSources`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x300d0`
- `0x34bf0`

## callees

- `0x2c100`
- `0x316f0`
- `0x338e0`
- `0x34ca0`
- `0x3d490`

## string_xrefs

- `0x3171b`: `SourcesMustBeInSameThread`

## pseudocode

```c

```

## disassembly

```asm
0x316f0  ldarg.1
0x316f1  brfalse.s loc_31735
0x316f3  ldarg.0
0x316f4  callvirt instance class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x316f9  stloc.0
0x316fa  ldc.i4.0
0x316fb  stloc.1
0x316fc  br.s     loc_3172F
0x316fe  ldarg.1
0x316ff  ldloc.1
0x31700  ldelem.ref
0x31701  callvirt instance class System.Windows.DependencyObject System.Windows.DependencySource::get_DependencyObject()
0x31706  callvirt instance class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x3170b  stloc.2
0x3170c  ldloc.2
0x3170d  ldloc.0
0x3170e  beq.s    loc_3172B
0x31710  ldarg.2
0x31711  callvirt instance bool System.Windows.Expression::get_SupportsUnboundSources()
0x31716  brfalse.s loc_3171B
0x31718  ldloc.2
0x31719  brfalse.s loc_3172B
0x3171b  ldstr    aSourcesmustbei// "SourcesMustBeInSameThread"
0x31720  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x31725  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3172a  throw
0x3172b  ldloc.1
0x3172c  ldc.i4.1
0x3172d  add
0x3172e  stloc.1
0x3172f  ldloc.1
0x31730  ldarg.1
0x31731  ldlen
0x31732  conv.i4
0x31733  blt.s    loc_316FE
0x31735  ret
```
