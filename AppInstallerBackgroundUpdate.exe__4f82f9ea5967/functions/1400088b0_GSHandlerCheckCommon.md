# __GSHandlerCheckCommon

- ea: `0x1400088b0`
- end: `0x140008913`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000888c`
- `0x14000891c`

## callees

- `0x140001530`
- `0x1400088b0`

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
0x1400088b0  mov     r10, rcx
0x1400088b3  mov     r11, rdx
0x1400088b6  mov     ecx, [r8]
0x1400088b9  and     ecx, 0FFFFFFF8h
0x1400088bc  test    byte ptr [r8], 4
0x1400088c0  jz      short loc_1400088D7
0x1400088c2  mov     eax, [r8+8]
0x1400088c6  movsxd  r9, dword ptr [r8+4]
0x1400088ca  neg     eax
0x1400088cc  movsxd  rdx, eax
0x1400088cf  add     r9, r10
0x1400088d2  and     r9, rdx
0x1400088d5  jmp     short loc_1400088DA
0x1400088d7  mov     r9, r10
0x1400088da  movsxd  rax, ecx
0x1400088dd  mov     rdx, [rax+r9]
0x1400088e1  mov     rax, [r11+10h]
0x1400088e5  mov     ecx, [rax+8]
0x1400088e8  mov     rax, [r11+8]
0x1400088ec  test    byte ptr [rcx+rax+3], 0Fh
0x1400088f1  jz      short loc_140008905
0x1400088f3  movzx   eax, byte ptr [rcx+rax+3]
0x1400088f8  mov     ecx, 0FFFFFFF0h
0x1400088fd  and     rax, rcx
0x140008900  add     rax, r10
0x140008903  jmp     short loc_140008908
0x140008905  mov     rax, r10
0x140008908  xor     rdx, rax
0x14000890b  mov     rcx, rdx; StackCookie
0x14000890e  jmp     __security_check_cookie
```
