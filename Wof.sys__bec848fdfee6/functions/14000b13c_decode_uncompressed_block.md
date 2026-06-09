# decode_uncompressed_block

- ea: `0x14000b13c`
- end: `0x14000b1e1`
- name: `decode_uncompressed_block`
- size: `165`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003254`

## callees

- `0x14000b13c`

## pseudocode

```c
__int64 __fastcall decode_uncompressed_block(__int64 a1, int a2, int a3)
{
  int v3; // ebx
  int v4; // r9d
  char *v5; // r8
  unsigned int v7; // r11d
  char v8; // al
  __int64 v9; // rdx
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx

  v3 = a2 + a3;
  v4 = a2;
  v5 = *(char **)(a1 + 11016);
  v7 = a2;
  while ( v4 < v3 )
  {
    if ( (unsigned __int64)v5 >= *(_QWORD *)(a1 + 11024) || v4 >= *(_DWORD *)(a1 + 8) + 261 )
      return 0xFFFFFFFFLL;
    v8 = *v5;
    v9 = v4++;
    ++v5;
    *(_BYTE *)(v9 + *(_QWORD *)a1) = v8;
  }
  *(_QWORD *)(a1 + 11016) = v5;
  v11 = v3;
  if ( v3 > 257 )
    v11 = 257;
  while ( v7 < v11 )
  {
    v12 = v7;
    v13 = v7 + *(_DWORD *)(a1 + 8);
    ++v7;
    *(_BYTE *)(v13 + *(_QWORD *)a1) = *(_BYTE *)(v12 + *(_QWORD *)a1);
  }
  *(_DWORD *)(a1 + 11984) = v4 & *(_DWORD *)(a1 + 12);
  return (unsigned int)(v4 - v3);
}

```

## disassembly

```asm
0x14000b13c  mov     [rsp+arg_0], rbx
0x14000b141  mov     [rsp+arg_8], rdi
0x14000b146  lea     ebx, [rdx+r8]
0x14000b14a  mov     r9d, edx
0x14000b14d  mov     r8, [rcx+2B08h]
0x14000b154  mov     r10, rcx
0x14000b157  mov     r11d, edx
0x14000b15a  cmp     r9d, ebx
0x14000b15d  jge     short loc_14000B18F
0x14000b15f  cmp     r8, [r10+2B10h]
0x14000b166  jnb     short loc_14000B18A
0x14000b168  mov     eax, [r10+8]
0x14000b16c  add     eax, 105h
0x14000b171  cmp     r9d, eax
0x14000b174  jge     short loc_14000B18A
0x14000b176  mov     al, [r8]
0x14000b179  mov     rcx, [r10]
0x14000b17c  movsxd  rdx, r9d
0x14000b17f  inc     r9d
0x14000b182  inc     r8
0x14000b185  mov     [rdx+rcx], al
0x14000b188  jmp     short loc_14000B15A
0x14000b18a  or      eax, 0FFFFFFFFh
0x14000b18d  jmp     short loc_14000B1D5
0x14000b18f  mov     eax, 101h
0x14000b194  mov     [r10+2B08h], r8
0x14000b19b  cmp     ebx, eax
0x14000b19d  mov     edi, ebx
0x14000b19f  cmovg   edi, eax
0x14000b1a2  jmp     short loc_14000B1BC
0x14000b1a4  mov     r8, [r10]
0x14000b1a7  mov     ecx, [r10+8]
0x14000b1ab  mov     edx, r11d
0x14000b1ae  add     ecx, r11d
0x14000b1b1  inc     r11d
0x14000b1b4  mov     al, [rdx+r8]
0x14000b1b8  mov     [rcx+r8], al
0x14000b1bc  cmp     r11d, edi
0x14000b1bf  jb      short loc_14000B1A4
0x14000b1c1  mov     eax, [r10+0Ch]
0x14000b1c5  and     eax, r9d
0x14000b1c8  sub     r9d, ebx
0x14000b1cb  mov     [r10+2ED0h], eax
0x14000b1d2  mov     eax, r9d
0x14000b1d5  mov     rbx, [rsp+arg_0]
0x14000b1da  mov     rdi, [rsp+arg_8]
0x14000b1df  retn
```
