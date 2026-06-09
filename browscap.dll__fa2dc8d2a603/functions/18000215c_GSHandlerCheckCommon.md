# __GSHandlerCheckCommon

- ea: `0x18000215c`
- end: `0x1800021bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002138`
- `0x18000b518`
- `0x18000b580`

## callees

- `0x18000215c`
- `0x18000b640`

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
0x18000215c  mov     r10, rcx
0x18000215f  mov     r11, rdx
0x180002162  mov     ecx, [r8]
0x180002165  and     ecx, 0FFFFFFF8h
0x180002168  test    byte ptr [r8], 4
0x18000216c  jz      short loc_180002183
0x18000216e  mov     eax, [r8+8]
0x180002172  movsxd  r9, dword ptr [r8+4]
0x180002176  neg     eax
0x180002178  movsxd  rdx, eax
0x18000217b  add     r9, r10
0x18000217e  and     r9, rdx
0x180002181  jmp     short loc_180002186
0x180002183  mov     r9, r10
0x180002186  movsxd  rax, ecx
0x180002189  mov     rdx, [rax+r9]
0x18000218d  mov     rax, [r11+10h]
0x180002191  mov     ecx, [rax+8]
0x180002194  mov     rax, [r11+8]
0x180002198  test    byte ptr [rcx+rax+3], 0Fh
0x18000219d  jz      short loc_1800021B1
0x18000219f  movzx   eax, byte ptr [rcx+rax+3]
0x1800021a4  mov     ecx, 0FFFFFFF0h
0x1800021a9  and     rax, rcx
0x1800021ac  add     rax, r10
0x1800021af  jmp     short loc_1800021B4
0x1800021b1  mov     rax, r10
0x1800021b4  xor     rdx, rax
0x1800021b7  mov     rcx, rdx; StackCookie
0x1800021ba  jmp     __security_check_cookie
```
