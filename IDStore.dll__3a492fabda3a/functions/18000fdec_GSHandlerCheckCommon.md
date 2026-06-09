# __GSHandlerCheckCommon

- ea: `0x18000fdec`
- end: `0x18000fe4f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fdc8`
- `0x18001963c`
- `0x1800196a4`

## callees

- `0x18000fdec`
- `0x180019750`

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
0x18000fdec  mov     r10, rcx
0x18000fdef  mov     r11, rdx
0x18000fdf2  mov     ecx, [r8]
0x18000fdf5  and     ecx, 0FFFFFFF8h
0x18000fdf8  test    byte ptr [r8], 4
0x18000fdfc  jz      short loc_18000FE13
0x18000fdfe  mov     eax, [r8+8]
0x18000fe02  movsxd  r9, dword ptr [r8+4]
0x18000fe06  neg     eax
0x18000fe08  movsxd  rdx, eax
0x18000fe0b  add     r9, r10
0x18000fe0e  and     r9, rdx
0x18000fe11  jmp     short loc_18000FE16
0x18000fe13  mov     r9, r10
0x18000fe16  movsxd  rax, ecx
0x18000fe19  mov     rdx, [rax+r9]
0x18000fe1d  mov     rax, [r11+10h]
0x18000fe21  mov     ecx, [rax+8]
0x18000fe24  mov     rax, [r11+8]
0x18000fe28  test    byte ptr [rcx+rax+3], 0Fh
0x18000fe2d  jz      short loc_18000FE41
0x18000fe2f  movzx   eax, byte ptr [rcx+rax+3]
0x18000fe34  mov     ecx, 0FFFFFFF0h
0x18000fe39  and     rax, rcx
0x18000fe3c  add     rax, r10
0x18000fe3f  jmp     short loc_18000FE44
0x18000fe41  mov     rax, r10
0x18000fe44  xor     rdx, rax
0x18000fe47  mov     rcx, rdx; StackCookie
0x18000fe4a  jmp     __security_check_cookie
```
