# __GSHandlerCheckCommon

- ea: `0x1800022b4`
- end: `0x180002317`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002234`

## callees

- `0x1800022b4`
- `0x180002340`

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
0x1800022b4  mov     r10, rcx
0x1800022b7  mov     r11, rdx
0x1800022ba  mov     ecx, [r8]
0x1800022bd  and     ecx, 0FFFFFFF8h
0x1800022c0  test    byte ptr [r8], 4
0x1800022c4  jz      short loc_1800022DB
0x1800022c6  mov     eax, [r8+8]
0x1800022ca  movsxd  r9, dword ptr [r8+4]
0x1800022ce  neg     eax
0x1800022d0  movsxd  rdx, eax
0x1800022d3  add     r9, r10
0x1800022d6  and     r9, rdx
0x1800022d9  jmp     short loc_1800022DE
0x1800022db  mov     r9, r10
0x1800022de  movsxd  rax, ecx
0x1800022e1  mov     rdx, [rax+r9]
0x1800022e5  mov     rax, [r11+10h]
0x1800022e9  mov     ecx, [rax+8]
0x1800022ec  mov     rax, [r11+8]
0x1800022f0  test    byte ptr [rcx+rax+3], 0Fh
0x1800022f5  jz      short loc_180002309
0x1800022f7  movzx   eax, byte ptr [rcx+rax+3]
0x1800022fc  mov     ecx, 0FFFFFFF0h
0x180002301  and     rax, rcx
0x180002304  add     rax, r10
0x180002307  jmp     short loc_18000230C
0x180002309  mov     rax, r10
0x18000230c  xor     rdx, rax
0x18000230f  mov     rcx, rdx; StackCookie
0x180002312  jmp     __security_check_cookie
```
