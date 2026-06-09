# __GSHandlerCheckCommon

- ea: `0x18001d3d0`
- end: `0x18001d433`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d3ac`
- `0x18001d43c`

## callees

- `0x180001520`
- `0x18001d3d0`

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
0x18001d3d0  mov     r10, rcx
0x18001d3d3  mov     r11, rdx
0x18001d3d6  mov     ecx, [r8]
0x18001d3d9  and     ecx, 0FFFFFFF8h
0x18001d3dc  test    byte ptr [r8], 4
0x18001d3e0  jz      short loc_18001D3F7
0x18001d3e2  mov     eax, [r8+8]
0x18001d3e6  movsxd  r9, dword ptr [r8+4]
0x18001d3ea  neg     eax
0x18001d3ec  movsxd  rdx, eax
0x18001d3ef  add     r9, r10
0x18001d3f2  and     r9, rdx
0x18001d3f5  jmp     short loc_18001D3FA
0x18001d3f7  mov     r9, r10
0x18001d3fa  movsxd  rax, ecx
0x18001d3fd  mov     rdx, [rax+r9]
0x18001d401  mov     rax, [r11+10h]
0x18001d405  mov     ecx, [rax+8]
0x18001d408  mov     rax, [r11+8]
0x18001d40c  test    byte ptr [rcx+rax+3], 0Fh
0x18001d411  jz      short loc_18001D425
0x18001d413  movzx   eax, byte ptr [rcx+rax+3]
0x18001d418  mov     ecx, 0FFFFFFF0h
0x18001d41d  and     rax, rcx
0x18001d420  add     rax, r10
0x18001d423  jmp     short loc_18001D428
0x18001d425  mov     rax, r10
0x18001d428  xor     rdx, rax
0x18001d42b  mov     rcx, rdx; StackCookie
0x18001d42e  jmp     __security_check_cookie
```
