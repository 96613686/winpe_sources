# __GSHandlerCheckCommon

- ea: `0x18001b6ac`
- end: `0x18001b70f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b688`
- `0x18001b718`

## callees

- `0x18001b6ac`
- `0x18001b7e0`

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
0x18001b6ac  mov     r10, rcx
0x18001b6af  mov     r11, rdx
0x18001b6b2  mov     ecx, [r8]
0x18001b6b5  and     ecx, 0FFFFFFF8h
0x18001b6b8  test    byte ptr [r8], 4
0x18001b6bc  jz      short loc_18001B6D3
0x18001b6be  mov     eax, [r8+8]
0x18001b6c2  movsxd  r9, dword ptr [r8+4]
0x18001b6c6  neg     eax
0x18001b6c8  movsxd  rdx, eax
0x18001b6cb  add     r9, r10
0x18001b6ce  and     r9, rdx
0x18001b6d1  jmp     short loc_18001B6D6
0x18001b6d3  mov     r9, r10
0x18001b6d6  movsxd  rax, ecx
0x18001b6d9  mov     rdx, [rax+r9]
0x18001b6dd  mov     rax, [r11+10h]
0x18001b6e1  mov     ecx, [rax+8]
0x18001b6e4  mov     rax, [r11+8]
0x18001b6e8  test    byte ptr [rcx+rax+3], 0Fh
0x18001b6ed  jz      short loc_18001B701
0x18001b6ef  movzx   eax, byte ptr [rcx+rax+3]
0x18001b6f4  mov     ecx, 0FFFFFFF0h
0x18001b6f9  and     rax, rcx
0x18001b6fc  add     rax, r10
0x18001b6ff  jmp     short loc_18001B704
0x18001b701  mov     rax, r10
0x18001b704  xor     rdx, rax
0x18001b707  mov     rcx, rdx; StackCookie
0x18001b70a  jmp     __security_check_cookie
```
