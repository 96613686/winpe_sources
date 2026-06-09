# __GSHandlerCheckCommon

- ea: `0x14000687c`
- end: `0x1400068ec`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006858`
- `0x1400068f4`

## callees

- `0x14000687c`
- `0x140006a20`

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
0x14000687c  sub     rsp, 28h
0x140006880  mov     eax, [r8]
0x140006883  mov     r10, rcx
0x140006886  mov     ecx, eax
0x140006888  mov     r11, rdx
0x14000688b  and     ecx, 0FFFFFFF8h
0x14000688e  test    al, 4
0x140006890  jz      short loc_1400068A7
0x140006892  mov     eax, [r8+8]
0x140006896  movsxd  r9, dword ptr [r8+4]
0x14000689a  neg     eax
0x14000689c  movsxd  rdx, eax
0x14000689f  add     r9, r10
0x1400068a2  and     r9, rdx
0x1400068a5  jmp     short loc_1400068AA
0x1400068a7  mov     r9, r10
0x1400068aa  movsxd  rax, ecx
0x1400068ad  mov     rdx, [rax+r9]
0x1400068b1  mov     rax, [r11+10h]
0x1400068b5  mov     ecx, [rax+8]
0x1400068b8  mov     rax, [r11+8]
0x1400068bc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400068c2  test    r8b, 0Fh
0x1400068c6  jz      short loc_1400068D8
0x1400068c8  mov     eax, r8d
0x1400068cb  mov     ecx, 0FFFFFFF0h
0x1400068d0  and     rax, rcx
0x1400068d3  add     rax, r10
0x1400068d6  jmp     short loc_1400068DB
0x1400068d8  mov     rax, r10
0x1400068db  xor     rdx, rax
0x1400068de  mov     rcx, rdx; StackCookie
0x1400068e1  call    __security_check_cookie
0x1400068e6  add     rsp, 28h
0x1400068ea  retn
```
