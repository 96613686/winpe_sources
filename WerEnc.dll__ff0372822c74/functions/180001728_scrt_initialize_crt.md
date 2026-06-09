# __scrt_initialize_crt

- ea: `0x180001728`
- end: `0x180001762`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001728`
- `0x180001a1c`
- `0x180001ffc`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_1800061B1 = 1;
  _isa_available_init();
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001728  sub     rsp, 28h
0x18000172c  test    ecx, ecx
0x18000172e  jnz     short loc_180001737
0x180001730  mov     cs:byte_1800061B1, 1
0x180001737  call    __isa_available_init
0x18000173c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001741  test    al, al
0x180001743  jnz     short loc_180001749
0x180001745  xor     al, al
0x180001747  jmp     short loc_18000175D
0x180001749  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000174e  test    al, al
0x180001750  jnz     short loc_18000175B
0x180001752  xor     ecx, ecx
0x180001754  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001759  jmp     short loc_180001745
0x18000175b  mov     al, 1
0x18000175d  add     rsp, 28h
0x180001761  retn
```
