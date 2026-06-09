# __GSHandlerCheckCommon

- ea: `0x180008f88`
- end: `0x180008feb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008f64`
- `0x180008ff4`

## callees

- `0x180001400`
- `0x180008f88`

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
0x180008f88  mov     r10, rcx
0x180008f8b  mov     r11, rdx
0x180008f8e  mov     ecx, [r8]
0x180008f91  and     ecx, 0FFFFFFF8h
0x180008f94  test    byte ptr [r8], 4
0x180008f98  jz      short loc_180008FAF
0x180008f9a  mov     eax, [r8+8]
0x180008f9e  movsxd  r9, dword ptr [r8+4]
0x180008fa2  neg     eax
0x180008fa4  movsxd  rdx, eax
0x180008fa7  add     r9, r10
0x180008faa  and     r9, rdx
0x180008fad  jmp     short loc_180008FB2
0x180008faf  mov     r9, r10
0x180008fb2  movsxd  rax, ecx
0x180008fb5  mov     rdx, [rax+r9]
0x180008fb9  mov     rax, [r11+10h]
0x180008fbd  mov     ecx, [rax+8]
0x180008fc0  mov     rax, [r11+8]
0x180008fc4  test    byte ptr [rcx+rax+3], 0Fh
0x180008fc9  jz      short loc_180008FDD
0x180008fcb  movzx   eax, byte ptr [rcx+rax+3]
0x180008fd0  mov     ecx, 0FFFFFFF0h
0x180008fd5  and     rax, rcx
0x180008fd8  add     rax, r10
0x180008fdb  jmp     short loc_180008FE0
0x180008fdd  mov     rax, r10
0x180008fe0  xor     rdx, rax
0x180008fe3  mov     rcx, rdx; StackCookie
0x180008fe6  jmp     __security_check_cookie
```
