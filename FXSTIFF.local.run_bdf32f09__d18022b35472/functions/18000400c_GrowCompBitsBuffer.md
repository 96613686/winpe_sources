# GrowCompBitsBuffer

- ea: `0x18000400c`
- end: `0x1800040c5`
- name: `GrowCompBitsBuffer`
- size: `185`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003704`

## callees

- `0x18000400c`
- `0x18000ea18`
- `0x18000eac0`
- `0x180017bc2`

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
0x18000400c  mov     [rsp+arg_0], rbx
0x180004011  mov     [rsp+arg_8], rsi
0x180004016  push    rdi
0x180004017  sub     rsp, 20h
0x18000401b  mov     rbx, rcx
0x18000401e  mov     ecx, [rcx+654h]
0x180004024  test    ecx, ecx
0x180004026  jz      loc_1800040B3
0x18000402c  mov     eax, [rbx+650h]
0x180004032  lea     edi, [rax+rcx]
0x180004035  cmp     edi, eax
0x180004037  jb      short loc_1800040B3
0x180004039  mov     ecx, edi; dwBytes
0x18000403b  call    pMemAlloc
0x180004040  mov     rsi, rax
0x180004043  test    rax, rax
0x180004046  jz      short loc_1800040B3
0x180004048  mov     r8d, [rbx+650h]; Size
0x18000404f  mov     rcx, rax; void *
0x180004052  mov     rdx, [rbx+640h]; Src
0x180004059  call    memcpy_0
0x18000405e  mov     rcx, [rbx+640h]; lpMem
0x180004065  mov     rdx, rsi
0x180004068  sub     rdx, rcx
0x18000406b  add     [rbx+638h], rdx
0x180004072  call    pMemFree
0x180004077  mov     ecx, [rbx+69Ch]
0x18000407d  mov     eax, 0FFFFFFFFh
0x180004082  shl     rcx, 2
0x180004086  mov     [rbx+640h], rsi
0x18000408d  cmp     rcx, rax
0x180004090  ja      short loc_1800040B3
0x180004092  cmp     edi, ecx
0x180004094  jb      short loc_1800040B3
0x180004096  mov     eax, edi
0x180004098  mov     [rbx+650h], edi
0x18000409e  sub     eax, ecx
0x1800040a0  mov     ecx, eax
0x1800040a2  mov     eax, 1
0x1800040a7  add     rcx, rsi
0x1800040aa  mov     [rbx+648h], rcx
0x1800040b1  jmp     short loc_1800040B5
0x1800040b3  xor     eax, eax
0x1800040b5  mov     rbx, [rsp+28h+arg_0]
0x1800040ba  mov     rsi, [rsp+28h+arg_8]
0x1800040bf  add     rsp, 20h
0x1800040c3  pop     rdi
0x1800040c4  retn
```
