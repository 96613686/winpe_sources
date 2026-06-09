# SystemSettings::Personalization::CSlideshowFolderHelper::RemoveFolder(SystemSettings::Personalization::CSlideshowFolder *,SystemSettings::Personalization::ISlideshowSingleton *)

- ea: `0x18019b540`
- end: `0x18019b8d5`
- name: `?RemoveFolder@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEAVCSlideshowFolder@23@PEAVISlideshowSingleton@23@@Z`
- size: `917`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowFolderHelper *__hidden this, struct SystemSettings::Personalization::CSlideshowFolder *, struct SystemSettings::Personalization::ISlideshowSingleton *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180197200`
- `0x18019f9c0`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180011bb0`
- `0x18001a64c`
- `0x1800234f8`
- `0x1800336b0`
- `0x180040000`
- `0x180046850`
- `0x18019b540`
- `0x18019b8dc`
- `0x18019bbb0`
- `0x18019c008`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019b63e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019b85a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019b63e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18019b85a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019b5c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019b5c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019b666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019b895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019b666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019b895`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019b827`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019b827`
- `SHELL32!SHCreateShellItem` at `0x18019b77c`
- `SHELL32!SHCreateShellItem` at `0x18019b77c`
- `SHELL32!__imp_ILClone` at `0x18019b749`
- `SHELL32!__imp_ILClone` at `0x18019b749`
- `SHELL32!__imp_ILFree` at `0x18019b7b5`
- `SHELL32!__imp_ILFree` at `0x18019b7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::Personalization::CSlideshowFolderHelper::RemoveFolder(
        SystemSettings::Personalization::CSlideshowFolderHelper *this,
        struct IShellLibrary *a2,
        struct SystemSettings::Personalization::ISlideshowSingleton *a3)
{
  char v6; // r14
  char *v7; // r13
  const WCHAR *v8; // rax
  LSTATUS Key; // eax
  signed int Size; // ebx
  __int64 v11; // rax
  LSTATUS v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rbx
  LPITEMIDLIST v15; // rsi
  const WCHAR *v16; // rax
  LSTATUS v17; // eax
  const WCHAR *v18; // rax
  LSTATUS v19; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  struct IShellLibrary *v22; // [rsp+50h] [rbp-B0h] BYREF
  IShellItem *ppsi; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[524]; // [rsp+74h] [rbp-8Ch] BYREF

  v6 = 0;
  hKey[0] = 0;
  v7 = (char *)this + 536;
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 536);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, v8, 0, 0, 0, 0x20006u, 0, hKey, 0);
  Size = Key;
  if ( Key > 0 )
    Size = (unsigned __int16)Key | 0x80070000;
  if ( Size >= 0 )
  {
    *(_DWORD *)ValueName = 0;
    memset_0(v26, 0, 0x204u);
    v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 600);
    dwOptions[0] = (DWORD)a2[28].lpVtbl->QueryInterface;
    Size = StringCchPrintfW(ValueName, 0x104u, L"%s%u", v11, *(_QWORD *)dwOptions);
    if ( Size >= 0 )
    {
      v12 = RegDeleteValueW(hKey[0], ValueName);
      Size = v12;
      if ( (v12 & 0xFFFFFFFD) != 0 )
      {
        if ( v12 > 0 )
          Size = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        Size = 0;
      }
    }
    RegCloseKey(hKey[0]);
    if ( Size >= 0 )
    {
      LODWORD(ppsi) = 0;
      Size = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
               *((_QWORD *)this + 66),
               &ppsi);
      v13 = 0;
      while ( Size >= 0 )
      {
        if ( v13 >= (unsigned int)ppsi )
          goto LABEL_18;
        v6 = 0;
        v22 = 0;
        v14 = *((_QWORD *)this + 66);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                 v14,
                 v13,
                 &v22);
        if ( Size >= 0 && v22 == a2 )
        {
          Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
                   *((_QWORD *)this + 66),
                   v13,
                   0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          v6 = 1;
          if ( Size < 0 )
            return (unsigned int)Size;
          SystemSettings::Personalization::CSlideshowFolderHelper::_LogSourceDirectoryCollectionInformation(this);
LABEL_18:
          v22 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          if ( (int)SystemSettings::Personalization::CSlideshowFolderHelper::_GetSlideshowLibrary(this, &v22) >= 0 )
          {
            v15 = ILClone((LPCITEMIDLIST)a2[28].lpVtbl->AddRef);
            if ( v15 )
            {
              ppsi = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsi);
              SHCreateShellItem(0, 0, v15, &ppsi);
              ((void (__fastcall *)(struct IShellLibrary *, IShellItem *))v22->lpVtbl->RemoveFolder)(v22, ppsi);
              ((void (__fastcall *)(struct IShellLibrary *))v22->lpVtbl->Commit)(v22);
              ILFree(v15);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsi);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          if ( v6 )
          {
            (*(void (__fastcall **)(struct SystemSettings::Personalization::ISlideshowSingleton *))(*(_QWORD *)a3 + 96LL))(a3);
            if ( (unsigned int)(*((_DWORD *)this + 130) - 5) <= 1 )
            {
              v16 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v7);
              v17 = RegOpenKeyExW(HKEY_CURRENT_USER, v16, 0, 0x20006u, hKey);
              Size = v17;
              if ( v17 > 0 )
                Size = (unsigned __int16)v17 | 0x80070000;
              if ( Size >= 0 )
              {
                v18 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 664);
                v19 = RegDeleteValueW(hKey[0], v18);
                Size = v19;
                if ( (v19 & 0xFFFFFFFD) != 0 )
                {
                  if ( v19 > 0 )
                    Size = (unsigned __int16)v19 | 0x80070000;
                }
                else
                {
                  Size = 0;
                }
                SystemSettings::Personalization::CSlideshowFolderHelper::SetErrorMessageCode(this, 1, a3);
                RegCloseKey(hKey[0]);
              }
            }
          }
          else
          {
            return (unsigned int)-2147418113;
          }
          return (unsigned int)Size;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        ++v13;
      }
    }
  }
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18019b540  mov     [rsp-8+arg_18], rbx
0x18019b545  push    rbp
0x18019b546  push    rsi
0x18019b547  push    rdi
0x18019b548  push    r12
0x18019b54a  push    r13
0x18019b54c  push    r14
0x18019b54e  push    r15
0x18019b550  lea     rbp, [rsp-190h]
0x18019b558  sub     rsp, 290h
0x18019b55f  mov     rax, cs:__security_cookie
0x18019b566  xor     rax, rsp
0x18019b569  mov     [rbp+1C0h+var_40], rax
0x18019b570  mov     r12, r8
0x18019b573  mov     r15, rdx
0x18019b576  mov     rdi, rcx
0x18019b579  xor     r14d, r14d
0x18019b57c  mov     [rsp+2C0h+hKey], r14
0x18019b581  lea     r13, [rcx+218h]
0x18019b588  mov     rcx, r13
0x18019b58b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b590  mov     [rsp+2C0h+lpdwDisposition], r14; lpdwDisposition
0x18019b595  lea     rcx, [rsp+2C0h+hKey]
0x18019b59a  mov     [rsp+2C0h+phkResult], rcx; phkResult
0x18019b59f  mov     [rsp+2C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18019b5a4  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x18019b5ac  mov     [rsp+2C0h+dwOptions], r14d; dwOptions
0x18019b5b1  xor     r9d, r9d; lpClass
0x18019b5b4  xor     r8d, r8d; Reserved
0x18019b5b7  mov     rdx, rax; lpSubKey
0x18019b5ba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18019b5c1  call    cs:__imp_RegCreateKeyExW
0x18019b5c8  nop     dword ptr [rax+rax+00h]
0x18019b5cd  mov     ebx, eax
0x18019b5cf  mov     esi, 80070000h
0x18019b5d4  test    eax, eax
0x18019b5d6  jle     short loc_18019B5DD
0x18019b5d8  movzx   ebx, ax
0x18019b5db  or      ebx, esi
0x18019b5dd  test    ebx, ebx
0x18019b5df  js      loc_18019B8A8
0x18019b5e5  mov     dword ptr [rsp+2C0h+ValueName], r14d
0x18019b5ea  xor     edx, edx; Val
0x18019b5ec  mov     r8d, 204h; Size
0x18019b5f2  lea     rcx, [rsp+2C0h+var_24C]; void *
0x18019b5f7  call    memset_0
0x18019b5fc  lea     rcx, [rdi+258h]
0x18019b603  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b608  mov     rcx, [r15+0E0h]
0x18019b60f  mov     edx, [rcx]
0x18019b611  mov     [rsp+2C0h+dwOptions], edx
0x18019b615  mov     r9, rax
0x18019b618  lea     r8, aSU_0; "%s%u"
0x18019b61f  mov     edx, 104h; unsigned __int64
0x18019b624  lea     rcx, [rsp+2C0h+ValueName]; unsigned __int16 *
0x18019b629  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019b62e  mov     ebx, eax
0x18019b630  test    eax, eax
0x18019b632  js      short loc_18019B661
0x18019b634  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x18019b639  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18019b63e  call    cs:__imp_RegDeleteValueW
0x18019b645  nop     dword ptr [rax+rax+00h]
0x18019b64a  mov     ebx, eax
0x18019b64c  test    eax, 0FFFFFFFDh
0x18019b651  jz      short loc_18019B65E
0x18019b653  test    eax, eax
0x18019b655  jle     short loc_18019B661
0x18019b657  movzx   ebx, ax
0x18019b65a  or      ebx, esi
0x18019b65c  jmp     short loc_18019B661
0x18019b65e  mov     ebx, r14d
0x18019b661  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18019b666  call    cs:__imp_RegCloseKey
0x18019b66d  nop     dword ptr [rax+rax+00h]
0x18019b672  test    ebx, ebx
0x18019b674  js      loc_18019B8A8
0x18019b67a  mov     dword ptr [rsp+2C0h+ppsi], r14d
0x18019b67f  lea     rdx, [rsp+2C0h+ppsi]
0x18019b684  mov     rcx, [rdi+210h]
0x18019b68b  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x18019b690  mov     ebx, eax
0x18019b692  mov     esi, r14d
0x18019b695  test    ebx, ebx
0x18019b697  js      loc_18019B8A8
0x18019b69d  cmp     esi, dword ptr [rsp+2C0h+ppsi]
0x18019b6a1  jnb     short loc_18019B716
0x18019b6a3  xor     r14d, r14d
0x18019b6a6  mov     [rsp+2C0h+var_270], r14
0x18019b6ab  mov     rbx, [rdi+210h]
0x18019b6b2  lea     rcx, [rsp+2C0h+var_270]
0x18019b6b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b6bc  lea     r8, [rsp+2C0h+var_270]
0x18019b6c1  mov     edx, esi
0x18019b6c3  mov     rcx, rbx
0x18019b6c6  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18019b6cb  mov     ebx, eax
0x18019b6cd  test    eax, eax
0x18019b6cf  js      short loc_18019B6D8
0x18019b6d1  cmp     [rsp+2C0h+var_270], r15
0x18019b6d6  jz      short loc_18019B6E6
0x18019b6d8  lea     rcx, [rsp+2C0h+var_270]
0x18019b6dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b6e2  inc     esi
0x18019b6e4  jmp     short loc_18019B695
0x18019b6e6  xor     r8d, r8d
0x18019b6e9  mov     edx, esi
0x18019b6eb  mov     rcx, [rdi+210h]
0x18019b6f2  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x18019b6f7  mov     ebx, eax
0x18019b6f9  lea     rcx, [rsp+2C0h+var_270]
0x18019b6fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b703  mov     r14b, 1
0x18019b706  test    ebx, ebx
0x18019b708  js      loc_18019B8A8
0x18019b70e  mov     rcx, rdi; this
0x18019b711  call    ?_LogSourceDirectoryCollectionInformation@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJXZ; SystemSettings::Personalization::CSlideshowFolderHelper::_LogSourceDirectoryCollectionInformation(void)
0x18019b716  mov     [rsp+2C0h+var_270], 0
0x18019b71f  lea     rcx, [rsp+2C0h+var_270]
0x18019b724  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b729  lea     rdx, [rsp+2C0h+var_270]; struct IShellLibrary **
0x18019b72e  mov     rcx, rdi; this
0x18019b731  call    ?_GetSlideshowLibrary@CSlideshowFolderHelper@Personalization@SystemSettings@@AEAAJPEAPEAUIShellLibrary@@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::_GetSlideshowLibrary(IShellLibrary * *)
0x18019b736  test    eax, eax
0x18019b738  js      loc_18019B7CD
0x18019b73e  mov     rcx, [r15+0E0h]
0x18019b745  mov     rcx, [rcx+8]; pidl
0x18019b749  call    cs:__imp_ILClone
0x18019b750  nop     dword ptr [rax+rax+00h]
0x18019b755  mov     rsi, rax
0x18019b758  test    rax, rax
0x18019b75b  jz      short loc_18019B7CD
0x18019b75d  mov     [rsp+2C0h+ppsi], 0
0x18019b766  lea     rcx, [rsp+2C0h+ppsi]
0x18019b76b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b770  lea     r9, [rsp+2C0h+ppsi]; ppsi
0x18019b775  mov     r8, rsi; pidl
0x18019b778  xor     edx, edx; psfParent
0x18019b77a  xor     ecx, ecx; pidlParent
0x18019b77c  call    cs:__imp_SHCreateShellItem
0x18019b783  nop     dword ptr [rax+rax+00h]
0x18019b788  mov     rcx, [rsp+2C0h+var_270]
0x18019b78d  mov     rax, [rcx]
0x18019b790  mov     rdx, [rsp+2C0h+ppsi]
0x18019b795  mov     rax, [rax+30h]
0x18019b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b79e  mov     rcx, [rsp+2C0h+var_270]
0x18019b7a3  mov     rax, [rcx]
0x18019b7a6  mov     rax, [rax+88h]
0x18019b7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b7b2  mov     rcx, rsi; pidl
0x18019b7b5  call    cs:__imp_ILFree
0x18019b7bc  nop     dword ptr [rax+rax+00h]
0x18019b7c1  nop
0x18019b7c2  lea     rcx, [rsp+2C0h+ppsi]
0x18019b7c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b7cc  nop
0x18019b7cd  lea     rcx, [rsp+2C0h+var_270]
0x18019b7d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019b7d7  test    r14b, r14b
0x18019b7da  jz      loc_18019B8A3
0x18019b7e0  mov     rax, [r12]
0x18019b7e4  mov     rcx, r12
0x18019b7e7  mov     rax, [rax+60h]
0x18019b7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b7f0  mov     eax, [rdi+208h]
0x18019b7f6  sub     eax, 5
0x18019b7f9  cmp     eax, 1
0x18019b7fc  ja      loc_18019B8A8
0x18019b802  mov     rcx, r13
0x18019b805  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b80a  lea     rdx, [rsp+2C0h+hKey]
0x18019b80f  mov     qword ptr [rsp+2C0h+dwOptions], rdx; phkResult
0x18019b814  mov     r9d, 20006h; samDesired
0x18019b81a  xor     r8d, r8d; ulOptions
0x18019b81d  mov     rdx, rax; lpSubKey
0x18019b820  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18019b827  call    cs:__imp_RegOpenKeyExW
0x18019b82e  nop     dword ptr [rax+rax+00h]
0x18019b833  mov     ebx, eax
0x18019b835  test    eax, eax
0x18019b837  jle     short loc_18019B842
0x18019b839  movzx   ebx, ax
0x18019b83c  or      ebx, 80070000h
0x18019b842  test    ebx, ebx
0x18019b844  js      short loc_18019B8A8
0x18019b846  lea     rcx, [rdi+298h]
0x18019b84d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18019b852  mov     rdx, rax; lpValueName
0x18019b855  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18019b85a  call    cs:__imp_RegDeleteValueW
0x18019b861  nop     dword ptr [rax+rax+00h]
0x18019b866  mov     ebx, eax
0x18019b868  test    eax, 0FFFFFFFDh
0x18019b86d  jz      short loc_18019B87E
0x18019b86f  test    eax, eax
0x18019b871  jle     short loc_18019B880
0x18019b873  movzx   ebx, ax
0x18019b876  or      ebx, 80070000h
0x18019b87c  jmp     short loc_18019B880
0x18019b87e  xor     ebx, ebx
0x18019b880  mov     r8, r12
0x18019b883  mov     edx, 1
0x18019b888  mov     rcx, rdi
0x18019b88b  call    ?SetErrorMessageCode@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAXW4ErrorMessageCode@23@PEAVISlideshowSingleton@23@@Z; SystemSettings::Personalization::CSlideshowFolderHelper::SetErrorMessageCode(SystemSettings::Personalization::ErrorMessageCode,SystemSettings::Personalization::ISlideshowSingleton *)
0x18019b890  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18019b895  call    cs:__imp_RegCloseKey
0x18019b89c  nop     dword ptr [rax+rax+00h]
0x18019b8a1  jmp     short loc_18019B8A8
0x18019b8a3  mov     ebx, 8000FFFFh
0x18019b8a8  mov     eax, ebx
0x18019b8aa  mov     rcx, [rbp+1C0h+var_40]
0x18019b8b1  xor     rcx, rsp; StackCookie
0x18019b8b4  call    __security_check_cookie
0x18019b8b9  mov     rbx, [rsp+2C0h+arg_18]
0x18019b8c1  add     rsp, 290h
0x18019b8c8  pop     r15
0x18019b8ca  pop     r14
0x18019b8cc  pop     r13
0x18019b8ce  pop     r12
0x18019b8d0  pop     rdi
0x18019b8d1  pop     rsi
0x18019b8d2  pop     rbp
0x18019b8d3  retn
```
