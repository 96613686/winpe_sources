# __GSHandlerCheckCommon

- ea: `0x1400093e0`
- end: `0x140009443`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400093bc`
- `0x14000944c`

## callees

- `0x1400093e0`
- `0x1400094d0`

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
0x1400093e0  mov     r10, rcx
0x1400093e3  mov     r11, rdx
0x1400093e6  mov     ecx, [r8]
0x1400093e9  and     ecx, 0FFFFFFF8h
0x1400093ec  test    byte ptr [r8], 4
0x1400093f0  jz      short loc_140009407
0x1400093f2  mov     eax, [r8+8]
0x1400093f6  movsxd  r9, dword ptr [r8+4]
0x1400093fa  neg     eax
0x1400093fc  movsxd  rdx, eax
0x1400093ff  add     r9, r10
0x140009402  and     r9, rdx
0x140009405  jmp     short loc_14000940A
0x140009407  mov     r9, r10
0x14000940a  movsxd  rax, ecx
0x14000940d  mov     rdx, [rax+r9]
0x140009411  mov     rax, [r11+10h]
0x140009415  mov     ecx, [rax+8]
0x140009418  mov     rax, [r11+8]
0x14000941c  test    byte ptr [rcx+rax+3], 0Fh
0x140009421  jz      short loc_140009435
0x140009423  movzx   eax, byte ptr [rcx+rax+3]
0x140009428  mov     ecx, 0FFFFFFF0h
0x14000942d  and     rax, rcx
0x140009430  add     rax, r10
0x140009433  jmp     short loc_140009438
0x140009435  mov     rax, r10
0x140009438  xor     rdx, rax
0x14000943b  mov     rcx, rdx; StackCookie
0x14000943e  jmp     __security_check_cookie
```
