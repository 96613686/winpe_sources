# __GSHandlerCheckCommon

- ea: `0x1800029cc`
- end: `0x180002a2f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029a8`
- `0x18000c8ec`

## callees

- `0x1800029cc`
- `0x18000c990`

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
0x1800029cc  mov     r10, rcx
0x1800029cf  mov     r11, rdx
0x1800029d2  mov     ecx, [r8]
0x1800029d5  and     ecx, 0FFFFFFF8h
0x1800029d8  test    byte ptr [r8], 4
0x1800029dc  jz      short loc_1800029F3
0x1800029de  mov     eax, [r8+8]
0x1800029e2  movsxd  r9, dword ptr [r8+4]
0x1800029e6  neg     eax
0x1800029e8  movsxd  rdx, eax
0x1800029eb  add     r9, r10
0x1800029ee  and     r9, rdx
0x1800029f1  jmp     short loc_1800029F6
0x1800029f3  mov     r9, r10
0x1800029f6  movsxd  rax, ecx
0x1800029f9  mov     rdx, [rax+r9]
0x1800029fd  mov     rax, [r11+10h]
0x180002a01  mov     ecx, [rax+8]
0x180002a04  mov     rax, [r11+8]
0x180002a08  test    byte ptr [rcx+rax+3], 0Fh
0x180002a0d  jz      short loc_180002A21
0x180002a0f  movzx   eax, byte ptr [rcx+rax+3]
0x180002a14  mov     ecx, 0FFFFFFF0h
0x180002a19  and     rax, rcx
0x180002a1c  add     rax, r10
0x180002a1f  jmp     short loc_180002A24
0x180002a21  mov     rax, r10
0x180002a24  xor     rdx, rax
0x180002a27  mov     rcx, rdx; StackCookie
0x180002a2a  jmp     __security_check_cookie
```
