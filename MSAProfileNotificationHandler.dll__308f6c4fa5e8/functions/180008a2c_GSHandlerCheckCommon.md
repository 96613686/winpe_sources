# __GSHandlerCheckCommon

- ea: `0x180008a2c`
- end: `0x180008a8f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008a08`
- `0x180008a98`
- `0x180008b00`

## callees

- `0x180001cb0`
- `0x180008a2c`

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
0x180008a2c  mov     r10, rcx
0x180008a2f  mov     r11, rdx
0x180008a32  mov     ecx, [r8]
0x180008a35  and     ecx, 0FFFFFFF8h
0x180008a38  test    byte ptr [r8], 4
0x180008a3c  jz      short loc_180008A53
0x180008a3e  mov     eax, [r8+8]
0x180008a42  movsxd  r9, dword ptr [r8+4]
0x180008a46  neg     eax
0x180008a48  movsxd  rdx, eax
0x180008a4b  add     r9, r10
0x180008a4e  and     r9, rdx
0x180008a51  jmp     short loc_180008A56
0x180008a53  mov     r9, r10
0x180008a56  movsxd  rax, ecx
0x180008a59  mov     rdx, [rax+r9]
0x180008a5d  mov     rax, [r11+10h]
0x180008a61  mov     ecx, [rax+8]
0x180008a64  mov     rax, [r11+8]
0x180008a68  test    byte ptr [rcx+rax+3], 0Fh
0x180008a6d  jz      short loc_180008A81
0x180008a6f  movzx   eax, byte ptr [rcx+rax+3]
0x180008a74  mov     ecx, 0FFFFFFF0h
0x180008a79  and     rax, rcx
0x180008a7c  add     rax, r10
0x180008a7f  jmp     short loc_180008A84
0x180008a81  mov     rax, r10
0x180008a84  xor     rdx, rax
0x180008a87  mov     rcx, rdx; StackCookie
0x180008a8a  jmp     __security_check_cookie
```
