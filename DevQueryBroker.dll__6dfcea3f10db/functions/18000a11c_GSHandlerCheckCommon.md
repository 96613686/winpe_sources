# __GSHandlerCheckCommon

- ea: `0x18000a11c`
- end: `0x18000a17f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a0f8`

## callees

- `0x18000a11c`
- `0x18000a1d0`

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
0x18000a11c  mov     r10, rcx
0x18000a11f  mov     r11, rdx
0x18000a122  mov     ecx, [r8]
0x18000a125  and     ecx, 0FFFFFFF8h
0x18000a128  test    byte ptr [r8], 4
0x18000a12c  jz      short loc_18000A143
0x18000a12e  mov     eax, [r8+8]
0x18000a132  movsxd  r9, dword ptr [r8+4]
0x18000a136  neg     eax
0x18000a138  movsxd  rdx, eax
0x18000a13b  add     r9, r10
0x18000a13e  and     r9, rdx
0x18000a141  jmp     short loc_18000A146
0x18000a143  mov     r9, r10
0x18000a146  movsxd  rax, ecx
0x18000a149  mov     rdx, [rax+r9]
0x18000a14d  mov     rax, [r11+10h]
0x18000a151  mov     ecx, [rax+8]
0x18000a154  mov     rax, [r11+8]
0x18000a158  test    byte ptr [rcx+rax+3], 0Fh
0x18000a15d  jz      short loc_18000A171
0x18000a15f  movzx   eax, byte ptr [rcx+rax+3]
0x18000a164  mov     ecx, 0FFFFFFF0h
0x18000a169  and     rax, rcx
0x18000a16c  add     rax, r10
0x18000a16f  jmp     short loc_18000A174
0x18000a171  mov     rax, r10
0x18000a174  xor     rdx, rax
0x18000a177  mov     rcx, rdx; StackCookie
0x18000a17a  jmp     __security_check_cookie
```
