# __scrt_dllmain_after_initialize_c

- ea: `0x180001f7c`
- end: `0x180001fb0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001bc8`

## callees

- `0x180001f7c`
- `0x1800024a4`
- `0x180002730`
- `0x18000279a`
- `0x1800027be`
- `0x1800218d0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  void *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = (unsigned int)BEnableBuiltInFeatures(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001f7c  sub     rsp, 28h
0x180001f80  call    __scrt_is_ucrt_dll_in_use
0x180001f85  test    eax, eax
0x180001f87  jz      short loc_180001F90
0x180001f89  call    __isa_available_init
0x180001f8e  jmp     short loc_180001FA9
0x180001f90  call    ?BEnableBuiltInFeatures@@YAHPEAX@Z; BEnableBuiltInFeatures(void *)
0x180001f95  mov     ecx, eax; mode
0x180001f97  call    _o__configure_narrow_argv_0
0x180001f9c  test    eax, eax
0x180001f9e  jz      short loc_180001FA4
0x180001fa0  xor     al, al
0x180001fa2  jmp     short loc_180001FAB
0x180001fa4  call    _initialize_narrow_environment
0x180001fa9  mov     al, 1
0x180001fab  add     rsp, 28h
0x180001faf  retn
```
