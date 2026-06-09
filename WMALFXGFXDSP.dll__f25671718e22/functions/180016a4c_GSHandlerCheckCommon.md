# __GSHandlerCheckCommon

- ea: `0x180016a4c`
- end: `0x180016aaf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016a28`

## callees

- `0x180015190`
- `0x180016a4c`

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
0x180016a4c  mov     r10, rcx
0x180016a4f  mov     r11, rdx
0x180016a52  mov     ecx, [r8]
0x180016a55  and     ecx, 0FFFFFFF8h
0x180016a58  test    byte ptr [r8], 4
0x180016a5c  jz      short loc_180016A73
0x180016a5e  mov     eax, [r8+8]
0x180016a62  movsxd  r9, dword ptr [r8+4]
0x180016a66  neg     eax
0x180016a68  movsxd  rdx, eax
0x180016a6b  add     r9, r10
0x180016a6e  and     r9, rdx
0x180016a71  jmp     short loc_180016A76
0x180016a73  mov     r9, r10
0x180016a76  movsxd  rax, ecx
0x180016a79  mov     rdx, [rax+r9]
0x180016a7d  mov     rax, [r11+10h]
0x180016a81  mov     ecx, [rax+8]
0x180016a84  mov     rax, [r11+8]
0x180016a88  test    byte ptr [rcx+rax+3], 0Fh
0x180016a8d  jz      short loc_180016AA1
0x180016a8f  movzx   eax, byte ptr [rcx+rax+3]
0x180016a94  mov     ecx, 0FFFFFFF0h
0x180016a99  and     rax, rcx
0x180016a9c  add     rax, r10
0x180016a9f  jmp     short loc_180016AA4
0x180016aa1  mov     rax, r10
0x180016aa4  xor     rdx, rax
0x180016aa7  mov     rcx, rdx; StackCookie
0x180016aaa  jmp     __security_check_cookie
```
