# __GSHandlerCheckCommon

- ea: `0x180003e60`
- end: `0x180003ec3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e3c`

## callees

- `0x180003e60`
- `0x180003ef0`

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
0x180003e60  mov     r10, rcx
0x180003e63  mov     r11, rdx
0x180003e66  mov     ecx, [r8]
0x180003e69  and     ecx, 0FFFFFFF8h
0x180003e6c  test    byte ptr [r8], 4
0x180003e70  jz      short loc_180003E87
0x180003e72  mov     eax, [r8+8]
0x180003e76  movsxd  r9, dword ptr [r8+4]
0x180003e7a  neg     eax
0x180003e7c  movsxd  rdx, eax
0x180003e7f  add     r9, r10
0x180003e82  and     r9, rdx
0x180003e85  jmp     short loc_180003E8A
0x180003e87  mov     r9, r10
0x180003e8a  movsxd  rax, ecx
0x180003e8d  mov     rdx, [rax+r9]
0x180003e91  mov     rax, [r11+10h]
0x180003e95  mov     ecx, [rax+8]
0x180003e98  mov     rax, [r11+8]
0x180003e9c  test    byte ptr [rcx+rax+3], 0Fh
0x180003ea1  jz      short loc_180003EB5
0x180003ea3  movzx   eax, byte ptr [rcx+rax+3]
0x180003ea8  mov     ecx, 0FFFFFFF0h
0x180003ead  and     rax, rcx
0x180003eb0  add     rax, r10
0x180003eb3  jmp     short loc_180003EB8
0x180003eb5  mov     rax, r10
0x180003eb8  xor     rdx, rax
0x180003ebb  mov     rcx, rdx; StackCookie
0x180003ebe  jmp     __security_check_cookie
```
