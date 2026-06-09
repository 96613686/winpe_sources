# __scrt_dllmain_after_initialize_c

- ea: `0x180002544`
- end: `0x180002578`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002148`

## callees

- `0x180002544`
- `0x180002c34`
- `0x180002ec0`
- `0x180002f5a`
- `0x180002f7e`
- `0x180004720`

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
0x180002544  sub     rsp, 28h
0x180002548  call    __scrt_is_ucrt_dll_in_use
0x18000254d  test    eax, eax
0x18000254f  jz      short loc_180002558
0x180002551  call    __isa_available_init
0x180002556  jmp     short loc_180002571
0x180002558  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x18000255d  mov     ecx, eax; mode
0x18000255f  call    _o__configure_narrow_argv_0
0x180002564  test    eax, eax
0x180002566  jz      short loc_18000256C
0x180002568  xor     al, al
0x18000256a  jmp     short loc_180002573
0x18000256c  call    _initialize_narrow_environment
0x180002571  mov     al, 1
0x180002573  add     rsp, 28h
0x180002577  retn
```
