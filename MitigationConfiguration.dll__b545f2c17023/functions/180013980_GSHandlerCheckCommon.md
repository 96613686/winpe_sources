# __GSHandlerCheckCommon

- ea: `0x180013980`
- end: `0x1800139e3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001395c`
- `0x1800139ec`

## callees

- `0x180001c00`
- `0x180013980`

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
0x180013980  mov     r10, rcx
0x180013983  mov     r11, rdx
0x180013986  mov     ecx, [r8]
0x180013989  and     ecx, 0FFFFFFF8h
0x18001398c  test    byte ptr [r8], 4
0x180013990  jz      short loc_1800139A7
0x180013992  mov     eax, [r8+8]
0x180013996  movsxd  r9, dword ptr [r8+4]
0x18001399a  neg     eax
0x18001399c  movsxd  rdx, eax
0x18001399f  add     r9, r10
0x1800139a2  and     r9, rdx
0x1800139a5  jmp     short loc_1800139AA
0x1800139a7  mov     r9, r10
0x1800139aa  movsxd  rax, ecx
0x1800139ad  mov     rdx, [rax+r9]
0x1800139b1  mov     rax, [r11+10h]
0x1800139b5  mov     ecx, [rax+8]
0x1800139b8  mov     rax, [r11+8]
0x1800139bc  test    byte ptr [rcx+rax+3], 0Fh
0x1800139c1  jz      short loc_1800139D5
0x1800139c3  movzx   eax, byte ptr [rcx+rax+3]
0x1800139c8  mov     ecx, 0FFFFFFF0h
0x1800139cd  and     rax, rcx
0x1800139d0  add     rax, r10
0x1800139d3  jmp     short loc_1800139D8
0x1800139d5  mov     rax, r10
0x1800139d8  xor     rdx, rax
0x1800139db  mov     rcx, rdx; StackCookie
0x1800139de  jmp     __security_check_cookie
```
