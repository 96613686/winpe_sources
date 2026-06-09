# __GSHandlerCheckCommon

- ea: `0x14000278c`
- end: `0x1400027ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002768`
- `0x140015a4c`

## callees

- `0x14000278c`
- `0x140015b00`

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
0x14000278c  mov     r10, rcx
0x14000278f  mov     r11, rdx
0x140002792  mov     ecx, [r8]
0x140002795  and     ecx, 0FFFFFFF8h
0x140002798  test    byte ptr [r8], 4
0x14000279c  jz      short loc_1400027B3
0x14000279e  mov     eax, [r8+8]
0x1400027a2  movsxd  r9, dword ptr [r8+4]
0x1400027a6  neg     eax
0x1400027a8  movsxd  rdx, eax
0x1400027ab  add     r9, r10
0x1400027ae  and     r9, rdx
0x1400027b1  jmp     short loc_1400027B6
0x1400027b3  mov     r9, r10
0x1400027b6  movsxd  rax, ecx
0x1400027b9  mov     rdx, [rax+r9]
0x1400027bd  mov     rax, [r11+10h]
0x1400027c1  mov     ecx, [rax+8]
0x1400027c4  mov     rax, [r11+8]
0x1400027c8  test    byte ptr [rcx+rax+3], 0Fh
0x1400027cd  jz      short loc_1400027E1
0x1400027cf  movzx   eax, byte ptr [rcx+rax+3]
0x1400027d4  mov     ecx, 0FFFFFFF0h
0x1400027d9  and     rax, rcx
0x1400027dc  add     rax, r10
0x1400027df  jmp     short loc_1400027E4
0x1400027e1  mov     rax, r10
0x1400027e4  xor     rdx, rax
0x1400027e7  mov     rcx, rdx; StackCookie
0x1400027ea  jmp     __security_check_cookie
```
