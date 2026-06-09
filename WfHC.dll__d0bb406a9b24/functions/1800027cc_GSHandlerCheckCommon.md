# __GSHandlerCheckCommon

- ea: `0x1800027cc`
- end: `0x18000282f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800027a8`
- `0x18000c4f8`

## callees

- `0x1800027cc`
- `0x18000c5b0`

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
0x1800027cc  mov     r10, rcx
0x1800027cf  mov     r11, rdx
0x1800027d2  mov     ecx, [r8]
0x1800027d5  and     ecx, 0FFFFFFF8h
0x1800027d8  test    byte ptr [r8], 4
0x1800027dc  jz      short loc_1800027F3
0x1800027de  mov     eax, [r8+8]
0x1800027e2  movsxd  r9, dword ptr [r8+4]
0x1800027e6  neg     eax
0x1800027e8  movsxd  rdx, eax
0x1800027eb  add     r9, r10
0x1800027ee  and     r9, rdx
0x1800027f1  jmp     short loc_1800027F6
0x1800027f3  mov     r9, r10
0x1800027f6  movsxd  rax, ecx
0x1800027f9  mov     rdx, [rax+r9]
0x1800027fd  mov     rax, [r11+10h]
0x180002801  mov     ecx, [rax+8]
0x180002804  mov     rax, [r11+8]
0x180002808  test    byte ptr [rcx+rax+3], 0Fh
0x18000280d  jz      short loc_180002821
0x18000280f  movzx   eax, byte ptr [rcx+rax+3]
0x180002814  mov     ecx, 0FFFFFFF0h
0x180002819  and     rax, rcx
0x18000281c  add     rax, r10
0x18000281f  jmp     short loc_180002824
0x180002821  mov     rax, r10
0x180002824  xor     rdx, rax
0x180002827  mov     rcx, rdx; StackCookie
0x18000282a  jmp     __security_check_cookie
```
