# SystemSettings::StorageSenseHandlers::CAutoUpdate::SetValue(bool)

- ea: `0x1800ccd00`
- end: `0x1800cd299`
- name: `?SetValue@CAutoUpdate@StorageSenseHandlers@SystemSettings@@MEAAJ_N@Z`
- size: `1433`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAutoUpdate *__hidden this, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180019fa8`
- `0x180035f2c`
- `0x1800369a4`
- `0x1800ccd00`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ccd7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ccfa8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ccd7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ccfa8`

## string_xrefs

- `0x1800ccf7d`: `Windows.Management.Deployment.AutoUpdateSettingsOptions`
- `0x1800ccd53`: `Windows.Management.Deployment.AppInstallerManager`
- `0x1800ccd91`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800ccddb`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800cce3f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800ccecb`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800ccf30`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800ccfbb`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800cd038`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800cd0aa`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800cd121`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`
- `0x1800cd194`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\autoupdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAutoUpdate::SetValue(
        SystemSettings::StorageSenseHandlers::CAutoUpdate *this,
        char a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v37; // rcx
  int v38; // [rsp+20h] [rbp-49h]
  __int64 v39; // [rsp+30h] [rbp-39h] BYREF
  __int64 v40; // [rsp+38h] [rbp-31h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-29h] BYREF
  __int64 v42; // [rsp+48h] [rbp-21h] BYREF
  __int64 v43; // [rsp+50h] [rbp-19h] BYREF
  __int64 v44; // [rsp+58h] [rbp-11h] BYREF
  __int64 v45; // [rsp+60h] [rbp-9h] BYREF
  __int64 v46; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v48; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( *((_BYTE *)this + 241) != a2 )
  {
    v46 = 0;
    v48 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.AppInstallerManager",
      0x32u,
      0x31u);
    v4 = v48;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_c95a6ed5_fc59_5336_9b2e_2b07c5e61434, &v46);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v38);
LABEL_43:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
      return v6;
    }
    v40 = 0;
    v7 = v46;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v40);
    v9 = v8(v7, &v40);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v9,
        v38);
LABEL_42:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v40);
      goto LABEL_43;
    }
    v42 = 0;
    v41 = 0;
    v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (HSTRING *)&hstringHeader,
                      L"Windows.Management.Deployment.PackageManager");
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
            *v10,
            &v42);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = 138;
LABEL_8:
      v13 = (unsigned int)v11;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)v13,
        v38);
LABEL_41:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v42);
      goto LABEL_42;
    }
    v14 = v42;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v42 + 168LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v41);
    v11 = v15(v14, 0, *((_QWORD *)this + 31), &v41);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = 139;
      goto LABEL_8;
    }
    if ( !v41 )
    {
      v6 = -2147023728;
      v13 = 2147943568LL;
      v12 = 140;
      goto LABEL_9;
    }
    v39 = 0;
    v16 = (**v41)(v41, &GUID_8b1ad942_12d7_4754_ae4e_638cbc0e3a2e, &v39);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v16,
        v38);
      v17 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      goto LABEL_41;
    }
    v43 = 0;
    v18 = v39;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
    v20 = v19(v18, &v43);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v20,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v21 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      goto LABEL_41;
    }
    v45 = 0;
    v48 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.AutoUpdateSettingsOptions",
      0x38u,
      0x37u);
    v22 = v48;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
    v23 = RoGetActivationFactory(v22, &GUID_887b337d_0c05_54d0_bd49_3bb7a2c084cb, &v45);
    v6 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v23,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v24 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      goto LABEL_41;
    }
    v44 = 0;
    v25 = v45;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
    v27 = v26(v25, v43, &v44);
    v6 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v27,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v29 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      goto LABEL_41;
    }
    LOBYTE(v28) = a2;
    v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 184LL))(v44, v28);
    v6 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v30,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v31 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      goto LABEL_41;
    }
    v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v40 + 48LL))(
            v40,
            *((_QWORD *)this + 32),
            v44);
    v6 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v32,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v33 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      goto LABEL_41;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v40 + 64LL))(
            v40,
            *((_QWORD *)this + 32),
            -(__int64)(a2 == 0) & 0x7FFFFFFFFFFFFFFFLL);
    v6 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\autoupdate.cpp",
        (const char *)(unsigned int)v34,
        v38);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
      v35 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      goto LABEL_41;
    }
    *((_BYTE *)this + 241) = a2;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
    v37 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ccd00  mov     [rsp-8+arg_8], rbx
0x1800ccd05  mov     [rsp-8+arg_10], rsi
0x1800ccd0a  push    rbp
0x1800ccd0b  push    rdi
0x1800ccd0c  push    r12
0x1800ccd0e  push    r14
0x1800ccd10  push    r15
0x1800ccd12  lea     rbp, [rsp-37h]
0x1800ccd17  sub     rsp, 0A0h
0x1800ccd1e  mov     rax, cs:__security_cookie
0x1800ccd25  xor     rax, rsp
0x1800ccd28  mov     [rbp+57h+var_30], rax
0x1800ccd2c  mov     r14b, dl
0x1800ccd2f  mov     rsi, rcx
0x1800ccd32  cmp     [rcx+0F1h], dl
0x1800ccd38  jz      loc_1800CD26F
0x1800ccd3e  xor     r12d, r12d
0x1800ccd41  mov     [rbp+57h+var_58], r12
0x1800ccd45  mov     [rbp+57h+var_38], r12
0x1800ccd49  lea     r9d, [r12+31h]; unsigned int
0x1800ccd4e  lea     r8d, [r12+32h]; unsigned int
0x1800ccd53  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_AppInstallerManager@@3QBGB; "Windows.Management.Deployment.AppInstal"...
0x1800ccd5a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ccd5e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ccd63  mov     rbx, [rbp+57h+var_38]
0x1800ccd67  lea     rcx, [rbp+57h+var_58]
0x1800ccd6b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccd70  lea     r8, [rbp+57h+var_58]
0x1800ccd74  lea     rdx, _GUID_c95a6ed5_fc59_5336_9b2e_2b07c5e61434
0x1800ccd7b  mov     rcx, rbx
0x1800ccd7e  call    cs:__imp_RoGetActivationFactory
0x1800ccd84  mov     ebx, eax
0x1800ccd86  test    eax, eax
0x1800ccd88  jns     short loc_1800CCDA7
0x1800ccd8a  mov     rcx, [rbp+5Fh]; this
0x1800ccd8e  mov     r9d, eax; char *
0x1800ccd91  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ccd98  lea     edx, [r12+73h]; void *
0x1800ccd9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccda2  jmp     loc_1800CD1FC
0x1800ccda7  mov     [rbp+57h+var_88], r12
0x1800ccdab  mov     rdi, [rbp+57h+var_58]
0x1800ccdaf  mov     rax, [rdi]
0x1800ccdb2  mov     rbx, [rax+30h]
0x1800ccdb6  lea     rcx, [rbp+57h+var_88]
0x1800ccdba  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccdbf  lea     rdx, [rbp+57h+var_88]
0x1800ccdc3  mov     rcx, rdi
0x1800ccdc6  mov     rax, rbx
0x1800ccdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccdce  mov     ebx, eax
0x1800ccdd0  test    eax, eax
0x1800ccdd2  jns     short loc_1800CCDF1
0x1800ccdd4  mov     rcx, [rbp+5Fh]; this
0x1800ccdd8  mov     r9d, eax; char *
0x1800ccddb  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ccde2  mov     edx, 76h ; 'v'; void *
0x1800ccde7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccdec  jmp     loc_1800CD1F2
0x1800ccdf1  mov     al, r14b
0x1800ccdf4  neg     al
0x1800ccdf6  sbb     r15, r15
0x1800ccdf9  not     r15
0x1800ccdfc  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800cce06  and     r15, rax
0x1800cce09  mov     [rbp+57h+var_78], r12
0x1800cce0d  mov     [rbp+57h+var_80], r12
0x1800cce11  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800cce18  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800cce1c  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800cce21  lea     rdx, [rbp+57h+var_78]
0x1800cce25  mov     rcx, [rax]
0x1800cce28  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1800cce2d  mov     ebx, eax
0x1800cce2f  test    eax, eax
0x1800cce31  jns     short loc_1800CCE50
0x1800cce33  mov     edx, 8Ah; void *
0x1800cce38  mov     r9d, eax; char *
0x1800cce3b  mov     rcx, [rbp+5Fh]; this
0x1800cce3f  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800cce46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cce4b  jmp     loc_1800CD1DE
0x1800cce50  mov     rdi, [rbp+57h+var_78]
0x1800cce54  mov     rax, [rdi]
0x1800cce57  mov     rbx, [rax+0A8h]
0x1800cce5e  lea     rcx, [rbp+57h+var_80]
0x1800cce62  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cce67  lea     r9, [rbp+57h+var_80]
0x1800cce6b  mov     r8, [rsi+0F8h]
0x1800cce72  xor     edx, edx
0x1800cce74  mov     rcx, rdi
0x1800cce77  mov     rax, rbx
0x1800cce7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cce7f  mov     ebx, eax
0x1800cce81  test    eax, eax
0x1800cce83  jns     short loc_1800CCE8C
0x1800cce85  mov     edx, 8Bh
0x1800cce8a  jmp     short loc_1800CCE38
0x1800cce8c  mov     rcx, [rbp+57h+var_80]
0x1800cce90  test    rcx, rcx
0x1800cce93  jnz     short loc_1800CCEA4
0x1800cce95  mov     ebx, 80070490h
0x1800cce9a  mov     r9d, ebx
0x1800cce9d  mov     edx, 8Ch
0x1800ccea2  jmp     short loc_1800CCE3B
0x1800ccea4  mov     [rbp+57h+var_90], r12
0x1800ccea8  mov     rax, [rcx]
0x1800cceab  lea     r8, [rbp+57h+var_90]
0x1800cceaf  lea     rdx, _GUID_8b1ad942_12d7_4754_ae4e_638cbc0e3a2e
0x1800cceb6  mov     rax, [rax]
0x1800cceb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccebe  mov     ebx, eax
0x1800ccec0  test    eax, eax
0x1800ccec2  jns     short loc_1800CCEFC
0x1800ccec4  mov     rcx, [rbp+5Fh]; this
0x1800ccec8  mov     r9d, eax; char *
0x1800ccecb  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800cced2  mov     edx, 8Fh; void *
0x1800cced7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccedc  nop
0x1800ccedd  mov     rcx, [rbp+57h+var_90]
0x1800ccee1  test    rcx, rcx
0x1800ccee4  jz      short loc_1800CCEF7
0x1800ccee6  mov     [rbp+57h+var_90], r12
0x1800cceea  mov     rax, [rcx]
0x1800cceed  mov     rax, [rax+10h]
0x1800ccef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccef6  nop
0x1800ccef7  jmp     loc_1800CD1DE
0x1800ccefc  mov     [rbp+57h+var_70], r12
0x1800ccf00  mov     rdi, [rbp+57h+var_90]
0x1800ccf04  mov     rax, [rdi]
0x1800ccf07  mov     rbx, [rax+30h]
0x1800ccf0b  lea     rcx, [rbp+57h+var_70]
0x1800ccf0f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccf14  lea     rdx, [rbp+57h+var_70]
0x1800ccf18  mov     rcx, rdi
0x1800ccf1b  mov     rax, rbx
0x1800ccf1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf23  mov     ebx, eax
0x1800ccf25  test    eax, eax
0x1800ccf27  jns     short loc_1800CCF6B
0x1800ccf29  mov     rcx, [rbp+5Fh]; this
0x1800ccf2d  mov     r9d, eax; char *
0x1800ccf30  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ccf37  mov     edx, 92h; void *
0x1800ccf3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccf41  nop
0x1800ccf42  lea     rcx, [rbp+57h+var_70]
0x1800ccf46  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccf4b  nop
0x1800ccf4c  mov     rcx, [rbp+57h+var_90]
0x1800ccf50  test    rcx, rcx
0x1800ccf53  jz      short loc_1800CCF66
0x1800ccf55  mov     [rbp+57h+var_90], r12
0x1800ccf59  mov     rax, [rcx]
0x1800ccf5c  mov     rax, [rax+10h]
0x1800ccf60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccf65  nop
0x1800ccf66  jmp     loc_1800CD1DE
0x1800ccf6b  mov     [rbp+57h+var_60], r12
0x1800ccf6f  mov     [rbp+57h+var_38], r12
0x1800ccf73  mov     r9d, 37h ; '7'; unsigned int
0x1800ccf79  lea     r8d, [r9+1]; unsigned int
0x1800ccf7d  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_AutoUpdateSettingsOptions@@3QBGB; "Windows.Management.Deployment.AutoUpdat"...
0x1800ccf84  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ccf88  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ccf8d  mov     rbx, [rbp+57h+var_38]
0x1800ccf91  lea     rcx, [rbp+57h+var_60]
0x1800ccf95  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccf9a  lea     r8, [rbp+57h+var_60]
0x1800ccf9e  lea     rdx, _GUID_887b337d_0c05_54d0_bd49_3bb7a2c084cb
0x1800ccfa5  mov     rcx, rbx
0x1800ccfa8  call    cs:__imp_RoGetActivationFactory
0x1800ccfae  mov     ebx, eax
0x1800ccfb0  test    eax, eax
0x1800ccfb2  jns     short loc_1800CD000
0x1800ccfb4  mov     rcx, [rbp+5Fh]; this
0x1800ccfb8  mov     r9d, eax; char *
0x1800ccfbb  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ccfc2  mov     edx, 95h; void *
0x1800ccfc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccfcc  nop
0x1800ccfcd  lea     rcx, [rbp+57h+var_60]
0x1800ccfd1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccfd6  nop
0x1800ccfd7  lea     rcx, [rbp+57h+var_70]
0x1800ccfdb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ccfe0  nop
0x1800ccfe1  mov     rcx, [rbp+57h+var_90]
0x1800ccfe5  test    rcx, rcx
0x1800ccfe8  jz      short loc_1800CCFFB
0x1800ccfea  mov     [rbp+57h+var_90], r12
0x1800ccfee  mov     rax, [rcx]
0x1800ccff1  mov     rax, [rax+10h]
0x1800ccff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccffa  nop
0x1800ccffb  jmp     loc_1800CD1DE
0x1800cd000  mov     [rbp+57h+var_68], r12
0x1800cd004  mov     rdi, [rbp+57h+var_60]
0x1800cd008  mov     rax, [rdi]
0x1800cd00b  mov     rbx, [rax+30h]
0x1800cd00f  lea     rcx, [rbp+57h+var_68]
0x1800cd013  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd018  lea     r8, [rbp+57h+var_68]
0x1800cd01c  mov     rdx, [rbp+57h+var_70]
0x1800cd020  mov     rcx, rdi
0x1800cd023  mov     rax, rbx
0x1800cd026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd02b  mov     ebx, eax
0x1800cd02d  test    eax, eax
0x1800cd02f  jns     short loc_1800CD087
0x1800cd031  mov     rcx, [rbp+5Fh]; this
0x1800cd035  mov     r9d, eax; char *
0x1800cd038  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800cd03f  mov     edx, 98h; void *
0x1800cd044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd049  nop
0x1800cd04a  lea     rcx, [rbp+57h+var_68]
0x1800cd04e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd053  nop
0x1800cd054  lea     rcx, [rbp+57h+var_60]
0x1800cd058  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd05d  nop
0x1800cd05e  lea     rcx, [rbp+57h+var_70]
0x1800cd062  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd067  nop
0x1800cd068  mov     rcx, [rbp+57h+var_90]
0x1800cd06c  test    rcx, rcx
0x1800cd06f  jz      short loc_1800CD082
0x1800cd071  mov     [rbp+57h+var_90], r12
0x1800cd075  mov     rax, [rcx]
0x1800cd078  mov     rax, [rax+10h]
0x1800cd07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd081  nop
0x1800cd082  jmp     loc_1800CD1DE
0x1800cd087  mov     rcx, [rbp+57h+var_68]
0x1800cd08b  mov     rax, [rcx]
0x1800cd08e  mov     dl, r14b
0x1800cd091  mov     rax, [rax+0B8h]
0x1800cd098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd09d  mov     ebx, eax
0x1800cd09f  test    eax, eax
0x1800cd0a1  jns     short loc_1800CD0F9
0x1800cd0a3  mov     rcx, [rbp+5Fh]; this
0x1800cd0a7  mov     r9d, eax; char *
0x1800cd0aa  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800cd0b1  mov     edx, 9Ah; void *
0x1800cd0b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd0bb  nop
0x1800cd0bc  lea     rcx, [rbp+57h+var_68]
0x1800cd0c0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd0c5  nop
0x1800cd0c6  lea     rcx, [rbp+57h+var_60]
0x1800cd0ca  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd0cf  nop
0x1800cd0d0  lea     rcx, [rbp+57h+var_70]
0x1800cd0d4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd0d9  nop
0x1800cd0da  mov     rcx, [rbp+57h+var_90]
0x1800cd0de  test    rcx, rcx
0x1800cd0e1  jz      short loc_1800CD0F4
0x1800cd0e3  mov     [rbp+57h+var_90], r12
0x1800cd0e7  mov     rax, [rcx]
0x1800cd0ea  mov     rax, [rax+10h]
0x1800cd0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd0f3  nop
0x1800cd0f4  jmp     loc_1800CD1DE
0x1800cd0f9  mov     rcx, [rbp+57h+var_88]
0x1800cd0fd  mov     rax, [rcx]
0x1800cd100  mov     r8, [rbp+57h+var_68]
0x1800cd104  mov     rdx, [rsi+100h]
0x1800cd10b  mov     rax, [rax+30h]
0x1800cd10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd114  mov     ebx, eax
0x1800cd116  test    eax, eax
0x1800cd118  jns     short loc_1800CD16D
0x1800cd11a  mov     rcx, [rbp+5Fh]; this
0x1800cd11e  mov     r9d, eax; char *
0x1800cd121  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\coresettinghandlers"...
0x1800cd128  mov     edx, 9Bh; void *
0x1800cd12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd132  nop
0x1800cd133  lea     rcx, [rbp+57h+var_68]
0x1800cd137  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd13c  nop
0x1800cd13d  lea     rcx, [rbp+57h+var_60]
0x1800cd141  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd146  nop
0x1800cd147  lea     rcx, [rbp+57h+var_70]
0x1800cd14b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800cd150  nop
0x1800cd151  mov     rcx, [rbp+57h+var_90]
0x1800cd155  test    rcx, rcx
0x1800cd158  jz      short loc_1800CD16B
0x1800cd15a  mov     [rbp+57h+var_90], r12
0x1800cd15e  mov     rax, [rcx]
0x1800cd161  mov     rax, [rax+10h]
0x1800cd165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd16a  nop
  ... truncated ...
```
