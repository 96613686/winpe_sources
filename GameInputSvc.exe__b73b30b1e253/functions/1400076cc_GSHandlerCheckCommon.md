# __GSHandlerCheckCommon

- ea: `0x1400076cc`
- end: `0x14000772f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400076a8`

## callees

- `0x1400076cc`
- `0x140007750`

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
0x1400076cc  mov     r10, rcx
0x1400076cf  mov     r11, rdx
0x1400076d2  mov     ecx, [r8]
0x1400076d5  and     ecx, 0FFFFFFF8h
0x1400076d8  test    byte ptr [r8], 4
0x1400076dc  jz      short loc_1400076F3
0x1400076de  mov     eax, [r8+8]
0x1400076e2  movsxd  r9, dword ptr [r8+4]
0x1400076e6  neg     eax
0x1400076e8  movsxd  rdx, eax
0x1400076eb  add     r9, r10
0x1400076ee  and     r9, rdx
0x1400076f1  jmp     short loc_1400076F6
0x1400076f3  mov     r9, r10
0x1400076f6  movsxd  rax, ecx
0x1400076f9  mov     rdx, [rax+r9]
0x1400076fd  mov     rax, [r11+10h]
0x140007701  mov     ecx, [rax+8]
0x140007704  mov     rax, [r11+8]
0x140007708  test    byte ptr [rcx+rax+3], 0Fh
0x14000770d  jz      short loc_140007721
0x14000770f  movzx   eax, byte ptr [rcx+rax+3]
0x140007714  mov     ecx, 0FFFFFFF0h
0x140007719  and     rax, rcx
0x14000771c  add     rax, r10
0x14000771f  jmp     short loc_140007724
0x140007721  mov     rax, r10
0x140007724  xor     rdx, rax
0x140007727  mov     rcx, rdx; StackCookie
0x14000772a  jmp     __security_check_cookie
```
