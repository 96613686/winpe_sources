# __scrt_dllmain_after_initialize_c

- ea: `0x180004324`
- end: `0x180004358`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003e58`

## callees

- `0x180004324`
- `0x180004a50`
- `0x180004eb0`
- `0x180004f4a`
- `0x180004f6e`
- `0x180006920`

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
0x180004324  sub     rsp, 28h
0x180004328  call    __scrt_is_ucrt_dll_in_use
0x18000432d  test    eax, eax
0x18000432f  jz      short loc_180004338
0x180004331  call    __isa_available_init
0x180004336  jmp     short loc_180004351
0x180004338  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x18000433d  mov     ecx, eax; mode
0x18000433f  call    _o__configure_narrow_argv_0
0x180004344  test    eax, eax
0x180004346  jz      short loc_18000434C
0x180004348  xor     al, al
0x18000434a  jmp     short loc_180004353
0x18000434c  call    _initialize_narrow_environment
0x180004351  mov     al, 1
0x180004353  add     rsp, 28h
0x180004357  retn
```
