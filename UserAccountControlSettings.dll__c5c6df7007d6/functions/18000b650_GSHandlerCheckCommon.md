# __GSHandlerCheckCommon

- ea: `0x18000b650`
- end: `0x18000b6b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b62c`

## callees

- `0x18000b650`
- `0x18000b710`

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
0x18000b650  mov     r10, rcx
0x18000b653  mov     r11, rdx
0x18000b656  mov     ecx, [r8]
0x18000b659  and     ecx, 0FFFFFFF8h
0x18000b65c  test    byte ptr [r8], 4
0x18000b660  jz      short loc_18000B677
0x18000b662  mov     eax, [r8+8]
0x18000b666  movsxd  r9, dword ptr [r8+4]
0x18000b66a  neg     eax
0x18000b66c  movsxd  rdx, eax
0x18000b66f  add     r9, r10
0x18000b672  and     r9, rdx
0x18000b675  jmp     short loc_18000B67A
0x18000b677  mov     r9, r10
0x18000b67a  movsxd  rax, ecx
0x18000b67d  mov     rdx, [rax+r9]
0x18000b681  mov     rax, [r11+10h]
0x18000b685  mov     ecx, [rax+8]
0x18000b688  mov     rax, [r11+8]
0x18000b68c  test    byte ptr [rcx+rax+3], 0Fh
0x18000b691  jz      short loc_18000B6A5
0x18000b693  movzx   eax, byte ptr [rcx+rax+3]
0x18000b698  mov     ecx, 0FFFFFFF0h
0x18000b69d  and     rax, rcx
0x18000b6a0  add     rax, r10
0x18000b6a3  jmp     short loc_18000B6A8
0x18000b6a5  mov     rax, r10
0x18000b6a8  xor     rdx, rax
0x18000b6ab  mov     rcx, rdx; StackCookie
0x18000b6ae  jmp     __security_check_cookie
```
