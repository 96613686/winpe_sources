# __GSHandlerCheckCommon

- ea: `0x14000179c`
- end: `0x14000180c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001778`

## callees

- `0x14000179c`
- `0x140001820`

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
0x14000179c  sub     rsp, 28h
0x1400017a0  mov     eax, [r8]
0x1400017a3  mov     r10, rcx
0x1400017a6  mov     ecx, eax
0x1400017a8  mov     r11, rdx
0x1400017ab  and     ecx, 0FFFFFFF8h
0x1400017ae  test    al, 4
0x1400017b0  jz      short loc_1400017C7
0x1400017b2  mov     eax, [r8+8]
0x1400017b6  movsxd  r9, dword ptr [r8+4]
0x1400017ba  neg     eax
0x1400017bc  movsxd  rdx, eax
0x1400017bf  add     r9, r10
0x1400017c2  and     r9, rdx
0x1400017c5  jmp     short loc_1400017CA
0x1400017c7  mov     r9, r10
0x1400017ca  movsxd  rax, ecx
0x1400017cd  mov     rdx, [rax+r9]
0x1400017d1  mov     rax, [r11+10h]
0x1400017d5  mov     ecx, [rax+8]
0x1400017d8  mov     rax, [r11+8]
0x1400017dc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400017e2  test    r8b, 0Fh
0x1400017e6  jz      short loc_1400017F8
0x1400017e8  mov     eax, r8d
0x1400017eb  mov     ecx, 0FFFFFFF0h
0x1400017f0  and     rax, rcx
0x1400017f3  add     rax, r10
0x1400017f6  jmp     short loc_1400017FB
0x1400017f8  mov     rax, r10
0x1400017fb  xor     rdx, rax
0x1400017fe  mov     rcx, rdx; StackCookie
0x140001801  call    __security_check_cookie
0x140001806  add     rsp, 28h
0x14000180a  retn
```
