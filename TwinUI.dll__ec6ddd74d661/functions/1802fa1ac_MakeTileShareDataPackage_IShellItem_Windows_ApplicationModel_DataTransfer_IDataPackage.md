# MakeTileShareDataPackage(IShellItem *,Windows::ApplicationModel::DataTransfer::IDataPackage * *)

- ea: `0x1802fa1ac`
- end: `0x1802fa7ff`
- name: `?MakeTileShareDataPackage@@YAJPEAUIShellItem@@PEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `1619`
- prototype: `__int64 __fastcall(struct IShellItem *, struct Windows::ApplicationModel::DataTransfer::IDataPackage **)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802f59e0`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18000b314`
- `0x18000b370`
- `0x18000edd4`
- `0x18001c710`
- `0x18002fc18`
- `0x180053740`
- `0x18005d830`
- `0x180090bc8`
- `0x1800aa9a0`
- `0x1800bfa60`
- `0x18011f01c`
- `0x180142e10`
- `0x18015d430`
- `0x180269bdc`
- `0x18028c2c8`
- `0x1802999ac`
- `0x1802f9f18`
- `0x1802fa154`
- `0x1802fa1ac`
- `0x180372580`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa3c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa4cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa3c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802fa4cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fa556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fa5ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fa556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802fa5ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa24c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa7b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa7c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa24c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa2e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa7b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fa7c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802fa533`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802fa533`
- `WSClient!GetApplicationURL` at `0x1802fa263`
- `WSClient!GetApplicationURL` at `0x1802fa263`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1802fa6c5`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1802fa6c5`

## pseudocode

```c
__int64 __fastcall MakeTileShareDataPackage(
        struct IShellItem *a1,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage **a2)
{
  unsigned __int16 *v4; // rbx
  int ApplicationURL; // edi
  _QWORD *v6; // rax
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v7; // rsi
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *); // rdi
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rdi
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, PVOID); // rdi
  const unsigned __int16 *v13; // r14
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, PVOID); // rdi
  int Error; // eax
  const unsigned __int16 *v17; // r14
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v18; // rsi
  __int64 (__fastcall *v19)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, PVOID); // rdi
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  _QWORD *v22; // rax
  _WORD *v23; // rsi
  __int64 (__fastcall *v24)(_WORD *, PVOID, HSTRING *); // rdi
  _WORD *v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v29; // rax
  struct IShellItemVtbl *v30; // rax
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rdi
  int ScaleFactorForPart; // eax
  _WORD *v33; // rsi
  __int64 (__fastcall *v34)(_WORD *, __int64, __int64, __int64 *); // rdi
  __int64 v35; // rdx
  const unsigned __int16 *v36; // rdx
  _QWORD *v37; // rax
  const unsigned __int16 *v38; // rsi
  __int64 (__fastcall *v39)(const unsigned __int16 *, HSTRING, __int64 *); // rdi
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v42; // [rsp+38h] [rbp-61h] BYREF
  _WORD *v43; // [rsp+40h] [rbp-59h] BYREF
  __int64 v44; // [rsp+48h] [rbp-51h] BYREF
  struct Windows::ApplicationModel::DataTransfer::IDataPackage *v45; // [rsp+50h] [rbp-49h] BYREF
  __int64 v46; // [rsp+58h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-39h] BYREF
  __int64 v48; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-29h] BYREF
  __int64 v50; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v51[2]; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER v52; // [rsp+90h] [rbp-9h] BYREF
  __int64 v53; // [rsp+A8h] [rbp+Fh]

  *a2 = 0;
  v51[0] = 0;
  v4 = 0;
  v42 = 0;
  ApplicationURL = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(
                     (unsigned int)v51,
                     (_DWORD)a1,
                     1,
                     (unsigned int)&PKEY_AppUserModel_PackageFamilyName,
                     1);
  if ( ApplicationURL >= 0 )
  {
    CoTaskMemFree(0);
    *(_DWORD *)&v52.Reserved.Reserved2[16] = 17;
    *(_OWORD *)&v52.Reserved.Reserved1 = PKEY_AppUserModel_PackageFamilyName;
    CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v51, &v52, &v42);
    v49 = 0;
    CoTaskMemFree(0);
    v4 = (unsigned __int16 *)v42;
    ApplicationURL = GetApplicationURL(v42, &v49);
    if ( ApplicationURL >= 0 )
    {
      v45 = 0;
      v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                       (HSTRING *)&v52,
                       L"Windows.ApplicationModel.DataTransfer.DataPackage");
      ApplicationURL = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>(
                         *v6,
                         &v45);
      if ( ApplicationURL >= 0 )
      {
        v7 = v45;
        v48 = 0;
        v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *))(*(_QWORD *)v45 + 56LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v48);
        ApplicationURL = v8(v7, &v48);
        if ( ApplicationURL >= 0 )
        {
          lpVtbl = a1->lpVtbl;
          pv = 0;
          GetDisplayName = lpVtbl->GetDisplayName;
          CoTaskMemFree(0);
          ApplicationURL = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))GetDisplayName)(a1, 0, &pv);
          if ( ApplicationURL >= 0 )
          {
            v11 = v48;
            v12 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v48 + 56LL);
            Windows::Internal::StringReference::_ConstructorHelper(
              (Windows::Internal::StringReference *)&v52,
              (const unsigned __int16 *)pv);
            ApplicationURL = v12(v11, v52.Reserved.Reserved1);
            if ( ApplicationURL >= 0 )
            {
              v13 = (const unsigned __int16 *)ShellConstructMessageStringW(&_ImageBase, 9587, pv);
              LocalFree(0);
              v42 = v13;
              if ( v13 )
              {
                v14 = v48;
                v15 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v48 + 72LL);
                Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&v52, v13);
                Error = v15(v14, v52.Reserved.Reserved1);
              }
              else
              {
                Error = ResultFromKnownLastError();
              }
              ApplicationURL = Error;
              CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v42);
              if ( ApplicationURL >= 0 )
              {
                v17 = (const unsigned __int16 *)ShellConstructMessageStringW(&_ImageBase, 9588, pv);
                LocalFree(0);
                v42 = v17;
                if ( v17 )
                {
                  v18 = v45;
                  v19 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, PVOID))(*(_QWORD *)v45 + 128LL);
                  Windows::Internal::StringReference::_ConstructorHelper(
                    (Windows::Internal::StringReference *)&v52,
                    v17);
                  v20 = v19(v18, v52.Reserved.Reserved1);
                }
                else
                {
                  v20 = ResultFromKnownLastError();
                }
                ApplicationURL = v20;
                CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v42);
                if ( ApplicationURL >= 0 )
                {
                  v43 = 0;
                  v22 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                    (HSTRING *)&v52,
                                    (const unsigned __int16 (*)[23])v21);
                  ApplicationURL = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                                     *v22,
                                     &v43);
                  if ( ApplicationURL >= 0 )
                  {
                    v23 = v43;
                    string = 0;
                    v24 = *(__int64 (__fastcall **)(_WORD *, PVOID, HSTRING *))(*(_QWORD *)v43 + 48LL);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                    Windows::Internal::StringReference::_ConstructorHelper(
                      (Windows::Internal::StringReference *)&v52,
                      v49);
                    ApplicationURL = v24(v23, v52.Reserved.Reserved1, &string);
                    if ( ApplicationURL >= 0 )
                      ApplicationURL = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, HSTRING))(*(_QWORD *)v45 + 136LL))(
                                         v45,
                                         string);
                    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                  }
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                  if ( ApplicationURL >= 0 )
                  {
                    v25 = (_WORD *)ShellConstructMessageStringW(&_ImageBase, 9589, v49);
                    LocalFree(0);
                    v43 = v25;
                    if ( v25 && *v25 || (ApplicationURL = ResultFromKnownLastError(), ApplicationURL >= 0) )
                    {
                      v44 = 0;
                      v53 = 0;
                      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                        &v52,
                        L"Windows.ApplicationModel.DataTransfer.HtmlFormatHelper",
                        0x37u,
                        0x36u);
                      v26 = v53;
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                      ApplicationURL = RoGetActivationFactory(v26, &GUID_e22e7749_dd70_446f_aefc_61cee59f655e, &v44);
                      if ( ApplicationURL >= 0 )
                      {
                        v27 = v44;
                        string = 0;
                        v28 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v44 + 56LL);
                        WindowsDeleteString(0);
                        string = 0;
                        v42 = v25;
                        v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v52, &v42);
                        ApplicationURL = v28(v27, *(_QWORD *)(v29 + 24), &string);
                        if ( ApplicationURL >= 0 )
                          ApplicationURL = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, HSTRING))(*(_QWORD *)v45 + 144LL))(
                                             v45,
                                             string);
                        WindowsDeleteString(string);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                    }
                    CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(&v43);
                    if ( ApplicationURL >= 0 )
                    {
                      v30 = a1->lpVtbl;
                      v43 = 0;
                      QueryInterface = v30->QueryInterface;
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                      ApplicationURL = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, _WORD **))QueryInterface)(
                                         a1,
                                         &GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc,
                                         &v43);
                      if ( ApplicationURL >= 0 )
                      {
                        v50 = 0;
                        ScaleFactorForPart = CLauncherSettings::GetScaleFactorForPart();
                        v33 = v43;
                        v46 = 0;
                        if ( ScaleFactorForPart < 100 )
                          ScaleFactorForPart = 100;
                        LODWORD(v46) = (int)(float)((float)((float)ScaleFactorForPart * 30.0) / 100.0);
                        HIDWORD(v46) = v46;
                        v34 = *(__int64 (__fastcall **)(_WORD *, __int64, __int64, __int64 *))(*(_QWORD *)v43 + 32LL);
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v50);
                        ApplicationURL = v34(v33, v46, 9, &v50);
                        if ( ApplicationURL >= 0 )
                        {
                          LODWORD(string) = 0;
                          v46 = 0;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                          ApplicationURL = GetStreamFromSharedBitmap(v50, v35, &string);
                          if ( ApplicationURL >= 0 )
                          {
                            string = 0;
                            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                            ApplicationURL = CreateRandomAccessStreamOverStream(
                                               v46,
                                               0,
                                               &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                               &string);
                            if ( ApplicationURL >= 0 )
                            {
                              v42 = 0;
                              v37 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                                (HSTRING *)&v52,
                                                (const unsigned __int16 (*)[52])v36);
                              ApplicationURL = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>>(
                                                 *v37,
                                                 &v42);
                              if ( ApplicationURL >= 0 )
                              {
                                v38 = v42;
                                v44 = 0;
                                v39 = *(__int64 (__fastcall **)(const unsigned __int16 *, HSTRING, __int64 *))(*(_QWORD *)v42 + 64LL);
                                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                                ApplicationURL = v39(v38, string, &v44);
                                if ( ApplicationURL >= 0 )
                                  ApplicationURL = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 88LL))(
                                                     v48,
                                                     v44);
                                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v44);
                              }
                              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
                            }
                            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
                          }
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                        }
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v50);
                      }
                      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
                      if ( ApplicationURL >= 0 )
                      {
                        Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v45);
                        ApplicationURL = 0;
                        *a2 = v45;
                      }
                    }
                  }
                }
              }
            }
          }
          CoTaskMemFree(pv);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v48);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v45);
    }
    CoTaskMemFree(v49);
  }
  DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v51);
  CoTaskMemFree(v4);
  return (unsigned int)ApplicationURL;
}

```

## disassembly

```asm
0x1802fa1ac  mov     [rsp-8+arg_10], rbx
0x1802fa1b1  push    rbp
0x1802fa1b2  push    rsi
0x1802fa1b3  push    rdi
0x1802fa1b4  push    r12
0x1802fa1b6  push    r13
0x1802fa1b8  push    r14
0x1802fa1ba  push    r15
0x1802fa1bc  lea     rbp, [rsp-27h]
0x1802fa1c1  sub     rsp, 0C0h
0x1802fa1c8  mov     rax, cs:__security_cookie
0x1802fa1cf  xor     rax, rsp
0x1802fa1d2  mov     [rbp+57h+var_40], rax
0x1802fa1d6  xor     r13d, r13d
0x1802fa1d9  lea     r9, PKEY_AppUserModel_PackageFamilyName
0x1802fa1e0  mov     r12, rdx
0x1802fa1e3  mov     [rdx], r13
0x1802fa1e6  mov     r15, rcx
0x1802fa1e9  mov     [rbp+57h+var_70], r13
0x1802fa1ed  mov     rdx, rcx
0x1802fa1f0  mov     ebx, r13d
0x1802fa1f3  lea     r8d, [r13+1]
0x1802fa1f7  mov     [rbp+57h+var_B8], rbx
0x1802fa1fb  lea     rcx, [rbp+57h+var_70]
0x1802fa1ff  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x1802fa204  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x1802fa209  mov     edi, eax
0x1802fa20b  test    eax, eax
0x1802fa20d  js      loc_1802FA7BD
0x1802fa213  xor     ecx, ecx; pv
0x1802fa215  call    cs:__imp_CoTaskMemFree
0x1802fa21c  nop     dword ptr [rax+rax+00h]
0x1802fa221  movups  xmm0, cs:PKEY_AppUserModel_PackageFamilyName
0x1802fa228  mov     eax, cs:dword_1804222A8
0x1802fa22e  lea     r8, [rbp+57h+var_B8]
0x1802fa232  lea     rdx, [rbp+57h+var_60]
0x1802fa236  mov     [rbp+57h+var_50], eax
0x1802fa239  lea     rcx, [rbp+57h+var_70]
0x1802fa23d  movaps  xmmword ptr [rbp+57h+var_60], xmm0
0x1802fa241  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1802fa246  xor     ecx, ecx; pv
0x1802fa248  mov     [rbp+57h+var_80], r13
0x1802fa24c  call    cs:__imp_CoTaskMemFree
0x1802fa253  nop     dword ptr [rax+rax+00h]
0x1802fa258  mov     rbx, [rbp+57h+var_B8]
0x1802fa25c  lea     rdx, [rbp+57h+var_80]
0x1802fa260  mov     rcx, rbx
0x1802fa263  call    cs:__imp_GetApplicationURL
0x1802fa26a  nop     dword ptr [rax+rax+00h]
0x1802fa26f  mov     edi, eax
0x1802fa271  test    eax, eax
0x1802fa273  js      loc_1802FA7AD
0x1802fa279  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_DataPackage@@3QBGB; "Windows.ApplicationModel.DataTransfer.D"...
0x1802fa280  mov     [rbp+57h+var_A0], r13
0x1802fa284  lea     rcx, [rbp+57h+var_60]; string
0x1802fa288  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x1802fa28d  lea     rdx, [rbp+57h+var_A0]
0x1802fa291  mov     rcx, [rax]
0x1802fa294  call    ??$ActivateInstance@V?$ComPtr@UIDataPackage@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDataPackage@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IDataPackage>>)
0x1802fa299  mov     edi, eax
0x1802fa29b  test    eax, eax
0x1802fa29d  js      loc_1802FA7A4
0x1802fa2a3  mov     rsi, [rbp+57h+var_A0]
0x1802fa2a7  lea     rcx, [rbp+57h+var_88]
0x1802fa2ab  mov     [rbp+57h+var_88], r13
0x1802fa2af  mov     rax, [rsi]
0x1802fa2b2  mov     rdi, [rax+38h]
0x1802fa2b6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa2bb  lea     rdx, [rbp+57h+var_88]
0x1802fa2bf  mov     rcx, rsi
0x1802fa2c2  mov     rax, rdi
0x1802fa2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa2ca  mov     edi, eax
0x1802fa2cc  test    eax, eax
0x1802fa2ce  js      loc_1802FA79B
0x1802fa2d4  mov     rax, [r15]
0x1802fa2d7  xor     ecx, ecx; pv
0x1802fa2d9  mov     [rbp+57h+pv], r13
0x1802fa2dd  mov     rdi, [rax+28h]
0x1802fa2e1  call    cs:__imp_CoTaskMemFree
0x1802fa2e8  nop     dword ptr [rax+rax+00h]
0x1802fa2ed  lea     r8, [rbp+57h+pv]
0x1802fa2f1  xor     edx, edx
0x1802fa2f3  mov     rcx, r15
0x1802fa2f6  mov     rax, rdi
0x1802fa2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa2fe  mov     edi, eax
0x1802fa300  test    eax, eax
0x1802fa302  js      loc_1802FA78B
0x1802fa308  mov     rsi, [rbp+57h+var_88]
0x1802fa30c  lea     rcx, [rbp+57h+var_60]; this
0x1802fa310  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1802fa314  mov     rax, [rsi]
0x1802fa317  mov     rdi, [rax+38h]
0x1802fa31b  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802fa320  mov     rdx, [rbp+57h+var_60]
0x1802fa324  mov     rcx, rsi
0x1802fa327  mov     rax, rdi
0x1802fa32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa32f  mov     edi, eax
0x1802fa331  test    eax, eax
0x1802fa333  js      loc_1802FA78B
0x1802fa339  mov     r8, [rbp+57h+pv]
0x1802fa33d  lea     rcx, __ImageBase
0x1802fa344  mov     edx, 2573h
0x1802fa349  call    ShellConstructMessageStringW
0x1802fa34e  xor     ecx, ecx; hMem
0x1802fa350  mov     r14, rax
0x1802fa353  call    cs:__imp_LocalFree
0x1802fa35a  nop     dword ptr [rax+rax+00h]
0x1802fa35f  mov     [rbp+57h+var_B8], r14
0x1802fa363  test    r14, r14
0x1802fa366  jz      short loc_1802FA390
0x1802fa368  mov     rsi, [rbp+57h+var_88]
0x1802fa36c  mov     rdx, r14; unsigned __int16 *
0x1802fa36f  mov     rcx, [rsi]
0x1802fa372  mov     rdi, [rcx+48h]
0x1802fa376  lea     rcx, [rbp+57h+var_60]; this
0x1802fa37a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802fa37f  mov     rdx, [rbp+57h+var_60]
0x1802fa383  mov     rcx, rsi
0x1802fa386  mov     rax, rdi
0x1802fa389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa38e  jmp     short loc_1802FA395
0x1802fa390  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802fa395  lea     rcx, [rbp+57h+var_B8]
0x1802fa399  mov     edi, eax
0x1802fa39b  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802fa3a0  test    edi, edi
0x1802fa3a2  js      loc_1802FA78B
0x1802fa3a8  mov     r9, [rbp+57h+var_80]
0x1802fa3ac  lea     rcx, __ImageBase
0x1802fa3b3  mov     r8, [rbp+57h+pv]
0x1802fa3b7  mov     edx, 2574h
0x1802fa3bc  call    ShellConstructMessageStringW
0x1802fa3c1  xor     ecx, ecx; hMem
0x1802fa3c3  mov     r14, rax
0x1802fa3c6  call    cs:__imp_LocalFree
0x1802fa3cd  nop     dword ptr [rax+rax+00h]
0x1802fa3d2  mov     [rbp+57h+var_B8], r14
0x1802fa3d6  test    r14, r14
0x1802fa3d9  jz      short loc_1802FA406
0x1802fa3db  mov     rsi, [rbp+57h+var_A0]
0x1802fa3df  mov     rdx, r14; unsigned __int16 *
0x1802fa3e2  mov     rcx, [rsi]
0x1802fa3e5  mov     rdi, [rcx+80h]
0x1802fa3ec  lea     rcx, [rbp+57h+var_60]; this
0x1802fa3f0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802fa3f5  mov     rdx, [rbp+57h+var_60]
0x1802fa3f9  mov     rcx, rsi
0x1802fa3fc  mov     rax, rdi
0x1802fa3ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa404  jmp     short loc_1802FA40B
0x1802fa406  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802fa40b  lea     rcx, [rbp+57h+var_B8]
0x1802fa40f  mov     edi, eax
0x1802fa411  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802fa416  test    edi, edi
0x1802fa418  js      loc_1802FA78B
0x1802fa41e  lea     rcx, [rbp+57h+var_60]; string
0x1802fa422  mov     [rbp+57h+var_B0], r13
0x1802fa426  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x1802fa42b  lea     rdx, [rbp+57h+var_B0]
0x1802fa42f  mov     rcx, [rax]
0x1802fa432  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1802fa437  mov     edi, eax
0x1802fa439  test    eax, eax
0x1802fa43b  js      short loc_1802FA49D
0x1802fa43d  mov     rsi, [rbp+57h+var_B0]
0x1802fa441  lea     rcx, [rbp+57h+string]
0x1802fa445  mov     [rbp+57h+string], r13
0x1802fa449  mov     rax, [rsi]
0x1802fa44c  mov     rdi, [rax+30h]
0x1802fa450  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa455  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1802fa459  lea     rcx, [rbp+57h+var_60]; this
0x1802fa45d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1802fa462  mov     rdx, [rbp+57h+var_60]
0x1802fa466  lea     r8, [rbp+57h+string]
0x1802fa46a  mov     rcx, rsi
0x1802fa46d  mov     rax, rdi
0x1802fa470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa475  mov     edi, eax
0x1802fa477  test    eax, eax
0x1802fa479  js      short loc_1802FA494
0x1802fa47b  mov     rcx, [rbp+57h+var_A0]
0x1802fa47f  mov     rdx, [rbp+57h+string]
0x1802fa483  mov     rax, [rcx]
0x1802fa486  mov     rax, [rax+88h]
0x1802fa48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa492  mov     edi, eax
0x1802fa494  lea     rcx, [rbp+57h+string]
0x1802fa498  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa49d  lea     rcx, [rbp+57h+var_B0]
0x1802fa4a1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa4a6  test    edi, edi
0x1802fa4a8  js      loc_1802FA78B
0x1802fa4ae  mov     r9, [rbp+57h+pv]
0x1802fa4b2  lea     rcx, __ImageBase
0x1802fa4b9  mov     r8, [rbp+57h+var_80]
0x1802fa4bd  mov     edx, 2575h
0x1802fa4c2  call    ShellConstructMessageStringW
0x1802fa4c7  xor     ecx, ecx; hMem
0x1802fa4c9  mov     r14, rax
0x1802fa4cc  call    cs:__imp_LocalFree
0x1802fa4d3  nop     dword ptr [rax+rax+00h]
0x1802fa4d8  mov     [rbp+57h+var_B0], r14
0x1802fa4dc  test    r14, r14
0x1802fa4df  jz      short loc_1802FA4E7
0x1802fa4e1  cmp     [r14], r13w
0x1802fa4e5  jnz     short loc_1802FA4F6
0x1802fa4e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802fa4ec  mov     edi, eax
0x1802fa4ee  test    eax, eax
0x1802fa4f0  js      loc_1802FA5C2
0x1802fa4f6  mov     r9d, 36h ; '6'; unsigned int
0x1802fa4fc  mov     [rbp+57h+var_A8], r13
0x1802fa500  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_HtmlFormatHelper@@3QBGB; "Windows.ApplicationModel.DataTransfer.H"...
0x1802fa507  mov     [rbp+57h+var_48], r13
0x1802fa50b  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x1802fa50f  lea     r8d, [r9+1]; unsigned int
0x1802fa513  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802fa518  mov     rdi, [rbp+57h+var_48]
0x1802fa51c  lea     rcx, [rbp+57h+var_A8]
0x1802fa520  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa525  lea     r8, [rbp+57h+var_A8]
0x1802fa529  mov     rcx, rdi
0x1802fa52c  lea     rdx, _GUID_e22e7749_dd70_446f_aefc_61cee59f655e
0x1802fa533  call    cs:__imp_RoGetActivationFactory
0x1802fa53a  nop     dword ptr [rax+rax+00h]
0x1802fa53f  mov     edi, eax
0x1802fa541  test    eax, eax
0x1802fa543  js      short loc_1802FA5B9
0x1802fa545  mov     rsi, [rbp+57h+var_A8]
0x1802fa549  xor     ecx, ecx; string
0x1802fa54b  mov     [rbp+57h+string], r13
0x1802fa54f  mov     rax, [rsi]
0x1802fa552  mov     rdi, [rax+38h]
0x1802fa556  call    cs:__imp_WindowsDeleteString
0x1802fa55d  nop     dword ptr [rax+rax+00h]
0x1802fa562  lea     rdx, [rbp+57h+var_B8]
0x1802fa566  mov     [rbp+57h+string], r13
0x1802fa56a  lea     rcx, [rbp+57h+var_60]
0x1802fa56e  mov     [rbp+57h+var_B8], r14
0x1802fa572  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1802fa577  lea     r8, [rbp+57h+string]
0x1802fa57b  mov     rcx, rsi
0x1802fa57e  mov     rdx, [rax+18h]
0x1802fa582  mov     rax, rdi
0x1802fa585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa58a  mov     edi, eax
0x1802fa58c  test    eax, eax
0x1802fa58e  js      short loc_1802FA5A9
0x1802fa590  mov     rcx, [rbp+57h+var_A0]
0x1802fa594  mov     rdx, [rbp+57h+string]
0x1802fa598  mov     rax, [rcx]
0x1802fa59b  mov     rax, [rax+90h]
0x1802fa5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa5a7  mov     edi, eax
0x1802fa5a9  mov     rcx, [rbp+57h+string]; string
0x1802fa5ad  call    cs:__imp_WindowsDeleteString
0x1802fa5b4  nop     dword ptr [rax+rax+00h]
0x1802fa5b9  lea     rcx, [rbp+57h+var_A8]
0x1802fa5bd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa5c2  lea     rcx, [rbp+57h+var_B0]
0x1802fa5c6  call    ??1?$CMemString@UCMemString_PolicyLocalMem@@@@QEAA@XZ; CMemString<CMemString_PolicyLocalMem>::~CMemString<CMemString_PolicyLocalMem>(void)
0x1802fa5cb  test    edi, edi
0x1802fa5cd  js      loc_1802FA78B
0x1802fa5d3  mov     rax, [r15]
0x1802fa5d6  lea     rcx, [rbp+57h+var_B0]
0x1802fa5da  mov     [rbp+57h+var_B0], r13
0x1802fa5de  mov     rdi, [rax]
0x1802fa5e1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa5e6  lea     r8, [rbp+57h+var_B0]
0x1802fa5ea  mov     rcx, r15
0x1802fa5ed  lea     rdx, _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc
0x1802fa5f4  mov     rax, rdi
0x1802fa5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa5fc  mov     edi, eax
0x1802fa5fe  test    eax, eax
0x1802fa600  js      loc_1802FA76A
0x1802fa606  mov     [rbp+57h+var_78], r13
0x1802fa60a  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x1802fa60f  mov     rsi, [rbp+57h+var_B0]
0x1802fa613  xorps   xmm0, xmm0
0x1802fa616  mov     ecx, 64h ; 'd'
0x1802fa61b  mov     [rbp+57h+var_98], r13
0x1802fa61f  cmp     eax, ecx
0x1802fa621  cmovl   eax, ecx
0x1802fa624  lea     rcx, [rbp+57h+var_78]
0x1802fa628  cvtsi2ss xmm0, rax
0x1802fa62d  mulss   xmm0, cs:__real@41f00000
0x1802fa635  divss   xmm0, cs:__real@42c80000
0x1802fa63d  cvttss2si eax, xmm0
0x1802fa641  mov     dword ptr [rbp+57h+var_98], eax
0x1802fa644  mov     dword ptr [rbp+57h+var_98+4], eax
0x1802fa647  mov     rax, [rsi]
0x1802fa64a  mov     rdi, [rax+20h]
0x1802fa64e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802fa653  mov     rdx, [rbp+57h+var_98]
  ... truncated ...
```
