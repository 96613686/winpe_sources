# __GSHandlerCheckCommon

- ea: `0x180019c68`
- end: `0x180019ccb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019c44`
- `0x180019cd4`

## callees

- `0x180012dd0`
- `0x180019c68`

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
0x180019c68  mov     r10, rcx
0x180019c6b  mov     r11, rdx
0x180019c6e  mov     ecx, [r8]
0x180019c71  and     ecx, 0FFFFFFF8h
0x180019c74  test    byte ptr [r8], 4
0x180019c78  jz      short loc_180019C8F
0x180019c7a  mov     eax, [r8+8]
0x180019c7e  movsxd  r9, dword ptr [r8+4]
0x180019c82  neg     eax
0x180019c84  movsxd  rdx, eax
0x180019c87  add     r9, r10
0x180019c8a  and     r9, rdx
0x180019c8d  jmp     short loc_180019C92
0x180019c8f  mov     r9, r10
0x180019c92  movsxd  rax, ecx
0x180019c95  mov     rdx, [rax+r9]
0x180019c99  mov     rax, [r11+10h]
0x180019c9d  mov     ecx, [rax+8]
0x180019ca0  mov     rax, [r11+8]
0x180019ca4  test    byte ptr [rcx+rax+3], 0Fh
0x180019ca9  jz      short loc_180019CBD
0x180019cab  movzx   eax, byte ptr [rcx+rax+3]
0x180019cb0  mov     ecx, 0FFFFFFF0h
0x180019cb5  and     rax, rcx
0x180019cb8  add     rax, r10
0x180019cbb  jmp     short loc_180019CC0
0x180019cbd  mov     rax, r10
0x180019cc0  xor     rdx, rax
0x180019cc3  mov     rcx, rdx; StackCookie
0x180019cc6  jmp     __security_check_cookie
```
