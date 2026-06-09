# __GSHandlerCheckCommon

- ea: `0x18001349c`
- end: `0x1800134ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013478`
- `0x180013508`

## callees

- `0x18001349c`
- `0x1800135c0`

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
0x18001349c  mov     r10, rcx
0x18001349f  mov     r11, rdx
0x1800134a2  mov     ecx, [r8]
0x1800134a5  and     ecx, 0FFFFFFF8h
0x1800134a8  test    byte ptr [r8], 4
0x1800134ac  jz      short loc_1800134C3
0x1800134ae  mov     eax, [r8+8]
0x1800134b2  movsxd  r9, dword ptr [r8+4]
0x1800134b6  neg     eax
0x1800134b8  movsxd  rdx, eax
0x1800134bb  add     r9, r10
0x1800134be  and     r9, rdx
0x1800134c1  jmp     short loc_1800134C6
0x1800134c3  mov     r9, r10
0x1800134c6  movsxd  rax, ecx
0x1800134c9  mov     rdx, [rax+r9]
0x1800134cd  mov     rax, [r11+10h]
0x1800134d1  mov     ecx, [rax+8]
0x1800134d4  mov     rax, [r11+8]
0x1800134d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800134dd  jz      short loc_1800134F1
0x1800134df  movzx   eax, byte ptr [rcx+rax+3]
0x1800134e4  mov     ecx, 0FFFFFFF0h
0x1800134e9  and     rax, rcx
0x1800134ec  add     rax, r10
0x1800134ef  jmp     short loc_1800134F4
0x1800134f1  mov     rax, r10
0x1800134f4  xor     rdx, rax
0x1800134f7  mov     rcx, rdx; StackCookie
0x1800134fa  jmp     __security_check_cookie
```
