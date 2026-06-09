# __GSHandlerCheckCommon

- ea: `0x1800030a4`
- end: `0x180003107`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003080`
- `0x18001a4cc`

## callees

- `0x180002c00`
- `0x1800030a4`

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
0x1800030a4  mov     r10, rcx
0x1800030a7  mov     r11, rdx
0x1800030aa  mov     ecx, [r8]
0x1800030ad  and     ecx, 0FFFFFFF8h
0x1800030b0  test    byte ptr [r8], 4
0x1800030b4  jz      short loc_1800030CB
0x1800030b6  mov     eax, [r8+8]
0x1800030ba  movsxd  r9, dword ptr [r8+4]
0x1800030be  neg     eax
0x1800030c0  movsxd  rdx, eax
0x1800030c3  add     r9, r10
0x1800030c6  and     r9, rdx
0x1800030c9  jmp     short loc_1800030CE
0x1800030cb  mov     r9, r10
0x1800030ce  movsxd  rax, ecx
0x1800030d1  mov     rdx, [rax+r9]
0x1800030d5  mov     rax, [r11+10h]
0x1800030d9  mov     ecx, [rax+8]
0x1800030dc  mov     rax, [r11+8]
0x1800030e0  test    byte ptr [rcx+rax+3], 0Fh
0x1800030e5  jz      short loc_1800030F9
0x1800030e7  movzx   eax, byte ptr [rcx+rax+3]
0x1800030ec  mov     ecx, 0FFFFFFF0h
0x1800030f1  and     rax, rcx
0x1800030f4  add     rax, r10
0x1800030f7  jmp     short loc_1800030FC
0x1800030f9  mov     rax, r10
0x1800030fc  xor     rdx, rax
0x1800030ff  mov     rcx, rdx; StackCookie
0x180003102  jmp     __security_check_cookie
```
