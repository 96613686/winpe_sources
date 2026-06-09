# Microsoft.Internal.GDIExporter.FontInstallInfo::Equals

- ea: `0x22b10`
- end: `0x22b62`
- name: `Microsoft.Internal.GDIExporter.FontInstallInfo::Equals`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22cb0`

## callees

- `0x22820`
- `0x22880`
- `0x229c0`
- `0x22b10`
- `0x22c40`

## pseudocode

```c

```

## disassembly

```asm
0x22b10  ldarg.2
0x22b11  ldnull
0x22b12  bne.un.s loc_22B17
0x22b14  ldc.i4.0
0x22b15  br.s     loc_22B18
0x22b17  ldc.i4.1
0x22b18  stloc.2
0x22b19  ldloc.2
0x22b1a  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x22b1f  ldarg.0
0x22b20  ldfld    class [System]System.Uri Microsoft.Internal.GDIExporter.FontInstallInfo::_uri
0x22b25  ldarg.2
0x22b26  ldfld    class [System]System.Uri Microsoft.Internal.GDIExporter.FontInstallInfo::_uri
0x22b2b  callvirt instance bool [System]System.Uri::Equals(object)
0x22b30  brfalse.s loc_22B34
0x22b32  ldc.i4.1
0x22b33  ret
0x22b34  ldarg.2
0x22b35  ldfld    class [System]System.Uri Microsoft.Internal.GDIExporter.FontInstallInfo::_uri
0x22b3a  ldarg.2
0x22b3b  ldfld    int32 Microsoft.Internal.GDIExporter.FontInstallInfo::_streamLength
0x22b40  newobj   instance void Microsoft.Internal.GDIExporter.FontStreamContext::.ctor(class [System]System.Uri source, int32 streamLength)
0x22b45  stloc.0
0x22b46  ldarg.1
0x22b47  ldloc.0
0x22b48  call     instance bool Microsoft.Internal.GDIExporter.FontStreamContext::Equals([hasfieldmarshal] modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext value)
0x22b4d  stloc.1
0x22b4e  leave.s  loc_22B60
0x22b50  ldarg.2
0x22b51  ldloc.0
0x22b52  call     instance void Microsoft.Internal.GDIExporter.FontInstallInfo::UpdateFromContext(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.FontStreamContext context)
0x22b57  ldloc.0
0x22b58  call     instance void Microsoft.Internal.GDIExporter.FontStreamContext::Close()
0x22b5d  endfinally
0x22b5e  ldc.i4.0
0x22b5f  ret
0x22b60  ldloc.1
0x22b61  ret
```
