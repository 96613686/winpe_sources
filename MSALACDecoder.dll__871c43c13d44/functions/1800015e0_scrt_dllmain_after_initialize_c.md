# __scrt_dllmain_after_initialize_c

- ea: `0x1800015e0`
- end: `0x180001614`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001238`

## callees

- `0x1800015e0`
- `0x180001b28`
- `0x180001db4`
- `0x180001e26`
- `0x180001e4a`
- `0x1800045b0`

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
0x1800015e0  sub     rsp, 28h
0x1800015e4  call    __scrt_is_ucrt_dll_in_use
0x1800015e9  test    eax, eax
0x1800015eb  jz      short loc_1800015F4
0x1800015ed  call    __isa_available_init
0x1800015f2  jmp     short loc_18000160D
0x1800015f4  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800015f9  mov     ecx, eax; mode
0x1800015fb  call    _o__configure_narrow_argv_0
0x180001600  test    eax, eax
0x180001602  jz      short loc_180001608
0x180001604  xor     al, al
0x180001606  jmp     short loc_18000160F
0x180001608  call    _initialize_narrow_environment
0x18000160d  mov     al, 1
0x18000160f  add     rsp, 28h
0x180001613  retn
```
