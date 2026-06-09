# __GSHandlerCheckCommon

- ea: `0x1400113e4`
- end: `0x140011447`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400113c0`
- `0x140011450`

## callees

- `0x1400016a0`
- `0x1400113e4`

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
0x1400113e4  mov     r10, rcx
0x1400113e7  mov     r11, rdx
0x1400113ea  mov     ecx, [r8]
0x1400113ed  and     ecx, 0FFFFFFF8h
0x1400113f0  test    byte ptr [r8], 4
0x1400113f4  jz      short loc_14001140B
0x1400113f6  mov     eax, [r8+8]
0x1400113fa  movsxd  r9, dword ptr [r8+4]
0x1400113fe  neg     eax
0x140011400  movsxd  rdx, eax
0x140011403  add     r9, r10
0x140011406  and     r9, rdx
0x140011409  jmp     short loc_14001140E
0x14001140b  mov     r9, r10
0x14001140e  movsxd  rax, ecx
0x140011411  mov     rdx, [rax+r9]
0x140011415  mov     rax, [r11+10h]
0x140011419  mov     ecx, [rax+8]
0x14001141c  mov     rax, [r11+8]
0x140011420  test    byte ptr [rcx+rax+3], 0Fh
0x140011425  jz      short loc_140011439
0x140011427  movzx   eax, byte ptr [rcx+rax+3]
0x14001142c  mov     ecx, 0FFFFFFF0h
0x140011431  and     rax, rcx
0x140011434  add     rax, r10
0x140011437  jmp     short loc_14001143C
0x140011439  mov     rax, r10
0x14001143c  xor     rdx, rax
0x14001143f  mov     rcx, rdx; StackCookie
0x140011442  jmp     __security_check_cookie
```
