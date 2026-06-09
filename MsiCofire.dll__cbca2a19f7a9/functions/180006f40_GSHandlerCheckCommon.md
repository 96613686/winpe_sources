# __GSHandlerCheckCommon

- ea: `0x180006f40`
- end: `0x180006fa3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006f1c`
- `0x180006fac`

## callees

- `0x180006f40`
- `0x180007040`

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
0x180006f40  mov     r10, rcx
0x180006f43  mov     r11, rdx
0x180006f46  mov     ecx, [r8]
0x180006f49  and     ecx, 0FFFFFFF8h
0x180006f4c  test    byte ptr [r8], 4
0x180006f50  jz      short loc_180006F67
0x180006f52  mov     eax, [r8+8]
0x180006f56  movsxd  r9, dword ptr [r8+4]
0x180006f5a  neg     eax
0x180006f5c  movsxd  rdx, eax
0x180006f5f  add     r9, r10
0x180006f62  and     r9, rdx
0x180006f65  jmp     short loc_180006F6A
0x180006f67  mov     r9, r10
0x180006f6a  movsxd  rax, ecx
0x180006f6d  mov     rdx, [rax+r9]
0x180006f71  mov     rax, [r11+10h]
0x180006f75  mov     ecx, [rax+8]
0x180006f78  mov     rax, [r11+8]
0x180006f7c  test    byte ptr [rcx+rax+3], 0Fh
0x180006f81  jz      short loc_180006F95
0x180006f83  movzx   eax, byte ptr [rcx+rax+3]
0x180006f88  mov     ecx, 0FFFFFFF0h
0x180006f8d  and     rax, rcx
0x180006f90  add     rax, r10
0x180006f93  jmp     short loc_180006F98
0x180006f95  mov     rax, r10
0x180006f98  xor     rdx, rax
0x180006f9b  mov     rcx, rdx; StackCookie
0x180006f9e  jmp     __security_check_cookie
```
