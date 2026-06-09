# __GSHandlerCheckCommon

- ea: `0x180004080`
- end: `0x1800040e3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000405c`
- `0x18001f7b4`

## callees

- `0x1800038f0`
- `0x180004080`

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
0x180004080  mov     r10, rcx
0x180004083  mov     r11, rdx
0x180004086  mov     ecx, [r8]
0x180004089  and     ecx, 0FFFFFFF8h
0x18000408c  test    byte ptr [r8], 4
0x180004090  jz      short loc_1800040A7
0x180004092  mov     eax, [r8+8]
0x180004096  movsxd  r9, dword ptr [r8+4]
0x18000409a  neg     eax
0x18000409c  movsxd  rdx, eax
0x18000409f  add     r9, r10
0x1800040a2  and     r9, rdx
0x1800040a5  jmp     short loc_1800040AA
0x1800040a7  mov     r9, r10
0x1800040aa  movsxd  rax, ecx
0x1800040ad  mov     rdx, [rax+r9]
0x1800040b1  mov     rax, [r11+10h]
0x1800040b5  mov     ecx, [rax+8]
0x1800040b8  mov     rax, [r11+8]
0x1800040bc  test    byte ptr [rcx+rax+3], 0Fh
0x1800040c1  jz      short loc_1800040D5
0x1800040c3  movzx   eax, byte ptr [rcx+rax+3]
0x1800040c8  mov     ecx, 0FFFFFFF0h
0x1800040cd  and     rax, rcx
0x1800040d0  add     rax, r10
0x1800040d3  jmp     short loc_1800040D8
0x1800040d5  mov     rax, r10
0x1800040d8  xor     rdx, rax
0x1800040db  mov     rcx, rdx; StackCookie
0x1800040de  jmp     __security_check_cookie
```
