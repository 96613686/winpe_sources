# __GSHandlerCheckCommon

- ea: `0x14000e3a8`
- end: `0x14000e408`
- name: `__GSHandlerCheckCommon`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e384`
- `0x14000e4e4`
- `0x14000f3d0`

## callees

- `0x14000a390`
- `0x14000e3a8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x14000e3a8  push    rbx
0x14000e3aa  mov     r11d, [r8]
0x14000e3ad  mov     rbx, rdx
0x14000e3b0  and     r11d, 0FFFFFFF8h
0x14000e3b4  mov     r9, rcx
0x14000e3b7  test    byte ptr [r8], 4
0x14000e3bb  mov     r10, rcx
0x14000e3be  jz      short loc_14000E3D3
0x14000e3c0  mov     eax, [r8+8]
0x14000e3c4  movsxd  r10, dword ptr [r8+4]
0x14000e3c8  neg     eax
0x14000e3ca  add     r10, rcx
0x14000e3cd  movsxd  rcx, eax
0x14000e3d0  and     r10, rcx
0x14000e3d3  movsxd  rax, r11d
0x14000e3d6  mov     rdx, [rax+r10]
0x14000e3da  mov     rax, [rbx+10h]
0x14000e3de  mov     ecx, [rax+8]
0x14000e3e1  mov     rax, [rbx+8]
0x14000e3e5  test    byte ptr [rcx+rax+3], 0Fh
0x14000e3ea  jz      short loc_14000E3FC
0x14000e3ec  movzx   eax, byte ptr [rcx+rax+3]
0x14000e3f1  mov     ecx, 0FFFFFFF0h
0x14000e3f6  and     rax, rcx
0x14000e3f9  add     r9, rax
0x14000e3fc  xor     r9, rdx
0x14000e3ff  mov     rcx, r9; StackCookie
0x14000e402  pop     rbx
0x14000e403  jmp     __security_check_cookie
```
