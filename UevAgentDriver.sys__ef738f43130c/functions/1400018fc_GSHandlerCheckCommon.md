# __GSHandlerCheckCommon

- ea: `0x1400018fc`
- end: `0x14000196c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400018d8`

## callees

- `0x1400018fc`
- `0x140001a30`

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
0x1400018fc  sub     rsp, 28h
0x140001900  mov     eax, [r8]
0x140001903  mov     r10, rcx
0x140001906  mov     ecx, eax
0x140001908  mov     r11, rdx
0x14000190b  and     ecx, 0FFFFFFF8h
0x14000190e  test    al, 4
0x140001910  jz      short loc_140001927
0x140001912  mov     eax, [r8+8]
0x140001916  movsxd  r9, dword ptr [r8+4]
0x14000191a  neg     eax
0x14000191c  movsxd  rdx, eax
0x14000191f  add     r9, r10
0x140001922  and     r9, rdx
0x140001925  jmp     short loc_14000192A
0x140001927  mov     r9, r10
0x14000192a  movsxd  rax, ecx
0x14000192d  mov     rdx, [rax+r9]
0x140001931  mov     rax, [r11+10h]
0x140001935  mov     ecx, [rax+8]
0x140001938  mov     rax, [r11+8]
0x14000193c  movzx   r8d, byte ptr [rcx+rax+3]
0x140001942  test    r8b, 0Fh
0x140001946  jz      short loc_140001958
0x140001948  mov     eax, r8d
0x14000194b  mov     ecx, 0FFFFFFF0h
0x140001950  and     rax, rcx
0x140001953  add     rax, r10
0x140001956  jmp     short loc_14000195B
0x140001958  mov     rax, r10
0x14000195b  xor     rdx, rax
0x14000195e  mov     rcx, rdx; StackCookie
0x140001961  call    __security_check_cookie
0x140001966  add     rsp, 28h
0x14000196a  retn
```
