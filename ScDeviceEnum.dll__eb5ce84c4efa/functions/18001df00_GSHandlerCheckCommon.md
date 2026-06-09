# __GSHandlerCheckCommon

- ea: `0x18001df00`
- end: `0x18001df63`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dedc`
- `0x18001df6c`

## callees

- `0x18001df00`
- `0x18001e020`

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
0x18001df00  mov     r10, rcx
0x18001df03  mov     r11, rdx
0x18001df06  mov     ecx, [r8]
0x18001df09  and     ecx, 0FFFFFFF8h
0x18001df0c  test    byte ptr [r8], 4
0x18001df10  jz      short loc_18001DF27
0x18001df12  mov     eax, [r8+8]
0x18001df16  movsxd  r9, dword ptr [r8+4]
0x18001df1a  neg     eax
0x18001df1c  movsxd  rdx, eax
0x18001df1f  add     r9, r10
0x18001df22  and     r9, rdx
0x18001df25  jmp     short loc_18001DF2A
0x18001df27  mov     r9, r10
0x18001df2a  movsxd  rax, ecx
0x18001df2d  mov     rdx, [rax+r9]
0x18001df31  mov     rax, [r11+10h]
0x18001df35  mov     ecx, [rax+8]
0x18001df38  mov     rax, [r11+8]
0x18001df3c  test    byte ptr [rcx+rax+3], 0Fh
0x18001df41  jz      short loc_18001DF55
0x18001df43  movzx   eax, byte ptr [rcx+rax+3]
0x18001df48  mov     ecx, 0FFFFFFF0h
0x18001df4d  and     rax, rcx
0x18001df50  add     rax, r10
0x18001df53  jmp     short loc_18001DF58
0x18001df55  mov     rax, r10
0x18001df58  xor     rdx, rax
0x18001df5b  mov     rcx, rdx; StackCookie
0x18001df5e  jmp     __security_check_cookie
```
