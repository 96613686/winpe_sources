# __GSHandlerCheckCommon

- ea: `0x18003d360`
- end: `0x18003d3c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d33c`
- `0x18003d3cc`
- `0x18003d434`

## callees

- `0x18003d360`
- `0x18003d510`

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
0x18003d360  mov     r10, rcx
0x18003d363  mov     r11, rdx
0x18003d366  mov     ecx, [r8]
0x18003d369  and     ecx, 0FFFFFFF8h
0x18003d36c  test    byte ptr [r8], 4
0x18003d370  jz      short loc_18003D387
0x18003d372  mov     eax, [r8+8]
0x18003d376  movsxd  r9, dword ptr [r8+4]
0x18003d37a  neg     eax
0x18003d37c  movsxd  rdx, eax
0x18003d37f  add     r9, r10
0x18003d382  and     r9, rdx
0x18003d385  jmp     short loc_18003D38A
0x18003d387  mov     r9, r10
0x18003d38a  movsxd  rax, ecx
0x18003d38d  mov     rdx, [rax+r9]
0x18003d391  mov     rax, [r11+10h]
0x18003d395  mov     ecx, [rax+8]
0x18003d398  mov     rax, [r11+8]
0x18003d39c  test    byte ptr [rcx+rax+3], 0Fh
0x18003d3a1  jz      short loc_18003D3B5
0x18003d3a3  movzx   eax, byte ptr [rcx+rax+3]
0x18003d3a8  mov     ecx, 0FFFFFFF0h
0x18003d3ad  and     rax, rcx
0x18003d3b0  add     rax, r10
0x18003d3b3  jmp     short loc_18003D3B8
0x18003d3b5  mov     rax, r10
0x18003d3b8  xor     rdx, rax
0x18003d3bb  mov     rcx, rdx; StackCookie
0x18003d3be  jmp     __security_check_cookie
```
