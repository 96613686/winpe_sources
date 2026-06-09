# __GSHandlerCheckCommon

- ea: `0x180004084`
- end: `0x1800040e7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004060`

## callees

- `0x180004084`
- `0x180004130`

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
0x180004084  mov     r10, rcx
0x180004087  mov     r11, rdx
0x18000408a  mov     ecx, [r8]
0x18000408d  and     ecx, 0FFFFFFF8h
0x180004090  test    byte ptr [r8], 4
0x180004094  jz      short loc_1800040AB
0x180004096  mov     eax, [r8+8]
0x18000409a  movsxd  r9, dword ptr [r8+4]
0x18000409e  neg     eax
0x1800040a0  movsxd  rdx, eax
0x1800040a3  add     r9, r10
0x1800040a6  and     r9, rdx
0x1800040a9  jmp     short loc_1800040AE
0x1800040ab  mov     r9, r10
0x1800040ae  movsxd  rax, ecx
0x1800040b1  mov     rdx, [rax+r9]
0x1800040b5  mov     rax, [r11+10h]
0x1800040b9  mov     ecx, [rax+8]
0x1800040bc  mov     rax, [r11+8]
0x1800040c0  test    byte ptr [rcx+rax+3], 0Fh
0x1800040c5  jz      short loc_1800040D9
0x1800040c7  movzx   eax, byte ptr [rcx+rax+3]
0x1800040cc  mov     ecx, 0FFFFFFF0h
0x1800040d1  and     rax, rcx
0x1800040d4  add     rax, r10
0x1800040d7  jmp     short loc_1800040DC
0x1800040d9  mov     rax, r10
0x1800040dc  xor     rdx, rax
0x1800040df  mov     rcx, rdx; StackCookie
0x1800040e2  jmp     __security_check_cookie
```
