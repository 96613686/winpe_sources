# __GSHandlerCheckCommon

- ea: `0x18000301c`
- end: `0x18000307f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ff8`

## callees

- `0x180001460`
- `0x18000301c`

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
0x18000301c  mov     r10, rcx
0x18000301f  mov     r11, rdx
0x180003022  mov     ecx, [r8]
0x180003025  and     ecx, 0FFFFFFF8h
0x180003028  test    byte ptr [r8], 4
0x18000302c  jz      short loc_180003043
0x18000302e  mov     eax, [r8+8]
0x180003032  movsxd  r9, dword ptr [r8+4]
0x180003036  neg     eax
0x180003038  movsxd  rdx, eax
0x18000303b  add     r9, r10
0x18000303e  and     r9, rdx
0x180003041  jmp     short loc_180003046
0x180003043  mov     r9, r10
0x180003046  movsxd  rax, ecx
0x180003049  mov     rdx, [rax+r9]
0x18000304d  mov     rax, [r11+10h]
0x180003051  mov     ecx, [rax+8]
0x180003054  mov     rax, [r11+8]
0x180003058  test    byte ptr [rcx+rax+3], 0Fh
0x18000305d  jz      short loc_180003071
0x18000305f  movzx   eax, byte ptr [rcx+rax+3]
0x180003064  mov     ecx, 0FFFFFFF0h
0x180003069  and     rax, rcx
0x18000306c  add     rax, r10
0x18000306f  jmp     short loc_180003074
0x180003071  mov     rax, r10
0x180003074  xor     rdx, rax
0x180003077  mov     rcx, rdx; StackCookie
0x18000307a  jmp     __security_check_cookie
```
