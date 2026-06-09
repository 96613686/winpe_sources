# __scrt_dllmain_after_initialize_c

- ea: `0x180003b14`
- end: `0x180003b48`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003798`

## callees

- `0x180003b14`
- `0x1800043c0`
- `0x18000464c`
- `0x180004746`
- `0x18000476a`
- `0x180013860`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode Type; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    Type = (unsigned int)TelemetryEventConsumer::GetType();
    if ( o__configure_narrow_argv_0(Type) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180003b14  sub     rsp, 28h
0x180003b18  call    __scrt_is_ucrt_dll_in_use
0x180003b1d  test    eax, eax
0x180003b1f  jz      short loc_180003B28
0x180003b21  call    __isa_available_init
0x180003b26  jmp     short loc_180003B41
0x180003b28  call    ?GetType@TelemetryEventConsumer@@UEBA?AW4Type@IPresentEventConsumer@@XZ; TelemetryEventConsumer::GetType(void)
0x180003b2d  mov     ecx, eax; mode
0x180003b2f  call    _o__configure_narrow_argv_0
0x180003b34  test    eax, eax
0x180003b36  jz      short loc_180003B3C
0x180003b38  xor     al, al
0x180003b3a  jmp     short loc_180003B43
0x180003b3c  call    _initialize_narrow_environment
0x180003b41  mov     al, 1
0x180003b43  add     rsp, 28h
0x180003b47  retn
```
