# __GSHandlerCheckCommon

- ea: `0x180003ad4`
- end: `0x180003b37`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ab0`

## callees

- `0x180001730`
- `0x180003ad4`

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
0x180003ad4  mov     r10, rcx
0x180003ad7  mov     r11, rdx
0x180003ada  mov     ecx, [r8]
0x180003add  and     ecx, 0FFFFFFF8h
0x180003ae0  test    byte ptr [r8], 4
0x180003ae4  jz      short loc_180003AFB
0x180003ae6  mov     eax, [r8+8]
0x180003aea  movsxd  r9, dword ptr [r8+4]
0x180003aee  neg     eax
0x180003af0  movsxd  rdx, eax
0x180003af3  add     r9, r10
0x180003af6  and     r9, rdx
0x180003af9  jmp     short loc_180003AFE
0x180003afb  mov     r9, r10
0x180003afe  movsxd  rax, ecx
0x180003b01  mov     rdx, [rax+r9]
0x180003b05  mov     rax, [r11+10h]
0x180003b09  mov     ecx, [rax+8]
0x180003b0c  mov     rax, [r11+8]
0x180003b10  test    byte ptr [rcx+rax+3], 0Fh
0x180003b15  jz      short loc_180003B29
0x180003b17  movzx   eax, byte ptr [rcx+rax+3]
0x180003b1c  mov     ecx, 0FFFFFFF0h
0x180003b21  and     rax, rcx
0x180003b24  add     rax, r10
0x180003b27  jmp     short loc_180003B2C
0x180003b29  mov     rax, r10
0x180003b2c  xor     rdx, rax
0x180003b2f  mov     rcx, rdx; StackCookie
0x180003b32  jmp     __security_check_cookie
```
