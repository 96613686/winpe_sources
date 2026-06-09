# __GSHandlerCheckCommon

- ea: `0x1400095b4`
- end: `0x140009617`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009590`
- `0x140009620`

## callees

- `0x1400095b4`
- `0x1400096d0`

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
0x1400095b4  mov     r10, rcx
0x1400095b7  mov     r11, rdx
0x1400095ba  mov     ecx, [r8]
0x1400095bd  and     ecx, 0FFFFFFF8h
0x1400095c0  test    byte ptr [r8], 4
0x1400095c4  jz      short loc_1400095DB
0x1400095c6  mov     eax, [r8+8]
0x1400095ca  movsxd  r9, dword ptr [r8+4]
0x1400095ce  neg     eax
0x1400095d0  movsxd  rdx, eax
0x1400095d3  add     r9, r10
0x1400095d6  and     r9, rdx
0x1400095d9  jmp     short loc_1400095DE
0x1400095db  mov     r9, r10
0x1400095de  movsxd  rax, ecx
0x1400095e1  mov     rdx, [rax+r9]
0x1400095e5  mov     rax, [r11+10h]
0x1400095e9  mov     ecx, [rax+8]
0x1400095ec  mov     rax, [r11+8]
0x1400095f0  test    byte ptr [rcx+rax+3], 0Fh
0x1400095f5  jz      short loc_140009609
0x1400095f7  movzx   eax, byte ptr [rcx+rax+3]
0x1400095fc  mov     ecx, 0FFFFFFF0h
0x140009601  and     rax, rcx
0x140009604  add     rax, r10
0x140009607  jmp     short loc_14000960C
0x140009609  mov     rax, r10
0x14000960c  xor     rdx, rax
0x14000960f  mov     rcx, rdx; StackCookie
0x140009612  jmp     __security_check_cookie
```
