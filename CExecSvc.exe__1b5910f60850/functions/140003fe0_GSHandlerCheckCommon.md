# __GSHandlerCheckCommon

- ea: `0x140003fe0`
- end: `0x140004043`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003fbc`
- `0x140021f14`

## callees

- `0x140002310`
- `0x140003fe0`

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
0x140003fe0  mov     r10, rcx
0x140003fe3  mov     r11, rdx
0x140003fe6  mov     ecx, [r8]
0x140003fe9  and     ecx, 0FFFFFFF8h
0x140003fec  test    byte ptr [r8], 4
0x140003ff0  jz      short loc_140004007
0x140003ff2  mov     eax, [r8+8]
0x140003ff6  movsxd  r9, dword ptr [r8+4]
0x140003ffa  neg     eax
0x140003ffc  movsxd  rdx, eax
0x140003fff  add     r9, r10
0x140004002  and     r9, rdx
0x140004005  jmp     short loc_14000400A
0x140004007  mov     r9, r10
0x14000400a  movsxd  rax, ecx
0x14000400d  mov     rdx, [rax+r9]
0x140004011  mov     rax, [r11+10h]
0x140004015  mov     ecx, [rax+8]
0x140004018  mov     rax, [r11+8]
0x14000401c  test    byte ptr [rcx+rax+3], 0Fh
0x140004021  jz      short loc_140004035
0x140004023  movzx   eax, byte ptr [rcx+rax+3]
0x140004028  mov     ecx, 0FFFFFFF0h
0x14000402d  and     rax, rcx
0x140004030  add     rax, r10
0x140004033  jmp     short loc_140004038
0x140004035  mov     rax, r10
0x140004038  xor     rdx, rax
0x14000403b  mov     rcx, rdx; StackCookie
0x14000403e  jmp     __security_check_cookie
```
