# __scrt_dllmain_crt_thread_attach

- ea: `0x180001df0`
- end: `0x180001e18`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019d0`

## callees

- `0x180001df0`
- `0x180003260`

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
0x180001df0  sub     rsp, 28h
0x180001df4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001df9  test    al, al
0x180001dfb  jnz     short loc_180001E01
0x180001dfd  xor     al, al
0x180001dff  jmp     short loc_180001E13
0x180001e01  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e06  test    al, al
0x180001e08  jnz     short loc_180001E11
0x180001e0a  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001e0f  jmp     short loc_180001DFD
0x180001e11  mov     al, 1
0x180001e13  add     rsp, 28h
0x180001e17  retn
```
