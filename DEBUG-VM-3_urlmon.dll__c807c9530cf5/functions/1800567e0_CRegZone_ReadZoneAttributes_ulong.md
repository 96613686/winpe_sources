# CRegZone::ReadZoneAttributes(ulong)

- ea: `0x1800567e0`
- end: `0x180056d57`
- name: `?ReadZoneAttributes@CRegZone@@QEAAJK@Z`
- size: `1399`
- prototype: `__int64 __fastcall(CRegZone *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800566cc`

## callees

- `0x1800215c0`
- `0x1800342d0`
- `0x1800567e0`
- `0x180056d60`
- `0x180056e20`
- `0x180056e60`
- `0x180056ed0`
- `0x180056f74`
- `0x18007d64c`
- `0x180107e28`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18005694a`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180056abf`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180056c8e`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18005694a`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180056abf`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180056c8e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800569eb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180056a11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800569eb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180056a11`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18005689a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800568bd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180056914`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180056936`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18005689a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800568bd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180056914`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180056936`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d0c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d23`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d3a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d0c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d23`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180056d3a`

## string_xrefs

- `0x180056bae`: `RecommendedLevel`
- `0x180056bd8`: `RecommendedLevel`

## pseudocode

```c
__int64 __fastcall CRegZone::ReadZoneAttributes(const unsigned __int16 **this, int a2)
{
  unsigned int v4; // r15d
  int v5; // eax
  const WCHAR *v6; // rdi
  LSTATUS v7; // esi
  LSTATUS v8; // r14d
  BOOL fIgnoreHKCU; // eax
  const WCHAR *v10; // rdi
  BOOL v11; // eax
  unsigned int v12; // r9d
  int v13; // eax
  unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdi
  CRegZone *v17; // rcx
  const unsigned __int16 *v18; // rdi
  CRegZone *v19; // rcx
  const unsigned __int16 *v20; // rdi
  const unsigned __int16 *v21; // rdi
  unsigned int v22; // edx
  const unsigned int *v24; // [rsp+30h] [rbp-49h] BYREF
  HUSKEY hUSKey; // [rsp+38h] [rbp-41h]
  BOOL v26; // [rsp+40h] [rbp-39h]
  __int64 v27; // [rsp+44h] [rbp-35h]
  const unsigned int *v28; // [rsp+50h] [rbp-29h] BYREF
  HUSKEY v29; // [rsp+58h] [rbp-21h]
  BOOL v30[2]; // [rsp+60h] [rbp-19h]
  int v31; // [rsp+68h] [rbp-11h]
  const unsigned int *v32; // [rsp+70h] [rbp-9h] BYREF
  HUSKEY v33; // [rsp+78h] [rbp-1h]
  int v34; // [rsp+80h] [rbp+7h]
  __int64 v35; // [rsp+84h] [rbp+Bh]
  HUSKEY phNewUSKey; // [rsp+E0h] [rbp+67h] BYREF

  v4 = -2147467259;
  if ( *(_DWORD *)this == -1 || (int)CRegZone::EnsureZoneAttributes((CRegZone *)this) < 0 )
    return v4;
  v5 = *((_DWORD *)this + 10);
  v6 = this[3];
  v32 = &CRegKey::`vftable';
  v28 = &CRegKey::`vftable';
  v24 = &CRegKey::`vftable';
  v33 = 0;
  v34 = v5;
  v35 = 0;
  v29 = 0;
  *(_QWORD *)v30 = 1;
  v31 = 0;
  hUSKey = 0;
  v26 = v5;
  v27 = 1;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v24);
  v7 = 87;
  if ( v6 )
  {
    if ( (_DWORD)v27 )
    {
      fIgnoreHKCU = v26;
      if ( v26 )
        goto LABEL_9;
      v8 = SHRegOpenUSKeyW(v6, 0x20019u, 0, &phNewUSKey, 1);
      if ( !v8 )
        goto LABEL_10;
    }
    fIgnoreHKCU = v26;
LABEL_9:
    v8 = SHRegOpenUSKeyW(v6, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU);
    if ( v8 )
      goto LABEL_11;
LABEL_10:
    hUSKey = phNewUSKey;
    goto LABEL_11;
  }
  v8 = 87;
LABEL_11:
  v10 = this[2];
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v28 + 2))(&v28);
  if ( !v10 )
    goto LABEL_18;
  if ( !v30[1] )
    goto LABEL_15;
  v11 = v30[0];
  if ( v30[0] )
    goto LABEL_16;
  v7 = SHRegOpenUSKeyW(v10, 0x20019u, 0, &phNewUSKey, 1);
  if ( v7 )
  {
LABEL_15:
    v11 = v30[0];
LABEL_16:
    v7 = SHRegOpenUSKeyW(v10, 0x20019u, 0, &phNewUSKey, v11);
    if ( v7 )
      goto LABEL_18;
  }
  v29 = phNewUSKey;
LABEL_18:
  if ( !IsProtectedModeProcess() || (v12 = 983103, *((_DWORD *)this + 10)) )
    v12 = 131097;
  v13 = CRegKey::Open((CRegKey *)&v32, 0, this[2], v12);
  if ( v13 == 5 )
    v13 = CRegKey::Open((CRegKey *)&v32, 0, this[2], 0x20019u);
  if ( !v13 || !v8 || !v7 )
  {
    v4 = 0;
    *(_DWORD *)this[4] = 1460;
    LODWORD(phNewUSKey) = 0;
    if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_READ_ZONE_STRINGS_FROM_REGISTRY)
      || *(_DWORD *)this > 4u
      || !LoadStringW(g_hinstMUI, *(_DWORD *)this + 4126, (LPWSTR)this[4] + 2, 260)
      || !LoadStringW(g_hinstMUI, *(_DWORD *)this + 4131, (LPWSTR)this[4] + 262, 200) )
    {
      v14 = (unsigned __int16 *)(this[4] + 2);
      LODWORD(phNewUSKey) = 520;
      if ( CRegKey::QueryValue((CRegKey *)&v24, v14, L"DisplayName", (unsigned int *)&phNewUSKey)
        && CRegKey::QueryValue(
             (CRegKey *)&v32,
             (unsigned __int16 *)this[4] + 2,
             L"DisplayName",
             (unsigned int *)&phNewUSKey) )
      {
        *((_WORD *)this[4] + 2) = 0;
      }
      v15 = (unsigned __int16 *)(this[4] + 262);
      LODWORD(phNewUSKey) = 400;
      if ( CRegKey::QueryValue((CRegKey *)&v24, v15, L"Description", (unsigned int *)&phNewUSKey)
        && CRegKey::QueryValue(
             (CRegKey *)&v32,
             (unsigned __int16 *)this[4] + 262,
             L"Description",
             (unsigned int *)&phNewUSKey) )
      {
        *((_WORD *)this[4] + 262) = 0;
      }
    }
    LODWORD(phNewUSKey) = 520;
    if ( (IsProtectedModeProcess()
       || CRegKey::QueryValue(
            (CRegKey *)&v24,
            (unsigned __int16 *)this[4] + 462,
            L"LowIcon",
            (unsigned int *)&phNewUSKey)
       && CRegKey::QueryValue(
            (CRegKey *)&v32,
            (unsigned __int16 *)this[4] + 462,
            L"LowIcon",
            (unsigned int *)&phNewUSKey))
      && CRegKey::QueryValue((CRegKey *)&v24, (unsigned __int16 *)this[4] + 462, L"Icon", (unsigned int *)&phNewUSKey)
      && CRegKey::QueryValue((CRegKey *)&v32, (unsigned __int16 *)this[4] + 462, L"Icon", (unsigned int *)&phNewUSKey) )
    {
      *((_WORD *)this[4] + 462) = 0;
    }
    v16 = this[4];
    if ( CRegKey::QueryValue((CRegKey *)&v24, (unsigned int *)v16 + 361, L"MinLevel")
      || (unsigned int)(*((_DWORD *)v16 + 361) - 0x10000) > 0x10000 )
    {
      *((_DWORD *)v16 + 361) = 0;
      CRegZone::QueryTemplatePolicyIndex(v17, (struct CRegKey *)&v28, L"MinLevel", (unsigned int *)this[4] + 361);
    }
    v18 = this[4];
    if ( CRegKey::QueryValue((CRegKey *)&v24, (unsigned int *)v18 + 362, L"RecommendedLevel")
      || (unsigned int)(*((_DWORD *)v18 + 362) - 0x10000) > 0x10000 )
    {
      *((_DWORD *)v18 + 362) = 0;
      CRegZone::QueryTemplatePolicyIndex(
        v19,
        (struct CRegKey *)&v28,
        L"RecommendedLevel",
        (unsigned int *)this[4] + 362);
    }
    v20 = this[4];
    if ( CRegKey::QueryValue((CRegKey *)&v24, (unsigned int *)v20 + 363, L"CurrentLevel")
      || (unsigned int)(*((_DWORD *)v20 + 363) - 0x10000) > 0x10000 )
    {
      *((_DWORD *)v20 + 363) = 0;
      v21 = this[4];
      if ( CRegKey::QueryValue((CRegKey *)&v32, (unsigned int *)v21 + 363, L"CurrentLevel")
        || (unsigned int)(*((_DWORD *)v21 + 363) - 0x10000) > 0x10000 )
      {
        *((_DWORD *)v21 + 363) = 0;
      }
      if ( (a2 & 0x20000) != 0 )
      {
        v22 = *((_DWORD *)this[4] + 363);
        if ( v22 )
        {
          if ( !CRegZone::VerifyTemplateSettings((CRegZone *)this, v22) )
          {
            *((_DWORD *)this[4] + 363) = 0;
            if ( IsProtectedModeProcess() )
            {
              if ( !*((_DWORD *)this + 10) )
                CRegKey::SetValue((CRegKey *)&v32, *((_DWORD *)this[4] + 363), L"CurrentLevel");
            }
          }
        }
      }
    }
    if ( CRegKey::QueryValue((CRegKey *)&v24, (unsigned int *)this[4] + 364, L"Flags") )
      CRegKey::QueryValue((CRegKey *)&v32, (unsigned int *)this[4] + 364, L"Flags");
    *((_DWORD *)this + 1) = *((_DWORD *)this[4] + 364);
  }
  v24 = &CRegKey::`vftable';
  if ( hUSKey )
  {
    SHRegCloseUSKey(hUSKey);
    hUSKey = 0;
  }
  v28 = &CRegKey::`vftable';
  if ( v29 )
  {
    SHRegCloseUSKey(v29);
    v29 = 0;
  }
  v32 = &CRegKey::`vftable';
  if ( v33 )
    SHRegCloseUSKey(v33);
  return v4;
}

```

## disassembly

```asm
0x1800567e0  push    rbp
0x1800567e2  push    rbx
0x1800567e3  push    rsi
0x1800567e4  push    rdi
0x1800567e5  push    r12
0x1800567e7  push    r13
0x1800567e9  push    r14
0x1800567eb  push    r15
0x1800567ed  lea     rbp, [rsp-1Fh]
0x1800567f2  sub     rsp, 98h
0x1800567f9  cmp     dword ptr [rcx], 0FFFFFFFFh
0x1800567fc  mov     r12d, edx
0x1800567ff  mov     rbx, rcx
0x180056802  mov     r15d, 80004005h
0x180056808  jz      loc_180056D40
0x18005680e  call    ?EnsureZoneAttributes@CRegZone@@AEAAJXZ; CRegZone::EnsureZoneAttributes(void)
0x180056813  xor     r13d, r13d
0x180056816  test    eax, eax
0x180056818  js      loc_180056D40
0x18005681e  mov     eax, [rbx+28h]
0x180056821  lea     rcx, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180056828  mov     rdi, [rbx+18h]
0x18005682c  lea     r14d, [r13+1]
0x180056830  mov     [rbp+57h+var_60], rcx
0x180056834  mov     [rbp+57h+var_80], rcx
0x180056838  mov     [rbp+57h+var_A0], rcx
0x18005683c  lea     rcx, [rbp+57h+var_A0]; this
0x180056840  mov     [rbp+57h+var_58], r13
0x180056844  mov     [rbp+57h+var_50], eax
0x180056847  mov     [rbp+57h+var_4C], r13
0x18005684b  mov     [rbp+57h+var_78], r13
0x18005684f  mov     qword ptr [rbp+57h+var_70], r14
0x180056853  mov     [rbp+57h+var_68], r13d
0x180056857  mov     [rbp+57h+hUSKey], r13
0x18005685b  mov     [rbp+57h+var_90], eax
0x18005685e  mov     [rbp+57h+var_8C], r14
0x180056862  mov     [rbp+57h+phNewUSKey], r13
0x180056866  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x18005686b  lea     esi, [r13+57h]
0x18005686f  test    rdi, rdi
0x180056872  jnz     short loc_180056879
0x180056874  mov     r14d, esi
0x180056877  jmp     short loc_1800568D2
0x180056879  cmp     dword ptr [rbp+57h+var_8C], r13d
0x18005687d  jz      short loc_1800568A7
0x18005687f  mov     eax, [rbp+57h+var_90]
0x180056882  test    eax, eax
0x180056884  jnz     short loc_1800568AA
0x180056886  lea     r9, [rbp+57h+phNewUSKey]; phNewUSKey
0x18005688a  mov     [rsp+0D0h+fIgnoreHKCU], r14d; fIgnoreHKCU
0x18005688f  xor     r8d, r8d; hRelativeUSKey
0x180056892  mov     edx, 20019h; samDesired
0x180056897  mov     rcx, rdi; pwzPath
0x18005689a  call    cs:__imp_SHRegOpenUSKeyW
0x1800568a0  mov     r14d, eax
0x1800568a3  test    eax, eax
0x1800568a5  jz      short loc_1800568CA
0x1800568a7  mov     eax, [rbp+57h+var_90]
0x1800568aa  lea     r9, [rbp+57h+phNewUSKey]; phNewUSKey
0x1800568ae  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x1800568b2  xor     r8d, r8d; hRelativeUSKey
0x1800568b5  mov     edx, 20019h; samDesired
0x1800568ba  mov     rcx, rdi; pwzPath
0x1800568bd  call    cs:__imp_SHRegOpenUSKeyW
0x1800568c3  mov     r14d, eax
0x1800568c6  test    eax, eax
0x1800568c8  jnz     short loc_1800568D2
0x1800568ca  mov     rax, [rbp+57h+phNewUSKey]
0x1800568ce  mov     [rbp+57h+hUSKey], rax
0x1800568d2  mov     rax, [rbp+57h+var_80]
0x1800568d6  lea     rcx, [rbp+57h+var_80]
0x1800568da  mov     rdi, [rbx+10h]
0x1800568de  mov     [rbp+57h+phNewUSKey], r13
0x1800568e2  mov     rax, [rax+10h]
0x1800568e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568eb  test    rdi, rdi
0x1800568ee  jz      short loc_18005694A
0x1800568f0  cmp     [rbp+57h+var_70+4], r13d
0x1800568f4  jz      short loc_180056920
0x1800568f6  mov     eax, [rbp+57h+var_70]
0x1800568f9  test    eax, eax
0x1800568fb  jnz     short loc_180056923
0x1800568fd  lea     r9, [rbp+57h+phNewUSKey]; phNewUSKey
0x180056901  mov     [rsp+0D0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180056909  xor     r8d, r8d; hRelativeUSKey
0x18005690c  mov     edx, 20019h; samDesired
0x180056911  mov     rcx, rdi; pwzPath
0x180056914  call    cs:__imp_SHRegOpenUSKeyW
0x18005691a  mov     esi, eax
0x18005691c  test    eax, eax
0x18005691e  jz      short loc_180056942
0x180056920  mov     eax, [rbp+57h+var_70]
0x180056923  lea     r9, [rbp+57h+phNewUSKey]; phNewUSKey
0x180056927  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18005692b  xor     r8d, r8d; hRelativeUSKey
0x18005692e  mov     edx, 20019h; samDesired
0x180056933  mov     rcx, rdi; pwzPath
0x180056936  call    cs:__imp_SHRegOpenUSKeyW
0x18005693c  mov     esi, eax
0x18005693e  test    eax, eax
0x180056940  jnz     short loc_18005694A
0x180056942  mov     rax, [rbp+57h+phNewUSKey]
0x180056946  mov     [rbp+57h+var_78], rax
0x18005694a  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180056950  test    eax, eax
0x180056952  jz      short loc_180056960
0x180056954  mov     r9d, 0F003Fh
0x18005695a  cmp     [rbx+28h], r13d
0x18005695e  jz      short loc_180056966
0x180056960  mov     r9d, 20019h; unsigned int
0x180056966  mov     r8, [rbx+10h]; unsigned __int16 *
0x18005696a  lea     rcx, [rbp+57h+var_60]; this
0x18005696e  xor     edx, edx; void *
0x180056970  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180056975  cmp     eax, 5
0x180056978  jnz     short loc_18005698F
0x18005697a  mov     r8, [rbx+10h]; unsigned __int16 *
0x18005697e  lea     rcx, [rbp+57h+var_60]; this
0x180056982  mov     r9d, 20019h; unsigned int
0x180056988  xor     edx, edx; void *
0x18005698a  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18005698f  test    eax, eax
0x180056991  jz      short loc_1800569A0
0x180056993  test    r14d, r14d
0x180056996  jz      short loc_1800569A0
0x180056998  test    esi, esi
0x18005699a  jnz     loc_180056CF8
0x1800569a0  mov     rax, [rbx+20h]
0x1800569a4  lea     rcx, ?FEATURE_READ_ZONE_STRINGS_FROM_REGISTRY@FCK@@3VCFeatureControlKey@@A; this
0x1800569ab  mov     r15d, r13d
0x1800569ae  mov     dword ptr [rax], 5B4h
0x1800569b4  mov     dword ptr [rbp+57h+phNewUSKey], r13d
0x1800569b8  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800569bd  mov     esi, 208h
0x1800569c2  lea     edi, [rsi+4]
0x1800569c5  test    eax, eax
0x1800569c7  jz      short loc_180056A1F
0x1800569c9  mov     edx, [rbx]
0x1800569cb  cmp     edx, 4
0x1800569ce  ja      short loc_180056A1F
0x1800569d0  mov     r8, [rbx+20h]
0x1800569d4  add     edx, 101Eh; uID
0x1800569da  mov     rcx, cs:g_hinstMUI; hInstance
0x1800569e1  add     r8, 4; lpBuffer
0x1800569e5  mov     r9d, 104h; cchBufferMax
0x1800569eb  call    cs:__imp_LoadStringW
0x1800569f1  test    eax, eax
0x1800569f3  jz      short loc_180056A1F
0x1800569f5  mov     r8, [rbx+20h]
0x1800569f9  mov     r9d, 0C8h; cchBufferMax
0x1800569ff  mov     edx, [rbx]
0x180056a01  add     r8, rdi; lpBuffer
0x180056a04  mov     rcx, cs:g_hinstMUI; hInstance
0x180056a0b  add     edx, 1023h; uID
0x180056a11  call    cs:__imp_LoadStringW
0x180056a17  test    eax, eax
0x180056a19  jnz     loc_180056ABC
0x180056a1f  mov     rdx, [rbx+20h]
0x180056a23  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056a27  add     rdx, 4; unsigned __int16 *
0x180056a2b  mov     dword ptr [rbp+57h+phNewUSKey], esi
0x180056a2e  lea     r8, aDisplayname; "DisplayName"
0x180056a35  lea     rcx, [rbp+57h+var_A0]; this
0x180056a39  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056a3e  test    eax, eax
0x180056a40  jz      short loc_180056A6B
0x180056a42  mov     rdx, [rbx+20h]
0x180056a46  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056a4a  add     rdx, 4; unsigned __int16 *
0x180056a4e  lea     r8, aDisplayname; "DisplayName"
0x180056a55  lea     rcx, [rbp+57h+var_60]; this
0x180056a59  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056a5e  test    eax, eax
0x180056a60  jz      short loc_180056A6B
0x180056a62  mov     rcx, [rbx+20h]
0x180056a66  mov     [rcx+4], r13w
0x180056a6b  mov     rdx, [rbx+20h]
0x180056a6f  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056a73  add     rdx, rdi; unsigned __int16 *
0x180056a76  mov     dword ptr [rbp+57h+phNewUSKey], 190h
0x180056a7d  lea     r8, aDescription; "Description"
0x180056a84  lea     rcx, [rbp+57h+var_A0]; this
0x180056a88  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056a8d  test    eax, eax
0x180056a8f  jz      short loc_180056ABC
0x180056a91  mov     rdx, [rbx+20h]
0x180056a95  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056a99  add     rdx, rdi; unsigned __int16 *
0x180056a9c  lea     r8, aDescription; "Description"
0x180056aa3  lea     rcx, [rbp+57h+var_60]; this
0x180056aa7  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056aac  test    eax, eax
0x180056aae  jz      short loc_180056ABC
0x180056ab0  mov     rcx, [rbx+20h]
0x180056ab4  mov     [rcx+20Ch], r13w
0x180056abc  mov     dword ptr [rbp+57h+phNewUSKey], esi
0x180056abf  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180056ac5  mov     edi, 39Ch
0x180056aca  test    eax, eax
0x180056acc  jnz     short loc_180056B0C
0x180056ace  mov     rdx, [rbx+20h]
0x180056ad2  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056ad6  add     rdx, rdi; unsigned __int16 *
0x180056ad9  lea     r8, aLowicon; "LowIcon"
0x180056ae0  lea     rcx, [rbp+57h+var_A0]; this
0x180056ae4  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056ae9  test    eax, eax
0x180056aeb  jz      short loc_180056B56
0x180056aed  mov     rdx, [rbx+20h]
0x180056af1  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056af5  add     rdx, rdi; unsigned __int16 *
0x180056af8  lea     r8, aLowicon; "LowIcon"
0x180056aff  lea     rcx, [rbp+57h+var_60]; this
0x180056b03  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056b08  test    eax, eax
0x180056b0a  jz      short loc_180056B56
0x180056b0c  mov     rdx, [rbx+20h]
0x180056b10  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056b14  add     rdx, rdi; unsigned __int16 *
0x180056b17  lea     r8, aIcon; "Icon"
0x180056b1e  lea     rcx, [rbp+57h+var_A0]; this
0x180056b22  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056b27  test    eax, eax
0x180056b29  jz      short loc_180056B56
0x180056b2b  mov     rdx, [rbx+20h]
0x180056b2f  lea     r9, [rbp+57h+phNewUSKey]; unsigned int *
0x180056b33  add     rdx, rdi; unsigned __int16 *
0x180056b36  lea     r8, aIcon; "Icon"
0x180056b3d  lea     rcx, [rbp+57h+var_60]; this
0x180056b41  call    ?QueryValue@CRegKey@@QEAAJPEAGPEBGPEAK@Z; CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x180056b46  test    eax, eax
0x180056b48  jz      short loc_180056B56
0x180056b4a  mov     rcx, [rbx+20h]
0x180056b4e  mov     [rcx+39Ch], r13w
0x180056b56  mov     rdi, [rbx+20h]
0x180056b5a  lea     r8, aMinlevel; "MinLevel"
0x180056b61  lea     rcx, [rbp+57h+var_A0]; this
0x180056b65  lea     rdx, [rdi+5A4h]; unsigned int *
0x180056b6c  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180056b71  mov     esi, 10000h
0x180056b76  test    eax, eax
0x180056b78  jnz     short loc_180056B86
0x180056b7a  mov     eax, [rdi+5A4h]
0x180056b80  sub     eax, esi
0x180056b82  cmp     eax, esi
0x180056b84  jbe     short loc_180056BAA
0x180056b86  mov     eax, r13d
0x180056b89  lea     r8, aMinlevel; "MinLevel"
0x180056b90  mov     [rdi+5A4h], eax
0x180056b96  lea     rdx, [rbp+57h+var_80]; struct CRegKey *
0x180056b9a  mov     r9, [rbx+20h]
0x180056b9e  add     r9, 5A4h; unsigned int *
0x180056ba5  call    ?QueryTemplatePolicyIndex@CRegZone@@IEBAHAEAVCRegKey@@PEBGPEAK@Z; CRegZone::QueryTemplatePolicyIndex(CRegKey &,ushort const *,ulong *)
0x180056baa  mov     rdi, [rbx+20h]
0x180056bae  lea     r8, aRecommendedlev; "RecommendedLevel"
0x180056bb5  lea     rcx, [rbp+57h+var_A0]; this
0x180056bb9  lea     rdx, [rdi+5A8h]; unsigned int *
0x180056bc0  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180056bc5  test    eax, eax
0x180056bc7  jnz     short loc_180056BD5
0x180056bc9  mov     eax, [rdi+5A8h]
0x180056bcf  sub     eax, esi
0x180056bd1  cmp     eax, esi
0x180056bd3  jbe     short loc_180056BF9
0x180056bd5  mov     eax, r13d
0x180056bd8  lea     r8, aRecommendedlev; "RecommendedLevel"
0x180056bdf  mov     [rdi+5A8h], eax
0x180056be5  lea     rdx, [rbp+57h+var_80]; struct CRegKey *
0x180056be9  mov     r9, [rbx+20h]
0x180056bed  add     r9, 5A8h; unsigned int *
0x180056bf4  call    ?QueryTemplatePolicyIndex@CRegZone@@IEBAHAEAVCRegKey@@PEBGPEAK@Z; CRegZone::QueryTemplatePolicyIndex(CRegKey &,ushort const *,ulong *)
0x180056bf9  mov     rdi, [rbx+20h]
0x180056bfd  lea     r14, aCurrentlevel; "CurrentLevel"
0x180056c04  mov     r8, r14; unsigned __int16 *
0x180056c07  lea     rcx, [rbp+57h+var_A0]; this
0x180056c0b  lea     rdx, [rdi+5ACh]; unsigned int *
0x180056c12  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180056c17  test    eax, eax
0x180056c19  jnz     short loc_180056C2B
0x180056c1b  mov     eax, [rdi+5ACh]
0x180056c21  sub     eax, esi
0x180056c23  cmp     eax, esi
0x180056c25  jbe     loc_180056CB4
0x180056c2b  mov     eax, r13d
0x180056c2e  lea     rcx, [rbp+57h+var_60]; this
0x180056c32  mov     [rdi+5ACh], eax
0x180056c38  mov     r8, r14; unsigned __int16 *
0x180056c3b  mov     rdi, [rbx+20h]
0x180056c3f  lea     rdx, [rdi+5ACh]; unsigned int *
0x180056c46  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180056c4b  test    eax, eax
0x180056c4d  jnz     short loc_180056C5B
0x180056c4f  mov     eax, [rdi+5ACh]
0x180056c55  sub     eax, esi
0x180056c57  cmp     eax, esi
0x180056c59  jbe     short loc_180056C62
0x180056c5b  mov     [rdi+5ACh], r13d
0x180056c62  bt      r12d, 11h
0x180056c67  jnb     short loc_180056CB4
0x180056c69  mov     rax, [rbx+20h]
  ... truncated ...
```
