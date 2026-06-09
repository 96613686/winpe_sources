# __scrt_dllmain_crt_thread_attach

- ea: `0x1800017a0`
- end: `0x1800017c8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x1800017a0`
- `0x180002684`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800017a0  sub     rsp, 28h
0x1800017a4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017a9  test    al, al
0x1800017ab  jnz     short loc_1800017B1
0x1800017ad  xor     al, al
0x1800017af  jmp     short loc_1800017C3
0x1800017b1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017b6  test    al, al
0x1800017b8  jnz     short loc_1800017C1
0x1800017ba  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017bf  jmp     short loc_1800017AD
0x1800017c1  mov     al, 1
0x1800017c3  add     rsp, 28h
0x1800017c7  retn
```
