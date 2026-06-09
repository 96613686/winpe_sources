# __GSHandlerCheckCommon

- ea: `0x18001d288`
- end: `0x18001d2eb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d264`

## callees

- `0x180001d40`
- `0x18001d288`

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
0x18001d288  mov     r10, rcx
0x18001d28b  mov     r11, rdx
0x18001d28e  mov     ecx, [r8]
0x18001d291  and     ecx, 0FFFFFFF8h
0x18001d294  test    byte ptr [r8], 4
0x18001d298  jz      short loc_18001D2AF
0x18001d29a  mov     eax, [r8+8]
0x18001d29e  movsxd  r9, dword ptr [r8+4]
0x18001d2a2  neg     eax
0x18001d2a4  movsxd  rdx, eax
0x18001d2a7  add     r9, r10
0x18001d2aa  and     r9, rdx
0x18001d2ad  jmp     short loc_18001D2B2
0x18001d2af  mov     r9, r10
0x18001d2b2  movsxd  rax, ecx
0x18001d2b5  mov     rdx, [rax+r9]
0x18001d2b9  mov     rax, [r11+10h]
0x18001d2bd  mov     ecx, [rax+8]
0x18001d2c0  mov     rax, [r11+8]
0x18001d2c4  test    byte ptr [rcx+rax+3], 0Fh
0x18001d2c9  jz      short loc_18001D2DD
0x18001d2cb  movzx   eax, byte ptr [rcx+rax+3]
0x18001d2d0  mov     ecx, 0FFFFFFF0h
0x18001d2d5  and     rax, rcx
0x18001d2d8  add     rax, r10
0x18001d2db  jmp     short loc_18001D2E0
0x18001d2dd  mov     rax, r10
0x18001d2e0  xor     rdx, rax
0x18001d2e3  mov     rcx, rdx; StackCookie
0x18001d2e6  jmp     __security_check_cookie
```
