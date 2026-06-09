# __GSHandlerCheckCommon

- ea: `0x140010ca0`
- end: `0x140010d03`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010c7c`
- `0x140010d0c`

## callees

- `0x1400016a0`
- `0x140010ca0`

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
0x140010ca0  mov     r10, rcx
0x140010ca3  mov     r11, rdx
0x140010ca6  mov     ecx, [r8]
0x140010ca9  and     ecx, 0FFFFFFF8h
0x140010cac  test    byte ptr [r8], 4
0x140010cb0  jz      short loc_140010CC7
0x140010cb2  mov     eax, [r8+8]
0x140010cb6  movsxd  r9, dword ptr [r8+4]
0x140010cba  neg     eax
0x140010cbc  movsxd  rdx, eax
0x140010cbf  add     r9, r10
0x140010cc2  and     r9, rdx
0x140010cc5  jmp     short loc_140010CCA
0x140010cc7  mov     r9, r10
0x140010cca  movsxd  rax, ecx
0x140010ccd  mov     rdx, [rax+r9]
0x140010cd1  mov     rax, [r11+10h]
0x140010cd5  mov     ecx, [rax+8]
0x140010cd8  mov     rax, [r11+8]
0x140010cdc  test    byte ptr [rcx+rax+3], 0Fh
0x140010ce1  jz      short loc_140010CF5
0x140010ce3  movzx   eax, byte ptr [rcx+rax+3]
0x140010ce8  mov     ecx, 0FFFFFFF0h
0x140010ced  and     rax, rcx
0x140010cf0  add     rax, r10
0x140010cf3  jmp     short loc_140010CF8
0x140010cf5  mov     rax, r10
0x140010cf8  xor     rdx, rax
0x140010cfb  mov     rcx, rdx; StackCookie
0x140010cfe  jmp     __security_check_cookie
```
