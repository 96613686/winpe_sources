# __GSHandlerCheckCommon

- ea: `0x180006554`
- end: `0x1800065b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006530`

## callees

- `0x180006554`
- `0x180006600`

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
0x180006554  mov     r10, rcx
0x180006557  mov     r11, rdx
0x18000655a  mov     ecx, [r8]
0x18000655d  and     ecx, 0FFFFFFF8h
0x180006560  test    byte ptr [r8], 4
0x180006564  jz      short loc_18000657B
0x180006566  mov     eax, [r8+8]
0x18000656a  movsxd  r9, dword ptr [r8+4]
0x18000656e  neg     eax
0x180006570  movsxd  rdx, eax
0x180006573  add     r9, r10
0x180006576  and     r9, rdx
0x180006579  jmp     short loc_18000657E
0x18000657b  mov     r9, r10
0x18000657e  movsxd  rax, ecx
0x180006581  mov     rdx, [rax+r9]
0x180006585  mov     rax, [r11+10h]
0x180006589  mov     ecx, [rax+8]
0x18000658c  mov     rax, [r11+8]
0x180006590  test    byte ptr [rcx+rax+3], 0Fh
0x180006595  jz      short loc_1800065A9
0x180006597  movzx   eax, byte ptr [rcx+rax+3]
0x18000659c  mov     ecx, 0FFFFFFF0h
0x1800065a1  and     rax, rcx
0x1800065a4  add     rax, r10
0x1800065a7  jmp     short loc_1800065AC
0x1800065a9  mov     rax, r10
0x1800065ac  xor     rdx, rax
0x1800065af  mov     rcx, rdx; StackCookie
0x1800065b2  jmp     __security_check_cookie
```
