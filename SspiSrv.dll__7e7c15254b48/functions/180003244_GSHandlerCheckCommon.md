# __GSHandlerCheckCommon

- ea: `0x180003244`
- end: `0x1800032a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003220`
- `0x1800032b0`

## callees

- `0x180003244`
- `0x180003340`

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
0x180003244  mov     r10, rcx
0x180003247  mov     r11, rdx
0x18000324a  mov     ecx, [r8]
0x18000324d  and     ecx, 0FFFFFFF8h
0x180003250  test    byte ptr [r8], 4
0x180003254  jz      short loc_18000326B
0x180003256  mov     eax, [r8+8]
0x18000325a  movsxd  r9, dword ptr [r8+4]
0x18000325e  neg     eax
0x180003260  movsxd  rdx, eax
0x180003263  add     r9, r10
0x180003266  and     r9, rdx
0x180003269  jmp     short loc_18000326E
0x18000326b  mov     r9, r10
0x18000326e  movsxd  rax, ecx
0x180003271  mov     rdx, [rax+r9]
0x180003275  mov     rax, [r11+10h]
0x180003279  mov     ecx, [rax+8]
0x18000327c  mov     rax, [r11+8]
0x180003280  test    byte ptr [rcx+rax+3], 0Fh
0x180003285  jz      short loc_180003299
0x180003287  movzx   eax, byte ptr [rcx+rax+3]
0x18000328c  mov     ecx, 0FFFFFFF0h
0x180003291  and     rax, rcx
0x180003294  add     rax, r10
0x180003297  jmp     short loc_18000329C
0x180003299  mov     rax, r10
0x18000329c  xor     rdx, rax
0x18000329f  mov     rcx, rdx; StackCookie
0x1800032a2  jmp     __security_check_cookie
```
