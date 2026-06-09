# __GSHandlerCheckCommon

- ea: `0x140002560`
- end: `0x1400025c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000253c`
- `0x140010d6c`

## callees

- `0x140002210`
- `0x140002560`

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
0x140002560  mov     r10, rcx
0x140002563  mov     r11, rdx
0x140002566  mov     ecx, [r8]
0x140002569  and     ecx, 0FFFFFFF8h
0x14000256c  test    byte ptr [r8], 4
0x140002570  jz      short loc_140002587
0x140002572  mov     eax, [r8+8]
0x140002576  movsxd  r9, dword ptr [r8+4]
0x14000257a  neg     eax
0x14000257c  movsxd  rdx, eax
0x14000257f  add     r9, r10
0x140002582  and     r9, rdx
0x140002585  jmp     short loc_14000258A
0x140002587  mov     r9, r10
0x14000258a  movsxd  rax, ecx
0x14000258d  mov     rdx, [rax+r9]
0x140002591  mov     rax, [r11+10h]
0x140002595  mov     ecx, [rax+8]
0x140002598  mov     rax, [r11+8]
0x14000259c  test    byte ptr [rcx+rax+3], 0Fh
0x1400025a1  jz      short loc_1400025B5
0x1400025a3  movzx   eax, byte ptr [rcx+rax+3]
0x1400025a8  mov     ecx, 0FFFFFFF0h
0x1400025ad  and     rax, rcx
0x1400025b0  add     rax, r10
0x1400025b3  jmp     short loc_1400025B8
0x1400025b5  mov     rax, r10
0x1400025b8  xor     rdx, rax
0x1400025bb  mov     rcx, rdx; StackCookie
0x1400025be  jmp     __security_check_cookie
```
