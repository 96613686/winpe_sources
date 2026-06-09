# __GSHandlerCheckCommon

- ea: `0x18000da2c`
- end: `0x18000da8f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000da08`
- `0x18000da98`

## callees

- `0x18000da2c`
- `0x18000db40`

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
0x18000da2c  mov     r10, rcx
0x18000da2f  mov     r11, rdx
0x18000da32  mov     ecx, [r8]
0x18000da35  and     ecx, 0FFFFFFF8h
0x18000da38  test    byte ptr [r8], 4
0x18000da3c  jz      short loc_18000DA53
0x18000da3e  mov     eax, [r8+8]
0x18000da42  movsxd  r9, dword ptr [r8+4]
0x18000da46  neg     eax
0x18000da48  movsxd  rdx, eax
0x18000da4b  add     r9, r10
0x18000da4e  and     r9, rdx
0x18000da51  jmp     short loc_18000DA56
0x18000da53  mov     r9, r10
0x18000da56  movsxd  rax, ecx
0x18000da59  mov     rdx, [rax+r9]
0x18000da5d  mov     rax, [r11+10h]
0x18000da61  mov     ecx, [rax+8]
0x18000da64  mov     rax, [r11+8]
0x18000da68  test    byte ptr [rcx+rax+3], 0Fh
0x18000da6d  jz      short loc_18000DA81
0x18000da6f  movzx   eax, byte ptr [rcx+rax+3]
0x18000da74  mov     ecx, 0FFFFFFF0h
0x18000da79  and     rax, rcx
0x18000da7c  add     rax, r10
0x18000da7f  jmp     short loc_18000DA84
0x18000da81  mov     rax, r10
0x18000da84  xor     rdx, rax
0x18000da87  mov     rcx, rdx; StackCookie
0x18000da8a  jmp     __security_check_cookie
```
