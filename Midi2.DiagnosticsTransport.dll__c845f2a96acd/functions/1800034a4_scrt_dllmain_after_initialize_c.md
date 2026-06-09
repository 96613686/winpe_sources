# __scrt_dllmain_after_initialize_c

- ea: `0x1800034a4`
- end: `0x1800034d8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800030a8`

## callees

- `0x1800034a4`
- `0x180003b90`
- `0x180004018`
- `0x1800040ba`
- `0x1800040de`
- `0x180005880`

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
0x1800034a4  sub     rsp, 28h
0x1800034a8  call    __scrt_is_ucrt_dll_in_use
0x1800034ad  test    eax, eax
0x1800034af  jz      short loc_1800034B8
0x1800034b1  call    __isa_available_init
0x1800034b6  jmp     short loc_1800034D1
0x1800034b8  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800034bd  mov     ecx, eax; mode
0x1800034bf  call    _o__configure_narrow_argv_0
0x1800034c4  test    eax, eax
0x1800034c6  jz      short loc_1800034CC
0x1800034c8  xor     al, al
0x1800034ca  jmp     short loc_1800034D3
0x1800034cc  call    _initialize_narrow_environment
0x1800034d1  mov     al, 1
0x1800034d3  add     rsp, 28h
0x1800034d7  retn
```
