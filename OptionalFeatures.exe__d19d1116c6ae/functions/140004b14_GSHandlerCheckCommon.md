# __GSHandlerCheckCommon

- ea: `0x140004b14`
- end: `0x140004b77`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004af0`

## callees

- `0x140004b14`
- `0x140004ba0`

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
0x140004b14  mov     r10, rcx
0x140004b17  mov     r11, rdx
0x140004b1a  mov     ecx, [r8]
0x140004b1d  and     ecx, 0FFFFFFF8h
0x140004b20  test    byte ptr [r8], 4
0x140004b24  jz      short loc_140004B3B
0x140004b26  mov     eax, [r8+8]
0x140004b2a  movsxd  r9, dword ptr [r8+4]
0x140004b2e  neg     eax
0x140004b30  movsxd  rdx, eax
0x140004b33  add     r9, r10
0x140004b36  and     r9, rdx
0x140004b39  jmp     short loc_140004B3E
0x140004b3b  mov     r9, r10
0x140004b3e  movsxd  rax, ecx
0x140004b41  mov     rdx, [rax+r9]
0x140004b45  mov     rax, [r11+10h]
0x140004b49  mov     ecx, [rax+8]
0x140004b4c  mov     rax, [r11+8]
0x140004b50  test    byte ptr [rcx+rax+3], 0Fh
0x140004b55  jz      short loc_140004B69
0x140004b57  movzx   eax, byte ptr [rcx+rax+3]
0x140004b5c  mov     ecx, 0FFFFFFF0h
0x140004b61  and     rax, rcx
0x140004b64  add     rax, r10
0x140004b67  jmp     short loc_140004B6C
0x140004b69  mov     rax, r10
0x140004b6c  xor     rdx, rax
0x140004b6f  mov     rcx, rdx; StackCookie
0x140004b72  jmp     __security_check_cookie
```
