# __GSHandlerCheckCommon

- ea: `0x18000e288`
- end: `0x18000e2eb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e264`
- `0x18000e2f4`
- `0x18000e35c`

## callees

- `0x1800017c0`
- `0x18000e288`

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
0x18000e288  mov     r10, rcx
0x18000e28b  mov     r11, rdx
0x18000e28e  mov     ecx, [r8]
0x18000e291  and     ecx, 0FFFFFFF8h
0x18000e294  test    byte ptr [r8], 4
0x18000e298  jz      short loc_18000E2AF
0x18000e29a  mov     eax, [r8+8]
0x18000e29e  movsxd  r9, dword ptr [r8+4]
0x18000e2a2  neg     eax
0x18000e2a4  movsxd  rdx, eax
0x18000e2a7  add     r9, r10
0x18000e2aa  and     r9, rdx
0x18000e2ad  jmp     short loc_18000E2B2
0x18000e2af  mov     r9, r10
0x18000e2b2  movsxd  rax, ecx
0x18000e2b5  mov     rdx, [rax+r9]
0x18000e2b9  mov     rax, [r11+10h]
0x18000e2bd  mov     ecx, [rax+8]
0x18000e2c0  mov     rax, [r11+8]
0x18000e2c4  test    byte ptr [rcx+rax+3], 0Fh
0x18000e2c9  jz      short loc_18000E2DD
0x18000e2cb  movzx   eax, byte ptr [rcx+rax+3]
0x18000e2d0  mov     ecx, 0FFFFFFF0h
0x18000e2d5  and     rax, rcx
0x18000e2d8  add     rax, r10
0x18000e2db  jmp     short loc_18000E2E0
0x18000e2dd  mov     rax, r10
0x18000e2e0  xor     rdx, rax
0x18000e2e3  mov     rcx, rdx; StackCookie
0x18000e2e6  jmp     __security_check_cookie
```
