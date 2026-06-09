# __scrt_dllmain_crt_thread_attach

- ea: `0x180007378`
- end: `0x1800073a0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800076a0`

## callees

- `0x180007378`
- `0x180008bec`
- `0x180008c00`
- `0x18000b834`

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
0x180007378  sub     rsp, 28h
0x18000737c  call    __vcrt_thread_attach
0x180007381  test    al, al
0x180007383  jnz     short loc_180007389
0x180007385  xor     al, al
0x180007387  jmp     short loc_18000739B
0x180007389  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000738e  test    al, al
0x180007390  jnz     short loc_180007399
0x180007392  call    __vcrt_thread_detach
0x180007397  jmp     short loc_180007385
0x180007399  mov     al, 1
0x18000739b  add     rsp, 28h
0x18000739f  retn
```
