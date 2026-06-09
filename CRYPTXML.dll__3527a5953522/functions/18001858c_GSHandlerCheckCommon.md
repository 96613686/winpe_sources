# __GSHandlerCheckCommon

- ea: `0x18001858c`
- end: `0x1800185ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018568`

## callees

- `0x18001858c`
- `0x180018640`

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
0x18001858c  mov     r10, rcx
0x18001858f  mov     r11, rdx
0x180018592  mov     ecx, [r8]
0x180018595  and     ecx, 0FFFFFFF8h
0x180018598  test    byte ptr [r8], 4
0x18001859c  jz      short loc_1800185B3
0x18001859e  mov     eax, [r8+8]
0x1800185a2  movsxd  r9, dword ptr [r8+4]
0x1800185a6  neg     eax
0x1800185a8  movsxd  rdx, eax
0x1800185ab  add     r9, r10
0x1800185ae  and     r9, rdx
0x1800185b1  jmp     short loc_1800185B6
0x1800185b3  mov     r9, r10
0x1800185b6  movsxd  rax, ecx
0x1800185b9  mov     rdx, [rax+r9]
0x1800185bd  mov     rax, [r11+10h]
0x1800185c1  mov     ecx, [rax+8]
0x1800185c4  mov     rax, [r11+8]
0x1800185c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800185cd  jz      short loc_1800185E1
0x1800185cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800185d4  mov     ecx, 0FFFFFFF0h
0x1800185d9  and     rax, rcx
0x1800185dc  add     rax, r10
0x1800185df  jmp     short loc_1800185E4
0x1800185e1  mov     rax, r10
0x1800185e4  xor     rdx, rax
0x1800185e7  mov     rcx, rdx; StackCookie
0x1800185ea  jmp     __security_check_cookie
```
