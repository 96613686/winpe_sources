# __GSHandlerCheckCommon

- ea: `0x1800117c0`
- end: `0x180011823`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001179c`
- `0x18001182c`

## callees

- `0x180009850`
- `0x1800117c0`

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
0x1800117c0  mov     r10, rcx
0x1800117c3  mov     r11, rdx
0x1800117c6  mov     ecx, [r8]
0x1800117c9  and     ecx, 0FFFFFFF8h
0x1800117cc  test    byte ptr [r8], 4
0x1800117d0  jz      short loc_1800117E7
0x1800117d2  mov     eax, [r8+8]
0x1800117d6  movsxd  r9, dword ptr [r8+4]
0x1800117da  neg     eax
0x1800117dc  movsxd  rdx, eax
0x1800117df  add     r9, r10
0x1800117e2  and     r9, rdx
0x1800117e5  jmp     short loc_1800117EA
0x1800117e7  mov     r9, r10
0x1800117ea  movsxd  rax, ecx
0x1800117ed  mov     rdx, [rax+r9]
0x1800117f1  mov     rax, [r11+10h]
0x1800117f5  mov     ecx, [rax+8]
0x1800117f8  mov     rax, [r11+8]
0x1800117fc  test    byte ptr [rcx+rax+3], 0Fh
0x180011801  jz      short loc_180011815
0x180011803  movzx   eax, byte ptr [rcx+rax+3]
0x180011808  mov     ecx, 0FFFFFFF0h
0x18001180d  and     rax, rcx
0x180011810  add     rax, r10
0x180011813  jmp     short loc_180011818
0x180011815  mov     rax, r10
0x180011818  xor     rdx, rax
0x18001181b  mov     rcx, rdx; StackCookie
0x18001181e  jmp     __security_check_cookie
```
