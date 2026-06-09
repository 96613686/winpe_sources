# __scrt_dllmain_crt_thread_attach

- ea: `0x180001750`
- end: `0x180001778`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001330`

## callees

- `0x180001750`
- `0x180002180`

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
0x180001750  sub     rsp, 28h
0x180001754  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001759  test    al, al
0x18000175b  jnz     short loc_180001761
0x18000175d  xor     al, al
0x18000175f  jmp     short loc_180001773
0x180001761  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001766  test    al, al
0x180001768  jnz     short loc_180001771
0x18000176a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000176f  jmp     short loc_18000175D
0x180001771  mov     al, 1
0x180001773  add     rsp, 28h
0x180001777  retn
```
