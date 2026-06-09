# __GSHandlerCheckCommon

- ea: `0x180001cfc`
- end: `0x180001d5f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cd8`

## callees

- `0x180001cfc`
- `0x18000a190`

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
0x180001cfc  mov     r10, rcx
0x180001cff  mov     r11, rdx
0x180001d02  mov     ecx, [r8]
0x180001d05  and     ecx, 0FFFFFFF8h
0x180001d08  test    byte ptr [r8], 4
0x180001d0c  jz      short loc_180001D23
0x180001d0e  mov     eax, [r8+8]
0x180001d12  movsxd  r9, dword ptr [r8+4]
0x180001d16  neg     eax
0x180001d18  movsxd  rdx, eax
0x180001d1b  add     r9, r10
0x180001d1e  and     r9, rdx
0x180001d21  jmp     short loc_180001D26
0x180001d23  mov     r9, r10
0x180001d26  movsxd  rax, ecx
0x180001d29  mov     rdx, [rax+r9]
0x180001d2d  mov     rax, [r11+10h]
0x180001d31  mov     ecx, [rax+8]
0x180001d34  mov     rax, [r11+8]
0x180001d38  test    byte ptr [rcx+rax+3], 0Fh
0x180001d3d  jz      short loc_180001D51
0x180001d3f  movzx   eax, byte ptr [rcx+rax+3]
0x180001d44  mov     ecx, 0FFFFFFF0h
0x180001d49  and     rax, rcx
0x180001d4c  add     rax, r10
0x180001d4f  jmp     short loc_180001D54
0x180001d51  mov     rax, r10
0x180001d54  xor     rdx, rax
0x180001d57  mov     rcx, rdx; StackCookie
0x180001d5a  jmp     __security_check_cookie
```
