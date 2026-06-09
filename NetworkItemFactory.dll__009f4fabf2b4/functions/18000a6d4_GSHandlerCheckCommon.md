# __GSHandlerCheckCommon

- ea: `0x18000a6d4`
- end: `0x18000a737`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6b0`
- `0x18000a740`

## callees

- `0x18000a6d4`
- `0x18000a7d0`

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
0x18000a6d4  mov     r10, rcx
0x18000a6d7  mov     r11, rdx
0x18000a6da  mov     ecx, [r8]
0x18000a6dd  and     ecx, 0FFFFFFF8h
0x18000a6e0  test    byte ptr [r8], 4
0x18000a6e4  jz      short loc_18000A6FB
0x18000a6e6  mov     eax, [r8+8]
0x18000a6ea  movsxd  r9, dword ptr [r8+4]
0x18000a6ee  neg     eax
0x18000a6f0  movsxd  rdx, eax
0x18000a6f3  add     r9, r10
0x18000a6f6  and     r9, rdx
0x18000a6f9  jmp     short loc_18000A6FE
0x18000a6fb  mov     r9, r10
0x18000a6fe  movsxd  rax, ecx
0x18000a701  mov     rdx, [rax+r9]
0x18000a705  mov     rax, [r11+10h]
0x18000a709  mov     ecx, [rax+8]
0x18000a70c  mov     rax, [r11+8]
0x18000a710  test    byte ptr [rcx+rax+3], 0Fh
0x18000a715  jz      short loc_18000A729
0x18000a717  movzx   eax, byte ptr [rcx+rax+3]
0x18000a71c  mov     ecx, 0FFFFFFF0h
0x18000a721  and     rax, rcx
0x18000a724  add     rax, r10
0x18000a727  jmp     short loc_18000A72C
0x18000a729  mov     rax, r10
0x18000a72c  xor     rdx, rax
0x18000a72f  mov     rcx, rdx; StackCookie
0x18000a732  jmp     __security_check_cookie
```
