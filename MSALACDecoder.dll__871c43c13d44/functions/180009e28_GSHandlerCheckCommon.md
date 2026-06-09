# __GSHandlerCheckCommon

- ea: `0x180009e28`
- end: `0x180009e8b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e04`
- `0x180009e94`

## callees

- `0x180001550`
- `0x180009e28`

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
0x180009e28  mov     r10, rcx
0x180009e2b  mov     r11, rdx
0x180009e2e  mov     ecx, [r8]
0x180009e31  and     ecx, 0FFFFFFF8h
0x180009e34  test    byte ptr [r8], 4
0x180009e38  jz      short loc_180009E4F
0x180009e3a  mov     eax, [r8+8]
0x180009e3e  movsxd  r9, dword ptr [r8+4]
0x180009e42  neg     eax
0x180009e44  movsxd  rdx, eax
0x180009e47  add     r9, r10
0x180009e4a  and     r9, rdx
0x180009e4d  jmp     short loc_180009E52
0x180009e4f  mov     r9, r10
0x180009e52  movsxd  rax, ecx
0x180009e55  mov     rdx, [rax+r9]
0x180009e59  mov     rax, [r11+10h]
0x180009e5d  mov     ecx, [rax+8]
0x180009e60  mov     rax, [r11+8]
0x180009e64  test    byte ptr [rcx+rax+3], 0Fh
0x180009e69  jz      short loc_180009E7D
0x180009e6b  movzx   eax, byte ptr [rcx+rax+3]
0x180009e70  mov     ecx, 0FFFFFFF0h
0x180009e75  and     rax, rcx
0x180009e78  add     rax, r10
0x180009e7b  jmp     short loc_180009E80
0x180009e7d  mov     rax, r10
0x180009e80  xor     rdx, rax
0x180009e83  mov     rcx, rdx; StackCookie
0x180009e86  jmp     __security_check_cookie
```
