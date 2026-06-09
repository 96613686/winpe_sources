# __GSHandlerCheckCommon

- ea: `0x180006d10`
- end: `0x180006d73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006cec`

## callees

- `0x180006d10`
- `0x180006dd0`

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
0x180006d10  mov     r10, rcx
0x180006d13  mov     r11, rdx
0x180006d16  mov     ecx, [r8]
0x180006d19  and     ecx, 0FFFFFFF8h
0x180006d1c  test    byte ptr [r8], 4
0x180006d20  jz      short loc_180006D37
0x180006d22  mov     eax, [r8+8]
0x180006d26  movsxd  r9, dword ptr [r8+4]
0x180006d2a  neg     eax
0x180006d2c  movsxd  rdx, eax
0x180006d2f  add     r9, r10
0x180006d32  and     r9, rdx
0x180006d35  jmp     short loc_180006D3A
0x180006d37  mov     r9, r10
0x180006d3a  movsxd  rax, ecx
0x180006d3d  mov     rdx, [rax+r9]
0x180006d41  mov     rax, [r11+10h]
0x180006d45  mov     ecx, [rax+8]
0x180006d48  mov     rax, [r11+8]
0x180006d4c  test    byte ptr [rcx+rax+3], 0Fh
0x180006d51  jz      short loc_180006D65
0x180006d53  movzx   eax, byte ptr [rcx+rax+3]
0x180006d58  mov     ecx, 0FFFFFFF0h
0x180006d5d  and     rax, rcx
0x180006d60  add     rax, r10
0x180006d63  jmp     short loc_180006D68
0x180006d65  mov     rax, r10
0x180006d68  xor     rdx, rax
0x180006d6b  mov     rcx, rdx; StackCookie
0x180006d6e  jmp     __security_check_cookie
```
