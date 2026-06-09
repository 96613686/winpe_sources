# __GSHandlerCheckCommon

- ea: `0x14000dc8c`
- end: `0x14000dcfc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000dc68`

## callees

- `0x14000dc8c`
- `0x14000ddc0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14000dc8c  sub     rsp, 28h
0x14000dc90  mov     eax, [r8]
0x14000dc93  mov     r10, rcx
0x14000dc96  mov     ecx, eax
0x14000dc98  mov     r11, rdx
0x14000dc9b  and     ecx, 0FFFFFFF8h
0x14000dc9e  test    al, 4
0x14000dca0  jz      short loc_14000DCB7
0x14000dca2  mov     eax, [r8+8]
0x14000dca6  movsxd  r9, dword ptr [r8+4]
0x14000dcaa  neg     eax
0x14000dcac  movsxd  rdx, eax
0x14000dcaf  add     r9, r10
0x14000dcb2  and     r9, rdx
0x14000dcb5  jmp     short loc_14000DCBA
0x14000dcb7  mov     r9, r10
0x14000dcba  movsxd  rax, ecx
0x14000dcbd  mov     rdx, [rax+r9]
0x14000dcc1  mov     rax, [r11+10h]
0x14000dcc5  mov     ecx, [rax+8]
0x14000dcc8  mov     rax, [r11+8]
0x14000dccc  movzx   r8d, byte ptr [rcx+rax+3]
0x14000dcd2  test    r8b, 0Fh
0x14000dcd6  jz      short loc_14000DCE8
0x14000dcd8  mov     eax, r8d
0x14000dcdb  mov     ecx, 0FFFFFFF0h
0x14000dce0  and     rax, rcx
0x14000dce3  add     rax, r10
0x14000dce6  jmp     short loc_14000DCEB
0x14000dce8  mov     rax, r10
0x14000dceb  xor     rdx, rax
0x14000dcee  mov     rcx, rdx; StackCookie
0x14000dcf1  call    __security_check_cookie
0x14000dcf6  add     rsp, 28h
0x14000dcfa  retn
```
