# __GSHandlerCheckCommon

- ea: `0x180011334`
- end: `0x180011397`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011310`
- `0x1800113a0`

## callees

- `0x180011334`
- `0x180011460`

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
0x180011334  mov     r10, rcx
0x180011337  mov     r11, rdx
0x18001133a  mov     ecx, [r8]
0x18001133d  and     ecx, 0FFFFFFF8h
0x180011340  test    byte ptr [r8], 4
0x180011344  jz      short loc_18001135B
0x180011346  mov     eax, [r8+8]
0x18001134a  movsxd  r9, dword ptr [r8+4]
0x18001134e  neg     eax
0x180011350  movsxd  rdx, eax
0x180011353  add     r9, r10
0x180011356  and     r9, rdx
0x180011359  jmp     short loc_18001135E
0x18001135b  mov     r9, r10
0x18001135e  movsxd  rax, ecx
0x180011361  mov     rdx, [rax+r9]
0x180011365  mov     rax, [r11+10h]
0x180011369  mov     ecx, [rax+8]
0x18001136c  mov     rax, [r11+8]
0x180011370  test    byte ptr [rcx+rax+3], 0Fh
0x180011375  jz      short loc_180011389
0x180011377  movzx   eax, byte ptr [rcx+rax+3]
0x18001137c  mov     ecx, 0FFFFFFF0h
0x180011381  and     rax, rcx
0x180011384  add     rax, r10
0x180011387  jmp     short loc_18001138C
0x180011389  mov     rax, r10
0x18001138c  xor     rdx, rax
0x18001138f  mov     rcx, rdx; StackCookie
0x180011392  jmp     __security_check_cookie
```
