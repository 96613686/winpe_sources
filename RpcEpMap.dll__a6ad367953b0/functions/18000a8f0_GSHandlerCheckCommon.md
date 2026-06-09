# __GSHandlerCheckCommon

- ea: `0x18000a8f0`
- end: `0x18000a953`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a8cc`

## callees

- `0x18000a8f0`
- `0x18000a980`

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
0x18000a8f0  mov     r10, rcx
0x18000a8f3  mov     r11, rdx
0x18000a8f6  mov     ecx, [r8]
0x18000a8f9  and     ecx, 0FFFFFFF8h
0x18000a8fc  test    byte ptr [r8], 4
0x18000a900  jz      short loc_18000A917
0x18000a902  mov     eax, [r8+8]
0x18000a906  movsxd  r9, dword ptr [r8+4]
0x18000a90a  neg     eax
0x18000a90c  movsxd  rdx, eax
0x18000a90f  add     r9, r10
0x18000a912  and     r9, rdx
0x18000a915  jmp     short loc_18000A91A
0x18000a917  mov     r9, r10
0x18000a91a  movsxd  rax, ecx
0x18000a91d  mov     rdx, [rax+r9]
0x18000a921  mov     rax, [r11+10h]
0x18000a925  mov     ecx, [rax+8]
0x18000a928  mov     rax, [r11+8]
0x18000a92c  test    byte ptr [rcx+rax+3], 0Fh
0x18000a931  jz      short loc_18000A945
0x18000a933  movzx   eax, byte ptr [rcx+rax+3]
0x18000a938  mov     ecx, 0FFFFFFF0h
0x18000a93d  and     rax, rcx
0x18000a940  add     rax, r10
0x18000a943  jmp     short loc_18000A948
0x18000a945  mov     rax, r10
0x18000a948  xor     rdx, rax
0x18000a94b  mov     rcx, rdx; StackCookie
0x18000a94e  jmp     __security_check_cookie
```
