# __scrt_dllmain_after_initialize_c

- ea: `0x180001850`
- end: `0x180001884`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800013f8`

## callees

- `0x180001850`
- `0x180001df0`
- `0x18000207c`
- `0x180002126`
- `0x18000214a`
- `0x180009640`

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
0x180001850  sub     rsp, 28h
0x180001854  call    __scrt_is_ucrt_dll_in_use
0x180001859  test    eax, eax
0x18000185b  jz      short loc_180001864
0x18000185d  call    __isa_available_init
0x180001862  jmp     short loc_18000187D
0x180001864  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180001869  mov     ecx, eax; mode
0x18000186b  call    _o__configure_narrow_argv_0
0x180001870  test    eax, eax
0x180001872  jz      short loc_180001878
0x180001874  xor     al, al
0x180001876  jmp     short loc_18000187F
0x180001878  call    _initialize_narrow_environment
0x18000187d  mov     al, 1
0x18000187f  add     rsp, 28h
0x180001883  retn
```
