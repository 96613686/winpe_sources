# __scrt_dllmain_after_initialize_c

- ea: `0x180001fc4`
- end: `0x180001ff8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001bc8`

## callees

- `0x180001fc4`
- `0x180002598`
- `0x180002824`
- `0x1800028ba`
- `0x1800028de`
- `0x180004060`

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
0x180001fc4  sub     rsp, 28h
0x180001fc8  call    __scrt_is_ucrt_dll_in_use
0x180001fcd  test    eax, eax
0x180001fcf  jz      short loc_180001FD8
0x180001fd1  call    __isa_available_init
0x180001fd6  jmp     short loc_180001FF1
0x180001fd8  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180001fdd  mov     ecx, eax; mode
0x180001fdf  call    _o__configure_narrow_argv_0
0x180001fe4  test    eax, eax
0x180001fe6  jz      short loc_180001FEC
0x180001fe8  xor     al, al
0x180001fea  jmp     short loc_180001FF3
0x180001fec  call    _initialize_narrow_environment
0x180001ff1  mov     al, 1
0x180001ff3  add     rsp, 28h
0x180001ff7  retn
```
