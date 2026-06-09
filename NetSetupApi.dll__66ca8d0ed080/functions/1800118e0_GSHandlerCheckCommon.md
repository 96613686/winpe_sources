# __GSHandlerCheckCommon

- ea: `0x1800118e0`
- end: `0x180011943`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800118bc`
- `0x18001194c`

## callees

- `0x1800118e0`
- `0x1800119f0`

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
0x1800118e0  mov     r10, rcx
0x1800118e3  mov     r11, rdx
0x1800118e6  mov     ecx, [r8]
0x1800118e9  and     ecx, 0FFFFFFF8h
0x1800118ec  test    byte ptr [r8], 4
0x1800118f0  jz      short loc_180011907
0x1800118f2  mov     eax, [r8+8]
0x1800118f6  movsxd  r9, dword ptr [r8+4]
0x1800118fa  neg     eax
0x1800118fc  movsxd  rdx, eax
0x1800118ff  add     r9, r10
0x180011902  and     r9, rdx
0x180011905  jmp     short loc_18001190A
0x180011907  mov     r9, r10
0x18001190a  movsxd  rax, ecx
0x18001190d  mov     rdx, [rax+r9]
0x180011911  mov     rax, [r11+10h]
0x180011915  mov     ecx, [rax+8]
0x180011918  mov     rax, [r11+8]
0x18001191c  test    byte ptr [rcx+rax+3], 0Fh
0x180011921  jz      short loc_180011935
0x180011923  movzx   eax, byte ptr [rcx+rax+3]
0x180011928  mov     ecx, 0FFFFFFF0h
0x18001192d  and     rax, rcx
0x180011930  add     rax, r10
0x180011933  jmp     short loc_180011938
0x180011935  mov     rax, r10
0x180011938  xor     rdx, rax
0x18001193b  mov     rcx, rdx; StackCookie
0x18001193e  jmp     __security_check_cookie
```
