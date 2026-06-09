# AppReadiness::Groups::RemovePackage::OnStarted(void)

- ea: `0x180028850`
- end: `0x180028c2e`
- name: `?OnStarted@RemovePackage@Groups@AppReadiness@@MEAAXXZ`
- size: `990`
- prototype: `void __fastcall(AppReadiness::Groups::RemovePackage *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a470`
- `0x180014a30`
- `0x180019260`
- `0x1800211dc`
- `0x180027a4c`
- `0x180028850`
- `0x18002a970`
- `0x180039604`
- `0x18003e210`
- `0x18003ecb4`
- `0x180062344`
- `0x180062a94`
- `0x180062c80`
- `0x180079010`

## string_xrefs

- `0x180028b4f`: `PackageRemovePause`
- `0x180028bb1`: `MakeAndInitialize<Tasks::Pause>(&pause, GetUser(), seconds)`
- `0x180028967`: `onecoreuap\shell\appreadiness\src\groups\removepackage.cpp`
- `0x180028a2a`: `onecoreuap\shell\appreadiness\src\groups\removepackage.cpp`
- `0x180028abe`: `onecoreuap\shell\appreadiness\src\groups\removepackage.cpp`
- `0x180028b9e`: `onecoreuap\shell\appreadiness\src\groups\removepackage.cpp`
- `0x180028a3d`: `MakeAndInitialize<Tasks::RemoveBackup>(&removeBackup, GetUser(), packageInfo)`
- `0x180028ad1`: `MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageInfo)`
- `0x180028973`: `AppReadiness::Groups::RemovePackage::OnStarted`
- `0x180028a36`: `AppReadiness::Groups::RemovePackage::OnStarted`
- `0x180028aca`: `AppReadiness::Groups::RemovePackage::OnStarted`
- `0x180028baa`: `AppReadiness::Groups::RemovePackage::OnStarted`
- `0x18002897a`: `MakeAndInitialize<Tasks::RemovePreviews>(&removePreviewTiles, GetUser(), packageInfo->GetPackageFamilyName())`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall AppReadiness::Groups::RemovePackage::OnStarted(AppReadiness::Groups::RemovePackage *this)
{
  char *v2; // r14
  __int64 v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 *v10; // rdi
  __int64 v11; // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+38h] [rbp-61h] BYREF
  __int64 *v16; // [rsp+40h] [rbp-59h] BYREF
  __int64 v17; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v18; // [rsp+50h] [rbp-49h]
  struct AppReadiness::User *v19; // [rsp+58h] [rbp-41h] BYREF
  std::_Ref_count_base *v20; // [rsp+60h] [rbp-39h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v22[7]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD *v23; // [rsp+C8h] [rbp+2Fh]

  v2 = (char *)this - 8;
  v3 = (*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *, struct AppReadiness::User **))(*(_QWORD *)this + 80LL))(
         this,
         &v19);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v3, &v17);
  if ( v20 )
    std::_Ref_count_base::_Decwref(v20);
  v4 = (*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this);
  v22[0] = off_18007ADB0;
  v22[1] = v2;
  v22[2] = &v17;
  v23 = v22;
  AppReadiness::User::ExecuteUnderContext(v4, (__int64)v22);
  if ( v23 )
  {
    v5 = v22;
    LOBYTE(v5) = v23 != v22;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v5);
  }
  if ( (*(_BYTE *)(v17 + 140) & 8) == 0 && !AppReadiness::System::IsSharedAppsEnabled() )
  {
    v14 = 0;
    v6 = v17;
    v15 = (*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::RemovePreviews,AppReadiness::ITask,AppReadiness::User *,std::wstring const &>(
           &v14,
           &v15,
           v6 + 40);
    if ( v7 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v7,
        "MakeAndInitialize<Tasks::RemovePreviews>(&removePreviewTiles, GetUser(), packageInfo->GetPackageFamilyName())",
        "AppReadiness::Groups::RemovePackage::OnStarted",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\removepackage.cpp",
        55);
      throw (Windows::HResultException *)pExceptionObject;
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 24LL))(v2, v14);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  }
  if ( *(_BYTE *)((*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this)
                + 218)
    && (*(_DWORD *)(v17 + 140) & 0x60) == 0 )
  {
    v14 = 0;
    v15 = (*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v8 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::RemoveBackup,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &>(
           &v14,
           &v15,
           (__int64)&v17);
    if ( v8 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v8,
        "MakeAndInitialize<Tasks::RemoveBackup>(&removeBackup, GetUser(), packageInfo)",
        "AppReadiness::Groups::RemovePackage::OnStarted",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\removepackage.cpp",
        66);
      throw (Windows::HResultException *)pExceptionObject;
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 24LL))(v2, v14);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  }
  v16 = 0;
  v15 = (*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v9 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &>(
         &v16,
         &v15,
         (__int64)&v17);
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v9,
      "MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageInfo)",
      "AppReadiness::Groups::RemovePackage::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\removepackage.cpp",
      72);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( (*(unsigned __int8 (__fastcall **)(AppReadiness::Groups::RemovePackage *, __int64))(*(_QWORD *)this + 136LL))(
         this,
         0x200000) )
  {
    v10 = v16;
    v11 = *v16;
    v12 = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 144))(v16);
    (*(void (__fastcall **)(__int64 *, _QWORD))(v11 + 128))(v10, v12 | 0x200000u);
  }
  (*(void (__fastcall **)(char *, __int64 *))(*(_QWORD *)v2 + 24LL))(v2, v16);
  LODWORD(v14) = AppReadiness::GetRegistryIntWithDefault(L"PackageRemovePause");
  if ( (_DWORD)v14 )
  {
    v15 = 0;
    v19 = (struct AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Groups::RemovePackage *))(*(_QWORD *)this + 112LL))(this);
    v13 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::Pause,AppReadiness::ITask,AppReadiness::User *,int &>(
            &v15,
            &v19,
            (int *)&v14);
    if ( v13 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v13,
        "MakeAndInitialize<Tasks::Pause>(&pause, GetUser(), seconds)",
        "AppReadiness::Groups::RemovePackage::OnStarted",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\removepackage.cpp",
        86);
      throw (Windows::HResultException *)pExceptionObject;
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 24LL))(v2, v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x180028850  mov     [rsp-8+arg_8], rbx
0x180028855  mov     [rsp-8+arg_10], rsi
0x18002885a  push    rbp
0x18002885b  push    rdi
0x18002885c  push    r14
0x18002885e  lea     rbp, [rsp-47h]
0x180028863  sub     rsp, 0E0h
0x18002886a  mov     rax, cs:__security_cookie
0x180028871  xor     rax, rsp
0x180028874  mov     [rbp+57h+var_20], rax
0x180028878  mov     rsi, rcx
0x18002887b  lea     r14, [rcx-8]
0x18002887f  mov     rax, [rcx]
0x180028882  lea     rdx, [rbp+57h+var_98]
0x180028886  mov     rax, [rax+50h]
0x18002888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002888f  lea     rdx, [rbp+57h+var_A8]
0x180028893  mov     rcx, rax
0x180028896  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x18002889b  nop
0x18002889c  mov     rcx, [rbp+57h+var_90]; this
0x1800288a0  test    rcx, rcx
0x1800288a3  jz      short loc_1800288AA
0x1800288a5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800288aa  mov     rax, [rsi]
0x1800288ad  mov     rcx, rsi
0x1800288b0  mov     rax, [rax+70h]
0x1800288b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288b9  lea     rcx, off_18007ADB0
0x1800288c0  mov     [rbp+57h+var_60], rcx
0x1800288c4  mov     [rbp+57h+var_58], r14
0x1800288c8  lea     rcx, [rbp+57h+var_A8]
0x1800288cc  mov     [rbp+57h+var_50], rcx
0x1800288d0  lea     rcx, [rbp+57h+var_60]
0x1800288d4  mov     [rbp+57h+var_28], rcx
0x1800288d8  lea     rdx, [rbp+57h+var_60]
0x1800288dc  mov     rcx, rax
0x1800288df  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x1800288e4  nop
0x1800288e5  mov     rcx, [rbp+57h+var_28]
0x1800288e9  test    rcx, rcx
0x1800288ec  jz      short loc_180028904
0x1800288ee  mov     rax, [rcx]
0x1800288f1  lea     rdx, [rbp+57h+var_60]
0x1800288f5  cmp     rcx, rdx
0x1800288f8  setnz   dl
0x1800288fb  mov     rax, [rax+20h]
0x1800288ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028904  mov     rax, [rbp+57h+var_A8]
0x180028908  test    byte ptr [rax+8Ch], 8
0x18002890f  jnz     loc_1800289BA
0x180028915  call    ?IsSharedAppsEnabled@System@AppReadiness@@SA_NXZ; AppReadiness::System::IsSharedAppsEnabled(void)
0x18002891a  test    al, al
0x18002891c  jnz     loc_1800289BA
0x180028922  mov     [rbp+57h+var_C0], 0
0x18002892a  mov     rbx, [rbp+57h+var_A8]
0x18002892e  mov     rax, [rsi]
0x180028931  mov     rcx, rsi
0x180028934  mov     rax, [rax+70h]
0x180028938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893d  mov     [rbp+57h+var_B8], rax
0x180028941  lea     rcx, [rbp+57h+var_C0]
0x180028945  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002894a  lea     r8, [rbx+28h]
0x18002894e  lea     rdx, [rbp+57h+var_B8]
0x180028952  lea     rcx, [rbp+57h+var_C0]
0x180028956  call    ??$MakeAndInitialize@VRemovePreviews@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::RemovePreviews,AppReadiness::ITask,AppReadiness::User *,std::wstring const &>(AppReadiness::ITask * *,AppReadiness::User * &&,std::wstring const &)
0x18002895b  test    eax, eax
0x18002895d  jns     short loc_18002899D
0x18002895f  mov     [rsp+0F0h+var_C8], 37h ; '7'; int
0x180028967  lea     rcx, aOnecoreuapShel_6; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18002896e  mov     [rsp+0F0h+var_D0], rcx; char *
0x180028973  lea     r9, aAppreadinessGr_2; "AppReadiness::Groups::RemovePackage::On"...
0x18002897a  lea     r8, aMakeandinitial_17; "MakeAndInitialize<Tasks::RemovePreviews"...
0x180028981  mov     edx, eax; int
0x180028983  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028987  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002898c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180028993  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028997  call    _CxxThrowException_0
0x18002899d  mov     rax, [r14]
0x1800289a0  mov     rdx, [rbp+57h+var_C0]
0x1800289a4  mov     rcx, r14
0x1800289a7  mov     rax, [rax+18h]
0x1800289ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289b0  nop
0x1800289b1  lea     rcx, [rbp+57h+var_C0]
0x1800289b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800289ba  mov     rax, [rsi]
0x1800289bd  mov     rcx, rsi
0x1800289c0  mov     rax, [rax+70h]
0x1800289c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289c9  cmp     byte ptr [rax+0DAh], 0
0x1800289d0  jz      loc_180028A7D
0x1800289d6  mov     rax, [rbp+57h+var_A8]
0x1800289da  mov     ecx, [rax+8Ch]
0x1800289e0  test    cl, 60h
0x1800289e3  jnz     loc_180028A7D
0x1800289e9  mov     [rbp+57h+var_C0], 0
0x1800289f1  mov     rax, [rsi]
0x1800289f4  mov     rcx, rsi
0x1800289f7  mov     rax, [rax+70h]
0x1800289fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a00  mov     [rbp+57h+var_B8], rax
0x180028a04  lea     rcx, [rbp+57h+var_C0]
0x180028a08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028a0d  lea     r8, [rbp+57h+var_A8]
0x180028a11  lea     rdx, [rbp+57h+var_B8]
0x180028a15  lea     rcx, [rbp+57h+var_C0]
0x180028a19  call    ??$MakeAndInitialize@VRemoveBackup@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::RemoveBackup,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &>(AppReadiness::ITask * *,AppReadiness::User * &&,std::shared_ptr<AppReadiness::PackageInfo> &)
0x180028a1e  test    eax, eax
0x180028a20  jns     short loc_180028A60
0x180028a22  mov     [rsp+0F0h+var_C8], 42h ; 'B'; int
0x180028a2a  lea     rcx, aOnecoreuapShel_6; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180028a31  mov     [rsp+0F0h+var_D0], rcx; char *
0x180028a36  lea     r9, aAppreadinessGr_2; "AppReadiness::Groups::RemovePackage::On"...
0x180028a3d  lea     r8, aMakeandinitial_5; "MakeAndInitialize<Tasks::RemoveBackup>("...
0x180028a44  mov     edx, eax; int
0x180028a46  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028a4a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180028a4f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180028a56  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028a5a  call    _CxxThrowException_0
0x180028a60  mov     rax, [r14]
0x180028a63  mov     rdx, [rbp+57h+var_C0]
0x180028a67  mov     rcx, r14
0x180028a6a  mov     rax, [rax+18h]
0x180028a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a73  nop
0x180028a74  lea     rcx, [rbp+57h+var_C0]
0x180028a78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028a7d  mov     [rbp+57h+var_B0], 0
0x180028a85  mov     rax, [rsi]
0x180028a88  mov     rcx, rsi
0x180028a8b  mov     rax, [rax+70h]
0x180028a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a94  mov     [rbp+57h+var_B8], rax
0x180028a98  lea     rcx, [rbp+57h+var_B0]
0x180028a9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028aa1  lea     r8, [rbp+57h+var_A8]
0x180028aa5  lea     rdx, [rbp+57h+var_B8]
0x180028aa9  lea     rcx, [rbp+57h+var_B0]
0x180028aad  call    ??$MakeAndInitialize@VUnregisterPackage@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &>(AppReadiness::ITask * *,AppReadiness::User * &&,std::shared_ptr<AppReadiness::PackageInfo> &)
0x180028ab2  test    eax, eax
0x180028ab4  jns     short loc_180028AF4
0x180028ab6  mov     [rsp+0F0h+var_C8], 48h ; 'H'; int
0x180028abe  lea     rcx, aOnecoreuapShel_6; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180028ac5  mov     [rsp+0F0h+var_D0], rcx; char *
0x180028aca  lea     r9, aAppreadinessGr_2; "AppReadiness::Groups::RemovePackage::On"...
0x180028ad1  lea     r8, aMakeandinitial_18; "MakeAndInitialize<Tasks::UnregisterPack"...
0x180028ad8  mov     edx, eax; int
0x180028ada  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028ade  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180028ae3  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180028aea  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028aee  call    _CxxThrowException_0
0x180028af4  mov     rax, [rsi]
0x180028af7  mov     edx, 200000h
0x180028afc  mov     rcx, rsi
0x180028aff  mov     rax, [rax+88h]
0x180028b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b0b  test    al, al
0x180028b0d  jz      short loc_180028B3A
0x180028b0f  mov     rdi, [rbp+57h+var_B0]
0x180028b13  mov     rbx, [rdi]
0x180028b16  mov     rcx, rdi
0x180028b19  mov     rax, [rbx+90h]
0x180028b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b25  bts     eax, 15h
0x180028b29  mov     edx, eax
0x180028b2b  mov     rcx, rdi
0x180028b2e  mov     rax, [rbx+80h]
0x180028b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b3a  mov     rax, [r14]
0x180028b3d  mov     rdx, [rbp+57h+var_B0]
0x180028b41  mov     rcx, r14
0x180028b44  mov     rax, [rax+18h]
0x180028b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b4d  xor     edx, edx
0x180028b4f  lea     rcx, aPackageremovep; "PackageRemovePause"
0x180028b56  call    AppReadiness__GetRegistryIntWithDefault
0x180028b5b  mov     dword ptr [rbp+57h+var_C0], eax
0x180028b5e  test    eax, eax
0x180028b60  jz      loc_180028BF2
0x180028b66  mov     [rbp+57h+var_B8], 0
0x180028b6e  mov     rax, [rsi]
0x180028b71  mov     rcx, rsi
0x180028b74  mov     rax, [rax+70h]
0x180028b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b7d  mov     [rbp+57h+var_98], rax
0x180028b81  lea     r8, [rbp+57h+var_C0]
0x180028b85  lea     rdx, [rbp+57h+var_98]
0x180028b89  lea     rcx, [rbp+57h+var_B8]
0x180028b8d  call    ??$MakeAndInitialize@VPause@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAH@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@012@$$QEAPEAVUser@AppReadiness@@AEAH@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::Pause,AppReadiness::ITask,AppReadiness::User *,int &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppReadiness::ITask>>,AppReadiness::User * &&,int &)
0x180028b92  test    eax, eax
0x180028b94  jns     short loc_180028BD4
0x180028b96  mov     [rsp+0F0h+var_C8], 56h ; 'V'; int
0x180028b9e  lea     rcx, aOnecoreuapShel_6; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180028ba5  mov     [rsp+0F0h+var_D0], rcx; char *
0x180028baa  lea     r9, aAppreadinessGr_2; "AppReadiness::Groups::RemovePackage::On"...
0x180028bb1  lea     r8, aMakeandinitial_7; "MakeAndInitialize<Tasks::Pause>(&pause,"...
0x180028bb8  mov     edx, eax; int
0x180028bba  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028bbe  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180028bc3  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180028bca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028bce  call    _CxxThrowException_0
0x180028bd4  mov     rax, [r14]
0x180028bd7  mov     rdx, [rbp+57h+var_B8]
0x180028bdb  mov     rcx, r14
0x180028bde  mov     rax, [rax+18h]
0x180028be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028be7  nop
0x180028be8  lea     rcx, [rbp+57h+var_B8]
0x180028bec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028bf1  nop
0x180028bf2  lea     rcx, [rbp+57h+var_B0]
0x180028bf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028bfb  nop
0x180028bfc  mov     rcx, [rbp+57h+var_A0]; this
0x180028c00  test    rcx, rcx
0x180028c03  jz      short loc_180028C0A
0x180028c05  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028c0a  mov     rcx, [rbp+57h+var_20]
0x180028c0e  xor     rcx, rsp; StackCookie
0x180028c11  call    __security_check_cookie
0x180028c16  lea     r11, [rsp+0F0h+var_10]
0x180028c1e  mov     rbx, [r11+28h]
0x180028c22  mov     rsi, [r11+30h]
0x180028c26  mov     rsp, r11
0x180028c29  pop     r14
0x180028c2b  pop     rdi
0x180028c2c  pop     rbp
0x180028c2d  retn
```
