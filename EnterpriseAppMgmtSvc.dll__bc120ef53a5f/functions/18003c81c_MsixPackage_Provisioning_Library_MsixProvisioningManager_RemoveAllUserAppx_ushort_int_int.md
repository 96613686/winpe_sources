# MsixPackage::Provisioning::Library::MsixProvisioningManager::RemoveAllUserAppx(ushort *,int,int *)

- ea: `0x18003c81c`
- end: `0x18003d28a`
- name: `?RemoveAllUserAppx@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAGHPEAH@Z`
- size: `2670`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d290`
- `0x18003d330`

## callees

- `0x18001d160`
- `0x180034f30`
- `0x180035a84`
- `0x18003c690`
- `0x18003c81c`
- `0x18003d4ec`
- `0x18003e278`
- `0x18003ead0`
- `0x18003f6f8`
- `0x1800451e0`
- `0x1800461ac`
- `0x1800497a4`
- `0x18004e4b0`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003c97c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c9ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cabf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cbc9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ccf4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cdbe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ce09`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ced0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cf1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cfd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d014`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d066`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d0ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d1be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d216`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c97c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c9ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cabf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cbc9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ccf4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cdbe`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ce09`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ced0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cf1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003cfd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d014`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d066`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d0ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d1be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d216`
- `AppXAllUserStore!IsPackageFamilyInUninstallBlocklistByPackageFullName` at `0x18003c934`
- `AppXAllUserStore!IsPackageFamilyInUninstallBlocklistByPackageFullName` at `0x18003c934`

## string_xrefs

- `0x18003c95d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003c9e0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003caa0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003cb52`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003cbaa`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003cd99`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003ceab`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003cfb0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d160`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d19f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003c94e`: `Failed while searching uninstall blocklist`
- `0x18003c9cc`: `Failed to uninstall becuase policy prevents the removal of this package`

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
  __int64 v12; // rdi
  __int64 v13; // rsi
  _QWORD *v14; // rcx
  int v15; // edi
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v16; // rcx
  int OptionalPackagesForMainPackage; // eax
  __int128 v18; // kr10_16
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v19; // rcx
  unsigned __int64 v20; // r15
  const char *i; // rsi
  _WORD *v22; // rdx
  __int64 v23; // r8
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v24; // rcx
  char *v25; // rcx
  int v26; // r14d
  const char *v27; // rdx
  const char *v28; // rdx
  int v29; // eax
  const char *v30; // rdx
  int v31; // eax
  char *v33; // [rsp+28h] [rbp-460h]
  _QWORD *v34; // [rsp+30h] [rbp-458h]
  _QWORD *v35; // [rsp+38h] [rbp-450h]
  _QWORD *v36; // [rsp+40h] [rbp-448h]
  _QWORD *v37; // [rsp+48h] [rbp-440h]
  _QWORD *v38; // [rsp+50h] [rbp-438h]
  char v39; // [rsp+80h] [rbp-408h] BYREF
  _BYTE v40[7]; // [rsp+81h] [rbp-407h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v41; // [rsp+88h] [rbp-400h] BYREF
  int v42; // [rsp+90h] [rbp-3F8h]
  __int128 v43; // [rsp+98h] [rbp-3F0h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-3E0h]
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v45; // [rsp+B0h] [rbp-3D8h] BYREF
  const char *v46; // [rsp+B8h] [rbp-3D0h]
  int *v47; // [rsp+C0h] [rbp-3C8h]
  char *v48[2]; // [rsp+C8h] [rbp-3C0h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-3B0h]
  unsigned __int64 v50; // [rsp+E0h] [rbp-3A8h]
  void *Src[3]; // [rsp+E8h] [rbp-3A0h] BYREF
  unsigned __int64 v52; // [rsp+100h] [rbp-388h]
  struct _RTL_AVL_TABLE Table; // [rsp+110h] [rbp-378h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  v47 = a4;
  v4 = a3;
  v42 = a3;
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
  v12 = *((_QWORD *)this + 3);
  v13 = *((_QWORD *)this + 2);
  v14 = (_QWORD *)((char *)this + 200);
  if ( v14[3] >= 8u )
    v14 = (_QWORD *)*v14;
  v38 = v6;
  v37 = v7;
  v36 = v8;
  v35 = v9;
  v34 = v10;
  LODWORD(v33) = v11;
  MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(&Table, v14, v13, v12);
  v41 = 0;
  v43 = 0;
  v44 = 0;
  v40[0] = 0;
  v39 = 0;
  v15 = IsPackageFamilyInUninstallBlocklistByPackageFullName(a2, &v39);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5B7,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed while searching uninstall blocklist",
      v33,
      v34,
      v35,
      v36,
      v37,
      v38);
    if ( (_QWORD)v43 )
    {
      operator delete((void *)v43);
      v43 = 0;
      v44 = 0;
    }
    if ( v41 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_108:
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)v15;
  }
  if ( v39 )
  {
    v15 = -2147009286;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)0x80073CFALL,
      (int)"Failed to uninstall becuase policy prevents the removal of this package",
      v33,
      v34,
      v35,
      v36,
      v37,
      v38);
    if ( (_QWORD)v43 )
    {
      operator delete((void *)v43);
      v43 = 0;
      v44 = 0;
    }
    if ( v41 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
    goto LABEL_108;
  }
  v16 = v41;
  v41 = 0;
  if ( v16 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v16 + 16LL))(v16);
  v15 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(
          a2,
          (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
          1,
          &v41);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed while initializing package adapter for package '%ws'",
      a2,
      v34,
      v35,
      v36,
      v37,
      v38);
    if ( (_QWORD)v43 )
    {
      operator delete((void *)v43);
      v43 = 0;
      v44 = 0;
    }
    if ( v41 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
    goto LABEL_108;
  }
  OptionalPackagesForMainPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(
                                     (char *)v41,
                                     0,
                                     (__int64)&Table,
                                     v40,
                                     (__int64)&v43);
  if ( OptionalPackagesForMainPackage >= 0 )
  {
    v18 = v43;
    if ( (_QWORD)v43 != *((_QWORD *)&v43 + 1) && v40[0] )
    {
      v19 = 0;
      v45 = 0;
      v20 = (__int64)(*((_QWORD *)&v43 + 1) - v43) >> 3;
      for ( i = 0; ; ++i )
      {
        v46 = i;
        if ( (unsigned __int64)i >= v20 )
          break;
        try
        {
          v50 = 7;
          v49 = 0;
          LOWORD(v48[0]) = 0;
          if ( (__int64)(*((_QWORD *)&v18 + 1) - v18) >> 3 <= (unsigned __int64)i )
            std::vector<wil::com_ptr_t<IAppxFile,wil::err_returncode_policy>>::_Xran();
          v22 = *(_WORD **)(v18 + 8LL * (_QWORD)i);
          v52 = 7;
          Src[2] = 0;
          LOWORD(Src[0]) = 0;
          if ( *v22 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v22[v23] );
          }
          std::wstring::assign(Src, v22);
          std::wstring::assign(v48, Src);
          if ( v52 >= 8 )
            operator delete(Src[0]);
        }
        catch ( ... )
        {
          v42 = wil::details::in1diag3::Return_CaughtExceptionMsg(
                  retaddr,
                  (void *)0x5E0,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
                  "Failed getting optionalPackagePath at index %Id",
                  v46);
          if ( v50 >= 8 )
            operator delete(v48[0]);
          v50 = 7;
          v49 = 0;
          LOWORD(v48[0]) = 0;
          if ( v45 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v45 + 16LL))(v45);
          if ( (_QWORD)v43 )
          {
            operator delete((void *)v43);
            v43 = 0;
            v44 = 0;
          }
          if ( v41 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
          v15 = v42;
          goto LABEL_108;
        }
        v24 = v45;
        v45 = 0;
        if ( v24 )
          (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v24 + 16LL))(v24);
        v25 = (char *)v48;
        if ( v50 >= 8 )
          v25 = v48[0];
        v26 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(
                v25,
                (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
                1,
                &v45);
        if ( v26 < 0 )
        {
          v27 = (const char *)v48;
          if ( v50 >= 8 )
            v27 = v48[0];
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5E5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v26,
            (int)"Failed while initializing optional package adapter for package '%ws'",
            v27,
            v34);
          if ( v50 >= 8 )
            operator delete(v48[0]);
          v50 = 7;
          v49 = 0;
          LOWORD(v48[0]) = 0;
          if ( v45 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v45 + 16LL))(v45);
          if ( (_QWORD)v43 )
          {
            operator delete((void *)v43);
            v43 = 0;
            v44 = 0;
          }
          if ( v41 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_67:
          v15 = v26;
          goto LABEL_108;
        }
        v26 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(v45, 0, v42, v47);
        v28 = (const char *)v48;
        if ( v26 < 0 )
        {
          if ( v50 >= 8 )
            v28 = v48[0];
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x5EA,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v26,
            (int)"Encountered failure while removing optional package %ws",
            v28,
            v34);
          if ( v50 >= 8 )
            operator delete(v48[0]);
          v50 = 7;
          v49 = 0;
          LOWORD(v48[0]) = 0;
          if ( v45 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v45 + 16LL))(v45);
          if ( (_QWORD)v43 )
          {
            operator delete((void *)v43);
            v43 = 0;
            v44 = 0;
          }
          if ( v41 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
          goto LABEL_67;
        }
        if ( v50 >= 8 )
          v28 = v48[0];
        v29 = MsixPackage::Provisioning::Library::MsixPackageAdapter::AddDeprovisionedPackageMarking(
                v45,
                (const unsigned __int16 *)v28);
        if ( v29 < 0 )
        {
          v30 = (const char *)v48;
          if ( v50 >= 8 )
            v30 = v48[0];
          LODWORD(v34) = v29;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x5F5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v29,
            (int)"AddDeprovisionedPackageMarking '%ws' hit error 0x%0x",
            v30,
            v34,
            v35,
            v36,
            v37,
            v38);
        }
        if ( v50 >= 8 )
          operator delete(v48[0]);
        v19 = v45;
        v18 = v43;
      }
      if ( v19 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
      v4 = v42;
    }
  }
  else
  {
    LODWORD(v34) = OptionalPackagesForMainPackage;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x5C9,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)OptionalPackagesForMainPackage,
      (int)"Getting optional package list for '%ws' hit error 0x%0x",
      a2,
      v34,
      v35,
      v36,
      v37,
      v38);
  }
  v15 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(v41, 0, v4, v47);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v15,
      (int)"Encountered failure while removing package %ws",
      a2,
      v34);
    if ( (_QWORD)v43 )
    {
      operator delete((void *)v43);
      v43 = 0;
      v44 = 0;
    }
    if ( v41 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
    goto LABEL_108;
  }
  v31 = MsixPackage::Provisioning::Library::MsixPackageAdapter::AddDeprovisionedPackageMarking(
          v41,
          (const unsigned __int16 *)a2);
  if ( v31 < 0 )
  {
    LODWORD(v34) = v31;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x609,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v31,
      (int)"AddDeprovisionedPackageMarking '%ws' hit error 0x%0x",
      a2,
      v34);
  }
  v15 = MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges((MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x60C,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v15,
      (int)"Encountered failure while finalizing package provision list.",
      v33,
      v34);
    if ( (_QWORD)v43 )
    {
      operator delete((void *)v43);
      v43 = 0;
      v44 = 0;
    }
    if ( v41 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
    goto LABEL_108;
  }
  if ( (_QWORD)v43 )
  {
    operator delete((void *)v43);
    v43 = 0;
    v44 = 0;
  }
  if ( v41 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v41 + 16LL))(v41);
  MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
  return 0;
}

```

## disassembly

```asm
0x18003c81c  push    rbx
0x18003c81e  push    rsi
0x18003c81f  push    rdi
0x18003c820  push    r12
0x18003c822  push    r13
0x18003c824  push    r14
0x18003c826  push    r15
0x18003c828  sub     rsp, 450h
0x18003c82f  mov     rax, cs:__security_cookie
0x18003c836  xor     rax, rsp
0x18003c839  mov     [rsp+488h+var_48], rax
0x18003c841  mov     [rsp+488h+var_3C8], r9
0x18003c849  mov     r14d, r8d
0x18003c84c  mov     [rsp+488h+var_3F8], r8d
0x18003c854  mov     r12, rdx
0x18003c857  lea     r10, [rcx+0A8h]
0x18003c85e  cmp     qword ptr [r10+18h], 8
0x18003c863  jb      short loc_18003C868
0x18003c865  mov     r10, [r10]
0x18003c868  lea     rax, [rcx+48h]
0x18003c86c  cmp     qword ptr [rax+18h], 8
0x18003c871  jb      short loc_18003C876
0x18003c873  mov     rax, [rax]
0x18003c876  lea     rdx, [rcx+88h]
0x18003c87d  cmp     qword ptr [rdx+18h], 8
0x18003c882  jb      short loc_18003C887
0x18003c884  mov     rdx, [rdx]
0x18003c887  lea     r8, [rcx+68h]
0x18003c88b  cmp     qword ptr [r8+18h], 8
0x18003c890  jb      short loc_18003C895
0x18003c892  mov     r8, [r8]
0x18003c895  lea     r9, [rcx+28h]
0x18003c899  cmp     qword ptr [r9+18h], 8
0x18003c89e  jb      short loc_18003C8A3
0x18003c8a0  mov     r9, [r9]
0x18003c8a3  movzx   r11d, byte ptr [rcx+8]
0x18003c8a8  mov     ebx, [rcx+20h]
0x18003c8ab  mov     rdi, [rcx+18h]
0x18003c8af  mov     rsi, [rcx+10h]
0x18003c8b3  add     rcx, 0C8h
0x18003c8ba  cmp     qword ptr [rcx+18h], 8
0x18003c8bf  jb      short loc_18003C8C4
0x18003c8c1  mov     rcx, [rcx]
0x18003c8c4  mov     [rsp+488h+var_438], r10
0x18003c8c9  mov     [rsp+488h+var_440], rax
0x18003c8ce  mov     [rsp+488h+var_448], rdx
0x18003c8d3  mov     [rsp+488h+var_450], r8
0x18003c8d8  mov     [rsp+488h+var_458], r9
0x18003c8dd  mov     dword ptr [rsp+488h+var_460], r11d; char *
0x18003c8e2  mov     [rsp+488h+var_468], ebx
0x18003c8e6  mov     r9, rdi
0x18003c8e9  mov     r8, rsi
0x18003c8ec  mov     rdx, rcx
0x18003c8ef  lea     rcx, [rsp+488h+Table]
0x18003c8f7  call    ??0MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@PEBGPEAUHKEY__@@1JH00000W4StubPackageOption@@IH0@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(ushort const *,HKEY__ *,HKEY__ *,long,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,StubPackageOption,uint,int,ushort const *)
0x18003c8fc  nop
0x18003c8fd  xor     ebx, ebx
0x18003c8ff  mov     [rsp+488h+var_400], rbx
0x18003c907  xorps   xmm0, xmm0
0x18003c90a  movdqu  [rsp+488h+var_3F0], xmm0
0x18003c913  mov     [rsp+488h+var_3E0], rbx
0x18003c91b  mov     [rsp+488h+var_407], bl
0x18003c922  mov     [rsp+488h+var_408], bl
0x18003c929  lea     rdx, [rsp+488h+var_408]
0x18003c931  mov     rcx, r12
0x18003c934  call    cs:__imp_IsPackageFamilyInUninstallBlocklistByPackageFullName
0x18003c93b  nop     dword ptr [rax+rax+00h]
0x18003c940  mov     edi, eax
0x18003c942  test    eax, eax
0x18003c944  jns     short loc_18003C9BB
0x18003c946  mov     rcx, [rsp+488h]; this
0x18003c94e  lea     rax, aFailedWhileSea_1; "Failed while searching uninstall blockl"...
0x18003c955  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003c95a  mov     r9d, edi; char *
0x18003c95d  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c964  mov     edx, 5B7h; void *
0x18003c969  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c96e  nop
0x18003c96f  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x18003c977  test    rcx, rcx
0x18003c97a  jz      short loc_18003C99C
0x18003c97c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c983  nop     dword ptr [rax+rax+00h]
0x18003c988  xorps   xmm0, xmm0
0x18003c98b  movdqu  [rsp+488h+var_3F0], xmm0
0x18003c994  mov     [rsp+488h+var_3E0], rbx
0x18003c99c  mov     rcx, [rsp+488h+var_400]
0x18003c9a4  test    rcx, rcx
0x18003c9a7  jz      short loc_18003C9B6
0x18003c9a9  mov     rax, [rcx]
0x18003c9ac  mov     rax, [rax+10h]
0x18003c9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9b5  nop
0x18003c9b6  jmp     loc_18003D1F8
0x18003c9bb  cmp     [rsp+488h+var_408], bl
0x18003c9c2  jz      short loc_18003CA3E
0x18003c9c4  mov     rcx, [rsp+488h]; this
0x18003c9cc  lea     rax, aFailedToUninst; "Failed to uninstall becuase policy prev"...
0x18003c9d3  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003c9d8  mov     edi, 80073CFAh
0x18003c9dd  mov     r9d, edi; char *
0x18003c9e0  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c9e7  mov     edx, 5BBh; void *
0x18003c9ec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c9f1  nop
0x18003c9f2  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x18003c9fa  test    rcx, rcx
0x18003c9fd  jz      short loc_18003CA1F
0x18003c9ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003ca06  nop     dword ptr [rax+rax+00h]
0x18003ca0b  xorps   xmm0, xmm0
0x18003ca0e  movdqu  [rsp+488h+var_3F0], xmm0
0x18003ca17  mov     [rsp+488h+var_3E0], rbx
0x18003ca1f  mov     rcx, [rsp+488h+var_400]
0x18003ca27  test    rcx, rcx
0x18003ca2a  jz      short loc_18003CA39
0x18003ca2c  mov     rax, [rcx]
0x18003ca2f  mov     rax, [rax+10h]
0x18003ca33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca38  nop
0x18003ca39  jmp     loc_18003D1F8
0x18003ca3e  mov     rcx, [rsp+488h+var_400]
0x18003ca46  mov     [rsp+488h+var_400], rbx
0x18003ca4e  test    rcx, rcx
0x18003ca51  jz      short loc_18003CA60
0x18003ca53  mov     rax, [rcx]
0x18003ca56  mov     rax, [rax+10h]
0x18003ca5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca5f  nop
0x18003ca60  lea     r9, [rsp+488h+var_400]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18003ca68  mov     r8d, 1; int
0x18003ca6e  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18003ca76  mov     rcx, r12; unsigned __int16 *
0x18003ca79  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18003ca7e  mov     edi, eax
0x18003ca80  test    eax, eax
0x18003ca82  jns     short loc_18003CAFE
0x18003ca84  mov     rcx, [rsp+488h]; this
0x18003ca8c  mov     [rsp+488h+var_460], r12; char *
0x18003ca91  lea     rax, aFailedWhileIni; "Failed while initializing package adapt"...
0x18003ca98  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003ca9d  mov     r9d, edi; char *
0x18003caa0  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003caa7  mov     edx, 5C1h; void *
0x18003caac  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003cab1  nop
0x18003cab2  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x18003caba  test    rcx, rcx
0x18003cabd  jz      short loc_18003CADF
0x18003cabf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003cac6  nop     dword ptr [rax+rax+00h]
0x18003cacb  xorps   xmm0, xmm0
0x18003cace  movdqu  [rsp+488h+var_3F0], xmm0
0x18003cad7  mov     [rsp+488h+var_3E0], rbx
0x18003cadf  mov     rcx, [rsp+488h+var_400]
0x18003cae7  test    rcx, rcx
0x18003caea  jz      short loc_18003CAF9
0x18003caec  mov     rax, [rcx]
0x18003caef  mov     rax, [rax+10h]
0x18003caf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003caf8  nop
0x18003caf9  jmp     loc_18003D1F8
0x18003cafe  lea     rax, [rsp+488h+var_3F0]
0x18003cb06  mov     qword ptr [rsp+488h+var_468], rax
0x18003cb0b  lea     r9, [rsp+488h+var_407]
0x18003cb13  lea     r8, [rsp+488h+Table]
0x18003cb1b  xor     edx, edx
0x18003cb1d  mov     rcx, [rsp+488h+var_400]
0x18003cb25  call    ?GetOptionalPackagesForMainPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHPEAVMsixProvisioningContext@234@PEA_NAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOptionalPackagesForMainPackage(int,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool *,std::vector<ushort const *> &)
0x18003cb2a  test    eax, eax
0x18003cb2c  jns     loc_18003CC08
0x18003cb32  mov     rcx, [rsp+488h]; this
0x18003cb3a  mov     dword ptr [rsp+488h+var_458], eax
0x18003cb3e  mov     [rsp+488h+var_460], r12; char *
0x18003cb43  lea     rdx, aGettingOptiona; "Getting optional package list for '%ws'"...
0x18003cb4a  mov     qword ptr [rsp+488h+var_468], rdx; int
0x18003cb4f  mov     r9d, eax; char *
0x18003cb52  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003cb59  mov     edx, 5C9h; void *
0x18003cb5e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003cb63  lea     r13, aAdddeprovision_1; "AddDeprovisionedPackageMarking '%ws' hi"...
0x18003cb6a  mov     r9, [rsp+488h+var_3C8]; int *
0x18003cb72  mov     r8d, r14d; int
0x18003cb75  xor     edx, edx; int
0x18003cb77  mov     rcx, [rsp+488h+var_400]; this
0x18003cb7f  call    ?RemovePackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHHPEAH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(int,int,int *)
0x18003cb84  mov     edi, eax
0x18003cb86  test    eax, eax
0x18003cb88  jns     loc_18003D133
0x18003cb8e  mov     rcx, [rsp+488h]; this
0x18003cb96  mov     [rsp+488h+var_460], r12; char *
0x18003cb9b  lea     rax, aEncounteredFai_2; "Encountered failure while removing pack"...
0x18003cba2  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003cba7  mov     r9d, edi; char *
0x18003cbaa  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003cbb1  mov     edx, 5FFh; void *
0x18003cbb6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003cbbb  nop
0x18003cbbc  mov     rcx, qword ptr [rsp+488h+var_3F0]
0x18003cbc4  test    rcx, rcx
0x18003cbc7  jz      short loc_18003CBE9
0x18003cbc9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003cbd0  nop     dword ptr [rax+rax+00h]
0x18003cbd5  xorps   xmm0, xmm0
0x18003cbd8  movdqu  [rsp+488h+var_3F0], xmm0
0x18003cbe1  mov     [rsp+488h+var_3E0], rbx
0x18003cbe9  mov     rcx, [rsp+488h+var_400]
0x18003cbf1  test    rcx, rcx
0x18003cbf4  jz      short loc_18003CC03
0x18003cbf6  mov     rax, [rcx]
0x18003cbf9  mov     rax, [rax+10h]
0x18003cbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc02  nop
0x18003cc03  jmp     loc_18003D1F8
0x18003cc08  mov     rdx, qword ptr [rsp+488h+var_3F0]
0x18003cc10  mov     rax, qword ptr [rsp+488h+var_3F0+8]
0x18003cc18  cmp     rdx, rax
0x18003cc1b  jz      loc_18003CB63
0x18003cc21  cmp     [rsp+488h+var_407], bl
0x18003cc28  jz      loc_18003CB63
0x18003cc2e  mov     rcx, rbx
0x18003cc31  mov     [rsp+488h+var_3D8], rbx
0x18003cc39  mov     r15, rax
0x18003cc3c  sub     r15, rdx
0x18003cc3f  sar     r15, 3
0x18003cc43  mov     rsi, rbx
0x18003cc46  mov     edi, 7
0x18003cc4b  lea     r13, aAdddeprovision_1; "AddDeprovisionedPackageMarking '%ws' hi"...
0x18003cc52  mov     [rsp+488h+var_3D0], rsi
0x18003cc5a  cmp     rsi, r15
0x18003cc5d  jnb     loc_18003D0A5
0x18003cc63  mov     [rsp+488h+var_3A8], rdi
0x18003cc6b  mov     [rsp+488h+var_3B0], rbx
0x18003cc73  mov     word ptr [rsp+488h+var_3C0], bx
0x18003cc7b  sub     rax, rdx
0x18003cc7e  sar     rax, 3
0x18003cc82  cmp     rax, rsi
0x18003cc85  jbe     loc_18003D283
0x18003cc8b  mov     rdx, [rdx+rsi*8]; Src
0x18003cc8f  mov     [rsp+488h+var_388], rdi
0x18003cc97  mov     [rsp+488h+var_390], rbx
0x18003cc9f  mov     word ptr [rsp+488h+Src], bx
0x18003cca7  cmp     [rdx], bx
0x18003ccaa  jnz     short loc_18003CCB1
0x18003ccac  mov     r8, rbx
0x18003ccaf  jmp     short loc_18003CCBF
0x18003ccb1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ccb5  inc     r8
0x18003ccb8  cmp     [rdx+r8*2], bx
0x18003ccbd  jnz     short loc_18003CCB5
0x18003ccbf  lea     rcx, [rsp+488h+Src]; void *
0x18003ccc7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003cccc  lea     rdx, [rsp+488h+Src]; Src
0x18003ccd4  lea     rcx, [rsp+488h+var_3C0]; void *
0x18003ccdc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18003cce1  cmp     [rsp+488h+var_388], 8
0x18003ccea  jb      short loc_18003CD01
0x18003ccec  mov     rcx, [rsp+488h+Src]
0x18003ccf4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003ccfb  nop     dword ptr [rax+rax+00h]
0x18003cd00  nop
0x18003cd01  mov     rcx, [rsp+488h+var_3D8]
0x18003cd09  mov     [rsp+488h+var_3D8], rbx
0x18003cd11  test    rcx, rcx
0x18003cd14  jz      short loc_18003CD23
0x18003cd16  mov     rax, [rcx]
0x18003cd19  mov     rax, [rax+10h]
0x18003cd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd22  nop
0x18003cd23  lea     rcx, [rsp+488h+var_3C0]
0x18003cd2b  cmp     [rsp+488h+var_3A8], 8
0x18003cd34  cmovnb  rcx, [rsp+488h+var_3C0]; unsigned __int16 *
0x18003cd3d  lea     r9, [rsp+488h+var_3D8]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18003cd45  mov     r8d, 1; int
0x18003cd4b  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18003cd53  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18003cd58  mov     r14d, eax
0x18003cd5b  test    eax, eax
0x18003cd5d  jns     loc_18003CE4B
0x18003cd63  lea     rdx, [rsp+488h+var_3C0]
0x18003cd6b  cmp     [rsp+488h+var_3A8], 8
0x18003cd74  cmovnb  rdx, [rsp+488h+var_3C0]
0x18003cd7d  mov     rcx, [rsp+488h]; this
0x18003cd85  mov     [rsp+488h+var_460], rdx; char *
0x18003cd8a  lea     rax, aFailedWhileIni_0; "Failed while initializing optional pack"...
0x18003cd91  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003cd96  mov     r9d, r14d; char *
0x18003cd99  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003cda0  mov     edx, 5E5h; void *
0x18003cda5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003cdaa  nop
0x18003cdab  cmp     [rsp+488h+var_3A8], 8
0x18003cdb4  jb      short loc_18003CDCA
0x18003cdb6  mov     rcx, [rsp+488h+var_3C0]
0x18003cdbe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003cdc5  nop     dword ptr [rax+rax+00h]
0x18003cdca  mov     [rsp+488h+var_3A8], rdi
0x18003cdd2  mov     [rsp+488h+var_3B0], rbx
0x18003cdda  mov     word ptr [rsp+488h+var_3C0], bx
0x18003cde2  mov     rcx, [rsp+488h+var_3D8]
  ... truncated ...
```
