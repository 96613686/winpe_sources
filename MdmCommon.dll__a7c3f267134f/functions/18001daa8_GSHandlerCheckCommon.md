# __GSHandlerCheckCommon

- ea: `0x18001daa8`
- end: `0x18001db0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001da84`
- `0x18001db14`

## callees

- `0x180001520`
- `0x18001daa8`

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
0x18001daa8  mov     r10, rcx
0x18001daab  mov     r11, rdx
0x18001daae  mov     ecx, [r8]
0x18001dab1  and     ecx, 0FFFFFFF8h
0x18001dab4  test    byte ptr [r8], 4
0x18001dab8  jz      short loc_18001DACF
0x18001daba  mov     eax, [r8+8]
0x18001dabe  movsxd  r9, dword ptr [r8+4]
0x18001dac2  neg     eax
0x18001dac4  movsxd  rdx, eax
0x18001dac7  add     r9, r10
0x18001daca  and     r9, rdx
0x18001dacd  jmp     short loc_18001DAD2
0x18001dacf  mov     r9, r10
0x18001dad2  movsxd  rax, ecx
0x18001dad5  mov     rdx, [rax+r9]
0x18001dad9  mov     rax, [r11+10h]
0x18001dadd  mov     ecx, [rax+8]
0x18001dae0  mov     rax, [r11+8]
0x18001dae4  test    byte ptr [rcx+rax+3], 0Fh
0x18001dae9  jz      short loc_18001DAFD
0x18001daeb  movzx   eax, byte ptr [rcx+rax+3]
0x18001daf0  mov     ecx, 0FFFFFFF0h
0x18001daf5  and     rax, rcx
0x18001daf8  add     rax, r10
0x18001dafb  jmp     short loc_18001DB00
0x18001dafd  mov     rax, r10
0x18001db00  xor     rdx, rax
0x18001db03  mov     rcx, rdx; StackCookie
0x18001db06  jmp     __security_check_cookie
```
