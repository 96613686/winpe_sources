# __GSHandlerCheckCommon

- ea: `0x1400191ec`
- end: `0x14001924f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400191c8`
- `0x140019258`
- `0x1400192c0`

## callees

- `0x1400029c0`
- `0x1400191ec`

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
0x1400191ec  mov     r10, rcx
0x1400191ef  mov     r11, rdx
0x1400191f2  mov     ecx, [r8]
0x1400191f5  and     ecx, 0FFFFFFF8h
0x1400191f8  test    byte ptr [r8], 4
0x1400191fc  jz      short loc_140019213
0x1400191fe  mov     eax, [r8+8]
0x140019202  movsxd  r9, dword ptr [r8+4]
0x140019206  neg     eax
0x140019208  movsxd  rdx, eax
0x14001920b  add     r9, r10
0x14001920e  and     r9, rdx
0x140019211  jmp     short loc_140019216
0x140019213  mov     r9, r10
0x140019216  movsxd  rax, ecx
0x140019219  mov     rdx, [rax+r9]
0x14001921d  mov     rax, [r11+10h]
0x140019221  mov     ecx, [rax+8]
0x140019224  mov     rax, [r11+8]
0x140019228  test    byte ptr [rcx+rax+3], 0Fh
0x14001922d  jz      short loc_140019241
0x14001922f  movzx   eax, byte ptr [rcx+rax+3]
0x140019234  mov     ecx, 0FFFFFFF0h
0x140019239  and     rax, rcx
0x14001923c  add     rax, r10
0x14001923f  jmp     short loc_140019244
0x140019241  mov     rax, r10
0x140019244  xor     rdx, rax
0x140019247  mov     rcx, rdx; StackCookie
0x14001924a  jmp     __security_check_cookie
```
