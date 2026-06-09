# CreativeFramework::LockScreenCreativeConfigHelpers::GetLockScreenEnabled(ushort const *,bool *,bool *)

- ea: `0x18001a530`
- end: `0x18001a9c4`
- name: `?GetLockScreenEnabled@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEA_N1@Z`
- size: `1172`
- prototype: `__int64 __fastcall(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const unsigned __int16 *, bool *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003395c`

## callees

- `0x180009ce4`
- `0x18000a718`
- `0x18000a910`
- `0x18000b0d4`
- `0x18000bd60`
- `0x18001a3d0`
- `0x18001a428`
- `0x18001a530`
- `0x18001a9cc`
- `0x18001aaa4`
- `0x180034db4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a79c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a90f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a79c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a90f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a96c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a72a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a72a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a879`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a8d3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a879`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a8d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a68b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a928`

## string_xrefs

- `0x18001a612`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a670`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a6cf`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a777`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a81a`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a951`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18001a993`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::GetLockScreenEnabled(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 *a2,
        bool *a3,
        bool *a4)
{
  int Setting; // eax
  bool v7; // dl
  CreativeFramework::Policy *v8; // rcx
  void *v9; // rbx
  unsigned __int64 v10; // r8
  LPVOID *cotaskmem_string_nothrow; // rax
  void *v12; // rsi
  unsigned __int16 **v14; // rdx
  int CurrentUserSidString; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // esi
  WCHAR *v19; // rcx
  LPCWSTR v20; // r15
  LSTATUS v21; // eax
  bool v22; // sf
  int v23; // eax
  HKEY v24; // rcx
  LSTATUS v25; // eax
  int v26; // r14d
  LSTATUS ValueW; // eax
  LSTATUS v28; // eax
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  int phkResultb; // [rsp+20h] [rbp-49h]
  int phkResultc; // [rsp+20h] [rbp-49h]
  int phkResultd; // [rsp+20h] [rbp-49h]
  DWORD v34; // [rsp+40h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  LPVOID v36; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-9h] BYREF
  LPCWSTR v39[9]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v41; // [rsp+D8h] [rbp+6Fh] BYREF
  bool *pvData; // [rsp+E0h] [rbp+77h] BYREF
  DWORD pcbData; // [rsp+E8h] [rbp+7Fh] BYREF

  pvData = a3;
  if ( a2 )
    *(_BYTE *)a2 = 0;
  LODWORD(pvData) = 0;
  Setting = CreativeFramework::ContentDeliveryManagerSettings::Details::GetSettingValue<unsigned long,16>(
              (_DWORD)this,
              (_DWORD)a2,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&pvData);
  if ( Setting >= 0 )
  {
    if ( (_DWORD)pvData )
    {
      if ( a2 )
        *(_BYTE *)a2 = (_DWORD)pvData == 1;
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\ContentDeliveryManagerSettings.h",
      (const char *)(unsigned int)Setting,
      phkResult);
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  if ( !CreativeFramework::Policy::IsContentDeliverySkuPolicyAllowed(v8, v7) )
    return 0;
  v9 = 0;
  v36 = 0;
  if ( this )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)this + v10) );
    cotaskmem_string_nothrow = (LPVOID *)wil::make_cotaskmem_string_nothrow(
                                           (wil *)&pv,
                                           (const unsigned __int16 *)this,
                                           v10);
    v12 = 0;
    if ( &v36 != cotaskmem_string_nothrow )
    {
      v36 = *cotaskmem_string_nothrow;
      v9 = v36;
      *cotaskmem_string_nothrow = 0;
      v12 = v9;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)0x8007000ELL,
        phkResult);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v36,
      0);
    CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                             (CreativeFramework::LockScreenCreativeConfigHelpers *)&v36,
                             v14);
    v16 = CurrentUserSidString;
    if ( CurrentUserSidString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)(unsigned int)CurrentUserSidString,
        phkResult);
      if ( v36 )
        CoTaskMemFree(v36);
      return v16;
    }
    v9 = v36;
  }
  memset(lpSubKey, 0, sizeof(lpSubKey));
  v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          lpSubKey,
          L"%s\\%s",
          v9,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager");
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)(unsigned int)v17,
      phkResult);
    v19 = (WCHAR *)lpSubKey[0];
    if ( !lpSubKey[0] )
      goto LABEL_26;
    goto LABEL_25;
  }
  hKey = 0;
  v20 = lpSubKey[0];
  v21 = RegOpenKeyExW(HKEY_USERS, lpSubKey[0], 0, 9u, &hKey);
  v22 = v21 < 0;
  if ( v21 > 0 )
    v22 = 1;
  if ( !v22 )
  {
    v26 = 1;
LABEL_43:
    LODWORD(pvData) = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, L"RotatingLockScreenEnabled", 0x10u, 0, &pvData, &pcbData);
    v18 = ValueW;
    if ( ValueW > 0 )
      v18 = (unsigned __int16)ValueW | 0x80070000;
    if ( v18 == -2147024894 )
    {
      LODWORD(pvData) = v26;
    }
    else if ( (v18 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)v18,
        phkResultc);
      if ( hKey )
        RegCloseKey(hKey);
      if ( !v20 )
        goto LABEL_26;
      v19 = (WCHAR *)v20;
LABEL_25:
      CoTaskMemFree(v19);
LABEL_26:
      if ( v9 )
        CoTaskMemFree(v9);
      return v18;
    }
    v41 = 0;
    v34 = 4;
    v28 = RegGetValueW(hKey, 0, L"RotatingLockScreenOverlayEnabled", 0x10u, 0, &v41, &v34);
    v18 = v28;
    if ( v28 > 0 )
      v18 = (unsigned __int16)v28 | 0x80070000;
    if ( v18 == -2147024894 )
    {
      v41 = v26;
    }
    else if ( (v18 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)v18,
        phkResultd);
      if ( hKey )
        RegCloseKey(hKey);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
      goto LABEL_26;
    }
    if ( a2 )
      *(_BYTE *)a2 = (_DWORD)pvData != 0;
    if ( hKey )
      RegCloseKey(hKey);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
    if ( v9 )
      CoTaskMemFree(v9);
    return 0;
  }
  memset(v39, 0, 24);
  v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          v39,
          L"%s\\%s",
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
          v9);
  v18 = v23;
  if ( v23 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v25 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v39[0], 0, 9u, &hKey);
    v18 = v25;
    if ( v25 > 0 )
      v18 = (unsigned __int16)v25 | 0x80070000;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
    v26 = 0;
    if ( (v18 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)v18,
        phkResultb);
      v24 = hKey;
      if ( !hKey )
        goto LABEL_35;
      goto LABEL_34;
    }
    goto LABEL_43;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x13C,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)(unsigned int)v23,
    phkResulta);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v39);
  v24 = hKey;
  if ( hKey )
LABEL_34:
    RegCloseKey(v24);
LABEL_35:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
  if ( !v9 )
    return v18;
  CoTaskMemFree(v9);
  return v18;
}

```

## disassembly

```asm
0x18001a530  mov     [rsp-8+arg_10], r8
0x18001a535  push    rbp
0x18001a536  push    rbx
0x18001a537  push    rsi
0x18001a538  push    rdi
0x18001a539  push    r12
0x18001a53b  push    r14
0x18001a53d  push    r15
0x18001a53f  lea     rbp, [rsp-27h]
0x18001a544  sub     rsp, 90h
0x18001a54b  mov     rdi, rdx
0x18001a54e  mov     rsi, rcx
0x18001a551  test    rdx, rdx
0x18001a554  jz      short loc_18001A559
0x18001a556  mov     byte ptr [rdx], 0
0x18001a559  xor     r12d, r12d
0x18001a55c  mov     dword ptr [rbp+57h+arg_10], r12d
0x18001a560  lea     rax, [rbp+57h+arg_10]
0x18001a564  mov     [rsp+0C0h+phkResult], rax; int
0x18001a569  call    ??$GetSettingValue@K$0BA@@Details@ContentDeliveryManagerSettings@CreativeFramework@@YAJPEAUHKEY__@@PEBG1_NPEAKK@Z; CreativeFramework::ContentDeliveryManagerSettings::Details::GetSettingValue<ulong,16>(HKEY__ *,ushort const *,ushort const *,bool,ulong *,ulong)
0x18001a56e  test    eax, eax
0x18001a570  jns     loc_18001A62E
0x18001a576  mov     rcx, [rbp+5Fh]; this
0x18001a57a  mov     r9d, eax; char *
0x18001a57d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Conte"...
0x18001a584  mov     edx, 1B3h; void *
0x18001a589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a58e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18001a595  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18001a59a  call    ?IsContentDeliverySkuPolicyAllowed@Policy@CreativeFramework@@YA_N_N@Z; CreativeFramework::Policy::IsContentDeliverySkuPolicyAllowed(bool)
0x18001a59f  test    al, al
0x18001a5a1  jz      loc_18001A92E
0x18001a5a7  mov     rbx, r12
0x18001a5aa  mov     [rbp+57h+var_70], rbx
0x18001a5ae  test    rsi, rsi
0x18001a5b1  jz      loc_18001A64F
0x18001a5b7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001a5be  xchg    ax, ax
0x18001a5c0  inc     r8; unsigned __int64
0x18001a5c3  cmp     word ptr [rsi+r8*2], 0
0x18001a5c9  jnz     short loc_18001A5C0
0x18001a5cb  mov     rdx, rsi; unsigned __int16 *
0x18001a5ce  lea     rcx, [rbp+57h+pv]; this
0x18001a5d2  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001a5d7  mov     rsi, r12
0x18001a5da  lea     rcx, [rbp+57h+var_70]
0x18001a5de  cmp     rcx, rax
0x18001a5e1  jz      short loc_18001A5F0
0x18001a5e3  mov     rbx, [rax]
0x18001a5e6  mov     [rbp+57h+var_70], rbx
0x18001a5ea  mov     [rax], r12
0x18001a5ed  mov     rsi, rbx
0x18001a5f0  mov     rcx, [rbp+57h+pv]; pv
0x18001a5f4  test    rcx, rcx
0x18001a5f7  jz      short loc_18001A5FF
0x18001a5f9  call    cs:__imp_CoTaskMemFree
0x18001a5ff  test    rsi, rsi
0x18001a602  jnz     loc_18001A69C
0x18001a608  mov     rcx, [rbp+5Fh]; this
0x18001a60c  mov     r9d, 8007000Eh; char *
0x18001a612  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a619  mov     edx, 124h; void *
0x18001a61e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a623  nop
0x18001a624  mov     eax, 8007000Eh
0x18001a629  jmp     loc_18001A930
0x18001a62e  mov     eax, dword ptr [rbp+57h+arg_10]
0x18001a631  test    eax, eax
0x18001a633  jz      loc_18001A58E
0x18001a639  cmp     eax, 1
0x18001a63c  setz    al
0x18001a63f  test    rdi, rdi
0x18001a642  jz      loc_18001A92E
0x18001a648  mov     [rdi], al
0x18001a64a  jmp     loc_18001A92E
0x18001a64f  xor     edx, edx
0x18001a651  lea     rcx, [rbp+57h+var_70]
0x18001a655  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001a65a  lea     rcx, [rbp+57h+var_70]; this
0x18001a65e  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x18001a663  mov     ebx, eax
0x18001a665  test    eax, eax
0x18001a667  jns     short loc_18001A698
0x18001a669  mov     rcx, [rbp+5Fh]; this
0x18001a66d  mov     r9d, eax; char *
0x18001a670  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a677  mov     edx, 129h; void *
0x18001a67c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a681  nop
0x18001a682  mov     rcx, [rbp+57h+var_70]; pv
0x18001a686  test    rcx, rcx
0x18001a689  jz      short loc_18001A691
0x18001a68b  call    cs:__imp_CoTaskMemFree
0x18001a691  mov     eax, ebx
0x18001a693  jmp     loc_18001A930
0x18001a698  mov     rbx, [rbp+57h+var_70]
0x18001a69c  mov     [rbp+57h+lpSubKey], r12
0x18001a6a0  mov     [rbp+57h+var_58], r12
0x18001a6a4  mov     [rbp+57h+var_50], r12
0x18001a6a8  lea     r9, ?c_contentDeliveryManagerKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a6af  mov     r8, rbx
0x18001a6b2  lea     rdx, aSS_1; "%s\\%s"
0x18001a6b9  lea     rcx, [rbp+57h+lpSubKey]
0x18001a6bd  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a6c2  mov     esi, eax
0x18001a6c4  test    eax, eax
0x18001a6c6  jns     short loc_18001A706
0x18001a6c8  mov     rcx, [rbp+5Fh]; this
0x18001a6cc  mov     r9d, eax; char *
0x18001a6cf  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a6d6  mov     edx, 12Dh; void *
0x18001a6db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6e0  nop
0x18001a6e1  mov     rcx, [rbp+57h+lpSubKey]; pv
0x18001a6e5  test    rcx, rcx
0x18001a6e8  jz      short loc_18001A6F1
0x18001a6ea  call    cs:__imp_CoTaskMemFree
0x18001a6f0  nop
0x18001a6f1  test    rbx, rbx
0x18001a6f4  jz      short loc_18001A6FF
0x18001a6f6  mov     rcx, rbx; pv
0x18001a6f9  call    cs:__imp_CoTaskMemFree
0x18001a6ff  mov     eax, esi
0x18001a701  jmp     loc_18001A930
0x18001a706  mov     [rbp+57h+hKey], r12
0x18001a70a  lea     rax, [rbp+57h+hKey]
0x18001a70e  mov     [rsp+0C0h+phkResult], rax; int
0x18001a713  mov     r9d, 9; samDesired
0x18001a719  xor     r8d, r8d; ulOptions
0x18001a71c  mov     r15, [rbp+57h+lpSubKey]
0x18001a720  mov     rdx, r15; lpSubKey
0x18001a723  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001a72a  call    cs:__imp_RegOpenKeyExW
0x18001a730  test    eax, eax
0x18001a732  jle     short loc_18001A73E
0x18001a734  movzx   eax, ax
0x18001a737  or      eax, 80070000h
0x18001a73c  test    eax, eax
0x18001a73e  jns     loc_18001A83E
0x18001a744  mov     [rbp+57h+var_48], r12
0x18001a748  mov     [rbp+57h+var_40], r12
0x18001a74c  mov     [rbp+57h+var_38], r12
0x18001a750  mov     r9, rbx
0x18001a753  lea     r8, ?c_logonUICreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a75a  lea     rdx, aSS_1; "%s\\%s"
0x18001a761  lea     rcx, [rbp+57h+var_48]
0x18001a765  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a76a  mov     esi, eax
0x18001a76c  test    eax, eax
0x18001a76e  jns     short loc_18001A7C6
0x18001a770  mov     rcx, [rbp+5Fh]; this
0x18001a774  mov     r9d, eax; char *
0x18001a777  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a77e  mov     edx, 13Ch; void *
0x18001a783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a788  nop
0x18001a789  lea     rcx, [rbp+57h+var_48]
0x18001a78d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a792  nop
0x18001a793  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a797  test    rcx, rcx
0x18001a79a  jz      short loc_18001A7A3
0x18001a79c  call    cs:__imp_RegCloseKey
0x18001a7a2  nop
0x18001a7a3  lea     rcx, [rbp+57h+lpSubKey]
0x18001a7a7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a7ac  nop
0x18001a7ad  test    rbx, rbx
0x18001a7b0  jz      loc_18001A6FF
0x18001a7b6  mov     rcx, rbx; pv
0x18001a7b9  call    cs:__imp_CoTaskMemFree
0x18001a7bf  mov     eax, esi
0x18001a7c1  jmp     loc_18001A930
0x18001a7c6  xor     edx, edx
0x18001a7c8  lea     rcx, [rbp+57h+hKey]
0x18001a7cc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a7d1  lea     rax, [rbp+57h+hKey]
0x18001a7d5  mov     [rsp+0C0h+phkResult], rax; int
0x18001a7da  mov     r9d, 9; samDesired
0x18001a7e0  xor     r8d, r8d; ulOptions
0x18001a7e3  mov     rdx, [rbp+57h+var_48]; lpSubKey
0x18001a7e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a7ee  call    cs:__imp_RegOpenKeyExW
0x18001a7f4  mov     esi, eax
0x18001a7f6  test    eax, eax
0x18001a7f8  jle     short loc_18001A803
0x18001a7fa  movzx   esi, ax
0x18001a7fd  or      esi, 80070000h
0x18001a803  lea     rcx, [rbp+57h+var_48]
0x18001a807  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a80c  mov     r14d, r12d
0x18001a80f  test    esi, esi
0x18001a811  jns     short loc_18001A844
0x18001a813  mov     rcx, [rbp+5Fh]; this
0x18001a817  mov     r9d, esi; char *
0x18001a81a  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a821  mov     edx, 13Fh; void *
0x18001a826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a82b  nop
0x18001a82c  mov     rcx, [rbp+57h+hKey]
0x18001a830  test    rcx, rcx
0x18001a833  jz      loc_18001A7A3
0x18001a839  jmp     loc_18001A79C
0x18001a83e  mov     r14d, 1
0x18001a844  mov     dword ptr [rbp+57h+arg_10], r12d
0x18001a848  mov     [rbp+57h+arg_18], 4
0x18001a84f  lea     rax, [rbp+57h+arg_18]
0x18001a853  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001a858  lea     rax, [rbp+57h+arg_10]
0x18001a85c  mov     [rsp+0C0h+pvData], rax; pvData
0x18001a861  mov     [rsp+0C0h+phkResult], r12; int
0x18001a866  mov     r9d, 10h; dwFlags
0x18001a86c  lea     r8, ?c_lockScreenEnabledName@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "RotatingLockScreenEnabled"
0x18001a873  xor     edx, edx; lpSubKey
0x18001a875  mov     rcx, [rbp+57h+hKey]; hkey
0x18001a879  call    cs:__imp_RegGetValueW
0x18001a87f  mov     esi, eax
0x18001a881  test    eax, eax
0x18001a883  jle     short loc_18001A88E
0x18001a885  movzx   esi, ax
0x18001a888  or      esi, 80070000h
0x18001a88e  cmp     esi, 80070002h
0x18001a894  jnz     loc_18001A942
0x18001a89a  mov     dword ptr [rbp+57h+arg_10], r14d
0x18001a89e  mov     [rbp+57h+arg_8], r12d
0x18001a8a2  mov     [rbp+57h+var_80], 4
0x18001a8a9  lea     rax, [rbp+57h+var_80]
0x18001a8ad  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001a8b2  lea     rax, [rbp+57h+arg_8]
0x18001a8b6  mov     [rsp+0C0h+pvData], rax; pvData
0x18001a8bb  mov     [rsp+0C0h+phkResult], r12; int
0x18001a8c0  mov     r9d, 10h; dwFlags
0x18001a8c6  lea     r8, ?c_lockScreenOverlayEnabledName@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "RotatingLockScreenOverlayEnabled"
0x18001a8cd  xor     edx, edx; lpSubKey
0x18001a8cf  mov     rcx, [rbp+57h+hKey]; hkey
0x18001a8d3  call    cs:__imp_RegGetValueW
0x18001a8d9  mov     esi, eax
0x18001a8db  test    eax, eax
0x18001a8dd  jle     short loc_18001A8E8
0x18001a8df  movzx   esi, ax
0x18001a8e2  or      esi, 80070000h
0x18001a8e8  cmp     esi, 80070002h
0x18001a8ee  jnz     loc_18001A984
0x18001a8f4  mov     [rbp+57h+arg_8], r14d
0x18001a8f8  cmp     dword ptr [rbp+57h+arg_10], 0
0x18001a8fc  setnz   al
0x18001a8ff  test    rdi, rdi
0x18001a902  jz      short loc_18001A906
0x18001a904  mov     [rdi], al
0x18001a906  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a90a  test    rcx, rcx
0x18001a90d  jz      short loc_18001A916
0x18001a90f  call    cs:__imp_RegCloseKey
0x18001a915  nop
0x18001a916  lea     rcx, [rbp+57h+lpSubKey]
0x18001a91a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001a91f  nop
0x18001a920  test    rbx, rbx
0x18001a923  jz      short loc_18001A92E
0x18001a925  mov     rcx, rbx; pv
0x18001a928  call    cs:__imp_CoTaskMemFree
0x18001a92e  xor     eax, eax
0x18001a930  add     rsp, 90h
0x18001a937  pop     r15
0x18001a939  pop     r14
0x18001a93b  pop     r12
0x18001a93d  pop     rdi
0x18001a93e  pop     rsi
0x18001a93f  pop     rbx
0x18001a940  pop     rbp
0x18001a941  retn
0x18001a942  test    esi, esi
0x18001a944  jns     loc_18001A89E
0x18001a94a  mov     rcx, [rbp+5Fh]; this
0x18001a94e  mov     r9d, esi; char *
0x18001a951  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a958  mov     edx, 14Bh; void *
0x18001a95d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a962  nop
0x18001a963  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a967  test    rcx, rcx
0x18001a96a  jz      short loc_18001A973
0x18001a96c  call    cs:__imp_RegCloseKey
0x18001a972  nop
0x18001a973  test    r15, r15
0x18001a976  jz      loc_18001A6F1
0x18001a97c  mov     rcx, r15
0x18001a97f  jmp     loc_18001A6EA
0x18001a984  test    esi, esi
0x18001a986  jns     loc_18001A8F8
0x18001a98c  mov     rcx, [rbp+5Fh]; this
0x18001a990  mov     r9d, esi; char *
0x18001a993  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18001a99a  mov     edx, 158h; void *
0x18001a99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9a4  nop
0x18001a9a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18001a9a9  test    rcx, rcx
0x18001a9ac  jz      short loc_18001A9B5
0x18001a9ae  call    cs:__imp_RegCloseKey
  ... truncated ...
```
