# __scrt_dllmain_crt_thread_attach

- ea: `0x18000ec20`
- end: `0x18000ec48`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e800`

## callees

- `0x18000ec20`
- `0x18000f920`

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
0x18000ec20  sub     rsp, 28h
0x18000ec24  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ec29  test    al, al
0x18000ec2b  jnz     short loc_18000EC31
0x18000ec2d  xor     al, al
0x18000ec2f  jmp     short loc_18000EC43
0x18000ec31  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ec36  test    al, al
0x18000ec38  jnz     short loc_18000EC41
0x18000ec3a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000ec3f  jmp     short loc_18000EC2D
0x18000ec41  mov     al, 1
0x18000ec43  add     rsp, 28h
0x18000ec47  retn
```
