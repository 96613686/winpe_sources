# __scrt_dllmain_after_initialize_c

- ea: `0x180001980`
- end: `0x1800019b4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800015d8`

## callees

- `0x180001980`
- `0x180001ec8`
- `0x180002154`
- `0x1800021c6`
- `0x1800021ea`
- `0x18001f420`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  ATL::CRegObject *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = ATL::CRegObject::AddRef(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001980  sub     rsp, 28h
0x180001984  call    __scrt_is_ucrt_dll_in_use
0x180001989  test    eax, eax
0x18000198b  jz      short loc_180001994
0x18000198d  call    __isa_available_init
0x180001992  jmp     short loc_1800019AD
0x180001994  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180001999  mov     ecx, eax; mode
0x18000199b  call    _o__configure_narrow_argv_0
0x1800019a0  test    eax, eax
0x1800019a2  jz      short loc_1800019A8
0x1800019a4  xor     al, al
0x1800019a6  jmp     short loc_1800019AF
0x1800019a8  call    _initialize_narrow_environment
0x1800019ad  mov     al, 1
0x1800019af  add     rsp, 28h
0x1800019b3  retn
```
