# SystemSettings::Personalization::CSlideshowSingleton::OnSingletonInit(void)

- ea: `0x18019f5c0`
- end: `0x18019f9b9`
- name: `?OnSingletonInit@CSlideshowSingleton@Personalization@SystemSettings@@MEAAJXZ`
- size: `1017`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::CSlideshowSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001a64c`
- `0x18002d624`
- `0x18004e624`
- `0x18004e8d4`
- `0x18006956c`
- `0x180086824`
- `0x18010f998`
- `0x18019ae2c`
- `0x18019f5c0`
- `0x18019fa40`
- `0x18019fa80`
- `0x18019fb58`
- `0x18021fbd0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f6c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019f6c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f6f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f754`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f6f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019f754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f65d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f723`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f65d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019f723`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::Personalization::CSlideshowSingleton::OnSingletonInit(
        SystemSettings::Personalization::CSlideshowSingleton *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v5; // r9d
  void *v6; // r8
  int v7; // ecx
  unsigned int *v8; // r8
  CreativeFramework::LockScreenCreativeConfigHelpers *v9; // rax
  unsigned __int16 **v10; // rdx
  int CurrentUserSidString; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v16; // [rsp+28h] [rbp-D8h]
  unsigned int *v17; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  int v22[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v23[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  SystemSettings::Personalization::CSlideshowFolderHelper::Initialize(
    (SystemSettings::Personalization::CSlideshowSingleton *)((char *)this + 240),
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
    a3,
    a4,
    L"LockScreenSlideshow",
    v16,
    L"Microsoft\\Windows\\LockScreenSlideshow",
    L"Software\\AppDataLow\\Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
    0xAu);
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Windows\\Control Panel\\Desktop",
          0,
          0x20019u,
          &hKey) )
  {
    pv = 0;
    if ( SHRegAllocData(hKey, 0, L"ScreenSaveActive", v5, &pv, v17) >= 0 )
    {
      v6 = pv;
      if ( pv )
      {
        v7 = *(unsigned __int16 *)pv - 48;
        if ( *(_WORD *)pv == 48 )
          v7 = *((unsigned __int16 *)pv + 1);
        if ( !v7 )
          *((_BYTE *)this + 1008) = 0;
        CoTaskMemFree(v6);
      }
    }
    *((_BYTE *)this + 1009) = (unsigned int)SHRegValueExists(hKey, L"SCRNSAVE.EXE", (unsigned int *)v6) != 0;
    RegCloseKey(hKey);
  }
  v20 = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", 0, 0x20019u, &v20) )
  {
    if ( (unsigned int)SHRegValueExists(v20, L"SCRNSAVE.EXE", v8) )
      *((_BYTE *)this + 1010) = 1;
    RegCloseKey(v20);
  }
  if ( *((_BYTE *)this + 1008) && (*((_BYTE *)this + 1010) || *((_BYTE *)this + 1009)) )
  {
    PersonalizeSettingsTelemetry::ScreenSaverIsCurrentlySet();
    SHRegSetBOOL(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
      L"SlideshowEnabled",
      0);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1040);
  CRegistryChangeListener_CreateInstance(
    -2147483647,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
    1,
    SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_Slideshow,
    this,
    (char *)this + 1040);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1048);
  CRegistryChangeListener_CreateInstance(
    -2147483647,
    L"Software\\AppDataLow\\Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
    1,
    SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_Slideshow_LowIL,
    this,
    (char *)this + 1048);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1072);
  CRegistryChangeListener_CreateInstance(
    -2147483647,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
    1,
    SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_ContentDeliveryManager,
    this,
    (char *)this + 1072);
  *(_QWORD *)v22 = 0;
  v9 = (CreativeFramework::LockScreenCreativeConfigHelpers *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v22);
  CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(v9, v10);
  v12 = CurrentUserSidString;
  if ( CurrentUserSidString < 0 )
  {
    v13 = 152;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\lockscreenslideshowsingleton.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      phkResult);
    goto LABEL_28;
  }
  phkResult = v22[0];
  CurrentUserSidString = StringCchPrintfW(
                           v23,
                           0x104u,
                           L"%s\\%s",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative");
  v12 = CurrentUserSidString;
  if ( CurrentUserSidString < 0 )
  {
    v13 = 154;
    goto LABEL_22;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1072);
  CRegistryChangeListener_CreateInstance(
    -2147483646,
    v23,
    1,
    SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_ContentDeliveryManager,
    this,
    (char *)this + 1072);
  if ( (int)SystemSettings::Personalization::CSlideshowSingleton::_InitializeFeedManager(this) >= 0 )
  {
    pv = 0;
    v21 = 0;
    if ( (*(int (__fastcall **)(_QWORD, LPVOID *, __int64 *))(**((_QWORD **)this + 129) + 96LL))(
           *((_QWORD *)this + 129),
           &pv,
           &v21) >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1056);
      CRegistryChangeListener_CreateInstance(
        -2147483647,
        pv,
        4,
        SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_FeedList,
        this,
        (char *)this + 1056);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1064);
      CRegistryChangeListener_CreateInstance(
        -2147483647,
        v21,
        0,
        SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_SelectedFeed,
        this,
        (char *)this + 1064);
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v21);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pv);
  }
  v12 = 0;
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v22);
  return v12;
}

```

## disassembly

```asm
0x18019f5c0  push    rbp
0x18019f5c2  push    rbx
0x18019f5c3  push    rsi
0x18019f5c4  push    rdi
0x18019f5c5  push    r13
0x18019f5c7  push    r15
0x18019f5c9  lea     rbp, [rsp-1A8h]
0x18019f5d1  sub     rsp, 2A8h
0x18019f5d8  mov     rax, cs:__security_cookie
0x18019f5df  xor     rax, rsp
0x18019f5e2  mov     [rbp+1D0h+var_40], rax
0x18019f5e9  mov     rdi, rcx
0x18019f5ec  add     rcx, 0F0h; this
0x18019f5f3  mov     [rsp+2D0h+var_290], 0Ah; unsigned int
0x18019f5fb  lea     r13, aSoftwareAppdat; "Software\\AppDataLow\\Software\\Microso"...
0x18019f602  mov     [rsp+2D0h+var_298], r13; unsigned __int16 *
0x18019f607  lea     rax, aMicrosoftWindo_15; "Microsoft\\Windows\\LockScreenSlideshow"
0x18019f60e  mov     [rsp+2D0h+var_2A0], rax; unsigned __int16 *
0x18019f613  lea     rax, aLockscreenslid; "LockScreenSlideshow"
0x18019f61a  mov     [rsp+2D0h+phkResult], rax; unsigned __int16 *
0x18019f61f  lea     rsi, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18019f626  mov     rdx, rsi; unsigned __int16 *
0x18019f629  call    ?Initialize@CSlideshowFolderHelper@Personalization@SystemSettings@@QEAAJPEBG000000I@Z; SystemSettings::Personalization::CSlideshowFolderHelper::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,uint)
0x18019f62e  mov     [rsp+2D0h+hKey], 0
0x18019f637  lea     rax, [rsp+2D0h+hKey]
0x18019f63c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18019f641  mov     ebx, 20019h
0x18019f646  mov     r9d, ebx; samDesired
0x18019f649  xor     r8d, r8d; ulOptions
0x18019f64c  lea     rdx, aSoftwarePolici_2; "Software\\Policies\\Microsoft\\Windows"...
0x18019f653  mov     r15, 0FFFFFFFF80000001h
0x18019f65a  mov     rcx, r15; hKey
0x18019f65d  call    cs:__imp_RegOpenKeyExW
0x18019f664  nop     dword ptr [rax+rax+00h]
0x18019f669  test    eax, eax
0x18019f66b  jnz     loc_18019F700
0x18019f671  mov     [rsp+2D0h+pv], 0
0x18019f67a  lea     rax, [rsp+2D0h+pv]
0x18019f67f  mov     [rsp+2D0h+phkResult], rax; void **
0x18019f684  lea     r8, aScreensaveacti; "ScreenSaveActive"
0x18019f68b  xor     edx, edx; unsigned __int16 *
0x18019f68d  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18019f692  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18019f697  test    eax, eax
0x18019f699  js      short loc_18019F6D3
0x18019f69b  mov     r8, [rsp+2D0h+pv]
0x18019f6a0  test    r8, r8
0x18019f6a3  jz      short loc_18019F6D3
0x18019f6a5  movzx   ecx, word ptr [r8]
0x18019f6a9  sub     ecx, 30h ; '0'
0x18019f6ac  jnz     short loc_18019F6BA
0x18019f6ae  movzx   ecx, word ptr [r8+2]
0x18019f6b3  xor     eax, eax
0x18019f6b5  movzx   edx, ax
0x18019f6b8  sub     ecx, edx
0x18019f6ba  test    ecx, ecx
0x18019f6bc  jnz     short loc_18019F6C4
0x18019f6be  mov     [rdi+3F0h], cl
0x18019f6c4  mov     rcx, r8; pv
0x18019f6c7  call    cs:__imp_CoTaskMemFree
0x18019f6ce  nop     dword ptr [rax+rax+00h]
0x18019f6d3  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x18019f6da  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x18019f6df  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x18019f6e4  test    eax, eax
0x18019f6e6  setnz   al
0x18019f6e9  mov     [rdi+3F1h], al
0x18019f6ef  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18019f6f4  call    cs:__imp_RegCloseKey
0x18019f6fb  nop     dword ptr [rax+rax+00h]
0x18019f700  mov     [rsp+2D0h+var_270], 0
0x18019f709  lea     rax, [rsp+2D0h+var_270]
0x18019f70e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18019f713  mov     r9d, ebx; samDesired
0x18019f716  xor     r8d, r8d; ulOptions
0x18019f719  lea     rdx, pszSubKey; "Control Panel\\Desktop"
0x18019f720  mov     rcx, r15; hKey
0x18019f723  call    cs:__imp_RegOpenKeyExW
0x18019f72a  nop     dword ptr [rax+rax+00h]
0x18019f72f  test    eax, eax
0x18019f731  jnz     short loc_18019F760
0x18019f733  lea     rdx, aScrnsaveExe; "SCRNSAVE.EXE"
0x18019f73a  mov     rcx, [rsp+2D0h+var_270]; HKEY
0x18019f73f  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x18019f744  test    eax, eax
0x18019f746  jz      short loc_18019F74F
0x18019f748  mov     byte ptr [rdi+3F2h], 1
0x18019f74f  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18019f754  call    cs:__imp_RegCloseKey
0x18019f75b  nop     dword ptr [rax+rax+00h]
0x18019f760  cmp     byte ptr [rdi+3F0h], 0
0x18019f767  jz      short loc_18019F795
0x18019f769  cmp     byte ptr [rdi+3F2h], 0
0x18019f770  jnz     short loc_18019F77B
0x18019f772  cmp     byte ptr [rdi+3F1h], 0
0x18019f779  jz      short loc_18019F795
0x18019f77b  call    ?ScreenSaverIsCurrentlySet@PersonalizeSettingsTelemetry@@SAXXZ; PersonalizeSettingsTelemetry::ScreenSaverIsCurrentlySet(void)
0x18019f780  xor     r9d, r9d; int
0x18019f783  lea     r8, aSlideshowenabl_0; "SlideshowEnabled"
0x18019f78a  mov     rdx, rsi; unsigned __int16 *
0x18019f78d  mov     rcx, r15; HKEY
0x18019f790  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18019f795  lea     rbx, [rdi+410h]
0x18019f79c  mov     rcx, rbx
0x18019f79f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f7a4  mov     [rsp+2D0h+var_2A8], rbx
0x18019f7a9  mov     [rsp+2D0h+phkResult], rdi
0x18019f7ae  lea     r9, ?_s_RegistryChangeCallback_Slideshow@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_Slideshow(void *)
0x18019f7b5  mov     r8d, 1
0x18019f7bb  mov     rdx, rsi
0x18019f7be  mov     rcx, r15
0x18019f7c1  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f7c6  lea     rbx, [rdi+418h]
0x18019f7cd  mov     rcx, rbx
0x18019f7d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f7d5  mov     [rsp+2D0h+var_2A8], rbx
0x18019f7da  mov     [rsp+2D0h+phkResult], rdi
0x18019f7df  lea     r9, ?_s_RegistryChangeCallback_Slideshow_LowIL@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_Slideshow_LowIL(void *)
0x18019f7e6  mov     r8d, 1
0x18019f7ec  mov     rdx, r13
0x18019f7ef  mov     rcx, r15
0x18019f7f2  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f7f7  lea     rsi, [rdi+430h]
0x18019f7fe  mov     rcx, rsi
0x18019f801  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f806  mov     [rsp+2D0h+var_2A8], rsi
0x18019f80b  mov     [rsp+2D0h+phkResult], rdi
0x18019f810  lea     r9, ?_s_RegistryChangeCallback_ContentDeliveryManager@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_ContentDeliveryManager(void *)
0x18019f817  mov     r8d, 1
0x18019f81d  lea     rdx, ?c_contentDeliveryManagerKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18019f824  mov     rcx, r15
0x18019f827  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f82c  mov     qword ptr [rsp+2D0h+var_260], 0
0x18019f835  lea     rcx, [rsp+2D0h+var_260]
0x18019f83a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18019f83f  mov     rcx, rax; this
0x18019f842  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x18019f847  mov     ebx, eax
0x18019f849  test    eax, eax
0x18019f84b  jns     short loc_18019F854
0x18019f84d  mov     edx, 98h
0x18019f852  jmp     short loc_18019F885
0x18019f854  mov     rax, qword ptr [rsp+2D0h+var_260]
0x18019f859  mov     [rsp+2D0h+phkResult], rax; int
0x18019f85e  lea     r9, ?c_logonUICreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18019f865  lea     r8, aSS; "%s\\%s"
0x18019f86c  mov     edx, 104h; unsigned __int64
0x18019f871  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18019f875  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019f87a  mov     ebx, eax
0x18019f87c  test    eax, eax
0x18019f87e  jns     short loc_18019F8A0
0x18019f880  mov     edx, 9Ah; void *
0x18019f885  lea     r8, aShellSystemset_114; "shell\\systemsettingsthreshold\\handler"...
0x18019f88c  mov     r9d, eax; char *
0x18019f88f  mov     rcx, [rbp+1D8h]; this
0x18019f896  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019f89b  jmp     loc_18019F98D
0x18019f8a0  mov     rcx, rsi
0x18019f8a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f8a8  mov     [rsp+2D0h+var_2A8], rsi
0x18019f8ad  mov     [rsp+2D0h+phkResult], rdi
0x18019f8b2  lea     r9, ?_s_RegistryChangeCallback_ContentDeliveryManager@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_ContentDeliveryManager(void *)
0x18019f8b9  mov     r8d, 1
0x18019f8bf  lea     rdx, [rbp+1D0h+var_250]
0x18019f8c3  mov     rcx, 0FFFFFFFF80000002h
0x18019f8ca  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f8cf  mov     rcx, rdi; this
0x18019f8d2  call    ?_InitializeFeedManager@CSlideshowSingleton@Personalization@SystemSettings@@AEAAJXZ; SystemSettings::Personalization::CSlideshowSingleton::_InitializeFeedManager(void)
0x18019f8d7  test    eax, eax
0x18019f8d9  js      loc_18019F98B
0x18019f8df  mov     [rsp+2D0h+pv], 0
0x18019f8e8  mov     [rsp+2D0h+var_268], 0
0x18019f8f1  mov     rcx, [rdi+408h]
0x18019f8f8  mov     rax, [rcx]
0x18019f8fb  lea     r8, [rsp+2D0h+var_268]
0x18019f900  lea     rdx, [rsp+2D0h+pv]
0x18019f905  mov     rax, [rax+60h]
0x18019f909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019f90e  test    eax, eax
0x18019f910  js      short loc_18019F976
0x18019f912  lea     rbx, [rdi+420h]
0x18019f919  mov     rcx, rbx
0x18019f91c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f921  mov     [rsp+2D0h+var_2A8], rbx
0x18019f926  mov     [rsp+2D0h+phkResult], rdi
0x18019f92b  lea     r9, ?_s_RegistryChangeCallback_FeedList@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_FeedList(void *)
0x18019f932  mov     r8d, 4
0x18019f938  mov     rdx, [rsp+2D0h+pv]
0x18019f93d  mov     rcx, r15
0x18019f940  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f945  lea     rbx, [rdi+428h]
0x18019f94c  mov     rcx, rbx
0x18019f94f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019f954  mov     [rsp+2D0h+var_2A8], rbx
0x18019f959  mov     [rsp+2D0h+phkResult], rdi
0x18019f95e  lea     r9, ?_s_RegistryChangeCallback_SelectedFeed@CSlideshowSingleton@Personalization@SystemSettings@@CAXPEAX@Z; SystemSettings::Personalization::CSlideshowSingleton::_s_RegistryChangeCallback_SelectedFeed(void *)
0x18019f965  xor     r8d, r8d
0x18019f968  mov     rdx, [rsp+2D0h+var_268]
0x18019f96d  mov     rcx, r15
0x18019f970  call    ?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z; CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)
0x18019f975  nop
0x18019f976  lea     rcx, [rsp+2D0h+var_268]
0x18019f97b  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18019f980  nop
0x18019f981  lea     rcx, [rsp+2D0h+pv]
0x18019f986  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18019f98b  xor     ebx, ebx
0x18019f98d  lea     rcx, [rsp+2D0h+var_260]
0x18019f992  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019f997  mov     eax, ebx
0x18019f999  mov     rcx, [rbp+1D0h+var_40]
0x18019f9a0  xor     rcx, rsp; StackCookie
0x18019f9a3  call    __security_check_cookie
0x18019f9a8  add     rsp, 2A8h
0x18019f9af  pop     r15
0x18019f9b1  pop     r13
0x18019f9b3  pop     rdi
0x18019f9b4  pop     rsi
0x18019f9b5  pop     rbx
0x18019f9b6  pop     rbp
0x18019f9b7  retn
```
