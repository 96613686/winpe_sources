# SystemSettings::StorageSenseHandlers::CAppPackageList::_EnumerateDependenciesByPackageManager(HSTRING__ *)

- ea: `0x1800ae294`
- end: `0x1800ae7f0`
- name: `?_EnumerateDependenciesByPackageManager@CAppPackageList@StorageSenseHandlers@SystemSettings@@IEAAJPEAUHSTRING__@@@Z`
- size: `1372`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppPackageList *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a4880`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180019fa8`
- `0x180035f2c`
- `0x1800369a4`
- `0x180036bfc`
- `0x180036c38`
- `0x1800a01b0`
- `0x1800ae294`
- `0x1800ae8b0`
- `0x1800bec40`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae52c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae6bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae74a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae52c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae6bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae74a`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppPackageList::_EnumerateDependenciesByPackageManager(
        SystemSettings::StorageSenseHandlers::CAppPackageList *this,
        const unsigned __int16 *a2)
{
  HSTRING *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HSTRING *v8; // rax
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, const unsigned __int16 *, __int64 *); // rbx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  unsigned int i; // r14d
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, _QWORD, _QWORD); // rbx
  int (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v21)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, HSTRING *); // rbx
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, _QWORD, HSTRING, __int64 *, __int64, __int64, struct SystemSettings::StorageSenseHandlers::CAppInfo **); // rbx
  __int64 v26; // rdi
  int (__fastcall *v27)(__int64, _QWORD, __int64, __int64 *); // rbx
  unsigned int j; // esi
  __int64 v29; // rdi
  int (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  __int64 v31; // rdi
  int (__fastcall *v32)(__int64, HSTRING *); // rbx
  __int64 v33; // rbx
  unsigned int v34; // edi
  HSTRING v35; // rsi
  __int64 v37; // [rsp+20h] [rbp-99h]
  __int64 v38; // [rsp+28h] [rbp-91h]
  struct SystemSettings::StorageSenseHandlers::CAppInfo **v39; // [rsp+30h] [rbp-89h]
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  char v41; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v42[7]; // [rsp+49h] [rbp-70h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v43; // [rsp+50h] [rbp-69h] BYREF
  __int64 v44; // [rsp+58h] [rbp-61h] BYREF
  __int64 v45; // [rsp+60h] [rbp-59h] BYREF
  __int64 v46; // [rsp+68h] [rbp-51h] BYREF
  __int64 v47; // [rsp+70h] [rbp-49h] BYREF
  __int64 v48; // [rsp+78h] [rbp-41h] BYREF
  HSTRING v49; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v50; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v51; // [rsp+8Ch] [rbp-2Dh] BYREF
  unsigned int v52; // [rsp+90h] [rbp-29h] BYREF
  int (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-21h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v58; // [rsp+C0h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v60; // [rsp+E0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v58 = 0;
  v55 = 0;
  v54 = 0;
  v52 = 0;
  v57 = 0;
  v56 = 0;
  v4 = Windows::Internal::StringReference::StringReference(
         (HSTRING *)&hstringHeader,
         (const unsigned __int16 (*)[41])a2);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         *v4,
         &v57);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 151;
LABEL_5:
    v9 = (unsigned int)v5;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)v9,
      v37);
    goto LABEL_42;
  }
  v8 = Windows::Internal::StringReference::StringReference(
         (HSTRING *)&hstringHeader,
         L"Windows.Internal.StateRepository.Application");
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
         *v8,
         &v56);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 152;
    goto LABEL_5;
  }
  v10 = (__int64 *)Windows::Internal::StringReference::StringReference(
                     (HSTRING *)&hstringHeader,
                     L"Windows.Management.Deployment.PackageManager");
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
         *v10,
         &v58);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 153;
    goto LABEL_5;
  }
  v11 = v58;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, __int64 *))(*(_QWORD *)v58 + 168LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v55);
  v5 = v12(v11, 0, a2, &v55);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 156;
    goto LABEL_5;
  }
  v13 = v55;
  if ( !v55 )
  {
    v6 = -2147023728;
    v9 = 2147943568LL;
    v7 = 157;
    goto LABEL_6;
  }
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 72LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
  v5 = v14(v13, &v54);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 158;
    goto LABEL_5;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v54 + 56LL))(v54, &v52);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 159;
    goto LABEL_5;
  }
  for ( i = 0; i < v52; ++i )
  {
    v53 = 0;
    v47 = 0;
    v46 = 0;
    v44 = 0;
    v45 = 0;
    string = 0;
    v42[0] = 0;
    v41 = 0;
    v50 = 0;
    v43 = 0;
    v16 = v54;
    v17 = *(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v54 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v53);
    if ( v17(v16, i, &v53) >= 0 )
    {
      v18 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v53;
      v19 = **v53;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v47);
      if ( v19(v18, &GUID_65aed1ae_b95b_450c_882b_6255187f397e, &v47) >= 0
        && ((int (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), char *))(*v53)[8])(v53, &v41) >= 0
        && !v41
        && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v47 + 56LL))(v47, v42) >= 0 )
      {
        if ( v42[0] )
        {
          v20 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v53;
          v21 = (*v53)[6];
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
          if ( ((int (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v21)(v20, &v46) >= 0 )
          {
            v22 = v46;
            v23 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 96LL);
            WindowsDeleteString(string);
            string = 0;
            if ( v23(v22, &string) >= 0 )
            {
              v24 = v57;
              v25 = *(int (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *, __int64, __int64, struct SystemSettings::StorageSenseHandlers::CAppInfo **))(*(_QWORD *)v57 + 368LL);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
              if ( v25(v24, 0, string, &v44, v37, v38, v39) >= 0 )
              {
                v51 = 0;
                if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 1008LL))(v44, &v51) >= 0 )
                {
                  v26 = v56;
                  v27 = *(int (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v56 + 304LL);
                  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
                  if ( v27(v26, 0, v44, &v45) >= 0
                    && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 56LL))(v45, &v50) >= 0 )
                  {
                    if ( v50 )
                    {
                      for ( j = 0; j < v50; ++j )
                      {
                        v49 = 0;
                        v48 = 0;
                        v29 = v45;
                        v30 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 48LL);
                        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v48);
                        if ( v30(v29, j, &v48) >= 0 )
                        {
                          v31 = v48;
                          v32 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 232LL);
                          WindowsDeleteString(v49);
                          v49 = 0;
                          if ( v32(v31, &v49) >= 0 )
                          {
                            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
                            v39 = &v43;
                            v38 = v48;
                            v37 = v44;
                            if ( (int)SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
                                        v49,
                                        string,
                                        32,
                                        v51) >= 0 )
                              SystemSettings::StorageSenseHandlers::CAppPackageList::_InsertApp(this, v43);
                          }
                        }
                        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v48);
                        WindowsDeleteString(v49);
                      }
                    }
                    else
                    {
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
                      v33 = v44;
                      v34 = v51;
                      v35 = string;
                      v60 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                        &hstringHeader,
                        &word_180106450,
                        1u,
                        0);
                      v39 = &v43;
                      v38 = 0;
                      v37 = v33;
                      if ( (int)SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
                                  v60,
                                  v35,
                                  32,
                                  v34) >= 0 )
                        SystemSettings::StorageSenseHandlers::CAppPackageList::_InsertApp(this, v43);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v43);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v53);
  }
  v6 = 0;
LABEL_42:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v58);
  return v6;
}

```

## disassembly

```asm
0x1800ae294  mov     [rsp-8+arg_10], rbx
0x1800ae299  mov     [rsp-8+arg_18], rsi
0x1800ae29e  push    rbp
0x1800ae29f  push    rdi
0x1800ae2a0  push    r12
0x1800ae2a2  push    r14
0x1800ae2a4  push    r15
0x1800ae2a6  lea     rbp, [rsp-37h]
0x1800ae2ab  sub     rsp, 0F0h
0x1800ae2b2  mov     rax, cs:__security_cookie
0x1800ae2b9  xor     rax, rsp
0x1800ae2bc  mov     [rbp+57h+var_28], rax
0x1800ae2c0  mov     rsi, rdx
0x1800ae2c3  mov     r15, rcx
0x1800ae2c6  xor     r12d, r12d
0x1800ae2c9  mov     [rbp+57h+var_50], r12
0x1800ae2cd  mov     [rbp+57h+var_68], r12
0x1800ae2d1  mov     [rbp+57h+var_70], r12
0x1800ae2d5  mov     [rbp+57h+var_80], r12d
0x1800ae2d9  mov     [rbp+57h+var_58], r12
0x1800ae2dd  mov     [rbp+57h+var_60], r12
0x1800ae2e1  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800ae2e5  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800ae2ea  lea     rdx, [rbp+57h+var_58]
0x1800ae2ee  mov     rcx, [rax]
0x1800ae2f1  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800ae2f6  mov     ebx, eax
0x1800ae2f8  test    eax, eax
0x1800ae2fa  jns     short loc_1800AE303
0x1800ae2fc  mov     edx, 97h
0x1800ae301  jmp     short loc_1800AE32A
0x1800ae303  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800ae30a  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800ae30e  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800ae313  lea     rdx, [rbp+57h+var_60]
0x1800ae317  mov     rcx, [rax]
0x1800ae31a  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800ae31f  mov     ebx, eax
0x1800ae321  test    eax, eax
0x1800ae323  jns     short loc_1800AE342
0x1800ae325  mov     edx, 98h; void *
0x1800ae32a  mov     r9d, eax; char *
0x1800ae32d  mov     rcx, [rbp+5Fh]; this
0x1800ae331  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ae338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae33d  jmp     loc_1800AE795
0x1800ae342  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800ae349  lea     rcx, [rbp+57h+hstringHeader]; string
0x1800ae34d  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800ae352  lea     rdx, [rbp+57h+var_50]
0x1800ae356  mov     rcx, [rax]
0x1800ae359  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1800ae35e  mov     ebx, eax
0x1800ae360  test    eax, eax
0x1800ae362  jns     short loc_1800AE36B
0x1800ae364  mov     edx, 99h
0x1800ae369  jmp     short loc_1800AE32A
0x1800ae36b  mov     rdi, [rbp+57h+var_50]
0x1800ae36f  mov     rax, [rdi]
0x1800ae372  mov     rbx, [rax+0A8h]
0x1800ae379  lea     rcx, [rbp+57h+var_68]
0x1800ae37d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae382  lea     r9, [rbp+57h+var_68]
0x1800ae386  mov     r8, rsi
0x1800ae389  xor     edx, edx
0x1800ae38b  mov     rcx, rdi
0x1800ae38e  mov     rax, rbx
0x1800ae391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae396  mov     ebx, eax
0x1800ae398  test    eax, eax
0x1800ae39a  jns     short loc_1800AE3A3
0x1800ae39c  mov     edx, 9Ch
0x1800ae3a1  jmp     short loc_1800AE32A
0x1800ae3a3  mov     rbx, [rbp+57h+var_68]
0x1800ae3a7  test    rbx, rbx
0x1800ae3aa  jnz     short loc_1800AE3BE
0x1800ae3ac  mov     ebx, 80070490h
0x1800ae3b1  mov     r9d, ebx
0x1800ae3b4  mov     edx, 9Dh
0x1800ae3b9  jmp     loc_1800AE32D
0x1800ae3be  mov     rax, [rbx]
0x1800ae3c1  mov     rdi, [rax+48h]
0x1800ae3c5  lea     rcx, [rbp+57h+var_70]
0x1800ae3c9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae3ce  lea     rdx, [rbp+57h+var_70]
0x1800ae3d2  mov     rcx, rbx
0x1800ae3d5  mov     rax, rdi
0x1800ae3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3dd  mov     ebx, eax
0x1800ae3df  test    eax, eax
0x1800ae3e1  jns     short loc_1800AE3ED
0x1800ae3e3  mov     edx, 9Eh
0x1800ae3e8  jmp     loc_1800AE32A
0x1800ae3ed  mov     rcx, [rbp+57h+var_70]
0x1800ae3f1  mov     rax, [rcx]
0x1800ae3f4  lea     rdx, [rbp+57h+var_80]
0x1800ae3f8  mov     rax, [rax+38h]
0x1800ae3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae401  mov     ebx, eax
0x1800ae403  test    eax, eax
0x1800ae405  jns     short loc_1800AE411
0x1800ae407  mov     edx, 9Fh
0x1800ae40c  jmp     loc_1800AE32A
0x1800ae411  mov     r14d, r12d
0x1800ae414  cmp     [rbp+57h+var_80], r12d
0x1800ae418  jbe     loc_1800AE792
0x1800ae41e  mov     [rbp+57h+var_78], r12
0x1800ae422  mov     [rbp+57h+var_A0], r12
0x1800ae426  mov     [rbp+57h+var_A8], r12
0x1800ae42a  mov     [rbp+57h+var_B8], r12
0x1800ae42e  mov     [rbp+57h+var_B0], r12
0x1800ae432  mov     [rbp+57h+string], r12
0x1800ae436  mov     [rbp+57h+var_C7], r12b
0x1800ae43a  mov     [rbp+57h+var_C8], r12b
0x1800ae43e  mov     [rbp+57h+var_88], r12d
0x1800ae442  mov     [rbp+57h+var_C0], r12
0x1800ae446  mov     rdi, [rbp+57h+var_70]
0x1800ae44a  mov     rax, [rdi]
0x1800ae44d  mov     rbx, [rax+30h]
0x1800ae451  lea     rcx, [rbp+57h+var_78]
0x1800ae455  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae45a  lea     r8, [rbp+57h+var_78]
0x1800ae45e  mov     edx, r14d
0x1800ae461  mov     rcx, rdi
0x1800ae464  mov     rax, rbx
0x1800ae467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae46c  test    eax, eax
0x1800ae46e  js      loc_1800AE73C
0x1800ae474  mov     rbx, [rbp+57h+var_78]
0x1800ae478  mov     rax, [rbx]
0x1800ae47b  mov     rdi, [rax]
0x1800ae47e  lea     rcx, [rbp+57h+var_A0]
0x1800ae482  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae487  lea     r8, [rbp+57h+var_A0]
0x1800ae48b  lea     rdx, _GUID_65aed1ae_b95b_450c_882b_6255187f397e
0x1800ae492  mov     rcx, rbx
0x1800ae495  mov     rax, rdi
0x1800ae498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae49d  nop
0x1800ae49e  test    eax, eax
0x1800ae4a0  js      loc_1800AE73C
0x1800ae4a6  mov     rcx, [rbp+57h+var_78]
0x1800ae4aa  mov     rax, [rcx]
0x1800ae4ad  lea     rdx, [rbp+57h+var_C8]
0x1800ae4b1  mov     rax, [rax+40h]
0x1800ae4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae4ba  test    eax, eax
0x1800ae4bc  js      loc_1800AE73C
0x1800ae4c2  cmp     [rbp+57h+var_C8], r12b
0x1800ae4c6  jnz     loc_1800AE73C
0x1800ae4cc  mov     rcx, [rbp+57h+var_A0]
0x1800ae4d0  mov     rax, [rcx]
0x1800ae4d3  lea     rdx, [rbp+57h+var_C7]
0x1800ae4d7  mov     rax, [rax+38h]
0x1800ae4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae4e0  test    eax, eax
0x1800ae4e2  js      loc_1800AE73C
0x1800ae4e8  cmp     [rbp+57h+var_C7], r12b
0x1800ae4ec  jz      loc_1800AE73C
0x1800ae4f2  mov     rdi, [rbp+57h+var_78]
0x1800ae4f6  mov     rax, [rdi]
0x1800ae4f9  mov     rbx, [rax+30h]
0x1800ae4fd  lea     rcx, [rbp+57h+var_A8]
0x1800ae501  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae506  lea     rdx, [rbp+57h+var_A8]
0x1800ae50a  mov     rcx, rdi
0x1800ae50d  mov     rax, rbx
0x1800ae510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae515  test    eax, eax
0x1800ae517  js      loc_1800AE73C
0x1800ae51d  mov     rdi, [rbp+57h+var_A8]
0x1800ae521  mov     rax, [rdi]
0x1800ae524  mov     rbx, [rax+60h]
0x1800ae528  mov     rcx, [rbp+57h+string]; string
0x1800ae52c  call    cs:__imp_WindowsDeleteString
0x1800ae532  mov     [rbp+57h+string], r12
0x1800ae536  lea     rdx, [rbp+57h+string]
0x1800ae53a  mov     rcx, rdi
0x1800ae53d  mov     rax, rbx
0x1800ae540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae545  test    eax, eax
0x1800ae547  js      loc_1800AE73C
0x1800ae54d  mov     rdi, [rbp+57h+var_58]
0x1800ae551  mov     rax, [rdi]
0x1800ae554  mov     rbx, [rax+170h]
0x1800ae55b  lea     rcx, [rbp+57h+var_B8]
0x1800ae55f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae564  lea     r9, [rbp+57h+var_B8]
0x1800ae568  mov     r8, [rbp+57h+string]
0x1800ae56c  xor     edx, edx
0x1800ae56e  mov     rcx, rdi
0x1800ae571  mov     rax, rbx
0x1800ae574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae579  test    eax, eax
0x1800ae57b  js      loc_1800AE73C
0x1800ae581  mov     [rbp+57h+var_84], r12d
0x1800ae585  mov     rcx, [rbp+57h+var_B8]
0x1800ae589  mov     rax, [rcx]
0x1800ae58c  lea     rdx, [rbp+57h+var_84]
0x1800ae590  mov     rax, [rax+3F0h]
0x1800ae597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae59c  test    eax, eax
0x1800ae59e  js      loc_1800AE73C
0x1800ae5a4  mov     rdi, [rbp+57h+var_60]
0x1800ae5a8  mov     rax, [rdi]
0x1800ae5ab  mov     rbx, [rax+130h]
0x1800ae5b2  lea     rcx, [rbp+57h+var_B0]
0x1800ae5b6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae5bb  lea     r9, [rbp+57h+var_B0]
0x1800ae5bf  mov     r8, [rbp+57h+var_B8]
0x1800ae5c3  xor     edx, edx
0x1800ae5c5  mov     rcx, rdi
0x1800ae5c8  mov     rax, rbx
0x1800ae5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae5d0  test    eax, eax
0x1800ae5d2  js      loc_1800AE73C
0x1800ae5d8  mov     rcx, [rbp+57h+var_B0]
0x1800ae5dc  mov     rax, [rcx]
0x1800ae5df  lea     rdx, [rbp+57h+var_88]
0x1800ae5e3  mov     rax, [rax+38h]
0x1800ae5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae5ec  test    eax, eax
0x1800ae5ee  js      loc_1800AE73C
0x1800ae5f4  mov     eax, [rbp+57h+var_88]
0x1800ae5f7  test    eax, eax
0x1800ae5f9  jz      loc_1800AE6CF
0x1800ae5ff  mov     esi, r12d
0x1800ae602  mov     [rbp+57h+var_90], r12
0x1800ae606  mov     [rbp+57h+var_98], r12
0x1800ae60a  mov     rdi, [rbp+57h+var_B0]
0x1800ae60e  mov     rax, [rdi]
0x1800ae611  mov     rbx, [rax+30h]
0x1800ae615  lea     rcx, [rbp+57h+var_98]
0x1800ae619  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae61e  lea     r8, [rbp+57h+var_98]
0x1800ae622  mov     edx, esi
0x1800ae624  mov     rcx, rdi
0x1800ae627  mov     rax, rbx
0x1800ae62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae62f  test    eax, eax
0x1800ae631  js      short loc_1800AE6AE
0x1800ae633  mov     rdi, [rbp+57h+var_98]
0x1800ae637  mov     rax, [rdi]
0x1800ae63a  mov     rbx, [rax+0E8h]
0x1800ae641  mov     rcx, [rbp+57h+var_90]; string
0x1800ae645  call    cs:__imp_WindowsDeleteString
0x1800ae64b  mov     [rbp+57h+var_90], r12
0x1800ae64f  lea     rdx, [rbp+57h+var_90]
0x1800ae653  mov     rcx, rdi
0x1800ae656  mov     rax, rbx
0x1800ae659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae65e  test    eax, eax
0x1800ae660  js      short loc_1800AE6AE
0x1800ae662  lea     rcx, [rbp+57h+var_C0]
0x1800ae666  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae66b  mov     rax, [rbp+57h+var_98]
0x1800ae66f  mov     r8, [rbp+57h+var_B8]
0x1800ae673  lea     rcx, [rbp+57h+var_C0]
0x1800ae677  mov     [rsp+110h+var_E0], rcx
0x1800ae67c  mov     [rsp+110h+var_E8], rax
0x1800ae681  mov     [rsp+110h+var_F0], r8
0x1800ae686  mov     r9d, [rbp+57h+var_84]
0x1800ae68a  mov     r8d, 20h ; ' '
0x1800ae690  mov     rdx, [rbp+57h+string]
0x1800ae694  mov     rcx, [rbp+57h+var_90]
0x1800ae698  call    ?CreateWithPackageOrigin@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@0W4PackageType@StateRepository@Internal@Windows@@W4PackageOrigin@678@PEAUIPackage@678@PEAUIApplication@678@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(HSTRING__ *,HSTRING__ *,Windows::Internal::StateRepository::PackageType,Windows::Internal::StateRepository::PackageOrigin,Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplication *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x1800ae69d  test    eax, eax
0x1800ae69f  js      short loc_1800AE6AE
0x1800ae6a1  mov     rdx, [rbp+57h+var_C0]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x1800ae6a5  mov     rcx, r15; this
0x1800ae6a8  call    ?_InsertApp@CAppPackageList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVCAppInfo@23@@Z; SystemSettings::StorageSenseHandlers::CAppPackageList::_InsertApp(SystemSettings::StorageSenseHandlers::CAppInfo *)
0x1800ae6ad  nop
0x1800ae6ae  lea     rcx, [rbp+57h+var_98]
0x1800ae6b2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae6b7  nop
0x1800ae6b8  mov     rcx, [rbp+57h+var_90]; string
0x1800ae6bc  call    cs:__imp_WindowsDeleteString
0x1800ae6c2  inc     esi
0x1800ae6c4  cmp     esi, [rbp+57h+var_88]
0x1800ae6c7  jb      loc_1800AE602
0x1800ae6cd  jmp     short loc_1800AE73C
0x1800ae6cf  lea     rcx, [rbp+57h+var_C0]
0x1800ae6d3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae6d8  mov     rbx, [rbp+57h+var_B8]
0x1800ae6dc  mov     edi, [rbp+57h+var_84]
0x1800ae6df  mov     rsi, [rbp+57h+string]
0x1800ae6e3  mov     [rbp+57h+var_30], r12
0x1800ae6e7  xor     r9d, r9d; unsigned int
0x1800ae6ea  lea     r8d, [r9+1]; unsigned int
0x1800ae6ee  lea     rdx, word_180106450; sourceString
0x1800ae6f5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ae6f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ae6fe  nop
0x1800ae6ff  lea     rax, [rbp+57h+var_C0]
0x1800ae703  mov     [rsp+110h+var_E0], rax
0x1800ae708  mov     [rsp+110h+var_E8], r12
0x1800ae70d  mov     [rsp+110h+var_F0], rbx
0x1800ae712  mov     r9d, edi
0x1800ae715  mov     r8d, 20h ; ' '
0x1800ae71b  mov     rdx, rsi
  ... truncated ...
```
