# __GSHandlerCheckCommon

- ea: `0x1800106ac`
- end: `0x18001070f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010688`
- `0x180010718`

## callees

- `0x1800106ac`
- `0x1800107c0`

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
0x1800106ac  mov     r10, rcx
0x1800106af  mov     r11, rdx
0x1800106b2  mov     ecx, [r8]
0x1800106b5  and     ecx, 0FFFFFFF8h
0x1800106b8  test    byte ptr [r8], 4
0x1800106bc  jz      short loc_1800106D3
0x1800106be  mov     eax, [r8+8]
0x1800106c2  movsxd  r9, dword ptr [r8+4]
0x1800106c6  neg     eax
0x1800106c8  movsxd  rdx, eax
0x1800106cb  add     r9, r10
0x1800106ce  and     r9, rdx
0x1800106d1  jmp     short loc_1800106D6
0x1800106d3  mov     r9, r10
0x1800106d6  movsxd  rax, ecx
0x1800106d9  mov     rdx, [rax+r9]
0x1800106dd  mov     rax, [r11+10h]
0x1800106e1  mov     ecx, [rax+8]
0x1800106e4  mov     rax, [r11+8]
0x1800106e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800106ed  jz      short loc_180010701
0x1800106ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800106f4  mov     ecx, 0FFFFFFF0h
0x1800106f9  and     rax, rcx
0x1800106fc  add     rax, r10
0x1800106ff  jmp     short loc_180010704
0x180010701  mov     rax, r10
0x180010704  xor     rdx, rax
0x180010707  mov     rcx, rdx; StackCookie
0x18001070a  jmp     __security_check_cookie
```
