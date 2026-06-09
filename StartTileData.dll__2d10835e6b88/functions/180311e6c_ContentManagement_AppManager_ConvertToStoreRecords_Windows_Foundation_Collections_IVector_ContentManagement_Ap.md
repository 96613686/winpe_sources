# ContentManagement::AppManager::ConvertToStoreRecords(Windows::Foundation::Collections::IVector<ContentManagement::AppInstallInfoRecord *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *> * *)

- ea: `0x180311e6c`
- end: `0x18031216b`
- name: `?ConvertToStoreRecords@AppManager@ContentManagement@@AEAAJPEAU?$IVector@PEAVAppInstallInfoRecord@ContentManagement@@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@456@@Z`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1803136b0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004ffc0`
- `0x180201e50`
- `0x180310160`
- `0x180310414`
- `0x180311e6c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031203b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180312049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803120b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803120e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180311f7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031203b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180312049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803120b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803120e2`

## string_xrefs

- `0x180311eee`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x18031207d`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x1803120a3`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x1803120cc`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x1803120f5`: `shellcommon\shell\contentdeliverymanager\utils\lib\appmanager\appmanager.cpp`
- `0x180311fb4`: `Windows.ApplicationModel.Store.Preview.InstallControl.Internal.InstallAppInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ContentManagement::AppManager::ConvertToStoreRecords(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  HSTRING v23; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  __int64 v25; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v6 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo,Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>>>(
         v5,
         &v28);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v27 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v27);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; i < v27; ++i )
      {
        v25 = 0;
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        v11 = v10(a2, i, &v25);
        v7 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x199,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v11,
            (int)v23);
          goto LABEL_26;
        }
        v23 = 0;
        v12 = v25;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL);
        WindowsDeleteString(0);
        v23 = 0;
        v14 = v13(v12, &v23);
        v7 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19B,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v14,
            (int)v23);
          goto LABEL_24;
        }
        string = 0;
        v15 = v25;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 64LL);
        WindowsDeleteString(0);
        string = 0;
        v17 = v16(v15, &string);
        v7 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19D,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v17,
            (int)v23);
          goto LABEL_22;
        }
        v26 = 0;
        v30 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.ApplicationModel.Store.Preview.InstallControl.Internal.InstallAppInfo",
          0x4Eu,
          0x4Du);
        v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IInstallAppInfo>>(
                v30,
                &v26);
        v7 = v18;
        if ( v18 < 0 )
        {
          v21 = 416;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
            (const char *)(unsigned int)v18,
            (int)v23);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
LABEL_22:
          WindowsDeleteString(string);
          string = 0;
LABEL_24:
          WindowsDeleteString(v23);
          v23 = 0;
LABEL_26:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          goto LABEL_30;
        }
        v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v26 + 56LL))(v26, v23);
        v7 = v18;
        if ( v18 < 0 )
        {
          v21 = 417;
          goto LABEL_20;
        }
        v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v26 + 104LL))(v26, string);
        v7 = v18;
        if ( v18 < 0 )
        {
          v21 = 418;
          goto LABEL_20;
        }
        v19 = *v28;
        v20 = v26;
        v26 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v19 + 104))(v28, v20);
        v7 = v18;
        if ( v18 < 0 )
        {
          v21 = 420;
          goto LABEL_20;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v23);
        v23 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      }
      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(*v28 + 64))(v28, a3);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v7 = 0;
        goto LABEL_30;
      }
      v8 = 423;
    }
    else
    {
      v8 = 405;
    }
  }
  else
  {
    v8 = 402;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\contentdeliverymanager\\utils\\lib\\appmanager\\appmanager.cpp",
    (const char *)(unsigned int)v6,
    (int)v23);
LABEL_30:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  return v7;
}

```

## disassembly

```asm
0x180311e6c  mov     [rsp-28h+arg_0], rbx
0x180311e71  mov     [rsp-28h+arg_18], rsi
0x180311e76  push    rbp
0x180311e77  push    rdi
0x180311e78  push    r12
0x180311e7a  push    r14
0x180311e7c  push    r15
0x180311e7e  mov     rbp, rsp
0x180311e81  sub     rsp, 80h
0x180311e88  mov     rax, cs:__security_cookie
0x180311e8f  xor     rax, rsp
0x180311e92  mov     [rbp+var_10], rax
0x180311e96  mov     r15, r8
0x180311e99  mov     r14, rdx
0x180311e9c  xor     r12d, r12d
0x180311e9f  mov     [r8], r12
0x180311ea2  mov     [rbp+var_38], r12
0x180311ea6  lea     rcx, [rbp+var_38]
0x180311eaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311eaf  lea     rdx, [rbp+var_38]
0x180311eb3  call    ??$CreateExternalObjectVector@VInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@V?$Vector@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@2Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@29Foundation@7@U?$DefaultVectorOptions@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@29Foundation@7@@2Collections@Foundation@7@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@2Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@29Foundation@7@U?$DefaultVectorOptions@PEAVInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@29Foundation@7@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo,Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::InstallAppInfo *>> * *)
0x180311eb8  mov     ebx, eax
0x180311eba  test    eax, eax
0x180311ebc  jns     short loc_180311EC5
0x180311ebe  mov     edx, 192h
0x180311ec3  jmp     short loc_180311EE7
0x180311ec5  mov     [rbp+var_40], r12d
0x180311ec9  mov     rax, [r14]
0x180311ecc  lea     rdx, [rbp+var_40]
0x180311ed0  mov     rcx, r14
0x180311ed3  mov     rax, [rax+38h]
0x180311ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311edc  mov     ebx, eax
0x180311ede  test    eax, eax
0x180311ee0  jns     short loc_180311EFF
0x180311ee2  mov     edx, 195h; void *
0x180311ee7  mov     rcx, [rbp+28h]; this
0x180311eeb  mov     r9d, eax; char *
0x180311eee  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180311ef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180311efa  jmp     loc_180312138
0x180311eff  mov     esi, r12d
0x180311f02  cmp     esi, [rbp+var_40]
0x180311f05  jnb     loc_180312112
0x180311f0b  mov     [rbp+var_50], r12
0x180311f0f  mov     rax, [r14]
0x180311f12  mov     rbx, [rax+30h]
0x180311f16  lea     rcx, [rbp+var_50]
0x180311f1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180311f1f  lea     r8, [rbp+var_50]
0x180311f23  mov     edx, esi
0x180311f25  mov     rcx, r14
0x180311f28  mov     rax, rbx
0x180311f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311f30  mov     ebx, eax
0x180311f32  test    eax, eax
0x180311f34  js      loc_1803120EE
0x180311f3a  mov     [rbp+var_60], r12
0x180311f3e  mov     rdi, [rbp+var_50]
0x180311f42  mov     rax, [rdi]
0x180311f45  mov     rbx, [rax+30h]
0x180311f49  xor     ecx, ecx; string
0x180311f4b  call    cs:__imp_WindowsDeleteString
0x180311f51  mov     [rbp+var_60], r12
0x180311f55  lea     rdx, [rbp+var_60]
0x180311f59  mov     rcx, rdi
0x180311f5c  mov     rax, rbx
0x180311f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311f64  mov     ebx, eax
0x180311f66  test    eax, eax
0x180311f68  js      loc_1803120C5
0x180311f6e  mov     [rbp+string], r12
0x180311f72  mov     rdi, [rbp+var_50]
0x180311f76  mov     rax, [rdi]
0x180311f79  mov     rbx, [rax+40h]
0x180311f7d  xor     ecx, ecx; string
0x180311f7f  call    cs:__imp_WindowsDeleteString
0x180311f85  mov     [rbp+string], r12
0x180311f89  lea     rdx, [rbp+string]
0x180311f8d  mov     rcx, rdi
0x180311f90  mov     rax, rbx
0x180311f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311f98  mov     ebx, eax
0x180311f9a  test    eax, eax
0x180311f9c  js      loc_18031209C
0x180311fa2  mov     [rbp+var_48], r12
0x180311fa6  mov     [rbp+var_18], r12
0x180311faa  mov     r9d, 4Dh ; 'M'; unsigned int
0x180311fb0  lea     r8d, [r9+1]; unsigned int
0x180311fb4  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_InstallAppInfo@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x180311fbb  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180311fbf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180311fc4  lea     rdx, [rbp+var_48]
0x180311fc8  mov     rcx, [rbp+var_18]
0x180311fcc  call    ??$ActivateInstance@V?$ComPtr@UIInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInstallAppInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IInstallAppInfo>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IInstallAppInfo>>)
0x180311fd1  mov     ebx, eax
0x180311fd3  test    eax, eax
0x180311fd5  js      loc_180312078
0x180311fdb  mov     rcx, [rbp+var_48]
0x180311fdf  mov     rax, [rcx]
0x180311fe2  mov     rdx, [rbp+var_60]
0x180311fe6  mov     rax, [rax+38h]
0x180311fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180311fef  mov     ebx, eax
0x180311ff1  test    eax, eax
0x180311ff3  js      short loc_180312071
0x180311ff5  mov     rcx, [rbp+var_48]
0x180311ff9  mov     rax, [rcx]
0x180311ffc  mov     rdx, [rbp+string]
0x180312000  mov     rax, [rax+68h]
0x180312004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180312009  mov     ebx, eax
0x18031200b  test    eax, eax
0x18031200d  js      short loc_18031206A
0x18031200f  mov     rcx, [rbp+var_38]
0x180312013  mov     rax, [rcx]
0x180312016  mov     rdx, [rbp+var_48]
0x18031201a  mov     [rbp+var_48], r12
0x18031201e  mov     rax, [rax+68h]
0x180312022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180312027  mov     ebx, eax
0x180312029  test    eax, eax
0x18031202b  js      short loc_180312063
0x18031202d  lea     rcx, [rbp+var_48]
0x180312031  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180312036  nop
0x180312037  mov     rcx, [rbp+string]; string
0x18031203b  call    cs:__imp_WindowsDeleteString
0x180312041  mov     [rbp+string], r12
0x180312045  mov     rcx, [rbp+var_60]; string
0x180312049  call    cs:__imp_WindowsDeleteString
0x18031204f  mov     [rbp+var_60], r12
0x180312053  lea     rcx, [rbp+var_50]
0x180312057  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031205c  inc     esi
0x18031205e  jmp     loc_180311F02
0x180312063  mov     edx, 1A4h
0x180312068  jmp     short loc_18031207D
0x18031206a  mov     edx, 1A2h
0x18031206f  jmp     short loc_18031207D
0x180312071  mov     edx, 1A1h
0x180312076  jmp     short loc_18031207D
0x180312078  mov     edx, 1A0h; void *
0x18031207d  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x180312084  mov     r9d, eax; char *
0x180312087  mov     rcx, [rbp+28h]; this
0x18031208b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180312090  nop
0x180312091  lea     rcx, [rbp+var_48]
0x180312095  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18031209a  jmp     short loc_1803120B5
0x18031209c  mov     rcx, [rbp+28h]; this
0x1803120a0  mov     r9d, eax; char *
0x1803120a3  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x1803120aa  mov     edx, 19Dh; void *
0x1803120af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803120b4  nop
0x1803120b5  mov     rcx, [rbp+string]; string
0x1803120b9  call    cs:__imp_WindowsDeleteString
0x1803120bf  mov     [rbp+string], r12
0x1803120c3  jmp     short loc_1803120DE
0x1803120c5  mov     rcx, [rbp+28h]; this
0x1803120c9  mov     r9d, eax; char *
0x1803120cc  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x1803120d3  mov     edx, 19Bh; void *
0x1803120d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803120dd  nop
0x1803120de  mov     rcx, [rbp+var_60]; string
0x1803120e2  call    cs:__imp_WindowsDeleteString
0x1803120e8  mov     [rbp+var_60], r12
0x1803120ec  jmp     short loc_180312107
0x1803120ee  mov     rcx, [rbp+28h]; this
0x1803120f2  mov     r9d, eax; char *
0x1803120f5  lea     r8, aShellcommonShe_98; "shellcommon\\shell\\contentdeliverymana"...
0x1803120fc  mov     edx, 199h; void *
0x180312101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180312106  nop
0x180312107  lea     rcx, [rbp+var_50]
0x18031210b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180312110  jmp     short loc_180312138
0x180312112  mov     rcx, [rbp+var_38]
0x180312116  mov     rax, [rcx]
0x180312119  mov     rdx, r15
0x18031211c  mov     rax, [rax+40h]
0x180312120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180312125  mov     ebx, eax
0x180312127  test    eax, eax
0x180312129  jns     short loc_180312135
0x18031212b  mov     edx, 1A7h
0x180312130  jmp     loc_180311EE7
0x180312135  mov     ebx, r12d
0x180312138  lea     rcx, [rbp+var_38]
0x18031213c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180312141  mov     eax, ebx
0x180312143  mov     rcx, [rbp+var_10]
0x180312147  xor     rcx, rsp; StackCookie
0x18031214a  call    __security_check_cookie
0x18031214f  lea     r11, [rsp+80h+var_s0]
0x180312157  mov     rbx, [r11+30h]
0x18031215b  mov     rsi, [r11+48h]
0x18031215f  mov     rsp, r11
0x180312162  pop     r15
0x180312164  pop     r14
0x180312166  pop     r12
0x180312168  pop     rdi
0x180312169  pop     rbp
0x18031216a  retn
```
