# __GSHandlerCheckCommon

- ea: `0x140008ac8`
- end: `0x140008b23`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008aa8`
- `0x140008b24`
- `0x140008ba4`

## callees

- `0x140007dd0`
- `0x140008ac8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rax

  v3 = a1;
  v4 = a1;
  if ( (*(_BYTE *)a3 & 4) != 0 )
    v4 = -*(_DWORD *)(a3 + 8) & (a1 + *(int *)(a3 + 4));
  v5 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v6 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v5 + v6 + 3) & 0xF) != 0 )
    v3 += *(_BYTE *)(v5 + v6 + 3) & 0xF0;
  return sub_140007DD0(*(_QWORD *)((int)(*(_DWORD *)a3 & 0xFFFFFFF8) + v4) ^ v3);
}

```

## disassembly

```asm
0x140008ac8  push    rbx
0x140008aca  mov     r11d, [r8]
0x140008acd  mov     rbx, rdx
0x140008ad0  and     r11d, 0FFFFFFF8h
0x140008ad4  mov     r9, rcx
0x140008ad7  test    byte ptr [r8], 4
0x140008adb  mov     r10, rcx
0x140008ade  jz      short loc_140008AF3
0x140008ae0  mov     eax, [r8+8]
0x140008ae4  movsxd  r10, dword ptr [r8+4]
0x140008ae8  neg     eax
0x140008aea  add     r10, rcx
0x140008aed  movsxd  rcx, eax
0x140008af0  and     r10, rcx
0x140008af3  movsxd  rax, r11d
0x140008af6  mov     rdx, [rax+r10]
0x140008afa  mov     rax, [rbx+10h]
0x140008afe  mov     ecx, [rax+8]
0x140008b01  mov     rax, [rbx+8]
0x140008b05  test    byte ptr [rcx+rax+3], 0Fh
0x140008b0a  jz      short loc_140008B17
0x140008b0c  movzx   eax, byte ptr [rcx+rax+3]
0x140008b11  and     eax, 0FFFFFFF0h
0x140008b14  add     r9, rax
0x140008b17  xor     r9, rdx
0x140008b1a  mov     rcx, r9
0x140008b1d  pop     rbx
0x140008b1e  jmp     sub_140007DD0
```
