# __scrt_dllmain_after_initialize_c

- ea: `0x1800039c4`
- end: `0x1800039f8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800035c8`

## callees

- `0x1800039c4`
- `0x1800040ec`
- `0x180004550`
- `0x1800045ea`
- `0x18000460e`
- `0x180005f10`

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
0x1800039c4  sub     rsp, 28h
0x1800039c8  call    __scrt_is_ucrt_dll_in_use
0x1800039cd  test    eax, eax
0x1800039cf  jz      short loc_1800039D8
0x1800039d1  call    __isa_available_init
0x1800039d6  jmp     short loc_1800039F1
0x1800039d8  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800039dd  mov     ecx, eax; mode
0x1800039df  call    _o__configure_narrow_argv_0
0x1800039e4  test    eax, eax
0x1800039e6  jz      short loc_1800039EC
0x1800039e8  xor     al, al
0x1800039ea  jmp     short loc_1800039F3
0x1800039ec  call    _initialize_narrow_environment
0x1800039f1  mov     al, 1
0x1800039f3  add     rsp, 28h
0x1800039f7  retn
```
