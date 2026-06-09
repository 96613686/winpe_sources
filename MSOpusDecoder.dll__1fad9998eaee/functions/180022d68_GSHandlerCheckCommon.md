# __GSHandlerCheckCommon

- ea: `0x180022d68`
- end: `0x180022dcb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022d44`
- `0x180022dd4`

## callees

- `0x1800018f0`
- `0x180022d68`

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
0x180022d68  mov     r10, rcx
0x180022d6b  mov     r11, rdx
0x180022d6e  mov     ecx, [r8]
0x180022d71  and     ecx, 0FFFFFFF8h
0x180022d74  test    byte ptr [r8], 4
0x180022d78  jz      short loc_180022D8F
0x180022d7a  mov     eax, [r8+8]
0x180022d7e  movsxd  r9, dword ptr [r8+4]
0x180022d82  neg     eax
0x180022d84  movsxd  rdx, eax
0x180022d87  add     r9, r10
0x180022d8a  and     r9, rdx
0x180022d8d  jmp     short loc_180022D92
0x180022d8f  mov     r9, r10
0x180022d92  movsxd  rax, ecx
0x180022d95  mov     rdx, [rax+r9]
0x180022d99  mov     rax, [r11+10h]
0x180022d9d  mov     ecx, [rax+8]
0x180022da0  mov     rax, [r11+8]
0x180022da4  test    byte ptr [rcx+rax+3], 0Fh
0x180022da9  jz      short loc_180022DBD
0x180022dab  movzx   eax, byte ptr [rcx+rax+3]
0x180022db0  mov     ecx, 0FFFFFFF0h
0x180022db5  and     rax, rcx
0x180022db8  add     rax, r10
0x180022dbb  jmp     short loc_180022DC0
0x180022dbd  mov     rax, r10
0x180022dc0  xor     rdx, rax
0x180022dc3  mov     rcx, rdx; StackCookie
0x180022dc6  jmp     __security_check_cookie
```
