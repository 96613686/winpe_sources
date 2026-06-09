# __GSHandlerCheckCommon

- ea: `0x180008350`
- end: `0x1800083b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000832c`

## callees

- `0x180008350`
- `0x180008410`

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
0x180008350  mov     r10, rcx
0x180008353  mov     r11, rdx
0x180008356  mov     ecx, [r8]
0x180008359  and     ecx, 0FFFFFFF8h
0x18000835c  test    byte ptr [r8], 4
0x180008360  jz      short loc_180008377
0x180008362  mov     eax, [r8+8]
0x180008366  movsxd  r9, dword ptr [r8+4]
0x18000836a  neg     eax
0x18000836c  movsxd  rdx, eax
0x18000836f  add     r9, r10
0x180008372  and     r9, rdx
0x180008375  jmp     short loc_18000837A
0x180008377  mov     r9, r10
0x18000837a  movsxd  rax, ecx
0x18000837d  mov     rdx, [rax+r9]
0x180008381  mov     rax, [r11+10h]
0x180008385  mov     ecx, [rax+8]
0x180008388  mov     rax, [r11+8]
0x18000838c  test    byte ptr [rcx+rax+3], 0Fh
0x180008391  jz      short loc_1800083A5
0x180008393  movzx   eax, byte ptr [rcx+rax+3]
0x180008398  mov     ecx, 0FFFFFFF0h
0x18000839d  and     rax, rcx
0x1800083a0  add     rax, r10
0x1800083a3  jmp     short loc_1800083A8
0x1800083a5  mov     rax, r10
0x1800083a8  xor     rdx, rax
0x1800083ab  mov     rcx, rdx; StackCookie
0x1800083ae  jmp     __security_check_cookie
```
