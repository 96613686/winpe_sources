# __GSHandlerCheckCommon

- ea: `0x180009b6c`
- end: `0x180009bcf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b48`
- `0x180009bd8`

## callees

- `0x180009b6c`
- `0x180009c90`

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
0x180009b6c  mov     r10, rcx
0x180009b6f  mov     r11, rdx
0x180009b72  mov     ecx, [r8]
0x180009b75  and     ecx, 0FFFFFFF8h
0x180009b78  test    byte ptr [r8], 4
0x180009b7c  jz      short loc_180009B93
0x180009b7e  mov     eax, [r8+8]
0x180009b82  movsxd  r9, dword ptr [r8+4]
0x180009b86  neg     eax
0x180009b88  movsxd  rdx, eax
0x180009b8b  add     r9, r10
0x180009b8e  and     r9, rdx
0x180009b91  jmp     short loc_180009B96
0x180009b93  mov     r9, r10
0x180009b96  movsxd  rax, ecx
0x180009b99  mov     rdx, [rax+r9]
0x180009b9d  mov     rax, [r11+10h]
0x180009ba1  mov     ecx, [rax+8]
0x180009ba4  mov     rax, [r11+8]
0x180009ba8  test    byte ptr [rcx+rax+3], 0Fh
0x180009bad  jz      short loc_180009BC1
0x180009baf  movzx   eax, byte ptr [rcx+rax+3]
0x180009bb4  mov     ecx, 0FFFFFFF0h
0x180009bb9  and     rax, rcx
0x180009bbc  add     rax, r10
0x180009bbf  jmp     short loc_180009BC4
0x180009bc1  mov     rax, r10
0x180009bc4  xor     rdx, rax
0x180009bc7  mov     rcx, rdx; StackCookie
0x180009bca  jmp     __security_check_cookie
```
