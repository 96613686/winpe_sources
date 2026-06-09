# __GSHandlerCheckCommon

- ea: `0x1800095fc`
- end: `0x18000965f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800095d8`

## callees

- `0x1800095fc`
- `0x1800096b0`

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
0x1800095fc  mov     r10, rcx
0x1800095ff  mov     r11, rdx
0x180009602  mov     ecx, [r8]
0x180009605  and     ecx, 0FFFFFFF8h
0x180009608  test    byte ptr [r8], 4
0x18000960c  jz      short loc_180009623
0x18000960e  mov     eax, [r8+8]
0x180009612  movsxd  r9, dword ptr [r8+4]
0x180009616  neg     eax
0x180009618  movsxd  rdx, eax
0x18000961b  add     r9, r10
0x18000961e  and     r9, rdx
0x180009621  jmp     short loc_180009626
0x180009623  mov     r9, r10
0x180009626  movsxd  rax, ecx
0x180009629  mov     rdx, [rax+r9]
0x18000962d  mov     rax, [r11+10h]
0x180009631  mov     ecx, [rax+8]
0x180009634  mov     rax, [r11+8]
0x180009638  test    byte ptr [rcx+rax+3], 0Fh
0x18000963d  jz      short loc_180009651
0x18000963f  movzx   eax, byte ptr [rcx+rax+3]
0x180009644  mov     ecx, 0FFFFFFF0h
0x180009649  and     rax, rcx
0x18000964c  add     rax, r10
0x18000964f  jmp     short loc_180009654
0x180009651  mov     rax, r10
0x180009654  xor     rdx, rax
0x180009657  mov     rcx, rdx; StackCookie
0x18000965a  jmp     __security_check_cookie
```
