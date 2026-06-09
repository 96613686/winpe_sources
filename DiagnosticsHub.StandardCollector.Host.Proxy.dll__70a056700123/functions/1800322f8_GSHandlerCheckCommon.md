# __GSHandlerCheckCommon

- ea: `0x1800322f8`
- end: `0x180032358`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800322d8`
- `0x1800327b0`
- `0x180032944`

## callees

- `0x1800322f8`
- `0x180032370`

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
0x1800322f8  push    rbx
0x1800322fa  mov     r11d, [r8]
0x1800322fd  mov     rbx, rdx
0x180032300  and     r11d, 0FFFFFFF8h
0x180032304  mov     r9, rcx
0x180032307  test    byte ptr [r8], 4
0x18003230b  mov     r10, rcx
0x18003230e  jz      short loc_180032323
0x180032310  mov     eax, [r8+8]
0x180032314  movsxd  r10, dword ptr [r8+4]
0x180032318  neg     eax
0x18003231a  add     r10, rcx
0x18003231d  movsxd  rcx, eax
0x180032320  and     r10, rcx
0x180032323  movsxd  rax, r11d
0x180032326  mov     rdx, [rax+r10]
0x18003232a  mov     rax, [rbx+10h]
0x18003232e  mov     ecx, [rax+8]
0x180032331  mov     rax, [rbx+8]
0x180032335  test    byte ptr [rcx+rax+3], 0Fh
0x18003233a  jz      short loc_18003234C
0x18003233c  movzx   eax, byte ptr [rcx+rax+3]
0x180032341  mov     ecx, 0FFFFFFF0h
0x180032346  and     rax, rcx
0x180032349  add     r9, rax
0x18003234c  xor     r9, rdx
0x18003234f  mov     rcx, r9; StackCookie
0x180032352  pop     rbx
0x180032353  jmp     __security_check_cookie
```
