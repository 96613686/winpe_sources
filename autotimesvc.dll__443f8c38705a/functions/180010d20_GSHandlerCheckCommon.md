# __GSHandlerCheckCommon

- ea: `0x180010d20`
- end: `0x180010d83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010cfc`
- `0x180010d8c`

## callees

- `0x180002a70`
- `0x180010d20`

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
0x180010d20  mov     r10, rcx
0x180010d23  mov     r11, rdx
0x180010d26  mov     ecx, [r8]
0x180010d29  and     ecx, 0FFFFFFF8h
0x180010d2c  test    byte ptr [r8], 4
0x180010d30  jz      short loc_180010D47
0x180010d32  mov     eax, [r8+8]
0x180010d36  movsxd  r9, dword ptr [r8+4]
0x180010d3a  neg     eax
0x180010d3c  movsxd  rdx, eax
0x180010d3f  add     r9, r10
0x180010d42  and     r9, rdx
0x180010d45  jmp     short loc_180010D4A
0x180010d47  mov     r9, r10
0x180010d4a  movsxd  rax, ecx
0x180010d4d  mov     rdx, [rax+r9]
0x180010d51  mov     rax, [r11+10h]
0x180010d55  mov     ecx, [rax+8]
0x180010d58  mov     rax, [r11+8]
0x180010d5c  test    byte ptr [rcx+rax+3], 0Fh
0x180010d61  jz      short loc_180010D75
0x180010d63  movzx   eax, byte ptr [rcx+rax+3]
0x180010d68  mov     ecx, 0FFFFFFF0h
0x180010d6d  and     rax, rcx
0x180010d70  add     rax, r10
0x180010d73  jmp     short loc_180010D78
0x180010d75  mov     rax, r10
0x180010d78  xor     rdx, rax
0x180010d7b  mov     rcx, rdx; StackCookie
0x180010d7e  jmp     __security_check_cookie
```
