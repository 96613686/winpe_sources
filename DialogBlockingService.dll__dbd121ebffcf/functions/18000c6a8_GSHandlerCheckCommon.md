# __GSHandlerCheckCommon

- ea: `0x18000c6a8`
- end: `0x18000c70b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c684`
- `0x18000c714`

## callees

- `0x180001620`
- `0x18000c6a8`

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
0x18000c6a8  mov     r10, rcx
0x18000c6ab  mov     r11, rdx
0x18000c6ae  mov     ecx, [r8]
0x18000c6b1  and     ecx, 0FFFFFFF8h
0x18000c6b4  test    byte ptr [r8], 4
0x18000c6b8  jz      short loc_18000C6CF
0x18000c6ba  mov     eax, [r8+8]
0x18000c6be  movsxd  r9, dword ptr [r8+4]
0x18000c6c2  neg     eax
0x18000c6c4  movsxd  rdx, eax
0x18000c6c7  add     r9, r10
0x18000c6ca  and     r9, rdx
0x18000c6cd  jmp     short loc_18000C6D2
0x18000c6cf  mov     r9, r10
0x18000c6d2  movsxd  rax, ecx
0x18000c6d5  mov     rdx, [rax+r9]
0x18000c6d9  mov     rax, [r11+10h]
0x18000c6dd  mov     ecx, [rax+8]
0x18000c6e0  mov     rax, [r11+8]
0x18000c6e4  test    byte ptr [rcx+rax+3], 0Fh
0x18000c6e9  jz      short loc_18000C6FD
0x18000c6eb  movzx   eax, byte ptr [rcx+rax+3]
0x18000c6f0  mov     ecx, 0FFFFFFF0h
0x18000c6f5  and     rax, rcx
0x18000c6f8  add     rax, r10
0x18000c6fb  jmp     short loc_18000C700
0x18000c6fd  mov     rax, r10
0x18000c700  xor     rdx, rax
0x18000c703  mov     rcx, rdx; StackCookie
0x18000c706  jmp     __security_check_cookie
```
