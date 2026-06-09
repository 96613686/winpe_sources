# Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::AdjustedAppDisplayInfo(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> const &)

- ea: `0x180064304`
- end: `0x180064a1b`
- name: `??0AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAA@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@6@@Z`
- size: `1815`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005fa5c`
- `0x180065a84`
- `0x1800901e0`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x18002e304`
- `0x18002f93c`
- `0x18002f978`
- `0x1800365c8`
- `0x180039e9c`
- `0x18003afa0`
- `0x18003b518`
- `0x18003f4a0`
- `0x180040454`
- `0x180040598`
- `0x1800416a0`
- `0x180041e2c`
- `0x1800422d0`
- `0x180042c4c`
- `0x180043538`
- `0x180043610`
- `0x1800439d4`
- `0x180043a40`
- `0x180044614`
- `0x1800464d0`
- `0x180046610`
- `0x1800483d4`
- `0x1800581a8`
- `0x180062198`
- `0x180064304`
- `0x180064fa8`
- `0x180065084`
- `0x1800b14c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800646f5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006485a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006485a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800648bd`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800648bd`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetParentSessionId` at `0x180064887`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetParentSessionId` at `0x180064887`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::AdjustedAppDisplayInfo(
        __int64 a1,
        DWORD a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rdi
  __int64 v8; // r15
  __int64 v9; // rbx
  void **v10; // r13
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r8
  __int64 UserSidStringFromProcessId; // rax
  PHANDLE ProcessTokenFromProcessId; // rax
  unsigned int v16; // edx
  __int64 DsmaSidString; // rax
  int v18; // ebx
  __int64 v19; // rax
  __int64 ActiveSessionUserSidString; // rax
  __int64 PackageFamilyNameFromProcessId; // rax
  __int64 v22; // rax
  __int64 v23; // r10
  __int64 ImageFullPathFromProcessId; // rax
  int v25; // eax
  __int64 SvchostPath; // rax
  __int64 v27; // rax
  __int64 v28; // r10
  __int64 UserSidStringFromToken; // rax
  __int64 v30; // rax
  __int64 v31; // r10
  Windows::Internal::CapabilityAccess::Private *v32; // rcx
  char IsAsyncSessionSupportEnabled; // al
  __int64 v34; // rcx
  unsigned int v35; // edx
  const char *v36; // r9
  bool IsAgenticSession; // al
  const char *v38; // r9
  const char *v39; // r9
  int v40; // eax
  __int64 v41; // r10
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // r10
  int v46; // [rsp+20h] [rbp-59h]
  void *SessionId; // [rsp+30h] [rbp-49h] BYREF
  DWORD pSessionId[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v49; // [rsp+40h] [rbp-39h]
  _QWORD v50[2]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v51; // [rsp+58h] [rbp-21h]
  _BYTE v52[32]; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)pSessionId = a4;
  v49 = a1;
  *(_QWORD *)a1 = &Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 20) = 0;
  v7 = a1 + 24;
  *(_OWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 7;
  *(_WORD *)(a1 + 24) = 0;
  v8 = a1 + 56;
  *(_OWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 7;
  *(_WORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 7;
  *(_WORD *)(a1 + 88) = 0;
  v9 = a1 + 120;
  *(_OWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 7;
  *(_WORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  v10 = (void **)(a1 + 168);
  *(_QWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 7;
  *(_WORD *)(a1 + 176) = 0;
  *(_OWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 7;
  *(_WORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a4 + 8LL);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    WPP_SF_DSS(*(_QWORD *)(v12 + 16), v11, v13);
  }
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\adjustedappdisplayinfo.cpp",
      (const char *)0x80070057LL,
      v46);
  *(_DWORD *)(a1 + 152) = a2;
  std::wstring::operator=(v7, a3);
  UserSidStringFromProcessId = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(v50, a2);
  std::wstring::operator=(v9, UserSidStringFromProcessId);
  std::wstring::_Tidy_deallocate(v50);
  ProcessTokenFromProcessId = Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(&SessionId, a2);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    a1 + 160,
    ProcessTokenFromProcessId);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&SessionId);
  if ( Windows::Internal::CapabilityAccess::Private::IsProcessRunningAsInteractiveUser(a2, v16) )
  {
    if ( *(_QWORD *)(a1 + 40) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids);
      }
      std::wstring::operator=(v7, v9);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids);
    }
    *(_QWORD *)(v7 + 16) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7) = 0;
  }
  DsmaSidString = Windows::Internal::CapabilityAccess::Private::GetDsmaSidString(v50);
  v18 = std::wstring::compare(v7, DsmaSidString);
  std::wstring::_Tidy_deallocate(v50);
  if ( !v18 && !*(_BYTE *)(**(_QWORD **)pSessionId + 41LL) )
  {
    Windows::Internal::CapabilityAccess::Private::GetAllSessionUserSidStrings(v50);
    v19 = (__int64)(v50[1] - v50[0]) >> 5;
    if ( v19 )
    {
      if ( v19 == 1 )
      {
        std::wstring::operator=(v7, v50[0]);
      }
      else
      {
        ActiveSessionUserSidString = Windows::Internal::CapabilityAccess::Private::GetActiveSessionUserSidString(v52);
        std::wstring::operator=(v7, ActiveSessionUserSidString);
        std::wstring::_Tidy_deallocate(v52);
      }
    }
    else
    {
      *(_QWORD *)(v7 + 16) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7) = 0;
    }
    std::vector<std::wstring>::_Tidy(v50);
  }
  *(_DWORD *)(a1 + 20) = 1;
  PackageFamilyNameFromProcessId = Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(
                                     v52,
                                     a2);
  std::wstring::operator=(v8, PackageFamilyNameFromProcessId);
  std::wstring::_Tidy_deallocate(v52);
  if ( !*(_QWORD *)(a1 + 72) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
      WPP_SF_S(*(_QWORD *)(v23 + 16), 17, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids, v22);
    }
    ImageFullPathFromProcessId = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(v52, a2);
    std::wstring::operator=(v8, ImageFullPathFromProcessId);
    std::wstring::_Tidy_deallocate(v52);
    *(_DWORD *)(a1 + 20) = 2;
  }
  if ( !*(_QWORD *)(a1 + 72) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\adjustedappdisplayinfo.cpp",
      (const char *)0x80070057LL,
      v46);
  if ( *(_DWORD *)(a1 + 20) == 2 )
  {
    std::wstring::wstring(v50, v8);
    v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)&SessionId,
      v25,
      v25 + 2 * v51,
      v25,
      *(__int64 *)&_o_towlower);
    SvchostPath = Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::GetSvchostPath();
    if ( !(unsigned int)std::wstring::compare(v50, SvchostPath) )
      *(_BYTE *)(a1 + 16) = 1;
    std::wstring::_Tidy_deallocate(v50);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
    && *(_QWORD *)(a1 + 40)
    && !(unsigned int)LUAGetStandardToken(*(HANDLE *)(a1 + 160), v10)
    && (char *)*v10 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      WPP_SF_S(*(_QWORD *)(v28 + 16), 18, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids, v27);
    }
    UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v52, v10);
    std::wstring::operator=(v7, UserSidStringFromToken);
    std::wstring::_Tidy_deallocate(v52);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      WPP_SF_S(*(_QWORD *)(v31 + 16), 19, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids, v30);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
  {
    IsAsyncSessionSupportEnabled = Windows::Internal::CapabilityAccess::Private::IsAsyncSessionSupportEnabled(v32);
    v34 = a1 + 176;
    if ( IsAsyncSessionSupportEnabled )
    {
      std::wstring::operator=(v34, v7);
      pSessionId[0] = 0;
      if ( !ProcessIdToSessionId(*(_DWORD *)(a1 + 152), pSessionId) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\adjustedappdisplayinfo.cpp",
          v36);
      IsAgenticSession = Windows::Internal::CapabilityAccess::Private::IsAgenticSession(
                           (Windows::Internal::CapabilityAccess::Private *)pSessionId[0],
                           v35);
      *(_BYTE *)(a1 + 248) = IsAgenticSession;
      if ( IsAgenticSession )
      {
        LODWORD(SessionId) = -1;
        if ( !(unsigned __int8)WinStationGetParentSessionId(pSessionId[0], &SessionId) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x9D2,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
            v38);
        if ( (_DWORD)SessionId == -1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE4,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\adjustedappdisplayinfo.cpp",
            (const char *)0x8000FFFFLL,
            v46);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          a1 + 240,
          0);
        if ( !WTSQueryUserToken((ULONG)SessionId, (PHANDLE)(a1 + 240)) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xE9,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\adjustedappdisplayinfo.cpp",
            v39);
      }
      else
      {
        *(_BYTE *)(a1 + 248) = 0;
      }
    }
    else
    {
      std::wstring::operator=(v34, v7);
    }
    std::wstring::operator=(a1 + 208, v7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 208);
      v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 176);
      WPP_SF_SS(*(_QWORD *)(v41 + 16), 20, (unsigned int)WPP_8e1a105c905d3ecde492b49159f83969_Traceguids, v40, v42);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
    WPP_SF_S(*(_QWORD *)(v44 + 16), 21, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids, v43);
  }
  return a1;
}

```

## disassembly

```asm
0x180064304  push    rbp
0x180064306  push    rbx
0x180064307  push    rsi
0x180064308  push    rdi
0x180064309  push    r12
0x18006430b  push    r13
0x18006430d  push    r14
0x18006430f  push    r15
0x180064311  lea     rbp, [rsp-1Fh]
0x180064316  sub     rsp, 98h
0x18006431d  mov     rax, cs:__security_cookie
0x180064324  xor     rax, rsp
0x180064327  mov     [rbp+57h+var_48], rax
0x18006432b  mov     qword ptr [rbp+57h+pSessionId], r9
0x18006432f  mov     r12, r8
0x180064332  mov     r14d, edx
0x180064335  mov     rsi, rcx
0x180064338  mov     [rbp+57h+var_90], rcx
0x18006433c  lea     rax, ??_7AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@6B@; const Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::`vftable'
0x180064343  mov     [rcx], rax
0x180064346  xor     eax, eax
0x180064348  mov     [rcx+8], rax
0x18006434c  xor     r8d, r8d
0x18006434f  mov     [rcx+10h], r8b
0x180064353  mov     [rcx+14h], r8d
0x180064357  lea     rdi, [rcx+18h]
0x18006435b  xorps   xmm0, xmm0
0x18006435e  movups  xmmword ptr [rdi], xmm0
0x180064361  mov     [rdi+10h], r8
0x180064365  lea     edx, [rax+7]
0x180064368  mov     [rdi+18h], rdx
0x18006436c  mov     [rdi], r8w
0x180064370  lea     r15, [rcx+38h]
0x180064374  movups  xmmword ptr [r15], xmm0
0x180064378  mov     [r15+10h], r8
0x18006437c  mov     [r15+18h], rdx
0x180064380  mov     [r15], r8w
0x180064384  movups  xmmword ptr [rcx+58h], xmm0
0x180064388  mov     [rcx+68h], r8
0x18006438c  mov     [rcx+70h], rdx
0x180064390  mov     [rcx+58h], r8w
0x180064395  lea     rbx, [rcx+78h]
0x180064399  movups  xmmword ptr [rbx], xmm0
0x18006439c  mov     [rbx+10h], r8
0x1800643a0  mov     [rbx+18h], rdx
0x1800643a4  mov     [rbx], r8w
0x1800643a8  mov     [rcx+0A0h], r8
0x1800643af  lea     r13, [rcx+0A8h]
0x1800643b6  mov     [r13+0], r8
0x1800643ba  movups  xmmword ptr [rcx+0B0h], xmm0
0x1800643c1  mov     [rcx+0C0h], r8
0x1800643c8  mov     [rcx+0C8h], rdx
0x1800643cf  mov     [rcx+0B0h], r8w
0x1800643d7  movups  xmmword ptr [rcx+0D0h], xmm0
0x1800643de  mov     [rcx+0E0h], r8
0x1800643e5  mov     [rcx+0E8h], rdx
0x1800643ec  mov     [rcx+0D0h], r8w
0x1800643f4  mov     [rcx+0F0h], r8
0x1800643fb  lea     rax, WPP_GLOBAL_Control
0x180064402  mov     r10, cs:WPP_GLOBAL_Control
0x180064409  cmp     r10, rax
0x18006440c  jz      short loc_180064455
0x18006440e  test    byte ptr [r10+1Ch], 1
0x180064413  jz      short loc_180064455
0x180064415  cmp     byte ptr [r10+19h], 4
0x18006441a  jb      short loc_180064455
0x18006441c  mov     rcx, [r9]
0x18006441f  add     rcx, 8
0x180064423  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064428  mov     r8, rax
0x18006442b  mov     rcx, r12
0x18006442e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064433  mov     edx, 0Ah
0x180064438  mov     [rsp+0D0h+var_A8], r8; __int64
0x18006443d  mov     [rsp+0D0h+var_B0], rax; int
0x180064442  mov     r9d, r14d
0x180064445  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x18006444c  mov     rcx, [r10+10h]; LoggerHandle
0x180064450  call    WPP_SF_DSS
0x180064455  mov     rcx, [rbp+5Fh]; this
0x180064459  test    r14d, r14d
0x18006445c  jz      loc_1800649C4
0x180064462  mov     [rsi+98h], r14d
0x180064469  mov     rdx, r12
0x18006446c  mov     rcx, rdi
0x18006446f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180064474  mov     edx, r14d
0x180064477  lea     rcx, [rbp+57h+var_88]
0x18006447b  call    ?GetUserSidStringFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(ulong)
0x180064480  mov     rdx, rax
0x180064483  mov     rcx, rbx
0x180064486  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006448b  lea     rcx, [rbp+57h+var_88]
0x18006448f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064494  mov     edx, r14d; dwProcessId
0x180064497  lea     rcx, [rbp+57h+SessionId]; phNewToken
0x18006449b  call    ?GetProcessTokenFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::GetProcessTokenFromProcessId(ulong)
0x1800644a0  mov     rdx, rax
0x1800644a3  lea     r12, [rsi+0A0h]
0x1800644aa  mov     rcx, r12
0x1800644ad  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800644b2  lea     rcx, [rbp+57h+SessionId]
0x1800644b6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800644bb  mov     ecx, r14d; dwProcessId
0x1800644be  call    ?IsProcessRunningAsInteractiveUser@Private@CapabilityAccess@Internal@Windows@@YA_NK@Z; Windows::Internal::CapabilityAccess::Private::IsProcessRunningAsInteractiveUser(ulong)
0x1800644c3  test    al, al
0x1800644c5  jnz     short loc_180064515
0x1800644c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644ce  lea     rax, WPP_GLOBAL_Control
0x1800644d5  cmp     rcx, rax
0x1800644d8  jz      short loc_1800644FB
0x1800644da  test    byte ptr [rcx+1Ch], 1
0x1800644de  jz      short loc_1800644FB
0x1800644e0  cmp     byte ptr [rcx+19h], 4
0x1800644e4  jb      short loc_1800644FB
0x1800644e6  mov     edx, 0Bh
0x1800644eb  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x1800644f2  mov     rcx, [rcx+10h]
0x1800644f6  call    WPP_SF_
0x1800644fb  mov     qword ptr [rdi+10h], 0
0x180064503  mov     rcx, rdi
0x180064506  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006450b  mov     rdx, rax
0x18006450e  xor     eax, eax
0x180064510  mov     [rdx], ax
0x180064513  jmp     short loc_180064591
0x180064515  cmp     qword ptr [rsi+28h], 0
0x18006451a  jnz     short loc_18006455D
0x18006451c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064523  lea     rax, WPP_GLOBAL_Control
0x18006452a  cmp     rcx, rax
0x18006452d  jz      short loc_180064550
0x18006452f  test    byte ptr [rcx+1Ch], 1
0x180064533  jz      short loc_180064550
0x180064535  cmp     byte ptr [rcx+19h], 4
0x180064539  jb      short loc_180064550
0x18006453b  mov     edx, 0Ch
0x180064540  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x180064547  mov     rcx, [rcx+10h]
0x18006454b  call    WPP_SF_
0x180064550  mov     rdx, rbx
0x180064553  mov     rcx, rdi
0x180064556  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006455b  jmp     short loc_180064591
0x18006455d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064564  lea     rax, WPP_GLOBAL_Control
0x18006456b  cmp     rcx, rax
0x18006456e  jz      short loc_180064591
0x180064570  test    byte ptr [rcx+1Ch], 1
0x180064574  jz      short loc_180064591
0x180064576  cmp     byte ptr [rcx+19h], 4
0x18006457a  jb      short loc_180064591
0x18006457c  mov     edx, 0Dh
0x180064581  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x180064588  mov     rcx, [rcx+10h]
0x18006458c  call    WPP_SF_
0x180064591  lea     rcx, [rbp+57h+var_88]
0x180064595  call    ?GetDsmaSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::GetDsmaSidString(void)
0x18006459a  mov     rdx, rax
0x18006459d  mov     rcx, rdi
0x1800645a0  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x1800645a5  mov     ebx, eax
0x1800645a7  lea     rcx, [rbp+57h+var_88]
0x1800645ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800645b0  test    ebx, ebx
0x1800645b2  jnz     short loc_180064629
0x1800645b4  mov     rax, qword ptr [rbp+57h+pSessionId]
0x1800645b8  mov     rax, [rax]
0x1800645bb  xor     ebx, ebx
0x1800645bd  cmp     [rax+29h], bl
0x1800645c0  jnz     short loc_18006462B
0x1800645c2  lea     rcx, [rbp+57h+var_88]
0x1800645c6  call    ?GetAllSessionUserSidStrings@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::GetAllSessionUserSidStrings(void)
0x1800645cb  nop
0x1800645cc  mov     rax, [rbp+57h+var_80]
0x1800645d0  mov     rdx, [rbp+57h+var_88]
0x1800645d4  sub     rax, rdx
0x1800645d7  sar     rax, 5
0x1800645db  test    rax, rax
0x1800645de  jz      short loc_18006460F
0x1800645e0  cmp     rax, 1
0x1800645e4  jz      short loc_180064605
0x1800645e6  lea     rcx, [rbp+57h+var_68]
0x1800645ea  call    ?GetActiveSessionUserSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::GetActiveSessionUserSidString(void)
0x1800645ef  mov     rdx, rax
0x1800645f2  mov     rcx, rdi
0x1800645f5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800645fa  lea     rcx, [rbp+57h+var_68]
0x1800645fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064603  jmp     short loc_18006461E
0x180064605  mov     rcx, rdi
0x180064608  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006460d  jmp     short loc_18006461E
0x18006460f  mov     [rdi+10h], rbx
0x180064613  mov     rcx, rdi
0x180064616  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006461b  mov     [rax], bx
0x18006461e  lea     rcx, [rbp+57h+var_88]
0x180064622  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180064627  jmp     short loc_18006462B
0x180064629  xor     ebx, ebx
0x18006462b  mov     dword ptr [rsi+14h], 1
0x180064632  mov     edx, r14d
0x180064635  lea     rcx, [rbp+57h+var_68]
0x180064639  call    ?GetPackageFamilyNameFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(ulong)
0x18006463e  mov     rdx, rax
0x180064641  mov     rcx, r15
0x180064644  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180064649  lea     rcx, [rbp+57h+var_68]
0x18006464d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180064652  cmp     [rsi+48h], rbx
0x180064656  jnz     short loc_1800646C0
0x180064658  mov     r10, cs:WPP_GLOBAL_Control
0x18006465f  lea     rax, WPP_GLOBAL_Control
0x180064666  cmp     r10, rax
0x180064669  jz      short loc_180064699
0x18006466b  test    byte ptr [r10+1Ch], 1
0x180064670  jz      short loc_180064699
0x180064672  cmp     byte ptr [r10+19h], 4
0x180064677  jb      short loc_180064699
0x180064679  mov     rcx, r15
0x18006467c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180064681  mov     edx, 11h
0x180064686  mov     r9, rax
0x180064689  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x180064690  mov     rcx, [r10+10h]
0x180064694  call    WPP_SF_S
0x180064699  mov     edx, r14d
0x18006469c  lea     rcx, [rbp+57h+var_68]
0x1800646a0  call    ?GetImageFullPathFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(ulong)
0x1800646a5  mov     rdx, rax
0x1800646a8  mov     rcx, r15
0x1800646ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800646b0  lea     rcx, [rbp+57h+var_68]
0x1800646b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800646b9  mov     dword ptr [rsi+14h], 2
0x1800646c0  mov     rcx, [rbp+5Fh]; this
0x1800646c4  cmp     [rsi+48h], rbx
0x1800646c8  jz      loc_1800649DC
0x1800646ce  cmp     dword ptr [rsi+14h], 2
0x1800646d2  jnz     short loc_18006472F
0x1800646d4  mov     rdx, r15
0x1800646d7  lea     rcx, [rbp+57h+var_88]
0x1800646db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800646e0  nop
0x1800646e1  lea     rcx, [rbp+57h+var_88]
0x1800646e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800646ea  mov     rdx, rax
0x1800646ed  mov     rax, [rbp+57h+var_78]
0x1800646f1  lea     r8, [rdx+rax*2]
0x1800646f5  mov     rax, cs:__imp__o_towlower
0x1800646fc  mov     [rsp+0D0h+var_B0], rax; int
0x180064701  mov     r9, rdx
0x180064704  lea     rcx, [rbp+57h+SessionId]
0x180064708  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18006470d  call    ?GetSvchostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::GetSvchostPath(void)
0x180064712  mov     rdx, rax
0x180064715  lea     rcx, [rbp+57h+var_88]
0x180064719  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x18006471e  test    eax, eax
0x180064720  jnz     short loc_180064726
0x180064722  mov     byte ptr [rsi+10h], 1
0x180064726  lea     rcx, [rbp+57h+var_88]
0x18006472a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006472f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180064736  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18006473b  test    al, al
0x18006473d  jz      loc_18006480F
0x180064743  cmp     [rsi+28h], rbx
0x180064747  jz      loc_18006480F
0x18006474d  mov     rdx, r13; NewTokenHandle
0x180064750  mov     rcx, [r12]; TokenHandle
0x180064754  call    LUAGetStandardToken
0x180064759  test    eax, eax
0x18006475b  jnz     loc_18006480F
0x180064761  mov     rax, [r13+0]
0x180064765  dec     rax
0x180064768  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006476c  ja      loc_18006480F
0x180064772  mov     r10, cs:WPP_GLOBAL_Control
0x180064779  lea     r12, WPP_GLOBAL_Control
0x180064780  cmp     r10, r12
0x180064783  jz      short loc_1800647B3
0x180064785  test    byte ptr [r10+1Ch], 1
0x18006478a  jz      short loc_1800647B3
0x18006478c  cmp     byte ptr [r10+19h], 4
0x180064791  jb      short loc_1800647B3
0x180064793  mov     rcx, rdi
0x180064796  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006479b  mov     edx, 12h
0x1800647a0  mov     r9, rax
0x1800647a3  lea     r8, WPP_8e1a105c905d3ecde492b49159f83969_Traceguids
0x1800647aa  mov     rcx, [r10+10h]
0x1800647ae  call    WPP_SF_S
0x1800647b3  mov     rdx, r13
0x1800647b6  lea     rcx, [rbp+57h+var_68]
0x1800647ba  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800647bf  mov     rdx, rax
0x1800647c2  mov     rcx, rdi
0x1800647c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
  ... truncated ...
```
