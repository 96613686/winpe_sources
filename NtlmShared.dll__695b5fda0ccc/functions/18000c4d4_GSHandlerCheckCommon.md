# __GSHandlerCheckCommon

- ea: `0x18000c4d4`
- end: `0x18000c537`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c4b0`

## callees

- `0x18000c4d4`
- `0x18000c560`

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
0x18000c4d4  mov     r10, rcx
0x18000c4d7  mov     r11, rdx
0x18000c4da  mov     ecx, [r8]
0x18000c4dd  and     ecx, 0FFFFFFF8h
0x18000c4e0  test    byte ptr [r8], 4
0x18000c4e4  jz      short loc_18000C4FB
0x18000c4e6  mov     eax, [r8+8]
0x18000c4ea  movsxd  r9, dword ptr [r8+4]
0x18000c4ee  neg     eax
0x18000c4f0  movsxd  rdx, eax
0x18000c4f3  add     r9, r10
0x18000c4f6  and     r9, rdx
0x18000c4f9  jmp     short loc_18000C4FE
0x18000c4fb  mov     r9, r10
0x18000c4fe  movsxd  rax, ecx
0x18000c501  mov     rdx, [rax+r9]
0x18000c505  mov     rax, [r11+10h]
0x18000c509  mov     ecx, [rax+8]
0x18000c50c  mov     rax, [r11+8]
0x18000c510  test    byte ptr [rcx+rax+3], 0Fh
0x18000c515  jz      short loc_18000C529
0x18000c517  movzx   eax, byte ptr [rcx+rax+3]
0x18000c51c  mov     ecx, 0FFFFFFF0h
0x18000c521  and     rax, rcx
0x18000c524  add     rax, r10
0x18000c527  jmp     short loc_18000C52C
0x18000c529  mov     rax, r10
0x18000c52c  xor     rdx, rax
0x18000c52f  mov     rcx, rdx; StackCookie
0x18000c532  jmp     __security_check_cookie
```
