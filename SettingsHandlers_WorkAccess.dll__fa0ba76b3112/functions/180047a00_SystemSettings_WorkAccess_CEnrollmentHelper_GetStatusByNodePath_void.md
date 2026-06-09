# SystemSettings::WorkAccess::CEnrollmentHelper::GetStatusByNodePath(void *)

- ea: `0x180047a00`
- end: `0x180047edf`
- name: `?GetStatusByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z`
- size: `1247`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x180009de8`
- `0x180009e68`
- `0x1800236fc`
- `0x1800458f0`
- `0x18004592c`
- `0x180047a00`
- `0x18004d2c0`
- `0x18004d310`
- `0x18004d580`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047c1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047c1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180047c2e`
- `OLEAUT32!__imp_SysAllocString` at `0x180047c2e`
- `OLEAUT32!__imp_VariantInit` at `0x180047a75`
- `OLEAUT32!__imp_VariantInit` at `0x180047a86`
- `OLEAUT32!__imp_VariantInit` at `0x180047abc`
- `OLEAUT32!__imp_VariantInit` at `0x180047ace`
- `OLEAUT32!__imp_VariantInit` at `0x180047a75`
- `OLEAUT32!__imp_VariantInit` at `0x180047a86`
- `OLEAUT32!__imp_VariantInit` at `0x180047abc`
- `OLEAUT32!__imp_VariantInit` at `0x180047ace`
- `OLEAUT32!__imp_VariantClear` at `0x180047e3f`
- `OLEAUT32!__imp_VariantClear` at `0x180047e51`
- `OLEAUT32!__imp_VariantClear` at `0x180047e8e`
- `OLEAUT32!__imp_VariantClear` at `0x180047e9f`
- `OLEAUT32!__imp_VariantClear` at `0x180047e3f`
- `OLEAUT32!__imp_VariantClear` at `0x180047e51`
- `OLEAUT32!__imp_VariantClear` at `0x180047e8e`
- `OLEAUT32!__imp_VariantClear` at `0x180047e9f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047b2d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047b2d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180047a3a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180047a3a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180047eac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180047eac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047b6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047b6b`

## string_xrefs

- `0x180047bc5`: `OMADM::TargetedUserSID`
- `0x180047a56`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180047b8c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180047cb3`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180047e15`: `Installing`
- `0x180047e1e`: `Not Installed`
- `0x180047deb`: `Installed`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::GetStatusByNodePath(PVOID Parameter)
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
  const wchar_t *v18; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  char v23; // [rsp+41h] [rbp-BFh]
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[8]; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v27; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v28; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v29; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v31; // [rsp+C8h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v34; // [rsp+100h] [rbp+0h]
  __int128 v35; // [rsp+110h] [rbp+10h]
  _OWORD v36[2]; // [rsp+120h] [rbp+20h]
  unsigned __int16 v37[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue = 0;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v23 = 1;
    VariantInit(&pvarg);
    VariantInit(&v31);
    v21 = 0;
    v22 = 0;
    v25 = 0;
    v24 = 0;
    VariantInit(&v27);
    VariantInit(&v28);
    *(_OWORD *)sz = *(_OWORD *)L"{66D0DB14-5638-475f-A386-629522D8C461}";
    v34 = *(_OWORD *)L"4-5638-475f-A386-629522D8C461}";
    v35 = *(_OWORD *)L"75f-A386-629522D8C461}";
    v36[0] = *(_OWORD *)L"-629522D8C461}";
    *(_OWORD *)((char *)v36 + 14) = *(_OWORD *)L"D8C461}";
    pclsid = 0;
    v3 = CLSIDFromString(sz, &pclsid);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 590;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v3,
        ppv);
LABEL_43:
      VariantClear(&v28);
      VariantClear(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      VariantClear(&v31);
      VariantClear(&pvarg);
      CoUninitialize();
      return v2;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v3 = CoCreateInstance(&pclsid, 0, 1u, &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0, &v21);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 592;
      goto LABEL_7;
    }
    bstr = wil::make_bstr(v26, L"OMADM::AccountID");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v25,
      bstr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
    v6 = wil::make_bstr(v26, L"OMADM::TargetedUserSID");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v24,
      v6);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
    v7 = v25;
    if ( !v25
      || (v8 = v24) == 0
      || !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
      || (StringRawBuffer = WindowsGetStringRawBuffer(
                              *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                         + 8),
                              0),
          v27.llVal = (LONGLONG)SysAllocString(StringRawBuffer),
          v10 = _bstr_t::copy((_bstr_t *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                        + 40)),
          v28.llVal = (LONGLONG)v10,
          !v27.llVal)
      || !v10 )
    {
      v2 = 1;
      goto LABEL_43;
    }
    v27.vt = 8;
    v28.vt = 8;
    v29 = v27;
    v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(v21, v7, &v29);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
        (const char *)(unsigned int)v11,
        ppv);
      v2 = v12;
      goto LABEL_43;
    }
    v29 = v28;
    v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(v21, v8, &v29);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 630;
      goto LABEL_7;
    }
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty )
      v13 = *(const unsigned __int16 **)SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty;
    else
      v13 = 0;
    v3 = StringCchCopyW(v37, 0x104u, v13);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 632;
      goto LABEL_7;
    }
    v3 = StringCchCatW(v37, v14, L"/Status");
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 634;
      goto LABEL_7;
    }
    v15 = v21;
    v16 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v21 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v3 = v16(v15, v37, &v22);
    v2 = v3;
    if ( v3 < 0 )
    {
      v4 = 636;
      goto LABEL_7;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v22 + 104LL))(v22, &pvarg);
    v2 = v3;
    if ( v3 < 0 )
    {
      if ( v3 == -2046820350 )
      {
        v2 = -2046820350;
        goto LABEL_43;
      }
      v4 = 638;
      goto LABEL_7;
    }
    if ( pvarg.lVal )
    {
      switch ( pvarg.lVal )
      {
        case 1:
          v18 = L"Installing";
          break;
        case 2:
          v17 = L"Failed";
          goto LABEL_37;
        case 3:
          v18 = L"Installed";
          break;
        default:
          v17 = L"Unrecognized Status";
LABEL_37:
          _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus, v17);
          SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader((SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance);
LABEL_41:
          v2 = 0;
          goto LABEL_43;
      }
    }
    else
    {
      v18 = L"Not Installed";
    }
    _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus, v18);
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x238,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v1,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x180047a00  mov     [rsp-8+arg_0], rbx
0x180047a05  mov     [rsp-8+arg_8], rdi
0x180047a0a  push    rbp
0x180047a0b  lea     rbp, [rsp-260h]
0x180047a13  sub     rsp, 360h
0x180047a1a  mov     rax, cs:__security_cookie
0x180047a21  xor     rax, rsp
0x180047a24  mov     [rbp+260h+var_10], rax
0x180047a2b  mov     cs:?_appCspValue@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, 0; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_appCspValue
0x180047a36  xor     edx, edx; dwCoInit
0x180047a38  xor     ecx, ecx; pvReserved
0x180047a3a  call    cs:__imp_CoInitializeEx
0x180047a41  nop     dword ptr [rax+rax+00h]
0x180047a46  mov     ebx, eax
0x180047a48  test    eax, eax
0x180047a4a  jns     short loc_180047A6C
0x180047a4c  mov     rcx, [rbp+268h]; this
0x180047a53  mov     r9d, eax; char *
0x180047a56  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180047a5d  mov     edx, 238h; void *
0x180047a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047a67  jmp     loc_180047EB8
0x180047a6c  mov     [rsp+360h+var_31F], 1
0x180047a71  lea     rcx, [rbp+260h+pvarg]; pvarg
0x180047a75  call    cs:__imp_VariantInit
0x180047a7c  nop     dword ptr [rax+rax+00h]
0x180047a81  nop
0x180047a82  lea     rcx, [rbp+260h+var_298]; pvarg
0x180047a86  call    cs:__imp_VariantInit
0x180047a8d  nop     dword ptr [rax+rax+00h]
0x180047a92  nop
0x180047a93  mov     [rsp+360h+var_330], 0
0x180047a9c  mov     [rsp+360h+var_328], 0
0x180047aa5  mov     [rsp+360h+var_310], 0
0x180047aae  mov     [rsp+360h+var_318], 0
0x180047ab7  lea     rcx, [rsp+360h+var_300]; pvarg
0x180047abc  call    cs:__imp_VariantInit
0x180047ac3  nop     dword ptr [rax+rax+00h]
0x180047ac8  nop
0x180047ac9  lea     rcx, [rsp+360h+var_2E8]; pvarg
0x180047ace  call    cs:__imp_VariantInit
0x180047ad5  nop     dword ptr [rax+rax+00h]
0x180047ada  nop
0x180047adb  cmp     [rsp+360h+var_330], 0
0x180047ae1  jnz     loc_180047B9D
0x180047ae7  movaps  xmm0, xmmword ptr cs:a66d0db14563847; "{66D0DB14-5638-475f-A386-629522D8C461}"
0x180047aee  movaps  xmmword ptr [rbp+260h+sz], xmm0
0x180047af2  movaps  xmm1, xmmword ptr cs:a66d0db14563847+10h; "4-5638-475f-A386-629522D8C461}"
0x180047af9  movaps  [rbp+260h+var_260], xmm1
0x180047afd  movaps  xmm0, xmmword ptr cs:a66d0db14563847+20h; "75f-A386-629522D8C461}"
0x180047b04  movaps  [rbp+260h+var_250], xmm0
0x180047b08  movaps  xmm1, xmmword ptr cs:a66d0db14563847+30h; "-629522D8C461}"
0x180047b0f  movaps  xmmword ptr [rbp+260h+var_240], xmm1
0x180047b13  movups  xmm0, xmmword ptr cs:a66d0db14563847+3Eh; "D8C461}"
0x180047b1a  movups  xmmword ptr [rbp+260h+var_240+0Eh], xmm0
0x180047b1e  xorps   xmm0, xmm0
0x180047b21  movups  xmmword ptr [rbp+260h+pclsid.Data1], xmm0
0x180047b25  lea     rdx, [rbp+260h+pclsid]; pclsid
0x180047b29  lea     rcx, [rbp+260h+sz]; lpsz
0x180047b2d  call    cs:__imp_CLSIDFromString
0x180047b34  nop     dword ptr [rax+rax+00h]
0x180047b39  mov     ebx, eax
0x180047b3b  test    eax, eax
0x180047b3d  jns     short loc_180047B46
0x180047b3f  mov     edx, 24Eh
0x180047b44  jmp     short loc_180047B82
0x180047b46  lea     rcx, [rsp+360h+var_330]
0x180047b4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047b50  lea     rax, [rsp+360h+var_330]
0x180047b55  mov     qword ptr [rsp+360h+ppv], rax; int
0x180047b5a  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180047b61  xor     edx, edx; pUnkOuter
0x180047b63  lea     r8d, [rdx+1]; dwClsContext
0x180047b67  lea     rcx, [rbp+260h+pclsid]; rclsid
0x180047b6b  call    cs:__imp_CoCreateInstance
0x180047b72  nop     dword ptr [rax+rax+00h]
0x180047b77  mov     ebx, eax
0x180047b79  test    eax, eax
0x180047b7b  jns     short loc_180047B9D
0x180047b7d  mov     edx, 250h; void *
0x180047b82  mov     rcx, [rbp+268h]; this
0x180047b89  mov     r9d, eax; char *
0x180047b8c  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180047b93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047b98  jmp     loc_180047E3A
0x180047b9d  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x180047ba4  lea     rcx, [rsp+360h+var_308]
0x180047ba9  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180047bae  mov     rdx, rax
0x180047bb1  lea     rcx, [rsp+360h+var_310]
0x180047bb6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180047bbb  lea     rcx, [rsp+360h+var_308]
0x180047bc0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180047bc5  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180047bcc  lea     rcx, [rsp+360h+var_308]
0x180047bd1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180047bd6  mov     rdx, rax
0x180047bd9  lea     rcx, [rsp+360h+var_318]
0x180047bde  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180047be3  lea     rcx, [rsp+360h+var_308]
0x180047be8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180047bed  mov     rdi, [rsp+360h+var_310]
0x180047bf2  test    rdi, rdi
0x180047bf5  jz      loc_180047E35
0x180047bfb  mov     rbx, [rsp+360h+var_318]
0x180047c00  test    rbx, rbx
0x180047c03  jz      loc_180047E35
0x180047c09  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180047c10  test    rcx, rcx
0x180047c13  jz      loc_180047E35
0x180047c19  xor     edx, edx; length
0x180047c1b  mov     rcx, [rcx+8]; string
0x180047c1f  call    cs:__imp_WindowsGetStringRawBuffer
0x180047c26  nop     dword ptr [rax+rax+00h]
0x180047c2b  mov     rcx, rax; psz
0x180047c2e  call    cs:__imp_SysAllocString
0x180047c35  nop     dword ptr [rax+rax+00h]
0x180047c3a  mov     qword ptr [rsp+360h+var_300+8], rax
0x180047c3f  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180047c46  add     rcx, 28h ; '('; this
0x180047c4a  call    ?copy@_bstr_t@@QEBAPEAGXZ; _bstr_t::copy(void)
0x180047c4f  mov     qword ptr [rbp+260h+var_2E8+8], rax
0x180047c53  cmp     qword ptr [rsp+360h+var_300+8], 0
0x180047c59  jz      loc_180047E35
0x180047c5f  test    rax, rax
0x180047c62  jz      loc_180047E35
0x180047c68  mov     eax, 8
0x180047c6d  mov     word ptr [rsp+360h+var_300], ax
0x180047c72  mov     word ptr [rsp+360h+var_2E8], ax
0x180047c77  mov     rcx, [rsp+360h+var_330]
0x180047c7c  movups  xmm0, xmmword ptr [rsp+360h+var_300]
0x180047c81  movaps  [rbp+260h+var_2D0], xmm0
0x180047c85  movsd   xmm1, qword ptr [rsp+360h+var_300+10h]
0x180047c8b  movsd   [rbp+260h+var_2C0], xmm1
0x180047c90  mov     rax, [rcx]
0x180047c93  lea     r8, [rbp+260h+var_2D0]
0x180047c97  mov     rdx, rdi
0x180047c9a  mov     rax, [rax+68h]
0x180047c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ca3  mov     edi, eax
0x180047ca5  test    eax, eax
0x180047ca7  jns     short loc_180047CCB
0x180047ca9  mov     rcx, [rbp+268h]; this
0x180047cb0  mov     r9d, eax; char *
0x180047cb3  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180047cba  mov     edx, 274h; void *
0x180047cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047cc4  mov     ebx, edi
0x180047cc6  jmp     loc_180047E3A
0x180047ccb  mov     rcx, [rsp+360h+var_330]
0x180047cd0  movups  xmm0, xmmword ptr [rsp+360h+var_2E8]
0x180047cd5  movaps  [rbp+260h+var_2D0], xmm0
0x180047cd9  movsd   xmm1, qword ptr [rbp+260h+var_2E8+10h]
0x180047cde  movsd   [rbp+260h+var_2C0], xmm1
0x180047ce3  mov     rax, [rcx]
0x180047ce6  lea     r8, [rbp+260h+var_2D0]
0x180047cea  mov     rdx, rbx
0x180047ced  mov     rax, [rax+68h]
0x180047cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cf6  mov     ebx, eax
0x180047cf8  test    eax, eax
0x180047cfa  jns     short loc_180047D06
0x180047cfc  mov     edx, 276h
0x180047d01  jmp     loc_180047B82
0x180047d06  mov     rax, cs:?_appStringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty
0x180047d0d  test    rax, rax
0x180047d10  jz      short loc_180047D17
0x180047d12  mov     r8, [rax]
0x180047d15  jmp     short loc_180047D1A
0x180047d17  xor     r8d, r8d; unsigned __int16 *
0x180047d1a  mov     edx, 104h; unsigned __int64
0x180047d1f  lea     rcx, [rbp+260h+var_220]; unsigned __int16 *
0x180047d23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047d28  mov     ebx, eax
0x180047d2a  test    eax, eax
0x180047d2c  jns     short loc_180047D38
0x180047d2e  mov     edx, 278h
0x180047d33  jmp     loc_180047B82
0x180047d38  lea     r8, aStatus; "/Status"
0x180047d3f  lea     rcx, [rbp+260h+var_220]; unsigned __int16 *
0x180047d43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180047d48  mov     ebx, eax
0x180047d4a  test    eax, eax
0x180047d4c  jns     short loc_180047D58
0x180047d4e  mov     edx, 27Ah
0x180047d53  jmp     loc_180047B82
0x180047d58  mov     rdi, [rsp+360h+var_330]
0x180047d5d  mov     rax, [rdi]
0x180047d60  mov     rbx, [rax+50h]
0x180047d64  lea     rcx, [rsp+360h+var_328]
0x180047d69  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047d6e  lea     r8, [rsp+360h+var_328]
0x180047d73  lea     rdx, [rbp+260h+var_220]
0x180047d77  mov     rcx, rdi
0x180047d7a  mov     rax, rbx
0x180047d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d82  mov     ebx, eax
0x180047d84  test    eax, eax
0x180047d86  jns     short loc_180047D92
0x180047d88  mov     edx, 27Ch
0x180047d8d  jmp     loc_180047B82
0x180047d92  mov     rcx, [rsp+360h+var_328]
0x180047d97  mov     rax, [rcx]
0x180047d9a  lea     rdx, [rbp+260h+pvarg]
0x180047d9e  mov     rax, [rax+68h]
0x180047da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047da7  mov     ebx, eax
0x180047da9  test    eax, eax
0x180047dab  jns     short loc_180047DC5
0x180047dad  cmp     eax, 86000002h
0x180047db2  jnz     short loc_180047DBB
0x180047db4  mov     ebx, 86000002h
0x180047db9  jmp     short loc_180047E3A
0x180047dbb  mov     edx, 27Eh
0x180047dc0  jmp     loc_180047B82
0x180047dc5  mov     ecx, dword ptr [rbp+260h+pvarg+8]
0x180047dc8  test    ecx, ecx
0x180047dca  jz      short loc_180047E1E
0x180047dcc  sub     ecx, 1
0x180047dcf  jz      short loc_180047E15
0x180047dd1  sub     ecx, 1
0x180047dd4  jz      short loc_180047DF4
0x180047dd6  cmp     ecx, 1
0x180047dd9  lea     rcx, ?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180047de0  jz      short loc_180047DEB
0x180047de2  lea     rdx, aUnrecognizedSt; "Unrecognized Status"
0x180047de9  jmp     short loc_180047E02
0x180047deb  lea     rdx, aInstalled; "Installed"
0x180047df2  jmp     short loc_180047E2C
0x180047df4  lea     rdx, aFailed; "Failed"
0x180047dfb  lea     rcx, ?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180047e02  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180047e07  lea     rcx, ?_corpDeviceNotificationInstance@CCorpDeviceNotificationSingleton@DataModel@SystemSettings@@1VCCorpDeviceNotificationSingletonInstance@23@A; this
0x180047e0e  call    ?NotifyShowApplicationsErrorHeader@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAXXZ; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyShowApplicationsErrorHeader(void)
0x180047e13  jmp     short loc_180047E31
0x180047e15  lea     rdx, aInstalling; "Installing"
0x180047e1c  jmp     short loc_180047E25
0x180047e1e  lea     rdx, aNotInstalled; "Not Installed"
0x180047e25  lea     rcx, ?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180047e2c  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180047e31  xor     ebx, ebx
0x180047e33  jmp     short loc_180047E3A
0x180047e35  mov     ebx, 1
0x180047e3a  lea     rcx, [rsp+360h+var_2E8]; pvarg
0x180047e3f  call    cs:__imp_VariantClear
0x180047e46  nop     dword ptr [rax+rax+00h]
0x180047e4b  nop
0x180047e4c  lea     rcx, [rsp+360h+var_300]; pvarg
0x180047e51  call    cs:__imp_VariantClear
0x180047e58  nop     dword ptr [rax+rax+00h]
0x180047e5d  nop
0x180047e5e  lea     rcx, [rsp+360h+var_318]
0x180047e63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180047e68  nop
0x180047e69  lea     rcx, [rsp+360h+var_310]
0x180047e6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180047e73  nop
0x180047e74  lea     rcx, [rsp+360h+var_328]
0x180047e79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047e7e  nop
0x180047e7f  lea     rcx, [rsp+360h+var_330]
0x180047e84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047e89  nop
0x180047e8a  lea     rcx, [rbp+260h+var_298]; pvarg
0x180047e8e  call    cs:__imp_VariantClear
0x180047e95  nop     dword ptr [rax+rax+00h]
0x180047e9a  nop
0x180047e9b  lea     rcx, [rbp+260h+pvarg]; pvarg
0x180047e9f  call    cs:__imp_VariantClear
0x180047ea6  nop     dword ptr [rax+rax+00h]
0x180047eab  nop
0x180047eac  call    cs:__imp_CoUninitialize
0x180047eb3  nop     dword ptr [rax+rax+00h]
0x180047eb8  mov     eax, ebx
0x180047eba  mov     rcx, [rbp+260h+var_10]
0x180047ec1  xor     rcx, rsp; StackCookie
0x180047ec4  call    __security_check_cookie
0x180047ec9  lea     r11, [rsp+360h+var_s0]
0x180047ed1  mov     rbx, [r11+10h]
0x180047ed5  mov     rdi, [r11+18h]
0x180047ed9  mov     rsp, r11
0x180047edc  pop     rbp
0x180047edd  retn
```
