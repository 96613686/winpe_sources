# __GSHandlerCheckCommon

- ea: `0x14000256c`
- end: `0x1400025cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002548`
- `0x14003fb00`

## callees

- `0x14000256c`
- `0x14003fbb0`

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
0x14000256c  mov     r10, rcx
0x14000256f  mov     r11, rdx
0x140002572  mov     ecx, [r8]
0x140002575  and     ecx, 0FFFFFFF8h
0x140002578  test    byte ptr [r8], 4
0x14000257c  jz      short loc_140002593
0x14000257e  mov     eax, [r8+8]
0x140002582  movsxd  r9, dword ptr [r8+4]
0x140002586  neg     eax
0x140002588  movsxd  rdx, eax
0x14000258b  add     r9, r10
0x14000258e  and     r9, rdx
0x140002591  jmp     short loc_140002596
0x140002593  mov     r9, r10
0x140002596  movsxd  rax, ecx
0x140002599  mov     rdx, [rax+r9]
0x14000259d  mov     rax, [r11+10h]
0x1400025a1  mov     ecx, [rax+8]
0x1400025a4  mov     rax, [r11+8]
0x1400025a8  test    byte ptr [rcx+rax+3], 0Fh
0x1400025ad  jz      short loc_1400025C1
0x1400025af  movzx   eax, byte ptr [rcx+rax+3]
0x1400025b4  mov     ecx, 0FFFFFFF0h
0x1400025b9  and     rax, rcx
0x1400025bc  add     rax, r10
0x1400025bf  jmp     short loc_1400025C4
0x1400025c1  mov     rax, r10
0x1400025c4  xor     rdx, rax
0x1400025c7  mov     rcx, rdx; StackCookie
0x1400025ca  jmp     __security_check_cookie
```
