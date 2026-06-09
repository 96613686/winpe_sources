# EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotRenameDevice(ushort const *)

- ea: `0x18017afa8`
- end: `0x18017b61d`
- name: `?AutoPilotRenameDevice@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBG@Z`
- size: `1653`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bdf58`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180084d5c`
- `0x18008a26c`
- `0x1800a3794`
- `0x18017a1a4`
- `0x18017afa8`
- `0x18017c63c`
- `0x18017c768`
- `0x18018528c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18017b065`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18017b065`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017b1bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18017b1bb`
- `OLEAUT32!__imp_SysAllocString` at `0x18017b0f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18017b0f5`
- `OLEAUT32!__imp_VariantInit` at `0x18017b04c`
- `OLEAUT32!__imp_VariantInit` at `0x18017b04c`
- `OLEAUT32!__imp_VariantClear` at `0x18017b098`
- `OLEAUT32!__imp_VariantClear` at `0x18017b131`
- `OLEAUT32!__imp_VariantClear` at `0x18017b1ee`
- `OLEAUT32!__imp_VariantClear` at `0x18017b29a`
- `OLEAUT32!__imp_VariantClear` at `0x18017b367`
- `OLEAUT32!__imp_VariantClear` at `0x18017b42a`
- `OLEAUT32!__imp_VariantClear` at `0x18017b4c8`
- `OLEAUT32!__imp_VariantClear` at `0x18017b533`
- `OLEAUT32!__imp_VariantClear` at `0x18017b5a1`
- `OLEAUT32!__imp_VariantClear` at `0x18017b098`
- `OLEAUT32!__imp_VariantClear` at `0x18017b131`
- `OLEAUT32!__imp_VariantClear` at `0x18017b1ee`
- `OLEAUT32!__imp_VariantClear` at `0x18017b29a`
- `OLEAUT32!__imp_VariantClear` at `0x18017b367`
- `OLEAUT32!__imp_VariantClear` at `0x18017b42a`
- `OLEAUT32!__imp_VariantClear` at `0x18017b4c8`
- `OLEAUT32!__imp_VariantClear` at `0x18017b533`
- `OLEAUT32!__imp_VariantClear` at `0x18017b5a1`

## string_xrefs

- `0x18017afd2`: `AutoPilotRenameDevice`
- `0x18017b035`: `ComputerName`

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
0x18017afa8  push    rbp
0x18017afaa  push    rbx
0x18017afab  push    rsi
0x18017afac  push    rdi
0x18017afad  lea     rbp, [rsp-128h]
0x18017afb5  sub     rsp, 228h
0x18017afbc  mov     rax, cs:__security_cookie
0x18017afc3  xor     rax, rsp
0x18017afc6  mov     [rbp+140h+var_30], rax
0x18017afcd  mov     [rsp+240h+psz], rcx
0x18017afd2  lea     rdx, aAutopilotrenam; "AutoPilotRenameDevice"
0x18017afd9  lea     rcx, [rbp+140h+var_180]; struct wil::details::IFailureCallback *
0x18017afdd  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18017afe2  lea     rax, ??_7AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::`vftable'
0x18017afe9  mov     [rbp+140h+var_180], rax
0x18017afed  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017aff2  lea     rcx, [rbp+140h+var_180]; this
0x18017aff6  call    ?StartActivity@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::StartActivity(ushort const *)
0x18017affb  nop
0x18017affc  lea     rax, [rbp+140h+var_180]
0x18017b000  mov     [rbp+140h+var_1C0], rax
0x18017b004  lea     rax, [rsp+240h+psz]
0x18017b009  mov     [rbp+140h+var_1B8], rax
0x18017b00d  mov     [rbp+140h+var_1B0], 1
0x18017b011  mov     [rsp+240h+var_208], 0
0x18017b01a  mov     [rsp+240h+var_210], 0
0x18017b023  mov     qword ptr [rsp+240h+var_1F0], 0
0x18017b02c  mov     [rsp+240h+var_1F8], 0
0x18017b035  lea     rdx, aComputername; "ComputerName"
0x18017b03c  lea     rcx, [rsp+240h+var_1E8]
0x18017b041  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18017b046  nop
0x18017b047  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b04c  call    cs:__imp_VariantInit
0x18017b053  nop     dword ptr [rax+rax+00h]
0x18017b058  nop
0x18017b059  mov     dword ptr [rsp+240h+var_1E0], 0
0x18017b061  xor     edx, edx; dwCoInit
0x18017b063  xor     ecx, ecx; pvReserved
0x18017b065  call    cs:__imp_CoInitializeEx
0x18017b06c  nop     dword ptr [rax+rax+00h]
0x18017b071  mov     ebx, eax
0x18017b073  test    eax, eax
0x18017b075  jns     short loc_18017B0F0
0x18017b077  mov     rcx, [rbp+148h]; this
0x18017b07e  mov     r9d, eax; char *
0x18017b081  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b088  mov     edx, 144h; void *
0x18017b08d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b092  nop
0x18017b093  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b098  call    cs:__imp_VariantClear
0x18017b09f  nop     dword ptr [rax+rax+00h]
0x18017b0a4  nop
0x18017b0a5  lea     rcx, [rsp+240h+var_1E8]
0x18017b0aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b0af  nop
0x18017b0b0  lea     rcx, [rsp+240h+var_1F8]
0x18017b0b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b0ba  nop
0x18017b0bb  lea     rcx, [rsp+240h+var_1F0]
0x18017b0c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b0c5  nop
0x18017b0c6  lea     rcx, [rsp+240h+var_210]
0x18017b0cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b0d0  nop
0x18017b0d1  lea     rcx, [rsp+240h+var_208]
0x18017b0d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b0db  nop
0x18017b0dc  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b0e1  lea     rcx, [rbp+140h+var_180]; this
0x18017b0e5  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b0ea  nop
0x18017b0eb  jmp     loc_18017B5F6
0x18017b0f0  mov     rcx, [rsp+240h+psz]; psz
0x18017b0f5  call    cs:__imp_SysAllocString
0x18017b0fc  nop     dword ptr [rax+rax+00h]
0x18017b101  mov     qword ptr [rsp+240h+pvarg+8], rax
0x18017b106  test    rax, rax
0x18017b109  jnz     short loc_18017B189
0x18017b10b  mov     rcx, [rbp+148h]; this
0x18017b112  mov     ebx, 8007000Eh
0x18017b117  mov     r9d, ebx; char *
0x18017b11a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b121  mov     edx, 14Bh; void *
0x18017b126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b12b  nop
0x18017b12c  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b131  call    cs:__imp_VariantClear
0x18017b138  nop     dword ptr [rax+rax+00h]
0x18017b13d  nop
0x18017b13e  lea     rcx, [rsp+240h+var_1E8]
0x18017b143  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b148  nop
0x18017b149  lea     rcx, [rsp+240h+var_1F8]
0x18017b14e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b153  nop
0x18017b154  lea     rcx, [rsp+240h+var_1F0]
0x18017b159  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b15e  nop
0x18017b15f  lea     rcx, [rsp+240h+var_210]
0x18017b164  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b169  nop
0x18017b16a  lea     rcx, [rsp+240h+var_208]
0x18017b16f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b174  nop
0x18017b175  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b17a  lea     rcx, [rbp+140h+var_180]; this
0x18017b17e  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b183  nop
0x18017b184  jmp     loc_18017B5F6
0x18017b189  mov     eax, 8
0x18017b18e  mov     word ptr [rsp+240h+pvarg], ax
0x18017b193  lea     rcx, [rsp+240h+var_208]
0x18017b198  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b19d  lea     rax, [rsp+240h+var_208]
0x18017b1a2  mov     qword ptr [rsp+240h+ppv], rax; int
0x18017b1a7  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18017b1ae  xor     edx, edx; pUnkOuter
0x18017b1b0  lea     r8d, [rdx+1]; dwClsContext
0x18017b1b4  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18017b1bb  call    cs:__imp_CoCreateInstance
0x18017b1c2  nop     dword ptr [rax+rax+00h]
0x18017b1c7  mov     ebx, eax
0x18017b1c9  test    eax, eax
0x18017b1cb  jns     short loc_18017B246
0x18017b1cd  mov     rcx, [rbp+148h]; this
0x18017b1d4  mov     r9d, eax; char *
0x18017b1d7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b1de  mov     edx, 14Eh; void *
0x18017b1e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b1e8  nop
0x18017b1e9  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b1ee  call    cs:__imp_VariantClear
0x18017b1f5  nop     dword ptr [rax+rax+00h]
0x18017b1fa  nop
0x18017b1fb  lea     rcx, [rsp+240h+var_1E8]
0x18017b200  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b205  nop
0x18017b206  lea     rcx, [rsp+240h+var_1F8]
0x18017b20b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b210  nop
0x18017b211  lea     rcx, [rsp+240h+var_1F0]
0x18017b216  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b21b  nop
0x18017b21c  lea     rcx, [rsp+240h+var_210]
0x18017b221  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b226  nop
0x18017b227  lea     rcx, [rsp+240h+var_208]
0x18017b22c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b231  nop
0x18017b232  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b237  lea     rcx, [rbp+140h+var_180]; this
0x18017b23b  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b240  nop
0x18017b241  jmp     loc_18017B5F6
0x18017b246  mov     rdi, [rsp+240h+var_208]
0x18017b24b  mov     rax, [rdi]
0x18017b24e  mov     rbx, [rax+50h]
0x18017b252  lea     rcx, [rsp+240h+var_210]
0x18017b257  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b25c  lea     r8, [rsp+240h+var_210]
0x18017b261  lea     rdx, aVendorMsftAcco; "./Vendor/MSFT/Accounts/Domain"
0x18017b268  mov     rcx, rdi
0x18017b26b  mov     rax, rbx
0x18017b26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b273  mov     ebx, eax
0x18017b275  test    eax, eax
0x18017b277  jns     short loc_18017B2F2
0x18017b279  mov     rcx, [rbp+148h]; this
0x18017b280  mov     r9d, eax; char *
0x18017b283  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b28a  mov     edx, 150h; void *
0x18017b28f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b294  nop
0x18017b295  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b29a  call    cs:__imp_VariantClear
0x18017b2a1  nop     dword ptr [rax+rax+00h]
0x18017b2a6  nop
0x18017b2a7  lea     rcx, [rsp+240h+var_1E8]
0x18017b2ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b2b1  nop
0x18017b2b2  lea     rcx, [rsp+240h+var_1F8]
0x18017b2b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b2bc  nop
0x18017b2bd  lea     rcx, [rsp+240h+var_1F0]
0x18017b2c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b2c7  nop
0x18017b2c8  lea     rcx, [rsp+240h+var_210]
0x18017b2cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b2d2  nop
0x18017b2d3  lea     rcx, [rsp+240h+var_208]
0x18017b2d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b2dd  nop
0x18017b2de  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b2e3  lea     rcx, [rbp+140h+var_180]; this
0x18017b2e7  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b2ec  nop
0x18017b2ed  jmp     loc_18017B5F6
0x18017b2f2  mov     rdi, [rsp+240h+var_210]
0x18017b2f7  mov     rax, [rdi]
0x18017b2fa  mov     rbx, [rax+18h]
0x18017b2fe  lea     rcx, [rsp+240h+var_1F0]
0x18017b303  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b308  movups  xmm0, xmmword ptr [rsp+240h+pvarg]
0x18017b30d  movaps  [rbp+140h+var_1A0], xmm0
0x18017b311  movsd   xmm1, qword ptr [rsp+240h+pvarg+10h]
0x18017b317  movsd   [rbp+140h+var_190], xmm1
0x18017b31c  lea     rax, [rsp+240h+var_1F0]
0x18017b321  mov     qword ptr [rsp+240h+ppv], rax; int
0x18017b326  lea     r9, [rbp+140h+var_1A0]
0x18017b32a  mov     r8d, 1
0x18017b330  mov     rdx, [rsp+240h+var_1E8]
0x18017b335  mov     rcx, rdi
0x18017b338  mov     rax, rbx
0x18017b33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b340  mov     ebx, eax
0x18017b342  test    eax, eax
0x18017b344  jns     short loc_18017B3BF
0x18017b346  mov     rcx, [rbp+148h]; this
0x18017b34d  mov     r9d, eax; char *
0x18017b350  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b357  mov     edx, 152h; void *
0x18017b35c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b361  nop
0x18017b362  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b367  call    cs:__imp_VariantClear
0x18017b36e  nop     dword ptr [rax+rax+00h]
0x18017b373  nop
0x18017b374  lea     rcx, [rsp+240h+var_1E8]
0x18017b379  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b37e  nop
0x18017b37f  lea     rcx, [rsp+240h+var_1F8]
0x18017b384  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b389  nop
0x18017b38a  lea     rcx, [rsp+240h+var_1F0]
0x18017b38f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b394  nop
0x18017b395  lea     rcx, [rsp+240h+var_210]
0x18017b39a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b39f  nop
0x18017b3a0  lea     rcx, [rsp+240h+var_208]
0x18017b3a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b3aa  nop
0x18017b3ab  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b3b0  lea     rcx, [rbp+140h+var_180]; this
0x18017b3b4  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b3b9  nop
0x18017b3ba  jmp     loc_18017B5F6
0x18017b3bf  mov     rcx, [rsp+240h+var_208]
0x18017b3c4  mov     rax, [rcx]
0x18017b3c7  mov     rax, [rax+18h]
0x18017b3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b3d0  mov     esi, eax
0x18017b3d2  test    eax, eax
0x18017b3d4  jns     loc_18017B58A
0x18017b3da  mov     rdi, [rsp+240h+var_210]
0x18017b3df  mov     rdx, [rdi]
0x18017b3e2  mov     rbx, [rdx+98h]
0x18017b3e9  lea     rcx, [rsp+240h+var_1F8]
0x18017b3ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b3f3  lea     rdx, [rsp+240h+var_1F8]
0x18017b3f8  mov     rcx, rdi
0x18017b3fb  mov     rax, rbx
0x18017b3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b403  mov     ebx, eax
0x18017b405  test    eax, eax
0x18017b407  jns     short loc_18017B482
0x18017b409  mov     rcx, [rbp+148h]; this
0x18017b410  mov     r9d, eax; char *
0x18017b413  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b41a  mov     edx, 158h; void *
0x18017b41f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b424  nop
0x18017b425  lea     rcx, [rsp+240h+pvarg]; pvarg
0x18017b42a  call    cs:__imp_VariantClear
0x18017b431  nop     dword ptr [rax+rax+00h]
0x18017b436  nop
0x18017b437  lea     rcx, [rsp+240h+var_1E8]
0x18017b43c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18017b441  nop
0x18017b442  lea     rcx, [rsp+240h+var_1F8]
0x18017b447  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b44c  nop
0x18017b44d  lea     rcx, [rsp+240h+var_1F0]
0x18017b452  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b457  nop
0x18017b458  lea     rcx, [rsp+240h+var_210]
0x18017b45d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b462  nop
0x18017b463  lea     rcx, [rsp+240h+var_208]
0x18017b468  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017b46d  nop
0x18017b46e  mov     rdx, [rsp+240h+psz]; unsigned __int16 *
0x18017b473  lea     rcx, [rbp+140h+var_180]; this
0x18017b477  call    ?Stop@AutoPilotRenameDevice@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutoPilotRenameDevice::Stop(ushort const *)
0x18017b47c  nop
0x18017b47d  jmp     loc_18017B5F6
0x18017b482  mov     rcx, [rsp+240h+var_1F8]
0x18017b487  mov     rax, [rcx]
  ... truncated ...
```
