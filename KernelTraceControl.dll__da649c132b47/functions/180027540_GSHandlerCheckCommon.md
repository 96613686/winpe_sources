# __GSHandlerCheckCommon

- ea: `0x180027540`
- end: `0x180027599`
- name: `__GSHandlerCheckCommon`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027520`
- `0x180027868`

## callees

- `0x180026e30`
- `0x180027540`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = *(_QWORD *)(a2 + 16);
  v3 = *(_QWORD *)(a2 + 8) + *(unsigned int *)(result + 8);
  if ( (*(_BYTE *)(v3 + 3) & 0xF) != 0 )
    return *(_BYTE *)(v3 + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180027540  push    rbx
0x180027542  mov     r11d, [r8]
0x180027545  mov     rbx, rdx
0x180027548  and     r11d, 0FFFFFFF8h
0x18002754c  mov     r9, rcx
0x18002754f  test    byte ptr [r8], 4
0x180027553  mov     r10, rcx
0x180027556  jz      short loc_18002756B
0x180027558  mov     eax, [r8+8]
0x18002755c  movsxd  r10, dword ptr [r8+4]
0x180027560  neg     eax
0x180027562  add     r10, rcx
0x180027565  movsxd  rcx, eax
0x180027568  and     r10, rcx
0x18002756b  movsxd  rax, r11d
0x18002756e  mov     rdx, [rax+r10]
0x180027572  mov     rax, [rbx+10h]
0x180027576  mov     ecx, [rax+8]
0x180027579  add     rcx, [rbx+8]
0x18002757d  test    byte ptr [rcx+3], 0Fh
0x180027581  jz      short loc_18002758D
0x180027583  movzx   eax, byte ptr [rcx+3]
0x180027587  and     eax, 0FFFFFFF0h
0x18002758a  add     r9, rax
0x18002758d  xor     r9, rdx
0x180027590  mov     rcx, r9
0x180027593  pop     rbx
0x180027594  jmp     __security_check_cookie
```
