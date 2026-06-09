# __GSHandlerCheckCommon

- ea: `0x180003a9c`
- end: `0x180003aff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a78`
- `0x180027c3c`

## callees

- `0x180003520`
- `0x180003a9c`

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
0x180003a9c  mov     r10, rcx
0x180003a9f  mov     r11, rdx
0x180003aa2  mov     ecx, [r8]
0x180003aa5  and     ecx, 0FFFFFFF8h
0x180003aa8  test    byte ptr [r8], 4
0x180003aac  jz      short loc_180003AC3
0x180003aae  mov     eax, [r8+8]
0x180003ab2  movsxd  r9, dword ptr [r8+4]
0x180003ab6  neg     eax
0x180003ab8  movsxd  rdx, eax
0x180003abb  add     r9, r10
0x180003abe  and     r9, rdx
0x180003ac1  jmp     short loc_180003AC6
0x180003ac3  mov     r9, r10
0x180003ac6  movsxd  rax, ecx
0x180003ac9  mov     rdx, [rax+r9]
0x180003acd  mov     rax, [r11+10h]
0x180003ad1  mov     ecx, [rax+8]
0x180003ad4  mov     rax, [r11+8]
0x180003ad8  test    byte ptr [rcx+rax+3], 0Fh
0x180003add  jz      short loc_180003AF1
0x180003adf  movzx   eax, byte ptr [rcx+rax+3]
0x180003ae4  mov     ecx, 0FFFFFFF0h
0x180003ae9  and     rax, rcx
0x180003aec  add     rax, r10
0x180003aef  jmp     short loc_180003AF4
0x180003af1  mov     rax, r10
0x180003af4  xor     rdx, rax
0x180003af7  mov     rcx, rdx; StackCookie
0x180003afa  jmp     __security_check_cookie
```
