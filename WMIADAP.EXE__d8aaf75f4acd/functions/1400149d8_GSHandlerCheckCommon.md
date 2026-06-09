# __GSHandlerCheckCommon

- ea: `0x1400149d8`
- end: `0x140014a3b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400149b4`
- `0x140014a44`

## callees

- `0x1400149d8`
- `0x140014ad0`

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
0x1400149d8  mov     r10, rcx
0x1400149db  mov     r11, rdx
0x1400149de  mov     ecx, [r8]
0x1400149e1  and     ecx, 0FFFFFFF8h
0x1400149e4  test    byte ptr [r8], 4
0x1400149e8  jz      short loc_1400149FF
0x1400149ea  mov     eax, [r8+8]
0x1400149ee  movsxd  r9, dword ptr [r8+4]
0x1400149f2  neg     eax
0x1400149f4  movsxd  rdx, eax
0x1400149f7  add     r9, r10
0x1400149fa  and     r9, rdx
0x1400149fd  jmp     short loc_140014A02
0x1400149ff  mov     r9, r10
0x140014a02  movsxd  rax, ecx
0x140014a05  mov     rdx, [rax+r9]
0x140014a09  mov     rax, [r11+10h]
0x140014a0d  mov     ecx, [rax+8]
0x140014a10  mov     rax, [r11+8]
0x140014a14  test    byte ptr [rcx+rax+3], 0Fh
0x140014a19  jz      short loc_140014A2D
0x140014a1b  movzx   eax, byte ptr [rcx+rax+3]
0x140014a20  mov     ecx, 0FFFFFFF0h
0x140014a25  and     rax, rcx
0x140014a28  add     rax, r10
0x140014a2b  jmp     short loc_140014A30
0x140014a2d  mov     rax, r10
0x140014a30  xor     rdx, rax
0x140014a33  mov     rcx, rdx; StackCookie
0x140014a36  jmp     __security_check_cookie
```
