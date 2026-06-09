# SystemSettings::WorkAccess::CEnrollmentHelper::GetAppNameByNodePath(void *)

- ea: `0x180046a40`
- end: `0x1800470c1`
- name: `?GetAppNameByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z`
- size: `1665`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x180009de8`
- `0x180009e68`
- `0x1800236fc`
- `0x1800458f0`
- `0x18004592c`
- `0x180046a40`
- `0x18004d2c0`
- `0x18004d310`
- `0x18004d580`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046c67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046c67`
- `OLEAUT32!__imp_SysAllocString` at `0x180046c76`
- `OLEAUT32!__imp_SysAllocString` at `0x180046ff5`
- `OLEAUT32!__imp_SysAllocString` at `0x180046c76`
- `OLEAUT32!__imp_SysAllocString` at `0x180046ff5`
- `OLEAUT32!__imp_VariantInit` at `0x180046ab5`
- `OLEAUT32!__imp_VariantInit` at `0x180046ac6`
- `OLEAUT32!__imp_VariantInit` at `0x180046b05`
- `OLEAUT32!__imp_VariantInit` at `0x180046b16`
- `OLEAUT32!__imp_VariantInit` at `0x180046ab5`
- `OLEAUT32!__imp_VariantInit` at `0x180046ac6`
- `OLEAUT32!__imp_VariantInit` at `0x180046b05`
- `OLEAUT32!__imp_VariantInit` at `0x180046b16`
- `OLEAUT32!__imp_VariantClear` at `0x180047016`
- `OLEAUT32!__imp_VariantClear` at `0x180047028`
- `OLEAUT32!__imp_VariantClear` at `0x180047070`
- `OLEAUT32!__imp_VariantClear` at `0x180047081`
- `OLEAUT32!__imp_VariantClear` at `0x180047016`
- `OLEAUT32!__imp_VariantClear` at `0x180047028`
- `OLEAUT32!__imp_VariantClear` at `0x180047070`
- `OLEAUT32!__imp_VariantClear` at `0x180047081`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046b75`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046b75`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180046a7a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180046a7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004708e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004708e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046bb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046bb3`

## string_xrefs

- `0x180046c0d`: `OMADM::TargetedUserSID`
- `0x180046a96`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180046bd4`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180046cfa`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180046e42`: `DownloadCompleted`
- `0x180046ed5`: `EnforcementCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::GetAppNameByNodePath(PVOID Parameter)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  HRESULT v3; // eax
  __int64 v4; // rdx
  __int64 bstr; // rax
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  const OLECHAR *StringRawBuffer; // rax
  unsigned __int16 *v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  const unsigned __int16 *v13; // r8
  unsigned __int64 v14; // rdx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  const wchar_t *v17; // rdx
  LONG lVal; // eax
  const unsigned __int16 *v19; // r8
  unsigned __int64 v20; // rdx
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  char v28; // [rsp+49h] [rbp-B7h]
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v32; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG v33; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v35; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v36; // [rsp+D0h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+E8h] [rbp-18h] BYREF
  OLECHAR sz[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int128 v40; // [rsp+120h] [rbp+20h]
  _OWORD v41[2]; // [rsp+130h] [rbp+30h]
  unsigned __int16 v42[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v43[264]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+488h]

  SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue = 0;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v28 = 1;
    VariantInit(&pvarg);
    VariantInit(&v36);
    v25 = 0;
    v27 = 0;
    v26 = 0;
    v30 = 0;
    v29 = 0;
    VariantInit(&v32);
    VariantInit(&v33);
    *(_OWORD *)sz = *(_OWORD *)L"{66D0DB14-5638-475f-A386-629522D8C461}";
    v39 = *(_OWORD *)L"4-5638-475f-A386-629522D8C461}";
    v40 = *(_OWORD *)L"75f-A386-629522D8C461}";
    v41[0] = *(_OWORD *)L"-629522D8C461}";
    *(_OWORD *)((char *)v41 + 14) = *(_OWORD *)L"D8C461}";
    pclsid = 0;
    v3 = CLSIDFromString(sz, &pclsid);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 466;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v3,
        ppv);
LABEL_80:
      VariantClear(&v33);
      VariantClear(&v32);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      VariantClear(&v36);
      VariantClear(&pvarg);
      CoUninitialize();
      return v2;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v3 = CoCreateInstance(&pclsid, 0, 1u, &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0, &v25);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 468;
      goto LABEL_8;
    }
    bstr = wil::make_bstr(v31, L"OMADM::AccountID");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v30,
      bstr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v31);
    v6 = wil::make_bstr(v31, L"OMADM::TargetedUserSID");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v29,
      v6);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v31);
    v7 = v30;
    if ( !v30
      || (v8 = v29) == 0
      || !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
      || (StringRawBuffer = WindowsGetStringRawBuffer(
                              *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                         + 8),
                              0),
          v32.llVal = (LONGLONG)SysAllocString(StringRawBuffer),
          v10 = _bstr_t::copy((_bstr_t *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                        + 40)),
          v33.llVal = (LONGLONG)v10,
          !v32.llVal)
      || !v10 )
    {
      v2 = 1;
      goto LABEL_80;
    }
    v32.vt = 8;
    v33.vt = 8;
    v35 = v32;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v25 + 104LL))(v25, v7, &v35);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v11,
        ppv);
      v2 = v12;
      goto LABEL_80;
    }
    v35 = v33;
    v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v25 + 104LL))(v25, v8, &v35);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 506;
      goto LABEL_8;
    }
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty )
      v13 = *(const unsigned __int16 **)SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty;
    else
      v13 = 0;
    v3 = StringCchCopyW(v42, 0x104u, v13);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 508;
      goto LABEL_8;
    }
    v3 = StringCchCatW(v42, v14, L"/Status");
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 510;
      goto LABEL_8;
    }
    v15 = v25;
    v16 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v25 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v3 = v16(v15, v42, &v27);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 512;
      goto LABEL_8;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v27 + 104LL))(v27, &pvarg);
    v2 = v3;
    if ( v3 < 0 )
    {
      if ( v3 == -2046820350 )
      {
        v2 = -2046820350;
        goto LABEL_80;
      }
      v4 = 514;
      goto LABEL_8;
    }
    if ( pvarg.lVal > 48 )
    {
      switch ( pvarg.lVal )
      {
        case 0x32:
          v17 = L"EnforcementInProgress";
          goto LABEL_59;
        case 0x37:
          v17 = L"PendingEnforcementRetry";
          goto LABEL_59;
        case 0x3C:
          v17 = L"EnforcementFailed";
          goto LABEL_59;
        case 0x46:
          v17 = L"EnforcementCompleted";
          goto LABEL_59;
        case 0x6E:
          v17 = L"HashMismatch";
          goto LABEL_59;
        case 0x8C:
          v17 = L"SignatureNotTrust";
          goto LABEL_59;
      }
    }
    else
    {
      switch ( pvarg.lVal )
      {
        case 0x30:
          v17 = L"PendingUserSession";
          goto LABEL_59;
        case 0xA:
          v17 = L"Initialized";
          goto LABEL_59;
        case 0x14:
          v17 = L"DownloadInProgress";
          goto LABEL_59;
        case 0x19:
          v17 = L"PendingDownloadRetry";
          goto LABEL_59;
        case 0x1E:
          v17 = L"DownloadFailed";
          goto LABEL_59;
        case 0x28:
          v17 = L"DownloadCompleted";
          goto LABEL_59;
        case 0x2D:
          v17 = L"ValidationPassed";
LABEL_59:
          _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus, v17);
          goto LABEL_60;
      }
    }
    _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus, L"Unrecognized Status");
    SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader((SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance);
LABEL_60:
    lVal = pvarg.lVal;
    if ( pvarg.lVal == 30 || pvarg.lVal == 60 || pvarg.lVal == 110 || pvarg.lVal == 140 )
    {
      SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader((SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance);
      lVal = pvarg.lVal;
    }
    if ( lVal == 70 )
    {
      if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty )
        v19 = *(const unsigned __int16 **)SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty;
      else
        v19 = 0;
      v3 = StringCchCopyW(v43, 0x104u, v19);
      v2 = v3;
      if ( v3 < 0 )
      {
        v4 = 550;
        goto LABEL_8;
      }
      v3 = StringCchCatW(v43, v20, L"/Name");
      v2 = v3;
      if ( v3 < 0 )
      {
        v4 = 552;
        goto LABEL_8;
      }
      v21 = v25;
      v22 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v25 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      v3 = v22(v21, v43, &v26);
      v2 = v3;
      if ( v3 < 0 )
      {
        v4 = 554;
        goto LABEL_8;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v26 + 104LL))(v26, &v36);
      v2 = v3;
      if ( v3 < 0 )
      {
        v4 = 556;
        goto LABEL_8;
      }
      SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue = SysAllocString(v36.bstrVal);
    }
    v2 = 0;
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BA,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v1,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x180046a40  mov     [rsp-8+arg_0], rbx
0x180046a45  mov     [rsp-8+arg_8], rdi
0x180046a4a  push    rbp
0x180046a4b  lea     rbp, [rsp-480h]
0x180046a53  sub     rsp, 580h
0x180046a5a  mov     rax, cs:__security_cookie
0x180046a61  xor     rax, rsp
0x180046a64  mov     [rbp+480h+var_10], rax
0x180046a6b  mov     cs:?_appCspValue@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, 0; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue
0x180046a76  xor     edx, edx; dwCoInit
0x180046a78  xor     ecx, ecx; pvReserved
0x180046a7a  call    cs:__imp_CoInitializeEx
0x180046a81  nop     dword ptr [rax+rax+00h]
0x180046a86  mov     ebx, eax
0x180046a88  test    eax, eax
0x180046a8a  jns     short loc_180046AAC
0x180046a8c  mov     rcx, [rbp+488h]; this
0x180046a93  mov     r9d, eax; char *
0x180046a96  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180046a9d  mov     edx, 1BAh; void *
0x180046aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046aa7  jmp     loc_18004709A
0x180046aac  mov     [rsp+580h+var_537], 1
0x180046ab1  lea     rcx, [rbp+480h+pvarg]; pvarg
0x180046ab5  call    cs:__imp_VariantInit
0x180046abc  nop     dword ptr [rax+rax+00h]
0x180046ac1  nop
0x180046ac2  lea     rcx, [rbp+480h+var_4B0]; pvarg
0x180046ac6  call    cs:__imp_VariantInit
0x180046acd  nop     dword ptr [rax+rax+00h]
0x180046ad2  nop
0x180046ad3  mov     [rsp+580h+var_550], 0
0x180046adc  mov     [rsp+580h+var_540], 0
0x180046ae5  mov     [rsp+580h+var_548], 0
0x180046aee  mov     [rsp+580h+var_528], 0
0x180046af7  mov     [rsp+580h+var_530], 0
0x180046b00  lea     rcx, [rsp+580h+var_518]; pvarg
0x180046b05  call    cs:__imp_VariantInit
0x180046b0c  nop     dword ptr [rax+rax+00h]
0x180046b11  nop
0x180046b12  lea     rcx, [rbp+480h+var_500]; pvarg
0x180046b16  call    cs:__imp_VariantInit
0x180046b1d  nop     dword ptr [rax+rax+00h]
0x180046b22  nop
0x180046b23  cmp     [rsp+580h+var_550], 0
0x180046b29  jnz     loc_180046BE5
0x180046b2f  movaps  xmm0, xmmword ptr cs:a66d0db14563847; "{66D0DB14-5638-475f-A386-629522D8C461}"
0x180046b36  movaps  xmmword ptr [rbp+480h+sz], xmm0
0x180046b3a  movaps  xmm1, xmmword ptr cs:a66d0db14563847+10h; "4-5638-475f-A386-629522D8C461}"
0x180046b41  movaps  [rbp+480h+var_470], xmm1
0x180046b45  movaps  xmm0, xmmword ptr cs:a66d0db14563847+20h; "75f-A386-629522D8C461}"
0x180046b4c  movaps  [rbp+480h+var_460], xmm0
0x180046b50  movaps  xmm1, xmmword ptr cs:a66d0db14563847+30h; "-629522D8C461}"
0x180046b57  movaps  xmmword ptr [rbp+480h+var_450], xmm1
0x180046b5b  movups  xmm0, xmmword ptr cs:a66d0db14563847+3Eh; "D8C461}"
0x180046b62  movups  xmmword ptr [rbp+480h+var_450+0Eh], xmm0
0x180046b66  xorps   xmm0, xmm0
0x180046b69  movups  xmmword ptr [rbp+480h+pclsid.Data1], xmm0
0x180046b6d  lea     rdx, [rbp+480h+pclsid]; pclsid
0x180046b71  lea     rcx, [rbp+480h+sz]; lpsz
0x180046b75  call    cs:__imp_CLSIDFromString
0x180046b7c  nop     dword ptr [rax+rax+00h]
0x180046b81  mov     ebx, eax
0x180046b83  test    eax, eax
0x180046b85  jns     short loc_180046B8E
0x180046b87  mov     edx, 1D2h
0x180046b8c  jmp     short loc_180046BCA
0x180046b8e  lea     rcx, [rsp+580h+var_550]
0x180046b93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046b98  lea     rax, [rsp+580h+var_550]
0x180046b9d  mov     qword ptr [rsp+580h+ppv], rax; int
0x180046ba2  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180046ba9  xor     edx, edx; pUnkOuter
0x180046bab  lea     r8d, [rdx+1]; dwClsContext
0x180046baf  lea     rcx, [rbp+480h+pclsid]; rclsid
0x180046bb3  call    cs:__imp_CoCreateInstance
0x180046bba  nop     dword ptr [rax+rax+00h]
0x180046bbf  mov     ebx, eax
0x180046bc1  test    eax, eax
0x180046bc3  jns     short loc_180046BE5
0x180046bc5  mov     edx, 1D4h; void *
0x180046bca  mov     rcx, [rbp+488h]; this
0x180046bd1  mov     r9d, eax; char *
0x180046bd4  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180046bdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046be0  jmp     loc_180047012
0x180046be5  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x180046bec  lea     rcx, [rsp+580h+var_520]
0x180046bf1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180046bf6  mov     rdx, rax
0x180046bf9  lea     rcx, [rsp+580h+var_528]
0x180046bfe  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180046c03  lea     rcx, [rsp+580h+var_520]
0x180046c08  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180046c0d  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180046c14  lea     rcx, [rsp+580h+var_520]
0x180046c19  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180046c1e  mov     rdx, rax
0x180046c21  lea     rcx, [rsp+580h+var_530]
0x180046c26  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180046c2b  lea     rcx, [rsp+580h+var_520]
0x180046c30  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180046c35  mov     rdi, [rsp+580h+var_528]
0x180046c3a  test    rdi, rdi
0x180046c3d  jz      loc_18004700D
0x180046c43  mov     rbx, [rsp+580h+var_530]
0x180046c48  test    rbx, rbx
0x180046c4b  jz      loc_18004700D
0x180046c51  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180046c58  test    rcx, rcx
0x180046c5b  jz      loc_18004700D
0x180046c61  xor     edx, edx; length
0x180046c63  mov     rcx, [rcx+8]; string
0x180046c67  call    cs:__imp_WindowsGetStringRawBuffer
0x180046c6e  nop     dword ptr [rax+rax+00h]
0x180046c73  mov     rcx, rax; psz
0x180046c76  call    cs:__imp_SysAllocString
0x180046c7d  nop     dword ptr [rax+rax+00h]
0x180046c82  mov     qword ptr [rsp+580h+var_518+8], rax
0x180046c87  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180046c8e  add     rcx, 28h ; '('; this
0x180046c92  call    ?copy@_bstr_t@@QEBAPEAGXZ; _bstr_t::copy(void)
0x180046c97  mov     qword ptr [rbp+480h+var_500+8], rax
0x180046c9b  cmp     qword ptr [rsp+580h+var_518+8], 0
0x180046ca1  jz      loc_18004700D
0x180046ca7  test    rax, rax
0x180046caa  jz      loc_18004700D
0x180046cb0  mov     eax, 8
0x180046cb5  mov     word ptr [rsp+580h+var_518], ax
0x180046cba  mov     word ptr [rbp+480h+var_500], ax
0x180046cbe  mov     rcx, [rsp+580h+var_550]
0x180046cc3  movups  xmm0, xmmword ptr [rsp+580h+var_518]
0x180046cc8  movaps  [rbp+480h+var_4D0], xmm0
0x180046ccc  movsd   xmm1, qword ptr [rsp+580h+var_518+10h]
0x180046cd2  movsd   [rbp+480h+var_4C0], xmm1
0x180046cd7  mov     rax, [rcx]
0x180046cda  lea     r8, [rbp+480h+var_4D0]
0x180046cde  mov     rdx, rdi
0x180046ce1  mov     rax, [rax+68h]
0x180046ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cea  mov     edi, eax
0x180046cec  test    eax, eax
0x180046cee  jns     short loc_180046D12
0x180046cf0  mov     rcx, [rbp+488h]; this
0x180046cf7  mov     r9d, eax; char *
0x180046cfa  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180046d01  mov     edx, 1F8h; void *
0x180046d06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046d0b  mov     ebx, edi
0x180046d0d  jmp     loc_180047012
0x180046d12  mov     rcx, [rsp+580h+var_550]
0x180046d17  movups  xmm0, xmmword ptr [rbp+480h+var_500]
0x180046d1b  movaps  [rbp+480h+var_4D0], xmm0
0x180046d1f  movsd   xmm1, qword ptr [rbp+480h+var_500+10h]
0x180046d24  movsd   [rbp+480h+var_4C0], xmm1
0x180046d29  mov     rax, [rcx]
0x180046d2c  lea     r8, [rbp+480h+var_4D0]
0x180046d30  mov     rdx, rbx
0x180046d33  mov     rax, [rax+68h]
0x180046d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d3c  mov     ebx, eax
0x180046d3e  test    eax, eax
0x180046d40  jns     short loc_180046D4C
0x180046d42  mov     edx, 1FAh
0x180046d47  jmp     loc_180046BCA
0x180046d4c  mov     rax, cs:?_appStringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty
0x180046d53  test    rax, rax
0x180046d56  jz      short loc_180046D5D
0x180046d58  mov     r8, [rax]
0x180046d5b  jmp     short loc_180046D60
0x180046d5d  xor     r8d, r8d; unsigned __int16 *
0x180046d60  mov     edx, 104h; unsigned __int64
0x180046d65  lea     rcx, [rbp+480h+var_430]; unsigned __int16 *
0x180046d69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046d6e  mov     ebx, eax
0x180046d70  test    eax, eax
0x180046d72  jns     short loc_180046D7E
0x180046d74  mov     edx, 1FCh
0x180046d79  jmp     loc_180046BCA
0x180046d7e  lea     r8, aStatus; "/Status"
0x180046d85  lea     rcx, [rbp+480h+var_430]; unsigned __int16 *
0x180046d89  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046d8e  mov     ebx, eax
0x180046d90  test    eax, eax
0x180046d92  jns     short loc_180046D9E
0x180046d94  mov     edx, 1FEh
0x180046d99  jmp     loc_180046BCA
0x180046d9e  mov     rdi, [rsp+580h+var_550]
0x180046da3  mov     rax, [rdi]
0x180046da6  mov     rbx, [rax+50h]
0x180046daa  lea     rcx, [rsp+580h+var_540]
0x180046daf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046db4  lea     r8, [rsp+580h+var_540]
0x180046db9  lea     rdx, [rbp+480h+var_430]
0x180046dbd  mov     rcx, rdi
0x180046dc0  mov     rax, rbx
0x180046dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dc8  mov     ebx, eax
0x180046dca  test    eax, eax
0x180046dcc  jns     short loc_180046DD8
0x180046dce  mov     edx, 200h
0x180046dd3  jmp     loc_180046BCA
0x180046dd8  mov     rcx, [rsp+580h+var_540]
0x180046ddd  mov     rax, [rcx]
0x180046de0  lea     rdx, [rbp+480h+pvarg]
0x180046de4  mov     rax, [rax+68h]
0x180046de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ded  mov     ebx, eax
0x180046def  test    eax, eax
0x180046df1  jns     short loc_180046E0E
0x180046df3  cmp     eax, 86000002h
0x180046df8  jnz     short loc_180046E04
0x180046dfa  mov     ebx, 86000002h
0x180046dff  jmp     loc_180047012
0x180046e04  mov     edx, 202h
0x180046e09  jmp     loc_180046BCA
0x180046e0e  mov     ecx, dword ptr [rbp+480h+pvarg+8]
0x180046e11  cmp     ecx, 30h ; '0'
0x180046e14  jg      short loc_180046E84
0x180046e16  jz      short loc_180046E7B
0x180046e18  cmp     ecx, 0Ah
0x180046e1b  jz      short loc_180046E72
0x180046e1d  cmp     ecx, 14h
0x180046e20  jz      short loc_180046E66
0x180046e22  cmp     ecx, 19h
0x180046e25  jz      short loc_180046E5A
0x180046e27  cmp     ecx, 1Eh
0x180046e2a  jz      short loc_180046E4E
0x180046e2c  cmp     ecx, 28h ; '('
0x180046e2f  jz      short loc_180046E42
0x180046e31  cmp     ecx, 2Dh ; '-'
0x180046e34  jnz     short loc_180046EA2
0x180046e36  lea     rdx, aValidationpass; "ValidationPassed"
0x180046e3d  jmp     loc_180046EF7
0x180046e42  lea     rdx, aDownloadcomple; "DownloadCompleted"
0x180046e49  jmp     loc_180046EF7
0x180046e4e  lea     rdx, aDownloadfailed; "DownloadFailed"
0x180046e55  jmp     loc_180046EF7
0x180046e5a  lea     rdx, aPendingdownloa; "PendingDownloadRetry"
0x180046e61  jmp     loc_180046EF7
0x180046e66  lea     rdx, aDownloadinprog; "DownloadInProgress"
0x180046e6d  jmp     loc_180046EF7
0x180046e72  lea     rdx, aInitialized; "Initialized"
0x180046e79  jmp     short loc_180046EF7
0x180046e7b  lea     rdx, aPendinguserses; "PendingUserSession"
0x180046e82  jmp     short loc_180046EF7
0x180046e84  sub     ecx, 32h ; '2'
0x180046e87  jz      short loc_180046EF0
0x180046e89  sub     ecx, 5
0x180046e8c  jz      short loc_180046EE7
0x180046e8e  sub     ecx, 5
0x180046e91  jz      short loc_180046EDE
0x180046e93  sub     ecx, 0Ah
0x180046e96  jz      short loc_180046ED5
0x180046e98  sub     ecx, 28h ; '('
0x180046e9b  jz      short loc_180046ECC
0x180046e9d  cmp     ecx, 1Eh
0x180046ea0  jz      short loc_180046EC3
0x180046ea2  lea     rdx, aUnrecognizedSt; "Unrecognized Status"
0x180046ea9  lea     rcx, ?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180046eb0  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180046eb5  lea     rcx, ?_corpDeviceNotificationInstance@CCorpDeviceNotificationSingleton@DataModel@SystemSettings@@1VCCorpDeviceNotificationSingletonInstance@23@A; this
0x180046ebc  call    ?NotifyShowApplicationsErrorHeader@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader(void)
0x180046ec1  jmp     short loc_180046F03
0x180046ec3  lea     rdx, aSignaturenottr; "SignatureNotTrust"
0x180046eca  jmp     short loc_180046EF7
0x180046ecc  lea     rdx, aHashmismatch; "HashMismatch"
0x180046ed3  jmp     short loc_180046EF7
0x180046ed5  lea     rdx, aEnforcementcom; "EnforcementCompleted"
0x180046edc  jmp     short loc_180046EF7
0x180046ede  lea     rdx, aEnforcementfai; "EnforcementFailed"
0x180046ee5  jmp     short loc_180046EF7
0x180046ee7  lea     rdx, aPendingenforce; "PendingEnforcementRetry"
0x180046eee  jmp     short loc_180046EF7
0x180046ef0  lea     rdx, aEnforcementinp; "EnforcementInProgress"
0x180046ef7  lea     rcx, ?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180046efe  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180046f03  mov     eax, dword ptr [rbp+480h+pvarg+8]
0x180046f06  cmp     eax, 1Eh
0x180046f09  jz      short loc_180046F1C
0x180046f0b  cmp     eax, 3Ch ; '<'
0x180046f0e  jz      short loc_180046F1C
0x180046f10  cmp     eax, 6Eh ; 'n'
0x180046f13  jz      short loc_180046F1C
0x180046f15  cmp     eax, 8Ch
0x180046f1a  jnz     short loc_180046F2B
0x180046f1c  lea     rcx, ?_corpDeviceNotificationInstance@CCorpDeviceNotificationSingleton@DataModel@SystemSettings@@1VCCorpDeviceNotificationSingletonInstance@23@A; this
0x180046f23  call    ?NotifyShowApplicationsErrorHeader@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader(void)
0x180046f28  mov     eax, dword ptr [rbp+480h+pvarg+8]
0x180046f2b  cmp     eax, 46h ; 'F'
0x180046f2e  jz      short loc_180046F37
0x180046f30  xor     ebx, ebx
0x180046f32  jmp     loc_180047012
0x180046f37  mov     rax, cs:?_appStringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty
0x180046f3e  test    rax, rax
0x180046f41  jz      short loc_180046F48
0x180046f43  mov     r8, [rax]
0x180046f46  jmp     short loc_180046F4B
0x180046f48  xor     r8d, r8d; unsigned __int16 *
0x180046f4b  mov     edx, 104h; unsigned __int64
  ... truncated ...
```
