# Microsoft.BusinessIntelligence.ExposureControlProvider::SetExposureControl

- ea: `0x3c0`
- end: `0x3e3`
- name: `Microsoft.BusinessIntelligence.ExposureControlProvider::SetExposureControl`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3f0`

## callees

- `0x3c0`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  volatile.
0x3c2  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.BusinessIntelligence.ExposureControl Microsoft.BusinessIntelligence.ExposureControlProvider::exposureControl
0x3c7  brfalse.s loc_3D4
0x3c9  ldstr    aYouCannotSetTh// "You cannot set the exposure control ins"...
0x3ce  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3d3  throw
0x3d4  ldarg.0
0x3d5  ldarg.1
0x3d6  call     instance class Microsoft.BusinessIntelligence.ExposureControl Microsoft.BusinessIntelligence.ExposureControlProvider::CreateExposureControl(valuetype Microsoft.BusinessIntelligence.ExposureLevel exposureLevel)
0x3db  volatile.
0x3dd  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.BusinessIntelligence.ExposureControl Microsoft.BusinessIntelligence.ExposureControlProvider::exposureControl
0x3e2  ret
```
