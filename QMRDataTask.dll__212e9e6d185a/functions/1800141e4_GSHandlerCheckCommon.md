# __GSHandlerCheckCommon

- ea: `0x1800141e4`
- end: `0x180014247`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800141c0`
- `0x180014250`

## callees

- `0x1800141e4`
- `0x180014310`

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
0x1800141e4  mov     r10, rcx
0x1800141e7  mov     r11, rdx
0x1800141ea  mov     ecx, [r8]
0x1800141ed  and     ecx, 0FFFFFFF8h
0x1800141f0  test    byte ptr [r8], 4
0x1800141f4  jz      short loc_18001420B
0x1800141f6  mov     eax, [r8+8]
0x1800141fa  movsxd  r9, dword ptr [r8+4]
0x1800141fe  neg     eax
0x180014200  movsxd  rdx, eax
0x180014203  add     r9, r10
0x180014206  and     r9, rdx
0x180014209  jmp     short loc_18001420E
0x18001420b  mov     r9, r10
0x18001420e  movsxd  rax, ecx
0x180014211  mov     rdx, [rax+r9]
0x180014215  mov     rax, [r11+10h]
0x180014219  mov     ecx, [rax+8]
0x18001421c  mov     rax, [r11+8]
0x180014220  test    byte ptr [rcx+rax+3], 0Fh
0x180014225  jz      short loc_180014239
0x180014227  movzx   eax, byte ptr [rcx+rax+3]
0x18001422c  mov     ecx, 0FFFFFFF0h
0x180014231  and     rax, rcx
0x180014234  add     rax, r10
0x180014237  jmp     short loc_18001423C
0x180014239  mov     rax, r10
0x18001423c  xor     rdx, rax
0x18001423f  mov     rcx, rdx; StackCookie
0x180014242  jmp     __security_check_cookie
```
