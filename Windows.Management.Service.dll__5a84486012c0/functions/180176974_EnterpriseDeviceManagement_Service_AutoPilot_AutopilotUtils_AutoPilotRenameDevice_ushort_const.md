# EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotRenameDevice(ushort const *)

- ea: `0x180176974`
- end: `0x180176f9a`
- name: `?AutoPilotRenameDevice@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBG@Z`
- size: `1574`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bc174`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x1800841e8`
- `0x18008939c`
- `0x1800a2174`
- `0x180175bbc`
- `0x180176974`
- `0x180177f24`
- `0x180178048`
- `0x18018079c`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180176a2b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180176a2b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180176b69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180176b69`
- `OLEAUT32!__imp_SysAllocString` at `0x180176aaf`
- `OLEAUT32!__imp_SysAllocString` at `0x180176aaf`
- `OLEAUT32!__imp_VariantInit` at `0x180176a18`
- `OLEAUT32!__imp_VariantInit` at `0x180176a18`
- `OLEAUT32!__imp_VariantClear` at `0x180176a58`
- `OLEAUT32!__imp_VariantClear` at `0x180176ae5`
- `OLEAUT32!__imp_VariantClear` at `0x180176b96`
- `OLEAUT32!__imp_VariantClear` at `0x180176c3c`
- `OLEAUT32!__imp_VariantClear` at `0x180176d03`
- `OLEAUT32!__imp_VariantClear` at `0x180176dc0`
- `OLEAUT32!__imp_VariantClear` at `0x180176e58`
- `OLEAUT32!__imp_VariantClear` at `0x180176ebd`
- `OLEAUT32!__imp_VariantClear` at `0x180176f25`
- `OLEAUT32!__imp_VariantClear` at `0x180176a58`
- `OLEAUT32!__imp_VariantClear` at `0x180176ae5`
- `OLEAUT32!__imp_VariantClear` at `0x180176b96`
- `OLEAUT32!__imp_VariantClear` at `0x180176c3c`
- `OLEAUT32!__imp_VariantClear` at `0x180176d03`
- `OLEAUT32!__imp_VariantClear` at `0x180176dc0`
- `OLEAUT32!__imp_VariantClear` at `0x180176e58`
- `OLEAUT32!__imp_VariantClear` at `0x180176ebd`
- `OLEAUT32!__imp_VariantClear` at `0x180176f25`

## string_xrefs

- `0x18017699e`: `AutoPilotRenameDevice`
- `0x180176a01`: `ComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotRenameDevice(OLECHAR *a1)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  HRESULT v3; // eax
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64, VARIANTARG *); // rbx
  int v9; // eax
  int v10; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v18; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  char *v23; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v25; // [rsp+80h] [rbp-80h]
  OLECHAR **p_psz; // [rsp+88h] [rbp-78h]
  char v27; // [rsp+90h] [rbp-70h]
  VARIANTARG v28; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v29[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  psz = a1;
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::`vftable';
  ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::StartActivity(
    (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
    psz);
  v25 = v29;
  p_psz = &psz;
  v27 = 1;
  v18 = 0;
  v17 = 0;
  *(_QWORD *)v21 = 0;
  v20 = 0;
  wil::make_bstr(&v22, L"ComputerName");
  VariantInit(&pvarg);
  LODWORD(v23) = 0;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( pvarg.llVal )
    {
      pvarg.vt = 8;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      v3 = CoCreateInstance(
             &GUID_66d0db14_5638_475f_a386_629522d8c461,
             0,
             1u,
             &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
             &v18);
      v2 = v3;
      if ( v3 >= 0 )
      {
        v4 = v18;
        v5 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v18 + 80LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        v6 = v5(v4, L"./Vendor/MSFT/Accounts/Domain", &v17);
        v2 = v6;
        if ( v6 >= 0 )
        {
          v7 = v17;
          v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64, VARIANTARG *))(*(_QWORD *)v17 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
          v28 = pvarg;
          v9 = v8(v7, v22, 1, &v28);
          v2 = v9;
          if ( v9 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 24LL))(v18);
            if ( v10 >= 0 )
            {
              Microsoft::Windows::Autopilot::AutopilotPolicyInternal::SetRegistryString(
                L"CloudAssignedDeviceNameLastProcessed",
                (const BYTE *)psz);
              VariantClear(&pvarg);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
              ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
                (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
                psz);
              v2 = 0;
            }
            else
            {
              v11 = v17;
              v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 152LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
              v13 = v12(v11, &v20);
              v2 = v13;
              if ( v13 >= 0 )
              {
                (*(void (__fastcall **)(__int64, __int64, char **))(*(_QWORD *)v20 + 24LL))(v20, 1, &v23);
                v2 = (unsigned int)v23;
                if ( (int)v23 >= 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x162,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
                    (const char *)(unsigned int)v10,
                    (int)v21);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
                  ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
                    (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
                    psz);
                  v2 = v10;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x160,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
                    (const char *)(unsigned int)v23,
                    (int)v21);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
                  ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
                    (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
                    psz);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x158,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
                  (const char *)(unsigned int)v13,
                  (int)v21);
                VariantClear(&pvarg);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
                ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
                  (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
                  psz);
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x152,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
              (const char *)(unsigned int)v9,
              (int)v21);
            VariantClear(&pvarg);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
            ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
              (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
              psz);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x150,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
            (const char *)(unsigned int)v6,
            ppva);
          VariantClear(&pvarg);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
          ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
            (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
            psz);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
          (const char *)(unsigned int)v3,
          ppva);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
          (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
          psz);
      }
    }
    else
    {
      v2 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
        (const char *)0x8007000ELL,
        ppv);
      VariantClear(&pvarg);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
      ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(
        (ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29,
        psz);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
      (const char *)(unsigned int)v1,
      ppv);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop((ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29, psz);
  }
  ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::~AutoPilotRenameDevice((ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice *)v29);
  return v2;
}

```

## disassembly

```asm
0x180176974  push    rbp
0x180176976  push    rbx
0x180176977  push    rsi
0x180176978  push    rdi
0x180176979  lea     rbp, [rsp-128h]
0x180176981  sub     rsp, 228h
0x180176988  mov     rax, cs:__security_cookie
0x18017698f  xor     rax, rsp
0x180176992  mov     [rbp+140h+var_30], rax
0x180176999  mov     [rsp+240h+psz], rcx
0x18017699e  lea     rdx, aAutopilotrenam; "AutoPilotRenameDevice"
0x1801769a5  lea     rcx, [rbp+140h+var_180]; struct wil::details::IFailureCallback *
0x1801769a9  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1801769ae  lea     rax, ??_7AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::`vftable'
0x1801769b5  mov     [rbp+140h+var_180], rax
0x1801769b9  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x1801769be  lea     rcx, [rbp+140h+var_180]; this
0x1801769c2  call    ?StartActivity@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::StartActivity(ushort const *)
0x1801769c7  nop
0x1801769c8  lea     rax, [rbp+140h+var_180]
0x1801769cc  mov     [rbp+140h+var_1C0], rax
0x1801769d0  lea     rax, [rsp+240h+psz]
0x1801769d5  mov     [rbp+140h+var_1B8], rax
0x1801769d9  mov     [rbp+140h+var_1B0], 1
0x1801769dd  mov     [rsp+240h+var_208], 0
0x1801769e6  mov     [rsp+240h+var_210], 0
0x1801769ef  mov     qword ptr [rsp+240h+var_1F0], 0
0x1801769f8  mov     [rsp+240h+var_1F8], 0
0x180176a01  lea     rdx, aComputername; "ComputerName"
0x180176a08  lea     rcx, [rsp+240h+var_1E8]
0x180176a0d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180176a12  nop
0x180176a13  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176a18  call    cs:__imp_VariantInit
0x180176a1e  nop
0x180176a1f  mov     dword ptr [rsp+240h+var_1E0], 0
0x180176a27  xor     edx, edx; dwCoInit
0x180176a29  xor     ecx, ecx; pvReserved
0x180176a2b  call    cs:__imp_CoInitializeEx
0x180176a31  mov     ebx, eax
0x180176a33  test    eax, eax
0x180176a35  jns     short loc_180176AAA
0x180176a37  mov     rcx, [rbp+148h]; this
0x180176a3e  mov     r9d, eax; char *
0x180176a41  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176a48  mov     edx, 144h; void *
0x180176a4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176a52  nop
0x180176a53  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176a58  call    cs:__imp_VariantClear
0x180176a5e  nop
0x180176a5f  lea     rcx, [rsp+240h+var_1E8]
0x180176a64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176a69  nop
0x180176a6a  lea     rcx, [rsp+240h+var_1F8]
0x180176a6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176a74  nop
0x180176a75  lea     rcx, [rsp+240h+var_1F0]
0x180176a7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176a7f  nop
0x180176a80  lea     rcx, [rsp+240h+var_210]
0x180176a85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176a8a  nop
0x180176a8b  lea     rcx, [rsp+240h+var_208]
0x180176a90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176a95  nop
0x180176a96  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176a9b  lea     rcx, [rbp+140h+var_180]; this
0x180176a9f  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176aa4  nop
0x180176aa5  jmp     loc_180176F74
0x180176aaa  mov     rcx, [rsp+240h+psz]; psz
0x180176aaf  call    cs:__imp_SysAllocString
0x180176ab5  mov     qword ptr [rsp+240h+pvarg+8], rax
0x180176aba  test    rax, rax
0x180176abd  jnz     short loc_180176B37
0x180176abf  mov     rcx, [rbp+148h]; this
0x180176ac6  mov     ebx, 8007000Eh
0x180176acb  mov     r9d, ebx; char *
0x180176ace  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176ad5  mov     edx, 14Bh; void *
0x180176ada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176adf  nop
0x180176ae0  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176ae5  call    cs:__imp_VariantClear
0x180176aeb  nop
0x180176aec  lea     rcx, [rsp+240h+var_1E8]
0x180176af1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176af6  nop
0x180176af7  lea     rcx, [rsp+240h+var_1F8]
0x180176afc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176b01  nop
0x180176b02  lea     rcx, [rsp+240h+var_1F0]
0x180176b07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176b0c  nop
0x180176b0d  lea     rcx, [rsp+240h+var_210]
0x180176b12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176b17  nop
0x180176b18  lea     rcx, [rsp+240h+var_208]
0x180176b1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176b22  nop
0x180176b23  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176b28  lea     rcx, [rbp+140h+var_180]; this
0x180176b2c  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176b31  nop
0x180176b32  jmp     loc_180176F74
0x180176b37  mov     eax, 8
0x180176b3c  mov     word ptr [rsp+240h+pvarg], ax
0x180176b41  lea     rcx, [rsp+240h+var_208]
0x180176b46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176b4b  lea     rax, [rsp+240h+var_208]
0x180176b50  mov     qword ptr [rsp+240h+ppv], rax; int
0x180176b55  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180176b5c  xor     edx, edx; pUnkOuter
0x180176b5e  lea     r8d, [rdx+1]; dwClsContext
0x180176b62  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180176b69  call    cs:__imp_CoCreateInstance
0x180176b6f  mov     ebx, eax
0x180176b71  test    eax, eax
0x180176b73  jns     short loc_180176BE8
0x180176b75  mov     rcx, [rbp+148h]; this
0x180176b7c  mov     r9d, eax; char *
0x180176b7f  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176b86  mov     edx, 14Eh; void *
0x180176b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176b90  nop
0x180176b91  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176b96  call    cs:__imp_VariantClear
0x180176b9c  nop
0x180176b9d  lea     rcx, [rsp+240h+var_1E8]
0x180176ba2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176ba7  nop
0x180176ba8  lea     rcx, [rsp+240h+var_1F8]
0x180176bad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176bb2  nop
0x180176bb3  lea     rcx, [rsp+240h+var_1F0]
0x180176bb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176bbd  nop
0x180176bbe  lea     rcx, [rsp+240h+var_210]
0x180176bc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176bc8  nop
0x180176bc9  lea     rcx, [rsp+240h+var_208]
0x180176bce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176bd3  nop
0x180176bd4  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176bd9  lea     rcx, [rbp+140h+var_180]; this
0x180176bdd  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176be2  nop
0x180176be3  jmp     loc_180176F74
0x180176be8  mov     rdi, [rsp+240h+var_208]
0x180176bed  mov     rax, [rdi]
0x180176bf0  mov     rbx, [rax+50h]
0x180176bf4  lea     rcx, [rsp+240h+var_210]
0x180176bf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176bfe  lea     r8, [rsp+240h+var_210]
0x180176c03  lea     rdx, aVendorMsftAcco; "./Vendor/MSFT/Accounts/Domain"
0x180176c0a  mov     rcx, rdi
0x180176c0d  mov     rax, rbx
0x180176c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176c15  mov     ebx, eax
0x180176c17  test    eax, eax
0x180176c19  jns     short loc_180176C8E
0x180176c1b  mov     rcx, [rbp+148h]; this
0x180176c22  mov     r9d, eax; char *
0x180176c25  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176c2c  mov     edx, 150h; void *
0x180176c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176c36  nop
0x180176c37  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176c3c  call    cs:__imp_VariantClear
0x180176c42  nop
0x180176c43  lea     rcx, [rsp+240h+var_1E8]
0x180176c48  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176c4d  nop
0x180176c4e  lea     rcx, [rsp+240h+var_1F8]
0x180176c53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176c58  nop
0x180176c59  lea     rcx, [rsp+240h+var_1F0]
0x180176c5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176c63  nop
0x180176c64  lea     rcx, [rsp+240h+var_210]
0x180176c69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176c6e  nop
0x180176c6f  lea     rcx, [rsp+240h+var_208]
0x180176c74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176c79  nop
0x180176c7a  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176c7f  lea     rcx, [rbp+140h+var_180]; this
0x180176c83  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176c88  nop
0x180176c89  jmp     loc_180176F74
0x180176c8e  mov     rdi, [rsp+240h+var_210]
0x180176c93  mov     rax, [rdi]
0x180176c96  mov     rbx, [rax+18h]
0x180176c9a  lea     rcx, [rsp+240h+var_1F0]
0x180176c9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176ca4  movups  xmm0, xmmword ptr [rsp+240h+pvarg]
0x180176ca9  movaps  [rbp+140h+var_1A0], xmm0
0x180176cad  movsd   xmm1, qword ptr [rsp+240h+pvarg+10h]
0x180176cb3  movsd   [rbp+140h+var_190], xmm1
0x180176cb8  lea     rax, [rsp+240h+var_1F0]
0x180176cbd  mov     qword ptr [rsp+240h+ppv], rax; int
0x180176cc2  lea     r9, [rbp+140h+var_1A0]
0x180176cc6  mov     r8d, 1
0x180176ccc  mov     rdx, [rsp+240h+var_1E8]
0x180176cd1  mov     rcx, rdi
0x180176cd4  mov     rax, rbx
0x180176cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176cdc  mov     ebx, eax
0x180176cde  test    eax, eax
0x180176ce0  jns     short loc_180176D55
0x180176ce2  mov     rcx, [rbp+148h]; this
0x180176ce9  mov     r9d, eax; char *
0x180176cec  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176cf3  mov     edx, 152h; void *
0x180176cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176cfd  nop
0x180176cfe  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176d03  call    cs:__imp_VariantClear
0x180176d09  nop
0x180176d0a  lea     rcx, [rsp+240h+var_1E8]
0x180176d0f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176d14  nop
0x180176d15  lea     rcx, [rsp+240h+var_1F8]
0x180176d1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176d1f  nop
0x180176d20  lea     rcx, [rsp+240h+var_1F0]
0x180176d25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176d2a  nop
0x180176d2b  lea     rcx, [rsp+240h+var_210]
0x180176d30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176d35  nop
0x180176d36  lea     rcx, [rsp+240h+var_208]
0x180176d3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176d40  nop
0x180176d41  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176d46  lea     rcx, [rbp+140h+var_180]; this
0x180176d4a  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176d4f  nop
0x180176d50  jmp     loc_180176F74
0x180176d55  mov     rcx, [rsp+240h+var_208]
0x180176d5a  mov     rax, [rcx]
0x180176d5d  mov     rax, [rax+18h]
0x180176d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176d66  mov     esi, eax
0x180176d68  test    eax, eax
0x180176d6a  jns     loc_180176F0E
0x180176d70  mov     rdi, [rsp+240h+var_210]
0x180176d75  mov     rdx, [rdi]
0x180176d78  mov     rbx, [rdx+98h]
0x180176d7f  lea     rcx, [rsp+240h+var_1F8]
0x180176d84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176d89  lea     rdx, [rsp+240h+var_1F8]
0x180176d8e  mov     rcx, rdi
0x180176d91  mov     rax, rbx
0x180176d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176d99  mov     ebx, eax
0x180176d9b  test    eax, eax
0x180176d9d  jns     short loc_180176E12
0x180176d9f  mov     rcx, [rbp+148h]; this
0x180176da6  mov     r9d, eax; char *
0x180176da9  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176db0  mov     edx, 158h; void *
0x180176db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176dba  nop
0x180176dbb  lea     rcx, [rsp+240h+pvarg]; pvarg
0x180176dc0  call    cs:__imp_VariantClear
0x180176dc6  nop
0x180176dc7  lea     rcx, [rsp+240h+var_1E8]
0x180176dcc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180176dd1  nop
0x180176dd2  lea     rcx, [rsp+240h+var_1F8]
0x180176dd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176ddc  nop
0x180176ddd  lea     rcx, [rsp+240h+var_1F0]
0x180176de2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176de7  nop
0x180176de8  lea     rcx, [rsp+240h+var_210]
0x180176ded  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176df2  nop
0x180176df3  lea     rcx, [rsp+240h+var_208]
0x180176df8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180176dfd  nop
0x180176dfe  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x180176e03  lea     rcx, [rbp+140h+var_180]; this
0x180176e07  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x180176e0c  nop
0x180176e0d  jmp     loc_180176F74
0x180176e12  mov     rcx, [rsp+240h+var_1F8]
0x180176e17  mov     rax, [rcx]
0x180176e1a  xor     r9d, r9d
0x180176e1d  lea     r8, [rsp+240h+var_1E0]
0x180176e22  lea     edx, [r9+1]
0x180176e26  mov     rax, [rax+18h]
0x180176e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180176e2f  mov     ebx, dword ptr [rsp+240h+var_1E0]
0x180176e33  mov     rcx, [rbp+148h]; this
0x180176e3a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176e41  test    ebx, ebx
0x180176e43  jns     short loc_180176EAA
  ... truncated ...
```
