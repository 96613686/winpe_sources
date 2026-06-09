# ipx::mtf::TransportLib_DeserializeFromStream(IUnknown *,IUnknown * *,bool)

- ea: `0x180023e18`
- end: `0x1800243e9`
- name: `?TransportLib_DeserializeFromStream@mtf@ipx@@YAJPEAUIUnknown@@PEAPEAU3@_N@Z`
- size: `1489`
- prototype: `__int64 __fastcall(ipx::mtf *__hidden this, struct IUnknown *, struct IUnknown **, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f850`
- `0x1800215c0`
- `0x180022c0c`

## callees

- `0x180006054`
- `0x180006074`
- `0x180023e18`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800240e7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800240e7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800240f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800240f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002400b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002400b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ipx::mtf::TransportLib_DeserializeFromStream(
        __int64 (__fastcall ***this)(ipx::mtf *, GUID *, LPSTREAM *),
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  __int64 (__fastcall *v4)(ipx::mtf *, GUID *, LPSTREAM *); // rax
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  HGLOBAL v13; // rax
  const char *v14; // r9
  void *v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  HRESULT v18; // edi
  __int64 v19; // rcx
  __int64 v21; // rcx
  LPSTREAM v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  LPSTREAM v25; // rcx
  int v26; // eax
  LPSTREAM v27; // rcx
  LPSTREAM v28; // rcx
  __int64 *v29; // rax
  LPSTREAM v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  LPSTREAM v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  LPSTREAM v36; // rcx
  LPSTREAM v37; // rcx
  int v38; // [rsp+20h] [rbp-50h]
  LPSTREAM ppstm; // [rsp+30h] [rbp-40h] BYREF
  __int64 v40; // [rsp+38h] [rbp-38h] BYREF
  int v41[2]; // [rsp+40h] [rbp-30h] BYREF
  int v42; // [rsp+48h] [rbp-28h] BYREF
  SIZE_T dwBytes; // [rsp+50h] [rbp-20h] BYREF
  __int128 v44; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  ppstm = 0;
  v4 = **this;
  if ( (_BYTE)a3 )
  {
    v40 = 0;
    v5 = v4((ipx::mtf *)this, &GUID_0000000c_0000_0000_c000_000000000046, (LPSTREAM *)&v40);
    LastError = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v5,
        v38);
      v7 = v40;
      v40 = 0;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      ppstm = 0;
      return LastError;
    }
    dwBytes = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, SIZE_T *))(*(_QWORD *)v40 + 40LL))(v40, 0, 2, &dwBytes);
    LastError = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v8,
        v38);
      v9 = v40;
      v40 = 0;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      ppstm = 0;
      return LastError;
    }
    if ( HIDWORD(dwBytes) )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)0x8007000ELL,
        v38);
      v10 = v40;
      v40 = 0;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      ppstm = 0;
      return LastError;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v40 + 40LL))(v40, 0, 0, 0);
    LastError = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v11,
        v38);
      v12 = v40;
      v40 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      ppstm = 0;
      return LastError;
    }
    v13 = GlobalAlloc(0, (unsigned int)dwBytes);
    v15 = v13;
    if ( !v13 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x54,
                    (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
                    v14);
      v16 = v40;
      v40 = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      ppstm = 0;
      return LastError;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, HGLOBAL, _QWORD, _QWORD))(*(_QWORD *)v40 + 24LL))(
            v40,
            v13,
            (unsigned int)dwBytes,
            0);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v17,
        v38);
      v19 = v40;
      v40 = 0;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      ppstm = 0;
      return (unsigned int)v18;
    }
    v18 = CreateStreamOnHGlobal(v15, 1, &ppstm);
    if ( v18 < 0 )
    {
      GlobalFree(v15);
      v21 = v40;
      v40 = 0;
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      v22 = ppstm;
      ppstm = 0;
      if ( v22 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v22 + 16LL))(v22);
      return (unsigned int)v18;
    }
    v23 = v40;
    v40 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  else
  {
    v26 = v4((ipx::mtf *)this, &GUID_0000000c_0000_0000_c000_000000000046, &ppstm);
    LastError = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)(unsigned int)v26,
        v38);
      v27 = ppstm;
      ppstm = 0;
      if ( v27 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v27 + 16LL))(v27);
      return LastError;
    }
  }
  v44 = 0;
  v42 = 0;
  v24 = (*(__int64 (__fastcall **)(LPSTREAM, __int128 *, __int64, int *))(*(_QWORD *)ppstm + 24LL))(
          ppstm,
          &v44,
          16,
          &v42);
  LastError = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
      (const char *)(unsigned int)v24,
      v38);
    v25 = ppstm;
    ppstm = 0;
    if ( v25 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v25 + 16LL))(v25);
    return LastError;
  }
  if ( v42 != 16 )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
      (const char *)0x80004005LL,
      v38);
    v28 = ppstm;
    ppstm = 0;
    if ( v28 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v28 + 16LL))(v28);
    return LastError;
  }
  v29 = qword_18003E5D0;
  while ( *(_OWORD *)v29 != v44 )
  {
    v29 += 2;
    if ( v29 == qword_18003F210 )
    {
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
        (const char *)0x80070057LL,
        v38);
      v30 = ppstm;
      ppstm = 0;
      if ( v30 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v30 + 16LL))(v30);
      return LastError;
    }
  }
  *(_QWORD *)v41 = 0;
  v31 = ((__int64 (__fastcall *)(__int128 *, _QWORD, __int64, GUID *))Hooked_CoCreateInstance)(
          &v44,
          0,
          1,
          &GUID_06445657_3a07_492d_94c3_052034ef2d12);
  LastError = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
      (const char *)(unsigned int)v31,
      (int)v41);
    v32 = *(_QWORD *)v41;
    *(_QWORD *)v41 = 0;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v33 = ppstm;
    ppstm = 0;
    if ( v33 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v33 + 16LL))(v33);
    return LastError;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM))(**(_QWORD **)v41 + 40LL))(*(_QWORD *)v41, ppstm);
  LastError = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\serialize.cpp",
      (const char *)(unsigned int)v34,
      (int)v41);
    v35 = *(_QWORD *)v41;
    *(_QWORD *)v41 = 0;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v36 = ppstm;
    ppstm = 0;
    if ( v36 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v36 + 16LL))(v36);
    return LastError;
  }
  a2->lpVtbl = *(struct IUnknownVtbl **)v41;
  *(_QWORD *)v41 = 0;
  v37 = ppstm;
  ppstm = 0;
  if ( v37 )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v37 + 16LL))(v37);
  return 0;
}

```

## disassembly

```asm
0x180023e18  mov     [rsp-18h+arg_10], rbx
0x180023e1d  mov     [rsp-18h+arg_18], rsi
0x180023e22  push    rbp
0x180023e23  push    rdi
0x180023e24  push    r14
0x180023e26  mov     rbp, rsp
0x180023e29  sub     rsp, 70h
0x180023e2d  mov     rax, cs:__security_cookie
0x180023e34  xor     rax, rsp
0x180023e37  mov     [rbp+var_8], rax
0x180023e3b  mov     rsi, rdx
0x180023e3e  xor     r14d, r14d
0x180023e41  mov     [rbp+ppstm], r14
0x180023e45  mov     rax, [rcx]
0x180023e48  mov     rax, [rax]
0x180023e4b  test    r8b, r8b
0x180023e4e  jz      loc_1800241B8
0x180023e54  mov     [rbp+var_38], r14
0x180023e58  lea     r8, [rbp+var_38]
0x180023e5c  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180023e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e68  mov     ebx, eax
0x180023e6a  test    eax, eax
0x180023e6c  jns     short loc_180023EBF
0x180023e6e  mov     rcx, [rbp+18h]; this
0x180023e72  mov     r9d, eax; char *
0x180023e75  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023e7c  lea     edx, [r14+4Ah]; void *
0x180023e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e85  nop
0x180023e86  mov     rcx, [rbp+var_38]
0x180023e8a  mov     [rbp+var_38], r14
0x180023e8e  test    rcx, rcx
0x180023e91  jz      short loc_180023EA0
0x180023e93  mov     rax, [rcx]
0x180023e96  mov     rax, [rax+10h]
0x180023e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e9f  nop
0x180023ea0  mov     rcx, [rbp+ppstm]
0x180023ea4  mov     [rbp+ppstm], r14
0x180023ea8  test    rcx, rcx
0x180023eab  jz      short loc_180023EBA
0x180023ead  mov     rax, [rcx]
0x180023eb0  mov     rax, [rax+10h]
0x180023eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb9  nop
0x180023eba  jmp     loc_1800242AC
0x180023ebf  mov     [rbp+dwBytes], r14
0x180023ec3  mov     rcx, [rbp+var_38]
0x180023ec7  mov     rdx, r14
0x180023eca  mov     rax, [rcx]
0x180023ecd  lea     r9, [rbp+dwBytes]
0x180023ed1  mov     r8d, 2
0x180023ed7  mov     rax, [rax+28h]
0x180023edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ee0  mov     ebx, eax
0x180023ee2  test    eax, eax
0x180023ee4  jns     short loc_180023F38
0x180023ee6  mov     rcx, [rbp+18h]; this
0x180023eea  mov     r9d, eax; char *
0x180023eed  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023ef4  mov     edx, 4Eh ; 'N'; void *
0x180023ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023efe  nop
0x180023eff  mov     rcx, [rbp+var_38]
0x180023f03  mov     [rbp+var_38], r14
0x180023f07  test    rcx, rcx
0x180023f0a  jz      short loc_180023F19
0x180023f0c  mov     rax, [rcx]
0x180023f0f  mov     rax, [rax+10h]
0x180023f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f18  nop
0x180023f19  mov     rcx, [rbp+ppstm]
0x180023f1d  mov     [rbp+ppstm], r14
0x180023f21  test    rcx, rcx
0x180023f24  jz      short loc_180023F33
0x180023f26  mov     rax, [rcx]
0x180023f29  mov     rax, [rax+10h]
0x180023f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f32  nop
0x180023f33  jmp     loc_1800242AC
0x180023f38  cmp     dword ptr [rbp+dwBytes+4], r14d
0x180023f3c  jz      short loc_180023F95
0x180023f3e  mov     rcx, [rbp+18h]; this
0x180023f42  mov     ebx, 8007000Eh
0x180023f47  mov     r9d, ebx; char *
0x180023f4a  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023f51  mov     edx, 4Fh ; 'O'; void *
0x180023f56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f5b  nop
0x180023f5c  mov     rcx, [rbp+var_38]
0x180023f60  mov     [rbp+var_38], r14
0x180023f64  test    rcx, rcx
0x180023f67  jz      short loc_180023F76
0x180023f69  mov     rax, [rcx]
0x180023f6c  mov     rax, [rax+10h]
0x180023f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f75  nop
0x180023f76  mov     rcx, [rbp+ppstm]
0x180023f7a  mov     [rbp+ppstm], r14
0x180023f7e  test    rcx, rcx
0x180023f81  jz      short loc_180023F90
0x180023f83  mov     rdx, [rcx]
0x180023f86  mov     rax, [rdx+10h]
0x180023f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f8f  nop
0x180023f90  jmp     loc_1800242AC
0x180023f95  mov     rcx, [rbp+var_38]
0x180023f99  mov     rdx, r14
0x180023f9c  mov     rax, [rcx]
0x180023f9f  xor     r9d, r9d
0x180023fa2  xor     r8d, r8d
0x180023fa5  mov     rax, [rax+28h]
0x180023fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fae  mov     ebx, eax
0x180023fb0  test    eax, eax
0x180023fb2  jns     short loc_180024006
0x180023fb4  mov     rcx, [rbp+18h]; this
0x180023fb8  mov     r9d, eax; char *
0x180023fbb  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180023fc2  mov     edx, 51h ; 'Q'; void *
0x180023fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fcc  nop
0x180023fcd  mov     rcx, [rbp+var_38]
0x180023fd1  mov     [rbp+var_38], r14
0x180023fd5  test    rcx, rcx
0x180023fd8  jz      short loc_180023FE7
0x180023fda  mov     rax, [rcx]
0x180023fdd  mov     rax, [rax+10h]
0x180023fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fe6  nop
0x180023fe7  mov     rcx, [rbp+ppstm]
0x180023feb  mov     [rbp+ppstm], r14
0x180023fef  test    rcx, rcx
0x180023ff2  jz      short loc_180024001
0x180023ff4  mov     rax, [rcx]
0x180023ff7  mov     rax, [rax+10h]
0x180023ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024000  nop
0x180024001  jmp     loc_1800242AC
0x180024006  mov     edx, dword ptr [rbp+dwBytes]; dwBytes
0x180024009  xor     ecx, ecx; uFlags
0x18002400b  call    cs:__imp_GlobalAlloc
0x180024011  mov     rbx, rax
0x180024014  test    rax, rax
0x180024017  jnz     short loc_180024067
0x180024019  mov     rcx, [rbp+18h]; this
0x18002401d  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180024024  lea     edx, [rax+54h]; void *
0x180024027  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002402c  mov     ebx, eax
0x18002402e  mov     rcx, [rbp+var_38]
0x180024032  mov     [rbp+var_38], r14
0x180024036  test    rcx, rcx
0x180024039  jz      short loc_180024048
0x18002403b  mov     rdx, [rcx]
0x18002403e  mov     rax, [rdx+10h]
0x180024042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024047  nop
0x180024048  mov     rcx, [rbp+ppstm]
0x18002404c  mov     [rbp+ppstm], r14
0x180024050  test    rcx, rcx
0x180024053  jz      short loc_180024062
0x180024055  mov     rax, [rcx]
0x180024058  mov     rax, [rax+10h]
0x18002405c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024061  nop
0x180024062  jmp     loc_1800242AC
0x180024067  mov     rcx, [rbp+var_38]
0x18002406b  mov     rax, [rcx]
0x18002406e  xor     r9d, r9d
0x180024071  mov     r8d, dword ptr [rbp+dwBytes]
0x180024075  mov     rdx, rbx
0x180024078  mov     rax, [rax+18h]
0x18002407c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024081  mov     edi, eax
0x180024083  test    eax, eax
0x180024085  jns     short loc_1800240DB
0x180024087  mov     rcx, [rbp+18h]; this
0x18002408b  mov     r9d, eax; char *
0x18002408e  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180024095  mov     edx, 56h ; 'V'; void *
0x18002409a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002409f  nop
0x1800240a0  mov     rcx, [rbp+var_38]
0x1800240a4  mov     [rbp+var_38], r14
0x1800240a8  test    rcx, rcx
0x1800240ab  jz      short loc_1800240BA
0x1800240ad  mov     rax, [rcx]
0x1800240b0  mov     rax, [rax+10h]
0x1800240b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240b9  nop
0x1800240ba  mov     rcx, [rbp+ppstm]
0x1800240be  mov     [rbp+ppstm], r14
0x1800240c2  test    rcx, rcx
0x1800240c5  jz      short loc_1800240D4
0x1800240c7  mov     rax, [rcx]
0x1800240ca  mov     rax, [rax+10h]
0x1800240ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240d3  nop
0x1800240d4  mov     eax, edi
0x1800240d6  jmp     loc_1800242AE
0x1800240db  lea     r8, [rbp+ppstm]; ppstm
0x1800240df  mov     edx, 1; fDeleteOnRelease
0x1800240e4  mov     rcx, rbx; hGlobal
0x1800240e7  call    cs:__imp_CreateStreamOnHGlobal
0x1800240ed  mov     edi, eax
0x1800240ef  test    eax, eax
0x1800240f1  jns     short loc_180024133
0x1800240f3  mov     rcx, rbx; hMem
0x1800240f6  call    cs:__imp_GlobalFree
0x1800240fc  nop
0x1800240fd  mov     rcx, [rbp+var_38]
0x180024101  mov     [rbp+var_38], r14
0x180024105  test    rcx, rcx
0x180024108  jz      short loc_180024117
0x18002410a  mov     rdx, [rcx]
0x18002410d  mov     rax, [rdx+10h]
0x180024111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024116  nop
0x180024117  mov     rcx, [rbp+ppstm]
0x18002411b  mov     [rbp+ppstm], r14
0x18002411f  test    rcx, rcx
0x180024122  jz      short loc_180024131
0x180024124  mov     rax, [rcx]
0x180024127  mov     rax, [rax+10h]
0x18002412b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024130  nop
0x180024131  jmp     short loc_1800240D4
0x180024133  mov     rcx, [rbp+var_38]
0x180024137  mov     [rbp+var_38], r14
0x18002413b  test    rcx, rcx
0x18002413e  jz      short loc_18002414D
0x180024140  mov     rax, [rcx]
0x180024143  mov     rax, [rax+10h]
0x180024147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002414c  nop
0x18002414d  xorps   xmm0, xmm0
0x180024150  movups  [rbp+var_18], xmm0
0x180024154  mov     [rbp+var_28], r14d
0x180024158  mov     rcx, [rbp+ppstm]
0x18002415c  mov     rax, [rcx]
0x18002415f  lea     r9, [rbp+var_28]
0x180024163  mov     r8d, 10h
0x180024169  lea     rdx, [rbp+var_18]
0x18002416d  mov     rax, [rax+18h]
0x180024171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024176  mov     ebx, eax
0x180024178  test    eax, eax
0x18002417a  jns     loc_18002420A
0x180024180  mov     rcx, [rbp+18h]; this
0x180024184  mov     r9d, eax; char *
0x180024187  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002418e  mov     edx, 66h ; 'f'; void *
0x180024193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024198  nop
0x180024199  mov     rcx, [rbp+ppstm]
0x18002419d  mov     [rbp+ppstm], r14
0x1800241a1  test    rcx, rcx
0x1800241a4  jz      short loc_1800241B3
0x1800241a6  mov     rax, [rcx]
0x1800241a9  mov     rax, [rax+10h]
0x1800241ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241b2  nop
0x1800241b3  jmp     loc_1800242AC
0x1800241b8  lea     r8, [rbp+ppstm]
0x1800241bc  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800241c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241c8  mov     ebx, eax
0x1800241ca  test    eax, eax
0x1800241cc  jns     loc_18002414D
0x1800241d2  mov     rcx, [rbp+18h]; this
0x1800241d6  mov     r9d, eax; char *
0x1800241d9  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800241e0  mov     edx, 61h ; 'a'; void *
0x1800241e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800241ea  nop
0x1800241eb  mov     rcx, [rbp+ppstm]
0x1800241ef  mov     [rbp+ppstm], r14
0x1800241f3  test    rcx, rcx
0x1800241f6  jz      short loc_180024205
0x1800241f8  mov     rax, [rcx]
0x1800241fb  mov     rax, [rax+10h]
0x1800241ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024204  nop
0x180024205  jmp     loc_1800242AC
0x18002420a  cmp     [rbp+var_28], 10h
0x18002420e  jz      short loc_18002424A
0x180024210  mov     rcx, [rbp+18h]; this
0x180024214  mov     ebx, 80004005h
0x180024219  mov     r9d, ebx; char *
0x18002421c  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\internal"...
0x180024223  mov     edx, 67h ; 'g'; void *
0x180024228  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002422d  nop
0x18002422e  mov     rcx, [rbp+ppstm]
0x180024232  mov     [rbp+ppstm], r14
0x180024236  test    rcx, rcx
0x180024239  jz      short loc_180024248
0x18002423b  mov     rdx, [rcx]
  ... truncated ...
```
