# __GSHandlerCheckCommon

- ea: `0x18001ae20`
- end: `0x18001ae7b`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ae00`
- `0x18001af4c`
- `0x18001b040`

## callees

- `0x180007700`
- `0x18001ae20`

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
0x18001ae20  push    rbx
0x18001ae22  mov     r11d, [r8]
0x18001ae25  mov     rbx, rdx
0x18001ae28  and     r11d, 0FFFFFFF8h
0x18001ae2c  mov     r9, rcx
0x18001ae2f  test    byte ptr [r8], 4
0x18001ae33  mov     r10, rcx
0x18001ae36  jz      short loc_18001AE4B
0x18001ae38  mov     eax, [r8+8]
0x18001ae3c  movsxd  r10, dword ptr [r8+4]
0x18001ae40  neg     eax
0x18001ae42  add     r10, rcx
0x18001ae45  movsxd  rcx, eax
0x18001ae48  and     r10, rcx
0x18001ae4b  movsxd  rax, r11d
0x18001ae4e  mov     rdx, [rax+r10]
0x18001ae52  mov     rax, [rbx+10h]
0x18001ae56  mov     ecx, [rax+8]
0x18001ae59  mov     rax, [rbx+8]
0x18001ae5d  test    byte ptr [rcx+rax+3], 0Fh
0x18001ae62  jz      short loc_18001AE6F
0x18001ae64  movzx   eax, byte ptr [rcx+rax+3]
0x18001ae69  and     eax, 0FFFFFFF0h
0x18001ae6c  add     r9, rax
0x18001ae6f  xor     r9, rdx
0x18001ae72  mov     rcx, r9; StackCookie
0x18001ae75  pop     rbx
0x18001ae76  jmp     __security_check_cookie
```
