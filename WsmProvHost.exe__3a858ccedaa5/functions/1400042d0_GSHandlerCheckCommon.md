# __GSHandlerCheckCommon

- ea: `0x1400042d0`
- end: `0x140004333`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400042ac`

## callees

- `0x1400042d0`
- `0x140004360`

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
0x1400042d0  mov     r10, rcx
0x1400042d3  mov     r11, rdx
0x1400042d6  mov     ecx, [r8]
0x1400042d9  and     ecx, 0FFFFFFF8h
0x1400042dc  test    byte ptr [r8], 4
0x1400042e0  jz      short loc_1400042F7
0x1400042e2  mov     eax, [r8+8]
0x1400042e6  movsxd  r9, dword ptr [r8+4]
0x1400042ea  neg     eax
0x1400042ec  movsxd  rdx, eax
0x1400042ef  add     r9, r10
0x1400042f2  and     r9, rdx
0x1400042f5  jmp     short loc_1400042FA
0x1400042f7  mov     r9, r10
0x1400042fa  movsxd  rax, ecx
0x1400042fd  mov     rdx, [rax+r9]
0x140004301  mov     rax, [r11+10h]
0x140004305  mov     ecx, [rax+8]
0x140004308  mov     rax, [r11+8]
0x14000430c  test    byte ptr [rcx+rax+3], 0Fh
0x140004311  jz      short loc_140004325
0x140004313  movzx   eax, byte ptr [rcx+rax+3]
0x140004318  mov     ecx, 0FFFFFFF0h
0x14000431d  and     rax, rcx
0x140004320  add     rax, r10
0x140004323  jmp     short loc_140004328
0x140004325  mov     rax, r10
0x140004328  xor     rdx, rax
0x14000432b  mov     rcx, rdx; StackCookie
0x14000432e  jmp     __security_check_cookie
```
