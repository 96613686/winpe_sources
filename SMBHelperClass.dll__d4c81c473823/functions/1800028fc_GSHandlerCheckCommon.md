# __GSHandlerCheckCommon

- ea: `0x1800028fc`
- end: `0x18000295f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028d8`
- `0x18000fb78`

## callees

- `0x1800028fc`
- `0x18000fc30`

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
0x1800028fc  mov     r10, rcx
0x1800028ff  mov     r11, rdx
0x180002902  mov     ecx, [r8]
0x180002905  and     ecx, 0FFFFFFF8h
0x180002908  test    byte ptr [r8], 4
0x18000290c  jz      short loc_180002923
0x18000290e  mov     eax, [r8+8]
0x180002912  movsxd  r9, dword ptr [r8+4]
0x180002916  neg     eax
0x180002918  movsxd  rdx, eax
0x18000291b  add     r9, r10
0x18000291e  and     r9, rdx
0x180002921  jmp     short loc_180002926
0x180002923  mov     r9, r10
0x180002926  movsxd  rax, ecx
0x180002929  mov     rdx, [rax+r9]
0x18000292d  mov     rax, [r11+10h]
0x180002931  mov     ecx, [rax+8]
0x180002934  mov     rax, [r11+8]
0x180002938  test    byte ptr [rcx+rax+3], 0Fh
0x18000293d  jz      short loc_180002951
0x18000293f  movzx   eax, byte ptr [rcx+rax+3]
0x180002944  mov     ecx, 0FFFFFFF0h
0x180002949  and     rax, rcx
0x18000294c  add     rax, r10
0x18000294f  jmp     short loc_180002954
0x180002951  mov     rax, r10
0x180002954  xor     rdx, rax
0x180002957  mov     rcx, rdx; StackCookie
0x18000295a  jmp     __security_check_cookie
```
