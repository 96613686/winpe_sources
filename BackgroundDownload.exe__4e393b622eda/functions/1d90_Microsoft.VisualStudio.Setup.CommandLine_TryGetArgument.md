# Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument

- ea: `0x1d90`
- end: `0x1de5`
- name: `Microsoft.VisualStudio.Setup.CommandLine::TryGetArgument`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1df0`

## callees

- `0x1d50`
- `0x1d90`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldarg.0
0x1d91  brtrue.s loc_1D9E
0x1d93  ldstr    aArgs// "args"
0x1d98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d9d  throw
0x1d9e  ldarg.1
0x1d9f  ldind.i4
0x1da0  ldc.i4.0
0x1da1  bge.s    loc_1DAE
0x1da3  ldstr    aI// "i"
0x1da8  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1dad  throw
0x1dae  ldarg.1
0x1daf  ldind.i4
0x1db0  ldarg.0
0x1db1  callvirt instance int32 class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<string>::get_Count()
0x1db6  ldc.i4.1
0x1db7  sub
0x1db8  bge.s    loc_1DE0
0x1dba  ldarg.0
0x1dbb  ldarg.1
0x1dbc  ldind.i4
0x1dbd  ldc.i4.1
0x1dbe  add
0x1dbf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string>::get_Item(!!T0)
0x1dc4  ldloca.s 0
0x1dc6  call     bool Microsoft.VisualStudio.Setup.CommandLine::TryGetParameter(string arg, [out] string& param)
0x1dcb  brtrue.s loc_1DE0
0x1dcd  ldarg.2
0x1dce  ldarg.0
0x1dcf  ldarg.1
0x1dd0  ldarg.1
0x1dd1  ldind.i4
0x1dd2  ldc.i4.1
0x1dd3  add
0x1dd4  stloc.1
0x1dd5  ldloc.1
0x1dd6  stind.i4
0x1dd7  ldloc.1
0x1dd8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string>::get_Item(!!T0)
0x1ddd  stind.ref
0x1dde  ldc.i4.1
0x1ddf  ret
0x1de0  ldarg.2
0x1de1  ldnull
0x1de2  stind.ref
0x1de3  ldc.i4.0
0x1de4  ret
```
