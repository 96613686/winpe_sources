# __GSHandlerCheckCommon

- ea: `0x1800188a4`
- end: `0x180018907`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018880`
- `0x180018910`

## callees

- `0x1800188a4`
- `0x1800189d0`

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
0x1800188a4  mov     r10, rcx
0x1800188a7  mov     r11, rdx
0x1800188aa  mov     ecx, [r8]
0x1800188ad  and     ecx, 0FFFFFFF8h
0x1800188b0  test    byte ptr [r8], 4
0x1800188b4  jz      short loc_1800188CB
0x1800188b6  mov     eax, [r8+8]
0x1800188ba  movsxd  r9, dword ptr [r8+4]
0x1800188be  neg     eax
0x1800188c0  movsxd  rdx, eax
0x1800188c3  add     r9, r10
0x1800188c6  and     r9, rdx
0x1800188c9  jmp     short loc_1800188CE
0x1800188cb  mov     r9, r10
0x1800188ce  movsxd  rax, ecx
0x1800188d1  mov     rdx, [rax+r9]
0x1800188d5  mov     rax, [r11+10h]
0x1800188d9  mov     ecx, [rax+8]
0x1800188dc  mov     rax, [r11+8]
0x1800188e0  test    byte ptr [rcx+rax+3], 0Fh
0x1800188e5  jz      short loc_1800188F9
0x1800188e7  movzx   eax, byte ptr [rcx+rax+3]
0x1800188ec  mov     ecx, 0FFFFFFF0h
0x1800188f1  and     rax, rcx
0x1800188f4  add     rax, r10
0x1800188f7  jmp     short loc_1800188FC
0x1800188f9  mov     rax, r10
0x1800188fc  xor     rdx, rax
0x1800188ff  mov     rcx, rdx; StackCookie
0x180018902  jmp     __security_check_cookie
```
