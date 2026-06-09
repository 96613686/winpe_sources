# __GSHandlerCheckCommon

- ea: `0x180005ad0`
- end: `0x180005b33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005aac`

## callees

- `0x180005ad0`
- `0x180005b70`

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
0x180005ad0  mov     r10, rcx
0x180005ad3  mov     r11, rdx
0x180005ad6  mov     ecx, [r8]
0x180005ad9  and     ecx, 0FFFFFFF8h
0x180005adc  test    byte ptr [r8], 4
0x180005ae0  jz      short loc_180005AF7
0x180005ae2  mov     eax, [r8+8]
0x180005ae6  movsxd  r9, dword ptr [r8+4]
0x180005aea  neg     eax
0x180005aec  movsxd  rdx, eax
0x180005aef  add     r9, r10
0x180005af2  and     r9, rdx
0x180005af5  jmp     short loc_180005AFA
0x180005af7  mov     r9, r10
0x180005afa  movsxd  rax, ecx
0x180005afd  mov     rdx, [rax+r9]
0x180005b01  mov     rax, [r11+10h]
0x180005b05  mov     ecx, [rax+8]
0x180005b08  mov     rax, [r11+8]
0x180005b0c  test    byte ptr [rcx+rax+3], 0Fh
0x180005b11  jz      short loc_180005B25
0x180005b13  movzx   eax, byte ptr [rcx+rax+3]
0x180005b18  mov     ecx, 0FFFFFFF0h
0x180005b1d  and     rax, rcx
0x180005b20  add     rax, r10
0x180005b23  jmp     short loc_180005B28
0x180005b25  mov     rax, r10
0x180005b28  xor     rdx, rax
0x180005b2b  mov     rcx, rdx; StackCookie
0x180005b2e  jmp     __security_check_cookie
```
