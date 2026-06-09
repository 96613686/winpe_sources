# AIComponentsAdminHelper::RemovePackageByUriForLocalService(ushort const *)

- ea: `0x140066e60`
- end: `0x140067101`
- name: `?RemovePackageByUriForLocalService@AIComponentsAdminHelper@@UEAAJPEBG@Z`
- size: `673`
- prototype: `__int64 __fastcall(AIComponentsAdminHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x140011b68`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140026d74`
- `0x1400598e0`
- `0x140063f1c`
- `0x140066e60`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140066f75`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140066f75`

## string_xrefs

- `0x140066f42`: `Windows.Foundation.Uri`
- `0x140066ec8`: `pcshell\shell\systemsettings\adminflows\aicomponents\aicomponentsadminhelperimpl.cpp`
- `0x140066f16`: `pcshell\shell\systemsettings\adminflows\aicomponents\aicomponentsadminhelperimpl.cpp`
- `0x140066f85`: `pcshell\shell\systemsettings\adminflows\aicomponents\aicomponentsadminhelperimpl.cpp`
- `0x140066fdd`: `pcshell\shell\systemsettings\adminflows\aicomponents\aicomponentsadminhelperimpl.cpp`
- `0x140067068`: `pcshell\shell\systemsettings\adminflows\aicomponents\aicomponentsadminhelperimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AIComponentsAdminHelper::RemovePackageByUriForLocalService(
        AIComponentsAdminHelper *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rdi
  int v7; // eax
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-69h]
  int v23; // [rsp+20h] [rbp-69h]
  __int64 v24; // [rsp+40h] [rbp-49h] BYREF
  __int64 v25; // [rsp+48h] [rbp-41h] BYREF
  __int64 v26; // [rsp+50h] [rbp-39h] BYREF
  __int64 v27; // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-29h] BYREF
  const unsigned __int16 *v29; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v31; // [rsp+88h] [rbp-1h]
  HSTRING_HEADER v32; // [rsp+90h] [rbp+7h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v29 = a2;
  v28 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Management.Deployment.Internal.PackageManagerInternal",
    0x3Eu,
    0x3Du);
  v2 = v31;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v28);
  v3 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(
         v2,
         &v28);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\aicomponents\\aicomponentsadminhelperimpl.cpp",
      (const char *)(unsigned int)v3,
      v22);
    goto LABEL_21;
  }
  v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
  v25 = 0;
  v6 = **v28;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v25);
  v7 = v6(v5, &GUID_bcca89ee_2919_4a60_9a07_088108eb486d, &v25);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\aicomponents\\aicomponentsadminhelperimpl.cpp",
      (const char *)(unsigned int)v7,
      v22);
LABEL_5:
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v25);
    goto LABEL_21;
  }
  v26 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v8 = v31;
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v26);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v26);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\aicomponents\\aicomponentsadminhelperimpl.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v22);
LABEL_8:
    Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v26);
    goto LABEL_5;
  }
  v10 = v26;
  v24 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL);
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v29);
  v13 = v11(v10, *(_QWORD *)(v12 + 24), &v24);
  v4 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\aicomponents\\aicomponentsadminhelperimpl.cpp",
      (const char *)(unsigned int)v13,
      v22);
    goto LABEL_11;
  }
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v32, L"S-1-5-19", 9u, 8u);
  v27 = 0;
  v23 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v25 + 56LL))(v25, v24, v33, 0x2000);
  v4 = v15;
  if ( v15 < 0 )
  {
    v19 = 26;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\aicomponents\\aicomponentsadminhelperimpl.cpp",
      (const char *)(unsigned int)v15,
      v23);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v33 = 0;
LABEL_11:
    v14 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_8;
  }
  v15 = Windows::Management::Deployment::WaitForDeploymentOperation(v16, v27, v17, v18, 0);
  v4 = v15;
  if ( v15 < 0 )
  {
    v19 = 27;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v20 = v24;
  v33 = 0;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v25);
  v4 = 0;
LABEL_21:
  Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(&v28);
  return v4;
}

```

## disassembly

```asm
0x140066e60  push    rbp
0x140066e62  push    rbx
0x140066e63  push    rsi
0x140066e64  push    rdi
0x140066e65  lea     rbp, [rsp-3Fh]
0x140066e6a  sub     rsp, 0C8h
0x140066e71  mov     rax, cs:__security_cookie
0x140066e78  xor     rax, rsp
0x140066e7b  mov     [rbp+57h+var_30], rax
0x140066e7f  xor     esi, esi
0x140066e81  mov     [rbp+57h+var_78], rdx
0x140066e85  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x140066e8c  mov     [rbp+57h+var_80], rsi
0x140066e90  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140066e94  mov     [rbp+57h+var_58], rsi
0x140066e98  lea     r9d, [rsi+3Dh]; unsigned int
0x140066e9c  lea     r8d, [rsi+3Eh]; unsigned int
0x140066ea0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140066ea5  mov     rbx, [rbp+57h+var_58]
0x140066ea9  lea     rcx, [rbp+57h+var_80]
0x140066ead  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x140066eb2  lea     rdx, [rbp+57h+var_80]
0x140066eb6  mov     rcx, rbx
0x140066eb9  call    ??$ActivateInstance@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManagerInternal@Internal@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::Internal::IPackageManagerInternal>(HSTRING__ *,Windows::Management::Deployment::Internal::IPackageManagerInternal * *)
0x140066ebe  mov     ebx, eax
0x140066ec0  test    eax, eax
0x140066ec2  jns     short loc_140066EDF
0x140066ec4  mov     rcx, [rbp+5Fh]; this
0x140066ec8  lea     r8, aPcshellShellSy_22; "pcshell\\shell\\systemsettings\\adminfl"...
0x140066ecf  mov     r9d, eax; char *
0x140066ed2  lea     edx, [rsi+0Bh]; void *
0x140066ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066eda  jmp     loc_1400670DE
0x140066edf  mov     rbx, [rbp+57h+var_80]
0x140066ee3  lea     rcx, [rbp+57h+var_98]
0x140066ee7  mov     [rbp+57h+var_98], rsi
0x140066eeb  mov     rax, [rbx]
0x140066eee  mov     rdi, [rax]
0x140066ef1  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x140066ef6  lea     r8, [rbp+57h+var_98]
0x140066efa  mov     rcx, rbx
0x140066efd  lea     rdx, _GUID_bcca89ee_2919_4a60_9a07_088108eb486d
0x140066f04  mov     rax, rdi
0x140066f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066f0c  mov     ebx, eax
0x140066f0e  test    eax, eax
0x140066f10  jns     short loc_140066F38
0x140066f12  mov     rcx, [rbp+5Fh]; this
0x140066f16  lea     r8, aPcshellShellSy_22; "pcshell\\shell\\systemsettings\\adminfl"...
0x140066f1d  mov     r9d, eax; char *
0x140066f20  mov     edx, 0Eh; void *
0x140066f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066f2a  lea     rcx, [rbp+57h+var_98]
0x140066f2e  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x140066f33  jmp     loc_1400670DE
0x140066f38  mov     r9d, 16h; unsigned int
0x140066f3e  mov     [rbp+57h+var_90], rsi
0x140066f42  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x140066f49  mov     [rbp+57h+var_58], rsi
0x140066f4d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140066f51  lea     r8d, [r9+1]; unsigned int
0x140066f55  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140066f5a  mov     rbx, [rbp+57h+var_58]
0x140066f5e  lea     rcx, [rbp+57h+var_90]
0x140066f62  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x140066f67  lea     r8, [rbp+57h+var_90]
0x140066f6b  mov     rcx, rbx
0x140066f6e  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x140066f75  call    cs:__imp_RoGetActivationFactory
0x140066f7b  mov     ebx, eax
0x140066f7d  test    eax, eax
0x140066f7f  jns     short loc_140066FA4
0x140066f81  mov     rcx, [rbp+5Fh]; this
0x140066f85  lea     r8, aPcshellShellSy_22; "pcshell\\shell\\systemsettings\\adminfl"...
0x140066f8c  mov     r9d, eax; char *
0x140066f8f  mov     edx, 11h; void *
0x140066f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066f99  lea     rcx, [rbp+57h+var_90]
0x140066f9d  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x140066fa2  jmp     short loc_140066F2A
0x140066fa4  mov     rdi, [rbp+57h+var_90]
0x140066fa8  lea     rdx, [rbp+57h+var_78]
0x140066fac  mov     [rbp+57h+var_A0], rsi
0x140066fb0  lea     rcx, [rbp+57h+hstringHeader]
0x140066fb4  mov     rax, [rdi]
0x140066fb7  mov     rbx, [rax+30h]
0x140066fbb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140066fc0  lea     r8, [rbp+57h+var_A0]
0x140066fc4  mov     rcx, rdi
0x140066fc7  mov     rdx, [rax+18h]
0x140066fcb  mov     rax, rbx
0x140066fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066fd3  mov     ebx, eax
0x140066fd5  test    eax, eax
0x140066fd7  jns     short loc_14006700C
0x140066fd9  mov     rcx, [rbp+5Fh]; this
0x140066fdd  lea     r8, aPcshellShellSy_22; "pcshell\\shell\\systemsettings\\adminfl"...
0x140066fe4  mov     r9d, eax; char *
0x140066fe7  mov     edx, 13h; void *
0x140066fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066ff1  mov     rcx, [rbp+57h+var_A0]
0x140066ff5  test    rcx, rcx
0x140066ff8  jz      short loc_140066F99
0x140066ffa  mov     [rbp+57h+var_A0], rsi
0x140066ffe  mov     rax, [rcx]
0x140067001  mov     rax, [rax+10h]
0x140067005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006700a  jmp     short loc_140066F99
0x14006700c  mov     r9d, 8; unsigned int
0x140067012  mov     [rbp+57h+var_38], rsi
0x140067016  lea     rdx, aS1519; "S-1-5-19"
0x14006701d  lea     rcx, [rbp+57h+var_50]; hstringHeader
0x140067021  lea     r8d, [r9+1]; unsigned int
0x140067025  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14006702a  mov     rcx, [rbp+57h+var_98]
0x14006702e  lea     rdx, [rbp+57h+var_88]
0x140067032  mov     r8, [rbp+57h+var_38]
0x140067036  mov     r9d, 2000h
0x14006703c  mov     [rsp+0E0h+var_B8], rdx
0x140067041  mov     rdx, [rbp+57h+var_A0]
0x140067045  mov     [rbp+57h+var_88], rsi
0x140067049  mov     rax, [rcx]
0x14006704c  mov     [rsp+0E0h+var_C0], esi; int
0x140067050  mov     rax, [rax+38h]
0x140067054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067059  mov     ebx, eax
0x14006705b  test    eax, eax
0x14006705d  jns     short loc_140067089
0x14006705f  mov     edx, 1Ah; void *
0x140067064  mov     rcx, [rbp+5Fh]; this
0x140067068  lea     r8, aPcshellShellSy_22; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006706f  mov     r9d, eax; char *
0x140067072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140067077  lea     rcx, [rbp+57h+var_88]
0x14006707b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140067080  mov     [rbp+57h+var_38], rsi
0x140067084  jmp     loc_140066FF1
0x140067089  mov     rdx, [rbp+57h+var_88]
0x14006708d  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x140067092  call    ?WaitForDeploymentOperation@Deployment@Management@Windows@@YAJKPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@3@PEAU?$IAsyncOperationProgressHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@53@PEAPEAUIDeploymentResult@123@@Z; Windows::Management::Deployment::WaitForDeploymentOperation(ulong,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,Windows::Management::Deployment::IDeploymentResult * *)
0x140067097  mov     ebx, eax
0x140067099  test    eax, eax
0x14006709b  jns     short loc_1400670A4
0x14006709d  mov     edx, 1Bh
0x1400670a2  jmp     short loc_140067064
0x1400670a4  lea     rcx, [rbp+57h+var_88]
0x1400670a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400670ad  mov     rcx, [rbp+57h+var_A0]
0x1400670b1  mov     [rbp+57h+var_38], rsi
0x1400670b5  test    rcx, rcx
0x1400670b8  jz      short loc_1400670CA
0x1400670ba  mov     [rbp+57h+var_A0], rsi
0x1400670be  mov     rax, [rcx]
0x1400670c1  mov     rax, [rax+10h]
0x1400670c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400670ca  lea     rcx, [rbp+57h+var_90]
0x1400670ce  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x1400670d3  lea     rcx, [rbp+57h+var_98]
0x1400670d7  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x1400670dc  mov     ebx, esi
0x1400670de  lea     rcx, [rbp+57h+var_80]
0x1400670e2  call    ?InternalRelease@?$ComPtr@UICbsSession9@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICbsSession9>::InternalRelease(void)
0x1400670e7  mov     eax, ebx
0x1400670e9  mov     rcx, [rbp+57h+var_30]
0x1400670ed  xor     rcx, rsp; StackCookie
0x1400670f0  call    __security_check_cookie
0x1400670f5  add     rsp, 0C8h
0x1400670fc  pop     rdi
0x1400670fd  pop     rsi
0x1400670fe  pop     rbx
0x1400670ff  pop     rbp
0x140067100  retn
```
