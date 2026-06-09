# __GSHandlerCheckCommon

- ea: `0x180020b20`
- end: `0x180020b83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020afc`
- `0x180020b8c`

## callees

- `0x180020b20`
- `0x180020c30`

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
0x180020b20  mov     r10, rcx
0x180020b23  mov     r11, rdx
0x180020b26  mov     ecx, [r8]
0x180020b29  and     ecx, 0FFFFFFF8h
0x180020b2c  test    byte ptr [r8], 4
0x180020b30  jz      short loc_180020B47
0x180020b32  mov     eax, [r8+8]
0x180020b36  movsxd  r9, dword ptr [r8+4]
0x180020b3a  neg     eax
0x180020b3c  movsxd  rdx, eax
0x180020b3f  add     r9, r10
0x180020b42  and     r9, rdx
0x180020b45  jmp     short loc_180020B4A
0x180020b47  mov     r9, r10
0x180020b4a  movsxd  rax, ecx
0x180020b4d  mov     rdx, [rax+r9]
0x180020b51  mov     rax, [r11+10h]
0x180020b55  mov     ecx, [rax+8]
0x180020b58  mov     rax, [r11+8]
0x180020b5c  test    byte ptr [rcx+rax+3], 0Fh
0x180020b61  jz      short loc_180020B75
0x180020b63  movzx   eax, byte ptr [rcx+rax+3]
0x180020b68  mov     ecx, 0FFFFFFF0h
0x180020b6d  and     rax, rcx
0x180020b70  add     rax, r10
0x180020b73  jmp     short loc_180020B78
0x180020b75  mov     rax, r10
0x180020b78  xor     rdx, rax
0x180020b7b  mov     rcx, rdx; StackCookie
0x180020b7e  jmp     __security_check_cookie
```
