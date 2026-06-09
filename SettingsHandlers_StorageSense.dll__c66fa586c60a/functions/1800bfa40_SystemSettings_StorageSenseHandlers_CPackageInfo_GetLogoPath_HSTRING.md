# SystemSettings::StorageSenseHandlers::CPackageInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x1800bfa40`
- end: `0x1800bfd40`
- name: `?GetLogoPath@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `768`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180036c38`
- `0x1800a01b0`
- `0x1800ad168`
- `0x1800be1a8`
- `0x1800be3d4`
- `0x1800bfa40`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800bfd00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800bfd00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfcbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfcf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfcbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bfcf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageInfo::GetLogoPath(
        SystemSettings::StorageSenseHandlers::CPackageInfo *this,
        HSTRING *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  int v10; // eax
  HSTRING *v11; // rsi
  __int64 (__fastcall *v12)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *); // rbx
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  HSTRING *v16; // rax
  const unsigned __int16 *v17; // rdx
  HSTRING *v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, char *); // rbx
  int v25; // [rsp+20h] [rbp-39h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  int v27; // [rsp+38h] [rbp-21h] BYREF
  __int64 v28; // [rsp+40h] [rbp-19h] BYREF
  HSTRING string; // [rsp+48h] [rbp-11h] BYREF
  __int64 v30; // [rsp+50h] [rbp-9h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1h] BYREF
  HSTRING v32[4]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  v27 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4), &v27);
  if ( v5 < 0 )
  {
    v6 = 352;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v5,
      v25);
    return (unsigned int)v5;
  }
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_SettingsLogoLoader>::GetImpl'::`2'::impl,
    v4);
  if ( v27 )
  {
    v26 = 0;
    v8 = *((_QWORD *)this + 4);
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
    v10 = v9(v8, 0, &v26);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
        (const char *)(unsigned int)v10,
        v25);
LABEL_10:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
      return (unsigned int)v5;
    }
    if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 56LL))(v26, a2) >= 0 )
    {
      v5 = 0;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
  }
  v11 = (HSTRING *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
  {
    string = 0;
    v31 = 0;
    v28 = 0;
    v30 = 0;
    v26 = 0;
    v12 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *))(*(_QWORD *)this + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(this, &string);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 389;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
        (const char *)(unsigned int)v13,
        v25);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
      WindowsDeleteString(string);
      return (unsigned int)v5;
    }
    v16 = Windows::Internal::StringReference::StringReference(v32, (const unsigned __int16 (*)[41])v14);
    v13 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
            *v16,
            &v31);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 391;
      goto LABEL_25;
    }
    v18 = Windows::Internal::StringReference::StringReference(v32, (const unsigned __int16 (*)[57])v17);
    v13 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>(
            *v18,
            &v30);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 392;
      goto LABEL_25;
    }
    v19 = v31;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v31 + 368LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
    v13 = v20(v19, 0, string, &v28);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 394;
      goto LABEL_25;
    }
    v21 = v30;
    v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
    v13 = v22(v21, v28, &v26);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 396;
      goto LABEL_25;
    }
    v23 = v26;
    v24 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 72LL);
    WindowsDeleteString(*v11);
    *v11 = 0;
    v13 = v24(v23, (char *)this + 48);
    v5 = v13;
    if ( v13 < 0 )
    {
      v15 = 397;
      goto LABEL_25;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
    WindowsDeleteString(string);
  }
  v5 = WindowsDuplicateString(*v11, a2);
  if ( v5 < 0 )
  {
    v6 = 400;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bfa40  mov     [rsp-8+arg_10], rbx
0x1800bfa45  mov     [rsp-8+arg_18], rsi
0x1800bfa4a  push    rbp
0x1800bfa4b  push    rdi
0x1800bfa4c  push    r12
0x1800bfa4e  push    r14
0x1800bfa50  push    r15
0x1800bfa52  lea     rbp, [rsp-37h]
0x1800bfa57  sub     rsp, 90h
0x1800bfa5e  mov     rax, cs:__security_cookie
0x1800bfa65  xor     rax, rsp
0x1800bfa68  mov     [rbp+57h+var_30], rax
0x1800bfa6c  mov     r15, rdx
0x1800bfa6f  mov     r14, rcx
0x1800bfa72  xor     r12d, r12d
0x1800bfa75  mov     [rdx], r12
0x1800bfa78  mov     [rbp+57h+var_78], r12d
0x1800bfa7c  mov     rcx, [rcx+20h]
0x1800bfa80  mov     rax, [rcx]
0x1800bfa83  lea     rdx, [rbp+57h+var_78]
0x1800bfa87  mov     rax, [rax+38h]
0x1800bfa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa90  mov     ebx, eax
0x1800bfa92  test    eax, eax
0x1800bfa94  jns     short loc_1800BFAB5
0x1800bfa96  mov     edx, 160h; void *
0x1800bfa9b  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bfaa2  mov     r9d, ebx; char *
0x1800bfaa5  mov     rcx, [rbp+5Fh]; this
0x1800bfaa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfaae  mov     eax, ebx
0x1800bfab0  jmp     loc_1800BFD18
0x1800bfab5  mov     dl, 1
0x1800bfab7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader> `wil::Feature<__WilFeatureTraits_Feature_SettingsLogoLoader>::GetImpl(void)'::`2'::impl
0x1800bfabe  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SettingsLogoLoader@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsLogoLoader>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bfac3  cmp     [rbp+57h+var_78], r12d
0x1800bfac7  jbe     short loc_1800BFB43
0x1800bfac9  mov     [rbp+57h+var_80], r12
0x1800bfacd  mov     rdi, [r14+20h]
0x1800bfad1  mov     rax, [rdi]
0x1800bfad4  mov     rbx, [rax+30h]
0x1800bfad8  lea     rcx, [rbp+57h+var_80]
0x1800bfadc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfae1  lea     r8, [rbp+57h+var_80]
0x1800bfae5  xor     edx, edx
0x1800bfae7  mov     rcx, rdi
0x1800bfaea  mov     rax, rbx
0x1800bfaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfaf2  mov     ebx, eax
0x1800bfaf4  test    eax, eax
0x1800bfaf6  jns     short loc_1800BFB12
0x1800bfaf8  mov     rcx, [rbp+5Fh]; this
0x1800bfafc  mov     r9d, eax; char *
0x1800bfaff  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bfb06  mov     edx, 168h; void *
0x1800bfb0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfb10  jmp     short loc_1800BFB2C
0x1800bfb12  mov     rcx, [rbp+57h+var_80]
0x1800bfb16  mov     rax, [rcx]
0x1800bfb19  mov     rdx, r15
0x1800bfb1c  mov     rax, [rax+38h]
0x1800bfb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfb25  test    eax, eax
0x1800bfb27  js      short loc_1800BFB3A
0x1800bfb29  mov     ebx, r12d
0x1800bfb2c  lea     rcx, [rbp+57h+var_80]
0x1800bfb30  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfb35  jmp     loc_1800BFAAE
0x1800bfb3a  lea     rcx, [rbp+57h+var_80]
0x1800bfb3e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfb43  lea     rsi, [r14+30h]
0x1800bfb47  cmp     [rsi], r12
0x1800bfb4a  jnz     loc_1800BFCFA
0x1800bfb50  mov     [rbp+57h+string], r12
0x1800bfb54  mov     [rbp+57h+var_58], r12
0x1800bfb58  mov     [rbp+57h+var_70], r12
0x1800bfb5c  mov     [rbp+57h+var_60], r12
0x1800bfb60  mov     [rbp+57h+var_80], r12
0x1800bfb64  mov     rax, [r14]
0x1800bfb67  mov     rbx, [rax+50h]
0x1800bfb6b  xor     ecx, ecx; string
0x1800bfb6d  call    cs:__imp_WindowsDeleteString
0x1800bfb73  mov     [rbp+57h+string], r12
0x1800bfb77  lea     rdx, [rbp+57h+string]
0x1800bfb7b  mov     rcx, r14
0x1800bfb7e  mov     rax, rbx
0x1800bfb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfb86  mov     ebx, eax
0x1800bfb88  test    eax, eax
0x1800bfb8a  jns     short loc_1800BFB96
0x1800bfb8c  mov     edx, 185h
0x1800bfb91  jmp     loc_1800BFC7D
0x1800bfb96  lea     rcx, [rbp+57h+var_50]; string
0x1800bfb9a  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800bfb9f  lea     rdx, [rbp+57h+var_58]
0x1800bfba3  mov     rcx, [rax]
0x1800bfba6  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800bfbab  mov     ebx, eax
0x1800bfbad  test    eax, eax
0x1800bfbaf  jns     short loc_1800BFBBB
0x1800bfbb1  mov     edx, 187h
0x1800bfbb6  jmp     loc_1800BFC7D
0x1800bfbbb  lea     rcx, [rbp+57h+var_50]; string
0x1800bfbbf  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x1800bfbc4  lea     rdx, [rbp+57h+var_60]
0x1800bfbc8  mov     rcx, [rax]
0x1800bfbcb  call    ??$GetActivationFactory@V?$ComPtr@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>)
0x1800bfbd0  mov     ebx, eax
0x1800bfbd2  test    eax, eax
0x1800bfbd4  jns     short loc_1800BFBE0
0x1800bfbd6  mov     edx, 188h
0x1800bfbdb  jmp     loc_1800BFC7D
0x1800bfbe0  mov     rdi, [rbp+57h+var_58]
0x1800bfbe4  mov     rax, [rdi]
0x1800bfbe7  mov     rbx, [rax+170h]
0x1800bfbee  lea     rcx, [rbp+57h+var_70]
0x1800bfbf2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfbf7  lea     r9, [rbp+57h+var_70]
0x1800bfbfb  mov     r8, [rbp+57h+string]
0x1800bfbff  xor     edx, edx
0x1800bfc01  mov     rcx, rdi
0x1800bfc04  mov     rax, rbx
0x1800bfc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc0c  mov     ebx, eax
0x1800bfc0e  test    eax, eax
0x1800bfc10  jns     short loc_1800BFC19
0x1800bfc12  mov     edx, 18Ah
0x1800bfc17  jmp     short loc_1800BFC7D
0x1800bfc19  mov     rdi, [rbp+57h+var_60]
0x1800bfc1d  mov     rax, [rdi]
0x1800bfc20  mov     rbx, [rax+30h]
0x1800bfc24  lea     rcx, [rbp+57h+var_80]
0x1800bfc28  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfc2d  lea     r8, [rbp+57h+var_80]
0x1800bfc31  mov     rdx, [rbp+57h+var_70]
0x1800bfc35  mov     rcx, rdi
0x1800bfc38  mov     rax, rbx
0x1800bfc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc40  mov     ebx, eax
0x1800bfc42  test    eax, eax
0x1800bfc44  jns     short loc_1800BFC4D
0x1800bfc46  mov     edx, 18Ch
0x1800bfc4b  jmp     short loc_1800BFC7D
0x1800bfc4d  mov     rdi, [rbp+57h+var_80]
0x1800bfc51  mov     rax, [rdi]
0x1800bfc54  mov     rbx, [rax+48h]
0x1800bfc58  mov     rcx, [rsi]; string
0x1800bfc5b  call    cs:__imp_WindowsDeleteString
0x1800bfc61  mov     [rsi], r12
0x1800bfc64  mov     rdx, rsi
0x1800bfc67  mov     rcx, rdi
0x1800bfc6a  mov     rax, rbx
0x1800bfc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc72  mov     ebx, eax
0x1800bfc74  test    eax, eax
0x1800bfc76  jns     short loc_1800BFCC8
0x1800bfc78  mov     edx, 18Dh; void *
0x1800bfc7d  mov     r9d, eax; char *
0x1800bfc80  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bfc87  mov     rcx, [rbp+5Fh]; this
0x1800bfc8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfc90  nop
0x1800bfc91  lea     rcx, [rbp+57h+var_80]
0x1800bfc95  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfc9a  nop
0x1800bfc9b  lea     rcx, [rbp+57h+var_60]
0x1800bfc9f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfca4  nop
0x1800bfca5  lea     rcx, [rbp+57h+var_70]
0x1800bfca9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfcae  nop
0x1800bfcaf  lea     rcx, [rbp+57h+var_58]
0x1800bfcb3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfcb8  nop
0x1800bfcb9  mov     rcx, [rbp+57h+string]; string
0x1800bfcbd  call    cs:__imp_WindowsDeleteString
0x1800bfcc3  jmp     loc_1800BFAAE
0x1800bfcc8  lea     rcx, [rbp+57h+var_80]
0x1800bfccc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfcd1  nop
0x1800bfcd2  lea     rcx, [rbp+57h+var_60]
0x1800bfcd6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfcdb  nop
0x1800bfcdc  lea     rcx, [rbp+57h+var_70]
0x1800bfce0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfce5  nop
0x1800bfce6  lea     rcx, [rbp+57h+var_58]
0x1800bfcea  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bfcef  nop
0x1800bfcf0  mov     rcx, [rbp+57h+string]; string
0x1800bfcf4  call    cs:__imp_WindowsDeleteString
0x1800bfcfa  mov     rdx, r15; newString
0x1800bfcfd  mov     rcx, [rsi]; string
0x1800bfd00  call    cs:__imp_WindowsDuplicateString
0x1800bfd06  mov     ebx, eax
0x1800bfd08  test    eax, eax
0x1800bfd0a  jns     short loc_1800BFD16
0x1800bfd0c  mov     edx, 190h
0x1800bfd11  jmp     loc_1800BFA9B
0x1800bfd16  xor     eax, eax
0x1800bfd18  mov     rcx, [rbp+57h+var_30]
0x1800bfd1c  xor     rcx, rsp; StackCookie
0x1800bfd1f  call    __security_check_cookie
0x1800bfd24  lea     r11, [rsp+0B0h+var_20]
0x1800bfd2c  mov     rbx, [r11+40h]
0x1800bfd30  mov     rsi, [r11+48h]
0x1800bfd34  mov     rsp, r11
0x1800bfd37  pop     r15
0x1800bfd39  pop     r14
0x1800bfd3b  pop     r12
0x1800bfd3d  pop     rdi
0x1800bfd3e  pop     rbp
0x1800bfd3f  retn
```
