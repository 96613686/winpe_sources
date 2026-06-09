# __GSHandlerCheckCommon

- ea: `0x180020f90`
- end: `0x180020ff3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020f6c`

## callees

- `0x1800018b0`
- `0x180020f90`

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
0x180020f90  mov     r10, rcx
0x180020f93  mov     r11, rdx
0x180020f96  mov     ecx, [r8]
0x180020f99  and     ecx, 0FFFFFFF8h
0x180020f9c  test    byte ptr [r8], 4
0x180020fa0  jz      short loc_180020FB7
0x180020fa2  mov     eax, [r8+8]
0x180020fa6  movsxd  r9, dword ptr [r8+4]
0x180020faa  neg     eax
0x180020fac  movsxd  rdx, eax
0x180020faf  add     r9, r10
0x180020fb2  and     r9, rdx
0x180020fb5  jmp     short loc_180020FBA
0x180020fb7  mov     r9, r10
0x180020fba  movsxd  rax, ecx
0x180020fbd  mov     rdx, [rax+r9]
0x180020fc1  mov     rax, [r11+10h]
0x180020fc5  mov     ecx, [rax+8]
0x180020fc8  mov     rax, [r11+8]
0x180020fcc  test    byte ptr [rcx+rax+3], 0Fh
0x180020fd1  jz      short loc_180020FE5
0x180020fd3  movzx   eax, byte ptr [rcx+rax+3]
0x180020fd8  mov     ecx, 0FFFFFFF0h
0x180020fdd  and     rax, rcx
0x180020fe0  add     rax, r10
0x180020fe3  jmp     short loc_180020FE8
0x180020fe5  mov     rax, r10
0x180020fe8  xor     rdx, rax
0x180020feb  mov     rcx, rdx; StackCookie
0x180020fee  jmp     __security_check_cookie
```
