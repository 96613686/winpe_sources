# __scrt_dllmain_after_initialize_c

- ea: `0x1800160dc`
- end: `0x180016110`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180015d08`

## callees

- `0x1800160dc`
- `0x1800165f8`
- `0x180016884`
- `0x18001691a`
- `0x18001693e`
- `0x180017a50`

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
0x1800160dc  sub     rsp, 28h
0x1800160e0  call    __scrt_is_ucrt_dll_in_use
0x1800160e5  test    eax, eax
0x1800160e7  jz      short loc_1800160F0
0x1800160e9  call    __isa_available_init
0x1800160ee  jmp     short loc_180016109
0x1800160f0  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800160f5  mov     ecx, eax; mode
0x1800160f7  call    _o__configure_narrow_argv_0
0x1800160fc  test    eax, eax
0x1800160fe  jz      short loc_180016104
0x180016100  xor     al, al
0x180016102  jmp     short loc_18001610B
0x180016104  call    _initialize_narrow_environment
0x180016109  mov     al, 1
0x18001610b  add     rsp, 28h
0x18001610f  retn
```
