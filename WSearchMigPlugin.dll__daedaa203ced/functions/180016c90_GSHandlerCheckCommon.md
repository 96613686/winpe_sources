# __GSHandlerCheckCommon

- ea: `0x180016c90`
- end: `0x180016cf3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016c6c`
- `0x180016cfc`

## callees

- `0x1800026f0`
- `0x180016c90`

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
0x180016c90  mov     r10, rcx
0x180016c93  mov     r11, rdx
0x180016c96  mov     ecx, [r8]
0x180016c99  and     ecx, 0FFFFFFF8h
0x180016c9c  test    byte ptr [r8], 4
0x180016ca0  jz      short loc_180016CB7
0x180016ca2  mov     eax, [r8+8]
0x180016ca6  movsxd  r9, dword ptr [r8+4]
0x180016caa  neg     eax
0x180016cac  movsxd  rdx, eax
0x180016caf  add     r9, r10
0x180016cb2  and     r9, rdx
0x180016cb5  jmp     short loc_180016CBA
0x180016cb7  mov     r9, r10
0x180016cba  movsxd  rax, ecx
0x180016cbd  mov     rdx, [rax+r9]
0x180016cc1  mov     rax, [r11+10h]
0x180016cc5  mov     ecx, [rax+8]
0x180016cc8  mov     rax, [r11+8]
0x180016ccc  test    byte ptr [rcx+rax+3], 0Fh
0x180016cd1  jz      short loc_180016CE5
0x180016cd3  movzx   eax, byte ptr [rcx+rax+3]
0x180016cd8  mov     ecx, 0FFFFFFF0h
0x180016cdd  and     rax, rcx
0x180016ce0  add     rax, r10
0x180016ce3  jmp     short loc_180016CE8
0x180016ce5  mov     rax, r10
0x180016ce8  xor     rdx, rax
0x180016ceb  mov     rcx, rdx; StackCookie
0x180016cee  jmp     __security_check_cookie
```
