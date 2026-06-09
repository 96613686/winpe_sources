# __GSHandlerCheckCommon

- ea: `0x1800290d0`
- end: `0x180029133`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800290ac`
- `0x18002913c`

## callees

- `0x180002350`
- `0x1800290d0`

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
0x1800290d0  mov     r10, rcx
0x1800290d3  mov     r11, rdx
0x1800290d6  mov     ecx, [r8]
0x1800290d9  and     ecx, 0FFFFFFF8h
0x1800290dc  test    byte ptr [r8], 4
0x1800290e0  jz      short loc_1800290F7
0x1800290e2  mov     eax, [r8+8]
0x1800290e6  movsxd  r9, dword ptr [r8+4]
0x1800290ea  neg     eax
0x1800290ec  movsxd  rdx, eax
0x1800290ef  add     r9, r10
0x1800290f2  and     r9, rdx
0x1800290f5  jmp     short loc_1800290FA
0x1800290f7  mov     r9, r10
0x1800290fa  movsxd  rax, ecx
0x1800290fd  mov     rdx, [rax+r9]
0x180029101  mov     rax, [r11+10h]
0x180029105  mov     ecx, [rax+8]
0x180029108  mov     rax, [r11+8]
0x18002910c  test    byte ptr [rcx+rax+3], 0Fh
0x180029111  jz      short loc_180029125
0x180029113  movzx   eax, byte ptr [rcx+rax+3]
0x180029118  mov     ecx, 0FFFFFFF0h
0x18002911d  and     rax, rcx
0x180029120  add     rax, r10
0x180029123  jmp     short loc_180029128
0x180029125  mov     rax, r10
0x180029128  xor     rdx, rax
0x18002912b  mov     rcx, rdx; StackCookie
0x18002912e  jmp     __security_check_cookie
```
