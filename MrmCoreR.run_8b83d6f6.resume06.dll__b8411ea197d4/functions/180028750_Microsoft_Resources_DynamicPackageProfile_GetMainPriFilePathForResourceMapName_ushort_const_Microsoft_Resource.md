# Microsoft::Resources::DynamicPackageProfile::GetMainPriFilePathForResourceMapName(ushort const *,Microsoft::Resources::StringResult *,bool *)

- ea: `0x180028750`
- end: `0x180028a64`
- name: `?GetMainPriFilePathForResourceMapName@DynamicPackageProfile@Resources@Microsoft@@UEAAJPEBGPEAVStringResult@23@PEA_N@Z`
- size: `788`
- prototype: `int(Microsoft::Resources::DynamicPackageProfile *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::StringResult *, bool *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006bc80`
- `0x18006bdb0`
- `0x1800a5150`

## callees

- `0x1800172a0`
- `0x180017960`
- `0x1800218b4`
- `0x180028750`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x180056724`
- `0x180062a00`
- `0x18006d730`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800287ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800287ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028965`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028965`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800287ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002888f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800287ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002888f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800288f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002895c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002895c`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::DynamicPackageProfile::GetMainPriFilePathForResourceMapName(
        Microsoft::Resources::StringResult ***this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::StringResult *a3,
        bool *a4)
{
  __int64 v5; // rcx
  const WCHAR *v8; // r15
  int inited; // edi
  RTL_SRWLOCK *v10; // r12
  int i; // edi
  int j; // edi
  Microsoft::Resources::StringResult *v13; // rcx
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  int v16; // ecx
  const WCHAR *v17; // r8
  int v18; // eax
  __int64 v19; // rdx
  const WCHAR *v20; // rax
  int v21; // ecx
  const WCHAR *v22; // r8
  const unsigned __int16 *Ref; // rax
  bool v24; // r9
  unsigned int DefaultPriFileForResourceMapNameWorker; // ebx
  __int64 result; // rax
  const unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // rax
  bool v29; // r8
  int bIgnoreCase; // [rsp+20h] [rbp-48h]
  void **v31; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h]
  _BYTE *v33; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v34[32]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  bool v36; // [rsp+B8h] [rbp+50h] BYREF

  v5 = *(_QWORD *)a3;
  v8 = a2;
  if ( *(_QWORD *)a3 && (*(_QWORD *)v5 || !*(_DWORD *)(v5 + 8)) && (*(_DWORD *)(v5 + 8) || !*(_QWORD *)v5) )
    *(_QWORD *)(v5 + 16) = 0;
  if ( !a2 )
    return 2147957559LL;
  if ( a4 )
    *a4 = 0;
  inited = Microsoft::Resources::DynamicPackageProfile::InitPackagesInfo((Microsoft::Resources::DynamicPackageProfile *)this);
  if ( inited < 0 )
  {
    result = 2147958100LL;
    if ( inited != -2147009196 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x486,
        (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
        (const char *)(unsigned int)inited,
        bIgnoreCase);
      return (unsigned int)inited;
    }
  }
  else
  {
    v10 = (RTL_SRWLOCK *)(this + 19);
    LOBYTE(hKey) = 1;
    v31 = (void **)(this + 19);
    AcquireSRWLockShared((PSRWLOCK)this + 19);
    for ( i = 0; i < *((_DWORD *)this + 32); ++i )
    {
      if ( CompareStringOrdinal(v8, -1, (LPCWCH)this[17][2 * i + 1], -1, 1) == 2 )
      {
        if ( a4 )
          *a4 = 1;
        v8 = (const WCHAR *)this[17][2 * i];
        break;
      }
    }
    for ( j = 0; j < *((_DWORD *)this + 25); ++j )
    {
      v13 = this[13][j];
      if ( v13 )
      {
        v14 = *(_QWORD *)v13;
        if ( v14 && (*(_QWORD *)v14 || !*(_DWORD *)(v14 + 8)) && (*(_DWORD *)(v14 + 8) || !*(_QWORD *)v14) )
        {
          v15 = *(const WCHAR **)(v14 + 16);
          v16 = 0;
        }
        else
        {
          v15 = 0;
          v16 = -2147024809;
        }
        v17 = 0;
        if ( v16 >= 0 )
          v17 = v15;
        v18 = CompareStringOrdinal(v8, -1, v17, -1, 0);
        if ( !(unsigned int)IntToComparison((unsigned int)(v18 - 2)) )
          goto LABEL_40;
        if ( (v19 = *((_QWORD *)this[13][j] + 4)) != 0
          && (*(_QWORD *)v19 || !*(_DWORD *)(v19 + 8))
          && (*(_DWORD *)(v19 + 8) || !*(_QWORD *)v19) )
        {
          v20 = *(const WCHAR **)(v19 + 16);
          v21 = 0;
        }
        else
        {
          v20 = 0;
          v21 = -2147024809;
        }
        v22 = 0;
        if ( v21 >= 0 )
          v22 = v20;
        if ( CompareStringOrdinal(v8, -1, v22, -1, 1) == 2 )
        {
LABEL_40:
          ((void (__fastcall *)(Microsoft::Resources::StringResult ***))(*this)[46])(this);
          Ref = Microsoft::Resources::StringResult::GetRef(this[13][j]);
          hKey = 0;
          v31 = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
          DefaultPriFileForResourceMapNameWorker = Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapNameWorker(
                                                     0,
                                                     Ref,
                                                     (struct Microsoft::Resources::IProfileHelpers *)&v31,
                                                     v24,
                                                     a3);
          v31 = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_42;
        }
      }
    }
    DefStringResult_InitBuf(v34);
    v36 = 0;
    v33 = v34;
    v27 = Microsoft::Resources::StringResult::GetRef(*this[13]);
    if ( (int)Microsoft::Resources::StateRepositoryHelper::HasOptionalDependency(
                v27,
                v8,
                &v36,
                (struct Microsoft::Resources::StringResult *)&v33) < 0
      || !v36
      || (((void (__fastcall *)(Microsoft::Resources::StringResult ***))(*this)[46])(this),
          v28 = Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)&v33),
          Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapName(0, v28, v29, a3) < 0) )
    {
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v33);
      DefaultPriFileForResourceMapNameWorker = -2147009737;
LABEL_42:
      ReleaseSRWLockShared(v10);
      return DefaultPriFileForResourceMapNameWorker;
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v33);
    Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock((Microsoft::Resources::AutoReaderWriterLock *)&v31);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180028750  push    rbp
0x180028752  push    rbx
0x180028753  push    rsi
0x180028754  push    rdi
0x180028755  push    r12
0x180028757  push    r13
0x180028759  push    r14
0x18002875b  push    r15
0x18002875d  mov     rbp, rsp
0x180028760  sub     rsp, 68h
0x180028764  mov     rbx, rcx
0x180028767  xor     r14d, r14d
0x18002876a  mov     rcx, [r8]
0x18002876d  mov     rsi, r9
0x180028770  mov     r13, r8
0x180028773  mov     r15, rdx
0x180028776  test    rcx, rcx
0x180028779  jz      short loc_180028795
0x18002877b  cmp     [rcx], r14
0x18002877e  jnz     short loc_180028786
0x180028780  cmp     [rcx+8], r14d
0x180028784  ja      short loc_180028795
0x180028786  cmp     [rcx+8], r14d
0x18002878a  jnz     short loc_180028791
0x18002878c  cmp     [rcx], r14
0x18002878f  jnz     short loc_180028795
0x180028791  mov     [rcx+10h], r14
0x180028795  test    r15, r15
0x180028798  jz      loc_180028A5A
0x18002879e  test    rsi, rsi
0x1800287a1  jz      short loc_1800287A6
0x1800287a3  mov     [r9], r14b
0x1800287a6  mov     rcx, rbx; this
0x1800287a9  call    ?InitPackagesInfo@DynamicPackageProfile@Resources@Microsoft@@IEAAJXZ; Microsoft::Resources::DynamicPackageProfile::InitPackagesInfo(void)
0x1800287ae  mov     edi, eax
0x1800287b0  test    eax, eax
0x1800287b2  js      loc_180028A2E
0x1800287b8  lea     r12, [rbx+98h]
0x1800287bf  mov     byte ptr [rbp+hKey], 1
0x1800287c3  mov     rcx, r12; SRWLock
0x1800287c6  mov     [rbp+var_38], r12
0x1800287ca  call    cs:__imp_AcquireSRWLockShared
0x1800287d0  mov     edi, r14d
0x1800287d3  cmp     edi, [rbx+80h]
0x1800287d9  jge     short loc_180028823
0x1800287db  mov     r8, [rbx+88h]
0x1800287e2  or      r9d, 0FFFFFFFFh; cchCount2
0x1800287e6  movsxd  r14, edi
0x1800287e9  or      edx, r9d; cchCount1
0x1800287ec  add     r14, r14
0x1800287ef  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800287f7  mov     rcx, r15; lpString1
0x1800287fa  mov     r8, [r8+r14*8+8]; lpString2
0x1800287ff  call    cs:__imp_CompareStringOrdinal
0x180028805  lea     ecx, [rax-2]
0x180028808  test    ecx, ecx
0x18002880a  jz      short loc_180028810
0x18002880c  inc     edi
0x18002880e  jmp     short loc_1800287D3
0x180028810  test    rsi, rsi
0x180028813  jz      short loc_180028818
0x180028815  mov     byte ptr [rsi], 1
0x180028818  mov     rax, [rbx+88h]
0x18002881f  mov     r15, [rax+r14*8]
0x180028823  xor     r14d, r14d
0x180028826  mov     edi, r14d
0x180028829  cmp     edi, [rbx+64h]
0x18002882c  jge     loc_180028998
0x180028832  mov     rax, [rbx+68h]
0x180028836  movsxd  rsi, edi
0x180028839  mov     rcx, [rax+rsi*8]
0x18002883d  test    rcx, rcx
0x180028840  jz      loc_180028902
0x180028846  mov     rcx, [rcx]
0x180028849  test    rcx, rcx
0x18002884c  jz      loc_18002897E
0x180028852  cmp     [rcx], r14
0x180028855  jnz     short loc_180028861
0x180028857  cmp     [rcx+8], r14d
0x18002885b  ja      loc_18002897E
0x180028861  cmp     [rcx+8], r14d
0x180028865  jnz     short loc_180028870
0x180028867  cmp     [rcx], r14
0x18002886a  jnz     loc_18002897E
0x180028870  mov     rax, [rcx+10h]
0x180028874  mov     ecx, r14d
0x180028877  test    ecx, ecx
0x180028879  mov     [rsp+68h+bIgnoreCase], r14d; bIgnoreCase
0x18002887e  mov     r8, r14
0x180028881  mov     rcx, r15; lpString1
0x180028884  cmovns  r8, rax; lpString2
0x180028888  or      r9d, 0FFFFFFFFh; cchCount2
0x18002888c  or      edx, r9d; cchCount1
0x18002888f  call    cs:__imp_CompareStringOrdinal
0x180028895  lea     ecx, [rax-2]
0x180028898  call    _IntToComparison
0x18002889d  test    eax, eax
0x18002889f  jz      short loc_180028909
0x1800288a1  mov     rax, [rbx+68h]
0x1800288a5  mov     rcx, [rax+rsi*8]
0x1800288a9  mov     rdx, [rcx+20h]
0x1800288ad  test    rdx, rdx
0x1800288b0  jz      loc_18002898B
0x1800288b6  cmp     [rdx], r14
0x1800288b9  jnz     short loc_1800288C5
0x1800288bb  cmp     [rdx+8], r14d
0x1800288bf  ja      loc_18002898B
0x1800288c5  cmp     [rdx+8], r14d
0x1800288c9  jnz     short loc_1800288D4
0x1800288cb  cmp     [rdx], r14
0x1800288ce  jnz     loc_18002898B
0x1800288d4  mov     rax, [rdx+10h]
0x1800288d8  mov     ecx, r14d
0x1800288db  test    ecx, ecx
0x1800288dd  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800288e5  mov     r8, r14
0x1800288e8  mov     rcx, r15; lpString1
0x1800288eb  cmovns  r8, rax; lpString2
0x1800288ef  or      edx, 0FFFFFFFFh; cchCount1
0x1800288f2  mov     r9d, edx; cchCount2
0x1800288f5  call    cs:__imp_CompareStringOrdinal
0x1800288fb  lea     ecx, [rax-2]
0x1800288fe  test    ecx, ecx
0x180028900  jz      short loc_180028909
0x180028902  inc     edi
0x180028904  jmp     loc_180028829
0x180028909  mov     rax, [rbx]
0x18002890c  mov     rcx, rbx
0x18002890f  mov     rax, [rax+170h]
0x180028916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002891b  mov     rcx, [rbx+68h]
0x18002891f  mov     r9b, al
0x180028922  mov     rcx, [rcx+rsi*8]; this
0x180028926  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x18002892b  lea     rdi, ??_7WindowsClientProfileBaseHelpers@Resources@Microsoft@@6B@; const Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable'
0x180028932  mov     [rbp+hKey], r14
0x180028936  mov     rdx, rax; unsigned __int16 *
0x180028939  mov     [rbp+var_38], rdi
0x18002893d  lea     r8, [rbp+var_38]; struct Microsoft::Resources::IProfileHelpers *
0x180028941  mov     qword ptr [rsp+68h+bIgnoreCase], r13; struct Microsoft::Resources::StringResult *
0x180028946  xor     ecx, ecx; unsigned __int16 *
0x180028948  call    ?GetDefaultPriFileForResourceMapNameWorker@WindowsClientProfileBase@Resources@Microsoft@@SAJPEBG0PEAVIProfileHelpers@23@_NPEAVStringResult@23@@Z; Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapNameWorker(ushort const *,ushort const *,Microsoft::Resources::IProfileHelpers *,bool,Microsoft::Resources::StringResult *)
0x18002894d  mov     rcx, [rbp+hKey]; hKey
0x180028951  mov     ebx, eax
0x180028953  mov     [rbp+var_38], rdi
0x180028957  test    rcx, rcx
0x18002895a  jz      short loc_180028962
0x18002895c  call    cs:__imp_RegCloseKey
0x180028962  mov     rcx, r12; SRWLock
0x180028965  call    cs:__imp_ReleaseSRWLockShared
0x18002896b  mov     eax, ebx
0x18002896d  add     rsp, 68h
0x180028971  pop     r15
0x180028973  pop     r14
0x180028975  pop     r13
0x180028977  pop     r12
0x180028979  pop     rdi
0x18002897a  pop     rsi
0x18002897b  pop     rbx
0x18002897c  pop     rbp
0x18002897d  retn
0x18002897e  mov     rax, r14
0x180028981  mov     ecx, 80070057h
0x180028986  jmp     loc_180028877
0x18002898b  mov     rax, r14
0x18002898e  mov     ecx, 80070057h
0x180028993  jmp     loc_1800288DB
0x180028998  lea     rcx, [rbp+var_20]
0x18002899c  call    DefStringResult_InitBuf
0x1800289a1  lea     rcx, [rbp+var_20]
0x1800289a5  mov     [rbp+arg_8], r14b
0x1800289a9  mov     [rbp+var_28], rcx
0x1800289ad  mov     rcx, [rbx+68h]
0x1800289b1  mov     rcx, [rcx]; this
0x1800289b4  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800289b9  mov     rdx, r15; unsigned __int16 *
0x1800289bc  lea     r9, [rbp+var_28]; struct Microsoft::Resources::StringResult *
0x1800289c0  mov     rcx, rax; unsigned __int16 *
0x1800289c3  lea     r8, [rbp+arg_8]; bool *
0x1800289c7  call    ?HasOptionalDependency@StateRepositoryHelper@Resources@Microsoft@@SAJPEBG0PEA_NPEAVStringResult@23@@Z; Microsoft::Resources::StateRepositoryHelper::HasOptionalDependency(ushort const *,ushort const *,bool *,Microsoft::Resources::StringResult *)
0x1800289cc  test    eax, eax
0x1800289ce  jns     short loc_1800289E0
0x1800289d0  lea     rcx, [rbp+var_28]; this
0x1800289d4  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800289d9  mov     ebx, 80073B37h
0x1800289de  jmp     short loc_180028962
0x1800289e0  cmp     [rbp+arg_8], r14b
0x1800289e4  jz      short loc_1800289D0
0x1800289e6  mov     rax, [rbx]
0x1800289e9  mov     rcx, rbx
0x1800289ec  mov     rax, [rax+170h]
0x1800289f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f8  lea     rcx, [rbp+var_28]; this
0x1800289fc  mov     r8b, al
0x1800289ff  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180028a04  mov     rdx, rax; unsigned __int16 *
0x180028a07  mov     r9, r13; struct Microsoft::Resources::StringResult *
0x180028a0a  xor     ecx, ecx; unsigned __int16 *
0x180028a0c  call    ?GetDefaultPriFileForResourceMapName@WindowsClientProfileBase@Resources@Microsoft@@SAJPEBG0_NPEAVStringResult@23@@Z; Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapName(ushort const *,ushort const *,bool,Microsoft::Resources::StringResult *)
0x180028a11  test    eax, eax
0x180028a13  js      short loc_1800289D0
0x180028a15  lea     rcx, [rbp+var_28]; this
0x180028a19  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180028a1e  lea     rcx, [rbp+var_38]; this
0x180028a22  call    ??1AutoReaderWriterLock@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::AutoReaderWriterLock::~AutoReaderWriterLock(void)
0x180028a27  xor     eax, eax
0x180028a29  jmp     loc_18002896D
0x180028a2e  mov     eax, 80073D54h
0x180028a33  cmp     edi, eax
0x180028a35  jz      loc_18002896D
0x180028a3b  mov     rcx, [rbp+40h]; this
0x180028a3f  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x180028a46  mov     r9d, edi; char *
0x180028a49  mov     edx, 486h; void *
0x180028a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a53  mov     eax, edi
0x180028a55  jmp     loc_18002896D
0x180028a5a  mov     eax, 80073B37h
0x180028a5f  jmp     loc_18002896D
```
