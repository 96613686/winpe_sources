# System.ComponentModel.Design.DesignSurface::OnLoaded

- ea: `0x60730`
- end: `0x60797`
- name: `System.ComponentModel.Design.DesignSurface::OnLoaded`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x5f5a0`

## callees

- `0x60730`
- `0x607a0`
- `0x61550`
- `0x8ef40`

## string_xrefs

- `0x60756`: `DesignSurfaceNoRootComponent`
- `0x60767`: `DesignSurfaceNoRootComponent`

## pseudocode

```c

```

## disassembly

```asm
0x60730  ldarg.0
0x60731  ldarg.1
0x60732  stfld    bool System.ComponentModel.Design.DesignSurface::_loaded
0x60737  ldarg.0
0x60738  ldarg.2
0x60739  stfld    class [mscorlib]System.Collections.ICollection System.ComponentModel.Design.DesignSurface::_loadErrors
0x6073e  ldarg.1
0x6073f  brfalse.s loc_60789
0x60741  ldarg.0
0x60742  ldfld    class System.ComponentModel.Design.DesignerHost System.ComponentModel.Design.DesignSurface::_host
0x60747  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x6074c  stloc.0
0x6074d  ldloc.0
0x6074e  brtrue.s loc_60789
0x60750  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x60755  stloc.1
0x60756  ldstr    aDesignsurfacen// "DesignSurfaceNoRootComponent"
0x6075b  call     string System.Design.SR::GetString(string name)
0x60760  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x60765  stloc.2
0x60766  ldloc.2
0x60767  ldstr    aDesignsurfacen// "DesignSurfaceNoRootComponent"
0x6076c  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x60771  ldloc.1
0x60772  ldloc.2
0x60773  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x60778  pop
0x60779  ldarg.2
0x6077a  brfalse.s loc_60783
0x6077c  ldloc.1
0x6077d  ldarg.2
0x6077e  callvirt instance void [mscorlib]System.Collections.ArrayList::AddRange(class [mscorlib]System.Collections.ICollection)
0x60783  ldloc.1
0x60784  starg.s  2
0x60786  ldc.i4.0
0x60787  starg.s  1
0x60789  ldarg.0
0x6078a  ldarg.1
0x6078b  ldarg.2
0x6078c  newobj   instance void System.ComponentModel.Design.LoadedEventArgs::.ctor(bool succeeded, class [mscorlib]System.Collections.ICollection errors)
0x60791  callvirt instance void System.ComponentModel.Design.DesignSurface::OnLoaded(class System.ComponentModel.Design.LoadedEventArgs e)
0x60796  ret
```
