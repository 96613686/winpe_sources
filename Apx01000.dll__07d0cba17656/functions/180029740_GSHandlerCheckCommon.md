# __GSHandlerCheckCommon

- ea: `0x180029740`
- end: `0x1800297a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002971c`
- `0x1800297ac`

## callees

- `0x180001d30`
- `0x180029740`

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
0x180029740  mov     r10, rcx
0x180029743  mov     r11, rdx
0x180029746  mov     ecx, [r8]
0x180029749  and     ecx, 0FFFFFFF8h
0x18002974c  test    byte ptr [r8], 4
0x180029750  jz      short loc_180029767
0x180029752  mov     eax, [r8+8]
0x180029756  movsxd  r9, dword ptr [r8+4]
0x18002975a  neg     eax
0x18002975c  movsxd  rdx, eax
0x18002975f  add     r9, r10
0x180029762  and     r9, rdx
0x180029765  jmp     short loc_18002976A
0x180029767  mov     r9, r10
0x18002976a  movsxd  rax, ecx
0x18002976d  mov     rdx, [rax+r9]
0x180029771  mov     rax, [r11+10h]
0x180029775  mov     ecx, [rax+8]
0x180029778  mov     rax, [r11+8]
0x18002977c  test    byte ptr [rcx+rax+3], 0Fh
0x180029781  jz      short loc_180029795
0x180029783  movzx   eax, byte ptr [rcx+rax+3]
0x180029788  mov     ecx, 0FFFFFFF0h
0x18002978d  and     rax, rcx
0x180029790  add     rax, r10
0x180029793  jmp     short loc_180029798
0x180029795  mov     rax, r10
0x180029798  xor     rdx, rax
0x18002979b  mov     rcx, rdx; StackCookie
0x18002979e  jmp     __security_check_cookie
```
