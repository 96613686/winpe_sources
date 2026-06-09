# SystemSettings::Personalization::BackgroundChooseBackground::SetSlideshowImages(void)

- ea: `0x180122a5c`
- end: `0x180122db6`
- name: `?SetSlideshowImages@BackgroundChooseBackground@Personalization@SystemSettings@@AEAAJXZ`
- size: `858`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::BackgroundChooseBackground *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18011f110`
- `0x180126da4`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18004d1ac`
- `0x1801185a8`
- `0x1801196d4`
- `0x18011e038`
- `0x18011fd08`
- `0x180122a5c`
- `0x180123d00`
- `0x1801247d0`
- `0x1801292bc`
- `0x1801976d4`
- `0x180197d50`
- `0x1801981c8`
- `0x180198540`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180122ca2`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180122c32`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180122c32`
- `SHELL32!__imp_ILFree` at `0x180122c75`
- `SHELL32!__imp_ILFree` at `0x180122c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122bf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::Personalization::BackgroundChooseBackground::SetSlideshowImages(
        SystemSettings::Personalization::BackgroundChooseBackground *this)
{
  struct IShellItemArray **v1; // rdx
  int ImageSourceDirectoriesFromRegistry; // esi
  struct IShellItemArray *v3; // rdi
  HRESULT (__stdcall *GetItemAt)(IShellItemArray *, DWORD, IShellItem **); // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // r8d
  unsigned __int16 **v9; // r9
  HSTRING *v10; // r8
  struct _ITEMIDLIST **StringRawBuffer; // rax
  const unsigned __int16 *v12; // r8
  struct IShellItemArray *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v19[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  struct IShellItemArray *v22; // [rsp+40h] [rbp-C0h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+48h] [rbp-B8h] BYREF
  struct IShellLibrary *v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST rgpidl; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v29[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::`vftable';
  PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::StartActivity((PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages *)v29);
  v20 = 0;
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ImageSourceDirectoriesFromRegistry = SystemSettings::Personalization::RetrieveImageSourceDirectoriesFromRegistry(
                                         (SystemSettings::Personalization *)&v22,
                                         v1);
  if ( ImageSourceDirectoriesFromRegistry >= 0 )
  {
    if ( v22 )
    {
      ImageSourceDirectoriesFromRegistry = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))v22->lpVtbl->GetCount)(
                                             v22,
                                             &v20);
      if ( ImageSourceDirectoriesFromRegistry >= 0 )
      {
        if ( !v20 )
          goto LABEL_27;
        if ( v20 == 1 )
        {
          v25 = 0;
          v3 = v22;
          GetItemAt = v22->lpVtbl->GetItemAt;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          if ( ((int (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 *))GetItemAt)(v3, 0, &v25) >= 0 )
          {
            pv[0] = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v25 + 40LL))(v25, 2147844096LL, pv) >= 0 )
            {
              v24 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
              if ( (int)SHLoadLibraryFromKnownFolder(v6, v5, v7, &v24) >= 0 )
              {
                v19[0] = 0;
                if ( (int)IsPathInLibrary((const unsigned __int16 *)pv[0], v24, v8, v9, v19) >= 0 )
                {
                  if ( v19[0] )
                  {
                    WindowsDeleteString(0);
                    string = 0;
                    if ( (int)SystemSettings::DataModel::GetResourceStringById(
                                (SystemSettings::DataModel *)L"SystemSettings_Start_PlacesPicturesDescription",
                                &string,
                                v10) >= 0 )
                    {
                      rgpidl = 0;
                      StringRawBuffer = (struct _ITEMIDLIST **)WindowsGetStringRawBuffer(string, 0);
                      if ( (int)SystemSettings::Personalization::GetSearchPidlForPictureLibrary(
                                  (SystemSettings::Personalization *)&rgpidl,
                                  StringRawBuffer,
                                  v12) >= 0 )
                      {
                        ppsiItemArray = 0;
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsiItemArray);
                        if ( SHCreateShellItemArrayFromIDLists(1u, &rgpidl, &ppsiItemArray) >= 0 )
                        {
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
                          v13 = ppsiItemArray;
                          if ( ppsiItemArray )
                          {
                            ((void (__fastcall *)(IShellItemArray *))ppsiItemArray->lpVtbl->AddRef)(ppsiItemArray);
                            v13 = ppsiItemArray;
                          }
                          v22 = v13;
                        }
                        ILFree((LPITEMIDLIST)rgpidl);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppsiItemArray);
                      }
                    }
                    WindowsDeleteString(string);
                  }
                }
              }
              CoTaskMemFree(pv[0]);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        }
        ppv = 0;
        ImageSourceDirectoriesFromRegistry = SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(&ppv);
        if ( ImageSourceDirectoriesFromRegistry >= 0 )
        {
          ImageSourceDirectoriesFromRegistry = SystemSettings::Personalization::DesktopWallpaperHelper::Enable(
                                                 (SystemSettings::Personalization::DesktopWallpaperHelper *)&ppv,
                                                 1);
          if ( ImageSourceDirectoriesFromRegistry >= 0 )
            ImageSourceDirectoriesFromRegistry = SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshow(
                                                   (SystemSettings::Personalization::DesktopWallpaperHelper *)&ppv,
                                                   v22);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
    }
  }
  if ( v20 )
    goto LABEL_33;
LABEL_27:
  ppv = 0;
  v14 = SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(&ppv);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v14 = SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshow(
            (SystemSettings::Personalization::DesktopWallpaperHelper *)&ppv,
            0);
    v15 = v14;
    if ( v14 < 0 )
    {
      v16 = 675;
      goto LABEL_31;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_33:
    wil::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v29,
      (unsigned int)ImageSourceDirectoriesFromRegistry);
    v15 = ImageSourceDirectoriesFromRegistry;
    goto LABEL_34;
  }
  v16 = 674;
LABEL_31:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
    (const char *)(unsigned int)v14,
    v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::~BackgroundChooseBackgroundSetSlideshowImages((PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages *)v29);
  return v15;
}

```

## disassembly

```asm
0x180122a5c  push    rbp
0x180122a5e  push    rbx
0x180122a5f  push    rsi
0x180122a60  push    rdi
0x180122a61  push    r14
0x180122a63  lea     rbp, [rsp-0E0h]
0x180122a6b  sub     rsp, 1E0h
0x180122a72  mov     rax, cs:__security_cookie
0x180122a79  xor     rax, rsp
0x180122a7c  mov     [rbp+100h+var_30], rax
0x180122a83  lea     rdx, aBackgroundchoo_0; "BackgroundChooseBackgroundSetSlideshowI"...
0x180122a8a  lea     rcx, [rbp+100h+var_180]; struct wil::details::IFailureCallback *
0x180122a8e  call    ??0?$ActivityBase@VPersonalizeSettingsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180122a93  lea     rax, ??_7BackgroundChooseBackgroundSetSlideshowImages@PersonalizeSettingsTelemetry@@6B@; const PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::`vftable'
0x180122a9a  mov     [rbp+100h+var_180], rax
0x180122a9e  lea     rcx, [rbp+100h+var_180]; this
0x180122aa2  call    ?StartActivity@BackgroundChooseBackgroundSetSlideshowImages@PersonalizeSettingsTelemetry@@QEAAXXZ; PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::StartActivity(void)
0x180122aa7  nop
0x180122aa8  xor     r14d, r14d
0x180122aab  mov     [rsp+200h+var_1CC], r14d
0x180122ab0  mov     [rsp+200h+var_1C0], r14
0x180122ab5  lea     rcx, [rsp+200h+var_1C0]
0x180122aba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122abf  lea     rcx, [rsp+200h+var_1C0]; this
0x180122ac4  call    ?RetrieveImageSourceDirectoriesFromRegistry@Personalization@SystemSettings@@YAJPEAPEAUIShellItemArray@@@Z; SystemSettings::Personalization::RetrieveImageSourceDirectoriesFromRegistry(IShellItemArray * *)
0x180122ac9  mov     esi, eax
0x180122acb  test    eax, eax
0x180122acd  js      loc_180122D0D
0x180122ad3  mov     rcx, [rsp+200h+var_1C0]
0x180122ad8  test    rcx, rcx
0x180122adb  jz      loc_180122D0D
0x180122ae1  mov     rax, [rcx]
0x180122ae4  lea     rdx, [rsp+200h+var_1CC]
0x180122ae9  mov     rax, [rax+38h]
0x180122aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122af2  mov     esi, eax
0x180122af4  test    eax, eax
0x180122af6  js      loc_180122D0D
0x180122afc  mov     eax, [rsp+200h+var_1CC]
0x180122b00  test    eax, eax
0x180122b02  jz      loc_180122D15
0x180122b08  cmp     eax, 1
0x180122b0b  jnz     loc_180122CC4
0x180122b11  mov     [rsp+200h+var_1A8], r14
0x180122b16  mov     rdi, [rsp+200h+var_1C0]
0x180122b1b  mov     rax, [rdi]
0x180122b1e  mov     rbx, [rax+40h]
0x180122b22  lea     rcx, [rsp+200h+var_1A8]
0x180122b27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122b2c  lea     r8, [rsp+200h+var_1A8]
0x180122b31  xor     edx, edx
0x180122b33  mov     rcx, rdi
0x180122b36  mov     rax, rbx
0x180122b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122b3e  test    eax, eax
0x180122b40  js      loc_180122CBA
0x180122b46  mov     [rsp+200h+pv], r14
0x180122b4b  mov     rcx, [rsp+200h+var_1A8]
0x180122b50  mov     rax, [rcx]
0x180122b53  lea     r8, [rsp+200h+pv]
0x180122b58  mov     edx, 80058000h
0x180122b5d  mov     rax, [rax+28h]
0x180122b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122b66  test    eax, eax
0x180122b68  js      loc_180122CBA
0x180122b6e  mov     [rsp+200h+var_1B0], r14
0x180122b73  lea     rcx, [rsp+200h+var_1B0]
0x180122b78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122b7d  lea     r9, [rsp+200h+var_1B0]
0x180122b82  call    SHLoadLibraryFromKnownFolder
0x180122b87  test    eax, eax
0x180122b89  js      loc_180122C9D
0x180122b8f  mov     [rsp+200h+var_1D0], r14b
0x180122b94  lea     rax, [rsp+200h+var_1D0]
0x180122b99  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x180122b9e  mov     rdx, [rsp+200h+var_1B0]; struct IShellLibrary *
0x180122ba3  mov     rcx, [rsp+200h+pv]; unsigned __int16 *
0x180122ba8  call    ?IsPathInLibrary@@YAJPEBGPEAUIShellLibrary@@KPEAPEAGPEAE@Z; IsPathInLibrary(ushort const *,IShellLibrary *,ulong,ushort * *,uchar *)
0x180122bad  test    eax, eax
0x180122baf  js      loc_180122C9D
0x180122bb5  cmp     [rsp+200h+var_1D0], r14b
0x180122bba  jz      loc_180122C9D
0x180122bc0  xor     ecx, ecx; string
0x180122bc2  call    cs:__imp_WindowsDeleteString
0x180122bc9  nop     dword ptr [rax+rax+00h]
0x180122bce  mov     [rsp+200h+string], r14
0x180122bd3  lea     rdx, [rsp+200h+string]; HSTRING *
0x180122bd8  lea     rcx, aSystemsettings_1053; "SystemSettings_Start_PlacesPicturesDesc"...
0x180122bdf  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180122be4  test    eax, eax
0x180122be6  js      loc_180122C8C
0x180122bec  mov     [rsp+200h+rgpidl], r14
0x180122bf1  xor     edx, edx; length
0x180122bf3  mov     rcx, [rsp+200h+string]; string
0x180122bf8  call    cs:__imp_WindowsGetStringRawBuffer
0x180122bff  nop     dword ptr [rax+rax+00h]
0x180122c04  mov     rdx, rax; struct _ITEMIDLIST **
0x180122c07  lea     rcx, [rsp+200h+rgpidl]; this
0x180122c0c  call    ?GetSearchPidlForPictureLibrary@Personalization@SystemSettings@@YAJPEAPEFAU_ITEMIDLIST@@PEBG@Z; SystemSettings::Personalization::GetSearchPidlForPictureLibrary(_ITEMIDLIST * *,ushort const *)
0x180122c11  test    eax, eax
0x180122c13  js      short loc_180122C8C
0x180122c15  mov     [rsp+200h+ppsiItemArray], r14
0x180122c1a  lea     rcx, [rsp+200h+ppsiItemArray]
0x180122c1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122c24  lea     r8, [rsp+200h+ppsiItemArray]; ppsiItemArray
0x180122c29  lea     rdx, [rsp+200h+rgpidl]; rgpidl
0x180122c2e  lea     ecx, [r14+1]; cidl
0x180122c32  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180122c39  nop     dword ptr [rax+rax+00h]
0x180122c3e  test    eax, eax
0x180122c40  js      short loc_180122C70
0x180122c42  lea     rcx, [rsp+200h+var_1C0]
0x180122c47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122c4c  nop
0x180122c4d  mov     rcx, [rsp+200h+ppsiItemArray]
0x180122c52  test    rcx, rcx
0x180122c55  jz      short loc_180122C68
0x180122c57  mov     rax, [rcx]
0x180122c5a  mov     rax, [rax+8]
0x180122c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122c63  mov     rcx, [rsp+200h+ppsiItemArray]
0x180122c68  mov     [rsp+200h+var_1C0], rcx
0x180122c6d  mov     esi, r14d
0x180122c70  mov     rcx, [rsp+200h+rgpidl]; pidl
0x180122c75  call    cs:__imp_ILFree
0x180122c7c  nop     dword ptr [rax+rax+00h]
0x180122c81  lea     rcx, [rsp+200h+ppsiItemArray]
0x180122c86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122c8b  nop
0x180122c8c  mov     rcx, [rsp+200h+string]; string
0x180122c91  call    cs:__imp_WindowsDeleteString
0x180122c98  nop     dword ptr [rax+rax+00h]
0x180122c9d  mov     rcx, [rsp+200h+pv]; pv
0x180122ca2  call    cs:__imp_CoTaskMemFree
0x180122ca9  nop     dword ptr [rax+rax+00h]
0x180122cae  nop
0x180122caf  lea     rcx, [rsp+200h+var_1B0]
0x180122cb4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122cb9  nop
0x180122cba  lea     rcx, [rsp+200h+var_1A8]
0x180122cbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122cc4  mov     [rsp+200h+ppv], r14
0x180122cc9  test    esi, esi
0x180122ccb  js      short loc_180122D03
0x180122ccd  lea     rcx, [rsp+200h+ppv]; ppv
0x180122cd2  call    ?Initialize@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJXZ; SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(void)
0x180122cd7  mov     esi, eax
0x180122cd9  test    eax, eax
0x180122cdb  js      short loc_180122D03
0x180122cdd  mov     edx, 1; int
0x180122ce2  lea     rcx, [rsp+200h+ppv]; this
0x180122ce7  call    ?Enable@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJH@Z; SystemSettings::Personalization::DesktopWallpaperHelper::Enable(int)
0x180122cec  mov     esi, eax
0x180122cee  test    eax, eax
0x180122cf0  js      short loc_180122D03
0x180122cf2  mov     rdx, [rsp+200h+var_1C0]; struct IShellItemArray *
0x180122cf7  lea     rcx, [rsp+200h+ppv]; this
0x180122cfc  call    ?SetSlideshow@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAUIShellItemArray@@@Z; SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshow(IShellItemArray *)
0x180122d01  mov     esi, eax
0x180122d03  lea     rcx, [rsp+200h+ppv]
0x180122d08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122d0d  mov     eax, [rsp+200h+var_1CC]
0x180122d11  test    eax, eax
0x180122d13  jnz     short loc_180122D75
0x180122d15  mov     [rsp+200h+ppv], r14
0x180122d1a  lea     rcx, [rsp+200h+ppv]; ppv
0x180122d1f  call    ?Initialize@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJXZ; SystemSettings::Personalization::DesktopWallpaperHelper::Initialize(void)
0x180122d24  mov     ebx, eax
0x180122d26  test    eax, eax
0x180122d28  jns     short loc_180122D31
0x180122d2a  mov     edx, 2A2h
0x180122d2f  jmp     short loc_180122D48
0x180122d31  xor     edx, edx; struct IShellItemArray *
0x180122d33  lea     rcx, [rsp+200h+ppv]; this
0x180122d38  call    ?SetSlideshow@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAUIShellItemArray@@@Z; SystemSettings::Personalization::DesktopWallpaperHelper::SetSlideshow(IShellItemArray *)
0x180122d3d  mov     ebx, eax
0x180122d3f  test    eax, eax
0x180122d41  jns     short loc_180122D6B
0x180122d43  mov     edx, 2A3h; void *
0x180122d48  mov     r9d, eax; char *
0x180122d4b  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x180122d52  mov     rcx, [rbp+108h]; this
0x180122d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122d5e  nop
0x180122d5f  lea     rcx, [rsp+200h+ppv]
0x180122d64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122d69  jmp     short loc_180122D82
0x180122d6b  lea     rcx, [rsp+200h+ppv]
0x180122d70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122d75  mov     edx, esi
0x180122d77  lea     rcx, [rbp+100h+var_180]
0x180122d7b  call    ?Stop@?$ActivityBase@VPersonalizeSettingsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PersonalizeSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180122d80  mov     ebx, esi
0x180122d82  lea     rcx, [rsp+200h+var_1C0]
0x180122d87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180122d8c  nop
0x180122d8d  lea     rcx, [rbp+100h+var_180]; this
0x180122d91  call    ??1BackgroundChooseBackgroundSetSlideshowImages@PersonalizeSettingsTelemetry@@QEAA@XZ; PersonalizeSettingsTelemetry::BackgroundChooseBackgroundSetSlideshowImages::~BackgroundChooseBackgroundSetSlideshowImages(void)
0x180122d96  mov     eax, ebx
0x180122d98  mov     rcx, [rbp+100h+var_30]
0x180122d9f  xor     rcx, rsp; StackCookie
0x180122da2  call    __security_check_cookie
0x180122da7  add     rsp, 1E0h
0x180122dae  pop     r14
0x180122db0  pop     rdi
0x180122db1  pop     rsi
0x180122db2  pop     rbx
0x180122db3  pop     rbp
0x180122db4  retn
```
