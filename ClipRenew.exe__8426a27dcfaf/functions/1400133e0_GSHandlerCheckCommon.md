# __GSHandlerCheckCommon

- ea: `0x1400133e0`
- end: `0x140013443`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400133bc`

## callees

- `0x1400133e0`
- `0x1400134a0`

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
0x1400133e0  mov     r10, rcx
0x1400133e3  mov     r11, rdx
0x1400133e6  mov     ecx, [r8]
0x1400133e9  and     ecx, 0FFFFFFF8h
0x1400133ec  test    byte ptr [r8], 4
0x1400133f0  jz      short loc_140013407
0x1400133f2  mov     eax, [r8+8]
0x1400133f6  movsxd  r9, dword ptr [r8+4]
0x1400133fa  neg     eax
0x1400133fc  movsxd  rdx, eax
0x1400133ff  add     r9, r10
0x140013402  and     r9, rdx
0x140013405  jmp     short loc_14001340A
0x140013407  mov     r9, r10
0x14001340a  movsxd  rax, ecx
0x14001340d  mov     rdx, [rax+r9]
0x140013411  mov     rax, [r11+10h]
0x140013415  mov     ecx, [rax+8]
0x140013418  mov     rax, [r11+8]
0x14001341c  test    byte ptr [rcx+rax+3], 0Fh
0x140013421  jz      short loc_140013435
0x140013423  movzx   eax, byte ptr [rcx+rax+3]
0x140013428  mov     ecx, 0FFFFFFF0h
0x14001342d  and     rax, rcx
0x140013430  add     rax, r10
0x140013433  jmp     short loc_140013438
0x140013435  mov     rax, r10
0x140013438  xor     rdx, rax
0x14001343b  mov     rcx, rdx; StackCookie
0x14001343e  jmp     __security_check_cookie
```
