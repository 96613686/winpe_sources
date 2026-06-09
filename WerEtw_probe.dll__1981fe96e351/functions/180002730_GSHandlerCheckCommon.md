# __GSHandlerCheckCommon

- ea: `0x180002730`
- end: `0x180002793`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000270c`
- `0x180027b00`

## callees

- `0x180001870`
- `0x180002730`

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
0x180002730  mov     r10, rcx
0x180002733  mov     r11, rdx
0x180002736  mov     ecx, [r8]
0x180002739  and     ecx, 0FFFFFFF8h
0x18000273c  test    byte ptr [r8], 4
0x180002740  jz      short loc_180002757
0x180002742  mov     eax, [r8+8]
0x180002746  movsxd  r9, dword ptr [r8+4]
0x18000274a  neg     eax
0x18000274c  movsxd  rdx, eax
0x18000274f  add     r9, r10
0x180002752  and     r9, rdx
0x180002755  jmp     short loc_18000275A
0x180002757  mov     r9, r10
0x18000275a  movsxd  rax, ecx
0x18000275d  mov     rdx, [rax+r9]
0x180002761  mov     rax, [r11+10h]
0x180002765  mov     ecx, [rax+8]
0x180002768  mov     rax, [r11+8]
0x18000276c  test    byte ptr [rcx+rax+3], 0Fh
0x180002771  jz      short loc_180002785
0x180002773  movzx   eax, byte ptr [rcx+rax+3]
0x180002778  mov     ecx, 0FFFFFFF0h
0x18000277d  and     rax, rcx
0x180002780  add     rax, r10
0x180002783  jmp     short loc_180002788
0x180002785  mov     rax, r10
0x180002788  xor     rdx, rax
0x18000278b  mov     rcx, rdx; StackCookie
0x18000278e  jmp     __security_check_cookie
```
