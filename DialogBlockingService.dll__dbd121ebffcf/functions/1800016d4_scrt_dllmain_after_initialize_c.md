# __scrt_dllmain_after_initialize_c

- ea: `0x1800016d4`
- end: `0x180001708`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001308`

## callees

- `0x1800016d4`
- `0x180001cec`
- `0x180001f78`
- `0x18000201e`
- `0x180002042`
- `0x18000b890`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *v0; // rcx
  _crt_argv_mode Version; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    Version = (unsigned int)Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::GetVersion(v0);
    if ( o__configure_narrow_argv_0(Version) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800016d4  sub     rsp, 28h
0x1800016d8  call    __scrt_is_ucrt_dll_in_use
0x1800016dd  test    eax, eax
0x1800016df  jz      short loc_1800016E8
0x1800016e1  call    __isa_available_init
0x1800016e6  jmp     short loc_180001701
0x1800016e8  call    ?GetVersion@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@EEAAKXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::GetVersion(void)
0x1800016ed  mov     ecx, eax; mode
0x1800016ef  call    _o__configure_narrow_argv_0
0x1800016f4  test    eax, eax
0x1800016f6  jz      short loc_1800016FC
0x1800016f8  xor     al, al
0x1800016fa  jmp     short loc_180001703
0x1800016fc  call    _initialize_narrow_environment
0x180001701  mov     al, 1
0x180001703  add     rsp, 28h
0x180001707  retn
```
