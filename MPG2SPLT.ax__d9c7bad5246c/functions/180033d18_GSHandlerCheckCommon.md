# __GSHandlerCheckCommon

- ea: `0x180033d18`
- end: `0x180033d7b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033cf4`
- `0x180033d84`

## callees

- `0x180001460`
- `0x180033d18`

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
0x180033d18  mov     r10, rcx
0x180033d1b  mov     r11, rdx
0x180033d1e  mov     ecx, [r8]
0x180033d21  and     ecx, 0FFFFFFF8h
0x180033d24  test    byte ptr [r8], 4
0x180033d28  jz      short loc_180033D3F
0x180033d2a  mov     eax, [r8+8]
0x180033d2e  movsxd  r9, dword ptr [r8+4]
0x180033d32  neg     eax
0x180033d34  movsxd  rdx, eax
0x180033d37  add     r9, r10
0x180033d3a  and     r9, rdx
0x180033d3d  jmp     short loc_180033D42
0x180033d3f  mov     r9, r10
0x180033d42  movsxd  rax, ecx
0x180033d45  mov     rdx, [rax+r9]
0x180033d49  mov     rax, [r11+10h]
0x180033d4d  mov     ecx, [rax+8]
0x180033d50  mov     rax, [r11+8]
0x180033d54  test    byte ptr [rcx+rax+3], 0Fh
0x180033d59  jz      short loc_180033D6D
0x180033d5b  movzx   eax, byte ptr [rcx+rax+3]
0x180033d60  mov     ecx, 0FFFFFFF0h
0x180033d65  and     rax, rcx
0x180033d68  add     rax, r10
0x180033d6b  jmp     short loc_180033D70
0x180033d6d  mov     rax, r10
0x180033d70  xor     rdx, rax
0x180033d73  mov     rcx, rdx; StackCookie
0x180033d76  jmp     __security_check_cookie
```
