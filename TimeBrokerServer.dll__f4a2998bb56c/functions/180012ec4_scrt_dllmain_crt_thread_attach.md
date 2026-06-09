# __scrt_dllmain_crt_thread_attach

- ea: `0x180012ec4`
- end: `0x180012eec`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012a60`

## callees

- `0x180012ec4`
- `0x180013b34`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180012ec4  sub     rsp, 28h
0x180012ec8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012ecd  test    al, al
0x180012ecf  jnz     short loc_180012ED5
0x180012ed1  xor     al, al
0x180012ed3  jmp     short loc_180012EE7
0x180012ed5  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012eda  test    al, al
0x180012edc  jnz     short loc_180012EE5
0x180012ede  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012ee3  jmp     short loc_180012ED1
0x180012ee5  mov     al, 1
0x180012ee7  add     rsp, 28h
0x180012eeb  retn
```
