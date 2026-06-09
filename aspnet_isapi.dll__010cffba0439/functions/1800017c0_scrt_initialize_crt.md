# __scrt_initialize_crt

- ea: `0x1800017c0`
- end: `0x180001809`
- name: `__scrt_initialize_crt`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011a0`

## callees

- `0x1800017c0`
- `0x180001ce8`
- `0x180001ee4`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  char v1; // al

  v1 = byte_180003080;
  if ( !a1 )
    v1 = 1;
  byte_180003080 = v1;
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
0x1800017c0  push    rbx
0x1800017c2  sub     rsp, 20h
0x1800017c6  movzx   eax, cs:byte_180003080
0x1800017cd  test    ecx, ecx
0x1800017cf  mov     ebx, 1
0x1800017d4  cmovz   eax, ebx
0x1800017d7  mov     cs:byte_180003080, al
0x1800017dd  call    __isa_available_init
0x1800017e2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017e7  test    al, al
0x1800017e9  jnz     short loc_1800017EF
0x1800017eb  xor     al, al
0x1800017ed  jmp     short loc_180001803
0x1800017ef  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017f4  test    al, al
0x1800017f6  jnz     short loc_180001801
0x1800017f8  xor     ecx, ecx
0x1800017fa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017ff  jmp     short loc_1800017EB
0x180001801  mov     al, bl
0x180001803  add     rsp, 20h
0x180001807  pop     rbx
0x180001808  retn
```
