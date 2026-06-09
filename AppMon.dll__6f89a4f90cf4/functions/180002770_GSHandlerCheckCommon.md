# __GSHandlerCheckCommon

- ea: `0x180002770`
- end: `0x1800027d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000274c`
- `0x18000ee0c`

## callees

- `0x180001620`
- `0x180002770`

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
0x180002770  mov     r10, rcx
0x180002773  mov     r11, rdx
0x180002776  mov     ecx, [r8]
0x180002779  and     ecx, 0FFFFFFF8h
0x18000277c  test    byte ptr [r8], 4
0x180002780  jz      short loc_180002797
0x180002782  mov     eax, [r8+8]
0x180002786  movsxd  r9, dword ptr [r8+4]
0x18000278a  neg     eax
0x18000278c  movsxd  rdx, eax
0x18000278f  add     r9, r10
0x180002792  and     r9, rdx
0x180002795  jmp     short loc_18000279A
0x180002797  mov     r9, r10
0x18000279a  movsxd  rax, ecx
0x18000279d  mov     rdx, [rax+r9]
0x1800027a1  mov     rax, [r11+10h]
0x1800027a5  mov     ecx, [rax+8]
0x1800027a8  mov     rax, [r11+8]
0x1800027ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800027b1  jz      short loc_1800027C5
0x1800027b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800027b8  mov     ecx, 0FFFFFFF0h
0x1800027bd  and     rax, rcx
0x1800027c0  add     rax, r10
0x1800027c3  jmp     short loc_1800027C8
0x1800027c5  mov     rax, r10
0x1800027c8  xor     rdx, rax
0x1800027cb  mov     rcx, rdx; StackCookie
0x1800027ce  jmp     __security_check_cookie
```
