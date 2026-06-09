# __GSHandlerCheckCommon

- ea: `0x1800027a0`
- end: `0x180002800`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002780`
- `0x180032aa0`
- `0x180032c34`

## callees

- `0x1800027a0`
- `0x180002810`

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
0x1800027a0  push    rbx
0x1800027a2  mov     r11d, [r8]
0x1800027a5  mov     rbx, rdx
0x1800027a8  and     r11d, 0FFFFFFF8h
0x1800027ac  mov     r9, rcx
0x1800027af  test    byte ptr [r8], 4
0x1800027b3  mov     r10, rcx
0x1800027b6  jz      short loc_1800027CB
0x1800027b8  mov     eax, [r8+8]
0x1800027bc  movsxd  r10, dword ptr [r8+4]
0x1800027c0  neg     eax
0x1800027c2  add     r10, rcx
0x1800027c5  movsxd  rcx, eax
0x1800027c8  and     r10, rcx
0x1800027cb  movsxd  rax, r11d
0x1800027ce  mov     rdx, [rax+r10]
0x1800027d2  mov     rax, [rbx+10h]
0x1800027d6  mov     ecx, [rax+8]
0x1800027d9  mov     rax, [rbx+8]
0x1800027dd  test    byte ptr [rcx+rax+3], 0Fh
0x1800027e2  jz      short loc_1800027F4
0x1800027e4  movzx   eax, byte ptr [rcx+rax+3]
0x1800027e9  mov     ecx, 0FFFFFFF0h
0x1800027ee  and     rax, rcx
0x1800027f1  add     r9, rax
0x1800027f4  xor     r9, rdx
0x1800027f7  mov     rcx, r9; StackCookie
0x1800027fa  pop     rbx
0x1800027fb  jmp     __security_check_cookie
```
