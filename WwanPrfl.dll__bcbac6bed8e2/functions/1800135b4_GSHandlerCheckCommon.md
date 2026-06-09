# __GSHandlerCheckCommon

- ea: `0x1800135b4`
- end: `0x180013617`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013590`
- `0x180013620`

## callees

- `0x180001670`
- `0x1800135b4`

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
0x1800135b4  mov     r10, rcx
0x1800135b7  mov     r11, rdx
0x1800135ba  mov     ecx, [r8]
0x1800135bd  and     ecx, 0FFFFFFF8h
0x1800135c0  test    byte ptr [r8], 4
0x1800135c4  jz      short loc_1800135DB
0x1800135c6  mov     eax, [r8+8]
0x1800135ca  movsxd  r9, dword ptr [r8+4]
0x1800135ce  neg     eax
0x1800135d0  movsxd  rdx, eax
0x1800135d3  add     r9, r10
0x1800135d6  and     r9, rdx
0x1800135d9  jmp     short loc_1800135DE
0x1800135db  mov     r9, r10
0x1800135de  movsxd  rax, ecx
0x1800135e1  mov     rdx, [rax+r9]
0x1800135e5  mov     rax, [r11+10h]
0x1800135e9  mov     ecx, [rax+8]
0x1800135ec  mov     rax, [r11+8]
0x1800135f0  test    byte ptr [rcx+rax+3], 0Fh
0x1800135f5  jz      short loc_180013609
0x1800135f7  movzx   eax, byte ptr [rcx+rax+3]
0x1800135fc  mov     ecx, 0FFFFFFF0h
0x180013601  and     rax, rcx
0x180013604  add     rax, r10
0x180013607  jmp     short loc_18001360C
0x180013609  mov     rax, r10
0x18001360c  xor     rdx, rax
0x18001360f  mov     rcx, rdx; StackCookie
0x180013612  jmp     __security_check_cookie
```
