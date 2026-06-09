# __GSHandlerCheckCommon

- ea: `0x180003220`
- end: `0x180003283`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800031fc`

## callees

- `0x180003220`
- `0x1800032e0`

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
0x180003220  mov     r10, rcx
0x180003223  mov     r11, rdx
0x180003226  mov     ecx, [r8]
0x180003229  and     ecx, 0FFFFFFF8h
0x18000322c  test    byte ptr [r8], 4
0x180003230  jz      short loc_180003247
0x180003232  mov     eax, [r8+8]
0x180003236  movsxd  r9, dword ptr [r8+4]
0x18000323a  neg     eax
0x18000323c  movsxd  rdx, eax
0x18000323f  add     r9, r10
0x180003242  and     r9, rdx
0x180003245  jmp     short loc_18000324A
0x180003247  mov     r9, r10
0x18000324a  movsxd  rax, ecx
0x18000324d  mov     rdx, [rax+r9]
0x180003251  mov     rax, [r11+10h]
0x180003255  mov     ecx, [rax+8]
0x180003258  mov     rax, [r11+8]
0x18000325c  test    byte ptr [rcx+rax+3], 0Fh
0x180003261  jz      short loc_180003275
0x180003263  movzx   eax, byte ptr [rcx+rax+3]
0x180003268  mov     ecx, 0FFFFFFF0h
0x18000326d  and     rax, rcx
0x180003270  add     rax, r10
0x180003273  jmp     short loc_180003278
0x180003275  mov     rax, r10
0x180003278  xor     rdx, rax
0x18000327b  mov     rcx, rdx; StackCookie
0x18000327e  jmp     __security_check_cookie
```
