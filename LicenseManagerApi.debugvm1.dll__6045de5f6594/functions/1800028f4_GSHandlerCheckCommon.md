# __GSHandlerCheckCommon

- ea: `0x1800028f4`
- end: `0x180002957`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028d0`
- `0x180002960`

## callees

- `0x180001960`
- `0x1800028f4`

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
0x1800028f4  mov     r10, rcx
0x1800028f7  mov     r11, rdx
0x1800028fa  mov     ecx, [r8]
0x1800028fd  and     ecx, 0FFFFFFF8h
0x180002900  test    byte ptr [r8], 4
0x180002904  jz      short loc_18000291B
0x180002906  mov     eax, [r8+8]
0x18000290a  movsxd  r9, dword ptr [r8+4]
0x18000290e  neg     eax
0x180002910  movsxd  rdx, eax
0x180002913  add     r9, r10
0x180002916  and     r9, rdx
0x180002919  jmp     short loc_18000291E
0x18000291b  mov     r9, r10
0x18000291e  movsxd  rax, ecx
0x180002921  mov     rdx, [rax+r9]
0x180002925  mov     rax, [r11+10h]
0x180002929  mov     ecx, [rax+8]
0x18000292c  mov     rax, [r11+8]
0x180002930  test    byte ptr [rcx+rax+3], 0Fh
0x180002935  jz      short loc_180002949
0x180002937  movzx   eax, byte ptr [rcx+rax+3]
0x18000293c  mov     ecx, 0FFFFFFF0h
0x180002941  and     rax, rcx
0x180002944  add     rax, r10
0x180002947  jmp     short loc_18000294C
0x180002949  mov     rax, r10
0x18000294c  xor     rdx, rax
0x18000294f  mov     rcx, rdx; StackCookie
0x180002952  jmp     __security_check_cookie
```
