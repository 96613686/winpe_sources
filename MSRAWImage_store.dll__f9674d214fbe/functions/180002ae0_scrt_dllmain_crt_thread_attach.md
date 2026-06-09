# __scrt_dllmain_crt_thread_attach

- ea: `0x180002ae0`
- end: `0x180002b08`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002680`

## callees

- `0x180002ae0`
- `0x180003ce0`
- `0x180003cfc`
- `0x180095390`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002ae0  sub     rsp, 28h
0x180002ae4  call    __vcrt_thread_attach
0x180002ae9  test    al, al
0x180002aeb  jnz     short loc_180002AF1
0x180002aed  xor     al, al
0x180002aef  jmp     short loc_180002B03
0x180002af1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002af6  test    al, al
0x180002af8  jnz     short loc_180002B01
0x180002afa  call    __vcrt_thread_detach
0x180002aff  jmp     short loc_180002AED
0x180002b01  mov     al, 1
0x180002b03  add     rsp, 28h
0x180002b07  retn
```
