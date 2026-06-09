# CapabilityUsageServer::GetProcessDisplayInformationForAppsUsingCapability(uint *,Windows::Internal::CapabilityAccess::Management::ProcessDisplayInformation * *)

- ea: `0x18008ec80`
- end: `0x18008ef58`
- name: `?GetProcessDisplayInformationForAppsUsingCapability@CapabilityUsageServer@@UEAAJPEAIPEAPEAUProcessDisplayInformation@Management@CapabilityAccess@Internal@Windows@@@Z`
- size: `728`
- prototype: `__int64 __fastcall(CapabilityUsageServer *__hidden this, unsigned int *, struct Windows::Internal::CapabilityAccess::Management::ProcessDisplayInformation **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001c3b4`
- `0x18001e118`
- `0x18001e42c`
- `0x18002392c`
- `0x180029408`
- `0x18002f240`
- `0x18003b54c`
- `0x180043bc8`
- `0x180043ebc`
- `0x180046b28`
- `0x18006065c`
- `0x18008eb64`
- `0x18008ec80`
- `0x180090bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008ee17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008ee17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008ee63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18008ee63`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CapabilityUsageServer::GetProcessDisplayInformationForAppsUsingCapability(
        CapabilityUsageServer *this,
        unsigned int *a2,
        struct Windows::Internal::CapabilityAccess::Management::ProcessDisplayInformation **a3)
{
  Windows::Internal::CapabilityAccess::Private *v5; // rcx
  bool IsEnterpriseMultiSessionEnvironment; // al
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  Windows::Internal::CapabilityAccess::Private *v10; // rcx
  __int64 v11; // rax
  _BYTE *v12; // rcx
  __int64 Capability; // rax
  char v14; // bl
  __int64 v15; // rax
  __int64 v16; // rcx
  HSTRING *v17; // r14
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // r15
  const WCHAR *v21; // rax
  HRESULT String; // eax
  const char *v23; // r9
  __int64 result; // rax
  const struct wil::FailureInfo *Failure; // rax
  const char *v26; // rbx
  unsigned int v27; // edi
  int v28; // r14d
  const unsigned __int16 *v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  const unsigned __int16 *v33; // rax
  int v34; // [rsp+20h] [rbp-1A8h]
  HSTRING *v35; // [rsp+30h] [rbp-198h] BYREF
  __int64 v36; // [rsp+38h] [rbp-190h] BYREF
  __int64 v37; // [rsp+40h] [rbp-188h]
  __int64 v38; // [rsp+48h] [rbp-180h]
  struct Windows::Internal::CapabilityAccess::Management::ProcessDisplayInformation **v39; // [rsp+50h] [rbp-178h]
  CapabilityUsageServer *v40; // [rsp+58h] [rbp-170h]
  _BYTE v41[224]; // [rsp+60h] [rbp-168h] BYREF
  _BYTE v42[32]; // [rsp+140h] [rbp-88h] BYREF
  _BYTE v43[32]; // [rsp+160h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  try
  {
    v39 = a3;
    v40 = this;
    LODWORD(v35) = 0;
    *a2 = 0;
    *a3 = 0;
    if ( !*((_BYTE *)this + 32) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x281,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
        (const char *)0x80070005LL,
        v34);
    CapabilityUsageServer::EnsureCallerIsShellExperience(this);
    wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v41);
    IsEnterpriseMultiSessionEnvironment = Windows::Internal::CapabilityAccess::Private::IsEnterpriseMultiSessionEnvironment(v5);
    try
    {
      v7 = *((_QWORD *)this + 5);
      if ( IsEnterpriseMultiSessionEnvironment )
      {
        Capability = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(v7, v43);
        v14 = 1;
        LODWORD(v35) = 1;
        if ( (unsigned int)std::wstring::compare(Capability, L"location") )
        {
          v15 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                  *((_QWORD *)this + 5),
                  v42);
          v14 = 3;
          std::wstring::compare(v15, L"microphone");
        }
        if ( (v14 & 2) != 0 )
        {
          v14 &= ~2u;
          std::wstring::_Tidy_deallocate(v42);
        }
        if ( (v14 & 1) == 0 )
          goto LABEL_14;
        v12 = v43;
      }
      else
      {
        v8 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(v7, v42);
        v9 = std::wstring::compare(v8, L"location");
        std::wstring::_Tidy_deallocate(v42);
        if ( !v9 )
        {
LABEL_14:
          Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(v10);
          Windows::Internal::CapabilityAccess::Private::CapabilitySessionManager::GetInUseProcessIDsAndDisplayNamesForCapabilityAndUser(
            &v36,
            *((_QWORD *)this + 5) + 40LL,
            (char *)this + 56,
            0);
          v16 = v36;
          if ( v36 != v37 )
          {
            v17 = (HSTRING *)CoTaskMemAlloc(0xCCCCCCCCCCCCCCD0uLL * ((v37 - v36) >> 3));
            v35 = v17;
            if ( !v17 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2B9,
                (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
                (const char *)0x8007000ELL,
                v34);
            v18 = 0;
            v19 = v36;
            v20 = v37;
            while ( v19 != v20 )
            {
              v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
              String = WindowsCreateString(v21, *(_DWORD *)(v19 + 16), &v17[2 * v18]);
              if ( String < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x2C2,
                  (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
                  (const char *)(unsigned int)String,
                  v34);
              LODWORD(v17[2 * v18++ + 1]) = *(_DWORD *)(v19 + 32);
              v19 += 40;
            }
            v35 = 0;
            *v39 = (struct Windows::Internal::CapabilityAccess::Management::ProcessDisplayInformation *)v17;
            *a2 = v18;
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
            v16 = v36;
          }
          if ( v16 )
          {
            std::_Destroy_range<std::allocator<std::tuple<enum Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring>>>();
            std::_Deallocate<16>(v36, 8 * ((v38 - v36) >> 3));
          }
          wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v41);
          return 0;
        }
        v11 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(
                *((_QWORD *)this + 5),
                v42);
        std::wstring::compare(v11, L"microphone");
        v12 = v42;
      }
      std::wstring::_Tidy_deallocate(v12);
      goto LABEL_14;
    }
    catch ( wil::ResultException )
    {
      if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::GetIsTestCode() )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        Failure = wil::ThreadFailureCache::GetFailure((wil::ThreadFailureCache *)v41);
        if ( Failure )
          v26 = (const char *)*((_QWORD *)Failure + 7);
        else
          v26 = qword_1800D35C0;
        if ( Failure )
          v27 = *((_DWORD *)Failure + 16);
        else
          v27 = 0;
        if ( Failure )
          v28 = *((_DWORD *)Failure + 2);
        else
          v28 = 0;
        if ( Failure )
          v29 = (const unsigned __int16 *)*((_QWORD *)Failure + 3);
        else
          v29 = (const unsigned __int16 *)&Format;
        v30 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::operator-><Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager,0>((char *)v40 + 40);
        v31 = Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(v30, v43);
        v33 = (const unsigned __int16 *)std::wstring::c_str(v31, v32);
        LogCriticalUxDependencyFailure(
          v33,
          "CapabilityUsageServer::GetProcessDisplayInformationForAppsUsingCapability",
          v26,
          v27,
          v29,
          v28);
        std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v43);
      }
      throw;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2EA,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\capabilityusageserver.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x18008ec80  push    rbx
0x18008ec82  push    rsi
0x18008ec83  push    rdi
0x18008ec84  push    r12
0x18008ec86  push    r13
0x18008ec88  push    r14
0x18008ec8a  push    r15
0x18008ec8c  sub     rsp, 190h
0x18008ec93  mov     rax, cs:__security_cookie
0x18008ec9a  xor     rax, rsp
0x18008ec9d  mov     [rsp+1C8h+var_48], rax
0x18008eca5  mov     [rsp+1C8h+var_178], r8
0x18008ecaa  mov     r12, rdx
0x18008ecad  mov     rdi, rcx
0x18008ecb0  mov     [rsp+1C8h+var_170], rcx
0x18008ecb5  xor     r15d, r15d
0x18008ecb8  mov     dword ptr [rsp+1C8h+var_198], r15d
0x18008ecbd  mov     [rdx], r15d
0x18008ecc0  mov     [r8], r15
0x18008ecc3  mov     rcx, [rsp+1C8h]; this
0x18008eccb  cmp     [rdi+20h], r15b
0x18008eccf  jz      loc_18008EF13
0x18008ecd5  mov     rcx, rdi; this
0x18008ecd8  call    ?EnsureCallerIsShellExperience@CapabilityUsageServer@@AEBAXXZ; CapabilityUsageServer::EnsureCallerIsShellExperience(void)
0x18008ecdd  lea     rcx, [rsp+1C8h+var_168]; this
0x18008ece2  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x18008ece7  nop
0x18008ece8  call    ?IsEnterpriseMultiSessionEnvironment@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsEnterpriseMultiSessionEnvironment(void)
0x18008eced  mov     rcx, [rdi+28h]
0x18008ecf1  test    al, al
0x18008ecf3  jnz     short loc_18008ED52
0x18008ecf5  lea     rdx, [rsp+1C8h+var_88]
0x18008ecfd  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x18008ed02  lea     rdx, aLocation; "location"
0x18008ed09  mov     rcx, rax
0x18008ed0c  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18008ed11  mov     ebx, eax
0x18008ed13  lea     rcx, [rsp+1C8h+var_88]
0x18008ed1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008ed20  test    ebx, ebx
0x18008ed22  jz      loc_18008EDC9
0x18008ed28  lea     rdx, [rsp+1C8h+var_88]
0x18008ed30  mov     rcx, [rdi+28h]
0x18008ed34  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x18008ed39  lea     rdx, aMicrophone; "microphone"
0x18008ed40  mov     rcx, rax
0x18008ed43  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18008ed48  lea     rcx, [rsp+1C8h+var_88]
0x18008ed50  jmp     short loc_18008EDC4
0x18008ed52  lea     rdx, [rsp+1C8h+var_68]
0x18008ed5a  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x18008ed5f  nop
0x18008ed60  mov     ebx, 1
0x18008ed65  mov     dword ptr [rsp+1C8h+var_198], ebx
0x18008ed69  lea     rdx, aLocation; "location"
0x18008ed70  mov     rcx, rax
0x18008ed73  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18008ed78  test    eax, eax
0x18008ed7a  jz      short loc_18008EDA1
0x18008ed7c  lea     rdx, [rsp+1C8h+var_88]
0x18008ed84  mov     rcx, [rdi+28h]
0x18008ed88  call    ?get_Capability@CapabilityUsageManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityUsageManager::get_Capability(void)
0x18008ed8d  mov     ebx, 3
0x18008ed92  lea     rdx, aMicrophone; "microphone"
0x18008ed99  mov     rcx, rax
0x18008ed9c  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18008eda1  test    bl, 2
0x18008eda4  jz      short loc_18008EDB7
0x18008eda6  and     ebx, 0FFFFFFFDh
0x18008eda9  lea     rcx, [rsp+1C8h+var_88]
0x18008edb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008edb6  nop
0x18008edb7  test    bl, 1
0x18008edba  jz      short loc_18008EDC9
0x18008edbc  lea     rcx, [rsp+1C8h+var_68]
0x18008edc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008edc9  call    ?IsCTARegionActive@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(void)
0x18008edce  lea     r8, [rdi+38h]
0x18008edd2  mov     rdx, [rdi+28h]
0x18008edd6  add     rdx, 28h ; '('
0x18008edda  xor     r9d, r9d
0x18008eddd  lea     rcx, [rsp+1C8h+var_190]
0x18008ede2  call    ?GetInUseProcessIDsAndDisplayNamesForCapabilityAndUser@CapabilitySessionManager@Private@CapabilityAccess@Internal@Windows@@KA?AV?$vector@V?$tuple@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@V?$tuple@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0I@Z; Windows::Internal::CapabilityAccess::Private::CapabilitySessionManager::GetInUseProcessIDsAndDisplayNamesForCapabilityAndUser(std::wstring const &,std::wstring const &,uint)
0x18008ede7  nop
0x18008ede8  mov     rdx, [rsp+1C8h+var_188]
0x18008eded  mov     rcx, [rsp+1C8h+var_190]
0x18008edf2  mov     rsi, 0CCCCCCCCCCCCCCCDh
0x18008edfc  cmp     rcx, rdx
0x18008edff  jz      loc_18008EEB1
0x18008ee05  sub     rdx, rcx
0x18008ee08  sar     rdx, 3
0x18008ee0c  imul    rdx, rsi
0x18008ee10  shl     rdx, 4
0x18008ee14  mov     rcx, rdx; cb
0x18008ee17  call    cs:__imp_CoTaskMemAlloc
0x18008ee1d  mov     r14, rax
0x18008ee20  mov     [rsp+1C8h+var_198], rax
0x18008ee25  mov     rcx, [rsp+1C8h]; this
0x18008ee2d  test    rax, rax
0x18008ee30  jz      loc_18008EF2B
0x18008ee36  mov     rdi, r15
0x18008ee39  mov     rbx, [rsp+1C8h+var_190]
0x18008ee3e  mov     r15, [rsp+1C8h+var_188]
0x18008ee43  cmp     rbx, r15
0x18008ee46  jz      short loc_18008EE89
0x18008ee48  mov     rcx, rbx
0x18008ee4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008ee50  mov     r13, rdi
0x18008ee53  shl     r13, 4
0x18008ee57  add     r13, r14
0x18008ee5a  mov     r8, r13; string
0x18008ee5d  mov     edx, [rbx+10h]; length
0x18008ee60  mov     rcx, rax; sourceString
0x18008ee63  call    cs:__imp_WindowsCreateString
0x18008ee69  mov     rcx, [rsp+1C8h]; this
0x18008ee71  test    eax, eax
0x18008ee73  js      loc_18008EF42
0x18008ee79  mov     eax, [rbx+20h]
0x18008ee7c  mov     [r13+8], eax
0x18008ee80  inc     rdi
0x18008ee83  add     rbx, 28h ; '('
0x18008ee87  jmp     short loc_18008EE43
0x18008ee89  xor     r15d, r15d
0x18008ee8c  mov     [rsp+1C8h+var_198], r15
0x18008ee91  mov     rax, [rsp+1C8h+var_178]
0x18008ee96  mov     [rax], r14
0x18008ee99  mov     [r12], edi
0x18008ee9d  lea     rcx, [rsp+1C8h+var_198]
0x18008eea2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008eea7  mov     rdx, [rsp+1C8h+var_188]
0x18008eeac  mov     rcx, [rsp+1C8h+var_190]
0x18008eeb1  test    rcx, rcx
0x18008eeb4  jz      short loc_18008EEDE
0x18008eeb6  call    ??$_Destroy_range@V?$allocator@V?$tuple@W4AppIdType@Private@CapabilityAccess@Internal@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@YAXPEAV?$tuple@W4AppIdType@Private@CapabilityAccess@Internal@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@QEAV10@AEAV?$allocator@V?$tuple@W4AppIdType@Private@CapabilityAccess@Internal@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring>>>(std::tuple<Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring> *,std::tuple<Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring> * const,std::allocator<std::tuple<Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring>> &)
0x18008eebb  mov     rcx, [rsp+1C8h+var_190]
0x18008eec0  mov     rax, [rsp+1C8h+var_180]
0x18008eec5  sub     rax, rcx
0x18008eec8  sar     rax, 3
0x18008eecc  imul    rax, rsi
0x18008eed0  lea     rdx, [rax+rax*4]
0x18008eed4  shl     rdx, 3
0x18008eed8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008eedd  nop
0x18008eede  lea     rcx, [rsp+1C8h+var_168]; this
0x18008eee3  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x18008eee8  xor     eax, eax
0x18008eeea  jmp     short loc_18008EEF0
0x18008eeec  mov     eax, dword ptr [rsp+1C8h+var_198]
0x18008eef0  mov     rcx, [rsp+1C8h+var_48]
0x18008eef8  xor     rcx, rsp; StackCookie
0x18008eefb  call    __security_check_cookie
0x18008ef00  add     rsp, 190h
0x18008ef07  pop     r15
0x18008ef09  pop     r14
0x18008ef0b  pop     r13
0x18008ef0d  pop     r12
0x18008ef0f  pop     rdi
0x18008ef10  pop     rsi
0x18008ef11  pop     rbx
0x18008ef12  retn
0x18008ef13  mov     r9d, 80070005h; char *
0x18008ef19  lea     r8, aOnecoreBaseDev_57; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18008ef20  mov     edx, 281h; void *
0x18008ef25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008ef2b  mov     r9d, 8007000Eh; char *
0x18008ef31  lea     r8, aOnecoreBaseDev_57; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18008ef38  mov     edx, 2B9h; void *
0x18008ef3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008ef42  mov     r9d, eax; char *
0x18008ef45  lea     r8, aOnecoreBaseDev_57; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18008ef4c  mov     edx, 2C2h; void *
0x18008ef51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
