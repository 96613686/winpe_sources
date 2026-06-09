# __GSHandlerCheckCommon

- ea: `0x18000211c`
- end: `0x18000217f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020f8`
- `0x1800093b0`

## callees

- `0x18000211c`
- `0x180009440`

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
0x18000211c  mov     r10, rcx
0x18000211f  mov     r11, rdx
0x180002122  mov     ecx, [r8]
0x180002125  and     ecx, 0FFFFFFF8h
0x180002128  test    byte ptr [r8], 4
0x18000212c  jz      short loc_180002143
0x18000212e  mov     eax, [r8+8]
0x180002132  movsxd  r9, dword ptr [r8+4]
0x180002136  neg     eax
0x180002138  movsxd  rdx, eax
0x18000213b  add     r9, r10
0x18000213e  and     r9, rdx
0x180002141  jmp     short loc_180002146
0x180002143  mov     r9, r10
0x180002146  movsxd  rax, ecx
0x180002149  mov     rdx, [rax+r9]
0x18000214d  mov     rax, [r11+10h]
0x180002151  mov     ecx, [rax+8]
0x180002154  mov     rax, [r11+8]
0x180002158  test    byte ptr [rcx+rax+3], 0Fh
0x18000215d  jz      short loc_180002171
0x18000215f  movzx   eax, byte ptr [rcx+rax+3]
0x180002164  mov     ecx, 0FFFFFFF0h
0x180002169  and     rax, rcx
0x18000216c  add     rax, r10
0x18000216f  jmp     short loc_180002174
0x180002171  mov     rax, r10
0x180002174  xor     rdx, rax
0x180002177  mov     rcx, rdx; StackCookie
0x18000217a  jmp     __security_check_cookie
```
