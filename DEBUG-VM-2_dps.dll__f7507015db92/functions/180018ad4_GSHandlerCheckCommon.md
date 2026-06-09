# __GSHandlerCheckCommon

- ea: `0x180018ad4`
- end: `0x180018b37`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018ab0`

## callees

- `0x180009fb0`
- `0x180018ad4`

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
0x180018ad4  mov     r10, rcx
0x180018ad7  mov     r11, rdx
0x180018ada  mov     ecx, [r8]
0x180018add  and     ecx, 0FFFFFFF8h
0x180018ae0  test    byte ptr [r8], 4
0x180018ae4  jz      short loc_180018AFB
0x180018ae6  mov     eax, [r8+8]
0x180018aea  movsxd  r9, dword ptr [r8+4]
0x180018aee  neg     eax
0x180018af0  movsxd  rdx, eax
0x180018af3  add     r9, r10
0x180018af6  and     r9, rdx
0x180018af9  jmp     short loc_180018AFE
0x180018afb  mov     r9, r10
0x180018afe  movsxd  rax, ecx
0x180018b01  mov     rdx, [rax+r9]
0x180018b05  mov     rax, [r11+10h]
0x180018b09  mov     ecx, [rax+8]
0x180018b0c  mov     rax, [r11+8]
0x180018b10  test    byte ptr [rcx+rax+3], 0Fh
0x180018b15  jz      short loc_180018B29
0x180018b17  movzx   eax, byte ptr [rcx+rax+3]
0x180018b1c  mov     ecx, 0FFFFFFF0h
0x180018b21  and     rax, rcx
0x180018b24  add     rax, r10
0x180018b27  jmp     short loc_180018B2C
0x180018b29  mov     rax, r10
0x180018b2c  xor     rdx, rax
0x180018b2f  mov     rcx, rdx; StackCookie
0x180018b32  jmp     __security_check_cookie
```
