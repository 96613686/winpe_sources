# WebAuthNReportPasskeyHeartbeatServer

- ea: `0x180039a40`
- end: `0x18003a320`
- name: `WebAuthNReportPasskeyHeartbeatServer`
- size: `2272`
- prototype: ``
- caller_count: `4`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180085a2c`
- `0x1800acd58`
- `0x1800ad46c`
- `0x1800db85c`

## callees

- `0x1800031c0`
- `0x180017764`
- `0x180017a88`
- `0x180019938`
- `0x18001ee7c`
- `0x180021878`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003988c`
- `0x180039a40`
- `0x18003a328`
- `0x1800412c8`
- `0x18004349c`
- `0x180046820`
- `0x18004685c`
- `0x180047b08`
- `0x18004f8cc`
- `0x180053702`
- `0x1800537a4`
- `0x180063680`
- `0x18006b260`
- `0x18006f240`
- `0x18006f750`
- `0x18007e2a8`
- `0x18007fbb4`
- `0x18008b958`
- `0x18008f788`
- `0x18009331c`
- `0x180095734`
- `0x1800957a0`
- `0x180109d1c`
- `0x180109fa0`
- `0x18010a678`
- `0x18013c090`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180039aee`
- `msvcp_win!_Xtime_get_ticks` at `0x180039aee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180039e24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180039e32`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180039e24`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180039e32`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a17a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a17a`

## string_xrefs

- `0x18003a30d`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180039aba`: `onecore\ds\security\fido\webauthn\dll\webauthntelemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WebAuthNReportPasskeyHeartbeatServer(void *a1, int a2)
{
  __int16 v4; // r12
  int unique_key_nothrow; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  __int64 ticks; // rbx
  __int64 v10; // rsi
  unsigned __int16 *v11; // rbx
  unsigned __int64 v12; // rcx
  const unsigned __int8 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  char v15; // di
  signed __int64 v16; // r14
  signed __int64 v17; // r15
  unsigned __int8 *v18; // rbx
  CredentialInfo *v19; // r13
  __int64 v20; // rdx
  _QWORD *v21; // r9
  __int64 v22; // rbx
  __int64 v23; // r14
  __int64 v24; // r15
  _DWORD *v25; // r8
  int v26; // r8d
  int v27; // r9d
  int v28; // r8d
  int v29; // r9d
  int v30; // eax
  int lpData; // [rsp+20h] [rbp-1F8h]
  int lpDataa; // [rsp+20h] [rbp-1F8h]
  char v33; // [rsp+70h] [rbp-1A8h] BYREF
  _BYTE v34[3]; // [rsp+71h] [rbp-1A7h] BYREF
  __int16 v35; // [rsp+74h] [rbp-1A4h] BYREF
  _BYTE v36[2]; // [rsp+76h] [rbp-1A2h] BYREF
  int v37; // [rsp+78h] [rbp-1A0h] BYREF
  unsigned __int64 Data; // [rsp+80h] [rbp-198h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-190h] BYREF
  int v40; // [rsp+90h] [rbp-188h] BYREF
  int v41; // [rsp+94h] [rbp-184h] BYREF
  int *v42; // [rsp+98h] [rbp-180h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-178h]
  CredentialInfo *v44[2]; // [rsp+A8h] [rbp-170h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-160h]
  unsigned __int16 *v46; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v47[8]; // [rsp+C8h] [rbp-150h] BYREF
  void *v48[2]; // [rsp+D0h] [rbp-148h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-138h]
  CredentialInfo *v50[2]; // [rsp+E8h] [rbp-130h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-120h]
  _QWORD v52[2]; // [rsp+100h] [rbp-118h] BYREF
  _QWORD v53[2]; // [rsp+110h] [rbp-108h] BYREF
  _BYTE v54[8]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v55[8]; // [rsp+128h] [rbp-F0h] BYREF
  CredentialInfo *v56[2]; // [rsp+130h] [rbp-E8h] BYREF
  __int64 v57; // [rsp+140h] [rbp-D8h]
  _BYTE v58[16]; // [rsp+148h] [rbp-D0h] BYREF
  _BYTE v59[16]; // [rsp+158h] [rbp-C0h] BYREF
  _BYTE v60[16]; // [rsp+168h] [rbp-B0h] BYREF
  _BYTE v61[72]; // [rsp+178h] [rbp-A0h] BYREF
  unsigned __int8 *v62[4]; // [rsp+1C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  try
  {
    wil::impersonate_token(v47, a1);
    v4 = 0;
    hKey = 0;
    unique_key_nothrow = wil::reg::create_unique_key_nothrow(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Passkeys");
    v6 = unique_key_nothrow;
    if ( unique_key_nothrow >= 0 )
    {
      ticks = _Xtime_get_ticks();
      wil::reg::try_get_value<unsigned int>(v54, hKey, 0, L"LastHeartbeatWithSyncedInfoEpochDay");
      wil::reg::try_get_value<unsigned int>(v55, hKey, 0, L"LastHeartbeatEpochDay");
      v10 = (ticks + 116444736000000000LL) / 864000000000LL;
      if ( a2
        && (v54[4] && (_DWORD)v10 == *(_DWORD *)std::optional<unsigned int>::value(v54)
         || v55[4] && (_DWORD)v10 == *(_DWORD *)std::optional<unsigned int>::value(v55)) )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v47);
        result = 1;
      }
      else
      {
        v46 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v46,
          0);
        FidoGetUserSid(&v46);
        v11 = v46;
        std::wstring::wstring(v62, v46);
        v13 = (const unsigned __int8 *)v62;
        if ( v62[3] > (unsigned __int8 *)7 )
          v13 = v62[0];
        Data = std::_Fnv1a_append_bytes(v12, v13, 2 * (__int64)v62[2]);
        std::wstring::_Tidy_deallocate(v62);
        CredentialAuthenticatorCache::Refresh(a1, v14);
        *(_OWORD *)v44 = 0;
        v45 = 0;
        *(_OWORD *)v50 = 0;
        v51 = 0;
        *(_OWORD *)v56 = 0;
        v57 = 0;
        v15 = 1;
        v61[64] = 1;
        CredentialAuthenticatorCache::GetCredentialsFrom(v11, v61, 0, v44);
        std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(v61);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
          CredentialAuthenticatorCache::GetAllCredentialsFrom3PP(v11, v50);
        v16 = v44[1] - v44[0];
        v17 = v50[1] - v50[0];
        std::ranges::_Copy_fn::operator()<std::vector<CredentialInfo> &,std::back_insert_iterator<std::vector<CredentialInfo>>>(
          &v42,
          v56,
          v44);
        *(_OWORD *)v48 = 0;
        v49 = 0;
        v35 = wil::safe_cast<unsigned short,unsigned __int64,0>(0x2E8BA2E8BA2E8BA3LL * ((v44[1] - v44[0]) >> 5));
        std::ranges::_Copy_unchecked<unsigned char *,unsigned char *,std::back_insert_iterator<std::vector<unsigned char>>>(
          &v42,
          &v35,
          v36,
          v48);
        v18 = (unsigned __int8 *)v44[0];
        v19 = v44[1];
        while ( 1 )
        {
          if ( v18 == (unsigned __int8 *)v19 )
          {
            v15 = 0;
            goto LABEL_29;
          }
          v20 = 2LL * *(_QWORD *)(std::wstring::operator std::basic_string_view<unsigned short>(v18 + 40, v58) + 8) + 2;
          v33 = 0;
          if ( v18[348] )
            v33 = v18[344];
          v37 = v18[201];
          if ( (unsigned __int64)v48[1] + v20 - (unsigned __int64)v48[0] + 5 > 0xFFFF )
            break;
          if ( v21[3] > 7u )
            v21 = (_QWORD *)*v21;
          v53[0] = v21;
          v53[1] = v20;
          std::ranges::_Copy_fn::operator()<std::span<unsigned char const,-1>,std::back_insert_iterator<std::vector<unsigned char>>>(
            v59,
            v53,
            v48);
          v52[0] = &v33;
          v52[1] = 1;
          std::ranges::_Copy_fn::operator()<std::span<unsigned char const,-1>,std::back_insert_iterator<std::vector<unsigned char>>>(
            v60,
            v52,
            v48);
          v42 = &v37;
          v43 = 4;
          std::ranges::_Copy_fn::operator()<std::span<unsigned char const,-1>,std::back_insert_iterator<std::vector<unsigned char>>>(
            v62,
            &v42,
            v48);
          ++v4;
          v18 += 352;
        }
        if ( v48[0] )
        {
          if ( (void *)((char *)v48[1] - (char *)v48[0]) >= (void *)2 )
          {
            *(_WORD *)v48[0] = v4;
            goto LABEL_29;
          }
          memset_0(v48[0], 0, (char *)v48[1] - (char *)v48[0]);
          *(_DWORD *)_o__errno() = 34;
        }
        else
        {
          *(_DWORD *)_o__errno() = 22;
        }
        invalid_parameter_noinfo();
LABEL_29:
        v22 = (unsigned __int8)Data;
        v23 = 0x2E8BA2E8BA2E8BA3LL * (v16 >> 5);
        v24 = 0x2E8BA2E8BA2E8BA3LL * (v17 >> 5);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
        {
          v25 = *(_DWORD **)(wil::details::static_lazy<FidoRestrictedCoreProvider>::get() + 16);
          if ( *v25 > 5u && (unsigned __int8)tlgKeywordOn(v25, 0x800000000000LL) )
          {
            v42 = (int *)v48[0];
            LODWORD(v43) = (unsigned __int16)(LOWORD(v48[1]) - LOWORD(v48[0]));
            v33 = v15;
            v34[0] = 0;
            v37 = v23;
            v40 = v24;
            v41 = 0;
            LODWORD(Data) = 0;
            v52[0] = v22;
            v53[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(
              v26,
              (unsigned int)&unk_180186898,
              v26,
              v27,
              (__int64)v53,
              (__int64)v52,
              (__int64)&Data,
              (__int64)&v41,
              (__int64)&v40,
              (__int64)&v37,
              (__int64)v34,
              (__int64)&v33,
              (__int64)&v42);
          }
        }
        else if ( (unsigned int)dword_1801AB148 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801AB148, 0x800000000000LL) )
        {
          v42 = (int *)v48[0];
          LODWORD(v43) = (unsigned __int16)(LOWORD(v48[1]) - LOWORD(v48[0]));
          v34[0] = v15;
          v33 = 0;
          LODWORD(Data) = v23;
          v41 = v24;
          v40 = 0;
          v37 = 0;
          v53[0] = v22;
          v52[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(
            (unsigned int)&dword_1801AB148,
            (unsigned int)&unk_1801867A6,
            v28,
            v29,
            (__int64)v52,
            (__int64)v53,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v41,
            (__int64)&Data,
            (__int64)&v33,
            (__int64)v34,
            (__int64)&v42);
        }
        LODWORD(Data) = v10;
        v30 = RegSetKeyValueW(hKey, 0, L"LastHeartbeatEpochDay", 4u, &Data, 4u);
        if ( v30 > 0 )
          v30 = (unsigned __int16)v30 | 0x80070000;
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
            (const char *)(unsigned int)v30,
            lpDataa);
        std::vector<unsigned char>::_Tidy(v48);
        if ( v56[0] )
        {
          std::_Destroy_range<std::allocator<CredentialInfo>>(v56[0]);
          std::_Deallocate<16>(v56[0], 32 * ((signed __int64)(v57 - (unsigned __int64)v56[0]) >> 5));
          *(_OWORD *)v56 = 0;
          v57 = 0;
        }
        if ( v50[0] )
        {
          std::_Destroy_range<std::allocator<CredentialInfo>>(v50[0]);
          std::_Deallocate<16>(v50[0], 32 * ((signed __int64)(v51 - (unsigned __int64)v50[0]) >> 5));
          *(_OWORD *)v50 = 0;
          v51 = 0;
        }
        if ( v44[0] )
        {
          std::_Destroy_range<std::allocator<CredentialInfo>>(v44[0]);
          std::_Deallocate<16>(v44[0], 32 * ((signed __int64)(v45 - (unsigned __int64)v44[0]) >> 5));
          *(_OWORD *)v44 = 0;
          v45 = 0;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v46);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v47);
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthntelemetry.cpp",
        (const char *)(unsigned int)unique_key_nothrow,
        lpData);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v47);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x174,
                           (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthntelemetry.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180039a40  mov     [rsp+arg_8], rbx
0x180039a45  mov     [rsp+arg_10], rsi
0x180039a4a  push    rdi
0x180039a4b  push    r12
0x180039a4d  push    r13
0x180039a4f  push    r14
0x180039a51  push    r15
0x180039a53  sub     rsp, 1F0h
0x180039a5a  mov     rax, cs:__security_cookie
0x180039a61  xor     rax, rsp
0x180039a64  mov     [rsp+218h+var_38], rax
0x180039a6c  mov     r14d, edx
0x180039a6f  mov     rdi, rcx
0x180039a72  mov     rdx, rcx
0x180039a75  lea     rcx, [rsp+218h+var_150]
0x180039a7d  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x180039a82  nop
0x180039a83  xor     r12d, r12d
0x180039a86  mov     [rsp+218h+hKey], r12
0x180039a8e  lea     r8, [rsp+218h+hKey]
0x180039a96  mov     rdx, cs:off_18014C840; lpSubKey
0x180039a9d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180039aa4  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180039aa9  mov     ebx, eax
0x180039aab  test    eax, eax
0x180039aad  jns     short loc_180039AEE
0x180039aaf  mov     rcx, [rsp+218h]; this
0x180039ab7  mov     r9d, eax; char *
0x180039aba  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180039ac1  lea     edx, [r12+64h]; void *
0x180039ac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039acb  nop
0x180039acc  lea     rcx, [rsp+218h+hKey]
0x180039ad4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039ad9  nop
0x180039ada  lea     rcx, [rsp+218h+var_150]
0x180039ae2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180039ae7  mov     eax, ebx
0x180039ae9  jmp     loc_18003A2DD
0x180039aee  call    cs:__imp__Xtime_get_ticks
0x180039af4  mov     rbx, rax
0x180039af7  mov     r9, cs:off_18014C850; "LastHeartbeatWithSyncedInfoEpochDay"
0x180039afe  xor     r8d, r8d
0x180039b01  mov     rdx, [rsp+218h+hKey]
0x180039b09  lea     rcx, [rsp+218h+var_F8]
0x180039b11  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG1@Z; wil::reg::try_get_value<uint>(HKEY__ *,ushort const *,ushort const *)
0x180039b16  mov     r9, cs:lpValueName
0x180039b1d  xor     r8d, r8d
0x180039b20  mov     rdx, [rsp+218h+hKey]
0x180039b28  lea     rcx, [rsp+218h+var_F0]
0x180039b30  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG1@Z; wil::reg::try_get_value<uint>(HKEY__ *,ushort const *,ushort const *)
0x180039b35  mov     rax, 19DB1DED53E8000h
0x180039b3f  add     rax, rbx
0x180039b42  cqo
0x180039b44  mov     rcx, 0C92A69C000h
0x180039b4e  idiv    rcx
0x180039b51  mov     rsi, rax
0x180039b54  test    r14d, r14d
0x180039b57  jz      loc_180039BDD
0x180039b5d  cmp     [rsp+218h+var_F4], r12b
0x180039b65  jz      short loc_180039B9D
0x180039b67  lea     rcx, [rsp+218h+var_F8]
0x180039b6f  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x180039b74  cmp     esi, [rax]
0x180039b76  jnz     short loc_180039B9D
0x180039b78  lea     rcx, [rsp+218h+hKey]
0x180039b80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039b85  nop
0x180039b86  lea     rcx, [rsp+218h+var_150]
0x180039b8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180039b93  mov     eax, 1
0x180039b98  jmp     loc_18003A2DD
0x180039b9d  cmp     [rsp+218h+var_EC], r12b
0x180039ba5  jz      short loc_180039BDD
0x180039ba7  lea     rcx, [rsp+218h+var_F0]
0x180039baf  call    ?value@?$optional@I@std@@QEGBAAEBIXZ; std::optional<uint>::value(void)
0x180039bb4  cmp     esi, [rax]
0x180039bb6  jnz     short loc_180039BDD
0x180039bb8  lea     rcx, [rsp+218h+hKey]
0x180039bc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039bc5  nop
0x180039bc6  lea     rcx, [rsp+218h+var_150]
0x180039bce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180039bd3  mov     eax, 1
0x180039bd8  jmp     loc_18003A2DD
0x180039bdd  mov     [rsp+218h+var_158], r12
0x180039be5  xor     edx, edx
0x180039be7  lea     rcx, [rsp+218h+var_158]
0x180039bef  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039bf4  lea     rcx, [rsp+218h+var_158]; unsigned __int16 **
0x180039bfc  call    ?FidoGetUserSid@@YAJPEAPEAG@Z; FidoGetUserSid(ushort * *)
0x180039c01  mov     rbx, [rsp+218h+var_158]
0x180039c09  mov     rdx, rbx
0x180039c0c  lea     rcx, [rsp+218h+var_58]
0x180039c14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039c19  mov     r8, [rsp+218h+var_48]
0x180039c21  lea     rdx, [rsp+218h+var_58]
0x180039c29  cmp     [rsp+218h+var_40], 7
0x180039c32  cmova   rdx, [rsp+218h+var_58]; unsigned __int8 *
0x180039c3b  add     r8, r8; unsigned __int64
0x180039c3e  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180039c43  mov     [rsp+218h+Data], rax
0x180039c4b  lea     rcx, [rsp+218h+var_58]
0x180039c53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c58  mov     rcx, rdi; void *
0x180039c5b  call    ?Refresh@CredentialAuthenticatorCache@@SAJQEAXPEBG@Z; CredentialAuthenticatorCache::Refresh(void * const,ushort const *)
0x180039c60  xorps   xmm0, xmm0
0x180039c63  movdqu  xmmword ptr [rsp+218h+var_170], xmm0
0x180039c6c  mov     [rsp+218h+var_160], r12
0x180039c74  movdqu  xmmword ptr [rsp+218h+var_130], xmm0
0x180039c7d  mov     [rsp+218h+var_120], r12
0x180039c85  movdqu  xmmword ptr [rsp+218h+var_E8], xmm0
0x180039c8e  mov     [rsp+218h+var_D8], r12
0x180039c96  mov     edi, 1
0x180039c9b  mov     [rsp+218h+var_60], dil
0x180039ca3  lea     r9, [rsp+218h+var_170]
0x180039cab  xor     r8d, r8d
0x180039cae  lea     rdx, [rsp+218h+var_A0]
0x180039cb6  mov     rcx, rbx
0x180039cb9  call    ?GetCredentialsFrom@CredentialAuthenticatorCache@@SAJPEBGAEBV?$variant@UEmpty@Locations@FidoCredProvHelper@@UThisPc@23@UQrCode@23@USecurityKey@23@ULinkedDevice@23@UPluginAuthenticator@23@USyncedAccount@23@@std@@0AEAV?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@3@@Z; CredentialAuthenticatorCache::GetCredentialsFrom(ushort const *,std::variant<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount> const &,ushort const *,std::vector<CredentialInfo> &)
0x180039cbe  nop
0x180039cbf  lea     rcx, [rsp+218h+var_A0]
0x180039cc7  call    ?_Destroy@?$_Variant_base@UEmpty@Locations@FidoCredProvHelper@@UThisPc@23@UQrCode@23@USecurityKey@23@ULinkedDevice@23@UPluginAuthenticator@23@USyncedAccount@23@@std@@QEAAXXZ; std::_Variant_base<FidoCredProvHelper::Locations::Empty,FidoCredProvHelper::Locations::ThisPc,FidoCredProvHelper::Locations::QrCode,FidoCredProvHelper::Locations::SecurityKey,FidoCredProvHelper::Locations::LinkedDevice,FidoCredProvHelper::Locations::PluginAuthenticator,FidoCredProvHelper::Locations::SyncedAccount>::_Destroy(void)
0x180039ccc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x180039cd3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x180039cd8  test    al, al
0x180039cda  jz      short loc_180039CEC
0x180039cdc  lea     rdx, [rsp+218h+var_130]
0x180039ce4  mov     rcx, rbx
0x180039ce7  call    ?GetAllCredentialsFrom3PP@CredentialAuthenticatorCache@@SAJPEBGAEAV?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@std@@@Z; CredentialAuthenticatorCache::GetAllCredentialsFrom3PP(ushort const *,std::vector<CredentialInfo> &)
0x180039cec  mov     r14, [rsp+218h+var_170+8]
0x180039cf4  sub     r14, [rsp+218h+var_170]
0x180039cfc  mov     r15, [rsp+218h+var_130+8]
0x180039d04  sub     r15, [rsp+218h+var_130]
0x180039d0c  lea     r8, [rsp+218h+var_170]
0x180039d14  lea     rdx, [rsp+218h+var_E8]
0x180039d1c  lea     rcx, [rsp+218h+var_180]
0x180039d24  call    ??$?RAEAV?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@std@@V?$back_insert_iterator@V?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@std@@@1@@_Copy_fn@ranges@std@@SA?AU?$in_out_result@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCredentialInfo@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@std@@@2@@12@AEAV?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@2@V?$back_insert_iterator@V?$vector@UCredentialInfo@@V?$allocator@UCredentialInfo@@@std@@@std@@@2@@Z; std::ranges::_Copy_fn::operator()<std::vector<CredentialInfo> &,std::back_insert_iterator<std::vector<CredentialInfo>>>(std::vector<CredentialInfo> &,std::back_insert_iterator<std::vector<CredentialInfo>>)
0x180039d29  xorps   xmm0, xmm0
0x180039d2c  movdqu  xmmword ptr [rsp+218h+var_148], xmm0
0x180039d35  mov     [rsp+218h+var_138], r12
0x180039d3d  mov     rcx, [rsp+218h+var_170+8]
0x180039d45  sub     rcx, [rsp+218h+var_170]
0x180039d4d  sar     rcx, 5
0x180039d51  mov     rax, 2E8BA2E8BA2E8BA3h
0x180039d5b  imul    rcx, rax
0x180039d5f  call    ??$safe_cast@G_K$0A@@wil@@YAG_K@Z; wil::safe_cast<ushort,unsigned __int64,0>(unsigned __int64)
0x180039d64  mov     [rsp+218h+var_1A4], ax
0x180039d69  lea     r9, [rsp+218h+var_148]
0x180039d71  lea     r8, [rsp+218h+var_1A2]
0x180039d76  lea     rdx, [rsp+218h+var_1A4]
0x180039d7b  lea     rcx, [rsp+218h+var_180]
0x180039d83  call    ??$_Copy_unchecked@PEAEPEAEV?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@std@@@ranges@std@@YA?AU?$in_out_result@PEAEV?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@std@@@01@PEAE0V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@1@@Z; std::ranges::_Copy_unchecked<uchar *,uchar *,std::back_insert_iterator<std::vector<uchar>>>(uchar *,uchar *,std::back_insert_iterator<std::vector<uchar>>)
0x180039d88  mov     rbx, [rsp+218h+var_170]
0x180039d90  mov     r13, [rsp+218h+var_170+8]
0x180039d98  cmp     rbx, r13
0x180039d9b  jz      loc_180039EFA
0x180039da1  lea     r9, [rbx+28h]
0x180039da5  lea     rdx, [rsp+218h+var_D0]
0x180039dad  mov     rcx, r9
0x180039db0  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x180039db5  mov     rcx, [rax+8]
0x180039db9  lea     rdx, ds:2[rcx*2]
0x180039dc1  mov     [rsp+218h+var_1A8], 0
0x180039dc6  cmp     byte ptr [rbx+15Ch], 0
0x180039dcd  jz      short loc_180039DD9
0x180039dcf  mov     al, [rbx+158h]
0x180039dd5  mov     [rsp+218h+var_1A8], al
0x180039dd9  movzx   eax, byte ptr [rbx+0C9h]
0x180039de0  mov     [rsp+218h+var_1A0], eax
0x180039de4  mov     rax, rdx
0x180039de7  mov     rcx, [rsp+218h+var_148]; void *
0x180039def  sub     rax, rcx
0x180039df2  mov     r8, [rsp+218h+var_148+8]
0x180039dfa  add     rax, 5
0x180039dfe  add     rax, r8
0x180039e01  cmp     rax, 0FFFFh
0x180039e07  jbe     short loc_180039E4B
0x180039e09  test    rcx, rcx
0x180039e0c  jz      short loc_180039E32
0x180039e0e  sub     r8, rcx; Size
0x180039e11  cmp     r8, 2
0x180039e15  jb      short loc_180039E1D
0x180039e17  mov     [rcx], r12w
0x180039e1b  jmp     short loc_180039E43
0x180039e1d  xor     edx, edx; Val
0x180039e1f  call    memset_0
0x180039e24  call    cs:__imp__o__errno
0x180039e2a  mov     dword ptr [rax], 22h ; '"'
0x180039e30  jmp     short loc_180039E3E
0x180039e32  call    cs:__imp__o__errno
0x180039e38  mov     dword ptr [rax], 16h
0x180039e3e  call    _invalid_parameter_noinfo
0x180039e43  xor     r12d, r12d
0x180039e46  jmp     loc_180039F00
0x180039e4b  cmp     qword ptr [r9+18h], 7
0x180039e50  jbe     short loc_180039E55
0x180039e52  mov     r9, [r9]
0x180039e55  mov     [rsp+218h+var_108], r9
0x180039e5d  mov     [rsp+218h+var_100], rdx
0x180039e65  lea     r8, [rsp+218h+var_148]
0x180039e6d  lea     rdx, [rsp+218h+var_108]
0x180039e75  lea     rcx, [rsp+218h+var_C0]
0x180039e7d  call    ??$?RV?$span@$$CBE$0?0@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@1@@_Copy_fn@ranges@std@@SA?AU?$in_out_result@U?$_Span_iterator@$$CBE@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@12@$$QEAV?$span@$$CBE$0?0@2@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@Z; std::ranges::_Copy_fn::operator()<std::span<uchar const,-1>,std::back_insert_iterator<std::vector<uchar>>>(std::span<uchar const,-1> &&,std::back_insert_iterator<std::vector<uchar>>)
0x180039e82  lea     rax, [rsp+218h+var_1A8]
0x180039e87  mov     [rsp+218h+var_118], rax
0x180039e8f  mov     [rsp+218h+var_110], rdi
0x180039e97  lea     r8, [rsp+218h+var_148]
0x180039e9f  lea     rdx, [rsp+218h+var_118]
0x180039ea7  lea     rcx, [rsp+218h+var_B0]
0x180039eaf  call    ??$?RV?$span@$$CBE$0?0@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@1@@_Copy_fn@ranges@std@@SA?AU?$in_out_result@U?$_Span_iterator@$$CBE@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@12@$$QEAV?$span@$$CBE$0?0@2@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@Z; std::ranges::_Copy_fn::operator()<std::span<uchar const,-1>,std::back_insert_iterator<std::vector<uchar>>>(std::span<uchar const,-1> &&,std::back_insert_iterator<std::vector<uchar>>)
0x180039eb4  lea     rax, [rsp+218h+var_1A0]
0x180039eb9  mov     [rsp+218h+var_180], rax
0x180039ec1  mov     [rsp+218h+var_178], 4
0x180039ecd  lea     r8, [rsp+218h+var_148]
0x180039ed5  lea     rdx, [rsp+218h+var_180]
0x180039edd  lea     rcx, [rsp+218h+var_58]
0x180039ee5  call    ??$?RV?$span@$$CBE$0?0@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@1@@_Copy_fn@ranges@std@@SA?AU?$in_out_result@U?$_Span_iterator@$$CBE@std@@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@12@$$QEAV?$span@$$CBE$0?0@2@V?$back_insert_iterator@V?$vector@EV?$allocator@E@std@@@std@@@2@@Z; std::ranges::_Copy_fn::operator()<std::span<uchar const,-1>,std::back_insert_iterator<std::vector<uchar>>>(std::span<uchar const,-1> &&,std::back_insert_iterator<std::vector<uchar>>)
0x180039eea  add     r12w, di
0x180039eee  add     rbx, 160h
0x180039ef5  jmp     loc_180039D98
0x180039efa  xor     r12d, r12d
0x180039efd  mov     dil, r12b
0x180039f00  movzx   ebx, byte ptr [rsp+218h+Data]
0x180039f08  sar     r14, 5
0x180039f0c  mov     r13, 2E8BA2E8BA2E8BA3h
0x180039f16  imul    r14, r13
0x180039f1a  sar     r15, 5
0x180039f1e  imul    r15, r13
0x180039f22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180039f29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180039f2e  test    al, al
0x180039f30  jz      loc_18003A03B
0x180039f36  call    ?get@?$static_lazy@VFidoRestrictedCoreProvider@@@details@wil@@QEAAPEAVFidoRestrictedCoreProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoRestrictedCoreProvider>::get(void (*)(void))
0x180039f3b  mov     r8, [rax+10h]
0x180039f3f  mov     eax, [r8]
0x180039f42  cmp     eax, 5
0x180039f45  jbe     loc_18003A147
0x180039f4b  mov     rdx, 800000000000h
0x180039f55  mov     rcx, r8
0x180039f58  call    _tlgKeywordOn
0x180039f5d  test    al, al
0x180039f5f  jz      loc_18003A147
0x180039f65  mov     rcx, [rsp+218h+var_148]
0x180039f6d  mov     [rsp+218h+var_180], rcx
0x180039f75  movzx   eax, word ptr [rsp+218h+var_148+8]
0x180039f7d  sub     ax, cx
0x180039f80  movzx   eax, ax
0x180039f83  mov     dword ptr [rsp+218h+var_178], eax
0x180039f8a  mov     [rsp+218h+var_1A8], dil
0x180039f8f  mov     [rsp+218h+var_1A7], r12b
0x180039f94  mov     [rsp+218h+var_1A0], r14d
0x180039f99  mov     [rsp+218h+var_188], r15d
0x180039fa1  mov     [rsp+218h+var_184], r12d
0x180039fa9  mov     dword ptr [rsp+218h+Data], r12d
0x180039fb1  mov     [rsp+218h+var_118], rbx
0x180039fb9  mov     [rsp+218h+var_108], 1000000h
0x180039fc5  lea     rax, [rsp+218h+var_180]
0x180039fcd  mov     [rsp+218h+var_1B8], rax
0x180039fd2  lea     rax, [rsp+218h+var_1A8]
0x180039fd7  mov     [rsp+218h+var_1C0], rax
0x180039fdc  lea     rax, [rsp+218h+var_1A7]
0x180039fe1  mov     [rsp+218h+var_1C8], rax
0x180039fe6  lea     rax, [rsp+218h+var_1A0]
0x180039feb  mov     [rsp+218h+var_1D0], rax
0x180039ff0  lea     rax, [rsp+218h+var_188]
0x180039ff8  mov     [rsp+218h+var_1D8], rax
0x180039ffd  lea     rax, [rsp+218h+var_184]
0x18003a005  mov     [rsp+218h+var_1E0], rax
0x18003a00a  lea     rax, [rsp+218h+Data]
0x18003a012  mov     [rsp+218h+var_1E8], rax
0x18003a017  lea     rax, [rsp+218h+var_118]
0x18003a01f  mov     qword ptr [rsp+218h+cbData], rax
0x18003a024  lea     rax, [rsp+218h+var_108]
0x18003a02c  lea     rdx, unk_180186898
0x18003a033  mov     rcx, r8
0x18003a036  jmp     loc_18003A13D
0x18003a03b  mov     eax, cs:dword_1801AB148
0x18003a041  cmp     eax, 5
0x18003a044  jbe     loc_18003A147
0x18003a04a  mov     rdx, 800000000000h
0x18003a054  lea     rcx, dword_1801AB148
0x18003a05b  call    _tlgKeywordOn
0x18003a060  test    al, al
0x18003a062  jz      loc_18003A147
0x18003a068  mov     rcx, [rsp+218h+var_148]
0x18003a070  mov     [rsp+218h+var_180], rcx
0x18003a078  movzx   eax, word ptr [rsp+218h+var_148+8]
0x18003a080  sub     ax, cx
0x18003a083  movzx   eax, ax
0x18003a086  mov     dword ptr [rsp+218h+var_178], eax
0x18003a08d  mov     [rsp+218h+var_1A7], dil
0x18003a092  mov     [rsp+218h+var_1A8], r12b
0x18003a097  mov     dword ptr [rsp+218h+Data], r14d
0x18003a09f  mov     [rsp+218h+var_184], r15d
0x18003a0a7  mov     [rsp+218h+var_188], r12d
0x18003a0af  mov     [rsp+218h+var_1A0], r12d
0x18003a0b4  mov     [rsp+218h+var_108], rbx
0x18003a0bc  mov     [rsp+218h+var_118], 1000000h
0x18003a0c8  lea     rax, [rsp+218h+var_180]
  ... truncated ...
```
