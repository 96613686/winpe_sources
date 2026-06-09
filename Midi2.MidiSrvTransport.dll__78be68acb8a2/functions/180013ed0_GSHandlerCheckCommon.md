# __GSHandlerCheckCommon

- ea: `0x180013ed0`
- end: `0x180013f33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013eac`
- `0x180013f3c`
- `0x180013fa4`

## callees

- `0x180002470`
- `0x180013ed0`

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
0x180013ed0  mov     r10, rcx
0x180013ed3  mov     r11, rdx
0x180013ed6  mov     ecx, [r8]
0x180013ed9  and     ecx, 0FFFFFFF8h
0x180013edc  test    byte ptr [r8], 4
0x180013ee0  jz      short loc_180013EF7
0x180013ee2  mov     eax, [r8+8]
0x180013ee6  movsxd  r9, dword ptr [r8+4]
0x180013eea  neg     eax
0x180013eec  movsxd  rdx, eax
0x180013eef  add     r9, r10
0x180013ef2  and     r9, rdx
0x180013ef5  jmp     short loc_180013EFA
0x180013ef7  mov     r9, r10
0x180013efa  movsxd  rax, ecx
0x180013efd  mov     rdx, [rax+r9]
0x180013f01  mov     rax, [r11+10h]
0x180013f05  mov     ecx, [rax+8]
0x180013f08  mov     rax, [r11+8]
0x180013f0c  test    byte ptr [rcx+rax+3], 0Fh
0x180013f11  jz      short loc_180013F25
0x180013f13  movzx   eax, byte ptr [rcx+rax+3]
0x180013f18  mov     ecx, 0FFFFFFF0h
0x180013f1d  and     rax, rcx
0x180013f20  add     rax, r10
0x180013f23  jmp     short loc_180013F28
0x180013f25  mov     rax, r10
0x180013f28  xor     rdx, rax
0x180013f2b  mov     rcx, rdx; StackCookie
0x180013f2e  jmp     __security_check_cookie
```
