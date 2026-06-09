# __scrt_dllmain_after_initialize_c

- ea: `0x1800020d4`
- end: `0x180002108`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001cd8`

## callees

- `0x1800020d4`
- `0x1800026a8`
- `0x180002934`
- `0x1800029ca`
- `0x1800029ee`
- `0x180004170`

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
0x1800020d4  sub     rsp, 28h
0x1800020d8  call    __scrt_is_ucrt_dll_in_use
0x1800020dd  test    eax, eax
0x1800020df  jz      short loc_1800020E8
0x1800020e1  call    __isa_available_init
0x1800020e6  jmp     short loc_180002101
0x1800020e8  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800020ed  mov     ecx, eax; mode
0x1800020ef  call    _o__configure_narrow_argv_0
0x1800020f4  test    eax, eax
0x1800020f6  jz      short loc_1800020FC
0x1800020f8  xor     al, al
0x1800020fa  jmp     short loc_180002103
0x1800020fc  call    _initialize_narrow_environment
0x180002101  mov     al, 1
0x180002103  add     rsp, 28h
0x180002107  retn
```
