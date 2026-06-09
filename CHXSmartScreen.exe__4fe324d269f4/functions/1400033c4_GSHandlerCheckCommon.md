# __GSHandlerCheckCommon

- ea: `0x1400033c4`
- end: `0x140003427`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400033a0`
- `0x1400318c8`

## callees

- `0x1400033c4`
- `0x140031960`

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
0x1400033c4  mov     r10, rcx
0x1400033c7  mov     r11, rdx
0x1400033ca  mov     ecx, [r8]
0x1400033cd  and     ecx, 0FFFFFFF8h
0x1400033d0  test    byte ptr [r8], 4
0x1400033d4  jz      short loc_1400033EB
0x1400033d6  mov     eax, [r8+8]
0x1400033da  movsxd  r9, dword ptr [r8+4]
0x1400033de  neg     eax
0x1400033e0  movsxd  rdx, eax
0x1400033e3  add     r9, r10
0x1400033e6  and     r9, rdx
0x1400033e9  jmp     short loc_1400033EE
0x1400033eb  mov     r9, r10
0x1400033ee  movsxd  rax, ecx
0x1400033f1  mov     rdx, [rax+r9]
0x1400033f5  mov     rax, [r11+10h]
0x1400033f9  mov     ecx, [rax+8]
0x1400033fc  mov     rax, [r11+8]
0x140003400  test    byte ptr [rcx+rax+3], 0Fh
0x140003405  jz      short loc_140003419
0x140003407  movzx   eax, byte ptr [rcx+rax+3]
0x14000340c  mov     ecx, 0FFFFFFF0h
0x140003411  and     rax, rcx
0x140003414  add     rax, r10
0x140003417  jmp     short loc_14000341C
0x140003419  mov     rax, r10
0x14000341c  xor     rdx, rax
0x14000341f  mov     rcx, rdx; StackCookie
0x140003422  jmp     __security_check_cookie
```
