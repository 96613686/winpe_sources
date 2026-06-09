# __GSHandlerCheckCommon

- ea: `0x1800021ec`
- end: `0x18000224f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800021c8`
- `0x18001619c`

## callees

- `0x1800021ec`
- `0x180016280`

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
0x1800021ec  mov     r10, rcx
0x1800021ef  mov     r11, rdx
0x1800021f2  mov     ecx, [r8]
0x1800021f5  and     ecx, 0FFFFFFF8h
0x1800021f8  test    byte ptr [r8], 4
0x1800021fc  jz      short loc_180002213
0x1800021fe  mov     eax, [r8+8]
0x180002202  movsxd  r9, dword ptr [r8+4]
0x180002206  neg     eax
0x180002208  movsxd  rdx, eax
0x18000220b  add     r9, r10
0x18000220e  and     r9, rdx
0x180002211  jmp     short loc_180002216
0x180002213  mov     r9, r10
0x180002216  movsxd  rax, ecx
0x180002219  mov     rdx, [rax+r9]
0x18000221d  mov     rax, [r11+10h]
0x180002221  mov     ecx, [rax+8]
0x180002224  mov     rax, [r11+8]
0x180002228  test    byte ptr [rcx+rax+3], 0Fh
0x18000222d  jz      short loc_180002241
0x18000222f  movzx   eax, byte ptr [rcx+rax+3]
0x180002234  mov     ecx, 0FFFFFFF0h
0x180002239  and     rax, rcx
0x18000223c  add     rax, r10
0x18000223f  jmp     short loc_180002244
0x180002241  mov     rax, r10
0x180002244  xor     rdx, rax
0x180002247  mov     rcx, rdx; StackCookie
0x18000224a  jmp     __security_check_cookie
```
