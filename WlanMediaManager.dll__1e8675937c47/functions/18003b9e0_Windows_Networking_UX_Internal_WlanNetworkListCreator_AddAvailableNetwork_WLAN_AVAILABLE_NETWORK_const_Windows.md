# Windows::Networking::UX::Internal::WlanNetworkListCreator::AddAvailableNetwork(_WLAN_AVAILABLE_NETWORK const *,Windows::Networking::UX::ProfileType,_GUID const &,std::optional<Windows::Networking::UX::Internal::WlanHotspotMetadata>)

- ea: `0x18003b9e0`
- end: `0x18003c079`
- name: `?AddAvailableNetwork@WlanNetworkListCreator@Internal@UX@Networking@Windows@@UEAAJPEBU_WLAN_AVAILABLE_NETWORK@@W4ProfileType@345@AEBU_GUID@@V?$optional@UWlanHotspotMetadata@Internal@UX@Networking@Windows@@@std@@@Z`
- size: `1689`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b980`
- `0x18003c080`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x18000de4c`
- `0x1800121e8`
- `0x1800141a0`
- `0x180014ff8`
- `0x18001b230`
- `0x18001d4d4`
- `0x1800359ac`
- `0x1800359fc`
- `0x18003719c`
- `0x18003ab80`
- `0x18003b9e0`
- `0x180040d28`
- `0x18004ad38`
- `0x180051ea0`
- `0x180058ed0`
- `0x18005adb0`
- `0x1800740dc`
- `0x1800746b8`
- `0x180075638`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bbfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bd1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bb81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bbfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bd1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd85`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetworkListCreator::AddAvailableNetwork(
        __int64 a1,
        const struct _WLAN_AVAILABLE_NETWORK *a2,
        unsigned int ProfileType,
        const struct _GUID *a4,
        __int64 a5)
{
  int v9; // eax
  HRESULT ProfileName; // ebx
  Windows::Networking::UX::Internal::WlanNetwork *v11; // rcx
  Windows::Networking::UX::Internal::WlanNetwork *v12; // rbx
  char v13; // r13
  __int64 v14; // rdx
  __int64 v15; // r8
  Windows::Networking::UX::Internal::WlanNetwork *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  Windows::Networking::UX::Internal::WlanNetwork *v19; // rbx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64); // rdi
  __int64 v22; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  bool IsWritable; // si
  __int64 v27; // rdi
  PCWSTR v28; // rbx
  __int64 v29; // rdx
  Windows::Networking::UX::Internal::Profile *CachedProfile; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  char v33; // r15
  char v34; // r12
  __int64 v35; // r8
  bool v36; // si
  __int64 v37; // rdx
  int v38; // ebx
  __int64 v39; // r8
  PCWSTR v40; // rax
  int v41; // r8d
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v46; // rdx
  int v47; // ebx
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, GUID *, _QWORD); // rbx
  int v50; // ebx
  bool v51; // bl
  __int64 v52; // rcx
  __int64 v53; // rcx
  Windows::Networking::UX::Internal::WlanNetwork *v54; // rax
  PCWSTR v55; // rax
  int v56; // r8d
  int v57; // [rsp+20h] [rbp-81h]
  char v58[8]; // [rsp+40h] [rbp-61h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-59h] BYREF
  HSTRING string; // [rsp+50h] [rbp-51h] BYREF
  Windows::Networking::UX::Internal::WlanNetwork *v61; // [rsp+58h] [rbp-49h] BYREF
  HSTRING newString; // [rsp+60h] [rbp-41h] BYREF
  GUID v63; // [rsp+70h] [rbp-31h] BYREF
  GUID v64; // [rsp+80h] [rbp-21h] BYREF
  GUID v65; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v61 = 0;
  Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::WlanNetwork>::InternalRelease(&v61);
  v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::WlanNetwork,Windows::Networking::UX::Internal::WlanNetwork,_GUID const &>(
         &v61,
         a4);
  ProfileName = v9;
  if ( v9 >= 0 )
  {
    ProfileName = Windows::Networking::UX::Internal::WlanNetwork::InitializeFromAvailableNetwork(v61, a2, a4);
    if ( ProfileName < 0 )
      goto LABEL_37;
    v11 = v61;
    *(_OWORD *)((char *)v61 + 280) = *(_OWORD *)a5;
    *((_QWORD *)v11 + 37) = *(_QWORD *)(a5 + 16);
    v64 = 0;
    v65 = GUID_NULL;
    newString = 0;
    v12 = v61;
    v64 = (GUID)*((_OWORD *)v61 + 1);
    v13 = *((_BYTE *)v61 + 64);
    WindowsDeleteString(0);
    newString = 0;
    ProfileName = WindowsDuplicateString(*((HSTRING *)v12 + 6), &newString);
    if ( ProfileName < 0 )
      goto LABEL_36;
    v59 = 0;
    v16 = v61;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59, v14, v15);
    ProfileName = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::AvailableNetworkBase,Windows::Networking::UX::Internal::IWlanAvailableNetwork,Windows::Networking::UX::IWiFiAvailableNetwork>>(
                    v16,
                    &GUID_ac2798f8_4bd2_4d64_be61_7002641cd494,
                    &v59);
    if ( ProfileName >= 0 && v13 )
    {
      string = 0;
      v19 = v61;
      WindowsDeleteString(0);
      string = 0;
      ProfileName = Windows::Networking::UX::Internal::WlanNetwork::get_ProfileName(v19, &string);
      if ( ProfileName >= 0 )
      {
        v20 = v59;
        v21 = (*v59)[24];
        v22 = *(_QWORD *)(a1 + 32);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        LOBYTE(v24) = Windows::Networking::UX::Internal::ProfileManager::IsProfileAutoConnect(
                        (Windows::Networking::UX::Internal::ProfileManager *)(v22 + 656),
                        a4,
                        StringRawBuffer);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))v21)(v20, v24);
        if ( ProfileType == 5 )
        {
          ProfileType = *((_DWORD *)v61 + 47);
          if ( ProfileType == 5 )
            ProfileType = Windows::Networking::UX::Internal::WlanClient::GetProfileType(
                            *(_QWORD *)(a1 + 32),
                            a4,
                            string);
        }
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), _QWORD))(*v59)[27])(v59, ProfileType);
        IsWritable = 0;
        if ( ProfileType - 10 > 1 )
        {
          v27 = *(_QWORD *)(a1 + 32);
          v28 = WindowsGetStringRawBuffer(string, 0);
          wil::EnterCriticalSection(&v63, v27 + 664);
          CachedProfile = (Windows::Networking::UX::Internal::Profile *)Windows::Networking::UX::Internal::ProfileManager::FindCachedProfile(
                                                                          v27 + 656,
                                                                          v29,
                                                                          a4,
                                                                          v28);
          if ( CachedProfile )
            IsWritable = Windows::Networking::UX::Internal::Profile::IsWritable(CachedProfile);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v63);
        }
        LOBYTE(v25) = IsWritable;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64))(*v59)[25])(v59, v25);
        ProfileName = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), GUID *))(*v59)[13])(
                        v59,
                        &v65);
      }
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59, v17, v18);
    if ( ProfileName < 0 )
    {
LABEL_36:
      WindowsDeleteString(newString);
      goto LABEL_37;
    }
    v59 = 0;
    v33 = *((_BYTE *)v61 + 184);
    v34 = *((_BYTE *)v61 + 60);
    if ( v33 )
    {
      v31 = v34 ? *(_QWORD *)(a1 + 64) : *(_QWORD *)(a1 + 72);
      if ( v31 )
      {
        Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::operator=(&v59);
        v36 = 0;
        goto LABEL_27;
      }
    }
    v36 = 0;
    LODWORD(string) = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59, v31, v32);
    v47 = Windows::Networking::UX::Internal::_LookupNetworkMapAndList(
            *(_QWORD *)(a1 + 48),
            *(_QWORD *)(a1 + 40),
            (unsigned int)&v64,
            (unsigned int)&v59,
            (__int64)&string);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        285,
        &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
        (unsigned int)v47);
    if ( v47 >= 0 )
    {
      v51 = 1;
      if ( !v13 )
        goto LABEL_27;
    }
    else
    {
      if ( !v13 )
      {
        if ( !v33 )
        {
          v48 = *(_QWORD *)(a1 + 56);
          v49 = *(__int64 (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v48 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v59,
            v46,
            v35);
          v63 = v64;
          v50 = v49(v48, &v63, &v59);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              286,
              &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
              (unsigned int)v50);
          if ( v50 >= 0 )
            goto LABEL_27;
        }
LABEL_55:
        v38 = (*(__int64 (__fastcall **)(_QWORD, Windows::Networking::UX::Internal::WlanNetwork *))(**(_QWORD **)(a1 + 40)
                                                                                                  + 104LL))(
                *(_QWORD *)(a1 + 40),
                v61);
        if ( v38 >= 0 )
        {
          v58[0] = 0;
          LODWORD(string) = 0;
          v38 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)(a1 + 40) + 56LL))(
                  *(_QWORD *)(a1 + 40),
                  &string);
          if ( v38 < 0
            || (v53 = *(_QWORD *)(a1 + 48),
                v63 = v64,
                v38 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, char *))(*(_QWORD *)v53 + 80LL))(
                        v53,
                        &v63,
                        (unsigned int)((_DWORD)string - 1),
                        v58),
                v38 < 0) )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 112LL))(*(_QWORD *)(a1 + 40));
          }
          else
          {
            v54 = v61;
            if ( v33 )
            {
              if ( v34 )
              {
                if ( !*(_QWORD *)(a1 + 64) )
                  *(_QWORD *)(a1 + 64) = v61;
              }
              else if ( !*(_QWORD *)(a1 + 72) )
              {
                *(_QWORD *)(a1 + 72) = v61;
              }
            }
            ++*(_DWORD *)(a1 + 80);
            if ( v13 )
            {
              ++*(_DWORD *)(a1 + 84);
            }
            else if ( *((_BYTE *)v54 + 63) )
            {
              if ( v34 )
                ++*(_DWORD *)(a1 + 92);
              else
                ++*(_DWORD *)(a1 + 96);
            }
            else
            {
              ++*(_DWORD *)(a1 + 100);
            }
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v55 = WindowsGetStringRawBuffer(newString, 0);
          WPP_SF__guid_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, v56, (unsigned int)&v64, (__int64)v55, v13, v38);
        }
        goto LABEL_32;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59, v46, v35);
      v51 = (int)Windows::Networking::UX::Internal::_LookupNetworkMapAndList(
                   *(_QWORD *)(a1 + 48),
                   *(_QWORD *)(a1 + 40),
                   (unsigned int)&v65,
                   (unsigned int)&v59,
                   (__int64)&string) >= 0;
    }
    v58[0] = 0;
    v52 = *(_QWORD *)(a1 + 56);
    v63 = v65;
    v36 = (*(int (__fastcall **)(__int64, GUID *, Windows::Networking::UX::Internal::WlanNetwork *, char *))(*(_QWORD *)v52 + 80LL))(
            v52,
            &v63,
            v61,
            v58) >= 0;
    if ( !v51 )
      goto LABEL_55;
LABEL_27:
    string = 0;
    v38 = Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(
            &v59,
            (__int64)&string,
            v35);
    if ( v38 >= 0 )
    {
      v38 = (*(__int64 (__fastcall **)(HSTRING, Windows::Networking::UX::Internal::WlanNetwork *))(*(_QWORD *)string
                                                                                                 + 176LL))(
              string,
              v61);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v40 = WindowsGetStringRawBuffer(newString, 0);
        WPP_SF__guid_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, v41, (unsigned int)&v64, (__int64)v40, v13, v38);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string, v37, v39);
LABEL_32:
    if ( v38 < 0 && v36 )
    {
      v44 = *(_QWORD *)(a1 + 56);
      v63 = v65;
      (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v44 + 88LL))(v44, &v63);
    }
    ProfileName = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59, v42, v43);
    goto LABEL_36;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xF7A,
    (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
    (const char *)(unsigned int)v9,
    v57);
LABEL_37:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      289,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)ProfileName);
  Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::WlanNetwork>::InternalRelease(&v61);
  return (unsigned int)ProfileName;
}

```

## disassembly

```asm
0x18003b9e0  push    rbp
0x18003b9e2  push    rbx
0x18003b9e3  push    rsi
0x18003b9e4  push    rdi
0x18003b9e5  push    r12
0x18003b9e7  push    r13
0x18003b9e9  push    r14
0x18003b9eb  push    r15
0x18003b9ed  lea     rbp, [rsp-17h]
0x18003b9f2  sub     rsp, 0B8h
0x18003b9f9  mov     rax, cs:__security_cookie
0x18003ba00  xor     rax, rsp
0x18003ba03  mov     [rbp+4Fh+var_50], rax
0x18003ba07  mov     r12, r9
0x18003ba0a  mov     r15d, r8d
0x18003ba0d  mov     rdi, rdx
0x18003ba10  mov     r14, rcx
0x18003ba13  lea     rax, WPP_GLOBAL_Control
0x18003ba1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba21  cmp     rcx, rax
0x18003ba24  jz      short loc_18003BA41
0x18003ba26  test    byte ptr [rcx+1Ch], 40h
0x18003ba2a  jz      short loc_18003BA41
0x18003ba2c  mov     edx, 11Ch
0x18003ba31  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003ba38  mov     rcx, [rcx+10h]
0x18003ba3c  call    WPP_SF_
0x18003ba41  mov     [rbp+4Fh+var_98], 0
0x18003ba49  lea     rcx, [rbp+4Fh+var_98]
0x18003ba4d  call    ?InternalRelease@?$ComPtr@VWlanNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::WlanNetwork>::InternalRelease(void)
0x18003ba52  mov     rdx, r12
0x18003ba55  lea     rcx, [rbp+4Fh+var_98]
0x18003ba59  call    ??$MakeAndInitialize@VWlanNetwork@Internal@UX@Networking@Windows@@V12345@AEBU_GUID@@@Details@WRL@Microsoft@@YAJPEAPEAVWlanNetwork@Internal@UX@Networking@Windows@@AEBU_GUID@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::WlanNetwork,Windows::Networking::UX::Internal::WlanNetwork,_GUID const &>(Windows::Networking::UX::Internal::WlanNetwork * *,_GUID const &)
0x18003ba5e  mov     ebx, eax
0x18003ba60  test    eax, eax
0x18003ba62  jns     short loc_18003BA81
0x18003ba64  mov     rcx, [rbp+57h]; this
0x18003ba68  mov     r9d, eax; char *
0x18003ba6b  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18003ba72  mov     edx, 0F7Ah; void *
0x18003ba77  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ba7c  jmp     loc_18003BD8B
0x18003ba81  mov     r8, r12; struct _GUID *
0x18003ba84  mov     rdx, rdi; struct _WLAN_AVAILABLE_NETWORK *
0x18003ba87  mov     rcx, [rbp+4Fh+var_98]; this
0x18003ba8b  call    ?InitializeFromAvailableNetwork@WlanNetwork@Internal@UX@Networking@Windows@@QEAAJPEBU_WLAN_AVAILABLE_NETWORK@@AEBU_GUID@@@Z; Windows::Networking::UX::Internal::WlanNetwork::InitializeFromAvailableNetwork(_WLAN_AVAILABLE_NETWORK const *,_GUID const &)
0x18003ba90  mov     ebx, eax
0x18003ba92  xor     edi, edi
0x18003ba94  test    eax, eax
0x18003ba96  js      loc_18003BD8B
0x18003ba9c  mov     rcx, [rbp+4Fh+var_98]
0x18003baa0  mov     rax, [rbp+4Fh+arg_20]
0x18003baa4  movups  xmm0, xmmword ptr [rax]
0x18003baa7  movups  xmmword ptr [rcx+118h], xmm0
0x18003baae  movsd   xmm1, qword ptr [rax+10h]
0x18003bab3  movsd   qword ptr [rcx+128h], xmm1
0x18003babb  xorps   xmm0, xmm0
0x18003babe  movups  [rbp+4Fh+var_70], xmm0
0x18003bac2  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18003bac9  movdqu  [rbp+4Fh+var_60], xmm1
0x18003bace  mov     [rbp+4Fh+newString], rdi
0x18003bad2  mov     rbx, [rbp+4Fh+var_98]
0x18003bad6  movups  xmm0, xmmword ptr [rbx+10h]
0x18003bada  movdqu  [rbp+4Fh+var_70], xmm0
0x18003badf  movzx   r13d, byte ptr [rbx+40h]
0x18003bae4  xor     ecx, ecx; string
0x18003bae6  call    cs:__imp_WindowsDeleteString
0x18003baec  mov     [rbp+4Fh+newString], rdi
0x18003baf0  lea     rdx, [rbp+4Fh+newString]; newString
0x18003baf4  mov     rcx, [rbx+30h]; string
0x18003baf8  call    cs:__imp_WindowsDuplicateString
0x18003bafe  mov     ebx, eax
0x18003bb00  test    eax, eax
0x18003bb02  js      loc_18003BD81
0x18003bb08  mov     [rbp+4Fh+var_A8], rdi
0x18003bb0c  mov     rbx, [rbp+4Fh+var_98]
0x18003bb10  lea     rcx, [rbp+4Fh+var_A8]
0x18003bb14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bb19  lea     r8, [rbp+4Fh+var_A8]
0x18003bb1d  lea     rdx, _GUID_ac2798f8_4bd2_4d64_be61_7002641cd494
0x18003bb24  mov     rcx, rbx
0x18003bb27  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VAvailableNetworkBase@Internal@UX@Networking@Windows@@UIWlanAvailableNetwork@5678@UIWiFiAvailableNetwork@678@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VAvailableNetworkBase@Internal@UX@Networking@Windows@@UIWlanAvailableNetwork@5678@UIWiFiAvailableNetwork@678@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::AvailableNetworkBase,Windows::Networking::UX::Internal::IWlanAvailableNetwork,Windows::Networking::UX::IWiFiAvailableNetwork>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Networking::UX::Internal::AvailableNetworkBase,Windows::Networking::UX::Internal::IWlanAvailableNetwork,Windows::Networking::UX::IWiFiAvailableNetwork> *,_GUID const &,void * *)
0x18003bb2c  mov     ebx, eax
0x18003bb2e  test    eax, eax
0x18003bb30  js      loc_18003BC7A
0x18003bb36  test    r13b, r13b
0x18003bb39  jz      loc_18003BC7A
0x18003bb3f  mov     [rbp+4Fh+string], rdi
0x18003bb43  mov     rbx, [rbp+4Fh+var_98]
0x18003bb47  xor     ecx, ecx; string
0x18003bb49  call    cs:__imp_WindowsDeleteString
0x18003bb4f  mov     [rbp+4Fh+string], rdi
0x18003bb53  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x18003bb57  mov     rcx, rbx; this
0x18003bb5a  call    ?get_ProfileName@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WlanNetwork::get_ProfileName(HSTRING__ * *)
0x18003bb5f  mov     ebx, eax
0x18003bb61  test    eax, eax
0x18003bb63  js      loc_18003BC70
0x18003bb69  mov     rsi, [rbp+4Fh+var_A8]
0x18003bb6d  mov     rax, [rsi]
0x18003bb70  mov     rdi, [rax+0C0h]
0x18003bb77  mov     rbx, [r14+20h]
0x18003bb7b  xor     edx, edx; length
0x18003bb7d  mov     rcx, [rbp+4Fh+string]; string
0x18003bb81  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bb87  mov     r8, rax; unsigned __int16 *
0x18003bb8a  mov     rdx, r12; struct _GUID *
0x18003bb8d  lea     rcx, [rbx+290h]; this
0x18003bb94  call    ?IsProfileAutoConnect@ProfileManager@Internal@UX@Networking@Windows@@QEAA_NPEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::IsProfileAutoConnect(_GUID const *,ushort const *)
0x18003bb99  mov     dl, al
0x18003bb9b  mov     rcx, rsi
0x18003bb9e  mov     rax, rdi
0x18003bba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bba6  cmp     r15d, 5
0x18003bbaa  jnz     short loc_18003BBD0
0x18003bbac  mov     rax, [rbp+4Fh+var_98]
0x18003bbb0  mov     r15d, [rax+0BCh]
0x18003bbb7  cmp     r15d, 5
0x18003bbbb  jnz     short loc_18003BBD0
0x18003bbbd  mov     r8, [rbp+4Fh+string]
0x18003bbc1  mov     rdx, r12
0x18003bbc4  mov     rcx, [r14+20h]
0x18003bbc8  call    ?GetProfileType@WlanClient@Internal@UX@Networking@Windows@@QEAA?AW4ProfileType@345@AEBU_GUID@@PEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WlanClient::GetProfileType(_GUID const &,HSTRING__ *)
0x18003bbcd  mov     r15d, eax
0x18003bbd0  mov     rcx, [rbp+4Fh+var_A8]
0x18003bbd4  mov     rax, [rcx]
0x18003bbd7  mov     edx, r15d
0x18003bbda  mov     rax, [rax+0D8h]
0x18003bbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbe6  xor     edi, edi
0x18003bbe8  mov     sil, dil
0x18003bbeb  lea     eax, [r15-0Ah]
0x18003bbef  cmp     eax, 1
0x18003bbf2  jbe     short loc_18003BC44
0x18003bbf4  mov     rdi, [r14+20h]
0x18003bbf8  xor     edx, edx; length
0x18003bbfa  mov     rcx, [rbp+4Fh+string]; string
0x18003bbfe  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bc04  mov     rbx, rax
0x18003bc07  lea     rdx, [rdi+298h]
0x18003bc0e  lea     rcx, [rbp+4Fh+var_80]
0x18003bc12  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003bc17  mov     r9, rbx
0x18003bc1a  mov     r8, r12
0x18003bc1d  lea     rcx, [rdi+290h]
0x18003bc24  call    ?FindCachedProfile@ProfileManager@Internal@UX@Networking@Windows@@AEAAPEAVProfile@2345@Uread_lock_required@wil@@PEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::ProfileManager::FindCachedProfile(wil::read_lock_required,_GUID const *,ushort const *)
0x18003bc29  xor     edi, edi
0x18003bc2b  test    rax, rax
0x18003bc2e  jz      short loc_18003BC3B
0x18003bc30  mov     rcx, rax; this
0x18003bc33  call    ?IsWritable@Profile@Internal@UX@Networking@Windows@@QEAA_NXZ; Windows::Networking::UX::Internal::Profile::IsWritable(void)
0x18003bc38  mov     sil, al
0x18003bc3b  lea     rcx, [rbp+4Fh+var_80]
0x18003bc3f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003bc44  mov     rcx, [rbp+4Fh+var_A8]
0x18003bc48  mov     rax, [rcx]
0x18003bc4b  mov     dl, sil
0x18003bc4e  mov     rax, [rax+0C8h]
0x18003bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc5a  mov     rcx, [rbp+4Fh+var_A8]
0x18003bc5e  mov     rax, [rcx]
0x18003bc61  lea     rdx, [rbp+4Fh+var_60]
0x18003bc65  mov     rax, [rax+68h]
0x18003bc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc6e  mov     ebx, eax
0x18003bc70  mov     rcx, [rbp+4Fh+string]; string
0x18003bc74  call    cs:__imp_WindowsDeleteString
0x18003bc7a  lea     rcx, [rbp+4Fh+var_A8]
0x18003bc7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bc83  test    ebx, ebx
0x18003bc85  js      loc_18003BD81
0x18003bc8b  mov     [rbp+4Fh+var_A8], rdi
0x18003bc8f  mov     rax, [rbp+4Fh+var_98]
0x18003bc93  mov     r15b, [rax+0B8h]
0x18003bc9a  mov     r12b, [rax+3Ch]
0x18003bc9e  test    r15b, r15b
0x18003bca1  jz      loc_18003BDE7
0x18003bca7  test    r12b, r12b
0x18003bcaa  jz      short loc_18003BCB2
0x18003bcac  mov     rdx, [r14+40h]
0x18003bcb0  jmp     short loc_18003BCB6
0x18003bcb2  mov     rdx, [r14+48h]
0x18003bcb6  test    rdx, rdx
0x18003bcb9  jz      loc_18003BDE7
0x18003bcbf  lea     rcx, [rbp+4Fh+var_A8]
0x18003bcc3  call    ??4?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIAvailableNetwork@UX@Networking@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::operator=(Windows::Networking::UX::IAvailableNetwork *)
0x18003bcc8  mov     sil, dil
0x18003bccb  mov     [rbp+4Fh+string], rdi
0x18003bccf  lea     rdx, [rbp+4Fh+string]
0x18003bcd3  lea     rcx, [rbp+4Fh+var_A8]
0x18003bcd7  call    ??$As@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@?$ComPtr@UIAvailableNetwork@UX@Networking@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWlanAvailableNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Networking::UX::IAvailableNetwork>::As<Windows::Networking::UX::Internal::IWlanAvailableNetwork>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IWlanAvailableNetwork>>)
0x18003bcdc  mov     ebx, eax
0x18003bcde  test    eax, eax
0x18003bce0  js      short loc_18003BD47
0x18003bce2  mov     rcx, [rbp+4Fh+string]
0x18003bce6  mov     rax, [rcx]
0x18003bce9  mov     rdx, [rbp+4Fh+var_98]
0x18003bced  mov     rax, [rax+0B0h]
0x18003bcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcf9  mov     ebx, eax
0x18003bcfb  mov     rax, cs:WPP_GLOBAL_Control
0x18003bd02  lea     rcx, WPP_GLOBAL_Control
0x18003bd09  cmp     rax, rcx
0x18003bd0c  jz      short loc_18003BD47
0x18003bd0e  test    byte ptr [rax+1Ch], 8
0x18003bd12  jz      short loc_18003BD47
0x18003bd14  xor     edx, edx; length
0x18003bd16  mov     rcx, [rbp+4Fh+newString]; string
0x18003bd1a  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bd20  mov     edx, 120h
0x18003bd25  mov     [rsp+0F0h+var_C0], ebx
0x18003bd29  mov     [rsp+0F0h+var_C8], r13d
0x18003bd2e  mov     [rsp+0F0h+var_D0], rax
0x18003bd33  lea     r9, [rbp+4Fh+var_70]
0x18003bd37  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd3e  mov     rcx, [rcx+10h]
0x18003bd42  call    WPP_SF__guid_Sdd
0x18003bd47  lea     rcx, [rbp+4Fh+string]
0x18003bd4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bd50  test    ebx, ebx
0x18003bd52  jns     short loc_18003BD76
0x18003bd54  test    sil, sil
0x18003bd57  jz      short loc_18003BD76
0x18003bd59  mov     rcx, [r14+38h]
0x18003bd5d  movaps  xmm0, [rbp+4Fh+var_60]
0x18003bd61  movdqa  [rbp+4Fh+var_80], xmm0
0x18003bd66  mov     rax, [rcx]
0x18003bd69  lea     rdx, [rbp+4Fh+var_80]
0x18003bd6d  mov     rax, [rax+58h]
0x18003bd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd76  mov     ebx, edi
0x18003bd78  lea     rcx, [rbp+4Fh+var_A8]
0x18003bd7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bd81  mov     rcx, [rbp+4Fh+newString]; string
0x18003bd85  call    cs:__imp_WindowsDeleteString
0x18003bd8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd92  lea     rax, WPP_GLOBAL_Control
0x18003bd99  cmp     rcx, rax
0x18003bd9c  jz      short loc_18003BDBC
0x18003bd9e  test    byte ptr [rcx+1Ch], 40h
0x18003bda2  jz      short loc_18003BDBC
0x18003bda4  mov     edx, 121h
0x18003bda9  mov     r9d, ebx
0x18003bdac  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003bdb3  mov     rcx, [rcx+10h]
0x18003bdb7  call    WPP_SF_d
0x18003bdbc  lea     rcx, [rbp+4Fh+var_98]
0x18003bdc0  call    ?InternalRelease@?$ComPtr@VWlanNetwork@Internal@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::WlanNetwork>::InternalRelease(void)
0x18003bdc5  mov     eax, ebx
0x18003bdc7  mov     rcx, [rbp+4Fh+var_50]
0x18003bdcb  xor     rcx, rsp; StackCookie
0x18003bdce  call    __security_check_cookie
0x18003bdd3  add     rsp, 0B8h
0x18003bdda  pop     r15
0x18003bddc  pop     r14
0x18003bdde  pop     r13
0x18003bde0  pop     r12
0x18003bde2  pop     rdi
0x18003bde3  pop     rsi
0x18003bde4  pop     rbx
0x18003bde5  pop     rbp
0x18003bde6  retn
0x18003bde7  mov     sil, dil
0x18003bdea  mov     dword ptr [rbp+4Fh+string], edi
0x18003bded  lea     rcx, [rbp+4Fh+var_A8]
0x18003bdf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bdf6  lea     rax, [rbp+4Fh+string]
0x18003bdfa  mov     [rsp+0F0h+var_D0], rax
0x18003bdff  lea     r9, [rbp+4Fh+var_A8]
0x18003be03  lea     r8, [rbp+4Fh+var_70]
0x18003be07  mov     rdx, [r14+28h]
0x18003be0b  mov     rcx, [r14+30h]
0x18003be0f  call    ?_LookupNetworkMapAndList@Internal@UX@Networking@Windows@@YAJPEAU?$IMap@U_GUID@@I@Collections@Foundation@4@PEAU?$IVector@PEAUIAvailableNetwork@UX@Networking@Windows@@@674@AEBU_GUID@@PEAPEAUIAvailableNetwork@234@PEAI@Z; Windows::Networking::UX::Internal::_LookupNetworkMapAndList(Windows::Foundation::Collections::IMap<_GUID,uint> *,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IAvailableNetwork *> *,_GUID const &,Windows::Networking::UX::IAvailableNetwork * *,uint *)
0x18003be14  mov     ebx, eax
0x18003be16  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be1d  lea     rax, WPP_GLOBAL_Control
0x18003be24  cmp     rcx, rax
0x18003be27  jz      short loc_18003BE47
0x18003be29  test    byte ptr [rcx+1Ch], 8
0x18003be2d  jz      short loc_18003BE47
0x18003be2f  mov     edx, 11Dh
0x18003be34  mov     r9d, ebx
0x18003be37  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003be3e  mov     rcx, [rcx+10h]
0x18003be42  call    WPP_SF_d
0x18003be47  test    ebx, ebx
0x18003be49  jns     loc_18003BF00
0x18003be4f  test    r13b, r13b
0x18003be52  jnz     short loc_18003BECF
0x18003be54  test    r15b, r15b
0x18003be57  jnz     loc_18003BF4A
0x18003be5d  mov     rdi, [r14+38h]
0x18003be61  mov     rax, [rdi]
0x18003be64  mov     rbx, [rax+30h]
0x18003be68  lea     rcx, [rbp+4Fh+var_A8]
0x18003be6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003be71  movaps  xmm0, [rbp+4Fh+var_70]
0x18003be75  movdqa  [rbp+4Fh+var_80], xmm0
0x18003be7a  lea     r8, [rbp+4Fh+var_A8]
0x18003be7e  lea     rdx, [rbp+4Fh+var_80]
  ... truncated ...
```
