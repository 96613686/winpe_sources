# __GSHandlerCheckCommon

- ea: `0x140002714`
- end: `0x140002777`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400026f0`

## callees

- `0x140001330`
- `0x140002714`

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
0x140002714  mov     r10, rcx
0x140002717  mov     r11, rdx
0x14000271a  mov     ecx, [r8]
0x14000271d  and     ecx, 0FFFFFFF8h
0x140002720  test    byte ptr [r8], 4
0x140002724  jz      short loc_14000273B
0x140002726  mov     eax, [r8+8]
0x14000272a  movsxd  r9, dword ptr [r8+4]
0x14000272e  neg     eax
0x140002730  movsxd  rdx, eax
0x140002733  add     r9, r10
0x140002736  and     r9, rdx
0x140002739  jmp     short loc_14000273E
0x14000273b  mov     r9, r10
0x14000273e  movsxd  rax, ecx
0x140002741  mov     rdx, [rax+r9]
0x140002745  mov     rax, [r11+10h]
0x140002749  mov     ecx, [rax+8]
0x14000274c  mov     rax, [r11+8]
0x140002750  test    byte ptr [rcx+rax+3], 0Fh
0x140002755  jz      short loc_140002769
0x140002757  movzx   eax, byte ptr [rcx+rax+3]
0x14000275c  mov     ecx, 0FFFFFFF0h
0x140002761  and     rax, rcx
0x140002764  add     rax, r10
0x140002767  jmp     short loc_14000276C
0x140002769  mov     rax, r10
0x14000276c  xor     rdx, rax
0x14000276f  mov     rcx, rdx; StackCookie
0x140002772  jmp     __security_check_cookie
```
