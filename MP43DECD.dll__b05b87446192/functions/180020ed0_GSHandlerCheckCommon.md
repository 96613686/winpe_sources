# __GSHandlerCheckCommon

- ea: `0x180020ed0`
- end: `0x180020f33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020eac`

## callees

- `0x180001880`
- `0x180020ed0`

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
0x180020ed0  mov     r10, rcx
0x180020ed3  mov     r11, rdx
0x180020ed6  mov     ecx, [r8]
0x180020ed9  and     ecx, 0FFFFFFF8h
0x180020edc  test    byte ptr [r8], 4
0x180020ee0  jz      short loc_180020EF7
0x180020ee2  mov     eax, [r8+8]
0x180020ee6  movsxd  r9, dword ptr [r8+4]
0x180020eea  neg     eax
0x180020eec  movsxd  rdx, eax
0x180020eef  add     r9, r10
0x180020ef2  and     r9, rdx
0x180020ef5  jmp     short loc_180020EFA
0x180020ef7  mov     r9, r10
0x180020efa  movsxd  rax, ecx
0x180020efd  mov     rdx, [rax+r9]
0x180020f01  mov     rax, [r11+10h]
0x180020f05  mov     ecx, [rax+8]
0x180020f08  mov     rax, [r11+8]
0x180020f0c  test    byte ptr [rcx+rax+3], 0Fh
0x180020f11  jz      short loc_180020F25
0x180020f13  movzx   eax, byte ptr [rcx+rax+3]
0x180020f18  mov     ecx, 0FFFFFFF0h
0x180020f1d  and     rax, rcx
0x180020f20  add     rax, r10
0x180020f23  jmp     short loc_180020F28
0x180020f25  mov     rax, r10
0x180020f28  xor     rdx, rax
0x180020f2b  mov     rcx, rdx; StackCookie
0x180020f2e  jmp     __security_check_cookie
```
