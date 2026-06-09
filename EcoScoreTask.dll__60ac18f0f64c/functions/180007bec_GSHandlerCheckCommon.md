# __GSHandlerCheckCommon

- ea: `0x180007bec`
- end: `0x180007c4f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007bc8`

## callees

- `0x180007bec`
- `0x180007c90`

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
0x180007bec  mov     r10, rcx
0x180007bef  mov     r11, rdx
0x180007bf2  mov     ecx, [r8]
0x180007bf5  and     ecx, 0FFFFFFF8h
0x180007bf8  test    byte ptr [r8], 4
0x180007bfc  jz      short loc_180007C13
0x180007bfe  mov     eax, [r8+8]
0x180007c02  movsxd  r9, dword ptr [r8+4]
0x180007c06  neg     eax
0x180007c08  movsxd  rdx, eax
0x180007c0b  add     r9, r10
0x180007c0e  and     r9, rdx
0x180007c11  jmp     short loc_180007C16
0x180007c13  mov     r9, r10
0x180007c16  movsxd  rax, ecx
0x180007c19  mov     rdx, [rax+r9]
0x180007c1d  mov     rax, [r11+10h]
0x180007c21  mov     ecx, [rax+8]
0x180007c24  mov     rax, [r11+8]
0x180007c28  test    byte ptr [rcx+rax+3], 0Fh
0x180007c2d  jz      short loc_180007C41
0x180007c2f  movzx   eax, byte ptr [rcx+rax+3]
0x180007c34  mov     ecx, 0FFFFFFF0h
0x180007c39  and     rax, rcx
0x180007c3c  add     rax, r10
0x180007c3f  jmp     short loc_180007C44
0x180007c41  mov     rax, r10
0x180007c44  xor     rdx, rax
0x180007c47  mov     rcx, rdx; StackCookie
0x180007c4a  jmp     __security_check_cookie
```
