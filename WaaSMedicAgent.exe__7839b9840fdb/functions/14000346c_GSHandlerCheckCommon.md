# __GSHandlerCheckCommon

- ea: `0x14000346c`
- end: `0x1400034cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003448`
- `0x140011f44`

## callees

- `0x140002a30`
- `0x14000346c`

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
0x14000346c  mov     r10, rcx
0x14000346f  mov     r11, rdx
0x140003472  mov     ecx, [r8]
0x140003475  and     ecx, 0FFFFFFF8h
0x140003478  test    byte ptr [r8], 4
0x14000347c  jz      short loc_140003493
0x14000347e  mov     eax, [r8+8]
0x140003482  movsxd  r9, dword ptr [r8+4]
0x140003486  neg     eax
0x140003488  movsxd  rdx, eax
0x14000348b  add     r9, r10
0x14000348e  and     r9, rdx
0x140003491  jmp     short loc_140003496
0x140003493  mov     r9, r10
0x140003496  movsxd  rax, ecx
0x140003499  mov     rdx, [rax+r9]
0x14000349d  mov     rax, [r11+10h]
0x1400034a1  mov     ecx, [rax+8]
0x1400034a4  mov     rax, [r11+8]
0x1400034a8  test    byte ptr [rcx+rax+3], 0Fh
0x1400034ad  jz      short loc_1400034C1
0x1400034af  movzx   eax, byte ptr [rcx+rax+3]
0x1400034b4  mov     ecx, 0FFFFFFF0h
0x1400034b9  and     rax, rcx
0x1400034bc  add     rax, r10
0x1400034bf  jmp     short loc_1400034C4
0x1400034c1  mov     rax, r10
0x1400034c4  xor     rdx, rax
0x1400034c7  mov     rcx, rdx; StackCookie
0x1400034ca  jmp     __security_check_cookie
```
