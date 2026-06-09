# __GSHandlerCheckCommon

- ea: `0x140007bcc`
- end: `0x140007c3c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007ba8`

## callees

- `0x140007bcc`
- `0x140007d00`

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
0x140007bcc  sub     rsp, 28h
0x140007bd0  mov     eax, [r8]
0x140007bd3  mov     r10, rcx
0x140007bd6  mov     ecx, eax
0x140007bd8  mov     r11, rdx
0x140007bdb  and     ecx, 0FFFFFFF8h
0x140007bde  test    al, 4
0x140007be0  jz      short loc_140007BF7
0x140007be2  mov     eax, [r8+8]
0x140007be6  movsxd  r9, dword ptr [r8+4]
0x140007bea  neg     eax
0x140007bec  movsxd  rdx, eax
0x140007bef  add     r9, r10
0x140007bf2  and     r9, rdx
0x140007bf5  jmp     short loc_140007BFA
0x140007bf7  mov     r9, r10
0x140007bfa  movsxd  rax, ecx
0x140007bfd  mov     rdx, [rax+r9]
0x140007c01  mov     rax, [r11+10h]
0x140007c05  mov     ecx, [rax+8]
0x140007c08  mov     rax, [r11+8]
0x140007c0c  movzx   r8d, byte ptr [rcx+rax+3]
0x140007c12  test    r8b, 0Fh
0x140007c16  jz      short loc_140007C28
0x140007c18  mov     eax, r8d
0x140007c1b  mov     ecx, 0FFFFFFF0h
0x140007c20  and     rax, rcx
0x140007c23  add     rax, r10
0x140007c26  jmp     short loc_140007C2B
0x140007c28  mov     rax, r10
0x140007c2b  xor     rdx, rax
0x140007c2e  mov     rcx, rdx; StackCookie
0x140007c31  call    __security_check_cookie
0x140007c36  add     rsp, 28h
0x140007c3a  retn
```
