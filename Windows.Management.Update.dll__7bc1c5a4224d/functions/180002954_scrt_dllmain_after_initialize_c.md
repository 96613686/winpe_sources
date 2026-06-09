# __scrt_dllmain_after_initialize_c

- ea: `0x180002954`
- end: `0x180002988`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800025d8`

## callees

- `0x180002954`
- `0x180002ff0`
- `0x18000327c`
- `0x180003356`
- `0x18000337a`
- `0x1800143e0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator *v0; // rcx
  enum TrustLevel TrustLevel; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    TrustLevel = winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator::GetTrustLevel(v0);
    if ( o__configure_narrow_argv_0((_crt_argv_mode)TrustLevel) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002954  sub     rsp, 28h
0x180002958  call    __scrt_is_ucrt_dll_in_use
0x18000295d  test    eax, eax
0x18000295f  jz      short loc_180002968
0x180002961  call    __isa_available_init
0x180002966  jmp     short loc_180002981
0x180002968  call    ?GetTrustLevel@WindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@UEBA?AW4TrustLevel@Foundation@56@XZ; winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator::GetTrustLevel(void)
0x18000296d  mov     ecx, eax; mode
0x18000296f  call    _o__configure_narrow_argv_0
0x180002974  test    eax, eax
0x180002976  jz      short loc_18000297C
0x180002978  xor     al, al
0x18000297a  jmp     short loc_180002983
0x18000297c  call    _initialize_narrow_environment
0x180002981  mov     al, 1
0x180002983  add     rsp, 28h
0x180002987  retn
```
