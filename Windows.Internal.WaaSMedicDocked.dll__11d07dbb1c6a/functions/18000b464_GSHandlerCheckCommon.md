# __GSHandlerCheckCommon

- ea: `0x18000b464`
- end: `0x18000b4c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b440`
- `0x18000b4d0`

## callees

- `0x180001570`
- `0x18000b464`

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
0x18000b464  mov     r10, rcx
0x18000b467  mov     r11, rdx
0x18000b46a  mov     ecx, [r8]
0x18000b46d  and     ecx, 0FFFFFFF8h
0x18000b470  test    byte ptr [r8], 4
0x18000b474  jz      short loc_18000B48B
0x18000b476  mov     eax, [r8+8]
0x18000b47a  movsxd  r9, dword ptr [r8+4]
0x18000b47e  neg     eax
0x18000b480  movsxd  rdx, eax
0x18000b483  add     r9, r10
0x18000b486  and     r9, rdx
0x18000b489  jmp     short loc_18000B48E
0x18000b48b  mov     r9, r10
0x18000b48e  movsxd  rax, ecx
0x18000b491  mov     rdx, [rax+r9]
0x18000b495  mov     rax, [r11+10h]
0x18000b499  mov     ecx, [rax+8]
0x18000b49c  mov     rax, [r11+8]
0x18000b4a0  test    byte ptr [rcx+rax+3], 0Fh
0x18000b4a5  jz      short loc_18000B4B9
0x18000b4a7  movzx   eax, byte ptr [rcx+rax+3]
0x18000b4ac  mov     ecx, 0FFFFFFF0h
0x18000b4b1  and     rax, rcx
0x18000b4b4  add     rax, r10
0x18000b4b7  jmp     short loc_18000B4BC
0x18000b4b9  mov     rax, r10
0x18000b4bc  xor     rdx, rax
0x18000b4bf  mov     rcx, rdx; StackCookie
0x18000b4c2  jmp     __security_check_cookie
```
