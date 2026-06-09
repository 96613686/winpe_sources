# __GSHandlerCheckCommon

- ea: `0x18000d1dc`
- end: `0x18000d23f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d1b8`
- `0x18000d248`

## callees

- `0x18000d1dc`
- `0x18000d300`

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
0x18000d1dc  mov     r10, rcx
0x18000d1df  mov     r11, rdx
0x18000d1e2  mov     ecx, [r8]
0x18000d1e5  and     ecx, 0FFFFFFF8h
0x18000d1e8  test    byte ptr [r8], 4
0x18000d1ec  jz      short loc_18000D203
0x18000d1ee  mov     eax, [r8+8]
0x18000d1f2  movsxd  r9, dword ptr [r8+4]
0x18000d1f6  neg     eax
0x18000d1f8  movsxd  rdx, eax
0x18000d1fb  add     r9, r10
0x18000d1fe  and     r9, rdx
0x18000d201  jmp     short loc_18000D206
0x18000d203  mov     r9, r10
0x18000d206  movsxd  rax, ecx
0x18000d209  mov     rdx, [rax+r9]
0x18000d20d  mov     rax, [r11+10h]
0x18000d211  mov     ecx, [rax+8]
0x18000d214  mov     rax, [r11+8]
0x18000d218  test    byte ptr [rcx+rax+3], 0Fh
0x18000d21d  jz      short loc_18000D231
0x18000d21f  movzx   eax, byte ptr [rcx+rax+3]
0x18000d224  mov     ecx, 0FFFFFFF0h
0x18000d229  and     rax, rcx
0x18000d22c  add     rax, r10
0x18000d22f  jmp     short loc_18000D234
0x18000d231  mov     rax, r10
0x18000d234  xor     rdx, rax
0x18000d237  mov     rcx, rdx; StackCookie
0x18000d23a  jmp     __security_check_cookie
```
