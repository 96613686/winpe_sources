# __GSHandlerCheckCommon

- ea: `0x180018760`
- end: `0x1800187c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001873c`

## callees

- `0x180001dc0`
- `0x180018760`

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
0x180018760  mov     r10, rcx
0x180018763  mov     r11, rdx
0x180018766  mov     ecx, [r8]
0x180018769  and     ecx, 0FFFFFFF8h
0x18001876c  test    byte ptr [r8], 4
0x180018770  jz      short loc_180018787
0x180018772  mov     eax, [r8+8]
0x180018776  movsxd  r9, dword ptr [r8+4]
0x18001877a  neg     eax
0x18001877c  movsxd  rdx, eax
0x18001877f  add     r9, r10
0x180018782  and     r9, rdx
0x180018785  jmp     short loc_18001878A
0x180018787  mov     r9, r10
0x18001878a  movsxd  rax, ecx
0x18001878d  mov     rdx, [rax+r9]
0x180018791  mov     rax, [r11+10h]
0x180018795  mov     ecx, [rax+8]
0x180018798  mov     rax, [r11+8]
0x18001879c  test    byte ptr [rcx+rax+3], 0Fh
0x1800187a1  jz      short loc_1800187B5
0x1800187a3  movzx   eax, byte ptr [rcx+rax+3]
0x1800187a8  mov     ecx, 0FFFFFFF0h
0x1800187ad  and     rax, rcx
0x1800187b0  add     rax, r10
0x1800187b3  jmp     short loc_1800187B8
0x1800187b5  mov     rax, r10
0x1800187b8  xor     rdx, rax
0x1800187bb  mov     rcx, rdx; StackCookie
0x1800187be  jmp     __security_check_cookie
```
