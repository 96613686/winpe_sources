# __GSHandlerCheckCommon

- ea: `0x180006460`
- end: `0x1800064c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000643c`
- `0x1800064cc`

## callees

- `0x180006460`
- `0x180006570`

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
0x180006460  mov     r10, rcx
0x180006463  mov     r11, rdx
0x180006466  mov     ecx, [r8]
0x180006469  and     ecx, 0FFFFFFF8h
0x18000646c  test    byte ptr [r8], 4
0x180006470  jz      short loc_180006487
0x180006472  mov     eax, [r8+8]
0x180006476  movsxd  r9, dword ptr [r8+4]
0x18000647a  neg     eax
0x18000647c  movsxd  rdx, eax
0x18000647f  add     r9, r10
0x180006482  and     r9, rdx
0x180006485  jmp     short loc_18000648A
0x180006487  mov     r9, r10
0x18000648a  movsxd  rax, ecx
0x18000648d  mov     rdx, [rax+r9]
0x180006491  mov     rax, [r11+10h]
0x180006495  mov     ecx, [rax+8]
0x180006498  mov     rax, [r11+8]
0x18000649c  test    byte ptr [rcx+rax+3], 0Fh
0x1800064a1  jz      short loc_1800064B5
0x1800064a3  movzx   eax, byte ptr [rcx+rax+3]
0x1800064a8  mov     ecx, 0FFFFFFF0h
0x1800064ad  and     rax, rcx
0x1800064b0  add     rax, r10
0x1800064b3  jmp     short loc_1800064B8
0x1800064b5  mov     rax, r10
0x1800064b8  xor     rdx, rax
0x1800064bb  mov     rcx, rdx; StackCookie
0x1800064be  jmp     __security_check_cookie
```
