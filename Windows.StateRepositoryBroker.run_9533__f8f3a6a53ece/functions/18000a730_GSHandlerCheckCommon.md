# __GSHandlerCheckCommon

- ea: `0x18000a730`
- end: `0x18000a793`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a70c`
- `0x18000a79c`

## callees

- `0x180001d60`
- `0x18000a730`

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
0x18000a730  mov     r10, rcx
0x18000a733  mov     r11, rdx
0x18000a736  mov     ecx, [r8]
0x18000a739  and     ecx, 0FFFFFFF8h
0x18000a73c  test    byte ptr [r8], 4
0x18000a740  jz      short loc_18000A757
0x18000a742  mov     eax, [r8+8]
0x18000a746  movsxd  r9, dword ptr [r8+4]
0x18000a74a  neg     eax
0x18000a74c  movsxd  rdx, eax
0x18000a74f  add     r9, r10
0x18000a752  and     r9, rdx
0x18000a755  jmp     short loc_18000A75A
0x18000a757  mov     r9, r10
0x18000a75a  movsxd  rax, ecx
0x18000a75d  mov     rdx, [rax+r9]
0x18000a761  mov     rax, [r11+10h]
0x18000a765  mov     ecx, [rax+8]
0x18000a768  mov     rax, [r11+8]
0x18000a76c  test    byte ptr [rcx+rax+3], 0Fh
0x18000a771  jz      short loc_18000A785
0x18000a773  movzx   eax, byte ptr [rcx+rax+3]
0x18000a778  mov     ecx, 0FFFFFFF0h
0x18000a77d  and     rax, rcx
0x18000a780  add     rax, r10
0x18000a783  jmp     short loc_18000A788
0x18000a785  mov     rax, r10
0x18000a788  xor     rdx, rax
0x18000a78b  mov     rcx, rdx; StackCookie
0x18000a78e  jmp     __security_check_cookie
```
