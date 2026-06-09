# Windows::Networking::UX::Internal::WlanInterface::OnAcmConnectionComplete(_L2_NOTIFICATION_DATA const *)

- ea: `0x180041c70`
- end: `0x1800422ff`
- name: `?OnAcmConnectionComplete@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEBU_L2_NOTIFICATION_DATA@@@Z`
- size: `1679`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, const struct _L2_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800248a8`

## callees

- `0x180003ed0`
- `0x1800043bc`
- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x180012178`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001b230`
- `0x18001d3a4`
- `0x18001d4d4`
- `0x180023738`
- `0x1800289dc`
- `0x1800359ac`
- `0x180036e3c`
- `0x18003a174`
- `0x180041c70`
- `0x18004850c`
- `0x1800486c8`
- `0x180049498`
- `0x180049b10`
- `0x18004a9a8`
- `0x18004aa68`
- `0x18004b098`
- `0x18004b898`
- `0x18004d20c`
- `0x18004da20`
- `0x180066ec0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004221e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004221e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::OnAcmConnectionComplete(
        Windows::Networking::UX::Internal::WlanInterface *this,
        const struct _L2_NOTIFICATION_DATA *a2)
{
  int CurrentConnection; // ebx
  unsigned int *pData; // r14
  __int64 v6; // rdx
  Windows::Networking::UX::Internal::WlanInterface *v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  HSTRING *v17; // rdi
  __int64 (__fastcall *v18)(HSTRING *, GUID *, __int64 *); // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // eax
  int v22; // eax
  struct Windows::Networking::UX::IUserInputType *v23; // rax
  unsigned int v24; // eax
  HSTRING *v25; // rax
  HSTRING *v26; // rdi
  unsigned int v27; // ecx
  Windows::Networking::UX::Internal::WlanInterface *v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  struct _GUID *v34; // r9
  void *v35; // rcx
  char IsEnabled; // al
  unsigned int v37; // ecx
  const unsigned __int16 *v38; // r8
  int v40; // [rsp+20h] [rbp-49h]
  char v41[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v42; // [rsp+38h] [rbp-31h] BYREF
  HSTRING *v43; // [rsp+40h] [rbp-29h] BYREF
  struct Windows::Networking::UX::IUserInputType *v44; // [rsp+48h] [rbp-21h] BYREF
  struct _GUID v45; // [rsp+50h] [rbp-19h] BYREF
  char v46[8]; // [rsp+60h] [rbp-9h] BYREF
  char v47[8]; // [rsp+68h] [rbp-1h] BYREF
  struct _GUID v48; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  if ( a2->dwDataSize < 0x23C )
  {
    CurrentConnection = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62A,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)0x8000FFFFLL,
      v40);
    return (unsigned int)CurrentConnection;
  }
  wil::EnterCriticalSection(v47, (char *)this + 1304);
  pData = (unsigned int *)a2->pData;
  if ( pData && a2->dwDataSize >= 0x238 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, pData[140]);
    wil::EnterCriticalSection(v46, (char *)this + 752);
    if ( !*((_QWORD *)this + 99) )
    {
      *((_BYTE *)this + 34) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, pData[140]);
      LOBYTE(v6) = v41[0];
      CurrentConnection = Windows::Networking::UX::Internal::WlanInterface::_QueryCurrentConnection(this, v6);
      if ( CurrentConnection >= 0 )
        Windows::Networking::UX::Internal::WlanInterface::_UpdateConnectedNetwork((__int64)this, v32, v33, v34);
      Windows::Networking::UX::Internal::WlanMediaManager::FireCategoryEvent(
        *((_QWORD *)this + 2),
        2,
        (char *)this + 1204);
      goto LABEL_70;
    }
    v8 = pData[140];
    if ( !v8 )
    {
      v48 = 0;
      CurrentConnection = Windows::Networking::UX::Internal::WlanInterface::_GetSignatureForAcmNotification(
                            v7,
                            (const struct _WLAN_CONNECTION_NOTIFICATION_DATA *)pData,
                            &a2->InterfaceGuid,
                            &v48);
      if ( CurrentConnection >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
        v43 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43, v9, v10);
        v45 = v48;
        CurrentConnection = Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(
                              this,
                              v11,
                              &v45,
                              &v43);
        if ( CurrentConnection == -2147023728 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v43,
            v12,
            v13);
          CurrentConnection = Windows::Networking::UX::Internal::WlanInterface::_GetHiddenAvailableNetworkByProfileName(
                                (__int64)this,
                                v14,
                                (char *)pData + 4,
                                &v43);
          v42 = 0;
          if ( CurrentConnection >= 0
            && (int)Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v43,
                      (__int64)&v42,
                      v16) >= 0
            && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v42 + 128LL))(v42) )
          {
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 120LL))(v42, pData + 129);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v42,
            v15,
            v16);
        }
        if ( CurrentConnection >= 0 )
        {
          v41[0] = 0;
          CurrentConnection = (*((__int64 (__fastcall **)(HSTRING *, char *))*v43 + 17))(v43, v41);
          if ( CurrentConnection >= 0 )
          {
            if ( v41[0] )
              goto LABEL_32;
            v42 = 0;
            v17 = v43;
            v18 = *(__int64 (__fastcall **)(HSTRING *, GUID *, __int64 *))*v43;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v42,
              v12,
              v13);
            CurrentConnection = v18(v17, &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494, &v42);
            if ( CurrentConnection >= 0 )
            {
              v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 232LL))(v42, pData + 1);
              if ( v21 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x655,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
                  (const char *)(unsigned int)v21,
                  v40);
              v22 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 240LL))(v42, pData + 1);
              if ( v22 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x656,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
                  (const char *)(unsigned int)v22,
                  v40);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v42,
              v19,
              v20);
            if ( CurrentConnection >= 0 )
            {
LABEL_32:
              v23 = (struct Windows::Networking::UX::IUserInputType *)operator new(
                                                                        0x10u,
                                                                        (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)&v45.Data1 = v23;
              if ( v23 )
              {
                *((_DWORD *)v23 + 2) = 2;
                *(_QWORD *)v23 = &Windows::Networking::UX::Internal::WlanL3LocalConnectionEvent::`vftable';
                v42 = 0;
                v44 = v23;
                v24 = Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(*((_QWORD *)this + 99), &v44);
                CurrentConnection = v24;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    133,
                    &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
                    v24);
              }
              else
              {
                v42 = 0;
                CurrentConnection = -2147024882;
              }
              std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>(&v42);
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43, v12, v13);
      }
      goto LABEL_70;
    }
    CurrentConnection = 0;
    if ( *((_BYTE *)this + 37) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
      *((_BYTE *)this + 37) = 0;
      goto LABEL_70;
    }
    if ( *((_BYTE *)this + 36) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
      *((_BYTE *)this + 36) = 0;
      if ( pData[140] == 229377 )
      {
        v44 = 0;
        *(_QWORD *)&v45.Data1 = 0;
        LODWORD(v42) = 1;
        LODWORD(v43) = -2147023673;
        CurrentConnection = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CConnectionCompletionUIPrompt,Windows::Networking::UX::IUserInputType,long,enum Windows::Networking::UX::ConnectionCompletionReason,std::nullptr_t>(
                              (__int64)&v44,
                              (__int64)&v43,
                              (__int64)&v42,
                              (__int64)&v45);
        if ( CurrentConnection >= 0 )
          Windows::Networking::UX::Internal::WlanInterface::_PostUIPrompt(this, v44, (const struct _GUID *)this + 44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44, v30, v31);
      }
      goto LABEL_70;
    }
    if ( v8 == 229377 )
    {
      if ( *((_BYTE *)this + 39) )
      {
LABEL_56:
        *((_BYTE *)this + 34) = 0;
LABEL_70:
        *((_BYTE *)this + 33) = 0;
        v35 = (void *)*((_QWORD *)this + 92);
        *((_QWORD *)this + 92) = 0;
        if ( v35 )
          CoTaskMemFree(v35);
        *((_QWORD *)this + 93) = 0;
        *((GUID *)this + 45) = GUID_NULL;
        if ( *((_QWORD *)this + 172) != *(_QWORD *)&GUID_NULL.Data1
          || *((_QWORD *)this + 173) != *(_QWORD *)GUID_NULL.Data4 )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::GetImpl'::`2'::impl);
          v37 = pData[140];
          v38 = (const unsigned __int16 *)(pData + 1);
          if ( IsEnabled )
            Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(this, v37, v38);
          else
            Windows::Networking::UX::Internal::WlanInterface::_CompleteAddNetworkWiFiUriTipTest(this, v37 == 0, v38);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v46);
        goto LABEL_79;
      }
      *((_BYTE *)this + 39) = 1;
    }
    v25 = (HSTRING *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v26 = v25;
    *(_QWORD *)&v45.Data1 = v25;
    if ( v25 )
    {
      v27 = pData[140];
      *((_DWORD *)v25 + 2) = 3;
      *v25 = (HSTRING)&Windows::Networking::UX::Internal::WlanL2FailedEvent::`vftable';
      v25[2] = (HSTRING)v27;
      v25[3] = 0;
      v43 = v25;
      if ( pData[141] == 0x80000000 )
      {
        *((_DWORD *)v25 + 5) = pData[140];
        WindowsDeleteString(v25[3]);
        v26[3] = 0;
        Windows::Networking::UX::Internal::WlanInterface::_GetWlanNotificationProfileXml(v28, a2, v26 + 3);
      }
      v43 = 0;
      v44 = (struct Windows::Networking::UX::IUserInputType *)v26;
      v29 = Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(*((_QWORD *)this + 99), &v44);
      CurrentConnection = v29;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          pData[140],
          v29);
    }
    else
    {
      v43 = 0;
      CurrentConnection = -2147024882;
    }
    std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v43);
    goto LABEL_56;
  }
  CurrentConnection = -2147024883;
LABEL_79:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      138,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)CurrentConnection);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v47);
  return (unsigned int)CurrentConnection;
}

```

## disassembly

```asm
0x180041c70  mov     [rsp-8+arg_10], rbx
0x180041c75  push    rbp
0x180041c76  push    rsi
0x180041c77  push    rdi
0x180041c78  push    r12
0x180041c7a  push    r13
0x180041c7c  push    r14
0x180041c7e  push    r15
0x180041c80  lea     rbp, [rsp-27h]
0x180041c85  sub     rsp, 90h
0x180041c8c  mov     rax, cs:__security_cookie
0x180041c93  xor     rax, rsp
0x180041c96  mov     [rbp+57h+var_40], rax
0x180041c9a  mov     r15, rdx
0x180041c9d  mov     rsi, rcx
0x180041ca0  lea     r13, WPP_GLOBAL_Control
0x180041ca7  lea     rdi, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180041cae  mov     rcx, cs:WPP_GLOBAL_Control
0x180041cb5  cmp     rcx, r13
0x180041cb8  jz      short loc_180041CD1
0x180041cba  test    byte ptr [rcx+1Ch], 8
0x180041cbe  jz      short loc_180041CD1
0x180041cc0  mov     edx, 82h
0x180041cc5  mov     r8, rdi
0x180041cc8  mov     rcx, [rcx+10h]
0x180041ccc  call    WPP_SF_
0x180041cd1  cmp     dword ptr [r15+18h], 23Ch
0x180041cd9  jnb     short loc_180041CFD
0x180041cdb  mov     rcx, [rbp+5Fh]; this
0x180041cdf  mov     ebx, 8000FFFFh
0x180041ce4  mov     r9d, ebx; char *
0x180041ce7  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180041cee  mov     edx, 62Ah; void *
0x180041cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041cf8  jmp     loc_1800422D6
0x180041cfd  lea     rdx, [rsi+518h]
0x180041d04  lea     rcx, [rbp+57h+var_58]
0x180041d08  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180041d0d  nop
0x180041d0e  mov     r14, [r15+20h]
0x180041d12  xor     r12d, r12d
0x180041d15  test    r14, r14
0x180041d18  jz      loc_1800422A1
0x180041d1e  cmp     dword ptr [r15+18h], 238h
0x180041d26  jb      loc_1800422A1
0x180041d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d33  cmp     rcx, r13
0x180041d36  jz      short loc_180041D56
0x180041d38  test    byte ptr [rcx+1Ch], 8
0x180041d3c  jz      short loc_180041D56
0x180041d3e  mov     edx, 83h
0x180041d43  mov     r9d, [r14+230h]
0x180041d4a  mov     r8, rdi
0x180041d4d  mov     rcx, [rcx+10h]
0x180041d51  call    WPP_SF_d
0x180041d56  lea     rdx, [rsi+2F0h]
0x180041d5d  lea     rcx, [rbp+57h+var_60]
0x180041d61  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180041d66  nop
0x180041d67  cmp     [rsi+318h], r12
0x180041d6e  jz      loc_1800421A9
0x180041d74  mov     eax, [r14+230h]
0x180041d7b  test    eax, eax
0x180041d7d  jnz     loc_180041FE1
0x180041d83  xorps   xmm0, xmm0
0x180041d86  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180041d8a  lea     r8, [r15+8]; struct _GUID *
0x180041d8e  lea     r9, [rbp+57h+var_50]; struct _GUID *
0x180041d92  mov     rdx, r14; struct _WLAN_CONNECTION_NOTIFICATION_DATA *
0x180041d95  call    ?_GetSignatureForAcmNotification@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEBU_WLAN_CONNECTION_NOTIFICATION_DATA@@AEBU_GUID@@PEAU7@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetSignatureForAcmNotification(_WLAN_CONNECTION_NOTIFICATION_DATA const *,_GUID const &,_GUID *)
0x180041d9a  mov     ebx, eax
0x180041d9c  test    eax, eax
0x180041d9e  js      loc_180042205
0x180041da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180041dab  cmp     rcx, r13
0x180041dae  jz      short loc_180041DCB
0x180041db0  test    byte ptr [rcx+1Ch], 8
0x180041db4  jz      short loc_180041DCB
0x180041db6  mov     edx, 84h
0x180041dbb  lea     r9, [rbp+57h+var_50]
0x180041dbf  mov     r8, rdi
0x180041dc2  mov     rcx, [rcx+10h]
0x180041dc6  call    WPP_SF__guid_
0x180041dcb  mov     [rbp+57h+var_80], r12
0x180041dcf  lea     rcx, [rbp+57h+var_80]
0x180041dd3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041dd8  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x180041ddc  movdqa  [rbp+57h+var_70], xmm0
0x180041de1  lea     r9, [rbp+57h+var_80]
0x180041de5  lea     r8, [rbp+57h+var_70]
0x180041de9  mov     rcx, rsi
0x180041dec  call    ?_GetAvailableNetwork@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@U_GUID@@PEAPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetAvailableNetwork(wil::read_lock_required,_GUID,Windows::Networking::UX::IAvailableNetwork * *)
0x180041df1  mov     ebx, eax
0x180041df3  cmp     eax, 80070490h
0x180041df8  jnz     short loc_180041E66
0x180041dfa  lea     rcx, [rbp+57h+var_80]
0x180041dfe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041e03  lea     r8, [r14+4]
0x180041e07  lea     r9, [rbp+57h+var_80]
0x180041e0b  mov     rcx, rsi
0x180041e0e  call    ?_GetHiddenAvailableNetworkByProfileName@WlanInterface@Internal@UX@Networking@Windows@@IEAAJUread_lock_required@wil@@PEBGPEAPEAUIAvailableNetwork@345@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetHiddenAvailableNetworkByProfileName(wil::read_lock_required,ushort const *,Windows::Networking::UX::IAvailableNetwork * *)
0x180041e13  mov     ebx, eax
0x180041e15  mov     [rbp+57h+var_88], r12
0x180041e19  test    eax, eax
0x180041e1b  js      short loc_180041E5D
0x180041e1d  lea     rdx, [rbp+57h+var_88]
0x180041e21  lea     rcx, [rbp+57h+var_80]
0x180041e25  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x180041e2a  test    eax, eax
0x180041e2c  js      short loc_180041E5D
0x180041e2e  mov     rcx, [rbp+57h+var_88]
0x180041e32  mov     rax, [rcx]
0x180041e35  mov     rax, [rax+80h]
0x180041e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e41  test    al, al
0x180041e43  jz      short loc_180041E5D
0x180041e45  mov     rcx, [rbp+57h+var_88]
0x180041e49  mov     rax, [rcx]
0x180041e4c  lea     rdx, [r14+204h]
0x180041e53  mov     rax, [rax+78h]
0x180041e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e5c  nop
0x180041e5d  lea     rcx, [rbp+57h+var_88]
0x180041e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041e66  test    ebx, ebx
0x180041e68  js      loc_180041FD3
0x180041e6e  mov     [rbp+57h+var_90], r12b
0x180041e72  mov     rcx, [rbp+57h+var_80]
0x180041e76  mov     rax, [rcx]
0x180041e79  lea     rdx, [rbp+57h+var_90]
0x180041e7d  mov     rax, [rax+88h]
0x180041e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e89  mov     ebx, eax
0x180041e8b  test    eax, eax
0x180041e8d  js      loc_180041FD3
0x180041e93  cmp     [rbp+57h+var_90], r12b
0x180041e97  jnz     loc_180041F4F
0x180041e9d  mov     [rbp+57h+var_88], r12
0x180041ea1  mov     rdi, [rbp+57h+var_80]
0x180041ea5  mov     rax, [rdi]
0x180041ea8  mov     rbx, [rax]
0x180041eab  lea     rcx, [rbp+57h+var_88]
0x180041eaf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041eb4  lea     r8, [rbp+57h+var_88]
0x180041eb8  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x180041ebf  mov     rcx, rdi
0x180041ec2  mov     rax, rbx
0x180041ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041eca  mov     ebx, eax
0x180041ecc  test    eax, eax
0x180041ece  js      short loc_180041F37
0x180041ed0  mov     rcx, [rbp+57h+var_88]
0x180041ed4  mov     rax, [rcx]
0x180041ed7  lea     rdx, [r14+4]
0x180041edb  mov     rax, [rax+0E8h]
0x180041ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ee7  mov     rcx, [rbp+5Fh]; this
0x180041eeb  test    eax, eax
0x180041eed  jns     short loc_180041F03
0x180041eef  mov     r9d, eax; char *
0x180041ef2  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180041ef9  mov     edx, 655h; void *
0x180041efe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041f03  mov     rcx, [rbp+57h+var_88]
0x180041f07  mov     rax, [rcx]
0x180041f0a  lea     rdx, [r14+4]
0x180041f0e  mov     rax, [rax+0F0h]
0x180041f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f1a  mov     rcx, [rbp+5Fh]; this
0x180041f1e  test    eax, eax
0x180041f20  jns     short loc_180041F37
0x180041f22  mov     r9d, eax; char *
0x180041f25  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180041f2c  mov     edx, 656h; void *
0x180041f31  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041f36  nop
0x180041f37  lea     rcx, [rbp+57h+var_88]
0x180041f3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041f40  test    ebx, ebx
0x180041f42  js      loc_180041FD3
0x180041f48  lea     rdi, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180041f4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041f56  mov     ecx, 10h; unsigned __int64
0x180041f5b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180041f60  mov     qword ptr [rbp+57h+var_70], rax
0x180041f64  test    rax, rax
0x180041f67  jz      short loc_180041FC0
0x180041f69  mov     dword ptr [rax+8], 2
0x180041f70  lea     rcx, ??_7WlanL3LocalConnectionEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanL3LocalConnectionEvent::`vftable'
0x180041f77  mov     [rax], rcx
0x180041f7a  mov     [rbp+57h+var_88], rax
0x180041f7e  mov     [rbp+57h+var_88], r12
0x180041f82  mov     [rbp+57h+var_78], rax
0x180041f86  lea     rdx, [rbp+57h+var_78]
0x180041f8a  mov     rcx, [rsi+318h]
0x180041f91  call    ?PostMediaEvent@WlanStateMachine@Internal@UX@Networking@Windows@@UEAAJV?$unique_ptr@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>)
0x180041f96  mov     ebx, eax
0x180041f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f9f  cmp     rcx, r13
0x180041fa2  jz      short loc_180041FC9
0x180041fa4  test    byte ptr [rcx+1Ch], 8
0x180041fa8  jz      short loc_180041FC9
0x180041faa  mov     edx, 85h
0x180041faf  mov     r9d, eax
0x180041fb2  mov     r8, rdi
0x180041fb5  mov     rcx, [rcx+10h]
0x180041fb9  call    WPP_SF_d
0x180041fbe  jmp     short loc_180041FC9
0x180041fc0  mov     [rbp+57h+var_88], r12
0x180041fc4  mov     ebx, 8007000Eh
0x180041fc9  lea     rcx, [rbp+57h+var_88]
0x180041fcd  call    ??1?$unique_ptr@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>(void)
0x180041fd2  nop
0x180041fd3  lea     rcx, [rbp+57h+var_80]
0x180041fd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041fdc  jmp     loc_180042205
0x180041fe1  mov     ebx, r12d
0x180041fe4  cmp     [rsi+25h], r12b
0x180041fe8  jz      short loc_180042016
0x180041fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ff1  cmp     rcx, r13
0x180041ff4  jz      short loc_18004200D
0x180041ff6  test    byte ptr [rcx+1Ch], 4
0x180041ffa  jz      short loc_18004200D
0x180041ffc  mov     edx, 86h
0x180042001  mov     r8, rdi
0x180042004  mov     rcx, [rcx+10h]
0x180042008  call    WPP_SF_
0x18004200d  mov     [rsi+25h], r12b
0x180042011  jmp     loc_180042205
0x180042016  cmp     [rsi+24h], r12b
0x18004201a  jnz     loc_180042121
0x180042020  cmp     eax, 38001h
0x180042025  jnz     short loc_180042035
0x180042027  cmp     [rsi+27h], r12b
0x18004202b  jnz     loc_180042118
0x180042031  mov     byte ptr [rsi+27h], 1
0x180042035  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004203c  mov     ecx, 20h ; ' '; unsigned __int64
0x180042041  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180042046  mov     rdi, rax
0x180042049  mov     qword ptr [rbp+57h+var_70], rax
0x18004204d  test    rax, rax
0x180042050  jz      loc_180042106
0x180042056  mov     ecx, [r14+230h]
0x18004205d  mov     dword ptr [rax+8], 3
0x180042064  lea     rax, ??_7WlanL2FailedEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanL2FailedEvent::`vftable'
0x18004206b  mov     [rdi], rax
0x18004206e  mov     [rdi+10h], ecx
0x180042071  mov     [rdi+14h], r12d
0x180042075  mov     [rdi+18h], r12
0x180042079  mov     [rbp+57h+var_80], rdi
0x18004207d  test    rdi, rdi
0x180042080  jz      loc_18004210A
0x180042086  cmp     dword ptr [r14+234h], 80000000h
0x180042091  jnz     short loc_1800420B8
0x180042093  mov     eax, [r14+230h]
0x18004209a  mov     [rdi+14h], eax
0x18004209d  lea     rbx, [rdi+18h]
0x1800420a1  mov     rcx, [rbx]; string
0x1800420a4  call    cs:__imp_WindowsDeleteString
0x1800420aa  mov     [rbx], r12
0x1800420ad  mov     r8, rbx; HSTRING *
0x1800420b0  mov     rdx, r15; struct _L2_NOTIFICATION_DATA *
0x1800420b3  call    ?_GetWlanNotificationProfileXml@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEBU_L2_NOTIFICATION_DATA@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WlanInterface::_GetWlanNotificationProfileXml(_L2_NOTIFICATION_DATA const *,HSTRING__ * *)
0x1800420b8  mov     [rbp+57h+var_80], r12
0x1800420bc  mov     [rbp+57h+var_78], rdi
0x1800420c0  lea     rdx, [rbp+57h+var_78]
0x1800420c4  mov     rcx, [rsi+318h]
0x1800420cb  call    ?PostMediaEvent@WlanStateMachine@Internal@UX@Networking@Windows@@UEAAJV?$unique_ptr@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>)
0x1800420d0  mov     ebx, eax
0x1800420d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420d9  cmp     rcx, r13
0x1800420dc  jz      short loc_18004210F
0x1800420de  test    byte ptr [rcx+1Ch], 8
0x1800420e2  jz      short loc_18004210F
0x1800420e4  mov     edx, 87h
0x1800420e9  mov     [rsp+0C0h+var_A0], eax
0x1800420ed  mov     r9d, [r14+230h]
0x1800420f4  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x1800420fb  mov     rcx, [rcx+10h]
0x1800420ff  call    WPP_SF_Dd
0x180042104  jmp     short loc_18004210F
0x180042106  mov     [rbp+57h+var_80], r12
0x18004210a  mov     ebx, 8007000Eh
0x18004210f  lea     rcx, [rbp+57h+var_80]
0x180042113  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x180042118  mov     [rsi+22h], r12b
0x18004211c  jmp     loc_180042205
0x180042121  mov     rcx, cs:WPP_GLOBAL_Control
0x180042128  cmp     rcx, r13
0x18004212b  jz      short loc_180042144
0x18004212d  test    byte ptr [rcx+1Ch], 8
0x180042131  jz      short loc_180042144
0x180042133  mov     edx, 88h
0x180042138  mov     r8, rdi
0x18004213b  mov     rcx, [rcx+10h]
0x18004213f  call    WPP_SF_
0x180042144  mov     [rsi+24h], r12b
0x180042148  cmp     dword ptr [r14+230h], 38001h
  ... truncated ...
```
