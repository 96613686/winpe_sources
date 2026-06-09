# __GSHandlerCheckCommon

- ea: `0x180012f00`
- end: `0x180012f63`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012edc`

## callees

- `0x180012f00`
- `0x180012fc0`

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
0x180012f00  mov     r10, rcx
0x180012f03  mov     r11, rdx
0x180012f06  mov     ecx, [r8]
0x180012f09  and     ecx, 0FFFFFFF8h
0x180012f0c  test    byte ptr [r8], 4
0x180012f10  jz      short loc_180012F27
0x180012f12  mov     eax, [r8+8]
0x180012f16  movsxd  r9, dword ptr [r8+4]
0x180012f1a  neg     eax
0x180012f1c  movsxd  rdx, eax
0x180012f1f  add     r9, r10
0x180012f22  and     r9, rdx
0x180012f25  jmp     short loc_180012F2A
0x180012f27  mov     r9, r10
0x180012f2a  movsxd  rax, ecx
0x180012f2d  mov     rdx, [rax+r9]
0x180012f31  mov     rax, [r11+10h]
0x180012f35  mov     ecx, [rax+8]
0x180012f38  mov     rax, [r11+8]
0x180012f3c  test    byte ptr [rcx+rax+3], 0Fh
0x180012f41  jz      short loc_180012F55
0x180012f43  movzx   eax, byte ptr [rcx+rax+3]
0x180012f48  mov     ecx, 0FFFFFFF0h
0x180012f4d  and     rax, rcx
0x180012f50  add     rax, r10
0x180012f53  jmp     short loc_180012F58
0x180012f55  mov     rax, r10
0x180012f58  xor     rdx, rax
0x180012f5b  mov     rcx, rdx; StackCookie
0x180012f5e  jmp     __security_check_cookie
```
