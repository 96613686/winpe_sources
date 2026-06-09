# __GSHandlerCheckCommon

- ea: `0x180009e0c`
- end: `0x180009e6f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009de8`
- `0x180009e78`

## callees

- `0x180009e0c`
- `0x180009f30`

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
0x180009e0c  mov     r10, rcx
0x180009e0f  mov     r11, rdx
0x180009e12  mov     ecx, [r8]
0x180009e15  and     ecx, 0FFFFFFF8h
0x180009e18  test    byte ptr [r8], 4
0x180009e1c  jz      short loc_180009E33
0x180009e1e  mov     eax, [r8+8]
0x180009e22  movsxd  r9, dword ptr [r8+4]
0x180009e26  neg     eax
0x180009e28  movsxd  rdx, eax
0x180009e2b  add     r9, r10
0x180009e2e  and     r9, rdx
0x180009e31  jmp     short loc_180009E36
0x180009e33  mov     r9, r10
0x180009e36  movsxd  rax, ecx
0x180009e39  mov     rdx, [rax+r9]
0x180009e3d  mov     rax, [r11+10h]
0x180009e41  mov     ecx, [rax+8]
0x180009e44  mov     rax, [r11+8]
0x180009e48  test    byte ptr [rcx+rax+3], 0Fh
0x180009e4d  jz      short loc_180009E61
0x180009e4f  movzx   eax, byte ptr [rcx+rax+3]
0x180009e54  mov     ecx, 0FFFFFFF0h
0x180009e59  and     rax, rcx
0x180009e5c  add     rax, r10
0x180009e5f  jmp     short loc_180009E64
0x180009e61  mov     rax, r10
0x180009e64  xor     rdx, rax
0x180009e67  mov     rcx, rdx; StackCookie
0x180009e6a  jmp     __security_check_cookie
```
