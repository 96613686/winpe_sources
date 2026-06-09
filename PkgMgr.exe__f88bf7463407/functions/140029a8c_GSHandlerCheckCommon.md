# __GSHandlerCheckCommon

- ea: `0x140029a8c`
- end: `0x140029aef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140029a68`
- `0x140029af8`

## callees

- `0x140002360`
- `0x140029a8c`

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
0x140029a8c  mov     r10, rcx
0x140029a8f  mov     r11, rdx
0x140029a92  mov     ecx, [r8]
0x140029a95  and     ecx, 0FFFFFFF8h
0x140029a98  test    byte ptr [r8], 4
0x140029a9c  jz      short loc_140029AB3
0x140029a9e  mov     eax, [r8+8]
0x140029aa2  movsxd  r9, dword ptr [r8+4]
0x140029aa6  neg     eax
0x140029aa8  movsxd  rdx, eax
0x140029aab  add     r9, r10
0x140029aae  and     r9, rdx
0x140029ab1  jmp     short loc_140029AB6
0x140029ab3  mov     r9, r10
0x140029ab6  movsxd  rax, ecx
0x140029ab9  mov     rdx, [rax+r9]
0x140029abd  mov     rax, [r11+10h]
0x140029ac1  mov     ecx, [rax+8]
0x140029ac4  mov     rax, [r11+8]
0x140029ac8  test    byte ptr [rcx+rax+3], 0Fh
0x140029acd  jz      short loc_140029AE1
0x140029acf  movzx   eax, byte ptr [rcx+rax+3]
0x140029ad4  mov     ecx, 0FFFFFFF0h
0x140029ad9  and     rax, rcx
0x140029adc  add     rax, r10
0x140029adf  jmp     short loc_140029AE4
0x140029ae1  mov     rax, r10
0x140029ae4  xor     rdx, rax
0x140029ae7  mov     rcx, rdx; StackCookie
0x140029aea  jmp     __security_check_cookie
```
