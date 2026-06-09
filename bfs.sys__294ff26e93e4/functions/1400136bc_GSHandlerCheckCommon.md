# __GSHandlerCheckCommon

- ea: `0x1400136bc`
- end: `0x14001372c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013698`
- `0x140013734`

## callees

- `0x1400136bc`
- `0x140013860`

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
0x1400136bc  sub     rsp, 28h
0x1400136c0  mov     eax, [r8]
0x1400136c3  mov     r10, rcx
0x1400136c6  mov     ecx, eax
0x1400136c8  mov     r11, rdx
0x1400136cb  and     ecx, 0FFFFFFF8h
0x1400136ce  test    al, 4
0x1400136d0  jz      short loc_1400136E7
0x1400136d2  mov     eax, [r8+8]
0x1400136d6  movsxd  r9, dword ptr [r8+4]
0x1400136da  neg     eax
0x1400136dc  movsxd  rdx, eax
0x1400136df  add     r9, r10
0x1400136e2  and     r9, rdx
0x1400136e5  jmp     short loc_1400136EA
0x1400136e7  mov     r9, r10
0x1400136ea  movsxd  rax, ecx
0x1400136ed  mov     rdx, [rax+r9]
0x1400136f1  mov     rax, [r11+10h]
0x1400136f5  mov     ecx, [rax+8]
0x1400136f8  mov     rax, [r11+8]
0x1400136fc  movzx   r8d, byte ptr [rcx+rax+3]
0x140013702  test    r8b, 0Fh
0x140013706  jz      short loc_140013718
0x140013708  mov     eax, r8d
0x14001370b  mov     ecx, 0FFFFFFF0h
0x140013710  and     rax, rcx
0x140013713  add     rax, r10
0x140013716  jmp     short loc_14001371B
0x140013718  mov     rax, r10
0x14001371b  xor     rdx, rax
0x14001371e  mov     rcx, rdx; StackCookie
0x140013721  call    __security_check_cookie
0x140013726  add     rsp, 28h
0x14001372a  retn
```
