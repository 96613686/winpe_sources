# __GSHandlerCheckCommon

- ea: `0x14001114c`
- end: `0x1400111af`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011128`
- `0x1400111b8`
- `0x140011220`

## callees

- `0x1400023d0`
- `0x14001114c`

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
0x14001114c  mov     r10, rcx
0x14001114f  mov     r11, rdx
0x140011152  mov     ecx, [r8]
0x140011155  and     ecx, 0FFFFFFF8h
0x140011158  test    byte ptr [r8], 4
0x14001115c  jz      short loc_140011173
0x14001115e  mov     eax, [r8+8]
0x140011162  movsxd  r9, dword ptr [r8+4]
0x140011166  neg     eax
0x140011168  movsxd  rdx, eax
0x14001116b  add     r9, r10
0x14001116e  and     r9, rdx
0x140011171  jmp     short loc_140011176
0x140011173  mov     r9, r10
0x140011176  movsxd  rax, ecx
0x140011179  mov     rdx, [rax+r9]
0x14001117d  mov     rax, [r11+10h]
0x140011181  mov     ecx, [rax+8]
0x140011184  mov     rax, [r11+8]
0x140011188  test    byte ptr [rcx+rax+3], 0Fh
0x14001118d  jz      short loc_1400111A1
0x14001118f  movzx   eax, byte ptr [rcx+rax+3]
0x140011194  mov     ecx, 0FFFFFFF0h
0x140011199  and     rax, rcx
0x14001119c  add     rax, r10
0x14001119f  jmp     short loc_1400111A4
0x1400111a1  mov     rax, r10
0x1400111a4  xor     rdx, rax
0x1400111a7  mov     rcx, rdx; StackCookie
0x1400111aa  jmp     __security_check_cookie
```
