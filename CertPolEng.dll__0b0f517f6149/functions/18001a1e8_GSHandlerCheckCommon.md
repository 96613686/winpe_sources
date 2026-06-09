# __GSHandlerCheckCommon

- ea: `0x18001a1e8`
- end: `0x18001a24b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a1c4`
- `0x18001a254`
- `0x18001a2bc`

## callees

- `0x18001a1e8`
- `0x18001a380`

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
0x18001a1e8  mov     r10, rcx
0x18001a1eb  mov     r11, rdx
0x18001a1ee  mov     ecx, [r8]
0x18001a1f1  and     ecx, 0FFFFFFF8h
0x18001a1f4  test    byte ptr [r8], 4
0x18001a1f8  jz      short loc_18001A20F
0x18001a1fa  mov     eax, [r8+8]
0x18001a1fe  movsxd  r9, dword ptr [r8+4]
0x18001a202  neg     eax
0x18001a204  movsxd  rdx, eax
0x18001a207  add     r9, r10
0x18001a20a  and     r9, rdx
0x18001a20d  jmp     short loc_18001A212
0x18001a20f  mov     r9, r10
0x18001a212  movsxd  rax, ecx
0x18001a215  mov     rdx, [rax+r9]
0x18001a219  mov     rax, [r11+10h]
0x18001a21d  mov     ecx, [rax+8]
0x18001a220  mov     rax, [r11+8]
0x18001a224  test    byte ptr [rcx+rax+3], 0Fh
0x18001a229  jz      short loc_18001A23D
0x18001a22b  movzx   eax, byte ptr [rcx+rax+3]
0x18001a230  mov     ecx, 0FFFFFFF0h
0x18001a235  and     rax, rcx
0x18001a238  add     rax, r10
0x18001a23b  jmp     short loc_18001A240
0x18001a23d  mov     rax, r10
0x18001a240  xor     rdx, rax
0x18001a243  mov     rcx, rdx; StackCookie
0x18001a246  jmp     __security_check_cookie
```
