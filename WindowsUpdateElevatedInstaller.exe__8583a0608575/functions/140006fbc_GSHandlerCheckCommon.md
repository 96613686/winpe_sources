# __GSHandlerCheckCommon

- ea: `0x140006fbc`
- end: `0x14000701f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006f98`
- `0x140007028`

## callees

- `0x140001480`
- `0x140006fbc`

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
0x140006fbc  mov     r10, rcx
0x140006fbf  mov     r11, rdx
0x140006fc2  mov     ecx, [r8]
0x140006fc5  and     ecx, 0FFFFFFF8h
0x140006fc8  test    byte ptr [r8], 4
0x140006fcc  jz      short loc_140006FE3
0x140006fce  mov     eax, [r8+8]
0x140006fd2  movsxd  r9, dword ptr [r8+4]
0x140006fd6  neg     eax
0x140006fd8  movsxd  rdx, eax
0x140006fdb  add     r9, r10
0x140006fde  and     r9, rdx
0x140006fe1  jmp     short loc_140006FE6
0x140006fe3  mov     r9, r10
0x140006fe6  movsxd  rax, ecx
0x140006fe9  mov     rdx, [rax+r9]
0x140006fed  mov     rax, [r11+10h]
0x140006ff1  mov     ecx, [rax+8]
0x140006ff4  mov     rax, [r11+8]
0x140006ff8  test    byte ptr [rcx+rax+3], 0Fh
0x140006ffd  jz      short loc_140007011
0x140006fff  movzx   eax, byte ptr [rcx+rax+3]
0x140007004  mov     ecx, 0FFFFFFF0h
0x140007009  and     rax, rcx
0x14000700c  add     rax, r10
0x14000700f  jmp     short loc_140007014
0x140007011  mov     rax, r10
0x140007014  xor     rdx, rax
0x140007017  mov     rcx, rdx; StackCookie
0x14000701a  jmp     __security_check_cookie
```
