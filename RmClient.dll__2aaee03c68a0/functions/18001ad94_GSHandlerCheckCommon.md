# __GSHandlerCheckCommon

- ea: `0x18001ad94`
- end: `0x18001adf7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ad70`
- `0x18001ae00`

## callees

- `0x18001ad94`
- `0x18001aec0`

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
0x18001ad94  mov     r10, rcx
0x18001ad97  mov     r11, rdx
0x18001ad9a  mov     ecx, [r8]
0x18001ad9d  and     ecx, 0FFFFFFF8h
0x18001ada0  test    byte ptr [r8], 4
0x18001ada4  jz      short loc_18001ADBB
0x18001ada6  mov     eax, [r8+8]
0x18001adaa  movsxd  r9, dword ptr [r8+4]
0x18001adae  neg     eax
0x18001adb0  movsxd  rdx, eax
0x18001adb3  add     r9, r10
0x18001adb6  and     r9, rdx
0x18001adb9  jmp     short loc_18001ADBE
0x18001adbb  mov     r9, r10
0x18001adbe  movsxd  rax, ecx
0x18001adc1  mov     rdx, [rax+r9]
0x18001adc5  mov     rax, [r11+10h]
0x18001adc9  mov     ecx, [rax+8]
0x18001adcc  mov     rax, [r11+8]
0x18001add0  test    byte ptr [rcx+rax+3], 0Fh
0x18001add5  jz      short loc_18001ADE9
0x18001add7  movzx   eax, byte ptr [rcx+rax+3]
0x18001addc  mov     ecx, 0FFFFFFF0h
0x18001ade1  and     rax, rcx
0x18001ade4  add     rax, r10
0x18001ade7  jmp     short loc_18001ADEC
0x18001ade9  mov     rax, r10
0x18001adec  xor     rdx, rax
0x18001adef  mov     rcx, rdx; StackCookie
0x18001adf2  jmp     __security_check_cookie
```
