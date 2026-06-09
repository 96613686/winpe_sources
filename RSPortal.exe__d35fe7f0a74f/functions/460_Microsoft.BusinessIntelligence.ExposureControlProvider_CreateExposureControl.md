# Microsoft.BusinessIntelligence.ExposureControlProvider::CreateExposureControl

- ea: `0x460`
- end: `0x490`
- name: `Microsoft.BusinessIntelligence.ExposureControlProvider::CreateExposureControl`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3c0`

## callees

- `0x270`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldc.i4.1
0x461  ldarg.1
0x462  bne.un.s loc_46D
0x464  ldc.i4.1
0x465  newobj   instance void Microsoft.BusinessIntelligence.ExposureControl::.ctor(valuetype Microsoft.BusinessIntelligence.ExposureLevel exposureLevel)
0x46a  stloc.0
0x46b  br.s     loc_48E
0x46d  ldc.i4.2
0x46e  ldarg.1
0x46f  bne.un.s loc_47A
0x471  ldc.i4.2
0x472  newobj   instance void Microsoft.BusinessIntelligence.ExposureControl::.ctor(valuetype Microsoft.BusinessIntelligence.ExposureLevel exposureLevel)
0x477  stloc.0
0x478  br.s     loc_48E
0x47a  ldc.i4.3
0x47b  ldarg.1
0x47c  bne.un.s loc_487
0x47e  ldc.i4.3
0x47f  newobj   instance void Microsoft.BusinessIntelligence.ExposureControl::.ctor(valuetype Microsoft.BusinessIntelligence.ExposureLevel exposureLevel)
0x484  stloc.0
0x485  br.s     loc_48E
0x487  ldc.i4.0
0x488  newobj   instance void Microsoft.BusinessIntelligence.ExposureControl::.ctor(valuetype Microsoft.BusinessIntelligence.ExposureLevel exposureLevel)
0x48d  stloc.0
0x48e  ldloc.0
0x48f  ret
```
