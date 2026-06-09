# __GSHandlerCheckCommon

- ea: `0x1400264f8`
- end: `0x14002655b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400264d4`
- `0x140026564`

## callees

- `0x1400264f8`
- `0x140026650`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1400264f8  mov     r10, rcx
0x1400264fb  mov     r11, rdx
0x1400264fe  mov     ecx, [r8]
0x140026501  and     ecx, 0FFFFFFF8h
0x140026504  test    byte ptr [r8], 4
0x140026508  jz      short loc_14002651F
0x14002650a  mov     eax, [r8+8]
0x14002650e  movsxd  r9, dword ptr [r8+4]
0x140026512  neg     eax
0x140026514  movsxd  rdx, eax
0x140026517  add     r9, r10
0x14002651a  and     r9, rdx
0x14002651d  jmp     short loc_140026522
0x14002651f  mov     r9, r10
0x140026522  movsxd  rax, ecx
0x140026525  mov     rdx, [rax+r9]
0x140026529  mov     rax, [r11+10h]
0x14002652d  mov     ecx, [rax+8]
0x140026530  mov     rax, [r11+8]
0x140026534  test    byte ptr [rcx+rax+3], 0Fh
0x140026539  jz      short loc_14002654D
0x14002653b  movzx   eax, byte ptr [rcx+rax+3]
0x140026540  mov     ecx, 0FFFFFFF0h
0x140026545  and     rax, rcx
0x140026548  add     rax, r10
0x14002654b  jmp     short loc_140026550
0x14002654d  mov     rax, r10
0x140026550  xor     rdx, rax
0x140026553  mov     rcx, rdx; StackCookie
0x140026556  jmp     __security_check_cookie
```
