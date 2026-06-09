# __GSHandlerCheckCommon

- ea: `0x180007e24`
- end: `0x180007e87`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007e00`
- `0x180007e90`

## callees

- `0x180001560`
- `0x180007e24`

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
0x180007e24  mov     r10, rcx
0x180007e27  mov     r11, rdx
0x180007e2a  mov     ecx, [r8]
0x180007e2d  and     ecx, 0FFFFFFF8h
0x180007e30  test    byte ptr [r8], 4
0x180007e34  jz      short loc_180007E4B
0x180007e36  mov     eax, [r8+8]
0x180007e3a  movsxd  r9, dword ptr [r8+4]
0x180007e3e  neg     eax
0x180007e40  movsxd  rdx, eax
0x180007e43  add     r9, r10
0x180007e46  and     r9, rdx
0x180007e49  jmp     short loc_180007E4E
0x180007e4b  mov     r9, r10
0x180007e4e  movsxd  rax, ecx
0x180007e51  mov     rdx, [rax+r9]
0x180007e55  mov     rax, [r11+10h]
0x180007e59  mov     ecx, [rax+8]
0x180007e5c  mov     rax, [r11+8]
0x180007e60  test    byte ptr [rcx+rax+3], 0Fh
0x180007e65  jz      short loc_180007E79
0x180007e67  movzx   eax, byte ptr [rcx+rax+3]
0x180007e6c  mov     ecx, 0FFFFFFF0h
0x180007e71  and     rax, rcx
0x180007e74  add     rax, r10
0x180007e77  jmp     short loc_180007E7C
0x180007e79  mov     rax, r10
0x180007e7c  xor     rdx, rax
0x180007e7f  mov     rcx, rdx; StackCookie
0x180007e82  jmp     __security_check_cookie
```
