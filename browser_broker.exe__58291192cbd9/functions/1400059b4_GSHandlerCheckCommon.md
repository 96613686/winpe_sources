# __GSHandlerCheckCommon

- ea: `0x1400059b4`
- end: `0x140005a17`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005990`

## callees

- `0x140001600`
- `0x1400059b4`

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
0x1400059b4  mov     r10, rcx
0x1400059b7  mov     r11, rdx
0x1400059ba  mov     ecx, [r8]
0x1400059bd  and     ecx, 0FFFFFFF8h
0x1400059c0  test    byte ptr [r8], 4
0x1400059c4  jz      short loc_1400059DB
0x1400059c6  mov     eax, [r8+8]
0x1400059ca  movsxd  r9, dword ptr [r8+4]
0x1400059ce  neg     eax
0x1400059d0  movsxd  rdx, eax
0x1400059d3  add     r9, r10
0x1400059d6  and     r9, rdx
0x1400059d9  jmp     short loc_1400059DE
0x1400059db  mov     r9, r10
0x1400059de  movsxd  rax, ecx
0x1400059e1  mov     rdx, [rax+r9]
0x1400059e5  mov     rax, [r11+10h]
0x1400059e9  mov     ecx, [rax+8]
0x1400059ec  mov     rax, [r11+8]
0x1400059f0  test    byte ptr [rcx+rax+3], 0Fh
0x1400059f5  jz      short loc_140005A09
0x1400059f7  movzx   eax, byte ptr [rcx+rax+3]
0x1400059fc  mov     ecx, 0FFFFFFF0h
0x140005a01  and     rax, rcx
0x140005a04  add     rax, r10
0x140005a07  jmp     short loc_140005A0C
0x140005a09  mov     rax, r10
0x140005a0c  xor     rdx, rax
0x140005a0f  mov     rcx, rdx; StackCookie
0x140005a12  jmp     __security_check_cookie
```
