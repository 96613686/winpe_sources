# __GSHandlerCheckCommon

- ea: `0x100469920`
- end: `0x10046997b`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1004698fc`
- `0x100469984`

## callees

- `0x100468a30`
- `0x100469920`

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
0x100469920  push    rbx
0x100469922  mov     r11d, [r8]
0x100469925  mov     rbx, rdx
0x100469928  and     r11d, 0FFFFFFF8h
0x10046992c  mov     r9, rcx
0x10046992f  test    byte ptr [r8], 4
0x100469933  mov     r10, rcx
0x100469936  jz      short loc_10046994B
0x100469938  mov     eax, [r8+8]
0x10046993c  movsxd  r10, dword ptr [r8+4]
0x100469940  neg     eax
0x100469942  add     r10, rcx
0x100469945  movsxd  rcx, eax
0x100469948  and     r10, rcx
0x10046994b  movsxd  rax, r11d
0x10046994e  mov     rdx, [rax+r10]
0x100469952  mov     rax, [rbx+10h]
0x100469956  mov     ecx, [rax+8]
0x100469959  mov     rax, [rbx+8]
0x10046995d  test    byte ptr [rcx+rax+3], 0Fh
0x100469962  jz      short loc_10046996F
0x100469964  movzx   eax, byte ptr [rcx+rax+3]
0x100469969  and     eax, 0FFFFFFF0h
0x10046996c  add     r9, rax
0x10046996f  xor     r9, rdx
0x100469972  mov     rcx, r9; StackCookie
0x100469975  pop     rbx
0x100469976  jmp     __security_check_cookie
```
