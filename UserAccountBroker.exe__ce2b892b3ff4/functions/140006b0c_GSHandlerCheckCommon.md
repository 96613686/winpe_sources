# __GSHandlerCheckCommon

- ea: `0x140006b0c`
- end: `0x140006b6f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006ae8`

## callees

- `0x140006b0c`
- `0x140006b90`

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
0x140006b0c  mov     r10, rcx
0x140006b0f  mov     r11, rdx
0x140006b12  mov     ecx, [r8]
0x140006b15  and     ecx, 0FFFFFFF8h
0x140006b18  test    byte ptr [r8], 4
0x140006b1c  jz      short loc_140006B33
0x140006b1e  mov     eax, [r8+8]
0x140006b22  movsxd  r9, dword ptr [r8+4]
0x140006b26  neg     eax
0x140006b28  movsxd  rdx, eax
0x140006b2b  add     r9, r10
0x140006b2e  and     r9, rdx
0x140006b31  jmp     short loc_140006B36
0x140006b33  mov     r9, r10
0x140006b36  movsxd  rax, ecx
0x140006b39  mov     rdx, [rax+r9]
0x140006b3d  mov     rax, [r11+10h]
0x140006b41  mov     ecx, [rax+8]
0x140006b44  mov     rax, [r11+8]
0x140006b48  test    byte ptr [rcx+rax+3], 0Fh
0x140006b4d  jz      short loc_140006B61
0x140006b4f  movzx   eax, byte ptr [rcx+rax+3]
0x140006b54  mov     ecx, 0FFFFFFF0h
0x140006b59  and     rax, rcx
0x140006b5c  add     rax, r10
0x140006b5f  jmp     short loc_140006B64
0x140006b61  mov     rax, r10
0x140006b64  xor     rdx, rax
0x140006b67  mov     rcx, rdx; StackCookie
0x140006b6a  jmp     __security_check_cookie
```
