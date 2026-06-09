# __GSHandlerCheckCommon

- ea: `0x180002b7c`
- end: `0x180002bdf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b58`

## callees

- `0x180001400`
- `0x180002b7c`

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
0x180002b7c  mov     r10, rcx
0x180002b7f  mov     r11, rdx
0x180002b82  mov     ecx, [r8]
0x180002b85  and     ecx, 0FFFFFFF8h
0x180002b88  test    byte ptr [r8], 4
0x180002b8c  jz      short loc_180002BA3
0x180002b8e  mov     eax, [r8+8]
0x180002b92  movsxd  r9, dword ptr [r8+4]
0x180002b96  neg     eax
0x180002b98  movsxd  rdx, eax
0x180002b9b  add     r9, r10
0x180002b9e  and     r9, rdx
0x180002ba1  jmp     short loc_180002BA6
0x180002ba3  mov     r9, r10
0x180002ba6  movsxd  rax, ecx
0x180002ba9  mov     rdx, [rax+r9]
0x180002bad  mov     rax, [r11+10h]
0x180002bb1  mov     ecx, [rax+8]
0x180002bb4  mov     rax, [r11+8]
0x180002bb8  test    byte ptr [rcx+rax+3], 0Fh
0x180002bbd  jz      short loc_180002BD1
0x180002bbf  movzx   eax, byte ptr [rcx+rax+3]
0x180002bc4  mov     ecx, 0FFFFFFF0h
0x180002bc9  and     rax, rcx
0x180002bcc  add     rax, r10
0x180002bcf  jmp     short loc_180002BD4
0x180002bd1  mov     rax, r10
0x180002bd4  xor     rdx, rax
0x180002bd7  mov     rcx, rdx; StackCookie
0x180002bda  jmp     __security_check_cookie
```
