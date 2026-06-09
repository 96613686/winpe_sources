# __GSHandlerCheckCommon

- ea: `0x18002656c`
- end: `0x1800265cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026548`

## callees

- `0x1800018e0`
- `0x18002656c`

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
0x18002656c  mov     r10, rcx
0x18002656f  mov     r11, rdx
0x180026572  mov     ecx, [r8]
0x180026575  and     ecx, 0FFFFFFF8h
0x180026578  test    byte ptr [r8], 4
0x18002657c  jz      short loc_180026593
0x18002657e  mov     eax, [r8+8]
0x180026582  movsxd  r9, dword ptr [r8+4]
0x180026586  neg     eax
0x180026588  movsxd  rdx, eax
0x18002658b  add     r9, r10
0x18002658e  and     r9, rdx
0x180026591  jmp     short loc_180026596
0x180026593  mov     r9, r10
0x180026596  movsxd  rax, ecx
0x180026599  mov     rdx, [rax+r9]
0x18002659d  mov     rax, [r11+10h]
0x1800265a1  mov     ecx, [rax+8]
0x1800265a4  mov     rax, [r11+8]
0x1800265a8  test    byte ptr [rcx+rax+3], 0Fh
0x1800265ad  jz      short loc_1800265C1
0x1800265af  movzx   eax, byte ptr [rcx+rax+3]
0x1800265b4  mov     ecx, 0FFFFFFF0h
0x1800265b9  and     rax, rcx
0x1800265bc  add     rax, r10
0x1800265bf  jmp     short loc_1800265C4
0x1800265c1  mov     rax, r10
0x1800265c4  xor     rdx, rax
0x1800265c7  mov     rcx, rdx; StackCookie
0x1800265ca  jmp     __security_check_cookie
```
