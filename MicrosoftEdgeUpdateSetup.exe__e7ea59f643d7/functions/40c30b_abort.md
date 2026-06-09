# _abort

- ea: `0x40c30b`
- end: `0x40c34e`
- name: `_abort`
- size: `67`
- prototype: `void __cdecl __noreturn()`
- caller_count: `16`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x40943c`
- `0x409800`
- `0x40981c`
- `0x409ab7`
- `0x40a154`
- `0x40a292`
- `0x40a3ab`
- `0x40a76e`
- `0x40acdc`
- `0x40ad7d`
- `0x40ae65`
- `0x40c24f`
- `0x40e819`
- `0x40e8d6`
- `0x40fbdd`
- `0x411105`

## callees

- `0x40bb40`
- `0x40c30b`
- `0x40ea7a`
- `0x4118b9`
- `0x4118fe`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x40c327`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40c327`

## pseudocode

```c
void __cdecl __noreturn abort()
{
  if ( __acrt_get_sigabrt_handler() )
    raise(22);
  if ( (byte_426040 & 2) != 0 )
  {
    if ( IsProcessorFeaturePresent(0x17u) )
      __fastfail(7u);
    __acrt_call_reportfault(3, 1073741845, 1);
  }
  _exit(3);
}

```

## disassembly

```asm
0x40c30b  call    ___acrt_get_sigabrt_handler
0x40c310  test    eax, eax
0x40c312  jz      short loc_40C31C
0x40c314  push    16h; Signal
0x40c316  call    _raise
0x40c31b  pop     ecx
0x40c31c  test    byte_426040, 2
0x40c323  jz      short loc_40C347
0x40c325  push    17h; ProcessorFeature
0x40c327  call    ds:IsProcessorFeaturePresent
0x40c32d  test    eax, eax
0x40c32f  jz      short loc_40C336
0x40c331  push    7
0x40c333  pop     ecx
0x40c334  int     29h; Win8: RtlFailFast(ecx)
0x40c336  push    1
0x40c338  push    40000015h
0x40c33d  push    3
0x40c33f  call    ___acrt_call_reportfault
0x40c344  add     esp, 0Ch
0x40c347  push    3; Code
0x40c349  call    __exit
```
