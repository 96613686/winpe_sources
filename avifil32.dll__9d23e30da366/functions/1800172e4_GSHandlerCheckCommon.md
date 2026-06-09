# __GSHandlerCheckCommon

- ea: `0x1800172e4`
- end: `0x180017347`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800172c0`

## callees

- `0x180001460`
- `0x1800172e4`

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
0x1800172e4  mov     r10, rcx
0x1800172e7  mov     r11, rdx
0x1800172ea  mov     ecx, [r8]
0x1800172ed  and     ecx, 0FFFFFFF8h
0x1800172f0  test    byte ptr [r8], 4
0x1800172f4  jz      short loc_18001730B
0x1800172f6  mov     eax, [r8+8]
0x1800172fa  movsxd  r9, dword ptr [r8+4]
0x1800172fe  neg     eax
0x180017300  movsxd  rdx, eax
0x180017303  add     r9, r10
0x180017306  and     r9, rdx
0x180017309  jmp     short loc_18001730E
0x18001730b  mov     r9, r10
0x18001730e  movsxd  rax, ecx
0x180017311  mov     rdx, [rax+r9]
0x180017315  mov     rax, [r11+10h]
0x180017319  mov     ecx, [rax+8]
0x18001731c  mov     rax, [r11+8]
0x180017320  test    byte ptr [rcx+rax+3], 0Fh
0x180017325  jz      short loc_180017339
0x180017327  movzx   eax, byte ptr [rcx+rax+3]
0x18001732c  mov     ecx, 0FFFFFFF0h
0x180017331  and     rax, rcx
0x180017334  add     rax, r10
0x180017337  jmp     short loc_18001733C
0x180017339  mov     rax, r10
0x18001733c  xor     rdx, rax
0x18001733f  mov     rcx, rdx; StackCookie
0x180017342  jmp     __security_check_cookie
```
