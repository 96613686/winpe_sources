# __GSHandlerCheckCommon

- ea: `0x180021740`
- end: `0x1800217a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002171c`
- `0x1800217ac`

## callees

- `0x180021740`
- `0x180021850`

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
0x180021740  mov     r10, rcx
0x180021743  mov     r11, rdx
0x180021746  mov     ecx, [r8]
0x180021749  and     ecx, 0FFFFFFF8h
0x18002174c  test    byte ptr [r8], 4
0x180021750  jz      short loc_180021767
0x180021752  mov     eax, [r8+8]
0x180021756  movsxd  r9, dword ptr [r8+4]
0x18002175a  neg     eax
0x18002175c  movsxd  rdx, eax
0x18002175f  add     r9, r10
0x180021762  and     r9, rdx
0x180021765  jmp     short loc_18002176A
0x180021767  mov     r9, r10
0x18002176a  movsxd  rax, ecx
0x18002176d  mov     rdx, [rax+r9]
0x180021771  mov     rax, [r11+10h]
0x180021775  mov     ecx, [rax+8]
0x180021778  mov     rax, [r11+8]
0x18002177c  test    byte ptr [rcx+rax+3], 0Fh
0x180021781  jz      short loc_180021795
0x180021783  movzx   eax, byte ptr [rcx+rax+3]
0x180021788  mov     ecx, 0FFFFFFF0h
0x18002178d  and     rax, rcx
0x180021790  add     rax, r10
0x180021793  jmp     short loc_180021798
0x180021795  mov     rax, r10
0x180021798  xor     rdx, rax
0x18002179b  mov     rcx, rdx; StackCookie
0x18002179e  jmp     __security_check_cookie
```
