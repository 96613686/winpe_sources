# __GSHandlerCheckCommon

- ea: `0x140002a10`
- end: `0x140002a73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400029ec`
- `0x140002a7c`
- `0x140012eac`

## callees

- `0x140002a10`
- `0x140012f60`

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
0x140002a10  mov     r10, rcx
0x140002a13  mov     r11, rdx
0x140002a16  mov     ecx, [r8]
0x140002a19  and     ecx, 0FFFFFFF8h
0x140002a1c  test    byte ptr [r8], 4
0x140002a20  jz      short loc_140002A37
0x140002a22  mov     eax, [r8+8]
0x140002a26  movsxd  r9, dword ptr [r8+4]
0x140002a2a  neg     eax
0x140002a2c  movsxd  rdx, eax
0x140002a2f  add     r9, r10
0x140002a32  and     r9, rdx
0x140002a35  jmp     short loc_140002A3A
0x140002a37  mov     r9, r10
0x140002a3a  movsxd  rax, ecx
0x140002a3d  mov     rdx, [rax+r9]
0x140002a41  mov     rax, [r11+10h]
0x140002a45  mov     ecx, [rax+8]
0x140002a48  mov     rax, [r11+8]
0x140002a4c  test    byte ptr [rcx+rax+3], 0Fh
0x140002a51  jz      short loc_140002A65
0x140002a53  movzx   eax, byte ptr [rcx+rax+3]
0x140002a58  mov     ecx, 0FFFFFFF0h
0x140002a5d  and     rax, rcx
0x140002a60  add     rax, r10
0x140002a63  jmp     short loc_140002A68
0x140002a65  mov     rax, r10
0x140002a68  xor     rdx, rax
0x140002a6b  mov     rcx, rdx; StackCookie
0x140002a6e  jmp     __security_check_cookie
```
