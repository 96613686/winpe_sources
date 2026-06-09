# __GSHandlerCheckCommon

- ea: `0x18002287c`
- end: `0x1800228df`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022858`

## callees

- `0x180001ac0`
- `0x18002287c`

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
0x18002287c  mov     r10, rcx
0x18002287f  mov     r11, rdx
0x180022882  mov     ecx, [r8]
0x180022885  and     ecx, 0FFFFFFF8h
0x180022888  test    byte ptr [r8], 4
0x18002288c  jz      short loc_1800228A3
0x18002288e  mov     eax, [r8+8]
0x180022892  movsxd  r9, dword ptr [r8+4]
0x180022896  neg     eax
0x180022898  movsxd  rdx, eax
0x18002289b  add     r9, r10
0x18002289e  and     r9, rdx
0x1800228a1  jmp     short loc_1800228A6
0x1800228a3  mov     r9, r10
0x1800228a6  movsxd  rax, ecx
0x1800228a9  mov     rdx, [rax+r9]
0x1800228ad  mov     rax, [r11+10h]
0x1800228b1  mov     ecx, [rax+8]
0x1800228b4  mov     rax, [r11+8]
0x1800228b8  test    byte ptr [rcx+rax+3], 0Fh
0x1800228bd  jz      short loc_1800228D1
0x1800228bf  movzx   eax, byte ptr [rcx+rax+3]
0x1800228c4  mov     ecx, 0FFFFFFF0h
0x1800228c9  and     rax, rcx
0x1800228cc  add     rax, r10
0x1800228cf  jmp     short loc_1800228D4
0x1800228d1  mov     rax, r10
0x1800228d4  xor     rdx, rax
0x1800228d7  mov     rcx, rdx; StackCookie
0x1800228da  jmp     __security_check_cookie
```
