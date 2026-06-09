# UninstallTencentEmulator(void)

- ea: `0x180030164`
- end: `0x180030672`
- name: `?UninstallTencentEmulator@@YAXXZ`
- size: `1294`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030f28`

## callees

- `0x1800026b0`
- `0x1800030ee`
- `0x18000316c`
- `0x1800033c7`
- `0x1800033f7`
- `0x18000dc4f`
- `0x180011d18`
- `0x180021b9c`
- `0x180021cdc`
- `0x18002c4b8`
- `0x18002d674`
- `0x18002da38`
- `0x18002e398`
- `0x18002e550`
- `0x18002e5e4`
- `0x18002e64c`
- `0x18002efd8`
- `0x18002f1b4`
- `0x180030164`
- `0x180030aac`
- `0x180030b48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030535`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003066b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800303ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030535`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003066b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003020c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800302b0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003020c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800302b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800305c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800305c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030589`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800304e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003057f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800304e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003057f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305de`

## string_xrefs

- `0x1800303f6`: `\WinStore.DesktopExtension\StoreDesktopExtension.exe`
- `0x180030451`: `StoreDesktopExtension.exe -uninstallTencent`
- `0x180030517`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x1800305b0`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x1800304fa`: `Creating process for StoreDesktopExtension.exe -uninstallTencent failed with error code: %d`
- `0x180030593`: `Creating process for StoreDesktopExtension.exe -uninstallTencent failed with error code: %d`
- `0x18003050a`: `UninstallTencentEmulator`
- `0x1800305a3`: `UninstallTencentEmulator`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall UninstallTencentEmulator(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v2; // edx
  struct winrt::impl::shared_hstring_header *v3; // rbx
  volatile signed __int32 *v4; // rdi
  unsigned int v5; // r14d
  const void *v6; // r15
  struct winrt::impl::shared_hstring_header *v7; // rax
  __int64 v8; // rdx
  size_t v9; // r8
  void *v10; // rcx
  int v11; // eax
  HANDLE ProcessHeap; // rax
  int v13; // eax
  HANDLE v14; // rax
  unsigned int v15; // edx
  __int64 v16; // rcx
  const WCHAR *v17; // r14
  unsigned int v18; // eax
  const WCHAR *v19; // r15
  __int64 v20; // rdi
  struct winrt::impl::shared_hstring_header *v21; // rbx
  rsize_t v22; // rdi
  void *v23; // rdi
  int v24; // eax
  HANDLE v25; // rax
  char IsEnabled; // al
  WCHAR *v27; // rdx
  int v28; // esi
  HANDLE v29; // rax
  LPVOID lpEnvironment; // [rsp+30h] [rbp-D0h]
  LPVOID lpEnvironmenta; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v36; // [rsp+70h] [rbp-90h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v40; // [rsp+110h] [rbp+10h]

  v36 = &qword_18007F958;
  _InterlockedIncrement64(&qword_18007F958);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(
      a1,
      &v32,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18007F958, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18007F958, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      &v32,
      &lpMem);
  }
  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x24, v1);
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)((__int64 (*)(void))_o__errno)() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.WindowsStore_8wekyb3d8bbwe";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.WindowsStore_8wekyb3d8bbwe";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"sStore_8wekyb3d8bbwe";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"wekyb3d8bbwe";
    *(_QWORD *)((char *)v3 + 92) = *(_QWORD *)L"bbwe";
  }
  v36 = (__int64 *)v3;
  if ( !v3 )
    goto LABEL_8;
  if ( (*(_BYTE *)v3 & 1) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v3 + 6);
    v4 = (volatile signed __int32 *)v3;
    goto LABEL_18;
  }
  v5 = *((_DWORD *)v3 + 1);
  if ( !v5 )
  {
LABEL_8:
    v4 = 0;
    goto LABEL_18;
  }
  v6 = (const void *)*((_QWORD *)v3 + 2);
  v7 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v5, v2);
  v4 = (volatile signed __int32 *)v7;
  v9 = 2LL * v5;
  if ( v9 )
  {
    v10 = (char *)v7 + 28;
    if ( v7 != (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      if ( v6 )
      {
        memcpy_0(v10, v6, v9);
        goto LABEL_18;
      }
      memset_0(v10, 0, v9);
    }
    *(_DWORD *)_o__errno(v10, v8, v9) = 22;
    invalid_parameter_noinfo();
  }
LABEL_18:
  lpMem = (LPVOID)v4;
  lpCommandLine[0] = (LPWSTR)v4;
  winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackages(
    &v32,
    &v35,
    lpCommandLine);
  if ( v4 )
  {
    v11 = _InterlockedDecrement(v4 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
  }
  if ( v3 )
  {
    v13 = _InterlockedDecrement((volatile signed __int32 *)v3 + 6);
    if ( v13 )
    {
      if ( v13 < 0 )
        abort();
    }
    else
    {
      v14 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v14, 0, v3);
    }
  }
  if ( v32 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v32);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(
    &v35,
    &v34);
  if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::HasCurrent(&v34) )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(
      &v34,
      &v32);
    v16 = *(_QWORD *)winrt::impl::consume_Windows_ApplicationModel_IPackage8<winrt::Windows::ApplicationModel::Package>::InstalledPath(
                       &v32,
                       &lpMem);
    v17 = &ApplicationName;
    if ( v16 )
    {
      v18 = *(_DWORD *)(v16 + 4);
      v19 = *(const WCHAR **)(v16 + 16);
      v20 = v18;
    }
    else
    {
      v19 = &ApplicationName;
      v18 = 0;
      v20 = 0;
    }
    if ( v18 == -52 )
    {
      v21 = 0;
    }
    else
    {
      v21 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(v18 + 52), v15);
      v22 = 2 * v20;
      memcpy_s(*((void *const *)v21 + 2), v22, v19, v22);
      memcpy_s(
        (void *const)(v22 + *((_QWORD *)v21 + 2)),
        0x68u,
        L"\\WinStore.DesktopExtension\\StoreDesktopExtension.exe",
        0x68u);
    }
    v36 = (__int64 *)v21;
    v23 = lpMem;
    if ( lpMem )
    {
      v24 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v24 )
      {
        if ( v24 < 0 )
          abort();
      }
      else
      {
        v25 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v25, 0, v23);
      }
      lpMem = 0;
    }
    *(_OWORD *)lpCommandLine = 0;
    v40 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      lpCommandLine,
      L"StoreDesktopExtension.exe -uninstallTencent",
      43);
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloseHandleUninstallTencent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloseHandleUninstallTencent>::GetImpl'::`2'::impl);
    v27 = (WCHAR *)lpCommandLine;
    if ( IsEnabled )
    {
      if ( *((_QWORD *)&v40 + 1) > 7u )
        v27 = lpCommandLine[0];
      if ( v21 )
        v17 = (const WCHAR *)*((_QWORD *)v21 + 2);
      if ( !CreateProcessW(v17, v27, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        LODWORD(lpEnvironment) = GetLastError();
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          0x1EFu,
          "UninstallTencentEmulator",
          -1,
          L"Creating process for StoreDesktopExtension.exe -uninstallTencent failed with error code: %d",
          lpEnvironment);
LABEL_57:
        std::wstring::_Tidy_deallocate(lpCommandLine);
        if ( v21 )
        {
          v28 = _InterlockedDecrement((volatile signed __int32 *)v21 + 6);
          if ( v28 )
          {
            if ( v28 < 0 )
              abort();
          }
          else
          {
            v29 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v29, 0, v21);
          }
        }
        if ( v32 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v32);
        goto LABEL_62;
      }
    }
    else
    {
      if ( *((_QWORD *)&v40 + 1) > 7u )
        v27 = lpCommandLine[0];
      if ( v21 )
        v17 = (const WCHAR *)*((_QWORD *)v21 + 2);
      if ( !CreateProcessW(v17, v27, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        LODWORD(lpEnvironmenta) = GetLastError();
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          0x1F6u,
          "UninstallTencentEmulator",
          -1,
          L"Creating process for StoreDesktopExtension.exe -uninstallTencent failed with error code: %d",
          lpEnvironmenta);
      }
    }
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    goto LABEL_57;
  }
LABEL_62:
  if ( v34 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v34);
  if ( v35 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v35);
}

```

## disassembly

```asm
0x180030164  push    rbp
0x180030166  push    rbx
0x180030167  push    rsi
0x180030168  push    rdi
0x180030169  push    r12
0x18003016b  push    r13
0x18003016d  push    r14
0x18003016f  push    r15
0x180030171  lea     rbp, [rsp-38h]
0x180030176  sub     rsp, 138h
0x18003017d  mov     rax, cs:__security_cookie
0x180030184  xor     rax, rsp
0x180030187  mov     [rbp+70h+var_50], rax
0x18003018b  xor     r12d, r12d
0x18003018e  lea     rax, qword_18007F958
0x180030195  mov     [rsp+170h+var_100], rax
0x18003019a  lock inc cs:qword_18007F958
0x1800301a2  cmp     cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, r12; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x1800301a9  jz      short loc_1800301CB
0x1800301ab  lea     r8, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x1800301b2  lea     rdx, [rsp+170h+var_120]
0x1800301b7  call    ??R_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800301bc  nop
0x1800301bd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800301c1  lock add cs:qword_18007F958, rsi
0x1800301c9  jmp     short loc_1800301F3
0x1800301cb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800301cf  lock add cs:qword_18007F958, rsi
0x1800301d7  lea     rax, ?_lambda_invoker_cdecl_@_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800301de  mov     [rsp+170h+lpMem], rax
0x1800301e3  lea     r8, [rsp+170h+lpMem]
0x1800301e8  lea     rdx, [rsp+170h+var_120]
0x1800301ed  call    ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800301f2  nop
0x1800301f3  mov     ecx, 24h ; '$'; this
0x1800301f8  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800301fd  mov     rbx, rax
0x180030200  mov     r13d, 16h
0x180030206  add     rax, 1Ch
0x18003020a  jnz     short loc_18003021C
0x18003020c  call    cs:__imp__o__errno
0x180030212  mov     [rax], r13d
0x180030215  call    _invalid_parameter_noinfo
0x18003021a  jmp     short loc_180030254
0x18003021c  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_3; "Microsoft.WindowsStore_8wekyb3d8bbwe"
0x180030223  movups  xmmword ptr [rax], xmm0
0x180030226  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_3+10h; "t.WindowsStore_8wekyb3d8bbwe"
0x18003022d  movups  xmmword ptr [rax+10h], xmm1
0x180030231  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_3+20h; "sStore_8wekyb3d8bbwe"
0x180030238  movups  xmmword ptr [rax+20h], xmm0
0x18003023c  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_3+30h; "wekyb3d8bbwe"
0x180030243  movups  xmmword ptr [rax+30h], xmm1
0x180030247  movsd   xmm0, qword ptr cs:aMicrosoftWindo_3+40h; "bbwe"
0x18003024f  movsd   qword ptr [rax+40h], xmm0
0x180030254  mov     [rsp+170h+var_100], rbx
0x180030259  test    rbx, rbx
0x18003025c  jnz     short loc_180030263
0x18003025e  mov     rdi, r12
0x180030261  jmp     short loc_1800302BE
0x180030263  test    byte ptr [rbx], 1
0x180030266  jnz     short loc_180030271
0x180030268  lock inc dword ptr [rbx+18h]
0x18003026c  mov     rdi, rbx
0x18003026f  jmp     short loc_1800302BE
0x180030271  mov     r14d, [rbx+4]
0x180030275  test    r14d, r14d
0x180030278  jz      short loc_18003025E
0x18003027a  mov     r15, [rbx+10h]
0x18003027e  mov     ecx, r14d; this
0x180030281  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180030286  mov     rdi, rax
0x180030289  mov     r8d, r14d
0x18003028c  add     r8, r8; Size
0x18003028f  jz      short loc_1800302BE
0x180030291  lea     rcx, [rax+1Ch]; void *
0x180030295  test    rcx, rcx
0x180030298  jz      short loc_1800302B0
0x18003029a  test    r15, r15
0x18003029d  jz      short loc_1800302A9
0x18003029f  mov     rdx, r15; Src
0x1800302a2  call    memcpy_0
0x1800302a7  jmp     short loc_1800302BE
0x1800302a9  xor     edx, edx; Val
0x1800302ab  call    memset_0
0x1800302b0  call    cs:__imp__o__errno
0x1800302b6  mov     [rax], r13d
0x1800302b9  call    _invalid_parameter_noinfo
0x1800302be  mov     [rsp+170h+lpMem], rdi
0x1800302c3  mov     [rbp+70h+lpCommandLine], rdi
0x1800302c7  lea     r8, [rbp+70h+lpCommandLine]
0x1800302cb  lea     rdx, [rsp+170h+var_108]
0x1800302d0  lea     rcx, [rsp+170h+var_120]
0x1800302d5  call    ?FindPackages@?$consume_Windows_Management_Deployment_IPackageManager@UIPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackages(winrt::param::hstring const &)
0x1800302da  nop
0x1800302db  test    rdi, rdi
0x1800302de  jz      short loc_180030304
0x1800302e0  mov     eax, esi
0x1800302e2  lock xadd [rdi+18h], eax
0x1800302e7  sub     eax, 1
0x1800302ea  jnz     loc_18003039A
0x1800302f0  nop
0x1800302f1  call    WINRT_IMPL_GetProcessHeap
0x1800302f6  mov     rcx, rax; hHeap
0x1800302f9  mov     r8, rdi; lpMem
0x1800302fc  xor     edx, edx; dwFlags
0x1800302fe  call    WINRT_IMPL_HeapFree
0x180030303  nop
0x180030304  test    rbx, rbx
0x180030307  jz      short loc_18003032D
0x180030309  mov     eax, esi
0x18003030b  lock xadd [rbx+18h], eax
0x180030310  sub     eax, 1
0x180030313  jnz     loc_1800303A9
0x180030319  nop
0x18003031a  call    WINRT_IMPL_GetProcessHeap
0x18003031f  mov     rcx, rax; hHeap
0x180030322  mov     r8, rbx; lpMem
0x180030325  xor     edx, edx; dwFlags
0x180030327  call    WINRT_IMPL_HeapFree
0x18003032c  nop
0x18003032d  cmp     [rsp+170h+var_120], r12
0x180030332  jz      short loc_18003033E
0x180030334  lea     rcx, [rsp+170h+var_120]
0x180030339  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18003033e  lea     rdx, [rsp+170h+var_110]
0x180030343  lea     rcx, [rsp+170h+var_108]
0x180030348  call    ?First@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::First(void)
0x18003034d  nop
0x18003034e  lea     rcx, [rsp+170h+var_110]
0x180030353  call    ?HasCurrent@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::HasCurrent(void)
0x180030358  test    al, al
0x18003035a  jz      loc_180030624
0x180030360  lea     rdx, [rsp+170h+var_120]
0x180030365  lea     rcx, [rsp+170h+var_110]
0x18003036a  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::Current(void)
0x18003036f  nop
0x180030370  lea     rdx, [rsp+170h+lpMem]
0x180030375  lea     rcx, [rsp+170h+var_120]
0x18003037a  call    ?InstalledPath@?$consume_Windows_ApplicationModel_IPackage8@UPackage@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackage8<winrt::Windows::ApplicationModel::Package>::InstalledPath(void)
0x18003037f  nop
0x180030380  mov     rcx, [rax]
0x180030383  lea     r14, ApplicationName
0x18003038a  test    rcx, rcx
0x18003038d  jz      short loc_1800303B4
0x18003038f  mov     eax, [rcx+4]
0x180030392  mov     r15, [rcx+10h]
0x180030396  mov     edi, eax
0x180030398  jmp     short loc_1800303BD
0x18003039a  test    eax, eax
0x18003039c  jns     loc_180030304
0x1800303a2  call    cs:__imp_abort
0x1800303a9  test    eax, eax
0x1800303ab  jns     short loc_18003032D
0x1800303ad  call    cs:__imp_abort
0x1800303b4  mov     r15, r14
0x1800303b7  mov     rax, r12
0x1800303ba  mov     rdi, r12
0x1800303bd  lea     ecx, [rax+34h]; this
0x1800303c0  mov     r13d, 68h ; 'h'
0x1800303c6  test    ecx, ecx
0x1800303c8  jnz     short loc_1800303CF
0x1800303ca  mov     rbx, r12
0x1800303cd  jmp     short loc_180030405
0x1800303cf  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800303d4  mov     rbx, rax
0x1800303d7  add     rdi, rdi
0x1800303da  mov     r9, rdi; SourceSize
0x1800303dd  mov     r8, r15; Source
0x1800303e0  mov     rdx, rdi; DestinationSize
0x1800303e3  mov     rcx, [rax+10h]; Destination
0x1800303e7  call    memcpy_s
0x1800303ec  mov     rcx, [rbx+10h]
0x1800303f0  add     rcx, rdi; Destination
0x1800303f3  mov     r9, r13; SourceSize
0x1800303f6  lea     r8, aWinstoreDeskto; "\\WinStore.DesktopExtension\\StoreDeskt"...
0x1800303fd  mov     rdx, r13; DestinationSize
0x180030400  call    memcpy_s
0x180030405  mov     [rsp+170h+var_100], rbx
0x18003040a  mov     rdi, [rsp+170h+lpMem]
0x18003040f  test    rdi, rdi
0x180030412  jz      short loc_18003043C
0x180030414  mov     eax, esi
0x180030416  lock xadd [rdi+18h], eax
0x18003041b  sub     eax, 1
0x18003041e  jnz     loc_18003052D
0x180030424  nop
0x180030425  call    WINRT_IMPL_GetProcessHeap
0x18003042a  mov     rcx, rax; hHeap
0x18003042d  mov     r8, rdi; lpMem
0x180030430  xor     edx, edx; dwFlags
0x180030432  call    WINRT_IMPL_HeapFree
0x180030437  mov     [rsp+170h+lpMem], r12
0x18003043c  xorps   xmm0, xmm0
0x18003043f  movups  xmmword ptr [rbp+70h+lpCommandLine], xmm0
0x180030443  xorps   xmm1, xmm1
0x180030446  movdqu  [rbp+70h+var_60], xmm1
0x18003044b  mov     r8d, 2Bh ; '+'
0x180030451  lea     rdx, aStoredesktopex; "StoreDesktopExtension.exe -uninstallTen"...
0x180030458  lea     rcx, [rbp+70h+lpCommandLine]
0x18003045c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180030461  nop
0x180030462  mov     qword ptr [rbp+70h+StartupInfo.cb], 68h ; 'h'
0x18003046a  xor     edx, edx; Val
0x18003046c  lea     r8d, [rdx+60h]; Size
0x180030470  lea     rcx, [rbp+70h+StartupInfo.lpReserved]; void *
0x180030474  call    memset_0
0x180030479  xorps   xmm0, xmm0
0x18003047c  xor     eax, eax
0x18003047e  movups  xmmword ptr [rsp+170h+ProcessInformation.hProcess], xmm0
0x180030483  mov     qword ptr [rbp+70h+ProcessInformation.dwProcessId], rax
0x180030487  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloseHandleUninstallTencent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloseHandleUninstallTencent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloseHandleUninstallTencent> `wil::Feature<__WilFeatureTraits_Feature_CloseHandleUninstallTencent>::GetImpl(void)'::`2'::impl
0x18003048e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloseHandleUninstallTencent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloseHandleUninstallTencent>::__private_IsEnabled(void)
0x180030493  lea     rdx, [rbp+70h+lpCommandLine]
0x180030497  test    al, al
0x180030499  jz      loc_18003053C
0x18003049f  cmp     qword ptr [rbp+70h+var_60+8], 7
0x1800304a4  cmova   rdx, [rbp+70h+lpCommandLine]; lpCommandLine
0x1800304a9  test    rbx, rbx
0x1800304ac  jz      short loc_1800304B2
0x1800304ae  mov     r14, [rbx+10h]
0x1800304b2  lea     rax, [rsp+170h+ProcessInformation]
0x1800304b7  mov     [rsp+170h+lpProcessInformation], rax; lpProcessInformation
0x1800304bc  lea     rax, [rbp+70h+StartupInfo]
0x1800304c0  mov     [rsp+170h+lpStartupInfo], rax; lpStartupInfo
0x1800304c5  mov     [rsp+170h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800304ca  mov     [rsp+170h+lpEnvironment], r12; lpEnvironment
0x1800304cf  mov     [rsp+170h+dwCreationFlags], r12d; dwCreationFlags
0x1800304d4  mov     [rsp+170h+bInheritHandles], r12d; bInheritHandles
0x1800304d9  xor     r9d, r9d; lpThreadAttributes
0x1800304dc  xor     r8d, r8d; lpProcessAttributes
0x1800304df  mov     rcx, r14; lpApplicationName
0x1800304e2  call    cs:__imp_CreateProcessW
0x1800304e8  test    eax, eax
0x1800304ea  jnz     loc_1800305C1
0x1800304f0  call    cs:__imp_GetLastError
0x1800304f6  mov     dword ptr [rsp+170h+lpEnvironment], eax
0x1800304fa  lea     rax, aCreatingProces; "Creating process for StoreDesktopExtens"...
0x180030501  mov     qword ptr [rsp+170h+dwCreationFlags], rax; unsigned __int16 *
0x180030506  mov     [rsp+170h+bInheritHandles], esi; int
0x18003050a  lea     r9, aUninstalltence; "UninstallTencentEmulator"
0x180030511  mov     r8d, 1EFh; unsigned int
0x180030517  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003051e  mov     ecx, 2; unsigned int
0x180030523  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x180030528  jmp     loc_1800305E5
0x18003052d  test    eax, eax
0x18003052f  jns     loc_180030437
0x180030535  call    cs:__imp_abort
0x18003053c  cmp     qword ptr [rbp+70h+var_60+8], 7
0x180030541  cmova   rdx, [rbp+70h+lpCommandLine]; lpCommandLine
0x180030546  test    rbx, rbx
0x180030549  jz      short loc_18003054F
0x18003054b  mov     r14, [rbx+10h]
0x18003054f  lea     rax, [rsp+170h+ProcessInformation]
0x180030554  mov     [rsp+170h+lpProcessInformation], rax; lpProcessInformation
0x180030559  lea     rax, [rbp+70h+StartupInfo]
0x18003055d  mov     [rsp+170h+lpStartupInfo], rax; lpStartupInfo
0x180030562  mov     [rsp+170h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180030567  mov     [rsp+170h+lpEnvironment], r12; lpEnvironment
0x18003056c  mov     [rsp+170h+dwCreationFlags], r12d; dwCreationFlags
0x180030571  mov     [rsp+170h+bInheritHandles], r12d; bInheritHandles
0x180030576  xor     r9d, r9d; lpThreadAttributes
0x180030579  xor     r8d, r8d; lpProcessAttributes
0x18003057c  mov     rcx, r14; lpApplicationName
0x18003057f  call    cs:__imp_CreateProcessW
0x180030585  test    eax, eax
0x180030587  jnz     short loc_1800305C1
0x180030589  call    cs:__imp_GetLastError
0x18003058f  mov     dword ptr [rsp+170h+lpEnvironment], eax
0x180030593  lea     rax, aCreatingProces; "Creating process for StoreDesktopExtens"...
0x18003059a  mov     qword ptr [rsp+170h+dwCreationFlags], rax; unsigned __int16 *
0x18003059f  mov     [rsp+170h+bInheritHandles], esi; int
0x1800305a3  lea     r9, aUninstalltence; "UninstallTencentEmulator"
0x1800305aa  mov     r8d, 1F6h; unsigned int
0x1800305b0  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800305b7  mov     ecx, 2; unsigned int
0x1800305bc  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800305c1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800305c4  mov     rcx, [rsp+170h+ProcessInformation.hProcess]; hHandle
0x1800305c9  call    cs:__imp_WaitForSingleObject
0x1800305cf  mov     rcx, [rsp+170h+ProcessInformation.hProcess]; hObject
0x1800305d4  call    cs:__imp_CloseHandle
0x1800305da  mov     rcx, [rbp+70h+ProcessInformation.hThread]; hObject
0x1800305de  call    cs:__imp_CloseHandle
0x1800305e4  nop
0x1800305e5  lea     rcx, [rbp+70h+lpCommandLine]
0x1800305e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800305ee  nop
0x1800305ef  test    rbx, rbx
0x1800305f2  jz      short loc_180030612
0x1800305f4  lock xadd [rbx+18h], esi
0x1800305f9  sub     esi, 1
0x1800305fc  jnz     short loc_180030667
0x1800305fe  nop
0x1800305ff  call    WINRT_IMPL_GetProcessHeap
0x180030604  mov     rcx, rax; hHeap
0x180030607  mov     r8, rbx; lpMem
0x18003060a  xor     edx, edx; dwFlags
0x18003060c  call    WINRT_IMPL_HeapFree
0x180030611  nop
  ... truncated ...
```
