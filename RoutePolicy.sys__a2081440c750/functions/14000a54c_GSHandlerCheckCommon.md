# __GSHandlerCheckCommon

- ea: `0x14000a54c`
- end: `0x14000a5bc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a528`

## callees

- `0x14000a54c`
- `0x14000a680`

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
0x14000a54c  sub     rsp, 28h
0x14000a550  mov     eax, [r8]
0x14000a553  mov     r10, rcx
0x14000a556  mov     ecx, eax
0x14000a558  mov     r11, rdx
0x14000a55b  and     ecx, 0FFFFFFF8h
0x14000a55e  test    al, 4
0x14000a560  jz      short loc_14000A577
0x14000a562  mov     eax, [r8+8]
0x14000a566  movsxd  r9, dword ptr [r8+4]
0x14000a56a  neg     eax
0x14000a56c  movsxd  rdx, eax
0x14000a56f  add     r9, r10
0x14000a572  and     r9, rdx
0x14000a575  jmp     short loc_14000A57A
0x14000a577  mov     r9, r10
0x14000a57a  movsxd  rax, ecx
0x14000a57d  mov     rdx, [rax+r9]
0x14000a581  mov     rax, [r11+10h]
0x14000a585  mov     ecx, [rax+8]
0x14000a588  mov     rax, [r11+8]
0x14000a58c  movzx   r8d, byte ptr [rcx+rax+3]
0x14000a592  test    r8b, 0Fh
0x14000a596  jz      short loc_14000A5A8
0x14000a598  mov     eax, r8d
0x14000a59b  mov     ecx, 0FFFFFFF0h
0x14000a5a0  and     rax, rcx
0x14000a5a3  add     rax, r10
0x14000a5a6  jmp     short loc_14000A5AB
0x14000a5a8  mov     rax, r10
0x14000a5ab  xor     rdx, rax
0x14000a5ae  mov     rcx, rdx; StackCookie
0x14000a5b1  call    __security_check_cookie
0x14000a5b6  add     rsp, 28h
0x14000a5ba  retn
```
