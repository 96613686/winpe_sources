# __GSHandlerCheckCommon

- ea: `0x14000243c`
- end: `0x14000249f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002418`
- `0x1400159e4`

## callees

- `0x14000243c`
- `0x140015aa0`

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
0x14000243c  mov     r10, rcx
0x14000243f  mov     r11, rdx
0x140002442  mov     ecx, [r8]
0x140002445  and     ecx, 0FFFFFFF8h
0x140002448  test    byte ptr [r8], 4
0x14000244c  jz      short loc_140002463
0x14000244e  mov     eax, [r8+8]
0x140002452  movsxd  r9, dword ptr [r8+4]
0x140002456  neg     eax
0x140002458  movsxd  rdx, eax
0x14000245b  add     r9, r10
0x14000245e  and     r9, rdx
0x140002461  jmp     short loc_140002466
0x140002463  mov     r9, r10
0x140002466  movsxd  rax, ecx
0x140002469  mov     rdx, [rax+r9]
0x14000246d  mov     rax, [r11+10h]
0x140002471  mov     ecx, [rax+8]
0x140002474  mov     rax, [r11+8]
0x140002478  test    byte ptr [rcx+rax+3], 0Fh
0x14000247d  jz      short loc_140002491
0x14000247f  movzx   eax, byte ptr [rcx+rax+3]
0x140002484  mov     ecx, 0FFFFFFF0h
0x140002489  and     rax, rcx
0x14000248c  add     rax, r10
0x14000248f  jmp     short loc_140002494
0x140002491  mov     rax, r10
0x140002494  xor     rdx, rax
0x140002497  mov     rcx, rdx; StackCookie
0x14000249a  jmp     __security_check_cookie
```
