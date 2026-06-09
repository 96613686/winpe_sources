# __GSHandlerCheckCommon

- ea: `0x1800025ac`
- end: `0x18000260f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002588`

## callees

- `0x1800025ac`
- `0x180002650`

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
0x1800025ac  mov     r10, rcx
0x1800025af  mov     r11, rdx
0x1800025b2  mov     ecx, [r8]
0x1800025b5  and     ecx, 0FFFFFFF8h
0x1800025b8  test    byte ptr [r8], 4
0x1800025bc  jz      short loc_1800025D3
0x1800025be  mov     eax, [r8+8]
0x1800025c2  movsxd  r9, dword ptr [r8+4]
0x1800025c6  neg     eax
0x1800025c8  movsxd  rdx, eax
0x1800025cb  add     r9, r10
0x1800025ce  and     r9, rdx
0x1800025d1  jmp     short loc_1800025D6
0x1800025d3  mov     r9, r10
0x1800025d6  movsxd  rax, ecx
0x1800025d9  mov     rdx, [rax+r9]
0x1800025dd  mov     rax, [r11+10h]
0x1800025e1  mov     ecx, [rax+8]
0x1800025e4  mov     rax, [r11+8]
0x1800025e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800025ed  jz      short loc_180002601
0x1800025ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800025f4  mov     ecx, 0FFFFFFF0h
0x1800025f9  and     rax, rcx
0x1800025fc  add     rax, r10
0x1800025ff  jmp     short loc_180002604
0x180002601  mov     rax, r10
0x180002604  xor     rdx, rax
0x180002607  mov     rcx, rdx; StackCookie
0x18000260a  jmp     __security_check_cookie
```
