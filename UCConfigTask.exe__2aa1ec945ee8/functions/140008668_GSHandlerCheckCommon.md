# __GSHandlerCheckCommon

- ea: `0x140008668`
- end: `0x1400086cb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008644`
- `0x1400086d4`

## callees

- `0x1400014c0`
- `0x140008668`

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
0x140008668  mov     r10, rcx
0x14000866b  mov     r11, rdx
0x14000866e  mov     ecx, [r8]
0x140008671  and     ecx, 0FFFFFFF8h
0x140008674  test    byte ptr [r8], 4
0x140008678  jz      short loc_14000868F
0x14000867a  mov     eax, [r8+8]
0x14000867e  movsxd  r9, dword ptr [r8+4]
0x140008682  neg     eax
0x140008684  movsxd  rdx, eax
0x140008687  add     r9, r10
0x14000868a  and     r9, rdx
0x14000868d  jmp     short loc_140008692
0x14000868f  mov     r9, r10
0x140008692  movsxd  rax, ecx
0x140008695  mov     rdx, [rax+r9]
0x140008699  mov     rax, [r11+10h]
0x14000869d  mov     ecx, [rax+8]
0x1400086a0  mov     rax, [r11+8]
0x1400086a4  test    byte ptr [rcx+rax+3], 0Fh
0x1400086a9  jz      short loc_1400086BD
0x1400086ab  movzx   eax, byte ptr [rcx+rax+3]
0x1400086b0  mov     ecx, 0FFFFFFF0h
0x1400086b5  and     rax, rcx
0x1400086b8  add     rax, r10
0x1400086bb  jmp     short loc_1400086C0
0x1400086bd  mov     rax, r10
0x1400086c0  xor     rdx, rax
0x1400086c3  mov     rcx, rdx; StackCookie
0x1400086c6  jmp     __security_check_cookie
```
