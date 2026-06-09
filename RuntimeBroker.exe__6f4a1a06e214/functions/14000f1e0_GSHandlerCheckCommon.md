# __GSHandlerCheckCommon

- ea: `0x14000f1e0`
- end: `0x14000f243`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f1bc`

## callees

- `0x140008c80`
- `0x14000f1e0`

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
0x14000f1e0  mov     r10, rcx
0x14000f1e3  mov     r11, rdx
0x14000f1e6  mov     ecx, [r8]
0x14000f1e9  and     ecx, 0FFFFFFF8h
0x14000f1ec  test    byte ptr [r8], 4
0x14000f1f0  jz      short loc_14000F207
0x14000f1f2  mov     eax, [r8+8]
0x14000f1f6  movsxd  r9, dword ptr [r8+4]
0x14000f1fa  neg     eax
0x14000f1fc  movsxd  rdx, eax
0x14000f1ff  add     r9, r10
0x14000f202  and     r9, rdx
0x14000f205  jmp     short loc_14000F20A
0x14000f207  mov     r9, r10
0x14000f20a  movsxd  rax, ecx
0x14000f20d  mov     rdx, [rax+r9]
0x14000f211  mov     rax, [r11+10h]
0x14000f215  mov     ecx, [rax+8]
0x14000f218  mov     rax, [r11+8]
0x14000f21c  test    byte ptr [rcx+rax+3], 0Fh
0x14000f221  jz      short loc_14000F235
0x14000f223  movzx   eax, byte ptr [rcx+rax+3]
0x14000f228  mov     ecx, 0FFFFFFF0h
0x14000f22d  and     rax, rcx
0x14000f230  add     rax, r10
0x14000f233  jmp     short loc_14000F238
0x14000f235  mov     rax, r10
0x14000f238  xor     rdx, rax
0x14000f23b  mov     rcx, rdx; StackCookie
0x14000f23e  jmp     __security_check_cookie
```
