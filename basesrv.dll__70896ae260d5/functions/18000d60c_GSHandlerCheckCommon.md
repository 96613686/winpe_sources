# __GSHandlerCheckCommon

- ea: `0x18000d60c`
- end: `0x18000d667`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d5e8`
- `0x18000d670`

## callees

- `0x18000d60c`
- `0x18000d730`

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
0x18000d60c  push    rbx
0x18000d60e  mov     r11d, [r8]
0x18000d611  mov     rbx, rdx
0x18000d614  and     r11d, 0FFFFFFF8h
0x18000d618  mov     r9, rcx
0x18000d61b  test    byte ptr [r8], 4
0x18000d61f  mov     r10, rcx
0x18000d622  jz      short loc_18000D637
0x18000d624  mov     eax, [r8+8]
0x18000d628  movsxd  r10, dword ptr [r8+4]
0x18000d62c  neg     eax
0x18000d62e  add     r10, rcx
0x18000d631  movsxd  rcx, eax
0x18000d634  and     r10, rcx
0x18000d637  movsxd  rax, r11d
0x18000d63a  mov     rdx, [rax+r10]
0x18000d63e  mov     rax, [rbx+10h]
0x18000d642  mov     ecx, [rax+8]
0x18000d645  mov     rax, [rbx+8]
0x18000d649  test    byte ptr [rcx+rax+3], 0Fh
0x18000d64e  jz      short loc_18000D65B
0x18000d650  movzx   eax, byte ptr [rcx+rax+3]
0x18000d655  and     eax, 0FFFFFFF0h
0x18000d658  add     r9, rax
0x18000d65b  xor     r9, rdx
0x18000d65e  mov     rcx, r9; StackCookie
0x18000d661  pop     rbx
0x18000d662  jmp     __security_check_cookie
```
