# __GSHandlerCheckCommon

- ea: `0x1800027a0`
- end: `0x180002803`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000277c`
- `0x180010210`

## callees

- `0x180002300`
- `0x1800027a0`

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
0x1800027a0  mov     r10, rcx
0x1800027a3  mov     r11, rdx
0x1800027a6  mov     ecx, [r8]
0x1800027a9  and     ecx, 0FFFFFFF8h
0x1800027ac  test    byte ptr [r8], 4
0x1800027b0  jz      short loc_1800027C7
0x1800027b2  mov     eax, [r8+8]
0x1800027b6  movsxd  r9, dword ptr [r8+4]
0x1800027ba  neg     eax
0x1800027bc  movsxd  rdx, eax
0x1800027bf  add     r9, r10
0x1800027c2  and     r9, rdx
0x1800027c5  jmp     short loc_1800027CA
0x1800027c7  mov     r9, r10
0x1800027ca  movsxd  rax, ecx
0x1800027cd  mov     rdx, [rax+r9]
0x1800027d1  mov     rax, [r11+10h]
0x1800027d5  mov     ecx, [rax+8]
0x1800027d8  mov     rax, [r11+8]
0x1800027dc  test    byte ptr [rcx+rax+3], 0Fh
0x1800027e1  jz      short loc_1800027F5
0x1800027e3  movzx   eax, byte ptr [rcx+rax+3]
0x1800027e8  mov     ecx, 0FFFFFFF0h
0x1800027ed  and     rax, rcx
0x1800027f0  add     rax, r10
0x1800027f3  jmp     short loc_1800027F8
0x1800027f5  mov     rax, r10
0x1800027f8  xor     rdx, rax
0x1800027fb  mov     rcx, rdx; StackCookie
0x1800027fe  jmp     __security_check_cookie
```
