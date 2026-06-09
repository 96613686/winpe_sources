# __scrt_dllmain_crt_thread_attach

- ea: `0x180002ab4`
- end: `0x180002adc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800024a0`

## callees

- `0x180002ab4`
- `0x180005c98`
- `0x180022538`
- `0x18002254c`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002ab4  sub     rsp, 28h
0x180002ab8  call    __vcrt_thread_attach
0x180002abd  test    al, al
0x180002abf  jnz     short loc_180002AC5
0x180002ac1  xor     al, al
0x180002ac3  jmp     short loc_180002AD7
0x180002ac5  call    __acrt_thread_attach
0x180002aca  test    al, al
0x180002acc  jnz     short loc_180002AD5
0x180002ace  call    __vcrt_thread_detach
0x180002ad3  jmp     short loc_180002AC1
0x180002ad5  mov     al, 1
0x180002ad7  add     rsp, 28h
0x180002adb  retn
```
