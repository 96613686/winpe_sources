# __GSHandlerCheckCommon

- ea: `0x18000c4fc`
- end: `0x18000c55f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c4d8`
- `0x18000c568`

## callees

- `0x18000c4fc`
- `0x18000c610`

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
0x18000c4fc  mov     r10, rcx
0x18000c4ff  mov     r11, rdx
0x18000c502  mov     ecx, [r8]
0x18000c505  and     ecx, 0FFFFFFF8h
0x18000c508  test    byte ptr [r8], 4
0x18000c50c  jz      short loc_18000C523
0x18000c50e  mov     eax, [r8+8]
0x18000c512  movsxd  r9, dword ptr [r8+4]
0x18000c516  neg     eax
0x18000c518  movsxd  rdx, eax
0x18000c51b  add     r9, r10
0x18000c51e  and     r9, rdx
0x18000c521  jmp     short loc_18000C526
0x18000c523  mov     r9, r10
0x18000c526  movsxd  rax, ecx
0x18000c529  mov     rdx, [rax+r9]
0x18000c52d  mov     rax, [r11+10h]
0x18000c531  mov     ecx, [rax+8]
0x18000c534  mov     rax, [r11+8]
0x18000c538  test    byte ptr [rcx+rax+3], 0Fh
0x18000c53d  jz      short loc_18000C551
0x18000c53f  movzx   eax, byte ptr [rcx+rax+3]
0x18000c544  mov     ecx, 0FFFFFFF0h
0x18000c549  and     rax, rcx
0x18000c54c  add     rax, r10
0x18000c54f  jmp     short loc_18000C554
0x18000c551  mov     rax, r10
0x18000c554  xor     rdx, rax
0x18000c557  mov     rcx, rdx; StackCookie
0x18000c55a  jmp     __security_check_cookie
```
