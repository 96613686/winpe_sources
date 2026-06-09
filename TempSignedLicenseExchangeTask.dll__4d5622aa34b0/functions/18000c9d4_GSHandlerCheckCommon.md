# __GSHandlerCheckCommon

- ea: `0x18000c9d4`
- end: `0x18000ca37`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9b0`

## callees

- `0x180001400`
- `0x18000c9d4`

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
0x18000c9d4  mov     r10, rcx
0x18000c9d7  mov     r11, rdx
0x18000c9da  mov     ecx, [r8]
0x18000c9dd  and     ecx, 0FFFFFFF8h
0x18000c9e0  test    byte ptr [r8], 4
0x18000c9e4  jz      short loc_18000C9FB
0x18000c9e6  mov     eax, [r8+8]
0x18000c9ea  movsxd  r9, dword ptr [r8+4]
0x18000c9ee  neg     eax
0x18000c9f0  movsxd  rdx, eax
0x18000c9f3  add     r9, r10
0x18000c9f6  and     r9, rdx
0x18000c9f9  jmp     short loc_18000C9FE
0x18000c9fb  mov     r9, r10
0x18000c9fe  movsxd  rax, ecx
0x18000ca01  mov     rdx, [rax+r9]
0x18000ca05  mov     rax, [r11+10h]
0x18000ca09  mov     ecx, [rax+8]
0x18000ca0c  mov     rax, [r11+8]
0x18000ca10  test    byte ptr [rcx+rax+3], 0Fh
0x18000ca15  jz      short loc_18000CA29
0x18000ca17  movzx   eax, byte ptr [rcx+rax+3]
0x18000ca1c  mov     ecx, 0FFFFFFF0h
0x18000ca21  and     rax, rcx
0x18000ca24  add     rax, r10
0x18000ca27  jmp     short loc_18000CA2C
0x18000ca29  mov     rax, r10
0x18000ca2c  xor     rdx, rax
0x18000ca2f  mov     rcx, rdx; StackCookie
0x18000ca32  jmp     __security_check_cookie
```
