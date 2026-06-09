# __GSHandlerCheckCommon

- ea: `0x180003b24`
- end: `0x180003b87`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b00`
- `0x180011f10`

## callees

- `0x1800033d0`
- `0x180003b24`

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
0x180003b24  mov     r10, rcx
0x180003b27  mov     r11, rdx
0x180003b2a  mov     ecx, [r8]
0x180003b2d  and     ecx, 0FFFFFFF8h
0x180003b30  test    byte ptr [r8], 4
0x180003b34  jz      short loc_180003B4B
0x180003b36  mov     eax, [r8+8]
0x180003b3a  movsxd  r9, dword ptr [r8+4]
0x180003b3e  neg     eax
0x180003b40  movsxd  rdx, eax
0x180003b43  add     r9, r10
0x180003b46  and     r9, rdx
0x180003b49  jmp     short loc_180003B4E
0x180003b4b  mov     r9, r10
0x180003b4e  movsxd  rax, ecx
0x180003b51  mov     rdx, [rax+r9]
0x180003b55  mov     rax, [r11+10h]
0x180003b59  mov     ecx, [rax+8]
0x180003b5c  mov     rax, [r11+8]
0x180003b60  test    byte ptr [rcx+rax+3], 0Fh
0x180003b65  jz      short loc_180003B79
0x180003b67  movzx   eax, byte ptr [rcx+rax+3]
0x180003b6c  mov     ecx, 0FFFFFFF0h
0x180003b71  and     rax, rcx
0x180003b74  add     rax, r10
0x180003b77  jmp     short loc_180003B7C
0x180003b79  mov     rax, r10
0x180003b7c  xor     rdx, rax
0x180003b7f  mov     rcx, rdx; StackCookie
0x180003b82  jmp     __security_check_cookie
```
