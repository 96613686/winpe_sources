# StructuredQuery1::NamedEntityCollector::Add(ulong,ulong,ulong,ulong,IEntity *,wchar_t const *,__MIDL___MIDL_itf_structuredquery_0000_0012_0001)

- ea: `0x18003c010`
- end: `0x18003c320`
- name: `?Add@NamedEntityCollector@StructuredQuery1@@UEAAJKKKKPEAUIEntity@@PEB_WW4__MIDL___MIDL_itf_structuredquery_0000_0012_0001@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(StructuredQuery1::NamedEntityCollector *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, struct IEntity *, const wchar_t *, enum __MIDL___MIDL_itf_structuredquery_0000_0012_0001)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18003c010`
- `0x18005db14`
- `0x18005db64`
- `0x18005e048`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c0ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c0ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StructuredQuery1::NamedEntityCollector::Add(
        StructuredQuery1::NamedEntityCollector *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        struct IEntity *a6,
        const wchar_t *a7,
        enum __MIDL___MIDL_itf_structuredquery_0000_0012_0001 a8)
{
  const wchar_t *v9; // r15
  struct IEntityVtbl *lpVtbl; // rax
  int v11; // edi
  __int64 v12; // rbp
  const WCHAR *v13; // r12
  unsigned int v14; // edi
  __int64 v15; // rbx
  __int64 v16; // r13
  unsigned int v17; // ebx
  __int64 v18; // rsi
  const WCHAR *lpString2; // rax
  int v20; // eax
  int v22; // r14d
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rax
  _WORD *v26; // rax
  const struct std::nothrow_t *v27; // rdx
  void *v28; // rsi
  __int64 v29; // rcx
  const struct std::nothrow_t *v30; // rcx
  WCHAR *v31; // rax
  PCNZWCH lpString1[11]; // [rsp+30h] [rbp-58h] BYREF

  if ( a2 > a4 || a4 > a5 || a5 > a3 || a2 >= a3 || !a6 || (v9 = a7) == 0 )
    return (unsigned int)-2147024809;
  lpVtbl = a6->lpVtbl;
  lpString1[0] = 0;
  v11 = ((__int64 (__fastcall *)(struct IEntity *, PCNZWCH *))lpVtbl->Name)(a6, lpString1);
  if ( v11 < 0 )
    return (unsigned int)v11;
  v12 = 0;
  v13 = lpString1[0];
  v14 = 0;
  v15 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL);
  v16 = *(_QWORD *)(v15 + 40);
  v17 = *(_DWORD *)(v15 + 32);
  do
  {
    if ( v14 >= v17 )
    {
      v11 = 1;
      goto LABEL_39;
    }
    v18 = (v17 + v14) >> 1;
    lpString2 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v16 + 112 * v18))(v16 + 112 * v18);
    v20 = CompareStringW(0x7Fu, 0, v13, -1, lpString2, -1);
    if ( v20 == 2 )
    {
      v12 = v16 + 112 * v18;
    }
    else if ( v20 == 1 )
    {
      v17 = (v17 + v14) >> 1;
    }
    else
    {
      v14 = v18 + 1;
    }
  }
  while ( !v12 );
  if ( a8 )
  {
    if ( a8 == NEC_MEDIUM )
    {
      v22 = 1;
    }
    else
    {
      if ( a8 != NEC_HIGH )
        return 2147942487LL;
      v22 = 2;
    }
  }
  else
  {
    v22 = 0;
  }
  v23 = -1;
  do
    ++v23;
  while ( a7[v23] );
  v24 = v23 + 1;
  if ( v23 + 1 < v23 )
  {
    CoTaskMemFree((LPVOID)lpString1[0]);
    return 2147942934LL;
  }
  v25 = 2 * v24;
  if ( !is_mul_ok(v24, 2u) )
    v25 = -1;
  v26 = operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
  v28 = v26;
  if ( v26 )
  {
    if ( !v24 )
    {
      v11 = -2147024809;
      goto LABEL_36;
    }
    if ( v24 > 0x7FFFFFFF )
    {
      v11 = -2147024809;
      *v26 = 0;
    }
    else
    {
      v29 = 2147483646;
      v27 = (const struct std::nothrow_t *)v26;
      do
      {
        if ( !v29 )
          break;
        if ( !*v9 )
          break;
        *(_WORD *)v27 = *v9++;
        v27 = (const struct std::nothrow_t *)((char *)v27 + 2);
        --v29;
        --v24;
      }
      while ( v24 );
      v30 = (const struct std::nothrow_t *)((char *)v27 - 2);
      v11 = -2147024774;
      if ( v24 )
      {
        v30 = v27;
        v11 = 0;
      }
      *(_WORD *)v30 = 0;
LABEL_36:
      if ( v11 >= 0 )
      {
        v31 = (WCHAR *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
        lpString1[1] = v31;
        if ( v31 )
        {
          *(_QWORD *)v31 = &SemanticsUM::NamedEntityUM::`vftable';
          *((_DWORD *)v31 + 2) = a2;
          *((_DWORD *)v31 + 3) = a3;
          *((_DWORD *)v31 + 4) = a4;
          *((_DWORD *)v31 + 5) = a5;
          *((_QWORD *)v31 + 3) = v12;
          *((_QWORD *)v31 + 4) = v28;
          *((_DWORD *)v31 + 10) = v22;
          *((_QWORD *)v31 + 6) = 0;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1));
          v11 = 0;
LABEL_39:
          CoTaskMemFree((LPVOID)lpString1[0]);
          return (unsigned int)v11;
        }
        operator delete(v28, 0);
        goto LABEL_44;
      }
    }
    operator delete(v26, v27);
    goto LABEL_39;
  }
LABEL_44:
  CoTaskMemFree((LPVOID)lpString1[0]);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003c010  mov     [rsp+arg_18], r9d
0x18003c015  mov     [rsp+arg_10], r8d
0x18003c01a  mov     [rsp+arg_8], edx
0x18003c01e  mov     [rsp+arg_0], rcx
0x18003c023  push    rbx
0x18003c024  push    rbp
0x18003c025  push    rsi
0x18003c026  push    rdi
0x18003c027  push    r12
0x18003c029  push    r13
0x18003c02b  push    r14
0x18003c02d  push    r15
0x18003c02f  sub     rsp, 48h
0x18003c033  mov     rbx, rcx
0x18003c036  cmp     edx, r9d
0x18003c039  ja      loc_18003C2E5
0x18003c03f  mov     eax, [rsp+88h+arg_20]
0x18003c046  cmp     r9d, eax
0x18003c049  ja      loc_18003C2E5
0x18003c04f  cmp     eax, r8d
0x18003c052  ja      loc_18003C2E5
0x18003c058  cmp     edx, r8d
0x18003c05b  jnb     loc_18003C2E5
0x18003c061  mov     rcx, [rsp+88h+arg_28]
0x18003c069  test    rcx, rcx
0x18003c06c  jz      loc_18003C2E5
0x18003c072  mov     r15, [rsp+88h+arg_30]
0x18003c07a  test    r15, r15
0x18003c07d  jz      loc_18003C2E5
0x18003c083  mov     rax, [rcx]
0x18003c086  lea     rdx, [rsp+88h+lpString1]
0x18003c08b  mov     [rsp+88h+lpString1], 0
0x18003c094  mov     rax, [rax+18h]
0x18003c098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c09d  mov     edi, eax
0x18003c09f  test    eax, eax
0x18003c0a1  js      loc_18003C292
0x18003c0a7  mov     rax, [rbx+10h]
0x18003c0ab  xor     ebp, ebp
0x18003c0ad  mov     r12, [rsp+88h+lpString1]
0x18003c0b2  xor     edi, edi
0x18003c0b4  mov     rbx, [rax+8]
0x18003c0b8  mov     r13, [rbx+28h]
0x18003c0bc  mov     ebx, [rbx+20h]
0x18003c0bf  nop
0x18003c0c0  cmp     edi, ebx
0x18003c0c2  jnb     loc_18003C316
0x18003c0c8  lea     esi, [rbx+rdi]
0x18003c0cb  shr     esi, 1
0x18003c0cd  imul    r14, rsi, 70h ; 'p'
0x18003c0d1  add     r14, r13
0x18003c0d4  mov     rcx, r14
0x18003c0d7  mov     rax, [r14]
0x18003c0da  mov     rax, [rax]
0x18003c0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c0e9  mov     r8, r12; lpString1
0x18003c0ec  mov     [rsp+88h+cchCount2], ecx; cchCount2
0x18003c0f0  mov     r9d, ecx; cchCount1
0x18003c0f3  mov     ecx, 7Fh; Locale
0x18003c0f8  mov     [rsp+88h+lpString2], rax; lpString2
0x18003c0fd  xor     edx, edx; dwCmpFlags
0x18003c0ff  call    cs:__imp_CompareStringW
0x18003c105  cmp     eax, 2
0x18003c108  jz      short loc_18003C149
0x18003c10a  cmp     eax, 1
0x18003c10d  jnz     short loc_18003C14E
0x18003c10f  mov     ebx, esi
0x18003c111  test    rbp, rbp
0x18003c114  jz      short loc_18003C0C0
0x18003c116  mov     ecx, [rsp+88h+arg_38]
0x18003c11d  test    ecx, ecx
0x18003c11f  jz      short loc_18003C153
0x18003c121  sub     ecx, 1
0x18003c124  jz      loc_18003C2B0
0x18003c12a  cmp     ecx, 1
0x18003c12d  jz      loc_18003C2DA
0x18003c133  mov     eax, 80070057h
0x18003c138  add     rsp, 48h
0x18003c13c  pop     r15
0x18003c13e  pop     r14
0x18003c140  pop     r13
0x18003c142  pop     r12
0x18003c144  pop     rdi
0x18003c145  pop     rsi
0x18003c146  pop     rbp
0x18003c147  pop     rbx
0x18003c148  retn
0x18003c149  mov     rbp, r14
0x18003c14c  jmp     short loc_18003C111
0x18003c14e  lea     edi, [rsi+1]
0x18003c151  jmp     short loc_18003C111
0x18003c153  xor     r14d, r14d
0x18003c156  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18003c15d  mov     rcx, r8
0x18003c160  inc     rcx
0x18003c163  cmp     word ptr [r15+rcx*2], 0
0x18003c169  jnz     short loc_18003C160
0x18003c16b  lea     rbx, [rcx+1]
0x18003c16f  cmp     rbx, rcx
0x18003c172  jb      loc_18003C299
0x18003c178  mov     eax, 2
0x18003c17d  mul     rbx
0x18003c180  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c187  cmovb   rax, r8
0x18003c18b  mov     rcx, rax; unsigned __int64
0x18003c18e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003c193  mov     rsi, rax
0x18003c196  test    rax, rax
0x18003c199  jz      loc_18003C2C3
0x18003c19f  test    rbx, rbx
0x18003c1a2  jz      loc_18003C2F6
0x18003c1a8  cmp     rbx, 7FFFFFFFh
0x18003c1af  ja      loc_18003C2EC
0x18003c1b5  mov     ecx, 7FFFFFFEh
0x18003c1ba  mov     rdx, rax
0x18003c1bd  nop     dword ptr [rax]
0x18003c1c0  test    rcx, rcx
0x18003c1c3  jz      short loc_18003C1E2
0x18003c1c5  movzx   eax, word ptr [r15]
0x18003c1c9  test    ax, ax
0x18003c1cc  jz      short loc_18003C1E2
0x18003c1ce  mov     [rdx], ax
0x18003c1d1  add     r15, 2
0x18003c1d5  add     rdx, 2; struct std::nothrow_t *
0x18003c1d9  dec     rcx
0x18003c1dc  sub     rbx, 1
0x18003c1e0  jnz     short loc_18003C1C0
0x18003c1e2  test    rbx, rbx
0x18003c1e5  lea     rcx, [rdx-2]
0x18003c1e9  mov     edi, 8007007Ah
0x18003c1ee  cmovnz  rcx, rdx
0x18003c1f2  xor     eax, eax
0x18003c1f4  test    rbx, rbx
0x18003c1f7  cmovnz  edi, eax
0x18003c1fa  mov     [rcx], ax
0x18003c1fd  test    edi, edi
0x18003c1ff  js      loc_18003C309
0x18003c205  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c20c  mov     ecx, 38h ; '8'; unsigned __int64
0x18003c211  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c216  mov     [rsp+88h+var_50], rax
0x18003c21b  mov     rdx, rax; struct std::nothrow_t *
0x18003c21e  test    rax, rax
0x18003c221  jz      loc_18003C2BB
0x18003c227  mov     rcx, [rsp+88h+arg_0]
0x18003c22f  lea     rax, ??_7NamedEntityUM@SemanticsUM@@6B@; const SemanticsUM::NamedEntityUM::`vftable'
0x18003c236  mov     [rdx], rax
0x18003c239  mov     eax, [rsp+88h+arg_8]
0x18003c240  mov     [rdx+8], eax
0x18003c243  mov     eax, [rsp+88h+arg_10]
0x18003c24a  mov     [rdx+0Ch], eax
0x18003c24d  mov     eax, [rsp+88h+arg_18]
0x18003c254  mov     [rdx+10h], eax
0x18003c257  mov     eax, [rsp+88h+arg_20]
0x18003c25e  mov     [rdx+14h], eax
0x18003c261  mov     [rdx+18h], rbp
0x18003c265  mov     [rdx+20h], rsi
0x18003c269  mov     [rdx+28h], r14d
0x18003c26d  mov     qword ptr [rdx+30h], 0
0x18003c275  mov     rcx, [rcx+8]
0x18003c279  mov     rax, [rcx]
0x18003c27c  mov     rax, [rax+10h]
0x18003c280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c285  xor     edi, edi
0x18003c287  mov     rcx, [rsp+88h+lpString1]; pv
0x18003c28c  call    cs:__imp_CoTaskMemFree
0x18003c292  mov     eax, edi
0x18003c294  jmp     loc_18003C138
0x18003c299  mov     rcx, [rsp+88h+lpString1]; pv
0x18003c29e  mov     edi, 80070216h
0x18003c2a3  call    cs:__imp_CoTaskMemFree
0x18003c2a9  mov     eax, edi
0x18003c2ab  jmp     loc_18003C138
0x18003c2b0  mov     r14d, 1
0x18003c2b6  jmp     loc_18003C156
0x18003c2bb  mov     rcx, rsi; void *
0x18003c2be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c2c3  mov     rcx, [rsp+88h+lpString1]; pv
0x18003c2c8  mov     edi, 8007000Eh
0x18003c2cd  call    cs:__imp_CoTaskMemFree
0x18003c2d3  mov     eax, edi
0x18003c2d5  jmp     loc_18003C138
0x18003c2da  mov     r14d, 2
0x18003c2e0  jmp     loc_18003C156
0x18003c2e5  mov     edi, 80070057h
0x18003c2ea  jmp     short loc_18003C292
0x18003c2ec  mov     edi, 80070057h
0x18003c2f1  jmp     loc_18008A3E6
0x18003c2f6  mov     edi, 80070057h
0x18003c2fb  test    rbx, rbx
0x18003c2fe  jz      loc_18003C1FD
0x18003c304  jmp     loc_18008A3E6
0x18003c309  mov     rcx, rsi; void *
0x18003c30c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c311  jmp     loc_18003C287
0x18003c316  mov     edi, 1
0x18003c31b  jmp     loc_18003C287
0x18008a3e6  xor     eax, eax
0x18008a3e8  mov     [rsi], ax
0x18008a3eb  jmp     loc_18003C309
```
