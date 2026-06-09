# SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(_ITEMIDLIST const *,SystemSettings::Personalization::ISlideshowSingleton *,bool,bool)

- ea: `0x180199cb0`
- end: `0x18019a427`
- name: `?AddFolder@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEFBU_ITEMIDLIST@@PEAVISlideshowSingleton@23@_N2@Z`
- size: `1911`
- prototype: `__int64 __usercall@<rax>(SystemSettings::Personalization::CSlideshowFolderHelper *__hidden this@<rcx>, LPCITEMIDLIST pidl@<rdx>, struct SystemSettings::Personalization::ISlideshowSingleton *@<r8>, bool@<r9b>, bool)`
- caller_count: `3`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180196280`
- `0x18019a800`
- `0x18019f3e0`

## callees

- `0x18000c840`
- `0x18000c940`
- `0x18001098c`
- `0x1800109b0`
- `0x180011bb0`
- `0x18001a64c`
- `0x1800234f8`
- `0x1800336b0`
- `0x18003d038`
- `0x18003d280`
- `0x18004e624`
- `0x18004e954`
- `0x1801999ac`
- `0x180199af0`
- `0x180199c78`
- `0x180199cb0`
- `0x18019a770`
- `0x18019a800`
- `0x18019b8dc`
- `0x18019bbb0`
- `0x18019c008`
- `0x18019c0bc`
- `0x18019c318`
- `0x18019c3e4`
- `0x18019c46c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199f04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019a31d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199f04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019a31d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019a37a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019a37a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019a3e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019a3e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180199d5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180199d5e`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18019a243`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x18019a243`
- `SHELL32!__imp_ILClone` at `0x180199e0f`
- `SHELL32!__imp_ILClone` at `0x180199e0f`
- `SHELL32!__imp_ILFree` at `0x180199f5f`
- `SHELL32!__imp_ILFree` at `0x18019a155`
- `SHELL32!__imp_ILFree` at `0x18019a30c`
- `SHELL32!__imp_ILFree` at `0x180199f5f`
- `SHELL32!__imp_ILFree` at `0x18019a155`
- `SHELL32!__imp_ILFree` at `0x18019a30c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::AddFolder(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        LPCITEMIDLIST pidl,
        struct SystemSettings::Personalization::ISlideshowSingleton *a3,
        char a4,
        bool a5)
{
  struct SystemSettings::Personalization::ISlideshowSingleton *v5; // r15
  int Folders; // edi
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  SystemSettings::Personalization **v11; // r13
  LPCITEMIDLIST *v12; // rsi
  unsigned __int16 **v13; // r8
  __int64 i; // rcx
  struct _ITEMIDLIST *v15; // rdx
  const unsigned __int16 *v16; // r12
  unsigned int v17; // ebx
  unsigned int v18; // esi
  __int64 v19; // rax
  int v20; // r9d
  int v21; // eax
  const unsigned __int16 *v22; // rax
  struct _ITEMIDLIST **v23; // r8
  int v24; // ecx
  int v25; // edx
  SystemSettings::Personalization *v26; // rcx
  struct _ITEMIDLIST *v27; // rdx
  ITEMIDLIST *v28; // rbx
  UINT v29; // edx
  struct _ITEMIDLIST **v30; // r8
  __int64 v31; // rax
  unsigned int v32; // ebx
  unsigned int v33; // r12d
  __int64 v34; // rax
  IShellItemArray *v35; // rax
  SystemSettings::Personalization::INDEX_PIDL_PAIR *v36; // rbx
  struct IShellItemArrayVtbl *v37; // rcx
  unsigned int v38; // edx
  LPVOID v39; // rsi
  LPVOID v40; // r8
  unsigned int v41; // esi
  __int64 v42; // rbx
  UINT v43; // ebx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, LPVOID *); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, LPVOID *); // rdi
  __int64 v46; // rsi
  LPCITEMIDLIST *v47; // r15
  int v48; // eax
  const WCHAR *v49; // rax
  LSTATUS v50; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int *v53; // [rsp+28h] [rbp-D8h]
  char v54; // [rsp+30h] [rbp-D0h]
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  char v56; // [rsp+40h] [rbp-C0h]
  IShellItemArray *ppsiItemArray; // [rsp+48h] [rbp-B8h] BYREF
  UINT cidl[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST *rgpidl; // [rsp+60h] [rbp-A0h]
  __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  struct SystemSettings::Personalization::ISlideshowSingleton *v62; // [rsp+70h] [rbp-90h] BYREF
  struct SystemSettings::Personalization::ISlideshowSingleton *v63; // [rsp+78h] [rbp-88h]
  unsigned __int16 v64[264]; // [rsp+80h] [rbp-80h] BYREF

  v56 = a4;
  v5 = a3;
  v63 = a3;
  v62 = a3;
  v61 = 0;
  if ( a4 )
  {
    hKey = 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v61);
    Folders = SystemSettings::Personalization::CSlideshowFolderHelper::GetFolders(this, v5, &v61);
    hKey = 0;
    if ( Folders < 0 )
      goto LABEL_98;
  }
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 536);
  v10 = RegOpenKeyExW(HKEY_CURRENT_USER, v9, 0, 3u, &hKey);
  Folders = v10;
  if ( v10 > 0 )
    Folders = (unsigned __int16)v10 | 0x80070000;
  if ( Folders >= 0 )
  {
    v11 = (SystemSettings::Personalization **)operator new[](0x50u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v11
      || (v12 = (LPCITEMIDLIST *)operator new[](0x50u, (const struct std::nothrow_t *)&std::nothrow), (rgpidl = v12) == 0) )
    {
      Folders = -2147024882;
LABEL_97:
      RegCloseKey(hKey);
      goto LABEL_98;
    }
    v54 = 0;
    LODWORD(ppsiItemArray) = 0;
    cidl[0] = 0;
    for ( i = 0; i != 10; ++i )
    {
      v11[i] = 0;
      v12[i] = 0;
    }
    pv = 0;
    Folders = SystemSettings::Personalization::g_ConvertPIDLToString(pidl, (const struct _ITEMIDLIST *)&pv, v13);
    v16 = (const unsigned __int16 *)pv;
    if ( Folders < 0 )
    {
      v17 = (unsigned int)ppsiItemArray;
    }
    else
    {
      if ( SystemSettings::Personalization::g_IsValidForLibrary(pidl, v15) )
      {
        *v12 = ILClone(pidl);
        cidl[0] = 1;
      }
      *v11 = (SystemSettings::Personalization *)v16;
      v17 = 1;
      LODWORD(ppsiItemArray) = 1;
    }
    if ( v56 )
    {
LABEL_39:
      if ( Folders >= 0 )
      {
        Folders = SystemSettings::Personalization::CSlideshowFolderHelper::_RemoveSourceDirectoriesFromRegistry(
                    this,
                    hKey);
        if ( Folders >= 0 )
        {
          v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 600);
          LODWORD(phkResult) = 1;
          Folders = StringCchPrintfW(v64, 0x104u, L"%s%u", v31, phkResult);
          if ( Folders >= 0 )
            Folders = SHRegSetString(hKey, 0, v64, v16);
        }
        v32 = 1;
        v33 = (unsigned int)ppsiItemArray;
        while ( 1 )
        {
          if ( Folders < 0 )
            goto LABEL_80;
          if ( v32 >= v33 )
            break;
          v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 600);
          LODWORD(phkResult) = v32 + 1;
          Folders = StringCchPrintfW(v64, 0x104u, L"%s%u", v34, phkResult);
          if ( Folders >= 0 )
            Folders = SHRegSetString(hKey, 0, v64, (const unsigned __int16 *)v11[v32]);
          ++v32;
        }
        pv = 0;
        Folders = SystemSettings::Personalization::g_ConvertStringToPIDL(*v11, (const unsigned __int16 *)&pv, v30);
        if ( Folders >= 0 )
        {
          v35 = (IShellItemArray *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          v36 = (SystemSettings::Personalization::INDEX_PIDL_PAIR *)v35;
          ppsiItemArray = v35;
          v37 = (struct IShellItemArrayVtbl *)pv;
          if ( v35 )
          {
            LODWORD(v35->lpVtbl) = 1;
            v35[1].lpVtbl = v37;
            ppsiItemArray = v35;
            Microsoft::WRL::Details::Make<SystemSettings::Personalization::CSlideshowFolder,SystemSettings::Personalization::INDEX_PIDL_PAIR * &,SystemSettings::Personalization::ISlideshowSingleton * &>(
              &pv,
              &ppsiItemArray,
              &v62);
            v39 = pv;
            if ( pv )
            {
              ppsiItemArray = 0;
              Folders = Microsoft::WRL::ComPtr<SystemSettings::Personalization::CSlideshowFolder>::As<SystemSettings::DataModel::ISettingItem>(
                          &pv,
                          &ppsiItemArray);
              if ( Folders >= 0 )
              {
                v40 = v39;
                v39 = 0;
                Folders = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                            *((_QWORD *)this + 66),
                            0,
                            v40,
                            0);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsiItemArray);
            }
            else
            {
              Folders = -2147024882;
              SystemSettings::Personalization::INDEX_PIDL_PAIR::`scalar deleting destructor'(v36, v38);
            }
            if ( v39 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
          }
          else
          {
            Folders = -2147024882;
            ILFree((LPITEMIDLIST)pv);
          }
        }
        if ( v56 )
        {
LABEL_69:
          if ( Folders < 0 )
            goto LABEL_80;
        }
        else
        {
          LODWORD(ppsiItemArray) = 0;
          if ( Folders >= 0 )
            Folders = SystemSettings::Personalization::CSlideshowFolderHelper::GetFolderCount(
                        this,
                        v5,
                        (unsigned int *)&ppsiItemArray);
          v41 = 1;
          if ( Folders < 0 )
          {
LABEL_80:
            v46 = 0;
            if ( v33 )
            {
              v47 = rgpidl;
              do
              {
                ILFree((LPITEMIDLIST)v47[v46]);
                CoTaskMemFree(v11[v46]);
                v46 = (unsigned int)(v46 + 1);
              }
              while ( (unsigned int)v46 < v33 );
              v5 = v63;
            }
            operator delete(v11);
            operator delete(rgpidl);
            if ( Folders < 0 || v54 )
              goto LABEL_97;
            v48 = *((_DWORD *)this + 130);
            if ( v48 == 4 )
            {
              v49 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 664);
              v50 = RegDeleteValueW(hKey, v49);
              Folders = v50;
              if ( (v50 & 0xFFFFFFFD) != 0 )
              {
                if ( v50 > 0 )
                  Folders = (unsigned __int16)v50 | 0x80070000;
              }
              else
              {
                Folders = 0;
              }
            }
            else if ( v48 != 2 )
            {
LABEL_93:
              if ( !a5 )
                (*(void (__fastcall **)(struct SystemSettings::Personalization::ISlideshowSingleton *))(*(_QWORD *)v5 + 96LL))(v5);
              SystemSettings::Personalization::CSlideshowFolderHelper::_LogSourceDirectoryCollectionInformation(this);
              goto LABEL_97;
            }
            SystemSettings::Personalization::CSlideshowFolderHelper::SetErrorMessageCode(this, 1, v5);
            goto LABEL_93;
          }
          while ( v41 < (unsigned int)ppsiItemArray )
          {
            pv = 0;
            v42 = *((_QWORD *)this + 66);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
            Folders = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                        v42,
                        v41++,
                        &pv);
            if ( Folders >= 0 )
              **((_DWORD **)pv + 28) = v41;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
            if ( Folders < 0 )
              goto LABEL_69;
          }
        }
        v43 = cidl[0];
        if ( cidl[0] )
        {
          *(_QWORD *)cidl = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(cidl);
          Folders = SystemSettings::Personalization::CSlideshowFolderHelper::_GetSlideshowLibrary(
                      this,
                      (struct IShellLibrary **)cidl);
          if ( Folders >= 0 )
          {
            ppsiItemArray = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsiItemArray);
            Folders = SHCreateShellItemArrayFromIDLists(v43, rgpidl, &ppsiItemArray);
            if ( Folders >= 0 )
            {
              pv = 0;
              v44 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID *))cidl;
              v45 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID *))cidl;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
              Folders = v45(v44, &GUID_692f0195_c47b_4b2d_9de5_bc481ec5ebc9, &pv);
              if ( Folders >= 0 )
              {
                Folders = (*(__int64 (__fastcall **)(LPVOID, IShellItemArray *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)pv + 88LL))(
                            pv,
                            ppsiItemArray,
                            0,
                            0,
                            0);
                if ( Folders >= 0 )
                  Folders = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)cidl + 136LL))(*(_QWORD *)cidl);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsiItemArray);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(cidl);
        }
        goto LABEL_80;
      }
    }
    else
    {
      v18 = 1;
      if ( Folders >= 0 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v54 )
              goto LABEL_79;
            if ( v18 > 0xA )
              goto LABEL_39;
            v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 600);
            LODWORD(phkResult) = v18;
            Folders = StringCchPrintfW(v64, 0x104u, L"%s%u", v19, phkResult);
            if ( Folders >= 0 )
              break;
LABEL_38:
            ++v18;
            if ( Folders < 0 )
              goto LABEL_39;
          }
          pv = 0;
          v21 = SHRegAllocData(hKey, 0, v64, v20, &pv, v53);
          if ( (v21 & 0x1FFF0000) == 0x70000 )
            v21 = (unsigned __int16)v21;
          if ( v21 )
          {
            if ( v21 != 2 )
            {
              if ( v21 > 0 )
                Folders = (unsigned __int16)v21 | 0x80070000;
              else
                Folders = v21;
            }
            goto LABEL_38;
          }
          v22 = v16;
          v23 = (struct _ITEMIDLIST **)pv;
          do
          {
            v24 = *(const unsigned __int16 *)((char *)v22 + (_BYTE *)pv - (_BYTE *)v16);
            v25 = *v22 - v24;
            if ( v25 )
              break;
            ++v22;
          }
          while ( v24 );
          v26 = (SystemSettings::Personalization *)pv;
          if ( v25 )
          {
            v11[v17] = (SystemSettings::Personalization *)pv;
            LODWORD(ppsiItemArray) = v17 + 1;
            pv = 0;
            if ( (int)SystemSettings::Personalization::g_ConvertStringToPIDL(v26, (const unsigned __int16 *)&pv, v23) >= 0 )
            {
              v28 = (ITEMIDLIST *)pv;
              if ( SystemSettings::Personalization::g_IsValidForLibrary((LPCITEMIDLIST)pv, v27) )
              {
                v29 = cidl[0];
                rgpidl[cidl[0]] = v28;
                cidl[0] = v29 + 1;
              }
              else
              {
                ILFree(v28);
              }
            }
          }
          else
          {
            v54 = 1;
            CoTaskMemFree(pv);
          }
          ++v18;
          v17 = (unsigned int)ppsiItemArray;
        }
      }
    }
LABEL_79:
    v33 = (unsigned int)ppsiItemArray;
    goto LABEL_80;
  }
LABEL_98:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v61);
  return (unsigned int)Folders;
}

```

## disassembly

```asm
0x180199cb0  mov     [rsp-8+arg_18], rbx
0x180199cb5  push    rbp
0x180199cb6  push    rsi
0x180199cb7  push    rdi
0x180199cb8  push    r12
0x180199cba  push    r13
0x180199cbc  push    r14
0x180199cbe  push    r15
0x180199cc0  lea     rbp, [rsp-1A0h]
0x180199cc8  sub     rsp, 2A0h
0x180199ccf  mov     rax, cs:__security_cookie
0x180199cd6  xor     rax, rsp
0x180199cd9  mov     [rbp+1D0h+var_40], rax
0x180199ce0  mov     [rsp+2D0h+var_290], r9b
0x180199ce5  mov     r15, r8
0x180199ce8  mov     [rsp+2D0h+var_258], r8
0x180199ced  mov     rbx, rdx
0x180199cf0  mov     r14, rcx
0x180199cf3  mov     [rsp+2D0h+var_260], r8
0x180199cf8  xor     r12d, r12d
0x180199cfb  mov     [rsp+2D0h+var_268], r12
0x180199d00  test    r9b, r9b
0x180199d03  jz      short loc_180199D0C
0x180199d05  mov     [rsp+2D0h+hKey], r12
0x180199d0a  jmp     short loc_180199D35
0x180199d0c  lea     rcx, [rsp+2D0h+var_268]
0x180199d11  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180199d16  lea     r8, [rsp+2D0h+var_268]
0x180199d1b  mov     rdx, r15
0x180199d1e  mov     rcx, r14; this
0x180199d21  call    ?GetFolders@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEAVISlideshowSingleton@23@PEAPEAV?$AgileObservableVector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::GetFolders(SystemSettings::Personalization::ISlideshowSingleton *,Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>> * *)
0x180199d26  mov     edi, eax
0x180199d28  mov     [rsp+2D0h+hKey], r12
0x180199d2d  test    eax, eax
0x180199d2f  js      loc_18019A3F0
0x180199d35  lea     rcx, [r14+218h]
0x180199d3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180199d41  lea     rcx, [rsp+2D0h+hKey]
0x180199d46  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x180199d4b  mov     r9d, 3; samDesired
0x180199d51  xor     r8d, r8d; ulOptions
0x180199d54  mov     rdx, rax; lpSubKey
0x180199d57  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180199d5e  call    cs:__imp_RegOpenKeyExW
0x180199d65  nop     dword ptr [rax+rax+00h]
0x180199d6a  mov     edi, eax
0x180199d6c  test    eax, eax
0x180199d6e  jle     short loc_180199D79
0x180199d70  movzx   edi, ax
0x180199d73  or      edi, 80070000h
0x180199d79  test    edi, edi
0x180199d7b  js      loc_18019A3F0
0x180199d81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199d88  mov     edi, 50h ; 'P'
0x180199d8d  mov     ecx, edi; unsigned __int64
0x180199d8f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180199d94  mov     r13, rax
0x180199d97  test    rax, rax
0x180199d9a  jz      loc_18019A3D9
0x180199da0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180199da7  mov     ecx, edi; unsigned __int64
0x180199da9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180199dae  mov     rsi, rax
0x180199db1  mov     [rsp+2D0h+rgpidl], rax
0x180199db6  test    rax, rax
0x180199db9  jz      loc_18019A3D9
0x180199dbf  mov     [rsp+2D0h+var_2A0], r12b
0x180199dc4  mov     dword ptr [rsp+2D0h+ppsiItemArray], r12d
0x180199dc9  xor     eax, eax
0x180199dcb  mov     [rsp+2D0h+cidl], eax
0x180199dcf  mov     ecx, eax
0x180199dd1  mov     [r13+rcx*8+0], rax
0x180199dd6  mov     [rsi+rcx*8], rax
0x180199dda  inc     rcx
0x180199ddd  cmp     rcx, 0Ah
0x180199de1  jnz     short loc_180199DD1
0x180199de3  mov     [rsp+2D0h+pv], rax
0x180199de8  lea     rdx, [rsp+2D0h+pv]; struct _ITEMIDLIST *
0x180199ded  mov     rcx, rbx; pidl
0x180199df0  call    ?g_ConvertPIDLToString@Personalization@SystemSettings@@YAJPEFBU_ITEMIDLIST@@PEAPEAG@Z; SystemSettings::Personalization::g_ConvertPIDLToString(_ITEMIDLIST const *,ushort * *)
0x180199df5  mov     edi, eax
0x180199df7  mov     r12, [rsp+2D0h+pv]
0x180199dfc  test    eax, eax
0x180199dfe  js      short loc_180199E35
0x180199e00  mov     rcx, rbx; pidl
0x180199e03  call    ?g_IsValidForLibrary@Personalization@SystemSettings@@YA_NPEFAU_ITEMIDLIST@@@Z; SystemSettings::Personalization::g_IsValidForLibrary(_ITEMIDLIST *)
0x180199e08  test    al, al
0x180199e0a  jz      short loc_180199E26
0x180199e0c  mov     rcx, rbx; pidl
0x180199e0f  call    cs:__imp_ILClone
0x180199e16  nop     dword ptr [rax+rax+00h]
0x180199e1b  mov     [rsi], rax
0x180199e1e  mov     [rsp+2D0h+cidl], 1
0x180199e26  mov     [r13+0], r12
0x180199e2a  mov     ebx, 1
0x180199e2f  mov     dword ptr [rsp+2D0h+ppsiItemArray], ebx
0x180199e33  jmp     short loc_180199E39
0x180199e35  mov     ebx, dword ptr [rsp+2D0h+ppsiItemArray]
0x180199e39  cmp     [rsp+2D0h+var_290], 0
0x180199e3e  jnz     loc_180199F96
0x180199e44  mov     esi, 1
0x180199e49  test    edi, edi
0x180199e4b  js      loc_18019A2F7
0x180199e51  mov     al, [rsp+2D0h+var_2A0]
0x180199e55  test    al, al
0x180199e57  jnz     loc_18019A2F7
0x180199e5d  cmp     esi, 0Ah
0x180199e60  ja      loc_180199F9A
0x180199e66  lea     rcx, [r14+258h]
0x180199e6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180199e72  mov     dword ptr [rsp+2D0h+phkResult], esi
0x180199e76  mov     r9, rax
0x180199e79  lea     r8, aSU_0; "%s%u"
0x180199e80  mov     edx, 104h; unsigned __int64
0x180199e85  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x180199e89  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180199e8e  mov     edi, eax
0x180199e90  test    eax, eax
0x180199e92  js      loc_180199F8C
0x180199e98  mov     [rsp+2D0h+pv], 0
0x180199ea1  lea     rax, [rsp+2D0h+pv]
0x180199ea6  mov     [rsp+2D0h+phkResult], rax; void **
0x180199eab  lea     r8, [rbp+1D0h+var_250]; unsigned __int16 *
0x180199eaf  xor     edx, edx; unsigned __int16 *
0x180199eb1  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x180199eb6  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180199ebb  mov     ecx, eax
0x180199ebd  and     ecx, 1FFF0000h
0x180199ec3  cmp     ecx, 70000h
0x180199ec9  jnz     short loc_180199ECE
0x180199ecb  movzx   eax, ax
0x180199ece  test    eax, eax
0x180199ed0  jnz     loc_180199F76
0x180199ed6  mov     rax, r12
0x180199ed9  mov     r8, [rsp+2D0h+pv]; struct _ITEMIDLIST **
0x180199ede  mov     r9, r8
0x180199ee1  sub     r9, r12
0x180199ee4  movzx   edx, word ptr [rax]
0x180199ee7  movzx   ecx, word ptr [rax+r9]
0x180199eec  sub     edx, ecx
0x180199eee  jnz     short loc_180199EF8
0x180199ef0  add     rax, 2
0x180199ef4  test    ecx, ecx
0x180199ef6  jnz     short loc_180199EE4
0x180199ef8  mov     rcx, r8; this
0x180199efb  test    edx, edx
0x180199efd  jnz     short loc_180199F12
0x180199eff  mov     [rsp+2D0h+var_2A0], 1
0x180199f04  call    cs:__imp_CoTaskMemFree
0x180199f0b  nop     dword ptr [rax+rax+00h]
0x180199f10  jmp     short loc_180199F6B
0x180199f12  mov     eax, ebx
0x180199f14  mov     [r13+rax*8+0], r8
0x180199f19  inc     ebx
0x180199f1b  mov     dword ptr [rsp+2D0h+ppsiItemArray], ebx
0x180199f1f  mov     [rsp+2D0h+pv], 0
0x180199f28  lea     rdx, [rsp+2D0h+pv]; unsigned __int16 *
0x180199f2d  call    ?g_ConvertStringToPIDL@Personalization@SystemSettings@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; SystemSettings::Personalization::g_ConvertStringToPIDL(ushort const *,_ITEMIDLIST * *)
0x180199f32  test    eax, eax
0x180199f34  js      short loc_180199F6B
0x180199f36  mov     rbx, [rsp+2D0h+pv]
0x180199f3b  mov     rcx, rbx; pidl
0x180199f3e  call    ?g_IsValidForLibrary@Personalization@SystemSettings@@YA_NPEFAU_ITEMIDLIST@@@Z; SystemSettings::Personalization::g_IsValidForLibrary(_ITEMIDLIST *)
0x180199f43  test    al, al
0x180199f45  jz      short loc_180199F5C
0x180199f47  mov     edx, [rsp+2D0h+cidl]
0x180199f4b  mov     rcx, [rsp+2D0h+rgpidl]
0x180199f50  mov     [rcx+rdx*8], rbx
0x180199f54  inc     edx
0x180199f56  mov     [rsp+2D0h+cidl], edx
0x180199f5a  jmp     short loc_180199F6B
0x180199f5c  mov     rcx, rbx; pidl
0x180199f5f  call    cs:__imp_ILFree
0x180199f66  nop     dword ptr [rax+rax+00h]
0x180199f6b  inc     esi
0x180199f6d  mov     ebx, dword ptr [rsp+2D0h+ppsiItemArray]
0x180199f71  jmp     loc_180199E51
0x180199f76  cmp     eax, 2
0x180199f79  jz      short loc_180199F8C
0x180199f7b  test    eax, eax
0x180199f7d  jg      short loc_180199F83
0x180199f7f  mov     edi, eax
0x180199f81  jmp     short loc_180199F8C
0x180199f83  movzx   edi, ax
0x180199f86  or      edi, 80070000h
0x180199f8c  inc     esi
0x180199f8e  test    edi, edi
0x180199f90  jns     loc_180199E51
0x180199f96  mov     al, [rsp+2D0h+var_2A0]
0x180199f9a  test    edi, edi
0x180199f9c  js      loc_18019A2F7
0x180199fa2  test    al, al
0x180199fa4  jnz     loc_18019A2F7
0x180199faa  mov     rdx, [rsp+2D0h+hKey]; HKEY
0x180199faf  mov     rcx, r14; this
0x180199fb2  call    ?_RemoveSourceDirectoriesFromRegistry@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAUHKEY__@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_RemoveSourceDirectoriesFromRegistry(HKEY__ *)
0x180199fb7  mov     edi, eax
0x180199fb9  test    eax, eax
0x180199fbb  js      short loc_18019A004
0x180199fbd  lea     rcx, [r14+258h]
0x180199fc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180199fc9  mov     dword ptr [rsp+2D0h+phkResult], 1
0x180199fd1  mov     r9, rax
0x180199fd4  lea     r8, aSU_0; "%s%u"
0x180199fdb  mov     edx, 104h; unsigned __int64
0x180199fe0  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x180199fe4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180199fe9  mov     edi, eax
0x180199feb  test    eax, eax
0x180199fed  js      short loc_18019A004
0x180199fef  mov     r9, r12; unsigned __int16 *
0x180199ff2  lea     r8, [rbp+1D0h+var_250]; unsigned __int16 *
0x180199ff6  xor     edx, edx; unsigned __int16 *
0x180199ff8  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x180199ffd  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18019a002  mov     edi, eax
0x18019a004  mov     ebx, 1
0x18019a009  mov     r12d, dword ptr [rsp+2D0h+ppsiItemArray]
0x18019a00e  jmp     short loc_18019A062
0x18019a010  cmp     ebx, r12d
0x18019a013  jnb     short loc_18019A06B
0x18019a015  lea     rcx, [r14+258h]
0x18019a01c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019a021  lea     esi, [rbx+1]
0x18019a024  mov     dword ptr [rsp+2D0h+phkResult], esi
0x18019a028  mov     r9, rax
0x18019a02b  lea     r8, aSU_0; "%s%u"
0x18019a032  mov     edx, 104h; unsigned __int64
0x18019a037  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18019a03b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019a040  mov     edi, eax
0x18019a042  test    eax, eax
0x18019a044  js      short loc_18019A060
0x18019a046  mov     r9d, ebx
0x18019a049  mov     r9, [r13+r9*8+0]; unsigned __int16 *
0x18019a04e  lea     r8, [rbp+1D0h+var_250]; unsigned __int16 *
0x18019a052  xor     edx, edx; unsigned __int16 *
0x18019a054  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18019a059  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18019a05e  mov     edi, eax
0x18019a060  mov     ebx, esi
0x18019a062  test    edi, edi
0x18019a064  jns     short loc_18019A010
0x18019a066  jmp     loc_18019A2FC
0x18019a06b  mov     [rsp+2D0h+pv], 0
0x18019a074  lea     rdx, [rsp+2D0h+pv]; unsigned __int16 *
0x18019a079  mov     rcx, [r13+0]; this
0x18019a07d  call    ?g_ConvertStringToPIDL@Personalization@SystemSettings@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; SystemSettings::Personalization::g_ConvertStringToPIDL(ushort const *,_ITEMIDLIST * *)
0x18019a082  mov     edi, eax
0x18019a084  test    eax, eax
0x18019a086  js      loc_18019A161
0x18019a08c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019a093  mov     ecx, 10h; unsigned __int64
0x18019a098  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18019a09d  mov     rbx, rax
0x18019a0a0  mov     [rsp+2D0h+ppsiItemArray], rax
0x18019a0a5  mov     rcx, [rsp+2D0h+pv]; pidl
0x18019a0aa  test    rax, rax
0x18019a0ad  jz      loc_18019A150
0x18019a0b3  mov     dword ptr [rax], 1
0x18019a0b9  mov     [rax+8], rcx
0x18019a0bd  mov     [rsp+2D0h+ppsiItemArray], rax
0x18019a0c2  test    rax, rax
0x18019a0c5  jz      loc_18019A150
0x18019a0cb  lea     r8, [rsp+2D0h+var_260]
0x18019a0d0  lea     rdx, [rsp+2D0h+ppsiItemArray]
0x18019a0d5  lea     rcx, [rsp+2D0h+pv]
0x18019a0da  call    ??$Make@VCSlideshowFolder@Personalization@SystemSettings@@AEAPEAUINDEX_PIDL_PAIR@23@AEAPEAVISlideshowSingleton@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCSlideshowFolder@Personalization@SystemSettings@@@12@AEAPEAUINDEX_PIDL_PAIR@Personalization@SystemSettings@@AEAPEAVISlideshowSingleton@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::Personalization::CSlideshowFolder,SystemSettings::Personalization::INDEX_PIDL_PAIR * &,SystemSettings::Personalization::ISlideshowSingleton * &>(SystemSettings::Personalization::INDEX_PIDL_PAIR * &,SystemSettings::Personalization::ISlideshowSingleton * &)
0x18019a0df  mov     rsi, [rsp+2D0h+pv]
0x18019a0e4  test    rsi, rsi
0x18019a0e7  jz      short loc_18019A12B
0x18019a0e9  mov     [rsp+2D0h+ppsiItemArray], 0
0x18019a0f2  lea     rdx, [rsp+2D0h+ppsiItemArray]
0x18019a0f7  lea     rcx, [rsp+2D0h+pv]
0x18019a0fc  call    ??$As@UISettingItem@DataModel@SystemSettings@@@?$ComPtr@VCSlideshowFolder@Personalization@SystemSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SystemSettings::Personalization::CSlideshowFolder>::As<SystemSettings::DataModel::ISettingItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>)
0x18019a101  mov     edi, eax
0x18019a103  test    eax, eax
0x18019a105  js      short loc_18019A11F
0x18019a107  mov     r8, rsi
0x18019a10a  xor     esi, esi
0x18019a10c  xor     r9d, r9d
0x18019a10f  xor     edx, edx
0x18019a111  mov     rcx, [r14+210h]
0x18019a118  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18019a11d  mov     edi, eax
0x18019a11f  lea     rcx, [rsp+2D0h+ppsiItemArray]
0x18019a124  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019a129  jmp     short loc_18019A139
0x18019a12b  mov     edi, 8007000Eh
0x18019a130  mov     rcx, rbx; this
0x18019a133  call    ??_GINDEX_PIDL_PAIR@Personalization@SystemSettings@@QEAAPEAXI@Z; SystemSettings::Personalization::INDEX_PIDL_PAIR::`scalar deleting destructor'(uint)
0x18019a138  nop
0x18019a139  test    rsi, rsi
0x18019a13c  jz      short loc_18019A14E
0x18019a13e  mov     rax, [rsi]
0x18019a141  mov     rcx, rsi
0x18019a144  mov     rax, [rax+10h]
0x18019a148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019a14d  nop
0x18019a14e  jmp     short loc_18019A161
  ... truncated ...
```
