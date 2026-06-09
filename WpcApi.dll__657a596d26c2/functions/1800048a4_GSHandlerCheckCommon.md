# __GSHandlerCheckCommon

- ea: `0x1800048a4`
- end: `0x180004907`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004880`
- `0x180028f6c`

## callees

- `0x1800032a0`
- `0x1800048a4`

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
0x1800048a4  mov     r10, rcx
0x1800048a7  mov     r11, rdx
0x1800048aa  mov     ecx, [r8]
0x1800048ad  and     ecx, 0FFFFFFF8h
0x1800048b0  test    byte ptr [r8], 4
0x1800048b4  jz      short loc_1800048CB
0x1800048b6  mov     eax, [r8+8]
0x1800048ba  movsxd  r9, dword ptr [r8+4]
0x1800048be  neg     eax
0x1800048c0  movsxd  rdx, eax
0x1800048c3  add     r9, r10
0x1800048c6  and     r9, rdx
0x1800048c9  jmp     short loc_1800048CE
0x1800048cb  mov     r9, r10
0x1800048ce  movsxd  rax, ecx
0x1800048d1  mov     rdx, [rax+r9]
0x1800048d5  mov     rax, [r11+10h]
0x1800048d9  mov     ecx, [rax+8]
0x1800048dc  mov     rax, [r11+8]
0x1800048e0  test    byte ptr [rcx+rax+3], 0Fh
0x1800048e5  jz      short loc_1800048F9
0x1800048e7  movzx   eax, byte ptr [rcx+rax+3]
0x1800048ec  mov     ecx, 0FFFFFFF0h
0x1800048f1  and     rax, rcx
0x1800048f4  add     rax, r10
0x1800048f7  jmp     short loc_1800048FC
0x1800048f9  mov     rax, r10
0x1800048fc  xor     rdx, rax
0x1800048ff  mov     rcx, rdx; StackCookie
0x180004902  jmp     __security_check_cookie
```
