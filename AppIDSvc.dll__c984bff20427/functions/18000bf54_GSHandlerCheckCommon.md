# __GSHandlerCheckCommon

- ea: `0x18000bf54`
- end: `0x18000bfb7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bf30`
- `0x18000bfc0`
- `0x18000c028`

## callees

- `0x18000bf54`
- `0x18000c0e0`

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
0x18000bf54  mov     r10, rcx
0x18000bf57  mov     r11, rdx
0x18000bf5a  mov     ecx, [r8]
0x18000bf5d  and     ecx, 0FFFFFFF8h
0x18000bf60  test    byte ptr [r8], 4
0x18000bf64  jz      short loc_18000BF7B
0x18000bf66  mov     eax, [r8+8]
0x18000bf6a  movsxd  r9, dword ptr [r8+4]
0x18000bf6e  neg     eax
0x18000bf70  movsxd  rdx, eax
0x18000bf73  add     r9, r10
0x18000bf76  and     r9, rdx
0x18000bf79  jmp     short loc_18000BF7E
0x18000bf7b  mov     r9, r10
0x18000bf7e  movsxd  rax, ecx
0x18000bf81  mov     rdx, [rax+r9]
0x18000bf85  mov     rax, [r11+10h]
0x18000bf89  mov     ecx, [rax+8]
0x18000bf8c  mov     rax, [r11+8]
0x18000bf90  test    byte ptr [rcx+rax+3], 0Fh
0x18000bf95  jz      short loc_18000BFA9
0x18000bf97  movzx   eax, byte ptr [rcx+rax+3]
0x18000bf9c  mov     ecx, 0FFFFFFF0h
0x18000bfa1  and     rax, rcx
0x18000bfa4  add     rax, r10
0x18000bfa7  jmp     short loc_18000BFAC
0x18000bfa9  mov     rax, r10
0x18000bfac  xor     rdx, rax
0x18000bfaf  mov     rcx, rdx; StackCookie
0x18000bfb2  jmp     __security_check_cookie
```
