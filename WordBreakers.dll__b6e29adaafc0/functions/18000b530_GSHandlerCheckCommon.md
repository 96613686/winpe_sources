# __GSHandlerCheckCommon

- ea: `0x18000b530`
- end: `0x18000b593`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b50c`
- `0x18000b59c`

## callees

- `0x18000b530`
- `0x18000b640`

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
0x18000b530  mov     r10, rcx
0x18000b533  mov     r11, rdx
0x18000b536  mov     ecx, [r8]
0x18000b539  and     ecx, 0FFFFFFF8h
0x18000b53c  test    byte ptr [r8], 4
0x18000b540  jz      short loc_18000B557
0x18000b542  mov     eax, [r8+8]
0x18000b546  movsxd  r9, dword ptr [r8+4]
0x18000b54a  neg     eax
0x18000b54c  movsxd  rdx, eax
0x18000b54f  add     r9, r10
0x18000b552  and     r9, rdx
0x18000b555  jmp     short loc_18000B55A
0x18000b557  mov     r9, r10
0x18000b55a  movsxd  rax, ecx
0x18000b55d  mov     rdx, [rax+r9]
0x18000b561  mov     rax, [r11+10h]
0x18000b565  mov     ecx, [rax+8]
0x18000b568  mov     rax, [r11+8]
0x18000b56c  test    byte ptr [rcx+rax+3], 0Fh
0x18000b571  jz      short loc_18000B585
0x18000b573  movzx   eax, byte ptr [rcx+rax+3]
0x18000b578  mov     ecx, 0FFFFFFF0h
0x18000b57d  and     rax, rcx
0x18000b580  add     rax, r10
0x18000b583  jmp     short loc_18000B588
0x18000b585  mov     rax, r10
0x18000b588  xor     rdx, rax
0x18000b58b  mov     rcx, rdx; StackCookie
0x18000b58e  jmp     __security_check_cookie
```
