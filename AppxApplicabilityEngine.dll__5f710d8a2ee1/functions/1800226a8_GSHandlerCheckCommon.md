# __GSHandlerCheckCommon

- ea: `0x1800226a8`
- end: `0x18002270b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022684`
- `0x180022714`

## callees

- `0x1800226a8`
- `0x1800227c0`

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
0x1800226a8  mov     r10, rcx
0x1800226ab  mov     r11, rdx
0x1800226ae  mov     ecx, [r8]
0x1800226b1  and     ecx, 0FFFFFFF8h
0x1800226b4  test    byte ptr [r8], 4
0x1800226b8  jz      short loc_1800226CF
0x1800226ba  mov     eax, [r8+8]
0x1800226be  movsxd  r9, dword ptr [r8+4]
0x1800226c2  neg     eax
0x1800226c4  movsxd  rdx, eax
0x1800226c7  add     r9, r10
0x1800226ca  and     r9, rdx
0x1800226cd  jmp     short loc_1800226D2
0x1800226cf  mov     r9, r10
0x1800226d2  movsxd  rax, ecx
0x1800226d5  mov     rdx, [rax+r9]
0x1800226d9  mov     rax, [r11+10h]
0x1800226dd  mov     ecx, [rax+8]
0x1800226e0  mov     rax, [r11+8]
0x1800226e4  test    byte ptr [rcx+rax+3], 0Fh
0x1800226e9  jz      short loc_1800226FD
0x1800226eb  movzx   eax, byte ptr [rcx+rax+3]
0x1800226f0  mov     ecx, 0FFFFFFF0h
0x1800226f5  and     rax, rcx
0x1800226f8  add     rax, r10
0x1800226fb  jmp     short loc_180022700
0x1800226fd  mov     rax, r10
0x180022700  xor     rdx, rax
0x180022703  mov     rcx, rdx; StackCookie
0x180022706  jmp     __security_check_cookie
```
