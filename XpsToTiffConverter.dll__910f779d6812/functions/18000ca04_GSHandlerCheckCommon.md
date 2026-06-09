# __GSHandlerCheckCommon

- ea: `0x18000ca04`
- end: `0x18000ca67`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9e0`
- `0x18000ca70`

## callees

- `0x1800016a0`
- `0x18000ca04`

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
0x18000ca04  mov     r10, rcx
0x18000ca07  mov     r11, rdx
0x18000ca0a  mov     ecx, [r8]
0x18000ca0d  and     ecx, 0FFFFFFF8h
0x18000ca10  test    byte ptr [r8], 4
0x18000ca14  jz      short loc_18000CA2B
0x18000ca16  mov     eax, [r8+8]
0x18000ca1a  movsxd  r9, dword ptr [r8+4]
0x18000ca1e  neg     eax
0x18000ca20  movsxd  rdx, eax
0x18000ca23  add     r9, r10
0x18000ca26  and     r9, rdx
0x18000ca29  jmp     short loc_18000CA2E
0x18000ca2b  mov     r9, r10
0x18000ca2e  movsxd  rax, ecx
0x18000ca31  mov     rdx, [rax+r9]
0x18000ca35  mov     rax, [r11+10h]
0x18000ca39  mov     ecx, [rax+8]
0x18000ca3c  mov     rax, [r11+8]
0x18000ca40  test    byte ptr [rcx+rax+3], 0Fh
0x18000ca45  jz      short loc_18000CA59
0x18000ca47  movzx   eax, byte ptr [rcx+rax+3]
0x18000ca4c  mov     ecx, 0FFFFFFF0h
0x18000ca51  and     rax, rcx
0x18000ca54  add     rax, r10
0x18000ca57  jmp     short loc_18000CA5C
0x18000ca59  mov     rax, r10
0x18000ca5c  xor     rdx, rax
0x18000ca5f  mov     rcx, rdx; StackCookie
0x18000ca62  jmp     __security_check_cookie
```
