# __GSHandlerCheckCommon

- ea: `0x14001ac1c`
- end: `0x14001ac8c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001abf8`
- `0x14001ac94`

## callees

- `0x14001ac1c`
- `0x14001adc0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14001ac1c  sub     rsp, 28h
0x14001ac20  mov     eax, [r8]
0x14001ac23  mov     r10, rcx
0x14001ac26  mov     ecx, eax
0x14001ac28  mov     r11, rdx
0x14001ac2b  and     ecx, 0FFFFFFF8h
0x14001ac2e  test    al, 4
0x14001ac30  jz      short loc_14001AC47
0x14001ac32  mov     eax, [r8+8]
0x14001ac36  movsxd  r9, dword ptr [r8+4]
0x14001ac3a  neg     eax
0x14001ac3c  movsxd  rdx, eax
0x14001ac3f  add     r9, r10
0x14001ac42  and     r9, rdx
0x14001ac45  jmp     short loc_14001AC4A
0x14001ac47  mov     r9, r10
0x14001ac4a  movsxd  rax, ecx
0x14001ac4d  mov     rdx, [rax+r9]
0x14001ac51  mov     rax, [r11+10h]
0x14001ac55  mov     ecx, [rax+8]
0x14001ac58  mov     rax, [r11+8]
0x14001ac5c  movzx   r8d, byte ptr [rcx+rax+3]
0x14001ac62  test    r8b, 0Fh
0x14001ac66  jz      short loc_14001AC78
0x14001ac68  mov     eax, r8d
0x14001ac6b  mov     ecx, 0FFFFFFF0h
0x14001ac70  and     rax, rcx
0x14001ac73  add     rax, r10
0x14001ac76  jmp     short loc_14001AC7B
0x14001ac78  mov     rax, r10
0x14001ac7b  xor     rdx, rax
0x14001ac7e  mov     rcx, rdx; StackCookie
0x14001ac81  call    __security_check_cookie
0x14001ac86  add     rsp, 28h
0x14001ac8a  retn
```
