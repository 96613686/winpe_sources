# __GSHandlerCheckCommon

- ea: `0x18000b2ac`
- end: `0x18000b30f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b288`
- `0x18000b318`

## callees

- `0x180001e60`
- `0x18000b2ac`

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
0x18000b2ac  mov     r10, rcx
0x18000b2af  mov     r11, rdx
0x18000b2b2  mov     ecx, [r8]
0x18000b2b5  and     ecx, 0FFFFFFF8h
0x18000b2b8  test    byte ptr [r8], 4
0x18000b2bc  jz      short loc_18000B2D3
0x18000b2be  mov     eax, [r8+8]
0x18000b2c2  movsxd  r9, dword ptr [r8+4]
0x18000b2c6  neg     eax
0x18000b2c8  movsxd  rdx, eax
0x18000b2cb  add     r9, r10
0x18000b2ce  and     r9, rdx
0x18000b2d1  jmp     short loc_18000B2D6
0x18000b2d3  mov     r9, r10
0x18000b2d6  movsxd  rax, ecx
0x18000b2d9  mov     rdx, [rax+r9]
0x18000b2dd  mov     rax, [r11+10h]
0x18000b2e1  mov     ecx, [rax+8]
0x18000b2e4  mov     rax, [r11+8]
0x18000b2e8  test    byte ptr [rcx+rax+3], 0Fh
0x18000b2ed  jz      short loc_18000B301
0x18000b2ef  movzx   eax, byte ptr [rcx+rax+3]
0x18000b2f4  mov     ecx, 0FFFFFFF0h
0x18000b2f9  and     rax, rcx
0x18000b2fc  add     rax, r10
0x18000b2ff  jmp     short loc_18000B304
0x18000b301  mov     rax, r10
0x18000b304  xor     rdx, rax
0x18000b307  mov     rcx, rdx; StackCookie
0x18000b30a  jmp     __security_check_cookie
```
