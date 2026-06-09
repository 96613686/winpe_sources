# __GSHandlerCheckCommon

- ea: `0x1800120cc`
- end: `0x18001213c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800120a8`

## callees

- `0x1800120cc`
- `0x180012200`

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
0x1800120cc  sub     rsp, 28h
0x1800120d0  mov     eax, [r8]
0x1800120d3  mov     r10, rcx
0x1800120d6  mov     ecx, eax
0x1800120d8  mov     r11, rdx
0x1800120db  and     ecx, 0FFFFFFF8h
0x1800120de  test    al, 4
0x1800120e0  jz      short loc_1800120F7
0x1800120e2  mov     eax, [r8+8]
0x1800120e6  movsxd  r9, dword ptr [r8+4]
0x1800120ea  neg     eax
0x1800120ec  movsxd  rdx, eax
0x1800120ef  add     r9, r10
0x1800120f2  and     r9, rdx
0x1800120f5  jmp     short loc_1800120FA
0x1800120f7  mov     r9, r10
0x1800120fa  movsxd  rax, ecx
0x1800120fd  mov     rdx, [rax+r9]
0x180012101  mov     rax, [r11+10h]
0x180012105  mov     ecx, [rax+8]
0x180012108  mov     rax, [r11+8]
0x18001210c  movzx   r8d, byte ptr [rcx+rax+3]
0x180012112  test    r8b, 0Fh
0x180012116  jz      short loc_180012128
0x180012118  mov     eax, r8d
0x18001211b  mov     ecx, 0FFFFFFF0h
0x180012120  and     rax, rcx
0x180012123  add     rax, r10
0x180012126  jmp     short loc_18001212B
0x180012128  mov     rax, r10
0x18001212b  xor     rdx, rax
0x18001212e  mov     rcx, rdx; StackCookie
0x180012131  call    __security_check_cookie
0x180012136  add     rsp, 28h
0x18001213a  retn
```
