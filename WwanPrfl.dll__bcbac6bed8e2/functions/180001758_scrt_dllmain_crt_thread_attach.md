# __scrt_dllmain_crt_thread_attach

- ea: `0x180001758`
- end: `0x180001780`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012f0`

## callees

- `0x180001758`
- `0x1800022ac`

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
0x180001758  sub     rsp, 28h
0x18000175c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001761  test    al, al
0x180001763  jnz     short loc_180001769
0x180001765  xor     al, al
0x180001767  jmp     short loc_18000177B
0x180001769  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000176e  test    al, al
0x180001770  jnz     short loc_180001779
0x180001772  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001777  jmp     short loc_180001765
0x180001779  mov     al, 1
0x18000177b  add     rsp, 28h
0x18000177f  retn
```
