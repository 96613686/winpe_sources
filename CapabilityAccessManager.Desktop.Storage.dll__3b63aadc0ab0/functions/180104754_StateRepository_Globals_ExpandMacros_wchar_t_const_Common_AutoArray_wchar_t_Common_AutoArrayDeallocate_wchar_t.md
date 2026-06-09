# StateRepository::Globals::ExpandMacros(wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)

- ea: `0x180104754`
- end: `0x180104b37`
- name: `?ExpandMacros@Globals@StateRepository@@YAJPEB_WAEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@Common@@@Z`
- size: `995`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801052a8`

## callees

- `0x1800038f0`
- `0x1800e4c28`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800fb7b4`
- `0x1801025a4`
- `0x1801027d0`
- `0x180104754`
- `0x180104d04`
- `0x180109fac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801047b0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801047b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104825`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104897`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010492d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104980`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104897`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010492d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180104980`

## string_xrefs

- `0x1801048fa`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18010493c`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18010495e`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801049c9`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180104a44`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180104b25`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180104901`: `Required configuration data not found: %ws`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::ExpandMacros(__int64 a1, void **a2)
{
  __int64 v2; // rax
  _WORD *v4; // rdi
  char v5; // r13
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r15
  const wchar_t *v8; // rbx
  wchar_t *v9; // rax
  const WCHAR *v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r15
  const struct Common::StateSeparationRedirectionMapping *v15; // rcx
  unsigned __int64 v16; // r8
  const unsigned __int16 *v17; // r9
  wchar_t *v18; // rbx
  int RegKeyContainingValue; // edi
  int Setting; // eax
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rsi
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rax
  _WORD *v26; // rax
  _WORD *v27; // rbx
  __int64 v29; // r9
  __int64 v30; // rax
  _WORD *v31; // rdx
  _WORD *v32; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-30h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-30h]
  unsigned __int16 *v35; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v36[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF
  void *Block; // [rsp+A8h] [rbp+58h]

  v2 = a1;
  v36[0] = 0;
  v4 = 0;
  v36[1] = 0;
  if ( !a1 )
    goto LABEL_38;
  v5 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a1 + 2 * v6) );
  v7 = 0;
  if ( !v6 )
    goto LABEL_38;
  while ( 1 )
  {
    v8 = (const wchar_t *)(v2 + 2 * v7);
    v9 = wcschr(v8, 0x25u);
    v10 = v9;
    if ( !v9 )
    {
      if ( v5 )
      {
        if ( v7 < v6 )
        {
          v11 = StateRepository::Text::Append((StateRepository::Text *)v36, (const wchar_t *)(a1 + 2 * v7), v6 - v7);
          v12 = v11;
          if ( v11 < 0 )
          {
            v13 = 1443;
            goto LABEL_36;
          }
        }
      }
LABEL_37:
      v4 = (_WORD *)v36[0];
LABEL_38:
      if ( !v4 )
      {
        if ( *a2 )
        {
          operator delete(*a2);
          *a2 = 0;
        }
LABEL_61:
        StateRepository::TextA::Reset((StateRepository::TextA *)v36);
        return 0;
      }
      v23 = -1;
      do
        ++v23;
      while ( v4[v23] );
      v24 = v23 + 1;
      v25 = 2 * v24;
      if ( !is_mul_ok(v24, 2u) )
        v25 = -1;
      v26 = operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
      v27 = v26;
      if ( !v26 )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B0,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCase);
        operator delete(0);
        goto LABEL_47;
      }
      if ( v24 )
      {
        if ( v24 <= 0x7FFFFFFF )
        {
          v30 = 2147483646;
          v31 = v27;
          do
          {
            if ( !v30 )
              break;
            if ( !*v4 )
              break;
            *v31++ = *v4++;
            --v30;
            --v24;
          }
          while ( v24 );
          v32 = v31 - 1;
          v29 = v24 == 0 ? 0x8007007A : 0;
          if ( v24 )
            v32 = v31;
          *v32 = 0;
          if ( v24 )
          {
            if ( *a2 != v27 )
            {
              operator delete(*a2);
              *a2 = v27;
            }
            operator delete(0);
            goto LABEL_61;
          }
        }
        else
        {
          v29 = 2147942487LL;
          *v26 = 0;
        }
      }
      else
      {
        v29 = 2147942487LL;
      }
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x5B1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)v29,
        bIgnoreCase);
    }
    if ( v9 > v8 )
    {
      v11 = StateRepository::Text::Append((StateRepository::Text *)v36, v8, v9 - v8);
      v12 = v11;
      if ( v11 < 0 )
      {
        v13 = 1420;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)(unsigned int)v11,
          bIgnoreCase);
        goto LABEL_47;
      }
    }
    v14 = ((__int64)v10 - a1) >> 1;
    if ( (unsigned int)(v6 - v14) < 0xF || CompareStringOrdinal(v10, 15, L"%AppRepository%", 15, 1) != 2 )
    {
      v12 = -2140733437;
      goto LABEL_47;
    }
    hKey = 0;
    v18 = 0;
    Block = 0;
    v35 = 0;
    RegKeyContainingValue = Common::StateSeparation::GetRegKeyContainingValue(
                              v15,
                              (const unsigned __int16 **)&v35,
                              v16,
                              v17,
                              bIgnoreCasea,
                              (struct Common::RegistryKey *)&hKey);
    if ( RegKeyContainingValue < 0 )
      goto LABEL_24;
    Setting = StateRepository::Globals::GetSetting((Common::RegistryKey *)&hKey, L"PackageRepositoryRoot");
    RegKeyContainingValue = Setting;
    if ( Setting < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C3,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)Setting,
        bIgnoreCase);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      v18 = (wchar_t *)Block;
      goto LABEL_26;
    }
    v18 = (wchar_t *)Block;
    if ( !Block )
      break;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    if ( v18 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v18[v21] );
      RegKeyContainingValue = StateRepository::Text::Append((StateRepository::Text *)v36, v18, v21);
      if ( RegKeyContainingValue < 0 )
      {
        v22 = 1429;
        goto LABEL_27;
      }
    }
    v7 = v14 + 15;
    operator delete(v18);
    if ( v7 >= v6 )
      goto LABEL_37;
    v2 = a1;
    v5 = 1;
  }
  RegKeyContainingValue = -2147023286;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x5C4,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)0x8007064ALL,
    (int)"Required configuration data not found: %ws",
    (const char *)L"PackageRepositoryRoot");
LABEL_24:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
LABEL_26:
  v22 = 1428;
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
    (const char *)(unsigned int)RegKeyContainingValue,
    bIgnoreCase);
  operator delete(v18);
  v12 = RegKeyContainingValue;
LABEL_47:
  StateRepository::TextA::Reset((StateRepository::TextA *)v36);
  return v12;
}

```

## disassembly

```asm
0x180104754  mov     [rsp-38h+arg_0], rcx
0x180104759  push    rbp
0x18010475a  push    rbx
0x18010475b  push    rsi
0x18010475c  push    rdi
0x18010475d  push    r12
0x18010475f  push    r13
0x180104761  push    r15
0x180104763  mov     rbp, rsp
0x180104766  sub     rsp, 50h
0x18010476a  mov     rax, rcx
0x18010476d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180104771  xor     ecx, ecx
0x180104773  mov     r12, rdx
0x180104776  mov     [rbp+var_18], rcx
0x18010477a  mov     edi, ecx
0x18010477c  mov     [rbp+var_10], rcx
0x180104780  test    rax, rax
0x180104783  jz      loc_1801049EA
0x180104789  mov     r13b, cl
0x18010478c  mov     rsi, r8
0x18010478f  inc     rsi
0x180104792  cmp     [rax+rsi*2], cx
0x180104796  jnz     short loc_18010478F
0x180104798  mov     r15, rcx
0x18010479b  test    rsi, rsi
0x18010479e  jz      loc_1801049EA
0x1801047a4  lea     rbx, [rax+r15*2]
0x1801047a8  mov     edx, 25h ; '%'; Ch
0x1801047ad  mov     rcx, rbx; Str
0x1801047b0  call    cs:__imp_wcschr
0x1801047b6  mov     rdi, rax
0x1801047b9  test    rax, rax
0x1801047bc  jz      loc_180104996
0x1801047c2  cmp     rax, rbx
0x1801047c5  jbe     short loc_1801047EF
0x1801047c7  mov     r8, rax
0x1801047ca  lea     rcx, [rbp+var_18]; this
0x1801047ce  sub     r8, rbx
0x1801047d1  mov     rdx, rbx; wchar_t *
0x1801047d4  sar     r8, 1; unsigned __int64
0x1801047d7  call    ?Append@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::Append(wchar_t const *,unsigned __int64)
0x1801047dc  xor     r13d, r13d
0x1801047df  mov     ebx, eax
0x1801047e1  test    eax, eax
0x1801047e3  jns     short loc_1801047F2
0x1801047e5  mov     edx, 58Ch
0x1801047ea  jmp     loc_1801049C5
0x1801047ef  xor     r13d, r13d
0x1801047f2  mov     r15, rdi
0x1801047f5  mov     eax, esi
0x1801047f7  sub     r15, [rbp+arg_0]
0x1801047fb  mov     ecx, 0Fh
0x180104800  sar     r15, 1
0x180104803  sub     eax, r15d
0x180104806  cmp     eax, ecx
0x180104808  jb      loc_18010498C
0x18010480e  mov     r9d, ecx; cchCount2
0x180104811  mov     [rsp+50h+bIgnoreCase], 1; int
0x180104819  mov     edx, ecx; cchCount1
0x18010481b  lea     r8, ?appRepositoryPrefix@StateRepository@@3QB_WB; "%AppRepository%"
0x180104822  mov     rcx, rdi; lpString1
0x180104825  call    cs:__imp_CompareStringOrdinal
0x18010482b  cmp     eax, 2
0x18010482e  jnz     loc_18010498C
0x180104834  lea     rax, [rbp+hKey]
0x180104838  mov     [rbp+hKey], r13
0x18010483c  mov     rbx, r13
0x18010483f  mov     [rsp+50h+var_28], rax; struct Common::RegistryKey *
0x180104844  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180104848  mov     [rbp+Block], rbx
0x18010484c  mov     [rbp+var_20], r13
0x180104850  call    ?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z; Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)
0x180104855  mov     edi, eax
0x180104857  test    eax, eax
0x180104859  js      loc_18010491F
0x18010485f  lea     r9, [rbp+Block]
0x180104863  xor     r8d, r8d
0x180104866  lea     rdx, ?appRepositoryPath@StateRepository@@3QB_WB; "PackageRepositoryRoot"
0x18010486d  lea     rcx, [rbp+hKey]; this
0x180104871  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W1AEAV?$AutoArray@_W$1??$AutoArrayDeallocate@_W@Common@@YAXPEA_W@Z@4@@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,wchar_t const *,Common::AutoArray<wchar_t,&Common::AutoArrayDeallocate<wchar_t>(wchar_t *)> &)
0x180104876  mov     edi, eax
0x180104878  test    eax, eax
0x18010487a  js      loc_18010495A
0x180104880  mov     rbx, [rbp+Block]
0x180104884  test    rbx, rbx
0x180104887  jz      short loc_1801048EA
0x180104889  mov     rcx, [rbp+hKey]; hKey
0x18010488d  lea     rax, [rcx-1]
0x180104891  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180104895  ja      short loc_18010489D
0x180104897  call    cs:__imp_RegCloseKey
0x18010489d  test    rbx, rbx
0x1801048a0  jz      short loc_1801048C2
0x1801048a2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801048a6  inc     r8; unsigned __int64
0x1801048a9  cmp     [rbx+r8*2], r13w
0x1801048ae  jnz     short loc_1801048A6
0x1801048b0  mov     rdx, rbx; wchar_t *
0x1801048b3  lea     rcx, [rbp+var_18]; this
0x1801048b7  call    ?Append@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::Append(wchar_t const *,unsigned __int64)
0x1801048bc  mov     edi, eax
0x1801048be  test    eax, eax
0x1801048c0  js      short loc_1801048E3
0x1801048c2  mov     rcx, rbx; Block
0x1801048c5  add     r15, 0Fh
0x1801048c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801048ce  cmp     r15, rsi
0x1801048d1  jnb     loc_1801049E0
0x1801048d7  mov     rax, [rbp+arg_0]
0x1801048db  mov     r13b, 1
0x1801048de  jmp     loc_1801047A4
0x1801048e3  mov     edx, 595h
0x1801048e8  jmp     short loc_180104938
0x1801048ea  mov     rcx, [rbp+38h]; this
0x1801048ee  lea     rax, ?appRepositoryPath@StateRepository@@3QB_WB; "PackageRepositoryRoot"
0x1801048f5  mov     [rsp+50h+var_28], rax; char *
0x1801048fa  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104901  lea     rax, aRequiredConfig; "Required configuration data not found: "...
0x180104908  mov     edi, 8007064Ah
0x18010490d  mov     r9d, edi; char *
0x180104910  mov     qword ptr [rsp+50h+bIgnoreCase], rax; int
0x180104915  mov     edx, 5C4h; void *
0x18010491a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010491f  mov     rcx, [rbp+hKey]; hKey
0x180104923  lea     rax, [rcx-1]
0x180104927  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010492b  ja      short loc_180104933
0x18010492d  call    cs:__imp_RegCloseKey
0x180104933  mov     edx, 594h; void *
0x180104938  mov     rcx, [rbp+38h]; this
0x18010493c  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104943  mov     r9d, edi; char *
0x180104946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010494b  mov     rcx, rbx; Block
0x18010494e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104953  mov     ebx, edi
0x180104955  jmp     loc_180104A64
0x18010495a  mov     rcx, [rbp+38h]; this
0x18010495e  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104965  mov     r9d, eax; char *
0x180104968  mov     edx, 5C3h; void *
0x18010496d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104972  mov     rcx, [rbp+hKey]; hKey
0x180104976  lea     rax, [rcx-1]
0x18010497a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010497e  ja      short loc_180104986
0x180104980  call    cs:__imp_RegCloseKey
0x180104986  mov     rbx, [rbp+Block]
0x18010498a  jmp     short loc_180104933
0x18010498c  mov     ebx, 80670003h
0x180104991  jmp     loc_180104A64
0x180104996  test    r13b, r13b
0x180104999  jz      short loc_1801049DD
0x18010499b  cmp     r15, rsi
0x18010499e  jnb     short loc_1801049DD
0x1801049a0  mov     rax, [rbp+arg_0]
0x1801049a4  lea     rcx, [rbp+var_18]; this
0x1801049a8  sub     rsi, r15
0x1801049ab  mov     r8, rsi; unsigned __int64
0x1801049ae  lea     rdx, [rax+r15*2]; wchar_t *
0x1801049b2  call    ?Append@Text@StateRepository@@QEAAJPEB_W_K@Z; StateRepository::Text::Append(wchar_t const *,unsigned __int64)
0x1801049b7  xor     r13d, r13d
0x1801049ba  mov     ebx, eax
0x1801049bc  test    eax, eax
0x1801049be  jns     short loc_1801049E0
0x1801049c0  mov     edx, 5A3h; void *
0x1801049c5  mov     rcx, [rbp+38h]; this
0x1801049c9  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801049d0  mov     r9d, eax; char *
0x1801049d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801049d8  jmp     loc_180104A64
0x1801049dd  xor     r13d, r13d
0x1801049e0  mov     rdi, [rbp+var_18]
0x1801049e4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801049e8  jmp     short loc_1801049ED
0x1801049ea  xor     r13d, r13d
0x1801049ed  test    rdi, rdi
0x1801049f0  jnz     short loc_180104A0D
0x1801049f2  mov     rcx, [r12]; Block
0x1801049f6  test    rcx, rcx
0x1801049f9  jz      loc_180104B02
0x1801049ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104a04  mov     [r12], r13
0x180104a08  jmp     loc_180104B02
0x180104a0d  mov     rsi, r8
0x180104a10  inc     rsi
0x180104a13  cmp     [rdi+rsi*2], r13w
0x180104a18  jnz     short loc_180104A10
0x180104a1a  inc     rsi
0x180104a1d  mov     eax, 2
0x180104a22  mul     rsi
0x180104a25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180104a2c  cmovb   rax, r8
0x180104a30  mov     rcx, rax; unsigned __int64
0x180104a33  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180104a38  mov     rbx, rax
0x180104a3b  test    rax, rax
0x180104a3e  jnz     short loc_180104A7E
0x180104a40  mov     rcx, [rbp+38h]; this
0x180104a44  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104a4b  mov     ebx, 8007000Eh
0x180104a50  mov     edx, 5B0h; void *
0x180104a55  mov     r9d, ebx; char *
0x180104a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104a5d  xor     ecx, ecx; Block
0x180104a5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104a64  lea     rcx, [rbp+var_18]; this
0x180104a68  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180104a6d  mov     eax, ebx
0x180104a6f  add     rsp, 50h
0x180104a73  pop     r15
0x180104a75  pop     r13
0x180104a77  pop     r12
0x180104a79  pop     rdi
0x180104a7a  pop     rsi
0x180104a7b  pop     rbx
0x180104a7c  pop     rbp
0x180104a7d  retn
0x180104a7e  test    rsi, rsi
0x180104a81  jz      loc_180104B12
0x180104a87  cmp     rsi, 7FFFFFFFh
0x180104a8e  jbe     short loc_180104A9B
0x180104a90  mov     r9d, 80070057h
0x180104a96  jmp     loc_180104B1D
0x180104a9b  mov     eax, 7FFFFFFEh
0x180104aa0  mov     rdx, rbx
0x180104aa3  test    rax, rax
0x180104aa6  jz      short loc_180104AC4
0x180104aa8  movzx   ecx, word ptr [rdi]
0x180104aab  test    cx, cx
0x180104aae  jz      short loc_180104AC4
0x180104ab0  mov     [rdx], cx
0x180104ab3  add     rdi, 2
0x180104ab7  add     rdx, 2
0x180104abb  dec     rax
0x180104abe  sub     rsi, 1
0x180104ac2  jnz     short loc_180104AA3
0x180104ac4  mov     rax, rsi
0x180104ac7  lea     rcx, [rdx-2]
0x180104acb  neg     rax
0x180104ace  sbb     r9d, r9d
0x180104ad1  not     r9d
0x180104ad4  and     r9d, 8007007Ah
0x180104adb  test    rsi, rsi
0x180104ade  cmovnz  rcx, rdx
0x180104ae2  mov     [rcx], r13w
0x180104ae6  jz      short loc_180104B21
0x180104ae8  cmp     [r12], rbx
0x180104aec  jz      short loc_180104AFB
0x180104aee  mov     rcx, [r12]; Block
0x180104af2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104af7  mov     [r12], rbx
0x180104afb  xor     ecx, ecx; Block
0x180104afd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104b02  lea     rcx, [rbp+var_18]; this
0x180104b06  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180104b0b  xor     eax, eax
0x180104b0d  jmp     loc_180104A6F
0x180104b12  mov     r9d, 80070057h; char *
0x180104b18  test    rsi, rsi
0x180104b1b  jz      short loc_180104B21
0x180104b1d  mov     [rax], r13w
0x180104b21  mov     rcx, [rbp+38h]; this
0x180104b25  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104b2c  mov     edx, 5B1h; void *
0x180104b31  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
