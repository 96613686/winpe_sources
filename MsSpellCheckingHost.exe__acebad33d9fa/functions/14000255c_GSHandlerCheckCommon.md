# __GSHandlerCheckCommon

- ea: `0x14000255c`
- end: `0x1400025bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002538`
- `0x140011d70`

## callees

- `0x14000255c`
- `0x140011e10`

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
0x14000255c  mov     r10, rcx
0x14000255f  mov     r11, rdx
0x140002562  mov     ecx, [r8]
0x140002565  and     ecx, 0FFFFFFF8h
0x140002568  test    byte ptr [r8], 4
0x14000256c  jz      short loc_140002583
0x14000256e  mov     eax, [r8+8]
0x140002572  movsxd  r9, dword ptr [r8+4]
0x140002576  neg     eax
0x140002578  movsxd  rdx, eax
0x14000257b  add     r9, r10
0x14000257e  and     r9, rdx
0x140002581  jmp     short loc_140002586
0x140002583  mov     r9, r10
0x140002586  movsxd  rax, ecx
0x140002589  mov     rdx, [rax+r9]
0x14000258d  mov     rax, [r11+10h]
0x140002591  mov     ecx, [rax+8]
0x140002594  mov     rax, [r11+8]
0x140002598  test    byte ptr [rcx+rax+3], 0Fh
0x14000259d  jz      short loc_1400025B1
0x14000259f  movzx   eax, byte ptr [rcx+rax+3]
0x1400025a4  mov     ecx, 0FFFFFFF0h
0x1400025a9  and     rax, rcx
0x1400025ac  add     rax, r10
0x1400025af  jmp     short loc_1400025B4
0x1400025b1  mov     rax, r10
0x1400025b4  xor     rdx, rax
0x1400025b7  mov     rcx, rdx; StackCookie
0x1400025ba  jmp     __security_check_cookie
```
