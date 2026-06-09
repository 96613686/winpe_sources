# __GSHandlerCheckCommon

- ea: `0x14001a7a4`
- end: `0x14001a807`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a780`
- `0x14001a810`

## callees

- `0x14001a7a4`
- `0x14001a8d0`

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
0x14001a7a4  mov     r10, rcx
0x14001a7a7  mov     r11, rdx
0x14001a7aa  mov     ecx, [r8]
0x14001a7ad  and     ecx, 0FFFFFFF8h
0x14001a7b0  test    byte ptr [r8], 4
0x14001a7b4  jz      short loc_14001A7CB
0x14001a7b6  mov     eax, [r8+8]
0x14001a7ba  movsxd  r9, dword ptr [r8+4]
0x14001a7be  neg     eax
0x14001a7c0  movsxd  rdx, eax
0x14001a7c3  add     r9, r10
0x14001a7c6  and     r9, rdx
0x14001a7c9  jmp     short loc_14001A7CE
0x14001a7cb  mov     r9, r10
0x14001a7ce  movsxd  rax, ecx
0x14001a7d1  mov     rdx, [rax+r9]
0x14001a7d5  mov     rax, [r11+10h]
0x14001a7d9  mov     ecx, [rax+8]
0x14001a7dc  mov     rax, [r11+8]
0x14001a7e0  test    byte ptr [rcx+rax+3], 0Fh
0x14001a7e5  jz      short loc_14001A7F9
0x14001a7e7  movzx   eax, byte ptr [rcx+rax+3]
0x14001a7ec  mov     ecx, 0FFFFFFF0h
0x14001a7f1  and     rax, rcx
0x14001a7f4  add     rax, r10
0x14001a7f7  jmp     short loc_14001A7FC
0x14001a7f9  mov     rax, r10
0x14001a7fc  xor     rdx, rax
0x14001a7ff  mov     rcx, rdx; StackCookie
0x14001a802  jmp     __security_check_cookie
```
