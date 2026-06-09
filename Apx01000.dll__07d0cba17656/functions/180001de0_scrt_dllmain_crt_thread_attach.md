# __scrt_dllmain_crt_thread_attach

- ea: `0x180001de0`
- end: `0x180001e08`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019c0`

## callees

- `0x180001de0`
- `0x18000f8f0`

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
0x180001de0  sub     rsp, 28h
0x180001de4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001de9  test    al, al
0x180001deb  jnz     short loc_180001DF1
0x180001ded  xor     al, al
0x180001def  jmp     short loc_180001E03
0x180001df1  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001df6  test    al, al
0x180001df8  jnz     short loc_180001E01
0x180001dfa  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001dff  jmp     short loc_180001DED
0x180001e01  mov     al, 1
0x180001e03  add     rsp, 28h
0x180001e07  retn
```
