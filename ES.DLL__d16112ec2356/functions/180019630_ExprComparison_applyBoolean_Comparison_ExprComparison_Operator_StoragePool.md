# ExprComparison::applyBoolean_Comparison(ExprComparison &,Operator,StoragePool &)

- ea: `0x180019630`
- end: `0x180019cb7`
- name: `?applyBoolean_Comparison@ExprComparison@@UEAAPEAVExprNode@@AEAV1@W4Operator@@AEAVStoragePool@@@Z`
- size: `1671`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180019630`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x180019885`
- `msvcrt!malloc` at `0x180019922`
- `msvcrt!malloc` at `0x1800199c0`
- `msvcrt!malloc` at `0x180019a5b`
- `msvcrt!malloc` at `0x180019afa`
- `msvcrt!malloc` at `0x180019885`
- `msvcrt!malloc` at `0x180019922`
- `msvcrt!malloc` at `0x1800199c0`
- `msvcrt!malloc` at `0x180019a5b`
- `msvcrt!malloc` at `0x180019afa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001986c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001986c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800199a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019ae1`

## string_xrefs

- `0x1800198db`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019979`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019a12`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019aac`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019b4b`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019b79`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019b95`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019bba`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019be8`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019c0d`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019c37`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019c59`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
__int64 __fastcall ExprComparison::applyBoolean_Comparison(__int64 a1, __int64 a2, int a3, size_t *a4)
{
  size_t v4; // rax
  _QWORD *v5; // r13
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // r12
  size_t v12; // rcx
  unsigned __int64 v13; // rax
  _QWORD *v14; // r15
  size_t v15; // rdx
  unsigned __int64 v16; // rax
  _QWORD *v17; // rcx
  size_t v18; // rcx
  int v19; // r14d
  unsigned __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  _QWORD *v24; // rsi
  __int64 i; // rbp
  size_t v26; // rdi
  _QWORD *v27; // r15
  size_t v28; // rbx
  void *v29; // rax
  unsigned __int64 v30; // rax
  size_t v31; // r15
  _QWORD *v32; // rbp
  size_t v33; // rbx
  void *v34; // rax
  unsigned __int64 v35; // rax
  size_t v36; // r12
  _QWORD *v37; // rbp
  size_t v38; // rbx
  void *v39; // rax
  unsigned __int64 v40; // rax
  size_t v41; // rdi
  _QWORD *v42; // r15
  size_t v43; // rbx
  void *v44; // rax
  unsigned __int64 v45; // rax
  size_t v46; // r12
  _QWORD *v47; // r15
  size_t v48; // rbx
  void *v49; // rax
  unsigned __int64 v50; // rax
  unsigned int v51; // edx
  unsigned int v52; // edx
  unsigned int v53; // edx

  v4 = a4[1];
  v5 = 0;
  v9 = *(_QWORD *)(v4 + 16);
  if ( a3 != -5 )
  {
    if ( v9 < 0x20 || (v10 = *(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 16) = v9 - 32, *(_QWORD *)(v4 + 8) = v10 + 32, !v10) )
    {
      v26 = *a4;
      if ( *a4 < 0x20 )
        v26 = 64;
      v27 = CoTaskMemAlloc(0x20u);
      if ( v27 )
      {
        v28 = a4[1];
        v29 = malloc(v26);
        *v27 = v29;
        v27[1] = v29;
        v27[2] = v26;
        v27[3] = v28;
        if ( !v29 )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
      }
      else
      {
        v27 = 0;
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
      }
      *a4 = v26;
      a4[1] = (size_t)v27;
      v30 = v27[2];
      if ( v30 < 0x20 || (v10 = v27[1], v27[2] = v30 - 32, v27[1] = v10 + 32, !v10) )
      {
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
        return 0;
      }
    }
    *(_QWORD *)(v10 + 8) = 0;
    *(_QWORD *)v10 = &ExprBooleanAND::`vftable';
    v11 = a1;
    *(_DWORD *)(v10 + 16) = 2;
    *(_QWORD *)(v10 + 24) = 0;
    v12 = a4[1];
    v13 = *(_QWORD *)(v12 + 16);
    if ( *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) >= *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) )
    {
      v11 = a2;
      a2 = a1;
    }
    if ( v13 >= 0x10 )
    {
      v14 = *(_QWORD **)(v12 + 8);
      *(_QWORD *)(v12 + 16) = v13 - 16;
      *(_QWORD *)(v12 + 8) = v14 + 2;
      if ( v14 )
        goto LABEL_8;
    }
    v31 = *a4;
    if ( *a4 < 0x10 )
      v31 = 32;
    v32 = CoTaskMemAlloc(0x20u);
    if ( v32 )
    {
      v33 = a4[1];
      v34 = malloc(v31);
      *v32 = v34;
      v32[1] = v34;
      v32[2] = v31;
      v32[3] = v33;
      if ( !v34 )
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
    }
    else
    {
      v32 = 0;
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
    }
    *a4 = v31;
    a4[1] = (size_t)v32;
    v35 = v32[2];
    if ( v35 >= 0x10 && (v14 = (_QWORD *)v32[1], v32[2] = v35 - 16, v32[1] = v14 + 2, v14) )
    {
LABEL_8:
      *v14 = v11;
      v14[1] = 0;
    }
    else
    {
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
      v14 = 0;
    }
    v15 = a4[1];
    v16 = *(_QWORD *)(v15 + 16);
    if ( v16 >= 0x10 )
    {
      v17 = *(_QWORD **)(v15 + 8);
      *(_QWORD *)(v15 + 16) = v16 - 16;
      *(_QWORD *)(v15 + 8) = v17 + 2;
      if ( v17 )
        goto LABEL_11;
    }
    v36 = *a4;
    if ( *a4 < 0x10 )
      v36 = 32;
    v37 = CoTaskMemAlloc(0x20u);
    if ( v37 )
    {
      v38 = a4[1];
      v39 = malloc(v36);
      *v37 = v39;
      v37[1] = v39;
      v37[2] = v36;
      v37[3] = v38;
      if ( v39 )
      {
LABEL_53:
        *a4 = v36;
        a4[1] = (size_t)v37;
        v40 = v37[2];
        if ( v40 < 0x10 || (v17 = (_QWORD *)v37[1], v37[2] = v40 - 16, v37[1] = v17 + 2, !v17) )
        {
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
          v17 = 0;
          goto LABEL_12;
        }
LABEL_11:
        *v17 = a2;
        v17[1] = v14;
LABEL_12:
        *(_QWORD *)(v10 + 8) = v17;
        if ( *(_DWORD *)(a2 + 24) == 1 && !*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) )
          *(_QWORD *)(v10 + 24) = *(_QWORD *)(a2 + 16);
        return v10;
      }
      v51 = 34;
    }
    else
    {
      v37 = 0;
      v51 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v51, 0xC0001204, 0x10u);
    goto LABEL_53;
  }
  if ( v9 >= 0x18 )
  {
    v10 = *(_QWORD *)(v4 + 8);
    *(_QWORD *)(v4 + 16) = v9 - 24;
    *(_QWORD *)(v4 + 8) = v10 + 24;
    if ( v10 )
      goto LABEL_17;
  }
  v41 = *a4;
  if ( *a4 < 0x18 )
    v41 = 48;
  v42 = CoTaskMemAlloc(0x20u);
  if ( !v42 )
  {
    v42 = 0;
    v52 = 94;
LABEL_75:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v52, 0xC0001204, 0x10u);
    goto LABEL_60;
  }
  v43 = a4[1];
  v44 = malloc(v41);
  *v42 = v44;
  v42[1] = v44;
  v42[2] = v41;
  v42[3] = v43;
  if ( !v44 )
  {
    v52 = 34;
    goto LABEL_75;
  }
LABEL_60:
  *a4 = v41;
  a4[1] = (size_t)v42;
  v45 = v42[2];
  if ( v45 < 0x18 || (v10 = v42[1], v42[2] = v45 - 24, v42[1] = v10 + 24, !v10) )
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    v10 = 0;
    goto LABEL_18;
  }
LABEL_17:
  *(_QWORD *)(v10 + 8) = 0;
  *(_QWORD *)v10 = &ExprBooleanOR::`vftable';
  *(_BYTE *)(v10 + 16) = 0;
  (*(void (__fastcall **)(__int64, __int64, size_t *))(*(_QWORD *)a2 + 72LL))(a2, v10, a4);
LABEL_18:
  v18 = a4[1];
  v19 = 1;
  v20 = *(_QWORD *)(v18 + 16);
  if ( v20 >= 0x18 )
  {
    v21 = *(_QWORD *)(v18 + 8);
    *(_QWORD *)(v18 + 16) = v20 - 24;
    *(_QWORD *)(v18 + 8) = v21 + 24;
    if ( v21 )
      goto LABEL_20;
  }
  v46 = *a4;
  if ( *a4 < 0x18 )
    v46 = 48;
  v47 = CoTaskMemAlloc(0x20u);
  if ( !v47 )
  {
    v47 = 0;
    v53 = 94;
LABEL_77:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v53, 0xC0001204, 0x10u);
    goto LABEL_67;
  }
  v48 = a4[1];
  v49 = malloc(v46);
  *v47 = v49;
  v47[1] = v49;
  v47[2] = v46;
  v47[3] = v48;
  if ( !v49 )
  {
    v53 = 34;
    goto LABEL_77;
  }
LABEL_67:
  *a4 = v46;
  a4[1] = (size_t)v47;
  v50 = v47[2];
  if ( v50 >= 0x18 )
  {
    v21 = v47[1];
    v47[2] = v50 - 24;
    v47[1] = v21 + 24;
    if ( v21 )
    {
LABEL_20:
      *(_QWORD *)v21 = a1;
      *(_DWORD *)(v21 + 8) = 1;
      *(_QWORD *)(v21 + 16) = 0;
      goto LABEL_21;
    }
  }
  InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  v21 = 0;
LABEL_21:
  if ( *(_DWORD *)(a1 + 24) == 1 && !*(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) )
  {
    v24 = *(_QWORD **)(v10 + 8);
    for ( i = *(_QWORD *)(a1 + 16); v24; v24 = (_QWORD *)v24[2] )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v24 + 64LL))(*v24, i) )
        break;
      v5 = v24;
    }
    *(_QWORD *)(v21 + 16) = v24;
    if ( v24 )
      v19 = *((_DWORD *)v24 + 2) + 1;
    *(_DWORD *)(v21 + 8) = v19;
    if ( v5 )
    {
      v5[2] = v21;
      return v10;
    }
  }
  else
  {
    *(_QWORD *)(v21 + 16) = *(_QWORD *)(v10 + 8);
    v22 = *(_QWORD *)(v10 + 8);
    if ( v22 )
      v19 = *(_DWORD *)(v22 + 8) + 1;
    *(_DWORD *)(v21 + 8) = v19;
    *(_BYTE *)(v10 + 16) = 0;
  }
  *(_QWORD *)(v10 + 8) = v21;
  return v10;
}

```

## disassembly

```asm
0x180019630  push    rbx
0x180019632  push    rbp
0x180019633  push    rsi
0x180019634  push    rdi
0x180019635  push    r12
0x180019637  push    r13
0x180019639  push    r14
0x18001963b  push    r15
0x18001963d  sub     rsp, 28h
0x180019641  mov     rax, [r9+8]
0x180019645  xor     r13d, r13d
0x180019648  mov     rbp, rcx
0x18001964b  mov     rsi, r9
0x18001964e  mov     r14, rdx
0x180019651  mov     rcx, [rax+10h]
0x180019655  cmp     r8d, 0FFFFFFFBh
0x180019659  jz      loc_180019752
0x18001965f  mov     ebx, 20h ; ' '
0x180019664  cmp     rcx, rbx
0x180019667  jb      loc_18001985A
0x18001966d  mov     rdi, [rax+8]
0x180019671  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180019675  mov     [rax+10h], rcx
0x180019679  lea     rcx, [rdi+20h]
0x18001967d  mov     [rax+8], rcx
0x180019681  test    rdi, rdi
0x180019684  jz      loc_18001985A
0x18001968a  mov     [rdi+8], r13
0x18001968e  lea     rax, ??_7ExprBooleanAND@@6B@; const ExprBooleanAND::`vftable'
0x180019695  mov     [rdi], rax
0x180019698  mov     r12, rbp
0x18001969b  mov     dword ptr [rdi+10h], 2
0x1800196a2  mov     [rdi+18h], r13
0x1800196a6  mov     rax, [r14+8]
0x1800196aa  mov     rcx, [rsi+8]
0x1800196ae  mov     edx, [rax+10h]
0x1800196b1  mov     rax, [rbp+8]
0x1800196b5  cmp     edx, [rax+10h]
0x1800196b8  mov     rax, [rcx+10h]
0x1800196bc  cmovge  r12, r14
0x1800196c0  cmovge  r14, rbp
0x1800196c4  cmp     rax, 10h
0x1800196c8  jb      loc_1800198FB
0x1800196ce  mov     r15, [rcx+8]
0x1800196d2  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800196d6  mov     [rcx+10h], rax
0x1800196da  lea     rax, [r15+10h]
0x1800196de  mov     [rcx+8], rax
0x1800196e2  test    r15, r15
0x1800196e5  jz      loc_1800198FB
0x1800196eb  mov     [r15], r12
0x1800196ee  mov     [r15+8], r13
0x1800196f2  mov     rdx, [rsi+8]
0x1800196f6  mov     rax, [rdx+10h]
0x1800196fa  cmp     rax, 10h
0x1800196fe  jb      loc_180019999
0x180019704  mov     rcx, [rdx+8]
0x180019708  add     rax, 0FFFFFFFFFFFFFFF0h
0x18001970c  mov     [rdx+10h], rax
0x180019710  lea     rax, [rcx+10h]
0x180019714  mov     [rdx+8], rax
0x180019718  test    rcx, rcx
0x18001971b  jz      loc_180019999
0x180019721  mov     [rcx], r14
0x180019724  mov     [rcx+8], r15
0x180019728  mov     [rdi+8], rcx
0x18001972c  cmp     dword ptr [r14+18h], 1
0x180019731  jnz     loc_180019819
0x180019737  mov     rax, [r14+8]
0x18001973b  cmp     [rax+10h], r13d
0x18001973f  jnz     loc_180019819
0x180019745  mov     rax, [r14+10h]
0x180019749  mov     [rdi+18h], rax
0x18001974d  jmp     loc_180019819
0x180019752  mov     edx, 30h ; '0'
0x180019757  cmp     rcx, 18h
0x18001975b  jb      loc_180019A32
0x180019761  mov     rdi, [rax+8]
0x180019765  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180019769  mov     [rax+10h], rcx
0x18001976d  lea     rcx, [rdi+18h]
0x180019771  mov     [rax+8], rcx
0x180019775  test    rdi, rdi
0x180019778  jz      loc_180019A32
0x18001977e  lea     rax, ??_7ExprBooleanOR@@6B@; const ExprBooleanOR::`vftable'
0x180019785  mov     [rdi+8], r13
0x180019789  mov     [rdi], rax
0x18001978c  mov     r8, rsi
0x18001978f  mov     [rdi+10h], r13b
0x180019793  mov     rdx, rdi
0x180019796  mov     rax, [r14]
0x180019799  mov     rcx, r14
0x18001979c  mov     rax, [rax+48h]
0x1800197a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197a5  mov     rcx, [rsi+8]
0x1800197a9  mov     r14d, 1
0x1800197af  mov     rax, [rcx+10h]
0x1800197b3  cmp     rax, 18h
0x1800197b7  jb      loc_180019ACC
0x1800197bd  mov     rbx, [rcx+8]
0x1800197c1  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800197c5  mov     [rcx+10h], rax
0x1800197c9  lea     rax, [rbx+18h]
0x1800197cd  mov     [rcx+8], rax
0x1800197d1  test    rbx, rbx
0x1800197d4  jz      loc_180019ACC
0x1800197da  mov     [rbx], rbp
0x1800197dd  mov     [rbx+8], r14d
0x1800197e1  mov     [rbx+10h], r13
0x1800197e5  cmp     [rbp+18h], r14d
0x1800197e9  jnz     short loc_1800197F5
0x1800197eb  mov     rax, [rbp+8]
0x1800197ef  cmp     [rax+10h], r13d
0x1800197f3  jz      short loc_18001982D
0x1800197f5  mov     rax, [rdi+8]
0x1800197f9  mov     [rbx+10h], rax
0x1800197fd  mov     rax, [rdi+8]
0x180019801  test    rax, rax
0x180019804  jz      short loc_18001980D
0x180019806  mov     r14d, [rax+8]
0x18001980a  inc     r14d
0x18001980d  mov     [rbx+8], r14d
0x180019811  mov     [rdi+10h], r13b
0x180019815  mov     [rdi+8], rbx
0x180019819  mov     rax, rdi
0x18001981c  add     rsp, 28h
0x180019820  pop     r15
0x180019822  pop     r14
0x180019824  pop     r13
0x180019826  pop     r12
0x180019828  pop     rdi
0x180019829  pop     rsi
0x18001982a  pop     rbp
0x18001982b  pop     rbx
0x18001982c  retn
0x18001982d  mov     rsi, [rdi+8]
0x180019831  mov     rbp, [rbp+10h]
0x180019835  test    rsi, rsi
0x180019838  jnz     loc_180019C80
0x18001983e  mov     [rbx+10h], rsi
0x180019842  test    rsi, rsi
0x180019845  jnz     loc_180019CAB
0x18001984b  mov     [rbx+8], r14d
0x18001984f  test    r13, r13
0x180019852  jz      short loc_180019815
0x180019854  mov     [r13+10h], rbx
0x180019858  jmp     short loc_180019819
0x18001985a  mov     rdi, [r9]
0x18001985d  mov     eax, 40h ; '@'
0x180019862  cmp     rdi, rbx
0x180019865  mov     rcx, rbx; cb
0x180019868  cmovb   rdi, rax
0x18001986c  call    cs:__imp_CoTaskMemAlloc
0x180019872  mov     r15, rax
0x180019875  test    rax, rax
0x180019878  jz      loc_180019B90
0x18001987e  mov     rbx, [rsi+8]
0x180019882  mov     rcx, rdi; Size
0x180019885  call    cs:__imp_malloc
0x18001988b  mov     [r15], rax
0x18001988e  mov     [r15+8], rax
0x180019892  mov     [r15+10h], rdi
0x180019896  mov     [r15+18h], rbx
0x18001989a  test    rax, rax
0x18001989d  jz      loc_180019C32
0x1800198a3  mov     ebx, 20h ; ' '
0x1800198a8  mov     [rsi], rdi
0x1800198ab  mov     [rsi+8], r15
0x1800198af  mov     rax, [r15+10h]
0x1800198b3  cmp     rax, 20h ; ' '
0x1800198b7  jb      short loc_1800198D6
0x1800198b9  mov     rdi, [r15+8]
0x1800198bd  add     rax, 0FFFFFFFFFFFFFFE0h
0x1800198c1  mov     [r15+10h], rax
0x1800198c5  lea     rax, [rdi+20h]
0x1800198c9  mov     [r15+8], rax
0x1800198cd  test    rdi, rdi
0x1800198d0  jnz     loc_18001968A
0x1800198d6  mov     edx, 64h ; 'd'; unsigned int
0x1800198db  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800198e2  mov     r9d, 10h; unsigned __int16
0x1800198e8  mov     r8d, 0C0001204h; unsigned int
0x1800198ee  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800198f3  mov     rdi, r13
0x1800198f6  jmp     loc_180019819
0x1800198fb  mov     r15, [rsi]
0x1800198fe  mov     rcx, rbx; cb
0x180019901  cmp     r15, 10h
0x180019905  cmovb   r15, rbx
0x180019909  call    cs:__imp_CoTaskMemAlloc
0x18001990f  mov     rbp, rax
0x180019912  test    rax, rax
0x180019915  jz      loc_180019BB5
0x18001991b  mov     rbx, [rsi+8]
0x18001991f  mov     rcx, r15; Size
0x180019922  call    cs:__imp_malloc
0x180019928  mov     [rbp+0], rax
0x18001992c  mov     [rbp+8], rax
0x180019930  mov     [rbp+10h], r15
0x180019934  mov     [rbp+18h], rbx
0x180019938  test    rax, rax
0x18001993b  jz      loc_180019C54
0x180019941  mov     ebx, 20h ; ' '
0x180019946  mov     [rsi], r15
0x180019949  mov     [rsi+8], rbp
0x18001994d  mov     rax, [rbp+10h]
0x180019951  cmp     rax, 10h
0x180019955  jb      short loc_180019974
0x180019957  mov     r15, [rbp+8]
0x18001995b  add     rax, 0FFFFFFFFFFFFFFF0h
0x18001995f  mov     [rbp+10h], rax
0x180019963  lea     rax, [r15+10h]
0x180019967  mov     [rbp+8], rax
0x18001996b  test    r15, r15
0x18001996e  jnz     loc_1800196EB
0x180019974  mov     edx, 64h ; 'd'; unsigned int
0x180019979  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019980  mov     r9d, 10h; unsigned __int16
0x180019986  mov     r8d, 0C0001204h; unsigned int
0x18001998c  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180019991  mov     r15, r13
0x180019994  jmp     loc_1800196F2
0x180019999  mov     r12, [rsi]
0x18001999c  mov     rcx, rbx; cb
0x18001999f  cmp     r12, 10h
0x1800199a3  cmovb   r12, rbx
0x1800199a7  call    cs:__imp_CoTaskMemAlloc
0x1800199ad  mov     rbp, rax
0x1800199b0  test    rax, rax
0x1800199b3  jz      loc_180019B6B
0x1800199b9  mov     rbx, [rsi+8]
0x1800199bd  mov     rcx, r12; Size
0x1800199c0  call    cs:__imp_malloc
0x1800199c6  mov     [rbp+0], rax
0x1800199ca  mov     [rbp+8], rax
0x1800199ce  mov     [rbp+10h], r12
0x1800199d2  mov     [rbp+18h], rbx
0x1800199d6  test    rax, rax
0x1800199d9  jz      loc_180019C76
0x1800199df  mov     [rsi], r12
0x1800199e2  mov     [rsi+8], rbp
0x1800199e6  mov     rax, [rbp+10h]
0x1800199ea  cmp     rax, 10h
0x1800199ee  jb      short loc_180019A0D
0x1800199f0  mov     rcx, [rbp+8]
0x1800199f4  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800199f8  mov     [rbp+10h], rax
0x1800199fc  lea     rax, [rcx+10h]
0x180019a00  mov     [rbp+8], rax
0x180019a04  test    rcx, rcx
0x180019a07  jnz     loc_180019721
0x180019a0d  mov     edx, 64h ; 'd'; unsigned int
0x180019a12  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019a19  mov     r9d, 10h; unsigned __int16
0x180019a1f  mov     r8d, 0C0001204h; unsigned int
0x180019a25  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180019a2a  mov     rcx, r13
0x180019a2d  jmp     loc_180019728
0x180019a32  mov     rdi, [r9]
0x180019a35  mov     ecx, 20h ; ' '; cb
0x180019a3a  cmp     rdi, 18h
0x180019a3e  cmovb   rdi, rdx
0x180019a42  call    cs:__imp_CoTaskMemAlloc
0x180019a48  mov     r15, rax
0x180019a4b  test    rax, rax
0x180019a4e  jz      loc_180019BDA
0x180019a54  mov     rbx, [rsi+8]
0x180019a58  mov     rcx, rdi; Size
0x180019a5b  call    cs:__imp_malloc
0x180019a61  mov     [r15], rax
0x180019a64  mov     [r15+8], rax
0x180019a68  mov     [r15+10h], rdi
0x180019a6c  mov     [r15+18h], rbx
0x180019a70  test    rax, rax
0x180019a73  jz      loc_180019C24
0x180019a79  mov     [rsi], rdi
0x180019a7c  mov     [rsi+8], r15
0x180019a80  mov     rax, [r15+10h]
0x180019a84  cmp     rax, 18h
0x180019a88  jb      short loc_180019AA7
0x180019a8a  mov     rdi, [r15+8]
0x180019a8e  add     rax, 0FFFFFFFFFFFFFFE8h
0x180019a92  mov     [r15+10h], rax
0x180019a96  lea     rax, [rdi+18h]
0x180019a9a  mov     [r15+8], rax
0x180019a9e  test    rdi, rdi
0x180019aa1  jnz     loc_18001977E
0x180019aa7  mov     edx, 64h ; 'd'; unsigned int
0x180019aac  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019ab3  mov     r9d, 10h; unsigned __int16
0x180019ab9  mov     r8d, 0C0001204h; unsigned int
0x180019abf  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180019ac4  mov     rdi, r13
0x180019ac7  jmp     loc_1800197A5
0x180019acc  mov     r12, [rsi]
0x180019acf  mov     eax, 30h ; '0'
0x180019ad4  cmp     r12, 18h
0x180019ad8  mov     ecx, 20h ; ' '; cb
0x180019add  cmovb   r12, rax
0x180019ae1  call    cs:__imp_CoTaskMemAlloc
  ... truncated ...
```
