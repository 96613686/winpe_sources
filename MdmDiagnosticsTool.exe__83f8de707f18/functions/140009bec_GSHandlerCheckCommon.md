# __GSHandlerCheckCommon

- ea: `0x140009bec`
- end: `0x140009c4f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009bc8`
- `0x140009c58`

## callees

- `0x140009bec`
- `0x140009d00`

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
0x140009bec  mov     r10, rcx
0x140009bef  mov     r11, rdx
0x140009bf2  mov     ecx, [r8]
0x140009bf5  and     ecx, 0FFFFFFF8h
0x140009bf8  test    byte ptr [r8], 4
0x140009bfc  jz      short loc_140009C13
0x140009bfe  mov     eax, [r8+8]
0x140009c02  movsxd  r9, dword ptr [r8+4]
0x140009c06  neg     eax
0x140009c08  movsxd  rdx, eax
0x140009c0b  add     r9, r10
0x140009c0e  and     r9, rdx
0x140009c11  jmp     short loc_140009C16
0x140009c13  mov     r9, r10
0x140009c16  movsxd  rax, ecx
0x140009c19  mov     rdx, [rax+r9]
0x140009c1d  mov     rax, [r11+10h]
0x140009c21  mov     ecx, [rax+8]
0x140009c24  mov     rax, [r11+8]
0x140009c28  test    byte ptr [rcx+rax+3], 0Fh
0x140009c2d  jz      short loc_140009C41
0x140009c2f  movzx   eax, byte ptr [rcx+rax+3]
0x140009c34  mov     ecx, 0FFFFFFF0h
0x140009c39  and     rax, rcx
0x140009c3c  add     rax, r10
0x140009c3f  jmp     short loc_140009C44
0x140009c41  mov     rax, r10
0x140009c44  xor     rdx, rax
0x140009c47  mov     rcx, rdx; StackCookie
0x140009c4a  jmp     __security_check_cookie
```
