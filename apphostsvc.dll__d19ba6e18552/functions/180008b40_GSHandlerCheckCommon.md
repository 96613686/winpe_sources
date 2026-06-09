# __GSHandlerCheckCommon

- ea: `0x180008b40`
- end: `0x180008ba3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b1c`
- `0x180008bac`

## callees

- `0x180008b40`
- `0x180008c50`

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
0x180008b40  mov     r10, rcx
0x180008b43  mov     r11, rdx
0x180008b46  mov     ecx, [r8]
0x180008b49  and     ecx, 0FFFFFFF8h
0x180008b4c  test    byte ptr [r8], 4
0x180008b50  jz      short loc_180008B67
0x180008b52  mov     eax, [r8+8]
0x180008b56  movsxd  r9, dword ptr [r8+4]
0x180008b5a  neg     eax
0x180008b5c  movsxd  rdx, eax
0x180008b5f  add     r9, r10
0x180008b62  and     r9, rdx
0x180008b65  jmp     short loc_180008B6A
0x180008b67  mov     r9, r10
0x180008b6a  movsxd  rax, ecx
0x180008b6d  mov     rdx, [rax+r9]
0x180008b71  mov     rax, [r11+10h]
0x180008b75  mov     ecx, [rax+8]
0x180008b78  mov     rax, [r11+8]
0x180008b7c  test    byte ptr [rcx+rax+3], 0Fh
0x180008b81  jz      short loc_180008B95
0x180008b83  movzx   eax, byte ptr [rcx+rax+3]
0x180008b88  mov     ecx, 0FFFFFFF0h
0x180008b8d  and     rax, rcx
0x180008b90  add     rax, r10
0x180008b93  jmp     short loc_180008B98
0x180008b95  mov     rax, r10
0x180008b98  xor     rdx, rax
0x180008b9b  mov     rcx, rdx; StackCookie
0x180008b9e  jmp     __security_check_cookie
```
