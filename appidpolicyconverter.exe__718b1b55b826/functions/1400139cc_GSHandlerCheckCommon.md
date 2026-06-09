# __GSHandlerCheckCommon

- ea: `0x1400139cc`
- end: `0x140013a2f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400139a8`
- `0x140013a38`

## callees

- `0x1400139cc`
- `0x140013b10`

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
0x1400139cc  mov     r10, rcx
0x1400139cf  mov     r11, rdx
0x1400139d2  mov     ecx, [r8]
0x1400139d5  and     ecx, 0FFFFFFF8h
0x1400139d8  test    byte ptr [r8], 4
0x1400139dc  jz      short loc_1400139F3
0x1400139de  mov     eax, [r8+8]
0x1400139e2  movsxd  r9, dword ptr [r8+4]
0x1400139e6  neg     eax
0x1400139e8  movsxd  rdx, eax
0x1400139eb  add     r9, r10
0x1400139ee  and     r9, rdx
0x1400139f1  jmp     short loc_1400139F6
0x1400139f3  mov     r9, r10
0x1400139f6  movsxd  rax, ecx
0x1400139f9  mov     rdx, [rax+r9]
0x1400139fd  mov     rax, [r11+10h]
0x140013a01  mov     ecx, [rax+8]
0x140013a04  mov     rax, [r11+8]
0x140013a08  test    byte ptr [rcx+rax+3], 0Fh
0x140013a0d  jz      short loc_140013A21
0x140013a0f  movzx   eax, byte ptr [rcx+rax+3]
0x140013a14  mov     ecx, 0FFFFFFF0h
0x140013a19  and     rax, rcx
0x140013a1c  add     rax, r10
0x140013a1f  jmp     short loc_140013A24
0x140013a21  mov     rax, r10
0x140013a24  xor     rdx, rax
0x140013a27  mov     rcx, rdx; StackCookie
0x140013a2a  jmp     __security_check_cookie
```
