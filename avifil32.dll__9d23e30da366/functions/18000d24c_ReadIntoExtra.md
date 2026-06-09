# ReadIntoExtra

- ea: `0x18000d24c`
- end: `0x18000d363`
- name: `ReadIntoExtra`
- size: `279`
- prototype: `__int64 __fastcall(LPCVOID *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a060`
- `0x18000d0dc`

## callees

- `0x18000d24c`
- `0x180014880`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000d2b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000d2b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d294`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d294`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d2ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d2ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d28b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d28b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2a1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d2c1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d2c1`
- `WINMM!mmioSeek` at `0x18000d31f`
- `WINMM!mmioSeek` at `0x18000d31f`

## pseudocode

```c
__int64 __fastcall ReadIntoExtra(LPCVOID *a1, __int64 a2, _DWORD *a3)
{
  unsigned int v3; // eax
  unsigned int v7; // esi
  LPCVOID v8; // rcx
  int *v9; // rdi
  HGLOBAL v10; // rax
  unsigned int v11; // ebx
  HGLOBAL v12; // rax
  HGLOBAL v13; // rax
  char *v14; // rax
  char *v15; // rbp
  bool v16; // sf
  unsigned int v17; // esi
  __int64 v18; // rax
  LONG v19; // edx
  unsigned int v20; // ebx

  v3 = a3[1];
  v7 = v3 + 8;
  if ( v3 + 8 < v3 )
    return 2147762279LL;
  v8 = *a1;
  v9 = (int *)(a1 + 1);
  if ( v8 )
  {
    if ( v7 + *v9 < v7 )
      return 2147762279LL;
    v10 = GlobalHandle(v8);
    GlobalUnlock(v10);
    v11 = v7 + *v9;
    v12 = GlobalHandle(*a1);
    v13 = GlobalReAlloc(v12, v11, 0x2002u);
  }
  else
  {
    v13 = GlobalAlloc(0x2002u, v7);
  }
  v14 = (char *)GlobalLock(v13);
  v15 = v14;
  if ( !v14 )
    return 2147762279LL;
  v16 = *v9 < 0;
  *a1 = v14;
  if ( v16 )
    return 2147762279LL;
  *(_DWORD *)&v14[*v9] = *a3;
  *(_DWORD *)&v14[*v9 + 4] = a3[1];
  v17 = (v7 & 1) + v7;
  if ( (int)(v17 + *v9) <= 0 )
    return 2147762279LL;
  v18 = *(_QWORD *)(a2 + 16);
  v19 = a3[3];
  if ( v18 )
    *(_DWORD *)(v18 + 372) = v19;
  else
    mmioSeek(*(HMMIO *)(a2 + 8), v19, 0);
  v20 = a3[1];
  if ( (unsigned int)shfileRead(a2, &v15[*v9 + 8], v20) != v20 )
    return 2147762285LL;
  *v9 += v17;
  return 0;
}

```

## disassembly

```asm
0x18000d24c  push    rbx
0x18000d24e  push    rbp
0x18000d24f  push    rsi
0x18000d250  push    rdi
0x18000d251  push    r13
0x18000d253  push    r14
0x18000d255  push    r15
0x18000d257  sub     rsp, 20h
0x18000d25b  mov     eax, [r8+4]
0x18000d25f  mov     r14, r8
0x18000d262  mov     r13, rdx
0x18000d265  mov     r15, rcx
0x18000d268  lea     esi, [rax+8]
0x18000d26b  cmp     esi, eax
0x18000d26d  jb      loc_18000D34F
0x18000d273  mov     rcx, [rcx]; pMem
0x18000d276  lea     rdi, [r15+8]
0x18000d27a  test    rcx, rcx
0x18000d27d  jz      short loc_18000D2BA
0x18000d27f  mov     edx, [rdi]
0x18000d281  add     edx, esi
0x18000d283  cmp     edx, esi
0x18000d285  jb      loc_18000D34F
0x18000d28b  call    cs:__imp_GlobalHandle
0x18000d291  mov     rcx, rax; hMem
0x18000d294  call    cs:__imp_GlobalUnlock
0x18000d29a  mov     ebx, [rdi]
0x18000d29c  mov     rcx, [r15]; pMem
0x18000d29f  add     ebx, esi
0x18000d2a1  call    cs:__imp_GlobalHandle
0x18000d2a7  mov     r8d, 2002h; uFlags
0x18000d2ad  mov     edx, ebx; dwBytes
0x18000d2af  mov     rcx, rax; hMem
0x18000d2b2  call    cs:__imp_GlobalReAlloc
0x18000d2b8  jmp     short loc_18000D2C7
0x18000d2ba  mov     edx, esi; dwBytes
0x18000d2bc  mov     ecx, 2002h; uFlags
0x18000d2c1  call    cs:__imp_GlobalAlloc
0x18000d2c7  mov     rcx, rax; hMem
0x18000d2ca  call    cs:__imp_GlobalLock
0x18000d2d0  mov     rbp, rax
0x18000d2d3  test    rax, rax
0x18000d2d6  jz      short loc_18000D34F
0x18000d2d8  cmp     dword ptr [rdi], 0
0x18000d2db  mov     [r15], rax
0x18000d2de  jl      short loc_18000D34F
0x18000d2e0  movsxd  rcx, dword ptr [rdi]
0x18000d2e3  mov     eax, [r14]
0x18000d2e6  mov     [rcx+rbp], eax
0x18000d2e9  movsxd  rcx, dword ptr [rdi]
0x18000d2ec  mov     eax, [r14+4]
0x18000d2f0  mov     [rcx+rbp+4], eax
0x18000d2f4  mov     eax, esi
0x18000d2f6  mov     ecx, [rdi]
0x18000d2f8  and     eax, 1
0x18000d2fb  add     esi, eax
0x18000d2fd  add     ecx, esi
0x18000d2ff  test    ecx, ecx
0x18000d301  jle     short loc_18000D34F
0x18000d303  mov     rax, [r13+10h]
0x18000d307  mov     edx, [r14+0Ch]; lOffset
0x18000d30b  test    rax, rax
0x18000d30e  jz      short loc_18000D318
0x18000d310  mov     [rax+174h], edx
0x18000d316  jmp     short loc_18000D325
0x18000d318  mov     rcx, [r13+8]; hmmio
0x18000d31c  xor     r8d, r8d; iOrigin
0x18000d31f  call    cs:__imp_mmioSeek
0x18000d325  movsxd  rdx, dword ptr [rdi]
0x18000d328  mov     rcx, r13
0x18000d32b  mov     ebx, [r14+4]
0x18000d32f  add     rdx, 8
0x18000d333  add     rdx, rbp
0x18000d336  mov     r8d, ebx
0x18000d339  call    shfileRead
0x18000d33e  cmp     eax, ebx
0x18000d340  jz      short loc_18000D349
0x18000d342  mov     eax, 8004406Dh
0x18000d347  jmp     short loc_18000D354
0x18000d349  add     [rdi], esi
0x18000d34b  xor     eax, eax
0x18000d34d  jmp     short loc_18000D354
0x18000d34f  mov     eax, 80044067h
0x18000d354  add     rsp, 20h
0x18000d358  pop     r15
0x18000d35a  pop     r14
0x18000d35c  pop     r13
0x18000d35e  pop     rdi
0x18000d35f  pop     rsi
0x18000d360  pop     rbp
0x18000d361  pop     rbx
0x18000d362  retn
```
