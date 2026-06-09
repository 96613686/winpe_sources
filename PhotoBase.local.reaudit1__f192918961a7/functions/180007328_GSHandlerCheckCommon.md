# __GSHandlerCheckCommon

- ea: `0x180007328`
- end: `0x18000738b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007304`
- `0x180007394`
- `0x1800073fc`

## callees

- `0x180001480`
- `0x180007328`

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
0x180007328  mov     r10, rcx
0x18000732b  mov     r11, rdx
0x18000732e  mov     ecx, [r8]
0x180007331  and     ecx, 0FFFFFFF8h
0x180007334  test    byte ptr [r8], 4
0x180007338  jz      short loc_18000734F
0x18000733a  mov     eax, [r8+8]
0x18000733e  movsxd  r9, dword ptr [r8+4]
0x180007342  neg     eax
0x180007344  movsxd  rdx, eax
0x180007347  add     r9, r10
0x18000734a  and     r9, rdx
0x18000734d  jmp     short loc_180007352
0x18000734f  mov     r9, r10
0x180007352  movsxd  rax, ecx
0x180007355  mov     rdx, [rax+r9]
0x180007359  mov     rax, [r11+10h]
0x18000735d  mov     ecx, [rax+8]
0x180007360  mov     rax, [r11+8]
0x180007364  test    byte ptr [rcx+rax+3], 0Fh
0x180007369  jz      short loc_18000737D
0x18000736b  movzx   eax, byte ptr [rcx+rax+3]
0x180007370  mov     ecx, 0FFFFFFF0h
0x180007375  and     rax, rcx
0x180007378  add     rax, r10
0x18000737b  jmp     short loc_180007380
0x18000737d  mov     rax, r10
0x180007380  xor     rdx, rax
0x180007383  mov     rcx, rdx; StackCookie
0x180007386  jmp     __security_check_cookie
```
