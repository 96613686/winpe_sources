# __GSHandlerCheckCommon

- ea: `0x18002bb80`
- end: `0x18002bbe3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002bb5c`
- `0x18002bbec`

## callees

- `0x18002bb80`
- `0x18002bca0`

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
0x18002bb80  mov     r10, rcx
0x18002bb83  mov     r11, rdx
0x18002bb86  mov     ecx, [r8]
0x18002bb89  and     ecx, 0FFFFFFF8h
0x18002bb8c  test    byte ptr [r8], 4
0x18002bb90  jz      short loc_18002BBA7
0x18002bb92  mov     eax, [r8+8]
0x18002bb96  movsxd  r9, dword ptr [r8+4]
0x18002bb9a  neg     eax
0x18002bb9c  movsxd  rdx, eax
0x18002bb9f  add     r9, r10
0x18002bba2  and     r9, rdx
0x18002bba5  jmp     short loc_18002BBAA
0x18002bba7  mov     r9, r10
0x18002bbaa  movsxd  rax, ecx
0x18002bbad  mov     rdx, [rax+r9]
0x18002bbb1  mov     rax, [r11+10h]
0x18002bbb5  mov     ecx, [rax+8]
0x18002bbb8  mov     rax, [r11+8]
0x18002bbbc  test    byte ptr [rcx+rax+3], 0Fh
0x18002bbc1  jz      short loc_18002BBD5
0x18002bbc3  movzx   eax, byte ptr [rcx+rax+3]
0x18002bbc8  mov     ecx, 0FFFFFFF0h
0x18002bbcd  and     rax, rcx
0x18002bbd0  add     rax, r10
0x18002bbd3  jmp     short loc_18002BBD8
0x18002bbd5  mov     rax, r10
0x18002bbd8  xor     rdx, rax
0x18002bbdb  mov     rcx, rdx; StackCookie
0x18002bbde  jmp     __security_check_cookie
```
