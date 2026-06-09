# __GSHandlerCheckCommon

- ea: `0x180010e5c`
- end: `0x180010ebf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010e38`
- `0x180010ec8`

## callees

- `0x180010e5c`
- `0x180010f80`

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
0x180010e5c  mov     r10, rcx
0x180010e5f  mov     r11, rdx
0x180010e62  mov     ecx, [r8]
0x180010e65  and     ecx, 0FFFFFFF8h
0x180010e68  test    byte ptr [r8], 4
0x180010e6c  jz      short loc_180010E83
0x180010e6e  mov     eax, [r8+8]
0x180010e72  movsxd  r9, dword ptr [r8+4]
0x180010e76  neg     eax
0x180010e78  movsxd  rdx, eax
0x180010e7b  add     r9, r10
0x180010e7e  and     r9, rdx
0x180010e81  jmp     short loc_180010E86
0x180010e83  mov     r9, r10
0x180010e86  movsxd  rax, ecx
0x180010e89  mov     rdx, [rax+r9]
0x180010e8d  mov     rax, [r11+10h]
0x180010e91  mov     ecx, [rax+8]
0x180010e94  mov     rax, [r11+8]
0x180010e98  test    byte ptr [rcx+rax+3], 0Fh
0x180010e9d  jz      short loc_180010EB1
0x180010e9f  movzx   eax, byte ptr [rcx+rax+3]
0x180010ea4  mov     ecx, 0FFFFFFF0h
0x180010ea9  and     rax, rcx
0x180010eac  add     rax, r10
0x180010eaf  jmp     short loc_180010EB4
0x180010eb1  mov     rax, r10
0x180010eb4  xor     rdx, rax
0x180010eb7  mov     rcx, rdx; StackCookie
0x180010eba  jmp     __security_check_cookie
```
