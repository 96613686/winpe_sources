# __GSHandlerCheckCommon

- ea: `0x140007698`
- end: `0x1400076fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007674`

## callees

- `0x140001cd0`
- `0x140007698`

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
0x140007698  mov     r10, rcx
0x14000769b  mov     r11, rdx
0x14000769e  mov     ecx, [r8]
0x1400076a1  and     ecx, 0FFFFFFF8h
0x1400076a4  test    byte ptr [r8], 4
0x1400076a8  jz      short loc_1400076BF
0x1400076aa  mov     eax, [r8+8]
0x1400076ae  movsxd  r9, dword ptr [r8+4]
0x1400076b2  neg     eax
0x1400076b4  movsxd  rdx, eax
0x1400076b7  add     r9, r10
0x1400076ba  and     r9, rdx
0x1400076bd  jmp     short loc_1400076C2
0x1400076bf  mov     r9, r10
0x1400076c2  movsxd  rax, ecx
0x1400076c5  mov     rdx, [rax+r9]
0x1400076c9  mov     rax, [r11+10h]
0x1400076cd  mov     ecx, [rax+8]
0x1400076d0  mov     rax, [r11+8]
0x1400076d4  test    byte ptr [rcx+rax+3], 0Fh
0x1400076d9  jz      short loc_1400076ED
0x1400076db  movzx   eax, byte ptr [rcx+rax+3]
0x1400076e0  mov     ecx, 0FFFFFFF0h
0x1400076e5  and     rax, rcx
0x1400076e8  add     rax, r10
0x1400076eb  jmp     short loc_1400076F0
0x1400076ed  mov     rax, r10
0x1400076f0  xor     rdx, rax
0x1400076f3  mov     rcx, rdx; StackCookie
0x1400076f6  jmp     __security_check_cookie
```
