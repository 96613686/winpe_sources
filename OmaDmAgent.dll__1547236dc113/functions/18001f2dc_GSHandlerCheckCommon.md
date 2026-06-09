# __GSHandlerCheckCommon

- ea: `0x18001f2dc`
- end: `0x18001f33f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f2b8`
- `0x18001f348`

## callees

- `0x18001f2dc`
- `0x18001f420`

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
0x18001f2dc  mov     r10, rcx
0x18001f2df  mov     r11, rdx
0x18001f2e2  mov     ecx, [r8]
0x18001f2e5  and     ecx, 0FFFFFFF8h
0x18001f2e8  test    byte ptr [r8], 4
0x18001f2ec  jz      short loc_18001F303
0x18001f2ee  mov     eax, [r8+8]
0x18001f2f2  movsxd  r9, dword ptr [r8+4]
0x18001f2f6  neg     eax
0x18001f2f8  movsxd  rdx, eax
0x18001f2fb  add     r9, r10
0x18001f2fe  and     r9, rdx
0x18001f301  jmp     short loc_18001F306
0x18001f303  mov     r9, r10
0x18001f306  movsxd  rax, ecx
0x18001f309  mov     rdx, [rax+r9]
0x18001f30d  mov     rax, [r11+10h]
0x18001f311  mov     ecx, [rax+8]
0x18001f314  mov     rax, [r11+8]
0x18001f318  test    byte ptr [rcx+rax+3], 0Fh
0x18001f31d  jz      short loc_18001F331
0x18001f31f  movzx   eax, byte ptr [rcx+rax+3]
0x18001f324  mov     ecx, 0FFFFFFF0h
0x18001f329  and     rax, rcx
0x18001f32c  add     rax, r10
0x18001f32f  jmp     short loc_18001F334
0x18001f331  mov     rax, r10
0x18001f334  xor     rdx, rax
0x18001f337  mov     rcx, rdx; StackCookie
0x18001f33a  jmp     __security_check_cookie
```
