# __GSHandlerCheckCommon

- ea: `0x14000a2cc`
- end: `0x14000a32f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a2a8`
- `0x14000a338`

## callees

- `0x1400031b0`
- `0x14000a2cc`

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
0x14000a2cc  mov     r10, rcx
0x14000a2cf  mov     r11, rdx
0x14000a2d2  mov     ecx, [r8]
0x14000a2d5  and     ecx, 0FFFFFFF8h
0x14000a2d8  test    byte ptr [r8], 4
0x14000a2dc  jz      short loc_14000A2F3
0x14000a2de  mov     eax, [r8+8]
0x14000a2e2  movsxd  r9, dword ptr [r8+4]
0x14000a2e6  neg     eax
0x14000a2e8  movsxd  rdx, eax
0x14000a2eb  add     r9, r10
0x14000a2ee  and     r9, rdx
0x14000a2f1  jmp     short loc_14000A2F6
0x14000a2f3  mov     r9, r10
0x14000a2f6  movsxd  rax, ecx
0x14000a2f9  mov     rdx, [rax+r9]
0x14000a2fd  mov     rax, [r11+10h]
0x14000a301  mov     ecx, [rax+8]
0x14000a304  mov     rax, [r11+8]
0x14000a308  test    byte ptr [rcx+rax+3], 0Fh
0x14000a30d  jz      short loc_14000A321
0x14000a30f  movzx   eax, byte ptr [rcx+rax+3]
0x14000a314  mov     ecx, 0FFFFFFF0h
0x14000a319  and     rax, rcx
0x14000a31c  add     rax, r10
0x14000a31f  jmp     short loc_14000A324
0x14000a321  mov     rax, r10
0x14000a324  xor     rdx, rax
0x14000a327  mov     rcx, rdx; StackCookie
0x14000a32a  jmp     __security_check_cookie
```
