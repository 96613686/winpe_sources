# System.Windows.Xps.Packaging.XpsInterleavingPolicy::ConfirmCommited

- ea: `0x24420`
- end: `0x24471`
- name: `System.Windows.Xps.Packaging.XpsInterleavingPolicy::ConfirmCommited`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x24200`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x24420`
- `0x24480`
- `0x24610`

## string_xrefs

- `0x24447`: `ReachPackaging_DependantsNotCommitted`

## pseudocode

```c

```

## disassembly

```asm
0x24420  ldarg.0
0x24421  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.InterleavingNode> System.Windows.Xps.Packaging.XpsInterleavingPolicy::_interleavingNodes
0x24426  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.InterleavingNode>::GetEnumerator()
0x2442b  stloc.0
0x2442c  br.s     loc_24457
0x2442e  ldloca.s 0
0x24430  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.InterleavingNode>::get_Current()
0x24435  stloc.1
0x24436  ldarg.0
0x24437  ldloc.1
0x24438  call     instance bool System.Windows.Xps.Packaging.XpsInterleavingPolicy::IsPartialFlushAllowed(class System.Windows.Xps.Packaging.InterleavingNode n)
0x2443d  brtrue.s loc_24457
0x2443f  ldloc.1
0x24440  callvirt instance bool System.Windows.Xps.Packaging.InterleavingNode::get_Commited()
0x24445  brtrue.s loc_24457
0x24447  ldstr    aReachpackaging_16// "ReachPackaging_DependantsNotCommitted"
0x2444c  call     string System.Windows.Xps.SR::Get(string id)
0x24451  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x24456  throw
0x24457  ldloca.s 0
0x24459  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.InterleavingNode>::MoveNext()
0x2445e  brtrue.s loc_2442E
0x24460  leave.s  loc_24470
0x24462  ldloca.s 0
0x24464  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.InterleavingNode>
0x2446a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2446f  endfinally
0x24470  ret
```
