# __GSHandlerCheckCommon

- ea: `0x1800022c4`
- end: `0x180002327`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022a0`
- `0x180002330`
- `0x18000947c`
- `0x1800094e4`

## callees

- `0x1800022c4`
- `0x1800095c0`

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
0x1800022c4  mov     r10, rcx
0x1800022c7  mov     r11, rdx
0x1800022ca  mov     ecx, [r8]
0x1800022cd  and     ecx, 0FFFFFFF8h
0x1800022d0  test    byte ptr [r8], 4
0x1800022d4  jz      short loc_1800022EB
0x1800022d6  mov     eax, [r8+8]
0x1800022da  movsxd  r9, dword ptr [r8+4]
0x1800022de  neg     eax
0x1800022e0  movsxd  rdx, eax
0x1800022e3  add     r9, r10
0x1800022e6  and     r9, rdx
0x1800022e9  jmp     short loc_1800022EE
0x1800022eb  mov     r9, r10
0x1800022ee  movsxd  rax, ecx
0x1800022f1  mov     rdx, [rax+r9]
0x1800022f5  mov     rax, [r11+10h]
0x1800022f9  mov     ecx, [rax+8]
0x1800022fc  mov     rax, [r11+8]
0x180002300  test    byte ptr [rcx+rax+3], 0Fh
0x180002305  jz      short loc_180002319
0x180002307  movzx   eax, byte ptr [rcx+rax+3]
0x18000230c  mov     ecx, 0FFFFFFF0h
0x180002311  and     rax, rcx
0x180002314  add     rax, r10
0x180002317  jmp     short loc_18000231C
0x180002319  mov     rax, r10
0x18000231c  xor     rdx, rax
0x18000231f  mov     rcx, rdx; StackCookie
0x180002322  jmp     __security_check_cookie
```
