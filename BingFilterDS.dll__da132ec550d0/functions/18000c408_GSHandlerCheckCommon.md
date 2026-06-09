# __GSHandlerCheckCommon

- ea: `0x18000c408`
- end: `0x18000c46b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c3e4`
- `0x18000c474`

## callees

- `0x18000c408`
- `0x18000c530`

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
0x18000c408  mov     r10, rcx
0x18000c40b  mov     r11, rdx
0x18000c40e  mov     ecx, [r8]
0x18000c411  and     ecx, 0FFFFFFF8h
0x18000c414  test    byte ptr [r8], 4
0x18000c418  jz      short loc_18000C42F
0x18000c41a  mov     eax, [r8+8]
0x18000c41e  movsxd  r9, dword ptr [r8+4]
0x18000c422  neg     eax
0x18000c424  movsxd  rdx, eax
0x18000c427  add     r9, r10
0x18000c42a  and     r9, rdx
0x18000c42d  jmp     short loc_18000C432
0x18000c42f  mov     r9, r10
0x18000c432  movsxd  rax, ecx
0x18000c435  mov     rdx, [rax+r9]
0x18000c439  mov     rax, [r11+10h]
0x18000c43d  mov     ecx, [rax+8]
0x18000c440  mov     rax, [r11+8]
0x18000c444  test    byte ptr [rcx+rax+3], 0Fh
0x18000c449  jz      short loc_18000C45D
0x18000c44b  movzx   eax, byte ptr [rcx+rax+3]
0x18000c450  mov     ecx, 0FFFFFFF0h
0x18000c455  and     rax, rcx
0x18000c458  add     rax, r10
0x18000c45b  jmp     short loc_18000C460
0x18000c45d  mov     rax, r10
0x18000c460  xor     rdx, rax
0x18000c463  mov     rcx, rdx; StackCookie
0x18000c466  jmp     __security_check_cookie
```
