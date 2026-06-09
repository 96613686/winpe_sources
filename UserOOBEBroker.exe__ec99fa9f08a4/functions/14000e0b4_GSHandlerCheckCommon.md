# __GSHandlerCheckCommon

- ea: `0x14000e0b4`
- end: `0x14000e117`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e090`
- `0x14000e120`

## callees

- `0x14000e0b4`
- `0x14000e1c0`

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
0x14000e0b4  mov     r10, rcx
0x14000e0b7  mov     r11, rdx
0x14000e0ba  mov     ecx, [r8]
0x14000e0bd  and     ecx, 0FFFFFFF8h
0x14000e0c0  test    byte ptr [r8], 4
0x14000e0c4  jz      short loc_14000E0DB
0x14000e0c6  mov     eax, [r8+8]
0x14000e0ca  movsxd  r9, dword ptr [r8+4]
0x14000e0ce  neg     eax
0x14000e0d0  movsxd  rdx, eax
0x14000e0d3  add     r9, r10
0x14000e0d6  and     r9, rdx
0x14000e0d9  jmp     short loc_14000E0DE
0x14000e0db  mov     r9, r10
0x14000e0de  movsxd  rax, ecx
0x14000e0e1  mov     rdx, [rax+r9]
0x14000e0e5  mov     rax, [r11+10h]
0x14000e0e9  mov     ecx, [rax+8]
0x14000e0ec  mov     rax, [r11+8]
0x14000e0f0  test    byte ptr [rcx+rax+3], 0Fh
0x14000e0f5  jz      short loc_14000E109
0x14000e0f7  movzx   eax, byte ptr [rcx+rax+3]
0x14000e0fc  mov     ecx, 0FFFFFFF0h
0x14000e101  and     rax, rcx
0x14000e104  add     rax, r10
0x14000e107  jmp     short loc_14000E10C
0x14000e109  mov     rax, r10
0x14000e10c  xor     rdx, rax
0x14000e10f  mov     rcx, rdx; StackCookie
0x14000e112  jmp     __security_check_cookie
```
