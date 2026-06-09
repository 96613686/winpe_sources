# __GSHandlerCheckCommon

- ea: `0x140003738`
- end: `0x14000379b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003714`
- `0x14000ea3c`

## callees

- `0x1400033b0`
- `0x140003738`

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
0x140003738  mov     r10, rcx
0x14000373b  mov     r11, rdx
0x14000373e  mov     ecx, [r8]
0x140003741  and     ecx, 0FFFFFFF8h
0x140003744  test    byte ptr [r8], 4
0x140003748  jz      short loc_14000375F
0x14000374a  mov     eax, [r8+8]
0x14000374e  movsxd  r9, dword ptr [r8+4]
0x140003752  neg     eax
0x140003754  movsxd  rdx, eax
0x140003757  add     r9, r10
0x14000375a  and     r9, rdx
0x14000375d  jmp     short loc_140003762
0x14000375f  mov     r9, r10
0x140003762  movsxd  rax, ecx
0x140003765  mov     rdx, [rax+r9]
0x140003769  mov     rax, [r11+10h]
0x14000376d  mov     ecx, [rax+8]
0x140003770  mov     rax, [r11+8]
0x140003774  test    byte ptr [rcx+rax+3], 0Fh
0x140003779  jz      short loc_14000378D
0x14000377b  movzx   eax, byte ptr [rcx+rax+3]
0x140003780  mov     ecx, 0FFFFFFF0h
0x140003785  and     rax, rcx
0x140003788  add     rax, r10
0x14000378b  jmp     short loc_140003790
0x14000378d  mov     rax, r10
0x140003790  xor     rdx, rax
0x140003793  mov     rcx, rdx; StackCookie
0x140003796  jmp     __security_check_cookie
```
