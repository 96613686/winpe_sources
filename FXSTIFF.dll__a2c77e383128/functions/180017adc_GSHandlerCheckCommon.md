# __GSHandlerCheckCommon

- ea: `0x180017adc`
- end: `0x180017b3f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017ab8`
- `0x180017b48`

## callees

- `0x180017adc`
- `0x180017c00`

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
0x180017adc  mov     r10, rcx
0x180017adf  mov     r11, rdx
0x180017ae2  mov     ecx, [r8]
0x180017ae5  and     ecx, 0FFFFFFF8h
0x180017ae8  test    byte ptr [r8], 4
0x180017aec  jz      short loc_180017B03
0x180017aee  mov     eax, [r8+8]
0x180017af2  movsxd  r9, dword ptr [r8+4]
0x180017af6  neg     eax
0x180017af8  movsxd  rdx, eax
0x180017afb  add     r9, r10
0x180017afe  and     r9, rdx
0x180017b01  jmp     short loc_180017B06
0x180017b03  mov     r9, r10
0x180017b06  movsxd  rax, ecx
0x180017b09  mov     rdx, [rax+r9]
0x180017b0d  mov     rax, [r11+10h]
0x180017b11  mov     ecx, [rax+8]
0x180017b14  mov     rax, [r11+8]
0x180017b18  test    byte ptr [rcx+rax+3], 0Fh
0x180017b1d  jz      short loc_180017B31
0x180017b1f  movzx   eax, byte ptr [rcx+rax+3]
0x180017b24  mov     ecx, 0FFFFFFF0h
0x180017b29  and     rax, rcx
0x180017b2c  add     rax, r10
0x180017b2f  jmp     short loc_180017B34
0x180017b31  mov     rax, r10
0x180017b34  xor     rdx, rax
0x180017b37  mov     rcx, rdx; StackCookie
0x180017b3a  jmp     __security_check_cookie
```
