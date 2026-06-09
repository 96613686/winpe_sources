# __GSHandlerCheckCommon

- ea: `0x180002b6c`
- end: `0x180002bcf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b48`
- `0x18000a9c0`

## callees

- `0x180002b6c`
- `0x18000aa50`

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
0x180002b6c  mov     r10, rcx
0x180002b6f  mov     r11, rdx
0x180002b72  mov     ecx, [r8]
0x180002b75  and     ecx, 0FFFFFFF8h
0x180002b78  test    byte ptr [r8], 4
0x180002b7c  jz      short loc_180002B93
0x180002b7e  mov     eax, [r8+8]
0x180002b82  movsxd  r9, dword ptr [r8+4]
0x180002b86  neg     eax
0x180002b88  movsxd  rdx, eax
0x180002b8b  add     r9, r10
0x180002b8e  and     r9, rdx
0x180002b91  jmp     short loc_180002B96
0x180002b93  mov     r9, r10
0x180002b96  movsxd  rax, ecx
0x180002b99  mov     rdx, [rax+r9]
0x180002b9d  mov     rax, [r11+10h]
0x180002ba1  mov     ecx, [rax+8]
0x180002ba4  mov     rax, [r11+8]
0x180002ba8  test    byte ptr [rcx+rax+3], 0Fh
0x180002bad  jz      short loc_180002BC1
0x180002baf  movzx   eax, byte ptr [rcx+rax+3]
0x180002bb4  mov     ecx, 0FFFFFFF0h
0x180002bb9  and     rax, rcx
0x180002bbc  add     rax, r10
0x180002bbf  jmp     short loc_180002BC4
0x180002bc1  mov     rax, r10
0x180002bc4  xor     rdx, rax
0x180002bc7  mov     rcx, rdx; StackCookie
0x180002bca  jmp     __security_check_cookie
```
