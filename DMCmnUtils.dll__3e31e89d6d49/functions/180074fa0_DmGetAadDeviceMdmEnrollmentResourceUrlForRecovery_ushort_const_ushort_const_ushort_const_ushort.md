# DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180074fa0`
- end: `0x1800754e1`
- name: `?DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery@@YAJPEBG00PEAPEAG@Z`
- size: `1345`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x18005b638`
- `0x18005b914`
- `0x18005b984`
- `0x18005bd30`
- `0x1800605a8`
- `0x1800609dc`
- `0x180069ef0`
- `0x18006f8a8`
- `0x180072818`
- `0x180074aa4`
- `0x180074e6c`
- `0x180074fa0`
- `0x1800754f0`
- `0x180077c20`
- `0x1800782c8`
- `0x1800790f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800752f6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800752f6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180075310`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180075310`
- `RPCRT4!UuidFromStringW` at `0x180074fe8`
- `RPCRT4!UuidFromStringW` at `0x18007524f`
- `RPCRT4!UuidFromStringW` at `0x1800753bc`
- `RPCRT4!UuidFromStringW` at `0x180075417`
- `RPCRT4!UuidFromStringW` at `0x180074fe8`
- `RPCRT4!UuidFromStringW` at `0x18007524f`
- `RPCRT4!UuidFromStringW` at `0x1800753bc`
- `RPCRT4!UuidFromStringW` at `0x180075417`
- `dsreg!DsrGetJoinInfoEx` at `0x180075088`
- `dsreg!DsrGetJoinInfoEx` at `0x180075130`
- `dsreg!DsrGetJoinInfoEx` at `0x180075088`
- `dsreg!DsrGetJoinInfoEx` at `0x180075130`
- `dsreg!DsrFreeJoinInfoEx` at `0x18007510a`
- `dsreg!DsrFreeJoinInfoEx` at `0x18007510a`
- `dmEnrollEngine!GetEnrollmentType` at `0x18007502b`
- `dmEnrollEngine!GetEnrollmentType` at `0x18007502b`
- `dmEnrollEngine!SetEnrollmentResourceCache` at `0x18007526f`
- `dmEnrollEngine!SetEnrollmentResourceCache` at `0x1800753dc`
- `dmEnrollEngine!SetEnrollmentResourceCache` at `0x18007526f`
- `dmEnrollEngine!SetEnrollmentResourceCache` at `0x1800753dc`
- `dmEnrollEngine!GetEnrollmentResourceCache` at `0x180075469`
- `dmEnrollEngine!GetEnrollmentResourceCache` at `0x180075469`

## string_xrefs

- `0x180075002`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x1800750a6`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x18007514a`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x1800751c3`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`
- `0x18007542e`: `onecoreuap\admin\dm\dmcmnutils\tokenutils\tokenutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int EnrollmentType; // eax
  char v11; // r14
  int JoinInfo; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  int ActiveUserSid; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // rcx
  const unsigned __int16 *v22; // rdx
  _WORD *v23; // rdx
  unsigned __int16 *v24; // rbx
  wchar_t *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rax
  _WORD *v28; // rcx
  unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  RPC_STATUS EnrollmentResourceCache; // eax
  __int64 v32; // rdx
  unsigned __int64 v33; // r8
  unsigned __int16 **hlocal_string; // rax
  unsigned __int16 *v35; // rcx
  int v37; // [rsp+20h] [rbp-69h]
  int v38; // [rsp+20h] [rbp-69h]
  wchar_t *Str; // [rsp+30h] [rbp-59h] BYREF
  __int64 v40; // [rsp+38h] [rbp-51h] BYREF
  int v41; // [rsp+40h] [rbp-49h] BYREF
  const unsigned __int16 *v42; // [rsp+48h] [rbp-41h] BYREF
  UUID v43; // [rsp+50h] [rbp-39h] BYREF
  UUID v44; // [rsp+60h] [rbp-29h] BYREF
  UUID v45; // [rsp+70h] [rbp-19h] BYREF
  UUID Uuid; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  Uuid = 0;
  v41 = 63;
  v8 = UuidFromStringW(a3, &Uuid);
  if ( (v8 & 0x80000000) == 0 )
  {
    v45 = Uuid;
    EnrollmentType = GetEnrollmentType(&v45, &v41);
    v8 = EnrollmentType;
    if ( EnrollmentType == -2147024894 )
    {
      v8 = -2102525946;
LABEL_7:
      v9 = 1140;
      goto LABEL_3;
    }
    if ( EnrollmentType < 0 )
      goto LABEL_7;
    if ( v41 == 26 || (v11 = 0, v41 == 24) )
      v11 = 1;
    v40 = 0;
    v42 = a2;
    if ( v41 != 24 && v41 != 13 )
    {
      v40 = 0;
      JoinInfo = DsrGetJoinInfoEx(1, &v42, &v40);
      v8 = JoinInfo;
      if ( JoinInfo < 0 )
      {
        v13 = (unsigned int)JoinInfo;
        v14 = 1161;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
          (const char *)v13,
          v37);
LABEL_63:
        wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO_1 *,void (*)(void *),&void DsrFreeJoinInfoEx(void *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO_1 *,_DSREG_JOIN_INFO_1 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO_1 *,void (*)(void *),&void DsrFreeJoinInfoEx(void *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO_1 *,_DSREG_JOIN_INFO_1 *,0,std::nullptr_t>>(&v40);
        return v8;
      }
LABEL_24:
      if ( !v40 )
      {
        v8 = -2145647536;
        v13 = 2149319760LL;
        v14 = 1165;
        goto LABEL_15;
      }
      if ( v11 )
      {
        Str = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &Str,
          0);
        v18 = CreateCorrelationId(&Str);
        v8 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x493,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
            (const char *)(unsigned int)v18,
            v37);
          goto LABEL_29;
        }
        LOBYTE(v19) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
          v19);
        v20 = L"Device";
        if ( v41 != 26 )
          v20 = L"User";
        v21 = &pszSrc;
        v22 = &pszSrc;
        if ( *(_QWORD *)(v40 + 32) )
          v22 = *(const unsigned __int16 **)(v40 + 32);
        if ( *(_QWORD *)(v40 + 40) )
          v21 = *(const unsigned __int16 **)(v40 + 40);
        if ( (int)MmpcRetrieveResourceUrl(v21, v22, a3, v20, Str, a4) >= 0 )
        {
          v44 = 0;
          if ( UuidFromStringW(a3, &v44) >= 0 )
          {
            v45 = v44;
            SetEnrollmentResourceCache(&v45, *a4);
          }
LABEL_39:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
LABEL_40:
          v8 = 0;
          goto LABEL_63;
        }
      }
      else
      {
        v23 = *(_WORD **)(v40 + 56);
        if ( v23 && *v23 )
        {
          Str = 0;
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v43,
            v23,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &Str,
            &v43);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
          v24 = Str;
          if ( !Str )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
            v8 = 14;
            goto LABEL_63;
          }
          v25 = wcsstr(Str, L"https://");
          if ( v25 )
          {
            v27 = wcschr(v25 + 9, 0x2Fu);
            if ( v27 )
              v27[1] = 0;
          }
          Str = 0;
          *a4 = v24;
          LOBYTE(v26) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
            v26);
          goto LABEL_39;
        }
        v28 = *(_WORD **)(v40 + 144);
        if ( !v28 || !*v28 )
        {
          v8 = -2145845235;
          goto LABEL_63;
        }
        Str = 0;
        LOBYTE(v23) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
          v23);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &Str,
          0);
        if ( (int)DmGetAadDeviceMdmEnrollmentResourceUrlWithDiscovery(
                    a1,
                    *(const unsigned __int16 **)(v40 + 144),
                    0,
                    a2,
                    &Str,
                    0) >= 0 )
        {
          v29 = Str;
          Str = 0;
          *a4 = v29;
          v43 = 0;
          if ( UuidFromStringW(a3, &v43) >= 0 )
          {
            v45 = v43;
            SetEnrollmentResourceCache(&v45, *a4);
          }
          goto LABEL_39;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      LOBYTE(v30) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl'::`2'::impl,
        v30);
      Str = 0;
      v45 = 0;
      EnrollmentResourceCache = UuidFromStringW(a3, &v45);
      v8 = EnrollmentResourceCache;
      if ( EnrollmentResourceCache >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &Str,
          0);
        v44 = v45;
        EnrollmentResourceCache = GetEnrollmentResourceCache(&v44, &Str);
        v8 = EnrollmentResourceCache;
        if ( EnrollmentResourceCache >= 0 )
        {
          hlocal_string = (unsigned __int16 **)wil::make_hlocal_string((wil *)&v43, Str, v33);
          v35 = *hlocal_string;
          *hlocal_string = 0;
          *a4 = v35;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
          goto LABEL_40;
        }
        v32 = 1283;
      }
      else
      {
        v32 = 1282;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
        (const char *)(unsigned int)EnrollmentResourceCache,
        v38);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      goto LABEL_63;
    }
    Str = 0;
    LOBYTE(v44.Data1) = 0;
    BYTE2(v44.Data1) = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &Str,
      0);
    ActiveUserSid = DmGetActiveUserSid(&Str);
    v8 = ActiveUserSid;
    if ( ActiveUserSid >= 0 )
    {
      AutoImpersonate::ImpersonateSID((AutoImpersonate *)&v44, Str);
      v17 = v40;
      if ( v40 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v43);
        DsrFreeJoinInfoEx(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v43);
      }
      v40 = 0;
      ActiveUserSid = DsrGetJoinInfoEx(1, &v42, &v40);
      v8 = ActiveUserSid;
      if ( ActiveUserSid >= 0 )
      {
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v44);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        goto LABEL_24;
      }
      v16 = 1157;
    }
    else
    {
      v16 = 1155;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      v37);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v44);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
    goto LABEL_63;
  }
  v9 = 1134;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\tokenutils\\tokenutils.cpp",
    (const char *)v8,
    v37);
  return v8;
}

```

## disassembly

```asm
0x180074fa0  push    rbp
0x180074fa2  push    rbx
0x180074fa3  push    rsi
0x180074fa4  push    rdi
0x180074fa5  push    r12
0x180074fa7  push    r13
0x180074fa9  push    r14
0x180074fab  push    r15
0x180074fad  lea     rbp, [rsp-1Fh]
0x180074fb2  sub     rsp, 0A8h
0x180074fb9  mov     rax, cs:__security_cookie
0x180074fc0  xor     rax, rsp
0x180074fc3  mov     [rbp+57h+var_50], rax
0x180074fc7  mov     rdi, r9
0x180074fca  mov     rsi, r8
0x180074fcd  mov     r15, rdx
0x180074fd0  mov     r12, rcx
0x180074fd3  xorps   xmm0, xmm0
0x180074fd6  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180074fda  mov     [rbp+57h+var_A0], 3Fh ; '?'
0x180074fe1  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180074fe5  mov     rcx, r8; StringUuid
0x180074fe8  call    cs:__imp_UuidFromStringW
0x180074fef  nop     dword ptr [rax+rax+00h]
0x180074ff4  mov     ebx, eax
0x180074ff6  xor     r13d, r13d
0x180074ff9  test    eax, eax
0x180074ffb  jns     short loc_18007501A
0x180074ffd  mov     edx, 46Eh; void *
0x180075002  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180075009  mov     r9d, ebx; char *
0x18007500c  mov     rcx, [rbp+5Fh]; this
0x180075010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075015  jmp     loc_1800754BE
0x18007501a  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18007501e  movdqa  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x180075023  lea     rdx, [rbp+57h+var_A0]
0x180075027  lea     rcx, [rbp+57h+var_70]
0x18007502b  call    cs:__imp_GetEnrollmentType
0x180075032  nop     dword ptr [rax+rax+00h]
0x180075037  mov     ebx, eax
0x180075039  cmp     eax, 80070002h
0x18007503e  jnz     short loc_180075047
0x180075040  mov     ebx, 82AE0006h
0x180075045  jmp     short loc_18007504B
0x180075047  test    eax, eax
0x180075049  jns     short loc_180075052
0x18007504b  mov     edx, 474h
0x180075050  jmp     short loc_180075002
0x180075052  mov     eax, [rbp+57h+var_A0]
0x180075055  cmp     eax, 1Ah
0x180075058  jz      short loc_180075062
0x18007505a  mov     r14b, r13b
0x18007505d  cmp     eax, 18h
0x180075060  jnz     short loc_180075065
0x180075062  mov     r14b, 1
0x180075065  mov     [rbp+57h+var_A8], r13
0x180075069  mov     [rbp+57h+var_98], r15
0x18007506d  cmp     eax, 18h
0x180075070  jz      short loc_1800750BB
0x180075072  cmp     eax, 0Dh
0x180075075  jz      short loc_1800750BB
0x180075077  mov     [rbp+57h+var_A8], r13
0x18007507b  lea     r8, [rbp+57h+var_A8]
0x18007507f  lea     rdx, [rbp+57h+var_98]
0x180075083  mov     ecx, 1
0x180075088  call    cs:__imp_DsrGetJoinInfoEx
0x18007508f  nop     dword ptr [rax+rax+00h]
0x180075094  mov     ebx, eax
0x180075096  test    eax, eax
0x180075098  jns     loc_18007517A
0x18007509e  mov     r9d, eax; char *
0x1800750a1  mov     edx, 489h; void *
0x1800750a6  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x1800750ad  mov     rcx, [rbp+5Fh]; this
0x1800750b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800750b6  jmp     loc_1800754B5
0x1800750bb  mov     [rbp+57h+Str], r13
0x1800750bf  mov     byte ptr [rbp+57h+var_80.Data1], r13b
0x1800750c3  mov     byte ptr [rbp+57h+var_80.Data1+2], r13b
0x1800750c7  xor     edx, edx
0x1800750c9  lea     rcx, [rbp+57h+Str]
0x1800750cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800750d2  lea     rcx, [rbp+57h+Str]; unsigned __int16 **
0x1800750d6  call    ?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800750db  mov     ebx, eax
0x1800750dd  test    eax, eax
0x1800750df  jns     short loc_1800750E8
0x1800750e1  mov     edx, 483h
0x1800750e6  jmp     short loc_180075147
0x1800750e8  mov     rdx, [rbp+57h+Str]; unsigned __int16 *
0x1800750ec  lea     rcx, [rbp+57h+var_80]; this
0x1800750f0  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800750f5  mov     rbx, [rbp+57h+var_A8]
0x1800750f9  test    rbx, rbx
0x1800750fc  jz      short loc_18007511F
0x1800750fe  lea     rcx, [rbp+57h+var_90]; this
0x180075102  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180075107  mov     rcx, rbx
0x18007510a  call    cs:__imp_DsrFreeJoinInfoEx
0x180075111  nop     dword ptr [rax+rax+00h]
0x180075116  lea     rcx, [rbp+57h+var_90]; this
0x18007511a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007511f  mov     [rbp+57h+var_A8], r13
0x180075123  lea     r8, [rbp+57h+var_A8]
0x180075127  lea     rdx, [rbp+57h+var_98]
0x18007512b  mov     ecx, 1
0x180075130  call    cs:__imp_DsrGetJoinInfoEx
0x180075137  nop     dword ptr [rax+rax+00h]
0x18007513c  mov     ebx, eax
0x18007513e  test    eax, eax
0x180075140  jns     short loc_180075167
0x180075142  mov     edx, 485h; void *
0x180075147  mov     r9d, eax; char *
0x18007514a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180075151  mov     rcx, [rbp+5Fh]; this
0x180075155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007515a  nop
0x18007515b  lea     rcx, [rbp+57h+var_80]; this
0x18007515f  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180075164  nop
0x180075165  jmp     short loc_1800751D5
0x180075167  lea     rcx, [rbp+57h+var_80]; this
0x18007516b  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180075170  nop
0x180075171  lea     rcx, [rbp+57h+Str]
0x180075175  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007517a  mov     rax, [rbp+57h+var_A8]
0x18007517e  test    rax, rax
0x180075181  jnz     short loc_180075195
0x180075183  mov     ebx, 801C0450h
0x180075188  mov     r9d, ebx
0x18007518b  mov     edx, 48Dh
0x180075190  jmp     loc_1800750A6
0x180075195  test    r14b, r14b
0x180075198  jz      loc_180075292
0x18007519e  mov     [rbp+57h+Str], r13
0x1800751a2  xor     edx, edx
0x1800751a4  lea     rcx, [rbp+57h+Str]
0x1800751a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800751ad  lea     rcx, [rbp+57h+Str]; unsigned __int16 **
0x1800751b1  call    ?CreateCorrelationId@@YAJPEAPEAG@Z; CreateCorrelationId(ushort * *)
0x1800751b6  mov     ebx, eax
0x1800751b8  test    eax, eax
0x1800751ba  jns     short loc_1800751E3
0x1800751bc  mov     rcx, [rbp+5Fh]; this
0x1800751c0  mov     r9d, eax; char *
0x1800751c3  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x1800751ca  mov     edx, 493h; void *
0x1800751cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800751d4  nop
0x1800751d5  lea     rcx, [rbp+57h+Str]
0x1800751d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800751de  jmp     loc_1800754B5
0x1800751e3  mov     dl, 1
0x1800751e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781> `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl(void)'::`2'::impl
0x1800751ec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800751f1  mov     r8, [rbp+57h+Str]
0x1800751f5  lea     r9, aDevice; "Device"
0x1800751fc  lea     rax, aUser; "User"
0x180075203  cmp     [rbp+57h+var_A0], 1Ah
0x180075207  cmovnz  r9, rax; unsigned __int16 *
0x18007520b  mov     rax, [rbp+57h+var_A8]
0x18007520f  lea     rcx, pszSrc
0x180075216  mov     rdx, rcx
0x180075219  cmp     [rax+20h], r13
0x18007521d  cmovnz  rdx, [rax+20h]; unsigned __int16 *
0x180075222  cmp     [rax+28h], r13
0x180075226  cmovnz  rcx, [rax+28h]; unsigned __int16 *
0x18007522b  mov     [rsp+0E0h+var_B8], rdi; unsigned __int16 **
0x180075230  mov     [rsp+0E0h+var_C0], r8; int
0x180075235  mov     r8, rsi; unsigned __int16 *
0x180075238  call    ?MmpcRetrieveResourceUrl@@YAJPEBG0000PEAPEAG@Z; MmpcRetrieveResourceUrl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18007523d  test    eax, eax
0x18007523f  js      short loc_18007528D
0x180075241  xorps   xmm0, xmm0
0x180075244  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x180075248  lea     rdx, [rbp+57h+var_80]; Uuid
0x18007524c  mov     rcx, rsi; StringUuid
0x18007524f  call    cs:__imp_UuidFromStringW
0x180075256  nop     dword ptr [rax+rax+00h]
0x18007525b  test    eax, eax
0x18007525d  js      short loc_18007527C
0x18007525f  movaps  xmm0, xmmword ptr [rbp+57h+var_80.Data1]
0x180075263  movdqa  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x180075268  mov     rdx, [rdi]
0x18007526b  lea     rcx, [rbp+57h+var_70]
0x18007526f  call    cs:__imp_SetEnrollmentResourceCache
0x180075276  nop     dword ptr [rax+rax+00h]
0x18007527b  nop
0x18007527c  lea     rcx, [rbp+57h+Str]
0x180075280  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180075285  mov     ebx, r13d
0x180075288  jmp     loc_1800754B5
0x18007528d  jmp     loc_1800753EE
0x180075292  mov     rdx, [rax+38h]
0x180075296  test    rdx, rdx
0x180075299  jz      loc_180075341
0x18007529f  cmp     r13w, [rdx]
0x1800752a3  jz      loc_180075341
0x1800752a9  mov     [rbp+57h+Str], r13
0x1800752ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800752b1  lea     rcx, [rbp+57h+var_90]
0x1800752b5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800752ba  lea     rdx, [rbp+57h+var_90]
0x1800752be  lea     rcx, [rbp+57h+Str]
0x1800752c2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800752c7  lea     rcx, [rbp+57h+var_90]
0x1800752cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800752d0  mov     rbx, [rbp+57h+Str]
0x1800752d4  test    rbx, rbx
0x1800752d7  jnz     short loc_1800752EC
0x1800752d9  lea     rcx, [rbp+57h+Str]
0x1800752dd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800752e2  mov     ebx, 0Eh
0x1800752e7  jmp     loc_1800754B5
0x1800752ec  lea     rdx, aHttps; "https://"
0x1800752f3  mov     rcx, rbx; Str
0x1800752f6  call    cs:__imp_wcsstr
0x1800752fd  nop     dword ptr [rax+rax+00h]
0x180075302  test    rax, rax
0x180075305  jz      short loc_180075326
0x180075307  mov     edx, 2Fh ; '/'; Ch
0x18007530c  lea     rcx, [rax+12h]; Str
0x180075310  call    cs:__imp_wcschr
0x180075317  nop     dword ptr [rax+rax+00h]
0x18007531c  test    rax, rax
0x18007531f  jz      short loc_180075326
0x180075321  mov     [rax+2], r13w
0x180075326  mov     [rbp+57h+Str], r13
0x18007532a  mov     [rdi], rbx
0x18007532d  mov     dl, 1
0x18007532f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781> `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl(void)'::`2'::impl
0x180075336  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007533b  nop
0x18007533c  jmp     loc_18007527C
0x180075341  mov     rcx, [rax+90h]
0x180075348  test    rcx, rcx
0x18007534b  jz      loc_1800754B0
0x180075351  cmp     r13w, [rcx]
0x180075355  jz      loc_1800754B0
0x18007535b  mov     [rbp+57h+Str], r13
0x18007535f  mov     dl, 1
0x180075361  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781> `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl(void)'::`2'::impl
0x180075368  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007536d  xor     edx, edx
0x18007536f  lea     rcx, [rbp+57h+Str]
0x180075373  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180075378  mov     [rsp+0E0h+var_B8], r13; unsigned __int16 **
0x18007537d  lea     rax, [rbp+57h+Str]
0x180075381  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x180075386  mov     r9, r15; PCWSTR
0x180075389  xor     r8d, r8d; unsigned __int16 *
0x18007538c  mov     rdx, [rbp+57h+var_A8]
0x180075390  mov     rdx, [rdx+90h]; unsigned __int16 *
0x180075397  mov     rcx, r12; sourceString
0x18007539a  call    ?DmGetAadDeviceMdmEnrollmentResourceUrlWithDiscovery@@YAJPEBG000PEAPEAG1@Z; DmGetAadDeviceMdmEnrollmentResourceUrlWithDiscovery(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18007539f  test    eax, eax
0x1800753a1  js      short loc_1800753EE
0x1800753a3  mov     rax, [rbp+57h+Str]
0x1800753a7  mov     [rbp+57h+Str], r13
0x1800753ab  mov     [rdi], rax
0x1800753ae  xorps   xmm0, xmm0
0x1800753b1  movups  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800753b5  lea     rdx, [rbp+57h+var_90]; Uuid
0x1800753b9  mov     rcx, rsi; StringUuid
0x1800753bc  call    cs:__imp_UuidFromStringW
0x1800753c3  nop     dword ptr [rax+rax+00h]
0x1800753c8  test    eax, eax
0x1800753ca  js      short loc_1800753E9
0x1800753cc  movaps  xmm0, xmmword ptr [rbp+57h+var_90.Data1]
0x1800753d0  movdqa  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1800753d5  mov     rdx, [rdi]
0x1800753d8  lea     rcx, [rbp+57h+var_70]
0x1800753dc  call    cs:__imp_SetEnrollmentResourceCache
0x1800753e3  nop     dword ptr [rax+rax+00h]
0x1800753e8  nop
0x1800753e9  jmp     loc_18007527C
0x1800753ee  lea     rcx, [rbp+57h+Str]
0x1800753f2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800753f7  mov     dl, 1
0x1800753f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781> `wil::Feature<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::GetImpl(void)'::`2'::impl
0x180075400  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WPJRecoveryFix56099781@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WPJRecoveryFix56099781>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180075405  mov     [rbp+57h+Str], r13
0x180075409  xorps   xmm0, xmm0
0x18007540c  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x180075410  lea     rdx, [rbp+57h+var_70]; Uuid
0x180075414  mov     rcx, rsi; StringUuid
0x180075417  call    cs:__imp_UuidFromStringW
0x18007541e  nop     dword ptr [rax+rax+00h]
0x180075423  mov     ebx, eax
0x180075425  test    eax, eax
0x180075427  jns     short loc_18007544D
0x180075429  mov     edx, 502h; void *
0x18007542e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmcmnutils\\toke"...
0x180075435  mov     r9d, eax; char *
0x180075438  mov     rcx, [rbp+5Fh]; this
0x18007543c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075441  nop
0x180075442  lea     rcx, [rbp+57h+Str]
  ... truncated ...
```
