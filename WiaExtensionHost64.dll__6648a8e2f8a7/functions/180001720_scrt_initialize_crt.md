# __scrt_initialize_crt

- ea: `0x180001720`
- end: `0x18000175a`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001128`

## callees

- `0x180001720`
- `0x1800019bc`
- `0x180001d24`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_1800050F1 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v1) )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v2) )
  {
    _scrt_stub_for_acrt_uninitialize_critical(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001720  sub     rsp, 28h
0x180001724  test    ecx, ecx
0x180001726  jnz     short loc_18000172F
0x180001728  mov     cs:byte_1800050F1, 1
0x18000172f  call    __isa_available_init
0x180001734  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001739  test    al, al
0x18000173b  jnz     short loc_180001741
0x18000173d  xor     al, al
0x18000173f  jmp     short loc_180001755
0x180001741  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001746  test    al, al
0x180001748  jnz     short loc_180001753
0x18000174a  xor     ecx, ecx
0x18000174c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001751  jmp     short loc_18000173D
0x180001753  mov     al, 1
0x180001755  add     rsp, 28h
0x180001759  retn
```
