# __GSHandlerCheckCommon

- ea: `0x18000f410`
- end: `0x18000f473`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f3ec`
- `0x18000f47c`

## callees

- `0x180001760`
- `0x18000f410`

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
0x18000f410  mov     r10, rcx
0x18000f413  mov     r11, rdx
0x18000f416  mov     ecx, [r8]
0x18000f419  and     ecx, 0FFFFFFF8h
0x18000f41c  test    byte ptr [r8], 4
0x18000f420  jz      short loc_18000F437
0x18000f422  mov     eax, [r8+8]
0x18000f426  movsxd  r9, dword ptr [r8+4]
0x18000f42a  neg     eax
0x18000f42c  movsxd  rdx, eax
0x18000f42f  add     r9, r10
0x18000f432  and     r9, rdx
0x18000f435  jmp     short loc_18000F43A
0x18000f437  mov     r9, r10
0x18000f43a  movsxd  rax, ecx
0x18000f43d  mov     rdx, [rax+r9]
0x18000f441  mov     rax, [r11+10h]
0x18000f445  mov     ecx, [rax+8]
0x18000f448  mov     rax, [r11+8]
0x18000f44c  test    byte ptr [rcx+rax+3], 0Fh
0x18000f451  jz      short loc_18000F465
0x18000f453  movzx   eax, byte ptr [rcx+rax+3]
0x18000f458  mov     ecx, 0FFFFFFF0h
0x18000f45d  and     rax, rcx
0x18000f460  add     rax, r10
0x18000f463  jmp     short loc_18000F468
0x18000f465  mov     rax, r10
0x18000f468  xor     rdx, rax
0x18000f46b  mov     rcx, rdx; StackCookie
0x18000f46e  jmp     __security_check_cookie
```
