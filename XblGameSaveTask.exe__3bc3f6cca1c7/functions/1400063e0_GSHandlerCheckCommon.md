# __GSHandlerCheckCommon

- ea: `0x1400063e0`
- end: `0x140006443`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400063bc`
- `0x14000644c`

## callees

- `0x140001480`
- `0x1400063e0`

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
0x1400063e0  mov     r10, rcx
0x1400063e3  mov     r11, rdx
0x1400063e6  mov     ecx, [r8]
0x1400063e9  and     ecx, 0FFFFFFF8h
0x1400063ec  test    byte ptr [r8], 4
0x1400063f0  jz      short loc_140006407
0x1400063f2  mov     eax, [r8+8]
0x1400063f6  movsxd  r9, dword ptr [r8+4]
0x1400063fa  neg     eax
0x1400063fc  movsxd  rdx, eax
0x1400063ff  add     r9, r10
0x140006402  and     r9, rdx
0x140006405  jmp     short loc_14000640A
0x140006407  mov     r9, r10
0x14000640a  movsxd  rax, ecx
0x14000640d  mov     rdx, [rax+r9]
0x140006411  mov     rax, [r11+10h]
0x140006415  mov     ecx, [rax+8]
0x140006418  mov     rax, [r11+8]
0x14000641c  test    byte ptr [rcx+rax+3], 0Fh
0x140006421  jz      short loc_140006435
0x140006423  movzx   eax, byte ptr [rcx+rax+3]
0x140006428  mov     ecx, 0FFFFFFF0h
0x14000642d  and     rax, rcx
0x140006430  add     rax, r10
0x140006433  jmp     short loc_140006438
0x140006435  mov     rax, r10
0x140006438  xor     rdx, rax
0x14000643b  mov     rcx, rdx; StackCookie
0x14000643e  jmp     __security_check_cookie
```
