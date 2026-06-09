# Microsoft.ManagementConsole.ViewDescriptionCollection::OnItemsRemoved

- ea: `0x8df0`
- end: `0x8e4e`
- name: `Microsoft.ManagementConsole.ViewDescriptionCollection::OnItemsRemoved`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8df0`
- `0x8e70`
- `0x9980`
- `0x9a70`

## pseudocode

```c

```

## disassembly

```asm
0x8df0  ldarg.2
0x8df1  stloc.2
0x8df2  ldc.i4.0
0x8df3  stloc.3
0x8df4  br.s     loc_8E2B
0x8df6  ldloc.2
0x8df7  ldloc.3
0x8df8  ldelem.ref
0x8df9  castclass Microsoft.ManagementConsole.ViewDescription
0x8dfe  stloc.0
0x8dff  ldarg.0
0x8e00  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ManagementConsole.ViewDescriptionCollection::_idToViewDescription
0x8e05  ldloc.0
0x8e06  callvirt instance int32 Microsoft.ManagementConsole.ViewDescription::get_Id()
0x8e0b  box      [mscorlib]System.Int32
0x8e10  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x8e15  ldloc.0
0x8e16  ldarg.0
0x8e17  ldftn    instance void Microsoft.ManagementConsole.ViewDescriptionCollection::ItemChanged(object sender, class [mscorlib]System.EventArgs e)
0x8e1d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8e22  callvirt instance void Microsoft.ManagementConsole.ViewDescription::remove_Changed(class [mscorlib]System.EventHandler value)
0x8e27  ldloc.3
0x8e28  ldc.i4.1
0x8e29  add
0x8e2a  stloc.3
0x8e2b  ldloc.3
0x8e2c  ldloc.2
0x8e2d  ldlen
0x8e2e  conv.i4
0x8e2f  blt.s    loc_8DF6
0x8e31  ldarg.2
0x8e32  ldlen
0x8e33  conv.i4
0x8e34  newarr   Microsoft.ManagementConsole.ViewDescription
0x8e39  stloc.1
0x8e3a  ldarg.2
0x8e3b  ldloc.1
0x8e3c  ldarg.2
0x8e3d  ldlen
0x8e3e  conv.i4
0x8e3f  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x8e44  ldarg.0
0x8e45  ldarg.1
0x8e46  ldloc.1
0x8e47  ldc.i4.1
0x8e48  call     instance void Microsoft.ManagementConsole.ViewDescriptionCollection::Notify(int32 index, class Microsoft.ManagementConsole.ViewDescription[] items, valuetype Microsoft.ManagementConsole.ViewDescriptionCollectionChangeType action)
0x8e4d  ret
```
