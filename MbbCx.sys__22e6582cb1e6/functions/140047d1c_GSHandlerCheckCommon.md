# __GSHandlerCheckCommon

- ea: `0x140047d1c`
- end: `0x140047d8c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047cf8`

## callees

- `0x140047d1c`
- `0x140047e50`

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
0x140047d1c  sub     rsp, 28h
0x140047d20  mov     eax, [r8]
0x140047d23  mov     r10, rcx
0x140047d26  mov     ecx, eax
0x140047d28  mov     r11, rdx
0x140047d2b  and     ecx, 0FFFFFFF8h
0x140047d2e  test    al, 4
0x140047d30  jz      short loc_140047D47
0x140047d32  mov     eax, [r8+8]
0x140047d36  movsxd  r9, dword ptr [r8+4]
0x140047d3a  neg     eax
0x140047d3c  movsxd  rdx, eax
0x140047d3f  add     r9, r10
0x140047d42  and     r9, rdx
0x140047d45  jmp     short loc_140047D4A
0x140047d47  mov     r9, r10
0x140047d4a  movsxd  rax, ecx
0x140047d4d  mov     rdx, [rax+r9]
0x140047d51  mov     rax, [r11+10h]
0x140047d55  mov     ecx, [rax+8]
0x140047d58  mov     rax, [r11+8]
0x140047d5c  movzx   r8d, byte ptr [rcx+rax+3]
0x140047d62  test    r8b, 0Fh
0x140047d66  jz      short loc_140047D78
0x140047d68  mov     eax, r8d
0x140047d6b  mov     ecx, 0FFFFFFF0h
0x140047d70  and     rax, rcx
0x140047d73  add     rax, r10
0x140047d76  jmp     short loc_140047D7B
0x140047d78  mov     rax, r10
0x140047d7b  xor     rdx, rax
0x140047d7e  mov     rcx, rdx; StackCookie
0x140047d81  call    __security_check_cookie
0x140047d86  add     rsp, 28h
0x140047d8a  retn
```
