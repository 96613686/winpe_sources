# __GSHandlerCheckCommon

- ea: `0x180002c38`
- end: `0x180002c9b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c14`
- `0x18000be4c`

## callees

- `0x180002650`
- `0x180002c38`

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
0x180002c38  mov     r10, rcx
0x180002c3b  mov     r11, rdx
0x180002c3e  mov     ecx, [r8]
0x180002c41  and     ecx, 0FFFFFFF8h
0x180002c44  test    byte ptr [r8], 4
0x180002c48  jz      short loc_180002C5F
0x180002c4a  mov     eax, [r8+8]
0x180002c4e  movsxd  r9, dword ptr [r8+4]
0x180002c52  neg     eax
0x180002c54  movsxd  rdx, eax
0x180002c57  add     r9, r10
0x180002c5a  and     r9, rdx
0x180002c5d  jmp     short loc_180002C62
0x180002c5f  mov     r9, r10
0x180002c62  movsxd  rax, ecx
0x180002c65  mov     rdx, [rax+r9]
0x180002c69  mov     rax, [r11+10h]
0x180002c6d  mov     ecx, [rax+8]
0x180002c70  mov     rax, [r11+8]
0x180002c74  test    byte ptr [rcx+rax+3], 0Fh
0x180002c79  jz      short loc_180002C8D
0x180002c7b  movzx   eax, byte ptr [rcx+rax+3]
0x180002c80  mov     ecx, 0FFFFFFF0h
0x180002c85  and     rax, rcx
0x180002c88  add     rax, r10
0x180002c8b  jmp     short loc_180002C90
0x180002c8d  mov     rax, r10
0x180002c90  xor     rdx, rax
0x180002c93  mov     rcx, rdx; StackCookie
0x180002c96  jmp     __security_check_cookie
```
