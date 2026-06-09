# __GSHandlerCheckCommon

- ea: `0x180046ed4`
- end: `0x180046f37`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046eb0`
- `0x1800845bc`

## callees

- `0x18000ab90`
- `0x180046ed4`

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
0x180046ed4  mov     r10, rcx
0x180046ed7  mov     r11, rdx
0x180046eda  mov     ecx, [r8]
0x180046edd  and     ecx, 0FFFFFFF8h
0x180046ee0  test    byte ptr [r8], 4
0x180046ee4  jz      short loc_180046EFB
0x180046ee6  mov     eax, [r8+8]
0x180046eea  movsxd  r9, dword ptr [r8+4]
0x180046eee  neg     eax
0x180046ef0  movsxd  rdx, eax
0x180046ef3  add     r9, r10
0x180046ef6  and     r9, rdx
0x180046ef9  jmp     short loc_180046EFE
0x180046efb  mov     r9, r10
0x180046efe  movsxd  rax, ecx
0x180046f01  mov     rdx, [rax+r9]
0x180046f05  mov     rax, [r11+10h]
0x180046f09  mov     ecx, [rax+8]
0x180046f0c  mov     rax, [r11+8]
0x180046f10  test    byte ptr [rcx+rax+3], 0Fh
0x180046f15  jz      short loc_180046F29
0x180046f17  movzx   eax, byte ptr [rcx+rax+3]
0x180046f1c  mov     ecx, 0FFFFFFF0h
0x180046f21  and     rax, rcx
0x180046f24  add     rax, r10
0x180046f27  jmp     short loc_180046F2C
0x180046f29  mov     rax, r10
0x180046f2c  xor     rdx, rax
0x180046f2f  mov     rcx, rdx; StackCookie
0x180046f32  jmp     __security_check_cookie
```
