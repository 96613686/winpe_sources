# __GSHandlerCheckCommon

- ea: `0x18000dc14`
- end: `0x18000dc77`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dbf0`
- `0x18000dc80`

## callees

- `0x180002170`
- `0x18000dc14`

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
0x18000dc14  mov     r10, rcx
0x18000dc17  mov     r11, rdx
0x18000dc1a  mov     ecx, [r8]
0x18000dc1d  and     ecx, 0FFFFFFF8h
0x18000dc20  test    byte ptr [r8], 4
0x18000dc24  jz      short loc_18000DC3B
0x18000dc26  mov     eax, [r8+8]
0x18000dc2a  movsxd  r9, dword ptr [r8+4]
0x18000dc2e  neg     eax
0x18000dc30  movsxd  rdx, eax
0x18000dc33  add     r9, r10
0x18000dc36  and     r9, rdx
0x18000dc39  jmp     short loc_18000DC3E
0x18000dc3b  mov     r9, r10
0x18000dc3e  movsxd  rax, ecx
0x18000dc41  mov     rdx, [rax+r9]
0x18000dc45  mov     rax, [r11+10h]
0x18000dc49  mov     ecx, [rax+8]
0x18000dc4c  mov     rax, [r11+8]
0x18000dc50  test    byte ptr [rcx+rax+3], 0Fh
0x18000dc55  jz      short loc_18000DC69
0x18000dc57  movzx   eax, byte ptr [rcx+rax+3]
0x18000dc5c  mov     ecx, 0FFFFFFF0h
0x18000dc61  and     rax, rcx
0x18000dc64  add     rax, r10
0x18000dc67  jmp     short loc_18000DC6C
0x18000dc69  mov     rax, r10
0x18000dc6c  xor     rdx, rax
0x18000dc6f  mov     rcx, rdx; StackCookie
0x18000dc72  jmp     __security_check_cookie
```
