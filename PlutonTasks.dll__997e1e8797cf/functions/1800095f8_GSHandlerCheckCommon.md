# __GSHandlerCheckCommon

- ea: `0x1800095f8`
- end: `0x18000965b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800095d4`
- `0x180009664`

## callees

- `0x180001e00`
- `0x1800095f8`

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
0x1800095f8  mov     r10, rcx
0x1800095fb  mov     r11, rdx
0x1800095fe  mov     ecx, [r8]
0x180009601  and     ecx, 0FFFFFFF8h
0x180009604  test    byte ptr [r8], 4
0x180009608  jz      short loc_18000961F
0x18000960a  mov     eax, [r8+8]
0x18000960e  movsxd  r9, dword ptr [r8+4]
0x180009612  neg     eax
0x180009614  movsxd  rdx, eax
0x180009617  add     r9, r10
0x18000961a  and     r9, rdx
0x18000961d  jmp     short loc_180009622
0x18000961f  mov     r9, r10
0x180009622  movsxd  rax, ecx
0x180009625  mov     rdx, [rax+r9]
0x180009629  mov     rax, [r11+10h]
0x18000962d  mov     ecx, [rax+8]
0x180009630  mov     rax, [r11+8]
0x180009634  test    byte ptr [rcx+rax+3], 0Fh
0x180009639  jz      short loc_18000964D
0x18000963b  movzx   eax, byte ptr [rcx+rax+3]
0x180009640  mov     ecx, 0FFFFFFF0h
0x180009645  and     rax, rcx
0x180009648  add     rax, r10
0x18000964b  jmp     short loc_180009650
0x18000964d  mov     rax, r10
0x180009650  xor     rdx, rax
0x180009653  mov     rcx, rdx; StackCookie
0x180009656  jmp     __security_check_cookie
```
