# __GSHandlerCheckCommon

- ea: `0x18001b300`
- end: `0x18001b363`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b2dc`
- `0x18001b36c`

## callees

- `0x1800036a0`
- `0x18001b300`

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
0x18001b300  mov     r10, rcx
0x18001b303  mov     r11, rdx
0x18001b306  mov     ecx, [r8]
0x18001b309  and     ecx, 0FFFFFFF8h
0x18001b30c  test    byte ptr [r8], 4
0x18001b310  jz      short loc_18001B327
0x18001b312  mov     eax, [r8+8]
0x18001b316  movsxd  r9, dword ptr [r8+4]
0x18001b31a  neg     eax
0x18001b31c  movsxd  rdx, eax
0x18001b31f  add     r9, r10
0x18001b322  and     r9, rdx
0x18001b325  jmp     short loc_18001B32A
0x18001b327  mov     r9, r10
0x18001b32a  movsxd  rax, ecx
0x18001b32d  mov     rdx, [rax+r9]
0x18001b331  mov     rax, [r11+10h]
0x18001b335  mov     ecx, [rax+8]
0x18001b338  mov     rax, [r11+8]
0x18001b33c  test    byte ptr [rcx+rax+3], 0Fh
0x18001b341  jz      short loc_18001B355
0x18001b343  movzx   eax, byte ptr [rcx+rax+3]
0x18001b348  mov     ecx, 0FFFFFFF0h
0x18001b34d  and     rax, rcx
0x18001b350  add     rax, r10
0x18001b353  jmp     short loc_18001B358
0x18001b355  mov     rax, r10
0x18001b358  xor     rdx, rax
0x18001b35b  mov     rcx, rdx; StackCookie
0x18001b35e  jmp     __security_check_cookie
```
