# __GSHandlerCheckCommon

- ea: `0x1800049e4`
- end: `0x180004a3d`
- name: `__GSHandlerCheckCommon`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800049c4`
- `0x180004a40`

## callees

- `0x180003a70`
- `0x1800049e4`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = *(_QWORD *)(a2 + 16);
  v3 = *(_QWORD *)(a2 + 8) + *(unsigned int *)(result + 8);
  if ( (*(_BYTE *)(v3 + 3) & 0xF) != 0 )
    return *(_BYTE *)(v3 + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x1800049e4  push    rbx
0x1800049e6  mov     r11d, [r8]
0x1800049e9  mov     rbx, rdx
0x1800049ec  and     r11d, 0FFFFFFF8h
0x1800049f0  mov     r9, rcx
0x1800049f3  test    byte ptr [r8], 4
0x1800049f7  mov     r10, rcx
0x1800049fa  jz      short loc_180004A0F
0x1800049fc  mov     eax, [r8+8]
0x180004a00  movsxd  r10, dword ptr [r8+4]
0x180004a04  neg     eax
0x180004a06  add     r10, rcx
0x180004a09  movsxd  rcx, eax
0x180004a0c  and     r10, rcx
0x180004a0f  movsxd  rax, r11d
0x180004a12  mov     rdx, [rax+r10]
0x180004a16  mov     rax, [rbx+10h]
0x180004a1a  mov     ecx, [rax+8]
0x180004a1d  add     rcx, [rbx+8]
0x180004a21  test    byte ptr [rcx+3], 0Fh
0x180004a25  jz      short loc_180004A31
0x180004a27  movzx   eax, byte ptr [rcx+3]
0x180004a2b  and     eax, 0FFFFFFF0h
0x180004a2e  add     r9, rax
0x180004a31  xor     r9, rdx
0x180004a34  mov     rcx, r9; StackCookie
0x180004a37  pop     rbx
0x180004a38  jmp     __security_check_cookie
```
