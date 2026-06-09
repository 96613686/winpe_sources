# __GSHandlerCheckCommon

- ea: `0x180014160`
- end: `0x1800141c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001413c`
- `0x1800141cc`
- `0x180014234`

## callees

- `0x180001720`
- `0x180014160`

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
0x180014160  mov     r10, rcx
0x180014163  mov     r11, rdx
0x180014166  mov     ecx, [r8]
0x180014169  and     ecx, 0FFFFFFF8h
0x18001416c  test    byte ptr [r8], 4
0x180014170  jz      short loc_180014187
0x180014172  mov     eax, [r8+8]
0x180014176  movsxd  r9, dword ptr [r8+4]
0x18001417a  neg     eax
0x18001417c  movsxd  rdx, eax
0x18001417f  add     r9, r10
0x180014182  and     r9, rdx
0x180014185  jmp     short loc_18001418A
0x180014187  mov     r9, r10
0x18001418a  movsxd  rax, ecx
0x18001418d  mov     rdx, [rax+r9]
0x180014191  mov     rax, [r11+10h]
0x180014195  mov     ecx, [rax+8]
0x180014198  mov     rax, [r11+8]
0x18001419c  test    byte ptr [rcx+rax+3], 0Fh
0x1800141a1  jz      short loc_1800141B5
0x1800141a3  movzx   eax, byte ptr [rcx+rax+3]
0x1800141a8  mov     ecx, 0FFFFFFF0h
0x1800141ad  and     rax, rcx
0x1800141b0  add     rax, r10
0x1800141b3  jmp     short loc_1800141B8
0x1800141b5  mov     rax, r10
0x1800141b8  xor     rdx, rax
0x1800141bb  mov     rcx, rdx; StackCookie
0x1800141be  jmp     __security_check_cookie
```
