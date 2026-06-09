# __GSHandlerCheckCommon

- ea: `0x18001cdc0`
- end: `0x18001ce23`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cd9c`
- `0x18001ce2c`
- `0x18001ce94`

## callees

- `0x180001c60`
- `0x18001cdc0`

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
0x18001cdc0  mov     r10, rcx
0x18001cdc3  mov     r11, rdx
0x18001cdc6  mov     ecx, [r8]
0x18001cdc9  and     ecx, 0FFFFFFF8h
0x18001cdcc  test    byte ptr [r8], 4
0x18001cdd0  jz      short loc_18001CDE7
0x18001cdd2  mov     eax, [r8+8]
0x18001cdd6  movsxd  r9, dword ptr [r8+4]
0x18001cdda  neg     eax
0x18001cddc  movsxd  rdx, eax
0x18001cddf  add     r9, r10
0x18001cde2  and     r9, rdx
0x18001cde5  jmp     short loc_18001CDEA
0x18001cde7  mov     r9, r10
0x18001cdea  movsxd  rax, ecx
0x18001cded  mov     rdx, [rax+r9]
0x18001cdf1  mov     rax, [r11+10h]
0x18001cdf5  mov     ecx, [rax+8]
0x18001cdf8  mov     rax, [r11+8]
0x18001cdfc  test    byte ptr [rcx+rax+3], 0Fh
0x18001ce01  jz      short loc_18001CE15
0x18001ce03  movzx   eax, byte ptr [rcx+rax+3]
0x18001ce08  mov     ecx, 0FFFFFFF0h
0x18001ce0d  and     rax, rcx
0x18001ce10  add     rax, r10
0x18001ce13  jmp     short loc_18001CE18
0x18001ce15  mov     rax, r10
0x18001ce18  xor     rdx, rax
0x18001ce1b  mov     rcx, rdx; StackCookie
0x18001ce1e  jmp     __security_check_cookie
```
