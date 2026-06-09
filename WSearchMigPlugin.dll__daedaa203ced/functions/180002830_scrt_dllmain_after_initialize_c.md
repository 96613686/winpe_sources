# __scrt_dllmain_after_initialize_c

- ea: `0x180002830`
- end: `0x180002864`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800023c8`

## callees

- `0x180002830`
- `0x180002e98`
- `0x180003124`
- `0x1800031de`
- `0x180003202`
- `0x18000d2a0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  ATL::CRegistryVirtualMachine *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = (unsigned int)ATL::CRegistryVirtualMachine::Release(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002830  sub     rsp, 28h
0x180002834  call    __scrt_is_ucrt_dll_in_use
0x180002839  test    eax, eax
0x18000283b  jz      short loc_180002844
0x18000283d  call    __isa_available_init
0x180002842  jmp     short loc_18000285D
0x180002844  call    ?Release@CRegistryVirtualMachine@ATL@@UEAAKXZ; ATL::CRegistryVirtualMachine::Release(void)
0x180002849  mov     ecx, eax; mode
0x18000284b  call    _o__configure_narrow_argv_0
0x180002850  test    eax, eax
0x180002852  jz      short loc_180002858
0x180002854  xor     al, al
0x180002856  jmp     short loc_18000285F
0x180002858  call    _initialize_narrow_environment
0x18000285d  mov     al, 1
0x18000285f  add     rsp, 28h
0x180002863  retn
```
