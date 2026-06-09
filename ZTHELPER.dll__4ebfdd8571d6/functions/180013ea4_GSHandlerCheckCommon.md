# __GSHandlerCheckCommon

- ea: `0x180013ea4`
- end: `0x180013f07`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013e80`

## callees

- `0x1800014b0`
- `0x180013ea4`

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
0x180013ea4  mov     r10, rcx
0x180013ea7  mov     r11, rdx
0x180013eaa  mov     ecx, [r8]
0x180013ead  and     ecx, 0FFFFFFF8h
0x180013eb0  test    byte ptr [r8], 4
0x180013eb4  jz      short loc_180013ECB
0x180013eb6  mov     eax, [r8+8]
0x180013eba  movsxd  r9, dword ptr [r8+4]
0x180013ebe  neg     eax
0x180013ec0  movsxd  rdx, eax
0x180013ec3  add     r9, r10
0x180013ec6  and     r9, rdx
0x180013ec9  jmp     short loc_180013ECE
0x180013ecb  mov     r9, r10
0x180013ece  movsxd  rax, ecx
0x180013ed1  mov     rdx, [rax+r9]
0x180013ed5  mov     rax, [r11+10h]
0x180013ed9  mov     ecx, [rax+8]
0x180013edc  mov     rax, [r11+8]
0x180013ee0  test    byte ptr [rcx+rax+3], 0Fh
0x180013ee5  jz      short loc_180013EF9
0x180013ee7  movzx   eax, byte ptr [rcx+rax+3]
0x180013eec  mov     ecx, 0FFFFFFF0h
0x180013ef1  and     rax, rcx
0x180013ef4  add     rax, r10
0x180013ef7  jmp     short loc_180013EFC
0x180013ef9  mov     rax, r10
0x180013efc  xor     rdx, rax
0x180013eff  mov     rcx, rdx; StackCookie
0x180013f02  jmp     __security_check_cookie
```
