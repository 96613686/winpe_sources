# __GSHandlerCheckCommon

- ea: `0x14001358c`
- end: `0x1400135fc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013568`
- `0x140013604`

## callees

- `0x14001358c`
- `0x140013730`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14001358c  sub     rsp, 28h
0x140013590  mov     eax, [r8]
0x140013593  mov     r10, rcx
0x140013596  mov     ecx, eax
0x140013598  mov     r11, rdx
0x14001359b  and     ecx, 0FFFFFFF8h
0x14001359e  test    al, 4
0x1400135a0  jz      short loc_1400135B7
0x1400135a2  mov     eax, [r8+8]
0x1400135a6  movsxd  r9, dword ptr [r8+4]
0x1400135aa  neg     eax
0x1400135ac  movsxd  rdx, eax
0x1400135af  add     r9, r10
0x1400135b2  and     r9, rdx
0x1400135b5  jmp     short loc_1400135BA
0x1400135b7  mov     r9, r10
0x1400135ba  movsxd  rax, ecx
0x1400135bd  mov     rdx, [rax+r9]
0x1400135c1  mov     rax, [r11+10h]
0x1400135c5  mov     ecx, [rax+8]
0x1400135c8  mov     rax, [r11+8]
0x1400135cc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400135d2  test    r8b, 0Fh
0x1400135d6  jz      short loc_1400135E8
0x1400135d8  mov     eax, r8d
0x1400135db  mov     ecx, 0FFFFFFF0h
0x1400135e0  and     rax, rcx
0x1400135e3  add     rax, r10
0x1400135e6  jmp     short loc_1400135EB
0x1400135e8  mov     rax, r10
0x1400135eb  xor     rdx, rax
0x1400135ee  mov     rcx, rdx; StackCookie
0x1400135f1  call    __security_check_cookie
0x1400135f6  add     rsp, 28h
0x1400135fa  retn
```
