# __GSHandlerCheckCommon

- ea: `0x18001b8c4`
- end: `0x18001b927`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b8a0`

## callees

- `0x18001b8c4`
- `0x18001b980`

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
0x18001b8c4  mov     r10, rcx
0x18001b8c7  mov     r11, rdx
0x18001b8ca  mov     ecx, [r8]
0x18001b8cd  and     ecx, 0FFFFFFF8h
0x18001b8d0  test    byte ptr [r8], 4
0x18001b8d4  jz      short loc_18001B8EB
0x18001b8d6  mov     eax, [r8+8]
0x18001b8da  movsxd  r9, dword ptr [r8+4]
0x18001b8de  neg     eax
0x18001b8e0  movsxd  rdx, eax
0x18001b8e3  add     r9, r10
0x18001b8e6  and     r9, rdx
0x18001b8e9  jmp     short loc_18001B8EE
0x18001b8eb  mov     r9, r10
0x18001b8ee  movsxd  rax, ecx
0x18001b8f1  mov     rdx, [rax+r9]
0x18001b8f5  mov     rax, [r11+10h]
0x18001b8f9  mov     ecx, [rax+8]
0x18001b8fc  mov     rax, [r11+8]
0x18001b900  test    byte ptr [rcx+rax+3], 0Fh
0x18001b905  jz      short loc_18001B919
0x18001b907  movzx   eax, byte ptr [rcx+rax+3]
0x18001b90c  mov     ecx, 0FFFFFFF0h
0x18001b911  and     rax, rcx
0x18001b914  add     rax, r10
0x18001b917  jmp     short loc_18001B91C
0x18001b919  mov     rax, r10
0x18001b91c  xor     rdx, rax
0x18001b91f  mov     rcx, rdx; StackCookie
0x18001b922  jmp     __security_check_cookie
```
