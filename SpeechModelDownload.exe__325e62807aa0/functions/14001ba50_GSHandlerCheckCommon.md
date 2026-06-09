# __GSHandlerCheckCommon

- ea: `0x14001ba50`
- end: `0x14001bab3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ba2c`
- `0x14001babc`

## callees

- `0x140002600`
- `0x14001ba50`

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
0x14001ba50  mov     r10, rcx
0x14001ba53  mov     r11, rdx
0x14001ba56  mov     ecx, [r8]
0x14001ba59  and     ecx, 0FFFFFFF8h
0x14001ba5c  test    byte ptr [r8], 4
0x14001ba60  jz      short loc_14001BA77
0x14001ba62  mov     eax, [r8+8]
0x14001ba66  movsxd  r9, dword ptr [r8+4]
0x14001ba6a  neg     eax
0x14001ba6c  movsxd  rdx, eax
0x14001ba6f  add     r9, r10
0x14001ba72  and     r9, rdx
0x14001ba75  jmp     short loc_14001BA7A
0x14001ba77  mov     r9, r10
0x14001ba7a  movsxd  rax, ecx
0x14001ba7d  mov     rdx, [rax+r9]
0x14001ba81  mov     rax, [r11+10h]
0x14001ba85  mov     ecx, [rax+8]
0x14001ba88  mov     rax, [r11+8]
0x14001ba8c  test    byte ptr [rcx+rax+3], 0Fh
0x14001ba91  jz      short loc_14001BAA5
0x14001ba93  movzx   eax, byte ptr [rcx+rax+3]
0x14001ba98  mov     ecx, 0FFFFFFF0h
0x14001ba9d  and     rax, rcx
0x14001baa0  add     rax, r10
0x14001baa3  jmp     short loc_14001BAA8
0x14001baa5  mov     rax, r10
0x14001baa8  xor     rdx, rax
0x14001baab  mov     rcx, rdx; StackCookie
0x14001baae  jmp     __security_check_cookie
```
