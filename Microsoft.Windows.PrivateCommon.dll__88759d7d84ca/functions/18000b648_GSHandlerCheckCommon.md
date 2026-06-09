# __GSHandlerCheckCommon

- ea: `0x18000b648`
- end: `0x18000b6a8`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b628`
- `0x18000b77c`
- `0x18000b838`

## callees

- `0x180007280`
- `0x18000b648`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x18000b648  push    rbx
0x18000b64a  mov     r11d, [r8]
0x18000b64d  mov     rbx, rdx
0x18000b650  and     r11d, 0FFFFFFF8h
0x18000b654  mov     r9, rcx
0x18000b657  test    byte ptr [r8], 4
0x18000b65b  mov     r10, rcx
0x18000b65e  jz      short loc_18000B673
0x18000b660  mov     eax, [r8+8]
0x18000b664  movsxd  r10, dword ptr [r8+4]
0x18000b668  neg     eax
0x18000b66a  add     r10, rcx
0x18000b66d  movsxd  rcx, eax
0x18000b670  and     r10, rcx
0x18000b673  movsxd  rax, r11d
0x18000b676  mov     rdx, [rax+r10]
0x18000b67a  mov     rax, [rbx+10h]
0x18000b67e  mov     ecx, [rax+8]
0x18000b681  mov     rax, [rbx+8]
0x18000b685  test    byte ptr [rcx+rax+3], 0Fh
0x18000b68a  jz      short loc_18000B69C
0x18000b68c  movzx   eax, byte ptr [rcx+rax+3]
0x18000b691  mov     ecx, 0FFFFFFF0h
0x18000b696  and     rax, rcx
0x18000b699  add     r9, rax
0x18000b69c  xor     r9, rdx
0x18000b69f  mov     rcx, r9; StackCookie
0x18000b6a2  pop     rbx
0x18000b6a3  jmp     __security_check_cookie
```
