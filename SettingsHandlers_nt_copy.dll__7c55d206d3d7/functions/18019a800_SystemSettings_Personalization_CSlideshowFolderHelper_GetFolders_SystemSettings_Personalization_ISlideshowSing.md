# SystemSettings::Personalization::CSlideshowFolderHelper::GetFolders(SystemSettings::Personalization::ISlideshowSingleton *,Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>> * *)

- ea: `0x18019a800`
- end: `0x18019ad0e`
- name: `?GetFolders@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEAVISlideshowSingleton@23@PEAPEAV?$AgileObservableVector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@@Internal@Collections@Foundation@Windows@@@Z`
- size: `1294`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowFolderHelper *this)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180196390`
- `0x180199cb0`
- `0x18019a770`

## callees

- `0x18001098c`
- `0x180011bb0`
- `0x180019a20`
- `0x18001f3c8`
- `0x1800234f8`
- `0x18002b6bc`
- `0x1800320b0`
- `0x18003d280`
- `0x18003fdc0`
- `0x18004e884`
- `0x180110f6c`
- `0x180197ac8`
- `0x180197d50`
- `0x180199c78`
- `0x180199cb0`
- `0x18019a800`
- `0x18019b91c`
- `0x18019baf8`
- `0x18019bdf8`
- `0x1801cc7d8`
- `0x180220850`
- `0x180271dd4`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aa49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aa83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019abe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019acbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aa49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aa83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019aba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019abe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019acbc`
- `SHELL32!SHGetIDListFromObject` at `0x18019a9ef`
- `SHELL32!SHGetIDListFromObject` at `0x18019ab4e`
- `SHELL32!SHGetIDListFromObject` at `0x18019a9ef`
- `SHELL32!SHGetIDListFromObject` at `0x18019ab4e`
- `SHELL32!__imp_ILFree` at `0x18019aa91`
- `SHELL32!__imp_ILFree` at `0x18019abef`
- `SHELL32!__imp_ILFree` at `0x18019aa91`
- `SHELL32!__imp_ILFree` at `0x18019abef`

## string_xrefs

- `0x18019a939`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\slideshowcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::GetFolders(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        struct SystemSettings::Personalization::ISlideshowSingleton *a2,
        __int64 *a3)
{
  unsigned int v5; // edi
  __int64 *v6; // r14
  void *v7; // rax
  __int64 v8; // rbx
  int SlideshowFolderAndAddToCollection; // esi
  struct SystemSettings::Personalization::INDEX_PIDL_PAIR **v10; // r12
  const wchar_t *v11; // rax
  int Slideshow; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  char v16; // bl
  struct IShellItemArray *v17; // rdi
  HRESULT (__stdcall *GetItemAt)(IShellItemArray *, DWORD, IShellItem **); // rbx
  int v19; // eax
  ITEMIDLIST *v20; // rax
  LPITEMIDLIST v21; // rcx
  SystemSettings::DataModel *v22; // rax
  unsigned __int16 **v23; // r8
  const unsigned __int16 *v24; // rcx
  unsigned int v25; // edx
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // r8
  int DWORD; // eax
  int v29; // eax
  IUnknown *v30; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v32; // eax
  _QWORD *v33; // rax
  LPITEMIDLIST v34; // rcx
  SystemSettings::DataModel *v35; // rax
  unsigned __int16 **v36; // r8
  const unsigned __int16 *v37; // rcx
  bool v38; // zf
  __int64 v39; // rbx
  unsigned __int64 v40; // r14
  SystemSettings::Personalization::INDEX_PIDL_PAIR *v41; // rcx
  __int64 v42; // rcx
  int v43; // [rsp+20h] [rbp-69h]
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-59h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-51h] BYREF
  struct IShellItemArray *v46; // [rsp+40h] [rbp-49h] BYREF
  LPITEMIDLIST pidl; // [rsp+48h] [rbp-41h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-39h] BYREF
  struct SystemSettings::Personalization::INDEX_PIDL_PAIR **v49; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int64 v50; // [rsp+60h] [rbp-29h]
  __int64 v51; // [rsp+68h] [rbp-21h]
  __int64 v52; // [rsp+70h] [rbp-19h]
  _QWORD *v53; // [rsp+78h] [rbp-11h]
  __int64 v54; // [rsp+80h] [rbp-9h]
  __int64 v55; // [rsp+88h] [rbp-1h]
  __int64 v56; // [rsp+90h] [rbp+7h]
  __int64 v57; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  LPVOID pv; // [rsp+F0h] [rbp+67h] BYREF
  struct SystemSettings::Personalization::ISlideshowSingleton *v60; // [rsp+F8h] [rbp+6Fh]
  int v61; // [rsp+100h] [rbp+77h] BYREF
  int v62; // [rsp+108h] [rbp+7Fh] BYREF

  v60 = a2;
  v5 = 0;
  *a3 = 0;
  v6 = (__int64 *)((char *)this + 528);
  if ( *((_QWORD *)this + 66) )
  {
    SlideshowFolderAndAddToCollection = 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease((char *)this + 528);
    *v6 = 0;
    v7 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    pv = v7;
    v8 = 0;
    if ( v7 )
    {
      v8 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(v7);
      pv = 0;
    }
    Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(&pv);
    if ( v8 )
    {
      SlideshowFolderAndAddToCollection = 0;
      *v6 = v8;
    }
    else
    {
      SlideshowFolderAndAddToCollection = -2147024882;
    }
    if ( SlideshowFolderAndAddToCollection < 0 )
    {
LABEL_65:
      v42 = *a3;
      *a3 = 0;
      if ( v42 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<HSTRING__ *>,Windows::Foundation::Collections::IIterable<HSTRING__ *>,Windows::Foundation::Collections::IObservableVector<HSTRING__ *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
      *a3 = 0;
      return (unsigned int)SlideshowFolderAndAddToCollection;
    }
  }
  if ( !*((_BYTE *)this + 524) )
  {
    v10 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 696);
    if ( wcscmp_0(v11, L"Microsoft\\Windows\\BackgroundSlideshow") )
      goto LABEL_32;
    v46 = 0;
    ppv = 0;
    Slideshow = SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(&ppv);
    v13 = Slideshow;
    if ( Slideshow < 0 )
    {
      v14 = 388;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\slideshowcommon.cpp",
        (const char *)(unsigned int)Slideshow,
        v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      return v13;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Slideshow = SystemSettings::Personalization::DesktopWallpaperHelper::GetSlideshow(
                  (SystemSettings::Personalization::DesktopWallpaperHelper *)&ppv,
                  &v46);
    v13 = Slideshow;
    if ( Slideshow < 0 )
    {
      v14 = 389;
      goto LABEL_18;
    }
    v61 = 0;
    Slideshow = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))v46->lpVtbl->GetCount)(v46, &v61);
    v13 = Slideshow;
    if ( Slideshow < 0 )
    {
      v14 = 392;
      goto LABEL_18;
    }
    v16 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    if ( !v61 )
    {
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      if ( v16 )
        goto LABEL_48;
LABEL_32:
      LODWORD(pv) = 0;
      std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 568);
      v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 536);
      DWORD = SHRegGetDWORD(HKEY_CURRENT_USER, v26, v27, (unsigned int *)&pv);
      SlideshowFolderAndAddToCollection = DWORD;
      if ( DWORD < 0 )
      {
        v38 = (DWORD & 0x1FFF0000) == 458752;
        DWORD = (unsigned __int16)DWORD;
        if ( !v38 )
          DWORD = SlideshowFolderAndAddToCollection;
        if ( DWORD != 2 )
        {
LABEL_48:
          if ( SlideshowFolderAndAddToCollection >= 0 )
          {
            while ( v5 < v50 )
            {
              SlideshowFolderAndAddToCollection = SystemSettings::Personalization::CSlideshowFolderHelper::_CreateSlideshowFolderAndAddToCollection(
                                                    this,
                                                    v10[v5],
                                                    v60);
              v10[v5++] = 0;
              if ( SlideshowFolderAndAddToCollection < 0 )
                goto LABEL_53;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>>::InternalAddRef(v6);
            *a3 = *v6;
            SlideshowFolderAndAddToCollection = 0;
          }
LABEL_53:
          v39 = 0;
          if ( v50 )
          {
            v40 = v50;
            do
            {
              v41 = v10[v39];
              if ( v41 )
                SystemSettings::Personalization::INDEX_PIDL_PAIR::`scalar deleting destructor'(v41, v25);
              v39 = (unsigned int)(v39 + 1);
            }
            while ( (unsigned int)v39 < v40 );
            v6 = (__int64 *)((char *)this + 528);
          }
          if ( SlideshowFolderAndAddToCollection < 0 )
            Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*v6);
          else
            *((_BYTE *)this + 524) = 1;
          if ( v10 )
            CoTaskMemFree(v10);
          if ( SlideshowFolderAndAddToCollection >= 0 )
            return (unsigned int)SlideshowFolderAndAddToCollection;
          goto LABEL_65;
        }
        v29 = SystemSettings::Personalization::CSlideshowFolderHelper::_CreateAndSaveDefaultSourceDirectoryPIDLs(this);
      }
      else
      {
        v29 = SystemSettings::Personalization::CSlideshowFolderHelper::_LoadSourceDirectoriesFromRegistry(this, &v49);
      }
      v10 = v49;
      SlideshowFolderAndAddToCollection = v29;
      goto LABEL_48;
    }
    punk = 0;
    v17 = v46;
    GetItemAt = v46->lpVtbl->GetItemAt;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punk);
    v19 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, IUnknown **))GetItemAt)(v17, 0, &punk);
    v5 = 0;
    if ( v19 < 0 )
    {
LABEL_29:
      v16 = 0;
LABEL_30:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punk);
      goto LABEL_31;
    }
    v62 = 0;
    if ( ((int (__fastcall *)(IUnknown *, __int64, int *))punk->lpVtbl[2].QueryInterface)(punk, 0x20000000, &v62) >= 0
      && (v62 & 0x20000000) != 0 )
    {
      ppidl = 0;
      if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
      {
        v20 = (ITEMIDLIST *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        pidl = v20;
        v21 = ppidl;
        if ( v20 )
        {
          *(_DWORD *)&v20->mkid.cb = 1;
          *(_QWORD *)v20[2].mkid.abID = v21;
          v16 = 1;
          SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(this, ppidl, v60, 1, 0);
          pv = 0;
          CoTaskMemFree(0);
          v22 = (SystemSettings::DataModel *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 632);
          if ( (int)SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(
                      v22,
                      (const unsigned __int16 *)&pv,
                      v23) >= 0 )
            SetLastVisitedFolder(v24, (const unsigned __int16 *)pv, (struct IShellItem *)punk);
          CoTaskMemFree(pv);
          goto LABEL_30;
        }
        ILFree(ppidl);
      }
      goto LABEL_29;
    }
    ppidl = 0;
    v30 = punk;
    AddRef = punk->lpVtbl[1].AddRef;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppidl);
    v32 = ((__int64 (__fastcall *)(IUnknown *, LPITEMIDLIST *))AddRef)(v30, &ppidl);
    v5 = 0;
    if ( v32 >= 0 )
    {
      pidl = 0;
      if ( SHGetIDListFromObject((IUnknown *)ppidl, &pidl) >= 0 )
      {
        v33 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        v53 = v33;
        v34 = pidl;
        if ( v33 )
        {
          *(_DWORD *)v33 = 1;
          v33[1] = v34;
          v16 = 1;
          SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(this, pidl, v60, 1, 1);
          pv = 0;
          CoTaskMemFree(0);
          v35 = (SystemSettings::DataModel *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 632);
          if ( (int)SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(
                      v35,
                      (const unsigned __int16 *)&pv,
                      v36) >= 0 )
            SetLastVisitedFolder(v37, (const unsigned __int16 *)pv, (struct IShellItem *)ppidl);
          CoTaskMemFree(pv);
          goto LABEL_42;
        }
        ILFree(pidl);
      }
    }
    v16 = 0;
LABEL_42:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppidl);
    goto LABEL_30;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>>::InternalAddRef(v6);
  *a3 = *v6;
  return 0;
}

```

## disassembly

```asm
0x18019a800  mov     [rsp-8+arg_8], rdx
0x18019a805  push    rbp
0x18019a806  push    rbx
0x18019a807  push    rsi
0x18019a808  push    rdi
0x18019a809  push    r12
0x18019a80b  push    r13
0x18019a80d  push    r14
0x18019a80f  push    r15
0x18019a811  lea     rbp, [rsp-1Fh]
0x18019a816  sub     rsp, 0A8h
0x18019a81d  mov     r13, r8
0x18019a820  mov     r15, rcx
0x18019a823  xor     edi, edi
0x18019a825  mov     [r8], rdi
0x18019a828  lea     r14, [rcx+210h]
0x18019a82f  cmp     [r14], rdi
0x18019a832  jnz     short loc_18019A88E
0x18019a834  mov     rcx, r14
0x18019a837  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18019a83c  mov     [r14], rdi
0x18019a83f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019a846  mov     ecx, 0B8h; unsigned __int64
0x18019a84b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18019a850  mov     [rbp+57h+pv], rax
0x18019a854  mov     ebx, edi
0x18019a856  test    rax, rax
0x18019a859  jz      short loc_18019A86A
0x18019a85b  mov     rcx, rax
0x18019a85e  call    ??0?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *> const &,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::permission)
0x18019a863  mov     rbx, rax
0x18019a866  mov     [rbp+57h+pv], rdi
0x18019a86a  lea     rcx, [rbp+57h+pv]
0x18019a86e  call    ??1?$MakeAllocator@VCBrailleTableLanguageOutputSetting@Accessibility@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(void)
0x18019a873  test    rbx, rbx
0x18019a876  jz      short loc_18019A87F
0x18019a878  mov     esi, edi
0x18019a87a  mov     [r14], rbx
0x18019a87d  jmp     short loc_18019A884
0x18019a87f  mov     esi, 8007000Eh
0x18019a884  test    esi, esi
0x18019a886  js      loc_18019ACCE
0x18019a88c  jmp     short loc_18019A890
0x18019a88e  mov     esi, edi
0x18019a890  cmp     [r15+20Ch], dil
0x18019a897  jnz     loc_18019ACE6
0x18019a89d  mov     r12, rdi
0x18019a8a0  mov     [rbp+57h+var_88], rdi
0x18019a8a4  mov     [rbp+57h+var_80], rdi
0x18019a8a8  mov     [rbp+57h+var_78], rdi
0x18019a8ac  mov     [rbp+57h+var_70], rdi
0x18019a8b0  lea     rcx, [r15+2B8h]
0x18019a8b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019a8bc  mov     rcx, rax; String1
0x18019a8bf  lea     rdx, aMicrosoftWindo_5; "Microsoft\\Windows\\BackgroundSlideshow"
0x18019a8c6  call    wcscmp_0
0x18019a8cb  test    eax, eax
0x18019a8cd  jnz     loc_18019AAC5
0x18019a8d3  mov     [rbp+57h+var_A0], rdi
0x18019a8d7  mov     [rbp+57h+ppv], rdi
0x18019a8db  lea     rcx, [rbp+57h+ppv]; ppv
0x18019a8df  call    ?Initialize@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJXZ; SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(void)
0x18019a8e4  mov     ebx, eax
0x18019a8e6  test    eax, eax
0x18019a8e8  jns     short loc_18019A8F1
0x18019a8ea  mov     edx, 184h
0x18019a8ef  jmp     short loc_18019A936
0x18019a8f1  lea     rcx, [rbp+57h+var_A0]
0x18019a8f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019a8fa  lea     rdx, [rbp+57h+var_A0]; struct IShellItemArray **
0x18019a8fe  lea     rcx, [rbp+57h+ppv]; this
0x18019a902  call    ?GetSlideshow@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAPEAUIShellItemArray@@@Z; SystemSettings::Personalization::DesktopWallpaperHelper::GetSlideshow(IShellItemArray * *)
0x18019a907  mov     ebx, eax
0x18019a909  test    eax, eax
0x18019a90b  jns     short loc_18019A914
0x18019a90d  mov     edx, 185h
0x18019a912  jmp     short loc_18019A936
0x18019a914  mov     [rbp+57h+arg_10], edi
0x18019a917  mov     rcx, [rbp+57h+var_A0]
0x18019a91b  mov     rax, [rcx]
0x18019a91e  lea     rdx, [rbp+57h+arg_10]
0x18019a922  mov     rax, [rax+38h]
0x18019a926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a92b  mov     ebx, eax
0x18019a92d  test    eax, eax
0x18019a92f  jns     short loc_18019A965
0x18019a931  mov     edx, 188h; void *
0x18019a936  mov     r9d, eax; char *
0x18019a939  lea     r8, aShellSystemset_5; "shell\\systemsettingsthreshold\\handler"...
0x18019a940  mov     rcx, [rbp+5Fh]; this
0x18019a944  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019a949  nop
0x18019a94a  lea     rcx, [rbp+57h+ppv]
0x18019a94e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019a953  nop
0x18019a954  lea     rcx, [rbp+57h+var_A0]
0x18019a958  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019a95d  nop
0x18019a95e  mov     eax, ebx
0x18019a960  jmp     loc_18019ACF9
0x18019a965  mov     bl, dil
0x18019a968  mov     [rbp+57h+var_60], rdi
0x18019a96c  mov     [rbp+57h+var_58], rdi
0x18019a970  mov     [rbp+57h+var_50], rdi
0x18019a974  mov     [rbp+57h+var_48], rdi
0x18019a978  cmp     [rbp+57h+arg_10], edi
0x18019a97b  jbe     loc_18019AAAA
0x18019a981  mov     [rbp+57h+punk], rdi
0x18019a985  mov     rdi, [rbp+57h+var_A0]
0x18019a989  mov     rax, [rdi]
0x18019a98c  mov     rbx, [rax+40h]
0x18019a990  lea     rcx, [rbp+57h+punk]
0x18019a994  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019a999  lea     r8, [rbp+57h+punk]
0x18019a99d  xor     edx, edx
0x18019a99f  mov     rcx, rdi
0x18019a9a2  mov     rax, rbx
0x18019a9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a9aa  xor     edi, edi
0x18019a9ac  test    eax, eax
0x18019a9ae  js      loc_18019AA9D
0x18019a9b4  mov     [rbp+57h+arg_18], edi
0x18019a9b7  mov     rcx, [rbp+57h+punk]
0x18019a9bb  mov     rax, [rcx]
0x18019a9be  lea     r8, [rbp+57h+arg_18]
0x18019a9c2  mov     ebx, 20000000h
0x18019a9c7  mov     edx, ebx
0x18019a9c9  mov     rax, [rax+30h]
0x18019a9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a9d2  test    eax, eax
0x18019a9d4  js      loc_18019AB11
0x18019a9da  test    [rbp+57h+arg_18], ebx
0x18019a9dd  jz      loc_18019AB11
0x18019a9e3  mov     [rbp+57h+ppidl], rdi
0x18019a9e7  lea     rdx, [rbp+57h+ppidl]; ppidl
0x18019a9eb  mov     rcx, [rbp+57h+punk]; punk
0x18019a9ef  call    cs:__imp_SHGetIDListFromObject
0x18019a9f6  nop     dword ptr [rax+rax+00h]
0x18019a9fb  test    eax, eax
0x18019a9fd  js      loc_18019AA9D
0x18019aa03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019aa0a  lea     ecx, [rdi+10h]; unsigned __int64
0x18019aa0d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18019aa12  mov     [rbp+57h+pidl], rax
0x18019aa16  mov     rcx, [rbp+57h+ppidl]; pidl
0x18019aa1a  test    rax, rax
0x18019aa1d  jz      short loc_18019AA91
0x18019aa1f  mov     dword ptr [rax], 1
0x18019aa25  mov     [rax+8], rcx
0x18019aa29  mov     bl, 1
0x18019aa2b  mov     byte ptr [rsp+0E0h+var_C0], dil; bool
0x18019aa30  mov     r9b, bl; bool
0x18019aa33  mov     r8, [rbp+57h+arg_8]; struct SystemSettings::Personalization::ISlideshowSingleton *
0x18019aa37  mov     rdx, [rbp+57h+ppidl]; pidl
0x18019aa3b  mov     rcx, r15; this
0x18019aa3e  call    ?AddFolder@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEFBU_ITEMIDLIST@@PEAVISlideshowSingleton@23@_N2@Z; SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(_ITEMIDLIST const *,SystemSettings::Personalization::ISlideshowSingleton *,bool,bool)
0x18019aa43  mov     [rbp+57h+pv], rdi
0x18019aa47  xor     ecx, ecx; pv
0x18019aa49  call    cs:__imp_CoTaskMemFree
0x18019aa50  nop     dword ptr [rax+rax+00h]
0x18019aa55  lea     rcx, [r15+278h]
0x18019aa5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019aa61  lea     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18019aa65  mov     rcx, rax; this
0x18019aa68  call    ?GetCurrentProcessDefaultSettingsIdentifier@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(ushort const *,ushort * *)
0x18019aa6d  test    eax, eax
0x18019aa6f  js      short loc_18019AA7F
0x18019aa71  mov     r8, [rbp+57h+punk]; struct IShellItem *
0x18019aa75  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18019aa79  call    ?SetLastVisitedFolder@@YAJPEBG0PEAUIShellItem@@@Z; SetLastVisitedFolder(ushort const *,ushort const *,IShellItem *)
0x18019aa7e  nop
0x18019aa7f  mov     rcx, [rbp+57h+pv]; pv
0x18019aa83  call    cs:__imp_CoTaskMemFree
0x18019aa8a  nop     dword ptr [rax+rax+00h]
0x18019aa8f  jmp     short loc_18019AAA0
0x18019aa91  call    cs:__imp_ILFree
0x18019aa98  nop     dword ptr [rax+rax+00h]
0x18019aa9d  mov     bl, dil
0x18019aaa0  lea     rcx, [rbp+57h+punk]
0x18019aaa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aaa9  nop
0x18019aaaa  lea     rcx, [rbp+57h+ppv]
0x18019aaae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aab3  nop
0x18019aab4  lea     rcx, [rbp+57h+var_A0]
0x18019aab8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aabd  test    bl, bl
0x18019aabf  jnz     loc_18019AC34
0x18019aac5  mov     dword ptr [rbp+57h+pv], edi
0x18019aac8  lea     rcx, [r15+238h]
0x18019aacf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019aad4  mov     r8, rax
0x18019aad7  lea     rcx, [r15+218h]
0x18019aade  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019aae3  lea     r9, [rbp+57h+pv]; unsigned int *
0x18019aae7  mov     rdx, rax; unsigned __int16 *
0x18019aaea  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18019aaf1  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18019aaf6  mov     esi, eax
0x18019aaf8  test    eax, eax
0x18019aafa  js      loc_18019AC0C
0x18019ab00  lea     rdx, [rbp+57h+var_88]
0x18019ab04  mov     rcx, r15
0x18019ab07  call    ?_LoadSourceDirectoriesFromRegistry@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAV?$CCoSimpleArray@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@@@@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_LoadSourceDirectoriesFromRegistry(CCoSimpleArray<SystemSettings::Personalization::INDEX_PIDL_PAIR *,4294967294,CSimpleArrayStandardCompareHelper<SystemSettings::Personalization::INDEX_PIDL_PAIR *>> *)
0x18019ab0c  jmp     loc_18019AC2E
0x18019ab11  mov     [rbp+57h+ppidl], rdi
0x18019ab15  mov     rdi, [rbp+57h+punk]
0x18019ab19  mov     rax, [rdi]
0x18019ab1c  mov     rbx, [rax+20h]
0x18019ab20  lea     rcx, [rbp+57h+ppidl]
0x18019ab24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ab29  lea     rdx, [rbp+57h+ppidl]
0x18019ab2d  mov     rcx, rdi
0x18019ab30  mov     rax, rbx
0x18019ab33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab38  xor     edi, edi
0x18019ab3a  test    eax, eax
0x18019ab3c  js      loc_18019ABFB
0x18019ab42  mov     [rbp+57h+pidl], rdi
0x18019ab46  lea     rdx, [rbp+57h+pidl]; ppidl
0x18019ab4a  mov     rcx, [rbp+57h+ppidl]; punk
0x18019ab4e  call    cs:__imp_SHGetIDListFromObject
0x18019ab55  nop     dword ptr [rax+rax+00h]
0x18019ab5a  test    eax, eax
0x18019ab5c  js      loc_18019ABFB
0x18019ab62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019ab69  lea     ecx, [rdi+10h]; unsigned __int64
0x18019ab6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18019ab71  mov     [rbp+57h+var_68], rax
0x18019ab75  mov     rcx, [rbp+57h+pidl]; pidl
0x18019ab79  test    rax, rax
0x18019ab7c  jz      short loc_18019ABEF
0x18019ab7e  mov     dword ptr [rax], 1
0x18019ab84  mov     [rax+8], rcx
0x18019ab88  mov     bl, 1
0x18019ab8a  mov     byte ptr [rsp+0E0h+var_C0], bl; bool
0x18019ab8e  mov     r9b, bl; bool
0x18019ab91  mov     r8, [rbp+57h+arg_8]; struct SystemSettings::Personalization::ISlideshowSingleton *
0x18019ab95  mov     rdx, [rbp+57h+pidl]; pidl
0x18019ab99  mov     rcx, r15; this
0x18019ab9c  call    ?AddFolder@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEFBU_ITEMIDLIST@@PEAVISlideshowSingleton@23@_N2@Z; SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(_ITEMIDLIST const *,SystemSettings::Personalization::ISlideshowSingleton *,bool,bool)
0x18019aba1  mov     [rbp+57h+pv], rdi
0x18019aba5  xor     ecx, ecx; pv
0x18019aba7  call    cs:__imp_CoTaskMemFree
0x18019abae  nop     dword ptr [rax+rax+00h]
0x18019abb3  lea     rcx, [r15+278h]
0x18019abba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019abbf  lea     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18019abc3  mov     rcx, rax; this
0x18019abc6  call    ?GetCurrentProcessDefaultSettingsIdentifier@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetCurrentProcessDefaultSettingsIdentifier(ushort const *,ushort * *)
0x18019abcb  test    eax, eax
0x18019abcd  js      short loc_18019ABDD
0x18019abcf  mov     r8, [rbp+57h+ppidl]; struct IShellItem *
0x18019abd3  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18019abd7  call    ?SetLastVisitedFolder@@YAJPEBG0PEAUIShellItem@@@Z; SetLastVisitedFolder(ushort const *,ushort const *,IShellItem *)
0x18019abdc  nop
0x18019abdd  mov     rcx, [rbp+57h+pv]; pv
0x18019abe1  call    cs:__imp_CoTaskMemFree
0x18019abe8  nop     dword ptr [rax+rax+00h]
0x18019abed  jmp     short loc_18019ABFE
0x18019abef  call    cs:__imp_ILFree
0x18019abf6  nop     dword ptr [rax+rax+00h]
0x18019abfb  mov     bl, dil
0x18019abfe  lea     rcx, [rbp+57h+ppidl]
0x18019ac02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ac07  jmp     loc_18019AAA0
0x18019ac0c  and     eax, 1FFF0000h
0x18019ac11  cmp     eax, 70000h
0x18019ac16  movzx   eax, si
0x18019ac19  jz      short loc_18019AC1D
0x18019ac1b  mov     eax, esi
0x18019ac1d  cmp     eax, 2
0x18019ac20  jnz     short loc_18019AC34
0x18019ac22  lea     rdx, [rbp+57h+var_88]
0x18019ac26  mov     rcx, r15; this
0x18019ac29  call    ?_CreateAndSaveDefaultSourceDirectoryPIDLs@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAV?$CCoSimpleArray@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@@@@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_CreateAndSaveDefaultSourceDirectoryPIDLs(CCoSimpleArray<SystemSettings::Personalization::INDEX_PIDL_PAIR *,4294967294,CSimpleArrayStandardCompareHelper<SystemSettings::Personalization::INDEX_PIDL_PAIR *>> *)
0x18019ac2e  mov     r12, [rbp+57h+var_88]
0x18019ac32  mov     esi, eax
0x18019ac34  test    esi, esi
0x18019ac36  js      short loc_18019AC73
0x18019ac38  mov     ebx, edi
0x18019ac3a  cmp     rbx, [rbp+57h+var_80]
0x18019ac3e  jnb     short loc_18019AC62
0x18019ac40  mov     r8, [rbp+57h+arg_8]; struct SystemSettings::Personalization::ISlideshowSingleton *
0x18019ac44  mov     rdx, [r12+rbx*8]; struct SystemSettings::Personalization::INDEX_PIDL_PAIR *
0x18019ac48  mov     rcx, r15; this
0x18019ac4b  call    ?_CreateSlideshowFolderAndAddToCollection@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAUINDEX_PIDL_PAIR@23@PEAVISlideshowSingleton@23@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_CreateSlideshowFolderAndAddToCollection(SystemSettings::Personalization::INDEX_PIDL_PAIR *,SystemSettings::Personalization::ISlideshowSingleton *)
0x18019ac50  mov     esi, eax
0x18019ac52  mov     qword ptr [r12+rbx*8], 0
0x18019ac5a  inc     edi
0x18019ac5c  test    eax, eax
0x18019ac5e  jns     short loc_18019AC38
0x18019ac60  jmp     short loc_18019AC73
0x18019ac62  mov     rcx, r14
0x18019ac65  call    ?InternalAddRef@?$ComPtr@V?$AgileObservableVector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>>>::InternalAddRef(void)
0x18019ac6a  mov     r10, [r14]
0x18019ac6d  mov     [r13+0], r10
0x18019ac71  xor     esi, esi
0x18019ac73  xor     ebx, ebx
0x18019ac75  cmp     [rbp+57h+var_80], rbx
  ... truncated ...
```
