# __scrt_dllmain_crt_thread_attach

- ea: `0x180001638`
- end: `0x180001660`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001638`
- `0x180001ffc`

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
0x180001638  sub     rsp, 28h
0x18000163c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001641  test    al, al
0x180001643  jnz     short loc_180001649
0x180001645  xor     al, al
0x180001647  jmp     short loc_18000165B
0x180001649  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000164e  test    al, al
0x180001650  jnz     short loc_180001659
0x180001652  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001657  jmp     short loc_180001645
0x180001659  mov     al, 1
0x18000165b  add     rsp, 28h
0x18000165f  retn
```
