# GrowCompBitsBuffer

- ea: `0x18003a5ec`
- end: `0x18003a6a6`
- name: `GrowCompBitsBuffer`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003a074`

## callees

- `0x18002bab8`
- `0x18002bb58`
- `0x18003a5ec`
- `0x18003d4b2`

## pseudocode

```c
__int64 __fastcall GrowCompBitsBuffer(__int64 a1)
{
  int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // edi
  _BYTE *v5; // rax
  _BYTE *v6; // rsi
  _BYTE *v7; // rcx
  unsigned __int64 v8; // rcx
  __int64 result; // rax

  v2 = *(_DWORD *)(a1 + 1620);
  if ( !v2 )
    return 0;
  v3 = *(_DWORD *)(a1 + 1616);
  v4 = v3 + v2;
  if ( v3 + v2 < v3 )
    return 0;
  v5 = (_BYTE *)pMemAlloc(v4);
  v6 = v5;
  if ( !v5 )
    return 0;
  memcpy_0(v5, *(const void **)(a1 + 1600), *(unsigned int *)(a1 + 1616));
  v7 = *(_BYTE **)(a1 + 1600);
  *(_QWORD *)(a1 + 1592) += v6 - v7;
  pMemFree(v7);
  v8 = 4LL * *(unsigned int *)(a1 + 1692);
  *(_QWORD *)(a1 + 1600) = v6;
  if ( v8 > 0xFFFFFFFF || v4 < (unsigned int)v8 )
    return 0;
  *(_DWORD *)(a1 + 1616) = v4;
  result = 1;
  *(_QWORD *)(a1 + 1608) = &v6[v4 - (unsigned int)v8];
  return result;
}

```

## disassembly

```asm
0x18003a5ec  mov     [rsp+arg_0], rbx
0x18003a5f1  mov     [rsp+arg_8], rsi
0x18003a5f6  push    rdi
0x18003a5f7  sub     rsp, 20h
0x18003a5fb  mov     rbx, rcx
0x18003a5fe  mov     ecx, [rcx+654h]
0x18003a604  test    ecx, ecx
0x18003a606  jz      loc_18003A693
0x18003a60c  mov     eax, [rbx+650h]
0x18003a612  lea     edi, [rax+rcx]
0x18003a615  cmp     edi, eax
0x18003a617  jb      short loc_18003A693
0x18003a619  mov     ecx, edi; dwBytes
0x18003a61b  call    pMemAlloc
0x18003a620  mov     rsi, rax
0x18003a623  test    rax, rax
0x18003a626  jz      short loc_18003A693
0x18003a628  mov     r8d, [rbx+650h]; Size
0x18003a62f  mov     rcx, rax; void *
0x18003a632  mov     rdx, [rbx+640h]; Src
0x18003a639  call    memcpy_0
0x18003a63e  mov     rcx, [rbx+640h]; lpMem
0x18003a645  mov     rdx, rsi
0x18003a648  sub     rdx, rcx
0x18003a64b  add     [rbx+638h], rdx
0x18003a652  call    pMemFree
0x18003a657  mov     ecx, [rbx+69Ch]
0x18003a65d  mov     eax, 0FFFFFFFFh
0x18003a662  shl     rcx, 2
0x18003a666  mov     [rbx+640h], rsi
0x18003a66d  cmp     rcx, rax
0x18003a670  ja      short loc_18003A693
0x18003a672  cmp     edi, ecx
0x18003a674  jb      short loc_18003A693
0x18003a676  mov     eax, edi
0x18003a678  mov     [rbx+650h], edi
0x18003a67e  sub     eax, ecx
0x18003a680  mov     ecx, eax
0x18003a682  mov     eax, 1
0x18003a687  add     rcx, rsi
0x18003a68a  mov     [rbx+648h], rcx
0x18003a691  jmp     short loc_18003A695
0x18003a693  xor     eax, eax
0x18003a695  mov     rbx, [rsp+28h+arg_0]
0x18003a69a  mov     rsi, [rsp+28h+arg_8]
0x18003a69f  add     rsp, 20h
0x18003a6a3  pop     rdi
0x18003a6a4  retn
```
