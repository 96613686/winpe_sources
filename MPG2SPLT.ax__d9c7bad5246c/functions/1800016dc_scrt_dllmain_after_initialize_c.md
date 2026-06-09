# __scrt_dllmain_after_initialize_c

- ea: `0x1800016dc`
- end: `0x180001710`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001148`

## callees

- `0x1800016dc`
- `0x180001b10`
- `0x180001d9c`
- `0x180001e0a`
- `0x180001e2e`
- `0x18000d930`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  unsigned int v0; // edx
  CMPEG2TransportController *v1; // rcx
  struct CMediaType *v2; // r8
  _crt_argv_mode IsCopyBufferSource; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsCopyBufferSource = (unsigned int)CMPEG2TransportController::IsCopyBufferSource_(v1, v0, v2);
    if ( o__configure_narrow_argv_0(IsCopyBufferSource) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800016dc  sub     rsp, 28h
0x1800016e0  call    __scrt_is_ucrt_dll_in_use
0x1800016e5  test    eax, eax
0x1800016e7  jz      short loc_1800016F0
0x1800016e9  call    __isa_available_init
0x1800016ee  jmp     short loc_180001709
0x1800016f0  call    ?IsCopyBufferSource_@CMPEG2TransportController@@MEAAHKPEAVCMediaType@@@Z; CMPEG2TransportController::IsCopyBufferSource_(ulong,CMediaType *)
0x1800016f5  mov     ecx, eax; mode
0x1800016f7  call    _o__configure_narrow_argv_0
0x1800016fc  test    eax, eax
0x1800016fe  jz      short loc_180001704
0x180001700  xor     al, al
0x180001702  jmp     short loc_18000170B
0x180001704  call    _initialize_narrow_environment
0x180001709  mov     al, 1
0x18000170b  add     rsp, 28h
0x18000170f  retn
```
