# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithCallerIdentity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong)

- ea: `0x18006c6f4`
- end: `0x18006c91a`
- name: `?CreateWithCallerIdentity@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@KK@Z`
- size: `550`
- prototype: `__int64 __fastcall(int, int, DWORD dwProcessId, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180091ff4`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x18002f93c`
- `0x180039e9c`
- `0x18003f4a0`
- `0x180040d7c`
- `0x180042c4c`
- `0x180043610`
- `0x1800483d4`
- `0x1800581a8`
- `0x18006ae88`
- `0x18006c6f4`
- `0x1800b0208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c780`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c780`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c7f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c7f1`

## string_xrefs

- `0x18006c8de`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c8f6`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c908`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006c816`: `CreateWithCallerIdentity`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void *__fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithCallerIdentity(
        void *a1,
        __int64 a2,
        DWORD dwProcessId,
        int a4)
{
  DWORD CurrentProcessId; // eax
  PHANDLE ProcessTokenFromProcessId; // rax
  __int64 UserSidStringFromToken; // rax
  const char *v11; // r9
  int ReturnLength; // [rsp+20h] [rbp-A9h]
  int ReturnLengtha; // [rsp+20h] [rbp-A9h]
  HANDLE TokenHandle; // [rsp+50h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+58h] [rbp-71h] BYREF
  DWORD v17; // [rsp+5Ch] [rbp-6Dh] BYREF
  void *phNewToken[2]; // [rsp+60h] [rbp-69h] BYREF
  int v19[4]; // [rsp+70h] [rbp-59h] BYREF
  __m128i si128; // [rsp+80h] [rbp-49h]
  int v21[4]; // [rsp+90h] [rbp-39h] BYREF
  __m128i v22; // [rsp+A0h] [rbp-29h]
  __int64 v23[2]; // [rsp+B0h] [rbp-19h] BYREF
  __m128i v24; // [rsp+C0h] [rbp-9h]
  __int64 v25[4]; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  phNewToken[0] = a1;
  if ( !*(_QWORD *)(a2 + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)0x80070057LL,
      ReturnLength);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl)
    && !dwProcessId )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *(_OWORD *)v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(&TokenHandle);
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    ProcessTokenFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(
                                  phNewToken,
                                  CurrentProcessId);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &TokenHandle,
      ProcessTokenFromProcessId);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(phNewToken);
  }
  UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v25, &TokenHandle);
  std::wstring::operator=(v19, UserSidStringFromToken);
  std::wstring::_Tidy_deallocate(v25);
  v17 = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &v17) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      v11);
  if ( !TokenInformation )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)0x80070005LL,
      ReturnLengtha);
  std::wstring::wstring(v25, L"CreateWithCallerIdentity");
  *(_OWORD *)v23 = 0;
  v24 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23[0]) = 0;
  *(_OWORD *)v21 = 0;
  v22 = v24;
  LOWORD(v21[0]) = 0;
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::Create(
    (__int64 **)a1,
    (__int64)v19,
    a2,
    (__int64)v21,
    dwProcessId,
    a4,
    (__int64)v23,
    &TokenHandle,
    (__int64)v25,
    0);
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v25);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  std::wstring::_Tidy_deallocate(v19);
  return a1;
}

```

## disassembly

```asm
0x18006c6f4  push    rbp
0x18006c6f6  push    rbx
0x18006c6f7  push    rsi
0x18006c6f8  push    rdi
0x18006c6f9  push    r14
0x18006c6fb  lea     rbp, [rsp-37h]
0x18006c700  sub     rsp, 100h
0x18006c707  mov     rax, cs:__security_cookie
0x18006c70e  xor     rax, rsp
0x18006c711  mov     [rbp+57h+var_30], rax
0x18006c715  mov     r14d, r9d
0x18006c718  mov     edi, r8d
0x18006c71b  mov     rsi, rdx
0x18006c71e  mov     rbx, rcx
0x18006c721  mov     [rbp+57h+phNewToken], rcx
0x18006c725  mov     rcx, [rbp+5Fh]; this
0x18006c729  cmp     qword ptr [rdx+10h], 0
0x18006c72e  jz      loc_18006C8F0
0x18006c734  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x18006c73b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x18006c740  test    al, al
0x18006c742  jz      short loc_18006C74D
0x18006c744  test    edi, edi
0x18006c746  jnz     short loc_18006C74D
0x18006c748  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006c74d  xorps   xmm0, xmm0
0x18006c750  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18006c754  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006c75c  movdqu  [rbp+57h+var_A0], xmm1
0x18006c761  xor     eax, eax
0x18006c763  mov     word ptr [rbp+57h+var_B0], ax
0x18006c767  lea     rcx, [rbp+57h+TokenHandle]
0x18006c76b  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x18006c770  nop
0x18006c771  mov     rax, [rbp+57h+TokenHandle]
0x18006c775  inc     rax
0x18006c778  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006c77e  jnz     short loc_18006C7A6
0x18006c780  call    cs:__imp_GetCurrentProcessId
0x18006c786  mov     edx, eax; dwProcessId
0x18006c788  lea     rcx, [rbp+57h+phNewToken]; phNewToken
0x18006c78c  call    ?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)
0x18006c791  mov     rdx, rax
0x18006c794  lea     rcx, [rbp+57h+TokenHandle]
0x18006c798  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18006c79d  lea     rcx, [rbp+57h+phNewToken]
0x18006c7a1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c7a6  lea     rdx, [rbp+57h+TokenHandle]
0x18006c7aa  lea     rcx, [rbp+57h+var_50]
0x18006c7ae  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006c7b3  mov     rdx, rax
0x18006c7b6  lea     rcx, [rbp+57h+var_B0]
0x18006c7ba  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006c7bf  lea     rcx, [rbp+57h+var_50]
0x18006c7c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c7c8  mov     [rbp+57h+var_C4], 0
0x18006c7cf  mov     [rbp+57h+TokenInformation], 0
0x18006c7d6  lea     rax, [rbp+57h+var_C4]
0x18006c7da  mov     [rsp+120h+ReturnLength], rax; int
0x18006c7df  mov     r9d, 4; TokenInformationLength
0x18006c7e5  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18006c7e9  lea     edx, [r9+5]; TokenInformationClass
0x18006c7ed  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006c7f1  call    cs:__imp_GetTokenInformation
0x18006c7f7  mov     rcx, [rbp+5Fh]; this
0x18006c7fb  test    eax, eax
0x18006c7fd  jz      loc_18006C908
0x18006c803  cmp     [rbp+57h+TokenInformation], 0
0x18006c807  setz    al
0x18006c80a  mov     rcx, [rbp+5Fh]; this
0x18006c80e  test    al, al
0x18006c810  jnz     loc_18006C8D8
0x18006c816  lea     rdx, aCreatewithcall; "CreateWithCallerIdentity"
0x18006c81d  lea     rcx, [rbp+57h+var_50]
0x18006c821  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006c826  nop
0x18006c827  xorps   xmm0, xmm0
0x18006c82a  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18006c82e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006c836  movdqu  [rbp+57h+var_60], xmm1
0x18006c83b  xor     eax, eax
0x18006c83d  mov     word ptr [rbp+57h+var_70], ax
0x18006c841  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18006c845  movdqu  [rbp+57h+var_80], xmm1
0x18006c84a  mov     word ptr [rbp+57h+var_90], ax
0x18006c84e  mov     [rsp+120h+var_D8], al; char
0x18006c852  lea     rax, [rbp+57h+var_50]
0x18006c856  mov     [rsp+120h+var_E0], rax; __int64
0x18006c85b  lea     rax, [rbp+57h+TokenHandle]
0x18006c85f  mov     [rsp+120h+var_E8], rax; __int64
0x18006c864  lea     rax, [rbp+57h+var_70]
0x18006c868  mov     [rsp+120h+var_F0], rax; __int64
0x18006c86d  mov     [rsp+120h+var_F8], r14d; int
0x18006c872  mov     dword ptr [rsp+120h+ReturnLength], edi; dwProcessId
0x18006c876  lea     r9, [rbp+57h+var_90]; int
0x18006c87a  mov     r8, rsi; int
0x18006c87d  lea     rdx, [rbp+57h+var_B0]; int
0x18006c881  mov     rcx, rbx; int
0x18006c884  call    ?Create@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@CA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@00KK0$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@0_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::Create(std::wstring const &,std::wstring const &,std::wstring const &,ulong,ulong,std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,std::wstring const &,bool)
0x18006c889  nop
0x18006c88a  lea     rcx, [rbp+57h+var_90]
0x18006c88e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c893  nop
0x18006c894  lea     rcx, [rbp+57h+var_70]
0x18006c898  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c89d  nop
0x18006c89e  lea     rcx, [rbp+57h+var_50]
0x18006c8a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c8a7  nop
0x18006c8a8  lea     rcx, [rbp+57h+TokenHandle]
0x18006c8ac  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c8b1  nop
0x18006c8b2  lea     rcx, [rbp+57h+var_B0]
0x18006c8b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006c8bb  mov     rax, rbx
0x18006c8be  mov     rcx, [rbp+57h+var_30]
0x18006c8c2  xor     rcx, rsp; StackCookie
0x18006c8c5  call    __security_check_cookie
0x18006c8ca  add     rsp, 100h
0x18006c8d1  pop     r14
0x18006c8d3  pop     rdi
0x18006c8d4  pop     rsi
0x18006c8d5  pop     rbx
0x18006c8d6  pop     rbp
0x18006c8d7  retn
0x18006c8d8  mov     r9d, 80070005h; char *
0x18006c8de  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c8e5  mov     edx, 0C1h; void *
0x18006c8ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c8f0  mov     r9d, 80070057h; char *
0x18006c8f6  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c8fd  mov     edx, 0A2h; void *
0x18006c902  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c908  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006c90f  mov     edx, 0BFh; void *
0x18006c914  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
