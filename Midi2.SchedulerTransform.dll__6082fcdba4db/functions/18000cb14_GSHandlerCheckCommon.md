# __GSHandlerCheckCommon

- ea: `0x18000cb14`
- end: `0x18000cb77`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000caf0`
- `0x18000cb80`

## callees

- `0x180002000`
- `0x18000cb14`

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
0x18000cb14  mov     r10, rcx
0x18000cb17  mov     r11, rdx
0x18000cb1a  mov     ecx, [r8]
0x18000cb1d  and     ecx, 0FFFFFFF8h
0x18000cb20  test    byte ptr [r8], 4
0x18000cb24  jz      short loc_18000CB3B
0x18000cb26  mov     eax, [r8+8]
0x18000cb2a  movsxd  r9, dword ptr [r8+4]
0x18000cb2e  neg     eax
0x18000cb30  movsxd  rdx, eax
0x18000cb33  add     r9, r10
0x18000cb36  and     r9, rdx
0x18000cb39  jmp     short loc_18000CB3E
0x18000cb3b  mov     r9, r10
0x18000cb3e  movsxd  rax, ecx
0x18000cb41  mov     rdx, [rax+r9]
0x18000cb45  mov     rax, [r11+10h]
0x18000cb49  mov     ecx, [rax+8]
0x18000cb4c  mov     rax, [r11+8]
0x18000cb50  test    byte ptr [rcx+rax+3], 0Fh
0x18000cb55  jz      short loc_18000CB69
0x18000cb57  movzx   eax, byte ptr [rcx+rax+3]
0x18000cb5c  mov     ecx, 0FFFFFFF0h
0x18000cb61  and     rax, rcx
0x18000cb64  add     rax, r10
0x18000cb67  jmp     short loc_18000CB6C
0x18000cb69  mov     rax, r10
0x18000cb6c  xor     rdx, rax
0x18000cb6f  mov     rcx, rdx; StackCookie
0x18000cb72  jmp     __security_check_cookie
```
