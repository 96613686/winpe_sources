# __GSHandlerCheckCommon

- ea: `0x1800068e0`
- end: `0x180006943`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800068bc`

## callees

- `0x1800068e0`
- `0x180006980`

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
0x1800068e0  mov     r10, rcx
0x1800068e3  mov     r11, rdx
0x1800068e6  mov     ecx, [r8]
0x1800068e9  and     ecx, 0FFFFFFF8h
0x1800068ec  test    byte ptr [r8], 4
0x1800068f0  jz      short loc_180006907
0x1800068f2  mov     eax, [r8+8]
0x1800068f6  movsxd  r9, dword ptr [r8+4]
0x1800068fa  neg     eax
0x1800068fc  movsxd  rdx, eax
0x1800068ff  add     r9, r10
0x180006902  and     r9, rdx
0x180006905  jmp     short loc_18000690A
0x180006907  mov     r9, r10
0x18000690a  movsxd  rax, ecx
0x18000690d  mov     rdx, [rax+r9]
0x180006911  mov     rax, [r11+10h]
0x180006915  mov     ecx, [rax+8]
0x180006918  mov     rax, [r11+8]
0x18000691c  test    byte ptr [rcx+rax+3], 0Fh
0x180006921  jz      short loc_180006935
0x180006923  movzx   eax, byte ptr [rcx+rax+3]
0x180006928  mov     ecx, 0FFFFFFF0h
0x18000692d  and     rax, rcx
0x180006930  add     rax, r10
0x180006933  jmp     short loc_180006938
0x180006935  mov     rax, r10
0x180006938  xor     rdx, rax
0x18000693b  mov     rcx, rdx; StackCookie
0x18000693e  jmp     __security_check_cookie
```
