# __GSHandlerCheckCommon

- ea: `0x1800014d0`
- end: `0x18000152b`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800014b0`

## callees

- `0x1800014d0`
- `0x180001540`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x1800014d0  push    rbx
0x1800014d2  mov     r11d, [r8]
0x1800014d5  mov     rbx, rdx
0x1800014d8  and     r11d, 0FFFFFFF8h
0x1800014dc  mov     r9, rcx
0x1800014df  test    byte ptr [r8], 4
0x1800014e3  mov     r10, rcx
0x1800014e6  jz      short loc_1800014FB
0x1800014e8  mov     eax, [r8+8]
0x1800014ec  movsxd  r10, dword ptr [r8+4]
0x1800014f0  neg     eax
0x1800014f2  add     r10, rcx
0x1800014f5  movsxd  rcx, eax
0x1800014f8  and     r10, rcx
0x1800014fb  movsxd  rax, r11d
0x1800014fe  mov     rdx, [rax+r10]
0x180001502  mov     rax, [rbx+10h]
0x180001506  mov     ecx, [rax+8]
0x180001509  mov     rax, [rbx+8]
0x18000150d  test    byte ptr [rcx+rax+3], 0Fh
0x180001512  jz      short loc_18000151F
0x180001514  movzx   eax, byte ptr [rcx+rax+3]
0x180001519  and     eax, 0FFFFFFF0h
0x18000151c  add     r9, rax
0x18000151f  xor     r9, rdx
0x180001522  mov     rcx, r9; StackCookie
0x180001525  pop     rbx
0x180001526  jmp     __security_check_cookie
```
