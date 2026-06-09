# __GSHandlerCheckCommon

- ea: `0x180013500`
- end: `0x180013563`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800134dc`
- `0x18001356c`

## callees

- `0x180004c70`
- `0x180013500`

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
0x180013500  mov     r10, rcx
0x180013503  mov     r11, rdx
0x180013506  mov     ecx, [r8]
0x180013509  and     ecx, 0FFFFFFF8h
0x18001350c  test    byte ptr [r8], 4
0x180013510  jz      short loc_180013527
0x180013512  mov     eax, [r8+8]
0x180013516  movsxd  r9, dword ptr [r8+4]
0x18001351a  neg     eax
0x18001351c  movsxd  rdx, eax
0x18001351f  add     r9, r10
0x180013522  and     r9, rdx
0x180013525  jmp     short loc_18001352A
0x180013527  mov     r9, r10
0x18001352a  movsxd  rax, ecx
0x18001352d  mov     rdx, [rax+r9]
0x180013531  mov     rax, [r11+10h]
0x180013535  mov     ecx, [rax+8]
0x180013538  mov     rax, [r11+8]
0x18001353c  test    byte ptr [rcx+rax+3], 0Fh
0x180013541  jz      short loc_180013555
0x180013543  movzx   eax, byte ptr [rcx+rax+3]
0x180013548  mov     ecx, 0FFFFFFF0h
0x18001354d  and     rax, rcx
0x180013550  add     rax, r10
0x180013553  jmp     short loc_180013558
0x180013555  mov     rax, r10
0x180013558  xor     rdx, rax
0x18001355b  mov     rcx, rdx; StackCookie
0x18001355e  jmp     __security_check_cookie
```
