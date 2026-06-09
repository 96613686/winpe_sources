# __GSHandlerCheckCommon

- ea: `0x180003390`
- end: `0x1800033f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000336c`
- `0x180015e9c`

## callees

- `0x180002020`
- `0x180003390`

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
0x180003390  mov     r10, rcx
0x180003393  mov     r11, rdx
0x180003396  mov     ecx, [r8]
0x180003399  and     ecx, 0FFFFFFF8h
0x18000339c  test    byte ptr [r8], 4
0x1800033a0  jz      short loc_1800033B7
0x1800033a2  mov     eax, [r8+8]
0x1800033a6  movsxd  r9, dword ptr [r8+4]
0x1800033aa  neg     eax
0x1800033ac  movsxd  rdx, eax
0x1800033af  add     r9, r10
0x1800033b2  and     r9, rdx
0x1800033b5  jmp     short loc_1800033BA
0x1800033b7  mov     r9, r10
0x1800033ba  movsxd  rax, ecx
0x1800033bd  mov     rdx, [rax+r9]
0x1800033c1  mov     rax, [r11+10h]
0x1800033c5  mov     ecx, [rax+8]
0x1800033c8  mov     rax, [r11+8]
0x1800033cc  test    byte ptr [rcx+rax+3], 0Fh
0x1800033d1  jz      short loc_1800033E5
0x1800033d3  movzx   eax, byte ptr [rcx+rax+3]
0x1800033d8  mov     ecx, 0FFFFFFF0h
0x1800033dd  and     rax, rcx
0x1800033e0  add     rax, r10
0x1800033e3  jmp     short loc_1800033E8
0x1800033e5  mov     rax, r10
0x1800033e8  xor     rdx, rax
0x1800033eb  mov     rcx, rdx; StackCookie
0x1800033ee  jmp     __security_check_cookie
```
