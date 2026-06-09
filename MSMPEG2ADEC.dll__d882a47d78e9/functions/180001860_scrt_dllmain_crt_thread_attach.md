# __scrt_dllmain_crt_thread_attach

- ea: `0x180001860`
- end: `0x180001888`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001860`
- `0x180009658`

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
0x180001860  sub     rsp, 28h
0x180001864  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001869  test    al, al
0x18000186b  jnz     short loc_180001871
0x18000186d  xor     al, al
0x18000186f  jmp     short loc_180001883
0x180001871  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001876  test    al, al
0x180001878  jnz     short loc_180001881
0x18000187a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000187f  jmp     short loc_18000186D
0x180001881  mov     al, 1
0x180001883  add     rsp, 28h
0x180001887  retn
```
