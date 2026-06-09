# __GSHandlerCheckCommon

- ea: `0x1800096dc`
- end: `0x18000973f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800096b8`

## callees

- `0x1800096dc`
- `0x180009780`

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
0x1800096dc  mov     r10, rcx
0x1800096df  mov     r11, rdx
0x1800096e2  mov     ecx, [r8]
0x1800096e5  and     ecx, 0FFFFFFF8h
0x1800096e8  test    byte ptr [r8], 4
0x1800096ec  jz      short loc_180009703
0x1800096ee  mov     eax, [r8+8]
0x1800096f2  movsxd  r9, dword ptr [r8+4]
0x1800096f6  neg     eax
0x1800096f8  movsxd  rdx, eax
0x1800096fb  add     r9, r10
0x1800096fe  and     r9, rdx
0x180009701  jmp     short loc_180009706
0x180009703  mov     r9, r10
0x180009706  movsxd  rax, ecx
0x180009709  mov     rdx, [rax+r9]
0x18000970d  mov     rax, [r11+10h]
0x180009711  mov     ecx, [rax+8]
0x180009714  mov     rax, [r11+8]
0x180009718  test    byte ptr [rcx+rax+3], 0Fh
0x18000971d  jz      short loc_180009731
0x18000971f  movzx   eax, byte ptr [rcx+rax+3]
0x180009724  mov     ecx, 0FFFFFFF0h
0x180009729  and     rax, rcx
0x18000972c  add     rax, r10
0x18000972f  jmp     short loc_180009734
0x180009731  mov     rax, r10
0x180009734  xor     rdx, rax
0x180009737  mov     rcx, rdx; StackCookie
0x18000973a  jmp     __security_check_cookie
```
