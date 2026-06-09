# __GSHandlerCheckCommon

- ea: `0x180010430`
- end: `0x180010493`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001040c`
- `0x18001049c`

## callees

- `0x180002910`
- `0x180010430`

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
0x180010430  mov     r10, rcx
0x180010433  mov     r11, rdx
0x180010436  mov     ecx, [r8]
0x180010439  and     ecx, 0FFFFFFF8h
0x18001043c  test    byte ptr [r8], 4
0x180010440  jz      short loc_180010457
0x180010442  mov     eax, [r8+8]
0x180010446  movsxd  r9, dword ptr [r8+4]
0x18001044a  neg     eax
0x18001044c  movsxd  rdx, eax
0x18001044f  add     r9, r10
0x180010452  and     r9, rdx
0x180010455  jmp     short loc_18001045A
0x180010457  mov     r9, r10
0x18001045a  movsxd  rax, ecx
0x18001045d  mov     rdx, [rax+r9]
0x180010461  mov     rax, [r11+10h]
0x180010465  mov     ecx, [rax+8]
0x180010468  mov     rax, [r11+8]
0x18001046c  test    byte ptr [rcx+rax+3], 0Fh
0x180010471  jz      short loc_180010485
0x180010473  movzx   eax, byte ptr [rcx+rax+3]
0x180010478  mov     ecx, 0FFFFFFF0h
0x18001047d  and     rax, rcx
0x180010480  add     rax, r10
0x180010483  jmp     short loc_180010488
0x180010485  mov     rax, r10
0x180010488  xor     rdx, rax
0x18001048b  mov     rcx, rdx; StackCookie
0x18001048e  jmp     __security_check_cookie
```
