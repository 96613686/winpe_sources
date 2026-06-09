# __GSHandlerCheckCommon

- ea: `0x14000329c`
- end: `0x1400032ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003278`
- `0x1400183ec`

## callees

- `0x140002f40`
- `0x14000329c`

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
0x14000329c  mov     r10, rcx
0x14000329f  mov     r11, rdx
0x1400032a2  mov     ecx, [r8]
0x1400032a5  and     ecx, 0FFFFFFF8h
0x1400032a8  test    byte ptr [r8], 4
0x1400032ac  jz      short loc_1400032C3
0x1400032ae  mov     eax, [r8+8]
0x1400032b2  movsxd  r9, dword ptr [r8+4]
0x1400032b6  neg     eax
0x1400032b8  movsxd  rdx, eax
0x1400032bb  add     r9, r10
0x1400032be  and     r9, rdx
0x1400032c1  jmp     short loc_1400032C6
0x1400032c3  mov     r9, r10
0x1400032c6  movsxd  rax, ecx
0x1400032c9  mov     rdx, [rax+r9]
0x1400032cd  mov     rax, [r11+10h]
0x1400032d1  mov     ecx, [rax+8]
0x1400032d4  mov     rax, [r11+8]
0x1400032d8  test    byte ptr [rcx+rax+3], 0Fh
0x1400032dd  jz      short loc_1400032F1
0x1400032df  movzx   eax, byte ptr [rcx+rax+3]
0x1400032e4  mov     ecx, 0FFFFFFF0h
0x1400032e9  and     rax, rcx
0x1400032ec  add     rax, r10
0x1400032ef  jmp     short loc_1400032F4
0x1400032f1  mov     rax, r10
0x1400032f4  xor     rdx, rax
0x1400032f7  mov     rcx, rdx; StackCookie
0x1400032fa  jmp     __security_check_cookie
```
