# __GSHandlerCheckCommon

- ea: `0x14001ed18`
- end: `0x14001ed7b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ecf4`

## callees

- `0x14001ed18`
- `0x14001edc0`

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
0x14001ed18  mov     r10, rcx
0x14001ed1b  mov     r11, rdx
0x14001ed1e  mov     ecx, [r8]
0x14001ed21  and     ecx, 0FFFFFFF8h
0x14001ed24  test    byte ptr [r8], 4
0x14001ed28  jz      short loc_14001ED3F
0x14001ed2a  mov     eax, [r8+8]
0x14001ed2e  movsxd  r9, dword ptr [r8+4]
0x14001ed32  neg     eax
0x14001ed34  movsxd  rdx, eax
0x14001ed37  add     r9, r10
0x14001ed3a  and     r9, rdx
0x14001ed3d  jmp     short loc_14001ED42
0x14001ed3f  mov     r9, r10
0x14001ed42  movsxd  rax, ecx
0x14001ed45  mov     rdx, [rax+r9]
0x14001ed49  mov     rax, [r11+10h]
0x14001ed4d  mov     ecx, [rax+8]
0x14001ed50  mov     rax, [r11+8]
0x14001ed54  test    byte ptr [rcx+rax+3], 0Fh
0x14001ed59  jz      short loc_14001ED6D
0x14001ed5b  movzx   eax, byte ptr [rcx+rax+3]
0x14001ed60  mov     ecx, 0FFFFFFF0h
0x14001ed65  and     rax, rcx
0x14001ed68  add     rax, r10
0x14001ed6b  jmp     short loc_14001ED70
0x14001ed6d  mov     rax, r10
0x14001ed70  xor     rdx, rax
0x14001ed73  mov     rcx, rdx; StackCookie
0x14001ed76  jmp     __security_check_cookie
```
