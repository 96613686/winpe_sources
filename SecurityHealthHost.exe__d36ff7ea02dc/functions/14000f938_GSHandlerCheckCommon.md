# __GSHandlerCheckCommon

- ea: `0x14000f938`
- end: `0x14000f99b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f914`
- `0x14000f9a4`

## callees

- `0x1400015f0`
- `0x14000f938`

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
0x14000f938  mov     r10, rcx
0x14000f93b  mov     r11, rdx
0x14000f93e  mov     ecx, [r8]
0x14000f941  and     ecx, 0FFFFFFF8h
0x14000f944  test    byte ptr [r8], 4
0x14000f948  jz      short loc_14000F95F
0x14000f94a  mov     eax, [r8+8]
0x14000f94e  movsxd  r9, dword ptr [r8+4]
0x14000f952  neg     eax
0x14000f954  movsxd  rdx, eax
0x14000f957  add     r9, r10
0x14000f95a  and     r9, rdx
0x14000f95d  jmp     short loc_14000F962
0x14000f95f  mov     r9, r10
0x14000f962  movsxd  rax, ecx
0x14000f965  mov     rdx, [rax+r9]
0x14000f969  mov     rax, [r11+10h]
0x14000f96d  mov     ecx, [rax+8]
0x14000f970  mov     rax, [r11+8]
0x14000f974  test    byte ptr [rcx+rax+3], 0Fh
0x14000f979  jz      short loc_14000F98D
0x14000f97b  movzx   eax, byte ptr [rcx+rax+3]
0x14000f980  mov     ecx, 0FFFFFFF0h
0x14000f985  and     rax, rcx
0x14000f988  add     rax, r10
0x14000f98b  jmp     short loc_14000F990
0x14000f98d  mov     rax, r10
0x14000f990  xor     rdx, rax
0x14000f993  mov     rcx, rdx; StackCookie
0x14000f996  jmp     __security_check_cookie
```
