# __GSHandlerCheckCommon

- ea: `0x18000286c`
- end: `0x1800028cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002848`
- `0x18000a8cc`
- `0x18000a934`

## callees

- `0x18000286c`
- `0x18000a9d0`

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
0x18000286c  mov     r10, rcx
0x18000286f  mov     r11, rdx
0x180002872  mov     ecx, [r8]
0x180002875  and     ecx, 0FFFFFFF8h
0x180002878  test    byte ptr [r8], 4
0x18000287c  jz      short loc_180002893
0x18000287e  mov     eax, [r8+8]
0x180002882  movsxd  r9, dword ptr [r8+4]
0x180002886  neg     eax
0x180002888  movsxd  rdx, eax
0x18000288b  add     r9, r10
0x18000288e  and     r9, rdx
0x180002891  jmp     short loc_180002896
0x180002893  mov     r9, r10
0x180002896  movsxd  rax, ecx
0x180002899  mov     rdx, [rax+r9]
0x18000289d  mov     rax, [r11+10h]
0x1800028a1  mov     ecx, [rax+8]
0x1800028a4  mov     rax, [r11+8]
0x1800028a8  test    byte ptr [rcx+rax+3], 0Fh
0x1800028ad  jz      short loc_1800028C1
0x1800028af  movzx   eax, byte ptr [rcx+rax+3]
0x1800028b4  mov     ecx, 0FFFFFFF0h
0x1800028b9  and     rax, rcx
0x1800028bc  add     rax, r10
0x1800028bf  jmp     short loc_1800028C4
0x1800028c1  mov     rax, r10
0x1800028c4  xor     rdx, rax
0x1800028c7  mov     rcx, rdx; StackCookie
0x1800028ca  jmp     __security_check_cookie
```
