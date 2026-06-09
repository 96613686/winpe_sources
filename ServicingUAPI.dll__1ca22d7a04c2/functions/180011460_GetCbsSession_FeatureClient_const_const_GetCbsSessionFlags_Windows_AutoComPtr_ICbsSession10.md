# GetCbsSession(FeatureClient const * const,GetCbsSessionFlags,Windows::AutoComPtr<ICbsSession10> &)

- ea: `0x180011460`
- end: `0x180011bef`
- name: `?GetCbsSession@@YAXQEBUFeatureClient@@W4GetCbsSessionFlags@@AEAV?$AutoComPtr@UICbsSession10@@@Windows@@@Z`
- size: `1935`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010638`

## callees

- `0x1800031d0`
- `0x180008a90`
- `0x180009750`
- `0x18000aedc`
- `0x18000c468`
- `0x18000f5cc`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x18000fef0`
- `0x180010450`
- `0x180011460`
- `0x1800126b8`
- `0x18002bc54`
- `0x18002dd20`
- `0x180192920`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18001158e`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x18001158e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011718`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011718`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180011811`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180011811`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011749`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011749`

## string_xrefs

- `0x180011aad`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011ac2`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b0a`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b1c`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b31`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b51`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b89`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011b9e`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011bb3`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011bc8`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011bdd`: `onecore\base\servicing\uapi\lib\common.cpp`
- `0x180011612`: `Failed to get running module path`
- `0x180011694`: `Failed to create offline session`
- `0x180011b6d`: `Failed to create session classID`
- `0x180011734`: `Failed to create session classID - waiting for a second and trying again`
- `0x1800118f9`: `Failed to set CBS session source repository path`
- `0x18001196b`: `servicing\InboxFodMetadataCache`
- `0x1800119d7`: `Failed to add inbox metadata cache directory as a source`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
IUnknown *__fastcall GetCbsSession(__int64 a1, __int64 a2, IUnknown **a3)
{
  unsigned __int64 v5; // r14
  __int64 v6; // r12
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r8
  _QWORD *v9; // rbx
  _QWORD *v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rdx
  PCZZWSTR *v13; // rcx
  PCZZWSTR *v14; // rcx
  const WCHAR *v15; // rdx
  const char *v16; // r9
  _WORD *v17; // rcx
  signed int RunningDllPath; // eax
  int v19; // esi
  __int64 v20; // rdx
  const wchar_t *v21; // rdx
  signed int v22; // eax
  int v23; // esi
  __int64 v24; // rdx
  char v25; // r15
  HRESULT Instance; // eax
  __int64 v27; // rcx
  unsigned int v28; // esi
  signed int v29; // eax
  int v30; // esi
  __int64 v31; // r10
  __int64 v32; // rdx
  IUnknown *v33; // rcx
  HRESULT v34; // eax
  signed int v35; // eax
  int v36; // esi
  __int64 v37; // rdx
  signed int v38; // eax
  int v39; // edi
  __int64 v40; // rdx
  const WCHAR *v41; // rcx
  _QWORD *v42; // r8
  signed int v43; // eax
  int v44; // edi
  __int64 v45; // rdx
  IUnknown *v46; // rcx
  IUnknown *result; // rax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  int *ppv; // [rsp+28h] [rbp-79h]
  int ppva; // [rsp+28h] [rbp-79h]
  int *ppvb; // [rsp+28h] [rbp-79h]
  int v54[2]; // [rsp+48h] [rbp-59h] BYREF
  __int64 v55; // [rsp+50h] [rbp-51h]
  __int64 v56; // [rsp+58h] [rbp-49h]
  ULONG pulNumLanguages; // [rsp+60h] [rbp-41h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp-39h] BYREF
  PCZZWSTR pwszLanguagesBuffer[2]; // [rsp+70h] [rbp-31h] BYREF
  __m128i si128; // [rsp+80h] [rbp-21h]
  struct ICbsSession *v61; // [rsp+90h] [rbp-11h] BYREF
  _QWORD v62[4]; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v56 = -2;
  v5 = 0;
  v61 = 0;
  if ( *(_QWORD *)(a1 + 176) > 1u )
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::Log<>(
        a1,
        3,
        "FeatureClient.Sources.Length > 1; CBS only supports a single package source per session.");
    v49 = EnsureNTSTATUS<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)v49,
      (int)ppv);
  }
  v6 = -1;
  if ( *(_QWORD *)(a1 + 152) )
  {
    *(_OWORD *)pwszLanguagesBuffer = 0;
    v7 = 0;
    si128.m128i_i64[0] = 0;
    v8 = 7;
    si128.m128i_i64[1] = 7;
    LOWORD(pwszLanguagesBuffer[0]) = 0;
    v9 = *(_QWORD **)(a1 + 144);
    v10 = &v9[*(_QWORD *)(a1 + 152)];
    if ( v9 != v10 )
    {
      do
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(*v9 + 2 * v11) );
        std::wstring::_Append<wchar_t>(pwszLanguagesBuffer);
        v12 = si128.m128i_i64[0];
        v13 = pwszLanguagesBuffer;
        if ( si128.m128i_i64[0] >= (unsigned __int64)si128.m128i_i64[1] )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(pwszLanguagesBuffer);
        }
        else
        {
          ++si128.m128i_i64[0];
          if ( si128.m128i_i64[1] > 7uLL )
            v13 = (PCZZWSTR *)pwszLanguagesBuffer[0];
          *(_DWORD *)((char *)v13 + 2 * v12) = 0;
        }
        ++v9;
      }
      while ( v9 != v10 );
      v8 = si128.m128i_u64[1];
      v7 = si128.m128i_i64[0];
    }
    v14 = pwszLanguagesBuffer;
    if ( v7 >= v8 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(pwszLanguagesBuffer);
    }
    else
    {
      si128.m128i_i64[0] = v7 + 1;
      if ( v8 > 7 )
        v14 = (PCZZWSTR *)pwszLanguagesBuffer[0];
      *(_DWORD *)((char *)v14 + 2 * v7) = 0;
    }
    pulNumLanguages = *(_DWORD *)(a1 + 152);
    v15 = (const WCHAR *)pwszLanguagesBuffer;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = pwszLanguagesBuffer[0];
    if ( !SetThreadPreferredUILanguages(0, v15, &pulNumLanguages) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        v16);
    std::wstring::~wstring(pwszLanguagesBuffer);
  }
  if ( (*(_BYTE *)(a1 + 160) & 1) != 0 && (v17 = *(_WORD **)(a1 + 192)) != 0 && *v17 )
  {
    *(_OWORD *)pwszLanguagesBuffer = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(pwszLanguagesBuffer[0]) = 0;
    RunningDllPath = GetRunningDllPath(pwszLanguagesBuffer);
    v19 = RunningDllPath;
    if ( RunningDllPath < 0 )
    {
      pulNumLanguages = RunningDllPath;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get running module path");
        *(_QWORD *)v54 = &pulNumLanguages;
        ppv = v54;
        LOBYTE(v20) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v20,
          3,
          ": {}");
      }
    }
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v19,
        (int)ppv);
    if ( v61 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      __debugbreak();
    }
    v21 = (const wchar_t *)pwszLanguagesBuffer;
    if ( si128.m128i_i64[1] > 7uLL )
      v21 = pwszLanguagesBuffer[0];
    v22 = CbsOfflineUtil::CbsCreateOfflineSession((CbsOfflineUtil *)&vCbsOfflineUtil, v21, &v61);
    v23 = v22;
    if ( v22 < 0 )
    {
      pulNumLanguages = v22;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to create offline session");
        *(_QWORD *)v54 = &pulNumLanguages;
        ppv = v54;
        LOBYTE(v24) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v24,
          3,
          ": {}");
      }
    }
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v23,
        (int)ppv);
    v25 = 1;
    std::wstring::~wstring(pwszLanguagesBuffer);
  }
  else
  {
    v25 = 0;
    while ( 1 )
    {
      if ( v61 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        __debugbreak();
      }
      Instance = CoCreateInstance(
                   &CLSID_CbsSession,
                   0,
                   0x15u,
                   &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
                   (LPVOID *)&v61);
      v28 = Instance;
      if ( Instance >= 0 )
        break;
      if ( v5 >= 0xA )
      {
        if ( *(_QWORD *)&LogAdapter::g_Logger )
          LogAdapter::Logger::Log<>(v27, 3, "Failed to create session classID");
        v50 = EnsureNTSTATUS<long>(v28);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
          (const char *)v50,
          (int)ppv);
      }
      LogAdapter::TraceAtLevelHr<long,>(
        3,
        (unsigned int)Instance,
        "Failed to create session classID - waiting for a second and trying again");
      Sleep(0x3E8u);
      ++v5;
    }
  }
  pProxy = 0;
  v29 = (**(__int64 (__fastcall ***)(struct ICbsSession *, GUID *, IUnknown **))v61)(
          v61,
          &GUID_f112757a_565b_4260_bd05_9fa34417349a,
          &pProxy);
  v30 = v29;
  v31 = *(_QWORD *)&LogAdapter::g_Logger;
  if ( v29 < 0 )
  {
    pulNumLanguages = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to query session.");
      *(_QWORD *)v54 = &pulNumLanguages;
      ppv = v54;
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v32,
        3,
        ": {}");
      v31 = *(_QWORD *)&LogAdapter::g_Logger;
    }
  }
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)(unsigned int)v30,
      (int)ppv);
  v33 = pProxy;
  if ( !pProxy )
  {
    if ( v31 )
      LogAdapter::Logger::Log<>(0, 3, "Invalid CBS session");
    v48 = EnsureNTSTATUS<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)v48,
      (int)ppv);
  }
  if ( !v25 )
  {
    v34 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v34,
        ppva);
    v33 = pProxy;
  }
  ppvb = *(int **)(a1 + 192);
  v35 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))v33->lpVtbl[6].AddRef)(
          v33,
          0,
          *(_QWORD *)a1,
          *(_QWORD *)(a1 + 184));
  v36 = v35;
  if ( v35 < 0 )
  {
    pulNumLanguages = v35;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to initialize CBS session");
      *(_QWORD *)v54 = &pulNumLanguages;
      ppvb = v54;
      LOBYTE(v37) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v37,
        3,
        ": {}");
    }
  }
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
      (const char *)(unsigned int)v36,
      (int)ppvb);
  if ( *(_QWORD *)(a1 + 176) == 1 )
  {
    v38 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD))pProxy->lpVtbl[8].QueryInterface)(
            pProxy,
            1,
            **(_QWORD **)(a1 + 168));
    v39 = v38;
    if ( v38 < 0 )
    {
      pulNumLanguages = v38;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to set CBS session source repository path");
        *(_QWORD *)v54 = &pulNumLanguages;
        ppvb = v54;
        LOBYTE(v40) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v40,
          3,
          ": {}");
      }
    }
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
        (const char *)(unsigned int)v39,
        (int)ppvb);
  }
  else if ( (*(_BYTE *)(a1 + 160) & 1) != 0 )
  {
    v41 = *(const WCHAR **)(a1 + 192);
    if ( v41 )
    {
      if ( *v41 )
      {
        *(_QWORD *)v54 = L"servicing\\InboxFodMetadataCache";
        v55 = 31;
        pwszLanguagesBuffer[0] = v41;
        do
          ++v6;
        while ( v41[v6] );
        pwszLanguagesBuffer[1] = (PCZZWSTR)v6;
        CreatePath(v62, pwszLanguagesBuffer, v54);
        v42 = v62;
        if ( v62[3] > 7u )
          v42 = (_QWORD *)v62[0];
        v43 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD *))pProxy->lpVtbl[5].QueryInterface)(pProxy, 0, v42);
        v44 = v43;
        if ( v43 < 0 )
        {
          pulNumLanguages = v43;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed to add inbox metadata cache directory as a source");
            *(_QWORD *)v54 = &pulNumLanguages;
            ppvb = v54;
            LOBYTE(v45) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v45,
              3,
              ": {}");
          }
        }
        if ( v44 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\common.cpp",
            (const char *)(unsigned int)v44,
            (int)ppvb);
        std::wstring::~wstring(v62);
      }
    }
  }
  v46 = *a3;
  result = pProxy;
  *a3 = pProxy;
  pProxy = v46;
  if ( v46 )
  {
    result = (IUnknown *)((__int64 (__fastcall *)(IUnknown *))v46->lpVtbl->Release)(v46);
    pProxy = 0;
  }
  if ( v61 )
    return (IUnknown *)(*(__int64 (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v61 + 16LL))(v61);
  return result;
}

```

## disassembly

```asm
0x180011460  mov     rax, rsp
0x180011463  push    rbp
0x180011464  push    rsi
0x180011465  push    rdi
0x180011466  push    r12
0x180011468  push    r13
0x18001146a  push    r14
0x18001146c  push    r15
0x18001146e  lea     rbp, [rax-5Fh]
0x180011472  sub     rsp, 0C0h
0x180011479  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x180011481  mov     [rax+10h], rbx
0x180011485  mov     rax, cs:__security_cookie
0x18001148c  xor     rax, rsp
0x18001148f  mov     [rbp+57h+var_40], rax
0x180011493  mov     r13, r8
0x180011496  mov     rdi, rcx
0x180011499  xor     r14d, r14d
0x18001149c  mov     [rbp+57h+var_68], r14
0x1800114a0  cmp     qword ptr [rcx+0B0h], 1
0x1800114a8  ja      loc_180011ADF
0x1800114ae  lea     r15d, [r14+7]
0x1800114b2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800114b6  cmp     [rcx+98h], r14
0x1800114bd  jz      loc_1800115AF
0x1800114c3  xorps   xmm0, xmm0
0x1800114c6  movups  xmmword ptr [rbp+57h+pwszLanguagesBuffer], xmm0
0x1800114ca  mov     edx, r14d
0x1800114cd  mov     qword ptr [rbp+57h+var_78], rdx
0x1800114d1  mov     r8d, r15d
0x1800114d4  mov     qword ptr [rbp+57h+var_78+8], r15
0x1800114d8  mov     word ptr [rbp+57h+pwszLanguagesBuffer], r14w
0x1800114dd  mov     rbx, [rcx+90h]
0x1800114e4  mov     rax, [rcx+98h]
0x1800114eb  lea     rsi, [rbx+rax*8]
0x1800114ef  cmp     rbx, rsi
0x1800114f2  jz      short loc_18001154B
0x1800114f4  mov     rdx, [rbx]
0x1800114f7  mov     r8, r12
0x1800114fa  inc     r8
0x1800114fd  cmp     [rdx+r8*2], r14w
0x180011502  jnz     short loc_1800114FA
0x180011504  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; Src
0x180011508  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001150d  mov     rdx, qword ptr [rbp+57h+var_78]
0x180011511  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; Src
0x180011515  cmp     rdx, qword ptr [rbp+57h+var_78+8]
0x180011519  jnb     short loc_180011532
0x18001151b  lea     rax, [rdx+1]
0x18001151f  mov     qword ptr [rbp+57h+var_78], rax
0x180011523  cmp     qword ptr [rbp+57h+var_78+8], r15
0x180011527  cmova   rcx, [rbp+57h+pwszLanguagesBuffer]
0x18001152c  mov     [rcx+rdx*2], r14d
0x180011530  jmp     short loc_18001153A
0x180011532  xor     r9d, r9d
0x180011535  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001153a  add     rbx, 8
0x18001153e  cmp     rbx, rsi
0x180011541  jnz     short loc_1800114F4
0x180011543  mov     r8, qword ptr [rbp+57h+var_78+8]
0x180011547  mov     rdx, qword ptr [rbp+57h+var_78]
0x18001154b  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; Src
0x18001154f  cmp     rdx, r8
0x180011552  jnb     short loc_18001156A
0x180011554  lea     rax, [rdx+1]
0x180011558  mov     qword ptr [rbp+57h+var_78], rax
0x18001155c  cmp     r8, r15
0x18001155f  cmova   rcx, [rbp+57h+pwszLanguagesBuffer]
0x180011564  mov     [rcx+rdx*2], r14d
0x180011568  jmp     short loc_180011572
0x18001156a  xor     r9d, r9d
0x18001156d  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x180011572  mov     eax, [rdi+98h]
0x180011578  mov     [rbp+57h+pulNumLanguages], eax
0x18001157b  lea     rdx, [rbp+57h+pwszLanguagesBuffer]
0x18001157f  cmp     qword ptr [rbp+57h+var_78+8], r15
0x180011583  cmova   rdx, [rbp+57h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180011588  lea     r8, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x18001158c  xor     ecx, ecx; dwFlags
0x18001158e  call    cs:__imp_SetThreadPreferredUILanguages
0x180011595  nop     dword ptr [rax+rax+00h]
0x18001159a  mov     rcx, [rbp+5Fh]; this
0x18001159e  test    eax, eax
0x1800115a0  jz      loc_180011B1C
0x1800115a6  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; void *
0x1800115aa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800115af  test    byte ptr [rdi+0A0h], 1
0x1800115b6  jz      loc_1800116E8
0x1800115bc  mov     rcx, [rdi+0C0h]
0x1800115c3  test    rcx, rcx
0x1800115c6  jz      loc_1800116E8
0x1800115cc  cmp     r14w, [rcx]
0x1800115d0  jz      loc_1800116E8
0x1800115d6  xorps   xmm0, xmm0
0x1800115d9  movups  xmmword ptr [rbp+57h+pwszLanguagesBuffer], xmm0
0x1800115dd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800115e5  movdqu  [rbp+57h+var_78], xmm1
0x1800115ea  mov     word ptr [rbp+57h+pwszLanguagesBuffer], r14w
0x1800115ef  lea     rcx, [rbp+57h+pwszLanguagesBuffer]
0x1800115f3  call    ?GetRunningDllPath@@YAJPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetRunningDllPath(std::wstring *)
0x1800115f8  mov     esi, eax
0x1800115fa  mov     ebx, 3
0x1800115ff  test    eax, eax
0x180011601  jns     short loc_18001164C
0x180011603  mov     [rbp+57h+pulNumLanguages], eax
0x180011606  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001160d  test    rcx, rcx
0x180011610  jz      short loc_18001164C
0x180011612  lea     r9, aFailedToGetRun_0; "Failed to get running module path"
0x180011619  mov     r8d, ebx
0x18001161c  xor     edx, edx
0x18001161e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180011623  lea     rax, [rbp+57h+pulNumLanguages]
0x180011627  mov     qword ptr [rbp+57h+var_B0], rax
0x18001162b  lea     rax, [rbp+57h+var_B0]
0x18001162f  mov     [rsp+0F0h+ppv], rax; int
0x180011634  lea     r9, asc_1801CAFB4; ": {}"
0x18001163b  mov     r8d, ebx
0x18001163e  mov     dl, 1
0x180011640  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011647  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001164c  mov     rcx, [rbp+5Fh]; this
0x180011650  test    esi, esi
0x180011652  js      loc_180011B2E
0x180011658  cmp     [rbp+57h+var_68], r14
0x18001165c  jnz     loc_180011B43
0x180011662  lea     rdx, [rbp+57h+pwszLanguagesBuffer]
0x180011666  cmp     qword ptr [rbp+57h+var_78+8], r15
0x18001166a  cmova   rdx, [rbp+57h+pwszLanguagesBuffer]; wchar_t *
0x18001166f  lea     r8, [rbp+57h+var_68]; struct ICbsSession **
0x180011673  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x18001167a  call    ?CbsCreateOfflineSession@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateOfflineSession(wchar_t const *,ICbsSession * *)
0x18001167f  mov     esi, eax
0x180011681  test    eax, eax
0x180011683  jns     short loc_1800116CE
0x180011685  mov     [rbp+57h+pulNumLanguages], eax
0x180011688  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001168f  test    rcx, rcx
0x180011692  jz      short loc_1800116CE
0x180011694  lea     r9, aFailedToCreate_19; "Failed to create offline session"
0x18001169b  mov     r8d, ebx
0x18001169e  xor     edx, edx
0x1800116a0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800116a5  lea     rax, [rbp+57h+pulNumLanguages]
0x1800116a9  mov     qword ptr [rbp+57h+var_B0], rax
0x1800116ad  lea     rax, [rbp+57h+var_B0]
0x1800116b1  mov     [rsp+0F0h+ppv], rax; int
0x1800116b6  lea     r9, asc_1801CAFB4; ": {}"
0x1800116bd  mov     r8d, ebx
0x1800116c0  mov     dl, 1
0x1800116c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800116c9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800116ce  mov     rcx, [rbp+5Fh]; this
0x1800116d2  test    esi, esi
0x1800116d4  js      loc_180011B4E
0x1800116da  mov     r15b, 1
0x1800116dd  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; void *
0x1800116e1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800116e6  jmp     short loc_18001175D
0x1800116e8  mov     r15b, r14b
0x1800116eb  mov     ebx, 3
0x1800116f0  cmp     [rbp+57h+var_68], 0
0x1800116f5  jnz     loc_180011AD4
0x1800116fb  lea     rax, [rbp+57h+var_68]
0x1800116ff  mov     [rsp+0F0h+ppv], rax; int
0x180011704  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x18001170b  xor     edx, edx; pUnkOuter
0x18001170d  lea     r8d, [rdx+15h]; dwClsContext
0x180011711  lea     rcx, CLSID_CbsSession; rclsid
0x180011718  call    cs:__imp_CoCreateInstance
0x18001171f  nop     dword ptr [rax+rax+00h]
0x180011724  mov     esi, eax
0x180011726  test    eax, eax
0x180011728  jns     short loc_18001175A
0x18001172a  cmp     r14, 0Ah
0x18001172e  jnb     loc_180011B63
0x180011734  lea     r8, aFailedToCreate_5; "Failed to create session classID - wait"...
0x18001173b  mov     edx, eax
0x18001173d  mov     ecx, ebx
0x18001173f  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180011744  mov     ecx, 3E8h; dwMilliseconds
0x180011749  call    cs:__imp_Sleep
0x180011750  nop     dword ptr [rax+rax+00h]
0x180011755  inc     r14
0x180011758  jmp     short loc_1800116F0
0x18001175a  xor     r14d, r14d
0x18001175d  mov     [rbp+57h+pProxy], r14
0x180011761  mov     rcx, [rbp+57h+var_68]
0x180011765  mov     rax, [rcx]
0x180011768  lea     r8, [rbp+57h+pProxy]
0x18001176c  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x180011773  mov     rax, [rax]
0x180011776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001177b  mov     esi, eax
0x18001177d  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011784  test    eax, eax
0x180011786  jns     short loc_1800117D4
0x180011788  mov     [rbp+57h+pulNumLanguages], eax
0x18001178b  test    r10, r10
0x18001178e  jz      short loc_1800117D4
0x180011790  lea     r9, aFailedToQueryS; "Failed to query session."
0x180011797  mov     r8d, ebx
0x18001179a  xor     edx, edx
0x18001179c  mov     rcx, r10
0x18001179f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800117a4  lea     rax, [rbp+57h+pulNumLanguages]
0x1800117a8  mov     qword ptr [rbp+57h+var_B0], rax
0x1800117ac  lea     rax, [rbp+57h+var_B0]
0x1800117b0  mov     [rsp+0F0h+ppv], rax; int
0x1800117b5  lea     r9, asc_1801CAFB4; ": {}"
0x1800117bc  mov     r8d, ebx
0x1800117bf  mov     dl, 1
0x1800117c1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800117c8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800117cd  mov     r10, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800117d4  mov     rcx, [rbp+5Fh]; this
0x1800117d8  test    esi, esi
0x1800117da  js      loc_180011B9B
0x1800117e0  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800117e4  test    rcx, rcx
0x1800117e7  jz      loc_180011A89
0x1800117ed  test    r15b, r15b
0x1800117f0  jnz     short loc_18001182D
0x1800117f2  mov     [rsp+38h], r14d; dwCapabilities
0x1800117f7  mov     [rsp+0F0h+pAuthInfo], r14; pAuthInfo
0x1800117fc  mov     [rsp+0F0h+dwImpLevel], ebx; dwImpLevel
0x180011800  mov     dword ptr [rsp+0F0h+ppv], 5; int
0x180011808  mov     r9, r12; pServerPrincName
0x18001180b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001180e  mov     r8d, edx; dwAuthzSvc
0x180011811  call    cs:__imp_CoSetProxyBlanket
0x180011818  nop     dword ptr [rax+rax+00h]
0x18001181d  mov     rcx, [rbp+5Fh]; this
0x180011821  test    eax, eax
0x180011823  js      loc_180011BB0
0x180011829  mov     rcx, [rbp+57h+pProxy]
0x18001182d  mov     rax, [rcx]
0x180011830  mov     qword ptr [rsp+0F0h+dwImpLevel], r14
0x180011835  mov     rdx, [rdi+0C0h]
0x18001183c  mov     [rsp+0F0h+ppv], rdx
0x180011841  mov     r9, [rdi+0B8h]
0x180011848  mov     r8, [rdi]
0x18001184b  xor     edx, edx
0x18001184d  mov     rax, [rax+98h]
0x180011854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011859  mov     esi, eax
0x18001185b  test    eax, eax
0x18001185d  jns     short loc_1800118A8
0x18001185f  mov     [rbp+57h+pulNumLanguages], eax
0x180011862  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180011869  test    rcx, rcx
0x18001186c  jz      short loc_1800118A8
0x18001186e  lea     r9, aFailedToInitia; "Failed to initialize CBS session"
0x180011875  mov     r8d, ebx
0x180011878  xor     edx, edx
0x18001187a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001187f  lea     rax, [rbp+57h+pulNumLanguages]
0x180011883  mov     qword ptr [rbp+57h+var_B0], rax
0x180011887  lea     rax, [rbp+57h+var_B0]
0x18001188b  mov     [rsp+0F0h+ppv], rax; int
0x180011890  lea     r9, asc_1801CAFB4; ": {}"
0x180011897  mov     r8d, ebx
0x18001189a  mov     dl, 1
0x18001189c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800118a3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800118a8  mov     rcx, [rbp+5Fh]; this
0x1800118ac  test    esi, esi
0x1800118ae  js      loc_180011BC5
0x1800118b4  cmp     qword ptr [rdi+0B0h], 1
0x1800118bc  jnz     loc_180011944
0x1800118c2  mov     rcx, [rbp+57h+pProxy]
0x1800118c6  mov     rax, [rcx]
0x1800118c9  mov     r8, [rdi+0A8h]
0x1800118d0  mov     r8, [r8]
0x1800118d3  mov     edx, 1
0x1800118d8  mov     rax, [rax+0C0h]
0x1800118df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e4  mov     edi, eax
0x1800118e6  test    eax, eax
0x1800118e8  jns     short loc_180011933
0x1800118ea  mov     [rbp+57h+pulNumLanguages], eax
0x1800118ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800118f4  test    rcx, rcx
0x1800118f7  jz      short loc_180011933
0x1800118f9  lea     r9, aFailedToSetCbs; "Failed to set CBS session source reposi"...
0x180011900  mov     r8d, ebx
0x180011903  xor     edx, edx
0x180011905  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001190a  lea     rax, [rbp+57h+pulNumLanguages]
0x18001190e  mov     qword ptr [rbp+57h+var_B0], rax
0x180011912  lea     rax, [rbp+57h+var_B0]
0x180011916  mov     [rsp+0F0h+ppv], rax; int
0x18001191b  lea     r9, asc_1801CAFB4; ": {}"
0x180011922  mov     r8d, ebx
0x180011925  mov     dl, 1
0x180011927  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001192e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180011933  mov     rcx, [rbp+5Fh]; this
0x180011937  test    edi, edi
0x180011939  js      loc_180011ABF
  ... truncated ...
```
