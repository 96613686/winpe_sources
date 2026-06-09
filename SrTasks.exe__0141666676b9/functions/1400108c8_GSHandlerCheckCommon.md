# __GSHandlerCheckCommon

- ea: `0x1400108c8`
- end: `0x14001092b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400108a4`

## callees

- `0x1400108c8`
- `0x140010980`

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
0x1400108c8  mov     r10, rcx
0x1400108cb  mov     r11, rdx
0x1400108ce  mov     ecx, [r8]
0x1400108d1  and     ecx, 0FFFFFFF8h
0x1400108d4  test    byte ptr [r8], 4
0x1400108d8  jz      short loc_1400108EF
0x1400108da  mov     eax, [r8+8]
0x1400108de  movsxd  r9, dword ptr [r8+4]
0x1400108e2  neg     eax
0x1400108e4  movsxd  rdx, eax
0x1400108e7  add     r9, r10
0x1400108ea  and     r9, rdx
0x1400108ed  jmp     short loc_1400108F2
0x1400108ef  mov     r9, r10
0x1400108f2  movsxd  rax, ecx
0x1400108f5  mov     rdx, [rax+r9]
0x1400108f9  mov     rax, [r11+10h]
0x1400108fd  mov     ecx, [rax+8]
0x140010900  mov     rax, [r11+8]
0x140010904  test    byte ptr [rcx+rax+3], 0Fh
0x140010909  jz      short loc_14001091D
0x14001090b  movzx   eax, byte ptr [rcx+rax+3]
0x140010910  mov     ecx, 0FFFFFFF0h
0x140010915  and     rax, rcx
0x140010918  add     rax, r10
0x14001091b  jmp     short loc_140010920
0x14001091d  mov     rax, r10
0x140010920  xor     rdx, rax
0x140010923  mov     rcx, rdx; StackCookie
0x140010926  jmp     __security_check_cookie
```
