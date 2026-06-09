# __GSHandlerCheckCommon

- ea: `0x18001a5c0`
- end: `0x18001a623`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a59c`

## callees

- `0x180001630`
- `0x18001a5c0`

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
0x18001a5c0  mov     r10, rcx
0x18001a5c3  mov     r11, rdx
0x18001a5c6  mov     ecx, [r8]
0x18001a5c9  and     ecx, 0FFFFFFF8h
0x18001a5cc  test    byte ptr [r8], 4
0x18001a5d0  jz      short loc_18001A5E7
0x18001a5d2  mov     eax, [r8+8]
0x18001a5d6  movsxd  r9, dword ptr [r8+4]
0x18001a5da  neg     eax
0x18001a5dc  movsxd  rdx, eax
0x18001a5df  add     r9, r10
0x18001a5e2  and     r9, rdx
0x18001a5e5  jmp     short loc_18001A5EA
0x18001a5e7  mov     r9, r10
0x18001a5ea  movsxd  rax, ecx
0x18001a5ed  mov     rdx, [rax+r9]
0x18001a5f1  mov     rax, [r11+10h]
0x18001a5f5  mov     ecx, [rax+8]
0x18001a5f8  mov     rax, [r11+8]
0x18001a5fc  test    byte ptr [rcx+rax+3], 0Fh
0x18001a601  jz      short loc_18001A615
0x18001a603  movzx   eax, byte ptr [rcx+rax+3]
0x18001a608  mov     ecx, 0FFFFFFF0h
0x18001a60d  and     rax, rcx
0x18001a610  add     rax, r10
0x18001a613  jmp     short loc_18001A618
0x18001a615  mov     rax, r10
0x18001a618  xor     rdx, rax
0x18001a61b  mov     rcx, rdx; StackCookie
0x18001a61e  jmp     __security_check_cookie
```
