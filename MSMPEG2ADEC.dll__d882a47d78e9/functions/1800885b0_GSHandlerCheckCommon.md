# __GSHandlerCheckCommon

- ea: `0x1800885b0`
- end: `0x180088613`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008858c`
- `0x18008861c`

## callees

- `0x1800017b0`
- `0x1800885b0`

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
0x1800885b0  mov     r10, rcx
0x1800885b3  mov     r11, rdx
0x1800885b6  mov     ecx, [r8]
0x1800885b9  and     ecx, 0FFFFFFF8h
0x1800885bc  test    byte ptr [r8], 4
0x1800885c0  jz      short loc_1800885D7
0x1800885c2  mov     eax, [r8+8]
0x1800885c6  movsxd  r9, dword ptr [r8+4]
0x1800885ca  neg     eax
0x1800885cc  movsxd  rdx, eax
0x1800885cf  add     r9, r10
0x1800885d2  and     r9, rdx
0x1800885d5  jmp     short loc_1800885DA
0x1800885d7  mov     r9, r10
0x1800885da  movsxd  rax, ecx
0x1800885dd  mov     rdx, [rax+r9]
0x1800885e1  mov     rax, [r11+10h]
0x1800885e5  mov     ecx, [rax+8]
0x1800885e8  mov     rax, [r11+8]
0x1800885ec  test    byte ptr [rcx+rax+3], 0Fh
0x1800885f1  jz      short loc_180088605
0x1800885f3  movzx   eax, byte ptr [rcx+rax+3]
0x1800885f8  mov     ecx, 0FFFFFFF0h
0x1800885fd  and     rax, rcx
0x180088600  add     rax, r10
0x180088603  jmp     short loc_180088608
0x180088605  mov     rax, r10
0x180088608  xor     rdx, rax
0x18008860b  mov     rcx, rdx; StackCookie
0x18008860e  jmp     __security_check_cookie
```
