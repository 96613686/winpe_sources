# __GSHandlerCheckCommon

- ea: `0x18000a4f8`
- end: `0x18000a55b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a4d4`
- `0x18000a564`

## callees

- `0x18000a4f8`
- `0x18000a5f0`

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
0x18000a4f8  mov     r10, rcx
0x18000a4fb  mov     r11, rdx
0x18000a4fe  mov     ecx, [r8]
0x18000a501  and     ecx, 0FFFFFFF8h
0x18000a504  test    byte ptr [r8], 4
0x18000a508  jz      short loc_18000A51F
0x18000a50a  mov     eax, [r8+8]
0x18000a50e  movsxd  r9, dword ptr [r8+4]
0x18000a512  neg     eax
0x18000a514  movsxd  rdx, eax
0x18000a517  add     r9, r10
0x18000a51a  and     r9, rdx
0x18000a51d  jmp     short loc_18000A522
0x18000a51f  mov     r9, r10
0x18000a522  movsxd  rax, ecx
0x18000a525  mov     rdx, [rax+r9]
0x18000a529  mov     rax, [r11+10h]
0x18000a52d  mov     ecx, [rax+8]
0x18000a530  mov     rax, [r11+8]
0x18000a534  test    byte ptr [rcx+rax+3], 0Fh
0x18000a539  jz      short loc_18000A54D
0x18000a53b  movzx   eax, byte ptr [rcx+rax+3]
0x18000a540  mov     ecx, 0FFFFFFF0h
0x18000a545  and     rax, rcx
0x18000a548  add     rax, r10
0x18000a54b  jmp     short loc_18000A550
0x18000a54d  mov     rax, r10
0x18000a550  xor     rdx, rax
0x18000a553  mov     rcx, rdx; StackCookie
0x18000a556  jmp     __security_check_cookie
```
