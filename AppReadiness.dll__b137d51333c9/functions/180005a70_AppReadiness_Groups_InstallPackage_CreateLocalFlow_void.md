# AppReadiness::Groups::InstallPackage::CreateLocalFlow(void)

- ea: `0x180005a70`
- end: `0x180006174`
- name: `?CreateLocalFlow@InstallPackage@Groups@AppReadiness@@AEAAXXZ`
- size: `1796`
- prototype: `void __fastcall(AppReadiness::Groups::InstallPackage *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004470`

## callees

- `0x180002958`
- `0x180002dec`
- `0x1800041e0`
- `0x180005270`
- `0x180005a70`
- `0x180009f50`
- `0x18000a470`
- `0x180019260`
- `0x1800194d4`
- `0x18001aea0`
- `0x18001caa0`
- `0x180025bb8`
- `0x180027a4c`
- `0x18003648c`
- `0x18003943c`
- `0x180039528`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x1800628b0`
- `0x180079010`

## import_xrefs

- `AppXAllUserStore!TryGetEndOfLifePackageFullName` at `0x180005e05`
- `AppXAllUserStore!TryGetEndOfLifePackageFullName` at `0x180005e05`
- `AppXDeploymentClient!__imp_GetApplicability` at `0x180005d0b`
- `AppXDeploymentClient!__imp_GetApplicability` at `0x180005d0b`

## string_xrefs

- `0x180006084`: `onecoreuap\shell\appreadiness\src\groups\installpackage.cpp`
- `0x1800060c2`: `onecoreuap\shell\appreadiness\src\groups\installpackage.cpp`
- `0x180006100`: `onecoreuap\shell\appreadiness\src\groups\installpackage.cpp`
- `0x18000613e`: `onecoreuap\shell\appreadiness\src\groups\installpackage.cpp`
- `0x180006113`: `MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageFamilyName, removePackageFullName, true)`
- `0x180006151`: `MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageInfo, true)`
- `0x180006090`: `AppReadiness::Groups::InstallPackage::CreateLocalFlow`
- `0x1800060ce`: `AppReadiness::Groups::InstallPackage::CreateLocalFlow`
- `0x18000610c`: `AppReadiness::Groups::InstallPackage::CreateLocalFlow`
- `0x18000614a`: `AppReadiness::Groups::InstallPackage::CreateLocalFlow`
- `0x1800060d5`: `AppxAllUserStore::TryGetEndOfLifePackageFullName( GetUser()->GetUserSid().c_str(), packageFamilyName, removePackageFullName, ARRAYSIZE(removePackageFullName), &found)`
- `0x180006097`: `MakeAndInitialize<Tasks::RegisterPackage>(&registerTask, GetUser(), packageInfo)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::Groups::InstallPackage::CreateLocalFlow(AppReadiness::Groups::InstallPackage *this)
{
  char *v2; // rsi
  __int64 v3; // rax
  __int64 *v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // r9
  char v8; // di
  _QWORD *v9; // r15
  int v10; // eax
  __int64 v11; // rax
  _QWORD *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // r9
  AppReadiness::User *v17; // rax
  unsigned __int8 (__fastcall *v18)(_QWORD *, __int64); // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  char v23; // di
  __int64 *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // edx
  int v28; // r8d
  _QWORD *v29; // r9
  _QWORD *v30; // rbx
  __int64 v31; // rax
  _QWORD *v32; // rcx
  int EndOfLifePackageFullName; // eax
  __int64 *v34; // rdi
  __int64 v35; // rbx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 *v39; // rdi
  __int64 v40; // rbx
  int v41; // eax
  int v42; // eax
  __int64 *v43; // rdi
  __int64 v44; // rbx
  int v45; // eax
  char v46; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v47[7]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned int v48[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v50; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v51[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v53; // [rsp+78h] [rbp-88h]
  _QWORD *v54; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v56[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v57; // [rsp+B8h] [rbp-48h]
  int v58; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v59[252]; // [rsp+C4h] [rbp-3Ch] BYREF

  v2 = (char *)this + 8;
  v3 = (*(__int64 (__fastcall **)(char *, _BYTE *))(*((_QWORD *)this + 1) + 80LL))((char *)this + 8, v56);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v3, &v52);
  if ( v57 )
    std::_Ref_count_base::_Decwref(v57);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = (__int64 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
    v5 = (__int64)v4;
    if ( (unsigned __int64)v4[3] > 7 )
      v5 = *v4;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
    v7 = (_QWORD *)(v6 + 64);
    if ( *(_QWORD *)(v6 + 88) > 7u )
      v7 = (_QWORD *)*v7;
    WPP_SF_SqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_e30153cd1a1a3f1c22e2cc453454e070_Traceguids,
      (_DWORD)v7,
      (char)this,
      v5);
  }
  v8 = 0;
  v9 = (_QWORD *)v52;
  v10 = *(_DWORD *)(v52 + 140);
  if ( (v10 & 4) == 0
    && (v10 & 2) != 0
    && (!*(_DWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2) + 380)
     || *(_DWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2) + 380) == 1) )
  {
    v48[0] = 0;
    v11 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
    v12 = AppReadiness::Storage::PackageList::OpenUserMachineRoot(v51, v11, 1u);
    if ( SHRegGetDWORD((HKEY)v12[1], 0, L"LogonCount", v48) < 0 )
      v48[0] = 0;
    v51[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v51);
    if ( v48[0] <= 1 )
    {
      v8 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v13 = (__int64 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
        v14 = (__int64)v13;
        if ( (unsigned __int64)v13[3] > 7 )
          v14 = *v13;
        v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
        v16 = (_QWORD *)(v15 + 64);
        if ( *(_QWORD *)(v15 + 88) > 7u )
          v16 = (_QWORD *)*v16;
        WPP_SF_SqS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_e30153cd1a1a3f1c22e2cc453454e070_Traceguids,
          (_DWORD)v16,
          (char)this,
          v14);
      }
    }
  }
  v49 = 0;
  v17 = (AppReadiness::User *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
  if ( !AppReadiness::User::IsSpecialProfile(v17) && !v8 )
  {
    v18 = *(unsigned __int8 (__fastcall **)(_QWORD *, __int64))(*v9 + 16LL);
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
    if ( !v18(v9, v19) )
    {
      v20 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
      v21 = (_QWORD *)(v20 + 64);
      if ( *(_QWORD *)(v20 + 88) > 7u )
        v21 = (_QWORD *)*v21;
      v22 = v9 + 9;
      if ( v9[12] > 7u )
        v22 = (_QWORD *)*v22;
      if ( (int)GetApplicability(v22, v21, &v49) >= 0 )
      {
        v23 = v49;
        if ( (v49 & 0xFFFFFFFD) == 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v24 = (__int64 *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
            v25 = (__int64)v24;
            if ( (unsigned __int64)v24[3] > 7 )
              v25 = *v24;
            v26 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
            v29 = (_QWORD *)(v26 + 64);
            if ( *(_QWORD *)(v26 + 88) > 7u )
              v29 = (_QWORD *)*v29;
            WPP_SF_SqSL(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, (_DWORD)v29, (char)this, v25, v23);
          }
          goto LABEL_60;
        }
      }
    }
  }
  v58 = 0;
  memset_0(v59, 0, sizeof(v59));
  v30 = v9 + 5;
  if ( v9[8] > 7u )
    v30 = (_QWORD *)*v30;
  v54 = v30;
  v47[0] = 0;
  v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
  v32 = (_QWORD *)(v31 + 64);
  if ( *(_QWORD *)(v31 + 88) > 7u )
    v32 = (_QWORD *)*v32;
  EndOfLifePackageFullName = TryGetEndOfLifePackageFullName(v32, v30, &v58, 128, v47);
  if ( EndOfLifePackageFullName < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      EndOfLifePackageFullName,
      "AppxAllUserStore::TryGetEndOfLifePackageFullName( GetUser()->GetUserSid().c_str(), packageFamilyName, removePackag"
      "eFullName, ARRAYSIZE(removePackageFullName), &found)",
      "AppReadiness::Groups::InstallPackage::CreateLocalFlow",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\installpackage.cpp",
      113);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( v47[0] )
  {
    *(_QWORD *)v48 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 136LL))(v2, 0x200000) )
    {
      v34 = *(__int64 **)v48;
      v35 = **(_QWORD **)v48;
      v36 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v48 + 144LL))(*(_QWORD *)v48);
      (*(void (__fastcall **)(__int64 *, _QWORD))(v35 + 128))(v34, v36 | 0x200000u);
    }
    v46 = 1;
    v51[0] = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v48);
    v37 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,unsigned short const * &,unsigned short (&)[128],bool>(
            v48,
            v51,
            &v54,
            &v58,
            &v46);
    if ( v37 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v37,
        "MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageFamilyName, removePackageFullName, true)",
        "AppReadiness::Groups::InstallPackage::CreateLocalFlow",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\installpackage.cpp",
        124);
      throw (Windows::HResultException *)pExceptionObject;
    }
    (*(void (__fastcall **)(AppReadiness::Groups::InstallPackage *, _QWORD))(*(_QWORD *)this + 24LL))(
      this,
      *(_QWORD *)v48);
    std::wstring::assign((char *)this + 344, &v58);
LABEL_55:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v48);
    goto LABEL_56;
  }
  if ( AppReadiness::Groups::InstallPackage::NeedRepair(this) )
  {
    *(_QWORD *)v48 = 0;
    v46 = 1;
    v51[0] = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v48);
    v38 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &,bool>(
            v48,
            v51,
            &v52,
            &v46);
    if ( v38 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v38,
        "MakeAndInitialize<Tasks::UnregisterPackage>(&unregisterPackage, GetUser(), packageInfo, true)",
        "AppReadiness::Groups::InstallPackage::CreateLocalFlow",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\installpackage.cpp",
        132);
      throw (Windows::HResultException *)pExceptionObject;
    }
    if ( (*(unsigned __int8 (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 136LL))(v2, 0x200000) )
    {
      v39 = *(__int64 **)v48;
      v40 = **(_QWORD **)v48;
      v41 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v48 + 144LL))(*(_QWORD *)v48);
      (*(void (__fastcall **)(__int64 *, _QWORD))(v40 + 128))(v39, v41 | 0x200000u);
    }
    (*(void (__fastcall **)(AppReadiness::Groups::InstallPackage *, _QWORD))(*(_QWORD *)this + 24LL))(
      this,
      *(_QWORD *)v48);
    goto LABEL_55;
  }
LABEL_56:
  v50 = 0;
  v51[0] = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  v42 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::RegisterPackage,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &>(
          &v50,
          v51,
          &v52);
  if ( v42 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v42,
      "MakeAndInitialize<Tasks::RegisterPackage>(&registerTask, GetUser(), packageInfo)",
      "AppReadiness::Groups::InstallPackage::CreateLocalFlow",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\installpackage.cpp",
      145);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( (*(unsigned __int8 (__fastcall **)(char *, __int64))(*(_QWORD *)v2 + 136LL))(v2, 0x200000) )
  {
    v43 = v50;
    v44 = *v50;
    v45 = (*(__int64 (__fastcall **)(__int64 *))(*v50 + 144))(v50);
    (*(void (__fastcall **)(__int64 *, _QWORD))(v44 + 128))(v43, v45 | 0x200000u);
  }
  (*(void (__fastcall **)(AppReadiness::Groups::InstallPackage *, __int64 *))(*(_QWORD *)this + 24LL))(this, v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
LABEL_60:
  if ( v53 )
    std::_Ref_count_base::_Decref(v53);
}

```

## disassembly

```asm
0x180005a70  push    rbp
0x180005a72  push    rbx
0x180005a73  push    rsi
0x180005a74  push    rdi
0x180005a75  push    r14
0x180005a77  push    r15
0x180005a79  lea     rbp, [rsp-0D8h]
0x180005a81  sub     rsp, 1D8h
0x180005a88  mov     rax, cs:__security_cookie
0x180005a8f  xor     rax, rsp
0x180005a92  mov     [rbp+100h+var_40], rax
0x180005a99  mov     r14, rcx
0x180005a9c  lea     rsi, [rcx+8]
0x180005aa0  mov     rax, [rsi]
0x180005aa3  lea     rdx, [rbp+100h+var_150]
0x180005aa7  mov     rcx, rsi
0x180005aaa  mov     rax, [rax+50h]
0x180005aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab3  lea     rdx, [rsp+200h+var_190]
0x180005ab8  mov     rcx, rax
0x180005abb  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x180005ac0  nop
0x180005ac1  mov     rcx, [rbp+100h+var_148]; this
0x180005ac5  test    rcx, rcx
0x180005ac8  jz      short loc_180005ACF
0x180005aca  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180005acf  lea     rbx, WPP_GLOBAL_Control
0x180005ad6  mov     rax, cs:WPP_GLOBAL_Control
0x180005add  cmp     rax, rbx
0x180005ae0  jz      short loc_180005B4E
0x180005ae2  test    byte ptr [rax+1Ch], 4
0x180005ae6  jz      short loc_180005B4E
0x180005ae8  mov     rax, [rsi]
0x180005aeb  mov     rcx, rsi
0x180005aee  mov     rax, [rax+18h]
0x180005af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af7  mov     rbx, rax
0x180005afa  cmp     qword ptr [rax+18h], 7
0x180005aff  jbe     short loc_180005B04
0x180005b01  mov     rbx, [rax]
0x180005b04  mov     rax, [rsi]
0x180005b07  mov     rcx, rsi
0x180005b0a  mov     rax, [rax+70h]
0x180005b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b13  lea     r9, [rax+40h]
0x180005b17  cmp     qword ptr [r9+18h], 7
0x180005b1c  jbe     short loc_180005B21
0x180005b1e  mov     r9, [r9]
0x180005b21  mov     edx, 0Ah
0x180005b26  mov     qword ptr [rsp+200h+var_1D8], rbx
0x180005b2b  mov     [rsp+200h+var_1E0], r14
0x180005b30  lea     r8, WPP_e30153cd1a1a3f1c22e2cc453454e070_Traceguids
0x180005b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b3e  mov     rcx, [rcx+10h]
0x180005b42  call    WPP_SF_SqS
0x180005b47  lea     rbx, WPP_GLOBAL_Control
0x180005b4e  xor     dil, dil
0x180005b51  mov     r15, [rsp+200h+var_190]
0x180005b56  mov     eax, [r15+8Ch]
0x180005b5d  test    al, 4
0x180005b5f  jnz     loc_180005C7F
0x180005b65  test    al, 2
0x180005b67  jz      loc_180005C7F
0x180005b6d  mov     rax, [rsi]
0x180005b70  mov     rcx, rsi
0x180005b73  mov     rax, [rax+70h]
0x180005b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b7c  cmp     dword ptr [rax+17Ch], 0
0x180005b83  jz      short loc_180005BA1
0x180005b85  mov     rax, [rsi]
0x180005b88  mov     rcx, rsi
0x180005b8b  mov     rax, [rax+70h]
0x180005b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b94  cmp     dword ptr [rax+17Ch], 1
0x180005b9b  jnz     loc_180005C7F
0x180005ba1  mov     [rsp+200h+var_1B8], 0
0x180005ba9  mov     rax, [rsi]
0x180005bac  mov     rcx, rsi
0x180005baf  mov     rax, [rax+70h]
0x180005bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb8  mov     rdx, rax
0x180005bbb  mov     r8d, 1
0x180005bc1  lea     rcx, [rsp+200h+var_1A0]
0x180005bc6  call    ?OpenUserMachineRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserMachineRoot(AppReadiness::User const *,ulong)
0x180005bcb  lea     r9, [rsp+200h+var_1B8]; unsigned int *
0x180005bd0  lea     r8, aLogoncount; "LogonCount"
0x180005bd7  xor     edx, edx; unsigned __int16 *
0x180005bd9  mov     rcx, [rax+8]; HKEY
0x180005bdd  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180005be2  test    eax, eax
0x180005be4  jns     short loc_180005BEE
0x180005be6  mov     [rsp+200h+var_1B8], 0
0x180005bee  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180005bf5  mov     [rsp+200h+var_1A0], rax
0x180005bfa  lea     rcx, [rsp+200h+var_1A0]
0x180005bff  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180005c04  cmp     [rsp+200h+var_1B8], 1
0x180005c09  ja      short loc_180005C7F
0x180005c0b  mov     dil, 1
0x180005c0e  mov     rax, cs:WPP_GLOBAL_Control
0x180005c15  cmp     rax, rbx
0x180005c18  jz      short loc_180005C7F
0x180005c1a  test    byte ptr [rax+1Ch], 4
0x180005c1e  jz      short loc_180005C7F
0x180005c20  mov     rax, [rsi]
0x180005c23  mov     rcx, rsi
0x180005c26  mov     rax, [rax+18h]
0x180005c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c2f  mov     rbx, rax
0x180005c32  cmp     qword ptr [rax+18h], 7
0x180005c37  jbe     short loc_180005C3C
0x180005c39  mov     rbx, [rax]
0x180005c3c  mov     rax, [rsi]
0x180005c3f  mov     rcx, rsi
0x180005c42  mov     rax, [rax+70h]
0x180005c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4b  lea     r9, [rax+40h]
0x180005c4f  cmp     qword ptr [r9+18h], 7
0x180005c54  jbe     short loc_180005C59
0x180005c56  mov     r9, [r9]
0x180005c59  mov     edx, 0Bh
0x180005c5e  mov     qword ptr [rsp+200h+var_1D8], rbx
0x180005c63  mov     [rsp+200h+var_1E0], r14
0x180005c68  lea     r8, WPP_e30153cd1a1a3f1c22e2cc453454e070_Traceguids
0x180005c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c76  mov     rcx, [rcx+10h]
0x180005c7a  call    WPP_SF_SqS
0x180005c7f  mov     [rsp+200h+var_1B0], 0
0x180005c87  mov     rax, [rsi]
0x180005c8a  mov     rcx, rsi
0x180005c8d  mov     rax, [rax+70h]
0x180005c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c96  mov     rcx, rax; this
0x180005c99  call    ?IsSpecialProfile@User@AppReadiness@@QEAA_NXZ; AppReadiness::User::IsSpecialProfile(void)
0x180005c9e  test    al, al
0x180005ca0  jnz     loc_180005DA2
0x180005ca6  test    dil, dil
0x180005ca9  jnz     loc_180005DA2
0x180005caf  mov     rax, [r15]
0x180005cb2  mov     rbx, [rax+10h]
0x180005cb6  mov     rcx, [rsi]
0x180005cb9  mov     rax, [rcx+70h]
0x180005cbd  mov     rcx, rsi
0x180005cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc5  mov     rdx, rax
0x180005cc8  mov     rcx, r15
0x180005ccb  mov     rax, rbx
0x180005cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd3  test    al, al
0x180005cd5  jnz     loc_180005DA2
0x180005cdb  mov     rax, [rsi]
0x180005cde  mov     rcx, rsi
0x180005ce1  mov     rax, [rax+70h]
0x180005ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cea  lea     rdx, [rax+40h]
0x180005cee  cmp     qword ptr [rdx+18h], 7
0x180005cf3  jbe     short loc_180005CF8
0x180005cf5  mov     rdx, [rdx]
0x180005cf8  lea     rcx, [r15+48h]
0x180005cfc  cmp     qword ptr [rcx+18h], 7
0x180005d01  jbe     short loc_180005D06
0x180005d03  mov     rcx, [rcx]
0x180005d06  lea     r8, [rsp+200h+var_1B0]
0x180005d0b  call    cs:__imp_GetApplicability
0x180005d11  test    eax, eax
0x180005d13  js      loc_180005DA2
0x180005d19  mov     edi, [rsp+200h+var_1B0]
0x180005d1d  test    edi, 0FFFFFFFDh
0x180005d23  jnz     short loc_180005DA2
0x180005d25  mov     rax, cs:WPP_GLOBAL_Control
0x180005d2c  lea     rcx, WPP_GLOBAL_Control
0x180005d33  cmp     rax, rcx
0x180005d36  jz      loc_18000604E
0x180005d3c  test    byte ptr [rax+1Ch], 4
0x180005d40  jz      loc_18000604E
0x180005d46  mov     rax, [rsi]
0x180005d49  mov     rcx, rsi
0x180005d4c  mov     rax, [rax+18h]
0x180005d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d55  mov     rbx, rax
0x180005d58  cmp     qword ptr [rax+18h], 7
0x180005d5d  jbe     short loc_180005D62
0x180005d5f  mov     rbx, [rax]
0x180005d62  mov     rax, [rsi]
0x180005d65  mov     rcx, rsi
0x180005d68  mov     rax, [rax+70h]
0x180005d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d71  lea     r9, [rax+40h]
0x180005d75  cmp     qword ptr [r9+18h], 7
0x180005d7a  jbe     short loc_180005D7F
0x180005d7c  mov     r9, [r9]
0x180005d7f  mov     [rsp+200h+var_1D0], edi
0x180005d83  mov     qword ptr [rsp+200h+var_1D8], rbx
0x180005d88  mov     [rsp+200h+var_1E0], r14
0x180005d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d94  mov     rcx, [rcx+10h]
0x180005d98  call    WPP_SF_SqSL
0x180005d9d  jmp     loc_18000604E
0x180005da2  mov     [rbp+100h+var_140], 0
0x180005da9  xor     edx, edx; Val
0x180005dab  mov     r8d, 0FCh; Size
0x180005db1  lea     rcx, [rbp+100h+var_13C]; void *
0x180005db5  call    memset_0
0x180005dba  lea     rbx, [r15+28h]
0x180005dbe  cmp     qword ptr [rbx+18h], 7
0x180005dc3  jbe     short loc_180005DC8
0x180005dc5  mov     rbx, [rbx]
0x180005dc8  mov     [rbp+100h+var_180], rbx
0x180005dcc  mov     [rsp+200h+var_1BF], 0
0x180005dd1  mov     rax, [rsi]
0x180005dd4  mov     rcx, rsi
0x180005dd7  mov     rax, [rax+70h]
0x180005ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de0  lea     rcx, [rax+40h]
0x180005de4  cmp     qword ptr [rcx+18h], 7
0x180005de9  jbe     short loc_180005DEE
0x180005deb  mov     rcx, [rcx]
0x180005dee  lea     rax, [rsp+200h+var_1BF]
0x180005df3  mov     [rsp+200h+var_1E0], rax
0x180005df8  mov     r9d, 80h
0x180005dfe  lea     r8, [rbp+100h+var_140]
0x180005e02  mov     rdx, rbx
0x180005e05  call    cs:__imp_TryGetEndOfLifePackageFullName
0x180005e0b  test    eax, eax
0x180005e0d  js      loc_1800060BA
0x180005e13  mov     r15d, 200000h
0x180005e19  cmp     [rsp+200h+var_1BF], 0
0x180005e1e  jz      loc_180005EE7
0x180005e24  mov     qword ptr [rsp+200h+var_1B8], 0
0x180005e2d  mov     rax, [rsi]
0x180005e30  mov     edx, r15d
0x180005e33  mov     rcx, rsi
0x180005e36  mov     rax, [rax+88h]
0x180005e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e42  test    al, al
0x180005e44  jz      short loc_180005E71
0x180005e46  mov     rdi, qword ptr [rsp+200h+var_1B8]
0x180005e4b  mov     rbx, [rdi]
0x180005e4e  mov     rcx, rdi
0x180005e51  mov     rax, [rbx+90h]
0x180005e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5d  or      eax, r15d
0x180005e60  mov     edx, eax
0x180005e62  mov     rcx, rdi
0x180005e65  mov     rax, [rbx+80h]
0x180005e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e71  mov     [rsp+200h+var_1C0], 1
0x180005e76  mov     rax, [rsi]
0x180005e79  mov     rcx, rsi
0x180005e7c  mov     rax, [rax+70h]
0x180005e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e85  mov     [rsp+200h+var_1A0], rax
0x180005e8a  lea     rcx, [rsp+200h+var_1B8]
0x180005e8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005e94  lea     rax, [rsp+200h+var_1C0]
0x180005e99  mov     [rsp+200h+var_1E0], rax
0x180005e9e  lea     r9, [rbp+100h+var_140]
0x180005ea2  lea     r8, [rbp+100h+var_180]
0x180005ea6  lea     rdx, [rsp+200h+var_1A0]
0x180005eab  lea     rcx, [rsp+200h+var_1B8]
0x180005eb0  call    ??$MakeAndInitialize@VUnregisterPackage@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAPEBGAEAY0IA@G_N@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEAPEBGAEAY0IA@G$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,ushort const * &,ushort (&)[128],bool>(AppReadiness::ITask * *,AppReadiness::User * &&,ushort const * &,ushort (&)[128],bool &&)
0x180005eb5  test    eax, eax
0x180005eb7  js      loc_1800060F8
0x180005ebd  mov     rax, [r14]
0x180005ec0  mov     rdx, qword ptr [rsp+200h+var_1B8]
0x180005ec5  mov     rcx, r14
0x180005ec8  mov     rax, [rax+18h]
0x180005ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed1  lea     rcx, [r14+158h]
0x180005ed8  lea     rdx, [rbp+100h+var_140]
0x180005edc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180005ee1  nop
0x180005ee2  jmp     loc_180005F9D
0x180005ee7  mov     rcx, r14; this
0x180005eea  call    ?NeedRepair@InstallPackage@Groups@AppReadiness@@AEAA_NXZ; AppReadiness::Groups::InstallPackage::NeedRepair(void)
0x180005eef  test    al, al
0x180005ef1  jz      loc_180005FA7
0x180005ef7  mov     qword ptr [rsp+200h+var_1B8], 0
0x180005f00  mov     [rsp+200h+var_1C0], 1
0x180005f05  mov     rax, [rsi]
0x180005f08  mov     rcx, rsi
0x180005f0b  mov     rax, [rax+70h]
0x180005f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f14  mov     [rsp+200h+var_1A0], rax
0x180005f19  lea     rcx, [rsp+200h+var_1B8]
0x180005f1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005f23  lea     r9, [rsp+200h+var_1C0]
0x180005f28  lea     r8, [rsp+200h+var_190]
0x180005f2d  lea     rdx, [rsp+200h+var_1A0]
0x180005f32  lea     rcx, [rsp+200h+var_1B8]
0x180005f37  call    ??$MakeAndInitialize@VUnregisterPackage@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@_N@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEAV?$shared_ptr@VPackageInfo@AppReadiness@@@std@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::UnregisterPackage,AppReadiness::ITask,AppReadiness::User *,std::shared_ptr<AppReadiness::PackageInfo> &,bool>(AppReadiness::ITask * *,AppReadiness::User * &&,std::shared_ptr<AppReadiness::PackageInfo> &,bool &&)
0x180005f3c  test    eax, eax
0x180005f3e  js      loc_180006136
0x180005f44  mov     rax, [rsi]
0x180005f47  mov     edx, r15d
0x180005f4a  mov     rcx, rsi
0x180005f4d  mov     rax, [rax+88h]
0x180005f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f59  test    al, al
0x180005f5b  jz      short loc_180005F88
  ... truncated ...
```
