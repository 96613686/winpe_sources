# __GSHandlerCheckCommon

- ea: `0x140001a30`
- end: `0x140001a93`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001a0c`
- `0x14000b7c0`

## callees

- `0x1400016f0`
- `0x140001a30`

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
0x140001a30  mov     r10, rcx
0x140001a33  mov     r11, rdx
0x140001a36  mov     ecx, [r8]
0x140001a39  and     ecx, 0FFFFFFF8h
0x140001a3c  test    byte ptr [r8], 4
0x140001a40  jz      short loc_140001A57
0x140001a42  mov     eax, [r8+8]
0x140001a46  movsxd  r9, dword ptr [r8+4]
0x140001a4a  neg     eax
0x140001a4c  movsxd  rdx, eax
0x140001a4f  add     r9, r10
0x140001a52  and     r9, rdx
0x140001a55  jmp     short loc_140001A5A
0x140001a57  mov     r9, r10
0x140001a5a  movsxd  rax, ecx
0x140001a5d  mov     rdx, [rax+r9]
0x140001a61  mov     rax, [r11+10h]
0x140001a65  mov     ecx, [rax+8]
0x140001a68  mov     rax, [r11+8]
0x140001a6c  test    byte ptr [rcx+rax+3], 0Fh
0x140001a71  jz      short loc_140001A85
0x140001a73  movzx   eax, byte ptr [rcx+rax+3]
0x140001a78  mov     ecx, 0FFFFFFF0h
0x140001a7d  and     rax, rcx
0x140001a80  add     rax, r10
0x140001a83  jmp     short loc_140001A88
0x140001a85  mov     rax, r10
0x140001a88  xor     rdx, rax
0x140001a8b  mov     rcx, rdx; StackCookie
0x140001a8e  jmp     __security_check_cookie
```
