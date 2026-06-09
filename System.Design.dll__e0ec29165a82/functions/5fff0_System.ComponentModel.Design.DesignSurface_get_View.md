# System.ComponentModel.Design.DesignSurface::get_View

- ea: `0x5fff0`
- end: `0x6010e`
- name: `System.ComponentModel.Design.DesignSurface::get_View`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5fff0`
- `0x8ef40`

## string_xrefs

- `0x6007b`: `DesignSurfaceNoRootComponent`
- `0x6008c`: `DesignSurfaceNoRootComponent`

## pseudocode

```c

```

## disassembly

```asm
0x5fff0  ldarg.0
0x5fff1  ldfld    class System.ComponentModel.Design.DesignerHost System.ComponentModel.Design.DesignSurface::_host
0x5fff6  brtrue.s loc_60004
0x5fff8  ldarg.0
0x5fff9  callvirt instance string [mscorlib]System.Object::ToString()
0x5fffe  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x60003  throw
0x60004  ldarg.0
0x60005  ldfld    class System.ComponentModel.Design.DesignerHost System.ComponentModel.Design.DesignSurface::_host
0x6000a  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x6000f  stloc.1
0x60010  ldloc.1
0x60011  brtrue   loc_60098
0x60016  ldarg.0
0x60017  ldfld    class [mscorlib]System.Collections.ICollection System.ComponentModel.Design.DesignSurface::_loadErrors
0x6001c  brfalse.s loc_6007B
0x6001e  ldarg.0
0x6001f  ldfld    class [mscorlib]System.Collections.ICollection System.ComponentModel.Design.DesignSurface::_loadErrors
0x60024  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x60029  stloc.s  4
0x6002b  br.s     loc_6005B
0x6002d  ldloc.s  4
0x6002f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x60034  stloc.s  5
0x60036  ldloc.s  5
0x60038  isinst   [mscorlib]System.Exception
0x6003d  stloc.0
0x6003e  ldloc.0
0x6003f  brfalse.s loc_6004E
0x60041  ldloc.0
0x60042  callvirt instance string [mscorlib]System.Exception::get_Message()
0x60047  ldloc.0
0x60048  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x6004d  throw
0x6004e  ldloc.s  5
0x60050  callvirt instance string [mscorlib]System.Object::ToString()
0x60055  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6005a  throw
0x6005b  ldloc.s  4
0x6005d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x60062  brtrue.s loc_6002D
0x60064  leave.s  loc_6007B
0x60066  ldloc.s  4
0x60068  isinst   [mscorlib]System.IDisposable
0x6006d  stloc.s  6
0x6006f  ldloc.s  6
0x60071  brfalse.s loc_6007A
0x60073  ldloc.s  6
0x60075  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6007a  endfinally
0x6007b  ldstr    aDesignsurfacen// "DesignSurfaceNoRootComponent"
0x60080  call     string System.Design.SR::GetString(string name)
0x60085  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6008a  stloc.0
0x6008b  ldloc.0
0x6008c  ldstr    aDesignsurfacen// "DesignSurfaceNoRootComponent"
0x60091  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x60096  ldloc.0
0x60097  throw
0x60098  ldarg.0
0x60099  ldfld    class System.ComponentModel.Design.DesignerHost System.ComponentModel.Design.DesignSurface::_host
0x6009e  ldloc.1
0x6009f  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x600a4  isinst   [System]System.ComponentModel.Design.IRootDesigner
0x600a9  stloc.2
0x600aa  ldloc.2
0x600ab  brtrue.s loc_600CA
0x600ad  ldstr    aDesignsurfaced// "DesignSurfaceDesignerNotLoaded"
0x600b2  call     string System.Design.SR::GetString(string name)
0x600b7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x600bc  stloc.0
0x600bd  ldloc.0
0x600be  ldstr    aDesignsurfaced// "DesignSurfaceDesignerNotLoaded"
0x600c3  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x600c8  ldloc.0
0x600c9  throw
0x600ca  ldloc.2
0x600cb  callvirt instance valuetype [System]System.ComponentModel.Design.ViewTechnology[] [System]System.ComponentModel.Design.IRootDesigner::get_SupportedTechnologies()
0x600d0  stloc.3
0x600d1  ldloc.3
0x600d2  stloc.s  7
0x600d4  ldc.i4.0
0x600d5  stloc.s  8
0x600d7  br.s     loc_600E9
0x600d9  ldloc.s  7
0x600db  ldloc.s  8
0x600dd  ldelem.i4
0x600de  stloc.s  9
0x600e0  ldloc.2
0x600e1  ldloc.s  9
0x600e3  callvirt instance object [System]System.ComponentModel.Design.IRootDesigner::GetView(valuetype [System]System.ComponentModel.Design.ViewTechnology)
0x600e8  ret
0x600e9  ldloc.s  8
0x600eb  ldloc.s  7
0x600ed  ldlen
0x600ee  conv.i4
0x600ef  blt.s    loc_600D9
0x600f1  ldstr    aDesignsurfacen_0// "DesignSurfaceNoSupportedTechnology"
0x600f6  call     string System.Design.SR::GetString(string name)
0x600fb  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x60100  stloc.0
0x60101  ldloc.0
0x60102  ldstr    aDesignsurfacen_0// "DesignSurfaceNoSupportedTechnology"
0x60107  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6010c  ldloc.0
0x6010d  throw
```
