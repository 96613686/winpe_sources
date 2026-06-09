# __GSHandlerCheckCommon

- ea: `0x14000d6bc`
- end: `0x14000d72c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d698`

## callees

- `0x14000d6bc`
- `0x14000d7f0`

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
0x14000d6bc  sub     rsp, 28h
0x14000d6c0  mov     eax, [r8]
0x14000d6c3  mov     r10, rcx
0x14000d6c6  mov     ecx, eax
0x14000d6c8  mov     r11, rdx
0x14000d6cb  and     ecx, 0FFFFFFF8h
0x14000d6ce  test    al, 4
0x14000d6d0  jz      short loc_14000D6E7
0x14000d6d2  mov     eax, [r8+8]
0x14000d6d6  movsxd  r9, dword ptr [r8+4]
0x14000d6da  neg     eax
0x14000d6dc  movsxd  rdx, eax
0x14000d6df  add     r9, r10
0x14000d6e2  and     r9, rdx
0x14000d6e5  jmp     short loc_14000D6EA
0x14000d6e7  mov     r9, r10
0x14000d6ea  movsxd  rax, ecx
0x14000d6ed  mov     rdx, [rax+r9]
0x14000d6f1  mov     rax, [r11+10h]
0x14000d6f5  mov     ecx, [rax+8]
0x14000d6f8  mov     rax, [r11+8]
0x14000d6fc  movzx   r8d, byte ptr [rcx+rax+3]
0x14000d702  test    r8b, 0Fh
0x14000d706  jz      short loc_14000D718
0x14000d708  mov     eax, r8d
0x14000d70b  mov     ecx, 0FFFFFFF0h
0x14000d710  and     rax, rcx
0x14000d713  add     rax, r10
0x14000d716  jmp     short loc_14000D71B
0x14000d718  mov     rax, r10
0x14000d71b  xor     rdx, rax
0x14000d71e  mov     rcx, rdx; StackCookie
0x14000d721  call    __security_check_cookie
0x14000d726  add     rsp, 28h
0x14000d72a  retn
```
