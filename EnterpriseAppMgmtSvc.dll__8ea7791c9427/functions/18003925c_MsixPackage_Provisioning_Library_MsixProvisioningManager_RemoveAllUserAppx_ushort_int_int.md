# MsixPackage::Provisioning::Library::MsixProvisioningManager::RemoveAllUserAppx(ushort *,int,int *)

- ea: `0x18003925c`
- end: `0x180039c62`
- name: `?RemoveAllUserAppx@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAGHPEAH@Z`
- size: `2566`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180039c68`
- `0x180039cf8`

## callees

- `0x18001bf0c`
- `0x180032058`
- `0x180032ad0`
- `0x1800390e0`
- `0x18003925c`
- `0x180039e9c`
- `0x18003aba8`
- `0x18003b3f8`
- `0x18003bf94`
- `0x180041548`
- `0x180042444`
- `0x180045810`
- `0x18004a334`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800393b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039433`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800394ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800395f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039716`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800397da`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003981f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800398e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039925`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800399d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a5e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039adc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039ba3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039bf5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800393b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039433`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800394ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800395f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039716`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800397da`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003981f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800398e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039925`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800399d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039a5e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039adc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039ba3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180039bf5`
- `AppXAllUserStore!IsPackageFamilyInUninstallBlocklistByPackageFullName` at `0x180039374`
- `AppXAllUserStore!IsPackageFamilyInUninstallBlocklistByPackageFullName` at `0x180039374`

## string_xrefs

- `0x180039397`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180039414`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800394ce`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003957a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800395d2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800397b5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800398bb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800399b4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180039b49`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180039b84`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180039400`: `Failed to uninstall becuase policy prevents the removal of this package`
- `0x180039388`: `Failed while searching uninstall blocklist`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::RemoveAllUserAppx(
        MsixPackage::Provisioning::Library::MsixProvisioningManager *this,
        char *a2,
        int a3,
        int *a4)
{
  int v4; // r14d
  _QWORD *v6; // r10
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // r8
  _QWORD *v10; // r9
  int v11; // r11d
  int v12; // ebx
  __int64 v13; // rdi
  __int64 v14; // rsi
  _QWORD *v15; // rcx
  int v16; // edi
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v17; // rcx
  int OptionalPackagesForMainPackage; // eax
  __int128 v19; // kr10_16
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v20; // rcx
  unsigned __int64 v21; // r15
  const char *i; // rsi
  char *v23; // rdx
  unsigned __int64 v24; // r8
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v25; // rcx
  char *v26; // rcx
  int v27; // r14d
  const char *v28; // rdx
  const char *v29; // rdx
  int v30; // eax
  const char *v31; // rdx
  int v32; // eax
  char *v34; // [rsp+28h] [rbp-460h]
  __int64 v35; // [rsp+30h] [rbp-458h]
  char v36; // [rsp+80h] [rbp-408h] BYREF
  _BYTE v37[7]; // [rsp+81h] [rbp-407h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v38; // [rsp+88h] [rbp-400h] BYREF
  int v39; // [rsp+90h] [rbp-3F8h]
  __int128 v40; // [rsp+98h] [rbp-3F0h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-3E0h]
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v42; // [rsp+B0h] [rbp-3D8h] BYREF
  const char *v43; // [rsp+B8h] [rbp-3D0h]
  int *v44; // [rsp+C0h] [rbp-3C8h]
  char *v45[2]; // [rsp+C8h] [rbp-3C0h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-3B0h]
  unsigned __int64 v47; // [rsp+E0h] [rbp-3A8h]
  void *Src[3]; // [rsp+E8h] [rbp-3A0h] BYREF
  unsigned __int64 v49; // [rsp+100h] [rbp-388h]
  struct _RTL_AVL_TABLE Table; // [rsp+110h] [rbp-378h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  v44 = a4;
  v4 = a3;
  v39 = a3;
  v6 = (_QWORD *)((char *)this + 168);
  if ( *((_QWORD *)this + 24) >= 8u )
    v6 = (_QWORD *)*v6;
  v7 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) >= 8u )
    v7 = (_QWORD *)*v7;
  v8 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 20) >= 8u )
    v8 = (_QWORD *)*v8;
  v9 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) >= 8u )
    v9 = (_QWORD *)*v9;
  v10 = (_QWORD *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) >= 8u )
    v10 = (_QWORD *)*v10;
  v11 = *((unsigned __int8 *)this + 8);
  v12 = *((_DWORD *)this + 8);
  v13 = *((_QWORD *)this + 3);
  v14 = *((_QWORD *)this + 2);
  v15 = (_QWORD *)((char *)this + 200);
  if ( v15[3] >= 8u )
    v15 = (_QWORD *)*v15;
  MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(
    (__int64)&Table,
    (__int64)v15,
    v14,
    v13,
    v12,
    v11,
    (__int64)v10,
    (__int64)v9,
    (__int64)v8,
    (__int64)v7,
    (__int64)v6);
  v38 = 0;
  v40 = 0;
  v41 = 0;
  v37[0] = 0;
  v36 = 0;
  v16 = IsPackageFamilyInUninstallBlocklistByPackageFullName(a2, &v36);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5B7,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed while searching uninstall blocklist",
      v34);
    if ( (_QWORD)v40 )
    {
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    if ( v38 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_109:
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)v16;
  }
  if ( v36 )
  {
    v16 = -2147009286;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)0x80073CFALL,
      (int)"Failed to uninstall becuase policy prevents the removal of this package",
      v34);
    if ( (_QWORD)v40 )
    {
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    if ( v38 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_109;
  }
  v17 = v38;
  v38 = 0;
  if ( v17 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v17 + 16LL))(v17);
  v16 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(
          a2,
          (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
          1,
          &v38);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed while initializing package adapter for package '%ws'",
      a2);
    if ( (_QWORD)v40 )
    {
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    if ( v38 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_109;
  }
  OptionalPackagesForMainPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(
                                     (char *)v38,
                                     0,
                                     (__int64)&Table,
                                     v37,
                                     (__int64)&v40);
  if ( OptionalPackagesForMainPackage >= 0 )
  {
    v19 = v40;
    if ( (_QWORD)v40 != *((_QWORD *)&v40 + 1) && v37[0] )
    {
      v20 = 0;
      v42 = 0;
      v21 = (__int64)(*((_QWORD *)&v40 + 1) - v40) >> 3;
      for ( i = 0; ; ++i )
      {
        v43 = i;
        if ( (unsigned __int64)i >= v21 )
          break;
        try
        {
          v47 = 7;
          v46 = 0;
          LOWORD(v45[0]) = 0;
          if ( (__int64)(*((_QWORD *)&v19 + 1) - v19) >> 3 <= (unsigned __int64)i )
            std::vector<wil::com_ptr_t<IAppxFile,wil::err_returncode_policy>>::_Xran();
          v23 = *(char **)(v19 + 8LL * (_QWORD)i);
          v49 = 7;
          Src[2] = 0;
          LOWORD(Src[0]) = 0;
          if ( *(_WORD *)v23 )
          {
            v24 = -1;
            do
              ++v24;
            while ( *(_WORD *)&v23[2 * v24] );
          }
          else
          {
            v24 = 0;
          }
          std::wstring::assign(Src, v23, v24);
          std::wstring::assign(v45, Src);
          if ( v49 >= 8 )
            operator delete(Src[0]);
        }
        catch ( ... )
        {
          v39 = wil::details::in1diag3::Return_CaughtExceptionMsg(
                  retaddr,
                  (void *)0x5E0,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
                  "Failed getting optionalPackagePath at index %Id",
                  v43);
          if ( v47 >= 8 )
            operator delete(v45[0]);
          v47 = 7;
          v46 = 0;
          LOWORD(v45[0]) = 0;
          if ( v42 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v42 + 16LL))(v42);
          if ( (_QWORD)v40 )
          {
            operator delete((void *)v40);
            v40 = 0;
            v41 = 0;
          }
          if ( v38 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
          v16 = v39;
          goto LABEL_109;
        }
        v25 = v42;
        v42 = 0;
        if ( v25 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v25 + 16LL))(v25);
        v26 = (char *)v45;
        if ( v47 >= 8 )
          v26 = v45[0];
        v27 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(
                v26,
                (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
                1,
                &v42);
        if ( v27 < 0 )
        {
          v28 = (const char *)v45;
          if ( v47 >= 8 )
            v28 = v45[0];
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5E5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v27,
            (int)"Failed while initializing optional package adapter for package '%ws'",
            v28);
          if ( v47 >= 8 )
            operator delete(v45[0]);
          v47 = 7;
          v46 = 0;
          LOWORD(v45[0]) = 0;
          if ( v42 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v42 + 16LL))(v42);
          if ( (_QWORD)v40 )
          {
            operator delete((void *)v40);
            v40 = 0;
            v41 = 0;
          }
          if ( v38 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_68:
          v16 = v27;
          goto LABEL_109;
        }
        v27 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(v42, 0, v39, v44);
        v29 = (const char *)v45;
        if ( v27 < 0 )
        {
          if ( v47 >= 8 )
            v29 = v45[0];
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5EA,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v27,
            (int)"Encountered failure while removing optional package %ws",
            v29);
          if ( v47 >= 8 )
            operator delete(v45[0]);
          v47 = 7;
          v46 = 0;
          LOWORD(v45[0]) = 0;
          if ( v42 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v42 + 16LL))(v42);
          if ( (_QWORD)v40 )
          {
            operator delete((void *)v40);
            v40 = 0;
            v41 = 0;
          }
          if ( v38 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
          goto LABEL_68;
        }
        if ( v47 >= 8 )
          v29 = v45[0];
        v30 = MsixPackage::Provisioning::Library::MsixPackageAdapter::AddDeprovisionedPackageMarking(v42, v29);
        if ( v30 < 0 )
        {
          v31 = (const char *)v45;
          if ( v47 >= 8 )
            v31 = v45[0];
          LODWORD(v35) = v30;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x5F5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v30,
            (int)"AddDeprovisionedPackageMarking '%ws' hit error 0x%0x",
            v31,
            v35);
        }
        if ( v47 >= 8 )
          operator delete(v45[0]);
        v20 = v42;
        v19 = v40;
      }
      if ( v20 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
      v4 = v39;
    }
  }
  else
  {
    LODWORD(v35) = OptionalPackagesForMainPackage;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x5C9,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)OptionalPackagesForMainPackage,
      (int)"Getting optional package list for '%ws' hit error 0x%0x",
      a2,
      v35);
  }
  v16 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(v38, 0, v4, v44);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Encountered failure while removing package %ws",
      a2);
    if ( (_QWORD)v40 )
    {
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    if ( v38 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_109;
  }
  v32 = MsixPackage::Provisioning::Library::MsixPackageAdapter::AddDeprovisionedPackageMarking(v38, a2);
  if ( v32 < 0 )
  {
    LODWORD(v35) = v32;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x609,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v32,
      (int)"AddDeprovisionedPackageMarking '%ws' hit error 0x%0x",
      a2,
      v35);
  }
  v16 = MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges((MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x60C,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Encountered failure while finalizing package provision list.",
      v34);
    if ( (_QWORD)v40 )
    {
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    if ( v38 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_109;
  }
  if ( (_QWORD)v40 )
  {
    operator delete((void *)v40);
    v40 = 0;
    v41 = 0;
  }
  if ( v38 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v38 + 16LL))(v38);
  MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
  return 0;
}

```

## disassembly

```asm
0x18003925c  push    rbx
0x18003925e  push    rsi
0x18003925f  push    rdi
0x180039260  push    r12
0x180039262  push    r13
0x180039264  push    r14
0x180039266  push    r15
0x180039268  sub     rsp, 450h
0x18003926f  mov     rax, cs:__security_cookie
0x180039276  xor     rax, rsp
0x180039279  mov     [rsp+488h+var_48], rax
0x180039281  mov     [rsp+488h+var_3C8], r9
0x180039289  mov     r14d, r8d
0x18003928c  mov     [rsp+488h+var_3F8], r8d
0x180039294  mov     r12, rdx
0x180039297  lea     r10, [rcx+0A8h]
0x18003929e  cmp     qword ptr [r10+18h], 8
0x1800392a3  jb      short loc_1800392A8
0x1800392a5  mov     r10, [r10]
0x1800392a8  lea     rax, [rcx+48h]
0x1800392ac  cmp     qword ptr [rax+18h], 8
0x1800392b1  jb      short loc_1800392B6
0x1800392b3  mov     rax, [rax]
0x1800392b6  lea     rdx, [rcx+88h]
0x1800392bd  cmp     qword ptr [rdx+18h], 8
0x1800392c2  jb      short loc_1800392C7
0x1800392c4  mov     rdx, [rdx]
0x1800392c7  lea     r8, [rcx+68h]
0x1800392cb  cmp     qword ptr [r8+18h], 8
0x1800392d0  jb      short loc_1800392D5
0x1800392d2  mov     r8, [r8]
0x1800392d5  lea     r9, [rcx+28h]
0x1800392d9  cmp     qword ptr [r9+18h], 8
0x1800392de  jb      short loc_1800392E3
0x1800392e0  mov     r9, [r9]
0x1800392e3  movzx   r11d, byte ptr [rcx+8]
0x1800392e8  mov     ebx, [rcx+20h]
0x1800392eb  mov     rdi, [rcx+18h]
0x1800392ef  mov     rsi, [rcx+10h]
0x1800392f3  add     rcx, 0C8h
0x1800392fa  cmp     qword ptr [rcx+18h], 8
0x1800392ff  jb      short loc_180039304
0x180039301  mov     rcx, [rcx]
0x180039304  mov     [rsp+488h+var_438], r10
0x180039309  mov     [rsp+488h+var_440], rax
0x18003930e  mov     [rsp+488h+var_448], rdx
0x180039313  mov     [rsp+488h+var_450], r8
0x180039318  mov     [rsp+488h+var_458], r9
0x18003931d  mov     dword ptr [rsp+488h+var_460], r11d; char *
0x180039322  mov     [rsp+488h+var_468], ebx
0x180039326  mov     r9, rdi
0x180039329  mov     r8, rsi
0x18003932c  mov     rdx, rcx
0x18003932f  lea     rcx, [rsp+488h+Table]
0x180039337  call    ??0MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@PEBGPEAUHKEY__@@1JH00000W4StubPackageOption@@IH0@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(ushort const *,HKEY__ *,HKEY__ *,long,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,StubPackageOption,uint,int,ushort const *)
0x18003933c  nop
0x18003933d  xor     ebx, ebx
0x18003933f  mov     [rsp+488h+var_400], rbx
0x180039347  xorps   xmm0, xmm0
0x18003934a  movdqu  [rsp+488h+var_3F0], xmm0
0x180039353  mov     [rsp+488h+var_3E0], rbx
0x18003935b  mov     [rsp+488h+var_407], bl
0x180039362  mov     [rsp+488h+var_408], bl
0x180039369  lea     rdx, [rsp+488h+var_408]
0x180039371  mov     rcx, r12
0x180039374  call    cs:__imp_IsPackageFamilyInUninstallBlocklistByPackageFullName
0x18003937a  mov     edi, eax
0x18003937c  test    eax, eax
0x18003937e  jns     short loc_1800393EF
0x180039380  mov     rcx, [rsp+488h]; this
0x180039388  lea     rax, aFailedWhileSea_1; "Failed while searching uninstall blockl"...
0x18003938f  mov     qword ptr [rsp+488h+var_468], rax; int
0x180039394  mov     r9d, edi; char *
0x180039397  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003939e  mov     edx, 5B7h; void *
0x1800393a3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800393a8  nop
0x1800393a9  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x1800393b1  test    rcx, rcx
0x1800393b4  jz      short loc_1800393D0
0x1800393b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800393bc  xorps   xmm0, xmm0
0x1800393bf  movdqu  [rsp+488h+var_3F0], xmm0
0x1800393c8  mov     [rsp+488h+var_3E0], rbx
0x1800393d0  mov     rcx, [rsp+488h+var_400]
0x1800393d8  test    rcx, rcx
0x1800393db  jz      short loc_1800393EA
0x1800393dd  mov     rax, [rcx]
0x1800393e0  mov     rax, [rax+10h]
0x1800393e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393e9  nop
0x1800393ea  jmp     loc_180039BD7
0x1800393ef  cmp     [rsp+488h+var_408], bl
0x1800393f6  jz      short loc_18003946C
0x1800393f8  mov     rcx, [rsp+488h]; this
0x180039400  lea     rax, aFailedToUninst; "Failed to uninstall becuase policy prev"...
0x180039407  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003940c  mov     edi, 80073CFAh
0x180039411  mov     r9d, edi; char *
0x180039414  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003941b  mov     edx, 5BBh; void *
0x180039420  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180039425  nop
0x180039426  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x18003942e  test    rcx, rcx
0x180039431  jz      short loc_18003944D
0x180039433  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180039439  xorps   xmm0, xmm0
0x18003943c  movdqu  [rsp+488h+var_3F0], xmm0
0x180039445  mov     [rsp+488h+var_3E0], rbx
0x18003944d  mov     rcx, [rsp+488h+var_400]
0x180039455  test    rcx, rcx
0x180039458  jz      short loc_180039467
0x18003945a  mov     rax, [rcx]
0x18003945d  mov     rax, [rax+10h]
0x180039461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039466  nop
0x180039467  jmp     loc_180039BD7
0x18003946c  mov     rcx, [rsp+488h+var_400]
0x180039474  mov     [rsp+488h+var_400], rbx
0x18003947c  test    rcx, rcx
0x18003947f  jz      short loc_18003948E
0x180039481  mov     rax, [rcx]
0x180039484  mov     rax, [rax+10h]
0x180039488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003948d  nop
0x18003948e  lea     r9, [rsp+488h+var_400]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x180039496  mov     r8d, 1; int
0x18003949c  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x1800394a4  mov     rcx, r12; unsigned __int16 *
0x1800394a7  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x1800394ac  mov     edi, eax
0x1800394ae  test    eax, eax
0x1800394b0  jns     short loc_180039526
0x1800394b2  mov     rcx, [rsp+488h]; this
0x1800394ba  mov     [rsp+488h+var_460], r12; char *
0x1800394bf  lea     rax, aFailedWhileIni; "Failed while initializing package adapt"...
0x1800394c6  mov     qword ptr [rsp+488h+var_468], rax; int
0x1800394cb  mov     r9d, edi; char *
0x1800394ce  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800394d5  mov     edx, 5C1h; void *
0x1800394da  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800394df  nop
0x1800394e0  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x1800394e8  test    rcx, rcx
0x1800394eb  jz      short loc_180039507
0x1800394ed  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800394f3  xorps   xmm0, xmm0
0x1800394f6  movdqu  [rsp+488h+var_3F0], xmm0
0x1800394ff  mov     [rsp+488h+var_3E0], rbx
0x180039507  mov     rcx, [rsp+488h+var_400]
0x18003950f  test    rcx, rcx
0x180039512  jz      short loc_180039521
0x180039514  mov     rax, [rcx]
0x180039517  mov     rax, [rax+10h]
0x18003951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039520  nop
0x180039521  jmp     loc_180039BD7
0x180039526  lea     rax, [rsp+488h+var_3F0]
0x18003952e  mov     qword ptr [rsp+488h+var_468], rax
0x180039533  lea     r9, [rsp+488h+var_407]
0x18003953b  lea     r8, [rsp+488h+Table]
0x180039543  xor     edx, edx
0x180039545  mov     rcx, [rsp+488h+var_400]
0x18003954d  call    ?GetOptionalPackagesForMainPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHPEAVMsixProvisioningContext@234@PEA_NAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(int,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool *,std::vector<ushort const *> &)
0x180039552  test    eax, eax
0x180039554  jns     loc_18003962A
0x18003955a  mov     rcx, [rsp+488h]; this
0x180039562  mov     dword ptr [rsp+488h+var_458], eax
0x180039566  mov     [rsp+488h+var_460], r12; char *
0x18003956b  lea     rdx, aGettingOptiona; "Getting optional package list for '%ws'"...
0x180039572  mov     qword ptr [rsp+488h+var_468], rdx; int
0x180039577  mov     r9d, eax; char *
0x18003957a  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180039581  mov     edx, 5C9h; void *
0x180039586  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003958b  lea     r13, aAdddeprovision_1; "AddDeprovisionedPackageMarking '%ws' hi"...
0x180039592  mov     r9, [rsp+488h+var_3C8]; int *
0x18003959a  mov     r8d, r14d; int
0x18003959d  xor     edx, edx; int
0x18003959f  mov     rcx, [rsp+488h+var_400]; this
0x1800395a7  call    ?RemovePackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHHPEAH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(int,int,int *)
0x1800395ac  mov     edi, eax
0x1800395ae  test    eax, eax
0x1800395b0  jns     loc_180039B1C
0x1800395b6  mov     rcx, [rsp+488h]; this
0x1800395be  mov     [rsp+488h+var_460], r12; char *
0x1800395c3  lea     rax, aEncounteredFai_2; "Encountered failure while removing pack"...
0x1800395ca  mov     qword ptr [rsp+488h+var_468], rax; int
0x1800395cf  mov     r9d, edi; char *
0x1800395d2  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800395d9  mov     edx, 5FFh; void *
0x1800395de  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800395e3  nop
0x1800395e4  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x1800395ec  test    rcx, rcx
0x1800395ef  jz      short loc_18003960B
0x1800395f1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800395f7  xorps   xmm0, xmm0
0x1800395fa  movdqu  [rsp+488h+var_3F0], xmm0
0x180039603  mov     [rsp+488h+var_3E0], rbx
0x18003960b  mov     rcx, [rsp+488h+var_400]
0x180039613  test    rcx, rcx
0x180039616  jz      short loc_180039625
0x180039618  mov     rax, [rcx]
0x18003961b  mov     rax, [rax+10h]
0x18003961f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039624  nop
0x180039625  jmp     loc_180039BD7
0x18003962a  mov     rdx, qword ptr [rsp+488h+var_3F0]
0x180039632  mov     rax, qword ptr [rsp+488h+var_3F0+8]
0x18003963a  cmp     rdx, rax
0x18003963d  jz      loc_18003958B
0x180039643  cmp     [rsp+488h+var_407], bl
0x18003964a  jz      loc_18003958B
0x180039650  mov     rcx, rbx
0x180039653  mov     [rsp+488h+var_3D8], rbx
0x18003965b  mov     r15, rax
0x18003965e  sub     r15, rdx
0x180039661  sar     r15, 3
0x180039665  mov     rsi, rbx
0x180039668  mov     edi, 7
0x18003966d  lea     r13, aAdddeprovision_1; "AddDeprovisionedPackageMarking '%ws' hi"...
0x180039674  mov     [rsp+488h+var_3D0], rsi
0x18003967c  cmp     rsi, r15
0x18003967f  jnb     loc_180039A94
0x180039685  mov     [rsp+488h+var_3A8], rdi
0x18003968d  mov     [rsp+488h+var_3B0], rbx
0x180039695  mov     word ptr [rsp+488h+var_3C0], bx
0x18003969d  sub     rax, rdx
0x1800396a0  sar     rax, 3
0x1800396a4  cmp     rax, rsi
0x1800396a7  jbe     loc_180039C5B
0x1800396ad  mov     rdx, [rdx+rsi*8]; Src
0x1800396b1  mov     [rsp+488h+var_388], rdi
0x1800396b9  mov     [rsp+488h+var_390], rbx
0x1800396c1  mov     word ptr [rsp+488h+Src], bx
0x1800396c9  cmp     [rdx], bx
0x1800396cc  jnz     short loc_1800396D3
0x1800396ce  mov     r8, rbx
0x1800396d1  jmp     short loc_1800396E1
0x1800396d3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800396d7  inc     r8
0x1800396da  cmp     [rdx+r8*2], bx
0x1800396df  jnz     short loc_1800396D7
0x1800396e1  lea     rcx, [rsp+488h+Src]; void *
0x1800396e9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800396ee  lea     rdx, [rsp+488h+Src]; Src
0x1800396f6  lea     rcx, [rsp+488h+var_3C0]; void *
0x1800396fe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180039703  cmp     [rsp+488h+var_388], 8
0x18003970c  jb      short loc_18003971D
0x18003970e  mov     rcx, [rsp+488h+Src]
0x180039716  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003971c  nop
0x18003971d  mov     rcx, [rsp+488h+var_3D8]
0x180039725  mov     [rsp+488h+var_3D8], rbx
0x18003972d  test    rcx, rcx
0x180039730  jz      short loc_18003973F
0x180039732  mov     rax, [rcx]
0x180039735  mov     rax, [rax+10h]
0x180039739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003973e  nop
0x18003973f  lea     rcx, [rsp+488h+var_3C0]
0x180039747  cmp     [rsp+488h+var_3A8], 8
0x180039750  cmovnb  rcx, [rsp+488h+var_3C0]; unsigned __int16 *
0x180039759  lea     r9, [rsp+488h+var_3D8]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x180039761  mov     r8d, 1; int
0x180039767  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18003976f  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180039774  mov     r14d, eax
0x180039777  test    eax, eax
0x180039779  jns     loc_18003985B
0x18003977f  lea     rdx, [rsp+488h+var_3C0]
0x180039787  cmp     [rsp+488h+var_3A8], 8
0x180039790  cmovnb  rdx, [rsp+488h+var_3C0]
0x180039799  mov     rcx, [rsp+488h]; this
0x1800397a1  mov     [rsp+488h+var_460], rdx; char *
0x1800397a6  lea     rax, aFailedWhileIni_0; "Failed while initializing optional pack"...
0x1800397ad  mov     qword ptr [rsp+488h+var_468], rax; int
0x1800397b2  mov     r9d, r14d; char *
0x1800397b5  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800397bc  mov     edx, 5E5h; void *
0x1800397c1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800397c6  nop
0x1800397c7  cmp     [rsp+488h+var_3A8], 8
0x1800397d0  jb      short loc_1800397E0
0x1800397d2  mov     rcx, [rsp+488h+var_3C0]
0x1800397da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800397e0  mov     [rsp+488h+var_3A8], rdi
0x1800397e8  mov     [rsp+488h+var_3B0], rbx
0x1800397f0  mov     word ptr [rsp+488h+var_3C0], bx
0x1800397f8  mov     rcx, [rsp+488h+var_3D8]
0x180039800  test    rcx, rcx
0x180039803  jz      short loc_180039812
0x180039805  mov     rax, [rcx]
0x180039808  mov     rax, [rax+10h]
0x18003980c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039811  nop
0x180039812  mov     rcx, qword ptr [rsp+488h+var_3F0]
  ... truncated ...
```
