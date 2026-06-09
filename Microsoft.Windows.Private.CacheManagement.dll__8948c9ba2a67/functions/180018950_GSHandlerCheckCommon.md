# __GSHandlerCheckCommon

- ea: `0x180018950`
- end: `0x1800189b0`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018930`
- `0x180018c48`
- `0x18001c6bc`

## callees

- `0x1800181b0`
- `0x180018950`

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
0x180018950  push    rbx
0x180018952  mov     r11d, [r8]
0x180018955  mov     rbx, rdx
0x180018958  and     r11d, 0FFFFFFF8h
0x18001895c  mov     r9, rcx
0x18001895f  test    byte ptr [r8], 4
0x180018963  mov     r10, rcx
0x180018966  jz      short loc_18001897B
0x180018968  mov     eax, [r8+8]
0x18001896c  movsxd  r10, dword ptr [r8+4]
0x180018970  neg     eax
0x180018972  add     r10, rcx
0x180018975  movsxd  rcx, eax
0x180018978  and     r10, rcx
0x18001897b  movsxd  rax, r11d
0x18001897e  mov     rdx, [rax+r10]
0x180018982  mov     rax, [rbx+10h]
0x180018986  mov     ecx, [rax+8]
0x180018989  mov     rax, [rbx+8]
0x18001898d  test    byte ptr [rcx+rax+3], 0Fh
0x180018992  jz      short loc_1800189A4
0x180018994  movzx   eax, byte ptr [rcx+rax+3]
0x180018999  mov     ecx, 0FFFFFFF0h
0x18001899e  and     rax, rcx
0x1800189a1  add     r9, rax
0x1800189a4  xor     r9, rdx
0x1800189a7  mov     rcx, r9; StackCookie
0x1800189aa  pop     rbx
0x1800189ab  jmp     __security_check_cookie
```
