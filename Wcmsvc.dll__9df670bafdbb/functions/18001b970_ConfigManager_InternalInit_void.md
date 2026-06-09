# ConfigManager::InternalInit(void)

- ea: `0x18001b970`
- end: `0x18001c115`
- name: `?InternalInit@ConfigManager@@AEAAXXZ`
- size: `1957`
- prototype: `void __fastcall(ConfigManager *__hidden this)`
- caller_count: `13`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b7f0`
- `0x18003cfb0`
- `0x18003feec`
- `0x18005ddb4`
- `0x180060784`
- `0x1800612e8`
- `0x180061568`
- `0x180064b78`
- `0x180077268`
- `0x18007ac74`
- `0x18007b814`
- `0x18007ca6c`
- `0x18007de48`

## callees

- `0x180007f90`
- `0x1800137a0`
- `0x1800138dc`
- `0x18001b970`
- `0x180024640`
- `0x18002ab74`
- `0x18002abb0`
- `0x180036c74`
- `0x180039f54`
- `0x18003fe94`
- `0x180050944`
- `0x18006bd0c`
- `0x18006f718`
- `0x180084f50`
- `0x180085bc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba30`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf5f`
- `ntdll!RtlNtStatusToDosError` at `0x18001c05d`
- `ntdll!RtlNtStatusToDosError` at `0x18001bf5f`
- `ntdll!RtlNtStatusToDosError` at `0x18001c05d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bcb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bd92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001beba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bb91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bcb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bd92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001beba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bf32`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ba08`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001badf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001ba08`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001badf`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
void __fastcall ConfigManager::InternalInit(ConfigManager *this)
{
  HKEY v1; // rbx
  __int64 v2; // rdi
  NTSTATUS PersistedRegistryLocationW; // eax
  __int64 v4; // rbx
  NTSTATUS v5; // eax
  const char *v6; // r9
  __int64 v7; // rax
  HKEY *v8; // rax
  HKEY *v9; // r14
  HKEY *v10; // rax
  HKEY *v11; // rbx
  __int64 v12; // rax
  HKEY *v13; // rax
  HKEY *v14; // rbx
  __int64 v15; // r8
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  const char *v18; // r9
  __int64 v19; // rax
  HKEY *v20; // rax
  HKEY *v21; // rbx
  ULONG v22; // eax
  __int64 v23; // rdx
  HKEY hKey; // [rsp+30h] [rbp-2A8h] BYREF
  __int128 v25; // [rsp+38h] [rbp-2A0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-290h]
  __int64 v27; // [rsp+50h] [rbp-288h]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+58h] [rbp-280h]
  __int128 v29; // [rsp+60h] [rbp-278h] BYREF
  __int128 Src; // [rsp+70h] [rbp-268h] BYREF
  __int128 v31; // [rsp+80h] [rbp-258h]
  _WORD v32[264]; // [rsp+90h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  EnterCriticalSection(&s_keyLock);
  v28 = &s_keyLock;
  v1 = s_wcmRootKey;
  v2 = s_wcmFailoverPolicyKey;
  if ( s_wcmRootKey && s_wcmFailoverPolicyKey && s_wcmRootPolicyKey && s_wcmGroupPolicyKey && s_wcmLocalPolicyKey )
    goto LABEL_7;
  memset_0(v32, 0, 0x208u);
  if ( v1 && v2 )
    goto LABEL_12;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"WcmSvcRoot", L"Software\\Microsoft\\WcmSvc", v32, 520);
  if ( PersistedRegistryLocationW < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v22 = RtlNtStatusToDosError(PersistedRegistryLocationW);
      v23 = 11;
LABEL_81:
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v23, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v22);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  if ( !s_wcmRootKey )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v32);
    }
    v29 = 0;
    Src = 0;
    v31 = 0;
    v19 = std::wstring::wstring(&v25, v32);
    WcmCommon::Registry::Path::Create<-2147483646>(&v29, v19);
    v20 = (HKEY *)WcmCommon::Registry::TryOpenKeyRW(&hKey, &v29);
    v21 = v20;
    if ( &s_wcmRootKey != v20 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &s_wcmRootKey,
        *v20);
      *v21 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)&v29);
  }
  if ( s_wcmFailoverPolicyKey )
  {
LABEL_12:
    v4 = -1;
  }
  else
  {
    v29 = 0;
    Src = 0;
    v31 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v4 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v32[v15] );
    try
    {
      std::wstring::_Construct<1,unsigned short const *>(&v25, v32);
      WcmCommon::Registry::Path::Create<-2147483646>(&v29, &v25);
      std::wstring::_Append<unsigned short>(&Src);
      std::wstring::_Append<unsigned short>(&Src);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
          (unsigned int)v32,
          (__int64)L"CellularFailover");
      }
      v16 = (_QWORD *)WcmCommon::Registry::TryOpenKeyRW(&hKey, &v29);
      v17 = v16;
      if ( &s_wcmFailoverPolicyKey != (_UNKNOWN *)v16 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &s_wcmFailoverPolicyKey,
          *v16);
        *v17 = 0;
      }
      if ( hKey )
        RegCloseKey(hKey);
      WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)&v29);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
        v18);
      goto LABEL_12;
    }
  }
  if ( !s_wcmRootPolicyKey || !s_wcmGroupPolicyKey || !s_wcmLocalPolicyKey )
  {
    memset_0(v32, 0, 0x208u);
    v5 = GetPersistedRegistryLocationW(L"WcmSvcPolicies", L"Software\\Policies\\Microsoft\\Windows\\WcmSvc", v32, 520);
    if ( v5 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v22 = RtlNtStatusToDosError(v5);
        v23 = 14;
        goto LABEL_81;
      }
    }
    else
    {
      if ( !s_wcmRootPolicyKey )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v32);
        }
        v29 = 0;
        Src = 0;
        v31 = 0;
        v7 = std::wstring::wstring(&v25, v32);
        WcmCommon::Registry::Path::Create<-2147483646>(&v29, v7);
        v8 = (HKEY *)WcmCommon::Registry::TryOpenKeyRO(&hKey, &v29);
        v9 = v8;
        if ( &s_wcmRootPolicyKey != v8 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &s_wcmRootPolicyKey,
            *v8);
          *v9 = 0;
        }
        if ( hKey )
          RegCloseKey(hKey);
        WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)&v29);
      }
      if ( !s_wcmLocalPolicyKey )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_SS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            16,
            (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
            (unsigned int)v32,
            (__int64)L"Local");
        }
        v29 = 0;
        Src = 0;
        v31 = 0;
        v25 = 0;
        v26 = 0;
        v27 = 0;
        do
          ++v4;
        while ( v32[v4] );
        try
        {
          std::wstring::_Construct<1,unsigned short const *>(&v25, v32);
          WcmCommon::Registry::Path::Create<-2147483646>(&v29, &v25);
          std::wstring::_Append<unsigned short>(&Src);
          std::wstring::_Append<unsigned short>(&Src);
          v10 = (HKEY *)WcmCommon::Registry::TryOpenKeyRW(&hKey, &v29);
          v11 = v10;
          if ( &s_wcmLocalPolicyKey != v10 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &s_wcmLocalPolicyKey,
              *v10);
            *v11 = 0;
          }
          if ( hKey )
            RegCloseKey(hKey);
          WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)&v29);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0xBC,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
            v6);
        }
      }
      try
      {
        if ( !s_wcmGroupPolicyKey )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_SS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              17,
              (unsigned int)WPP_d1926522bc273c8e7056db3405527a30_Traceguids,
              (unsigned int)v32,
              (__int64)L"GroupPolicy");
          }
          v29 = 0;
          Src = 0;
          v31 = 0;
          v12 = std::wstring::wstring(&v25, v32);
          WcmCommon::Registry::Path::Create<-2147483646>(&v29, v12);
          WcmCommon::Registry::Path::AppendPath((WcmCommon::Registry::Path *)&v29, L"GroupPolicy");
          v13 = (HKEY *)WcmCommon::Registry::TryOpenKeyRO(&hKey, &v29);
          v14 = v13;
          if ( &s_wcmGroupPolicyKey != v13 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &s_wcmGroupPolicyKey,
              *v13);
            *v14 = 0;
          }
          if ( hKey )
            RegCloseKey(hKey);
          WcmCommon::Registry::Path::~Path((WcmCommon::Registry::Path *)&v29);
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
          v6);
      }
    }
  }
LABEL_7:
  LeaveCriticalSection(&s_keyLock);
}

```

## disassembly

```asm
0x18001b970  push    rbx
0x18001b972  push    rsi
0x18001b973  push    rdi
0x18001b974  push    r14
0x18001b976  sub     rsp, 2B8h
0x18001b97d  mov     rax, cs:__security_cookie
0x18001b984  xor     rax, rsp
0x18001b987  mov     [rsp+2D8h+var_38], rax
0x18001b98f  lea     rsi, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x18001b996  mov     rcx, rsi; lpCriticalSection
0x18001b999  call    cs:__imp_EnterCriticalSection
0x18001b99f  mov     [rsp+2D8h+var_280], rsi
0x18001b9a4  mov     rbx, cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmRootKey
0x18001b9ab  mov     rdi, cs:?s_wcmFailoverPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmFailoverPolicyKey
0x18001b9b2  test    rbx, rbx
0x18001b9b5  jz      short loc_18001B9C0
0x18001b9b7  test    rdi, rdi
0x18001b9ba  jnz     loc_18001BA54
0x18001b9c0  xor     edx, edx; Val
0x18001b9c2  mov     r8d, 208h; Size
0x18001b9c8  lea     rcx, [rsp+2D8h+var_248]; void *
0x18001b9d0  call    memset_0
0x18001b9d5  test    rbx, rbx
0x18001b9d8  jz      short loc_18001B9E3
0x18001b9da  test    rdi, rdi
0x18001b9dd  jnz     loc_18001BA7F
0x18001b9e3  mov     [rsp+2D8h+var_2B8], 0
0x18001b9ec  mov     r9d, 208h
0x18001b9f2  lea     r8, [rsp+2D8h+var_248]
0x18001b9fa  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WcmSvc"
0x18001ba01  lea     rcx, aWcmsvcroot; "WcmSvcRoot"
0x18001ba08  call    cs:__imp_GetPersistedRegistryLocationW
0x18001ba0e  test    eax, eax
0x18001ba10  jns     loc_18001BDBC
0x18001ba16  lea     rdi, WPP_GLOBAL_Control
0x18001ba1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba24  cmp     rcx, rdi
0x18001ba27  jnz     loc_18001BF49
0x18001ba2d  mov     rcx, rsi; lpCriticalSection
0x18001ba30  call    cs:__imp_LeaveCriticalSection
0x18001ba36  nop
0x18001ba37  mov     rcx, [rsp+2D8h+var_38]
0x18001ba3f  xor     rcx, rsp; StackCookie
0x18001ba42  call    __security_check_cookie
0x18001ba47  add     rsp, 2B8h
0x18001ba4e  pop     r14
0x18001ba50  pop     rdi
0x18001ba51  pop     rsi
0x18001ba52  pop     rbx
0x18001ba53  retn
0x18001ba54  cmp     cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootPolicyKey
0x18001ba5c  jz      loc_18001B9C0
0x18001ba62  cmp     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18001ba6a  jz      loc_18001B9C0
0x18001ba70  cmp     cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18001ba78  jnz     short loc_18001BA2D
0x18001ba7a  jmp     loc_18001B9C0
0x18001ba7f  lea     rdi, WPP_GLOBAL_Control
0x18001ba86  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ba8d  cmp     cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootPolicyKey
0x18001ba95  jz      short loc_18001BAA5
0x18001ba97  cmp     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18001ba9f  jnz     loc_18001BDA9
0x18001baa5  xor     edx, edx; Val
0x18001baa7  mov     r8d, 208h; Size
0x18001baad  lea     rcx, [rsp+2D8h+var_248]; void *
0x18001bab5  call    memset_0
0x18001baba  mov     [rsp+2D8h+var_2B8], 0
0x18001bac3  mov     r9d, 208h
0x18001bac9  lea     r8, [rsp+2D8h+var_248]
0x18001bad1  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18001bad8  lea     rcx, aWcmsvcpolicies; "WcmSvcPolicies"
0x18001badf  call    cs:__imp_GetPersistedRegistryLocationW
0x18001bae5  test    eax, eax
0x18001bae7  js      loc_18001C037
0x18001baed  cmp     cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootPolicyKey
0x18001baf5  jnz     loc_18001BBA3
0x18001bafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb02  cmp     rcx, rdi
0x18001bb05  jz      short loc_18001BB30
0x18001bb07  cmp     byte ptr [rcx+19h], 4
0x18001bb0b  jb      short loc_18001BB30
0x18001bb0d  test    byte ptr [rcx+1Ch], 1
0x18001bb11  jz      short loc_18001BB30
0x18001bb13  mov     edx, 0Fh
0x18001bb18  lea     r9, [rsp+2D8h+var_248]
0x18001bb20  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18001bb27  mov     rcx, [rcx+10h]
0x18001bb2b  call    WPP_SF_S
0x18001bb30  xorps   xmm0, xmm0
0x18001bb33  movups  [rsp+2D8h+var_278], xmm0
0x18001bb38  movups  [rsp+2D8h+Src], xmm0
0x18001bb3d  movups  [rsp+2D8h+var_258], xmm0
0x18001bb45  lea     rdx, [rsp+2D8h+var_248]
0x18001bb4d  lea     rcx, [rsp+2D8h+var_2A0]
0x18001bb52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bb57  mov     rdx, rax
0x18001bb5a  lea     rcx, [rsp+2D8h+var_278]
0x18001bb5f  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18001bb64  nop
0x18001bb65  lea     rdx, [rsp+2D8h+var_278]
0x18001bb6a  lea     rcx, [rsp+2D8h+hKey]
0x18001bb6f  call    ?TryOpenKeyRO@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::TryOpenKeyRO(WcmCommon::Registry::Path const &)
0x18001bb74  mov     r14, rax
0x18001bb77  lea     rcx, ?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmRootPolicyKey
0x18001bb7e  cmp     rcx, rax
0x18001bb81  jnz     loc_18001C087
0x18001bb87  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001bb8c  test    rcx, rcx
0x18001bb8f  jz      short loc_18001BB98
0x18001bb91  call    cs:__imp_RegCloseKey
0x18001bb97  nop
0x18001bb98  lea     rcx, [rsp+2D8h+var_278]; this
0x18001bb9d  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18001bba2  nop
0x18001bba3  cmp     cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18001bbab  jnz     loc_18001BCC9
0x18001bbb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbb8  cmp     rcx, rdi
0x18001bbbb  jz      loc_18001C0B5
0x18001bbc1  cmp     byte ptr [rcx+19h], 4
0x18001bbc5  jb      loc_18001C0B5
0x18001bbcb  test    byte ptr [rcx+1Ch], 1
0x18001bbcf  jz      loc_18001C0B5
0x18001bbd5  mov     edx, 10h
0x18001bbda  lea     r14, aLocal; "Local"
0x18001bbe1  mov     [rsp+2D8h+var_2B8], r14
0x18001bbe6  lea     r9, [rsp+2D8h+var_248]
0x18001bbee  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18001bbf5  mov     rcx, [rcx+10h]
0x18001bbf9  call    WPP_SF_SS
0x18001bbfe  xorps   xmm0, xmm0
0x18001bc01  movups  [rsp+2D8h+var_278], xmm0
0x18001bc06  movups  [rsp+2D8h+Src], xmm0
0x18001bc0b  movups  [rsp+2D8h+var_258], xmm0
0x18001bc13  movups  [rsp+2D8h+var_2A0], xmm0
0x18001bc18  mov     [rsp+2D8h+var_290], 0
0x18001bc21  mov     [rsp+2D8h+var_288], 0
0x18001bc2a  lea     rax, [rsp+2D8h+var_248]
0x18001bc32  inc     rbx
0x18001bc35  cmp     word ptr [rax+rbx*2], 0
0x18001bc3a  jnz     short loc_18001BC32
0x18001bc3c  mov     r8, rbx
0x18001bc3f  lea     rdx, [rsp+2D8h+var_248]
0x18001bc47  lea     rcx, [rsp+2D8h+var_2A0]
0x18001bc4c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bc51  lea     rdx, [rsp+2D8h+var_2A0]
0x18001bc56  lea     rcx, [rsp+2D8h+var_278]
0x18001bc5b  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18001bc60  nop
0x18001bc61  mov     r8d, 1
0x18001bc67  lea     rdx, asc_180102808; "\\"
0x18001bc6e  lea     rcx, [rsp+2D8h+Src]; Src
0x18001bc73  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001bc78  mov     r8d, 5
0x18001bc7e  mov     rdx, r14
0x18001bc81  lea     rcx, [rsp+2D8h+Src]; Src
0x18001bc86  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001bc8b  lea     rdx, [rsp+2D8h+var_278]
0x18001bc90  lea     rcx, [rsp+2D8h+hKey]
0x18001bc95  call    ?TryOpenKeyRW@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::TryOpenKeyRW(WcmCommon::Registry::Path const &)
0x18001bc9a  mov     rbx, rax
0x18001bc9d  lea     rcx, ?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18001bca4  cmp     rcx, rax
0x18001bca7  jnz     loc_18001C0C1
0x18001bcad  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001bcb2  test    rcx, rcx
0x18001bcb5  jz      short loc_18001BCBE
0x18001bcb7  call    cs:__imp_RegCloseKey
0x18001bcbd  nop
0x18001bcbe  lea     rcx, [rsp+2D8h+var_278]; this
0x18001bcc3  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18001bcc8  nop
0x18001bcc9  cmp     cs:?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18001bcd1  jnz     loc_18001BA2D
0x18001bcd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcde  cmp     rcx, rdi
0x18001bce1  jz      loc_18001C0E8
0x18001bce7  cmp     byte ptr [rcx+19h], 4
0x18001bceb  jb      loc_18001C0E8
0x18001bcf1  test    byte ptr [rcx+1Ch], 1
0x18001bcf5  jz      loc_18001C0E8
0x18001bcfb  mov     edx, 11h
0x18001bd00  lea     rbx, aGrouppolicy_0; "GroupPolicy"
0x18001bd07  mov     [rsp+2D8h+var_2B8], rbx
0x18001bd0c  lea     r9, [rsp+2D8h+var_248]
0x18001bd14  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18001bd1b  mov     rcx, [rcx+10h]
0x18001bd1f  call    WPP_SF_SS
0x18001bd24  xorps   xmm0, xmm0
0x18001bd27  movups  [rsp+2D8h+var_278], xmm0
0x18001bd2c  movups  [rsp+2D8h+Src], xmm0
0x18001bd31  movups  [rsp+2D8h+var_258], xmm0
0x18001bd39  lea     rdx, [rsp+2D8h+var_248]
0x18001bd41  lea     rcx, [rsp+2D8h+var_2A0]
0x18001bd46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bd4b  mov     rdx, rax
0x18001bd4e  lea     rcx, [rsp+2D8h+var_278]
0x18001bd53  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18001bd58  nop
0x18001bd59  mov     rdx, rbx; unsigned __int16 *
0x18001bd5c  lea     rcx, [rsp+2D8h+var_278]; this
0x18001bd61  call    ?AppendPath@Path@Registry@WcmCommon@@QEAAAEAV123@PEBG@Z; WcmCommon::Registry::Path::AppendPath(ushort const *)
0x18001bd66  lea     rdx, [rsp+2D8h+var_278]
0x18001bd6b  lea     rcx, [rsp+2D8h+hKey]
0x18001bd70  call    ?TryOpenKeyRO@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::TryOpenKeyRO(WcmCommon::Registry::Path const &)
0x18001bd75  mov     rbx, rax
0x18001bd78  lea     rcx, ?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x18001bd7f  cmp     rcx, rax
0x18001bd82  jnz     loc_18001C0F4
0x18001bd88  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001bd8d  test    rcx, rcx
0x18001bd90  jz      short loc_18001BD99
0x18001bd92  call    cs:__imp_RegCloseKey
0x18001bd98  nop
0x18001bd99  lea     rcx, [rsp+2D8h+var_278]; this
0x18001bd9e  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18001bda3  nop
0x18001bda4  jmp     loc_18001BA2D
0x18001bda9  cmp     cs:?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x18001bdb1  jnz     loc_18001BA2D
0x18001bdb7  jmp     loc_18001BAA5
0x18001bdbc  cmp     cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootKey
0x18001bdc4  jz      loc_18001BF6F
0x18001bdca  lea     rdi, WPP_GLOBAL_Control
0x18001bdd1  cmp     cs:?s_wcmFailoverPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmFailoverPolicyKey
0x18001bdd9  jnz     loc_18001BA86
0x18001bddf  xorps   xmm0, xmm0
0x18001bde2  movups  [rsp+2D8h+var_278], xmm0
0x18001bde7  movups  [rsp+2D8h+Src], xmm0
0x18001bdec  movups  [rsp+2D8h+var_258], xmm0
0x18001bdf4  movups  [rsp+2D8h+var_2A0], xmm0
0x18001bdf9  mov     [rsp+2D8h+var_290], 0
0x18001be02  mov     [rsp+2D8h+var_288], 0
0x18001be0b  lea     rax, [rsp+2D8h+var_248]
0x18001be13  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001be1a  mov     r8, rbx
0x18001be1d  nop     dword ptr [rax]
0x18001be20  inc     r8
0x18001be23  cmp     word ptr [rax+r8*2], 0
0x18001be29  jnz     short loc_18001BE20
0x18001be2b  lea     rdx, [rsp+2D8h+var_248]
0x18001be33  lea     rcx, [rsp+2D8h+var_2A0]
0x18001be38  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001be3d  lea     rdx, [rsp+2D8h+var_2A0]
0x18001be42  lea     rcx, [rsp+2D8h+var_278]
0x18001be47  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18001be4c  nop
0x18001be4d  mov     r8d, 1
0x18001be53  lea     rdx, asc_180102808; "\\"
0x18001be5a  lea     rcx, [rsp+2D8h+Src]; Src
0x18001be5f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001be64  mov     r8d, 10h
0x18001be6a  lea     r14, aCellularfailov; "CellularFailover"
0x18001be71  mov     rdx, r14
0x18001be74  lea     rcx, [rsp+2D8h+Src]; Src
0x18001be79  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001be7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be85  cmp     rcx, rdi
0x18001be88  jnz     loc_18001BFDC
0x18001be8e  lea     rdx, [rsp+2D8h+var_278]
0x18001be93  lea     rcx, [rsp+2D8h+hKey]
0x18001be98  call    ?TryOpenKeyRW@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::TryOpenKeyRW(WcmCommon::Registry::Path const &)
0x18001be9d  mov     r14, rax
0x18001bea0  lea     rcx, ?s_wcmFailoverPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmFailoverPolicyKey
0x18001bea7  cmp     rcx, rax
0x18001beaa  jnz     loc_18001C017
0x18001beb0  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001beb5  test    rcx, rcx
0x18001beb8  jz      short loc_18001BEC1
0x18001beba  call    cs:__imp_RegCloseKey
0x18001bec0  nop
0x18001bec1  lea     rcx, [rsp+2D8h+var_278]; this
0x18001bec6  call    ??1Path@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Path::~Path(void)
0x18001becb  nop
0x18001becc  jmp     loc_18001BA8D
0x18001bed1  xorps   xmm0, xmm0
0x18001bed4  movups  [rsp+2D8h+var_278], xmm0
0x18001bed9  movups  [rsp+2D8h+Src], xmm0
0x18001bede  movups  [rsp+2D8h+var_258], xmm0
0x18001bee6  lea     rdx, [rsp+2D8h+var_248]
0x18001beee  lea     rcx, [rsp+2D8h+var_2A0]
0x18001bef3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001bef8  mov     rdx, rax
0x18001befb  lea     rcx, [rsp+2D8h+var_278]
0x18001bf00  call    ??$Create@$0?HPPPPPPO@@Path@Registry@WcmCommon@@SA?AV012@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WcmCommon::Registry::Path::Create<-2147483646>(std::wstring)
0x18001bf05  nop
0x18001bf06  lea     rdx, [rsp+2D8h+var_278]
0x18001bf0b  lea     rcx, [rsp+2D8h+hKey]
0x18001bf10  call    ?TryOpenKeyRW@Registry@WcmCommon@@YA?AVKey@12@AEBVPath@12@@Z; WcmCommon::Registry::TryOpenKeyRW(WcmCommon::Registry::Path const &)
0x18001bf15  mov     rbx, rax
0x18001bf18  lea     rcx, ?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmRootKey
0x18001bf1f  cmp     rcx, rax
0x18001bf22  jnz     loc_18001BFBC
0x18001bf28  mov     rcx, [rsp+2D8h+hKey]; hKey
0x18001bf2d  test    rcx, rcx
0x18001bf30  jz      short loc_18001BF39
0x18001bf32  call    cs:__imp_RegCloseKey
0x18001bf38  nop
0x18001bf39  lea     rcx, [rsp+2D8h+var_278]; this
  ... truncated ...
```
