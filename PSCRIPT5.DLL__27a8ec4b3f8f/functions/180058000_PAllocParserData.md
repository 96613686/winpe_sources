# PAllocParserData

- ea: `0x180058000`
- end: `0x1800581b4`
- name: `PAllocParserData`
- size: `436`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800581bc`

## callees

- `0x180057cf8`
- `0x180058000`
- `0x180058318`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180058037`
- `KERNEL32!HeapAlloc` at `0x180058116`
- `KERNEL32!HeapAlloc` at `0x180058133`
- `KERNEL32!HeapAlloc` at `0x180058037`
- `KERNEL32!HeapAlloc` at `0x180058116`
- `KERNEL32!HeapAlloc` at `0x180058133`
- `KERNEL32!HeapCreate` at `0x180058011`
- `KERNEL32!HeapCreate` at `0x180058011`
- `KERNEL32!HeapDestroy` at `0x18005819a`
- `KERNEL32!HeapDestroy` at `0x18005819a`

## pseudocode

```c
_QWORD *PAllocParserData()
{
  HANDLE v0; // rax
  void *v1; // rdi
  _QWORD *v2; // rax
  __int64 v3; // rbx
  LPVOID v4; // rax
  void *v5; // rcx
  LPVOID v6; // rax
  bool v7; // zf
  __int64 i; // rdx
  int v9; // r8d
  char *j; // rcx

  v0 = HeapCreate(0, 0, 0);
  v1 = v0;
  if ( !v0 )
    return 0;
  v2 = HeapAlloc(v0, 8u, 0x438u);
  v3 = (__int64)v2;
  if ( !v2 )
  {
    HeapDestroy(v1);
    return 0;
  }
  v2[1] = v1;
  v2[134] = v2;
  *v2 = v2;
  *((_DWORD *)v2 + 22) = -1;
  *((_DWORD *)v2 + 85) = 176128;
  *((_DWORD *)v2 + 87) = 0;
  *((_DWORD *)v2 + 88) = 300;
  *((_DWORD *)v2 + 133) = -1;
  *((_DWORD *)v2 + 134) = -1;
  *((_DWORD *)v2 + 132) = -1;
  *((_WORD *)v2 + 262) = 0;
  v2[71] = (char *)v2 + 628;
  v2[73] = (char *)v2 + 692;
  v2[75] = (char *)v2 + 756;
  *((_DWORD *)v2 + 101) = 2;
  v2[70] = 64;
  v2[72] = 64;
  v2[74] = 256;
  if ( (unsigned int)IGrowValueBuffer((__int64)(v2 + 76))
    || (v4 = HeapAlloc(*(HANDLE *)(v3 + 8), 8u, 0x18Cu),
        v5 = *(void **)(v3 + 8),
        *(_QWORD *)(v3 + 24) = v4,
        v6 = HeapAlloc(v5, 8u, 0x63u),
        v7 = *(_QWORD *)(v3 + 24) == 0,
        *(_QWORD *)(v3 + 32) = v6,
        v7)
    || !v6 )
  {
    VFreeParserData(v3);
    return 0;
  }
  for ( i = 0; i != 99; ++i )
  {
    v9 = 0;
    for ( j = (&gPpdBuiltInKeywordTable)[3 * i]; *j; ++j )
      v9 = (unsigned __int8)*j ^ (2 * v9);
    *(_DWORD *)(*(_QWORD *)(v3 + 24) + 4 * i) = v9;
  }
  return (_QWORD *)v3;
}

```

## disassembly

```asm
0x180058000  mov     [rsp+arg_0], rbx
0x180058005  push    rdi
0x180058006  sub     rsp, 20h
0x18005800a  xor     r8d, r8d; dwMaximumSize
0x18005800d  xor     edx, edx; dwInitialSize
0x18005800f  xor     ecx, ecx; flOptions
0x180058011  call    cs:__imp_HeapCreate
0x180058018  nop     dword ptr [rax+rax+00h]
0x18005801d  mov     rdi, rax
0x180058020  test    rax, rax
0x180058023  jz      loc_1800581A6
0x180058029  mov     edx, 8; dwFlags
0x18005802e  mov     r8d, 438h; dwBytes
0x180058034  mov     rcx, rax; hHeap
0x180058037  call    cs:__imp_HeapAlloc
0x18005803e  nop     dword ptr [rax+rax+00h]
0x180058043  mov     rbx, rax
0x180058046  test    rax, rax
0x180058049  jz      loc_180058197
0x18005804f  mov     [rax+8], rdi
0x180058053  lea     rcx, [rbx+260h]
0x18005805a  mov     [rax+430h], rax
0x180058061  mov     [rax], rax
0x180058064  mov     dword ptr [rax+58h], 0FFFFFFFFh
0x18005806b  mov     dword ptr [rax+154h], 2B000h
0x180058075  mov     dword ptr [rax+15Ch], 0
0x18005807f  mov     dword ptr [rax+160h], 12Ch
0x180058089  or      eax, 0FFFFFFFFh
0x18005808c  mov     [rbx+214h], eax
0x180058092  mov     [rbx+218h], eax
0x180058098  mov     [rbx+210h], eax
0x18005809e  xor     eax, eax
0x1800580a0  mov     [rbx+20Ch], ax
0x1800580a7  lea     rax, [rbx+274h]
0x1800580ae  mov     [rbx+238h], rax
0x1800580b5  lea     rax, [rbx+2B4h]
0x1800580bc  mov     [rbx+248h], rax
0x1800580c3  lea     rax, [rbx+2F4h]
0x1800580ca  mov     [rbx+258h], rax
0x1800580d1  mov     dword ptr [rbx+194h], 2
0x1800580db  mov     qword ptr [rbx+230h], 40h ; '@'
0x1800580e6  mov     qword ptr [rbx+240h], 40h ; '@'
0x1800580f1  mov     qword ptr [rbx+250h], 100h
0x1800580fc  call    IGrowValueBuffer
0x180058101  test    eax, eax
0x180058103  jnz     loc_18005818D
0x180058109  mov     rcx, [rbx+8]; hHeap
0x18005810d  lea     edx, [rax+8]; dwFlags
0x180058110  mov     r8d, 18Ch; dwBytes
0x180058116  call    cs:__imp_HeapAlloc
0x18005811d  nop     dword ptr [rax+rax+00h]
0x180058122  mov     rcx, [rbx+8]; hHeap
0x180058126  mov     edx, 8; dwFlags
0x18005812b  mov     [rbx+18h], rax
0x18005812f  lea     r8d, [rdx+5Bh]; dwBytes
0x180058133  call    cs:__imp_HeapAlloc
0x18005813a  nop     dword ptr [rax+rax+00h]
0x18005813f  cmp     qword ptr [rbx+18h], 0
0x180058144  mov     [rbx+20h], rax
0x180058148  jz      short loc_18005818D
0x18005814a  test    rax, rax
0x18005814d  jz      short loc_18005818D
0x18005814f  xor     edx, edx
0x180058151  lea     rax, [rdx+rdx*2]
0x180058155  xor     r8d, r8d
0x180058158  lea     rcx, gPpdBuiltInKeywordTable
0x18005815f  mov     rcx, [rcx+rax*8]
0x180058163  jmp     short loc_180058171
0x180058165  add     r8d, r8d
0x180058168  movzx   eax, al
0x18005816b  xor     r8d, eax
0x18005816e  inc     rcx
0x180058171  mov     al, [rcx]
0x180058173  test    al, al
0x180058175  jnz     short loc_180058165
0x180058177  mov     rcx, [rbx+18h]
0x18005817b  mov     [rcx+rdx*4], r8d
0x18005817f  inc     rdx
0x180058182  cmp     rdx, 63h ; 'c'
0x180058186  jnz     short loc_180058151
0x180058188  mov     rax, rbx
0x18005818b  jmp     short loc_1800581A8
0x18005818d  mov     rcx, rbx
0x180058190  call    VFreeParserData
0x180058195  jmp     short loc_1800581A6
0x180058197  mov     rcx, rdi; hHeap
0x18005819a  call    cs:__imp_HeapDestroy
0x1800581a1  nop     dword ptr [rax+rax+00h]
0x1800581a6  xor     eax, eax
0x1800581a8  mov     rbx, [rsp+28h+arg_0]
0x1800581ad  add     rsp, 20h
0x1800581b1  pop     rdi
0x1800581b2  retn
```
