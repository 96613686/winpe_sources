# __scrt_dllmain_crt_thread_attach

- ea: `0x18000a194`
- end: `0x18000a1bc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009c40`

## callees

- `0x18000a194`
- `0x18000afd4`

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
0x18000a194  sub     rsp, 28h
0x18000a198  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000a19d  test    al, al
0x18000a19f  jnz     short loc_18000A1A5
0x18000a1a1  xor     al, al
0x18000a1a3  jmp     short loc_18000A1B7
0x18000a1a5  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000a1aa  test    al, al
0x18000a1ac  jnz     short loc_18000A1B5
0x18000a1ae  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000a1b3  jmp     short loc_18000A1A1
0x18000a1b5  mov     al, 1
0x18000a1b7  add     rsp, 28h
0x18000a1bb  retn
```
