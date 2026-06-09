# __GSHandlerCheckCommon

- ea: `0x180002764`
- end: `0x1800027c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002740`
- `0x180017360`

## callees

- `0x180002030`
- `0x180002764`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180002764  mov     r10, rcx
0x180002767  mov     r11, rdx
0x18000276a  mov     ecx, [r8]
0x18000276d  and     ecx, 0FFFFFFF8h
0x180002770  test    byte ptr [r8], 4
0x180002774  jz      short loc_18000278B
0x180002776  mov     eax, [r8+8]
0x18000277a  movsxd  r9, dword ptr [r8+4]
0x18000277e  neg     eax
0x180002780  movsxd  rdx, eax
0x180002783  add     r9, r10
0x180002786  and     r9, rdx
0x180002789  jmp     short loc_18000278E
0x18000278b  mov     r9, r10
0x18000278e  movsxd  rax, ecx
0x180002791  mov     rdx, [rax+r9]
0x180002795  mov     rax, [r11+10h]
0x180002799  mov     ecx, [rax+8]
0x18000279c  mov     rax, [r11+8]
0x1800027a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800027a5  jz      short loc_1800027B9
0x1800027a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800027ac  mov     ecx, 0FFFFFFF0h
0x1800027b1  and     rax, rcx
0x1800027b4  add     rax, r10
0x1800027b7  jmp     short loc_1800027BC
0x1800027b9  mov     rax, r10
0x1800027bc  xor     rdx, rax
0x1800027bf  mov     rcx, rdx; StackCookie
0x1800027c2  jmp     __security_check_cookie
```
