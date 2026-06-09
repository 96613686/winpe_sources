# System.Deployment.Application.ManifestReader::FromDocumentNoValidation

- ea: `0x1a060`
- end: `0x1a0d8`
- name: `System.Deployment.Application.ManifestReader::FromDocumentNoValidation`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x139e0`

## callees

- `0x40`
- `0x146b0`
- `0x17cd0`
- `0x1a060`
- `0x22b20`
- `0x23020`
- `0x24840`

## string_xrefs

- `0x1a09a`: `Ex_ManifestFileTooLarge`
- `0x1a070`: `ManifestReader.FromDocumentNoValidation(`

## pseudocode

```c

```

## disassembly

```asm
0x1a060  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x1a065  ldc.i4   0x1C86
0x1a06a  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x1a06f  pop
0x1a070  ldstr    aManifestreader_0// "ManifestReader.FromDocumentNoValidation"...
0x1a075  ldarg.0
0x1a076  ldstr    aCalled// ") called."
0x1a07b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a080  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1a085  ldarg.0
0x1a086  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x1a08b  stloc.1
0x1a08c  ldloc.1
0x1a08d  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x1a092  ldc.i4   0x1000000
0x1a097  conv.i8
0x1a098  ble.s    loc_1A0AA
0x1a09a  ldstr    aExManifestfile// "Ex_ManifestFileTooLarge"
0x1a09f  call     string System.Deployment.Application.Resources::GetString(string s)
0x1a0a4  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x1a0a9  throw
0x1a0aa  ldarg.0
0x1a0ab  ldc.i4.3
0x1a0ac  ldc.i4.1
0x1a0ad  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x1a0b2  stloc.2
0x1a0b3  ldloc.2
0x1a0b4  newobj   instance void System.Deployment.Application.Manifest.AssemblyManifest::.ctor(class [mscorlib]System.IO.FileStream fileStream)
0x1a0b9  stloc.0
0x1a0ba  leave.s  loc_1A0C6
0x1a0bc  ldloc.2
0x1a0bd  brfalse.s loc_1A0C5
0x1a0bf  ldloc.2
0x1a0c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a0c5  endfinally
0x1a0c6  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x1a0cb  ldc.i4   0x1C87
0x1a0d0  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x1a0d5  pop
0x1a0d6  ldloc.0
0x1a0d7  ret
```
