# MsixPackage::Provisioning::Library::MsixPackageAdapter::WriteSetupPhaseForPackageTypesRequiringFullRegistration(void)

- ea: `0x18004b9f8`
- end: `0x18004bdd1`
- name: `?WriteSetupPhaseForPackageTypesRequiringFullRegistration@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `985`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x1800487bc`
- `0x18004c068`

## callees

- `0x180039e9c`
- `0x18003de34`
- `0x1800464e4`
- `0x1800473bc`
- `0x180047610`
- `0x180047780`
- `0x18004b9f8`
- `0x180066ad0`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004bb03`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bbfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc33`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc51`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bdab`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bb03`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bbfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc1d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc33`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bc51`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004bdab`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004bb3a`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004bd60`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004bb3a`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004bd60`

## string_xrefs

- `0x18004ba54`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004baeb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bbde`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bcc9`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bd90`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bb51`: `Failed to write setupPhase for package %ws`
- `0x18004bd77`: `Failed to write setupPhase for package %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::WriteSetupPhaseForPackageTypesRequiringFullRegistration(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this)
{
  __int64 v2; // rcx
  int IsLanguageOverlayPackage; // edi
  char *v4; // rsi
  const char *v5; // rax
  __int64 v6; // rdx
  const char *v8; // rdi
  char *v9; // rdx
  int PackageFamilyFromFullName; // r14d
  const char *v11; // rax
  __int64 v12; // rdx
  void **v13; // rdx
  __int64 v14; // r8
  char **v15; // rdx
  const char *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rsi
  const char *v19; // rdi
  char *v20; // rdx
  const char *v21; // rax
  __int64 v22; // rdx
  char **v23; // rdx
  bool v24[4]; // [rsp+30h] [rbp-39h] BYREF
  int v25; // [rsp+34h] [rbp-35h] BYREF
  int v26; // [rsp+38h] [rbp-31h] BYREF
  char *v27[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h]
  unsigned __int64 v29; // [rsp+58h] [rbp-11h]
  void *v30[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v31; // [rsp+70h] [rbp+7h]
  unsigned __int64 v32; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v24[0] = 0;
  IsLanguageOverlayPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::IsLanguageOverlayPackage(this, v24);
  if ( IsLanguageOverlayPackage < 0 )
  {
    v4 = (char *)this + 48;
    if ( *((_QWORD *)v4 + 3) >= 8u )
      v4 = *(char **)v4;
    v5 = "Failed to determine if package %ws is a language overlay package";
    v6 = 2518;
LABEL_5:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)IsLanguageOverlayPackage,
      (int)v5,
      v4);
    return (unsigned int)IsLanguageOverlayPackage;
  }
  if ( v24[0] )
  {
    v26 = 0;
    v29 = 7;
    v28 = 0;
    LOWORD(v27[0]) = 0;
    v32 = 7;
    v31 = 0;
    LOWORD(v30[0]) = 0;
    v8 = (char *)this + 48;
    if ( *((_QWORD *)this + 9) < 8u )
      v9 = (char *)this + 48;
    else
      v9 = *(char **)v8;
    PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(
                                  v2,
                                  v9,
                                  v30);
    if ( PackageFamilyFromFullName < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v8 = *(const char **)v8;
      v11 = "Failed to obtain package family name for %ws";
      v12 = 2530;
LABEL_15:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)PackageFamilyFromFullName,
        (int)v11,
        v8);
      if ( v32 >= 8 )
        operator delete(v30[0]);
      v32 = 7;
      v31 = 0;
      LOWORD(v30[0]) = 0;
      goto LABEL_66;
    }
    v13 = v30;
    if ( v32 >= 8 )
      v13 = (void **)v30[0];
    PackageFamilyFromFullName = UpdatePackageSetupPhase(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v13, 1);
    if ( PackageFamilyFromFullName < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v8 = *(const char **)v8;
      v11 = "Failed to write setupPhase for package %ws";
      v12 = 2536;
      goto LABEL_15;
    }
    PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOverlayLanguageName(
                                  this,
                                  v27);
    if ( PackageFamilyFromFullName < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v8 = *(const char **)v8;
      v11 = "Failed to determine language name from overlay package %ws";
      v12 = 2542;
      goto LABEL_15;
    }
    v15 = v27;
    if ( v29 >= 8 )
      v15 = (char **)v27[0];
    IsLanguageOverlayPackage = AddOverlayLanguageToListOfUILanguages(
                                 *(_QWORD *)(*((_QWORD *)this + 2) + 592LL),
                                 v15,
                                 v14,
                                 &v26);
    if ( IsLanguageOverlayPackage < 0 )
    {
      v16 = (const char *)v27;
      if ( v29 >= 8 )
        v16 = v27[0];
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9F8,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)IsLanguageOverlayPackage,
        (int)"Failed to add language: %ws to the UI Languages list",
        v16);
      if ( v32 >= 8 )
        operator delete(v30[0]);
      v32 = 7;
      v31 = 0;
      LOWORD(v30[0]) = 0;
      if ( v29 >= 8 )
        operator delete(v27[0]);
      return (unsigned int)IsLanguageOverlayPackage;
    }
    if ( v32 >= 8 )
      operator delete(v30[0]);
    v32 = 7;
    v31 = 0;
    LOWORD(v30[0]) = 0;
    if ( v29 >= 8 )
      operator delete(v27[0]);
  }
  v24[0] = 0;
  IsLanguageOverlayPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::IsDependencyTargetPackage(
                               this,
                               v24);
  if ( IsLanguageOverlayPackage < 0 )
  {
    v4 = (char *)this + 48;
    if ( *((_QWORD *)v4 + 3) >= 8u )
      v4 = *(char **)v4;
    v5 = "Failed to determine if package %ws is a dependencyTarget package";
    v6 = 2557;
    goto LABEL_5;
  }
  v25 = 0;
  PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageFramework(this, &v25);
  if ( PackageFamilyFromFullName < 0 )
  {
    v18 = (char *)this + 48;
    if ( *((_QWORD *)v18 + 3) >= 8u )
      v18 = *(char **)v18;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)PackageFamilyFromFullName,
      (int)"Failed to determine if package %ws is a framework package",
      v18);
    return (unsigned int)PackageFamilyFromFullName;
  }
  if ( v24[0] || v25 && !*((_DWORD *)this + 9) )
  {
    v29 = 7;
    v28 = 0;
    LOWORD(v27[0]) = 0;
    v19 = (char *)this + 48;
    if ( *((_QWORD *)this + 9) < 8u )
      v20 = (char *)this + 48;
    else
      v20 = *(char **)v19;
    PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(
                                  v17,
                                  v20,
                                  v27);
    if ( PackageFamilyFromFullName >= 0 )
    {
      v23 = v27;
      if ( v29 >= 8 )
        v23 = (char **)v27[0];
      PackageFamilyFromFullName = UpdatePackageSetupPhase(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v23, 2048);
      if ( PackageFamilyFromFullName >= 0 )
        goto LABEL_66;
      if ( *((_QWORD *)this + 9) >= 8u )
        v19 = *(const char **)v19;
      v21 = "Failed to write setupPhase for package %ws";
      v22 = 2577;
    }
    else
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v19 = *(const char **)v19;
      v21 = "Failed to obtain package family name for %ws";
      v22 = 2571;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)PackageFamilyFromFullName,
      (int)v21,
      v19);
LABEL_66:
    if ( v29 >= 8 )
      operator delete(v27[0]);
  }
  return (unsigned int)PackageFamilyFromFullName;
}

```

## disassembly

```asm
0x18004b9f8  push    rbp
0x18004b9fa  push    rsi
0x18004b9fb  push    rdi
0x18004b9fc  push    r12
0x18004b9fe  push    r14
0x18004ba00  push    r15
0x18004ba02  lea     rbp, [rsp-2Fh]
0x18004ba07  sub     rsp, 98h
0x18004ba0e  mov     rax, cs:__security_cookie
0x18004ba15  xor     rax, rsp
0x18004ba18  mov     [rbp+57h+var_40], rax
0x18004ba1c  mov     rsi, rcx
0x18004ba1f  xor     r15d, r15d
0x18004ba22  mov     [rbp+57h+var_90], r15b
0x18004ba26  lea     rdx, [rbp+57h+var_90]; bool *
0x18004ba2a  call    ?IsLanguageOverlayPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsLanguageOverlayPackage(bool &)
0x18004ba2f  mov     edi, eax
0x18004ba31  test    eax, eax
0x18004ba33  jns     short loc_18004BA73
0x18004ba35  add     rsi, 30h ; '0'
0x18004ba39  cmp     qword ptr [rsi+18h], 8
0x18004ba3e  jb      short loc_18004BA43
0x18004ba40  mov     rsi, [rsi]
0x18004ba43  lea     rax, aFailedToDeterm_11; "Failed to determine if package %ws is a"...
0x18004ba4a  mov     edx, 9D6h; void *
0x18004ba4f  mov     [rsp+0C0h+var_98], rsi; char *
0x18004ba54  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ba5b  mov     r9d, edi; char *
0x18004ba5e  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004ba63  mov     rcx, [rbp+5Fh]; this
0x18004ba67  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ba6c  mov     eax, edi
0x18004ba6e  jmp     loc_18004BDB4
0x18004ba73  mov     r12d, 7
0x18004ba79  cmp     [rbp+57h+var_90], r15b
0x18004ba7d  jz      loc_18004BC57
0x18004ba83  mov     [rbp+57h+var_88], r15d
0x18004ba87  mov     [rbp+57h+var_68], r12
0x18004ba8b  mov     [rbp+57h+var_70], r15
0x18004ba8f  mov     word ptr [rbp+57h+var_80], r15w
0x18004ba94  mov     [rbp+57h+var_48], r12
0x18004ba98  mov     [rbp+57h+var_50], r15
0x18004ba9c  mov     word ptr [rbp+57h+var_60], r15w
0x18004baa1  lea     rdi, [rsi+30h]
0x18004baa5  cmp     qword ptr [rdi+18h], 8
0x18004baaa  jb      short loc_18004BAB1
0x18004baac  mov     rdx, [rdi]
0x18004baaf  jmp     short loc_18004BAB4
0x18004bab1  mov     rdx, rdi
0x18004bab4  lea     r8, [rbp+57h+var_60]
0x18004bab8  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x18004babd  mov     r14d, eax
0x18004bac0  test    eax, eax
0x18004bac2  jns     short loc_18004BB1B
0x18004bac4  cmp     qword ptr [rdi+18h], 8
0x18004bac9  jb      short loc_18004BACE
0x18004bacb  mov     rdi, [rdi]
0x18004bace  lea     rax, aFailedToObtain_12; "Failed to obtain package family name fo"...
0x18004bad5  mov     edx, 9E2h; void *
0x18004bada  mov     [rsp+0C0h+var_98], rdi; char *
0x18004badf  mov     rcx, [rbp+5Fh]; this
0x18004bae3  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004bae8  mov     r9d, r14d; char *
0x18004baeb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004baf2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004baf7  nop
0x18004baf8  cmp     [rbp+57h+var_48], 8
0x18004bafd  jb      short loc_18004BB09
0x18004baff  mov     rcx, [rbp+57h+var_60]
0x18004bb03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bb09  mov     [rbp+57h+var_48], r12
0x18004bb0d  mov     [rbp+57h+var_50], r15
0x18004bb11  mov     word ptr [rbp+57h+var_60], r15w
0x18004bb16  jmp     loc_18004BDA0
0x18004bb1b  lea     rdx, [rbp+57h+var_60]
0x18004bb1f  cmp     [rbp+57h+var_48], 8
0x18004bb24  cmovnb  rdx, [rbp+57h+var_60]
0x18004bb29  mov     rcx, [rsi+10h]
0x18004bb2d  mov     r8d, 1
0x18004bb33  mov     rcx, [rcx+248h]
0x18004bb3a  call    cs:__imp_UpdatePackageSetupPhase
0x18004bb40  mov     r14d, eax
0x18004bb43  test    eax, eax
0x18004bb45  jns     short loc_18004BB62
0x18004bb47  cmp     qword ptr [rdi+18h], 8
0x18004bb4c  jb      short loc_18004BB51
0x18004bb4e  mov     rdi, [rdi]
0x18004bb51  lea     rax, aFailedToWriteS_0; "Failed to write setupPhase for package "...
0x18004bb58  mov     edx, 9E8h
0x18004bb5d  jmp     loc_18004BADA
0x18004bb62  lea     rdx, [rbp+57h+var_80]
0x18004bb66  mov     rcx, rsi
0x18004bb69  call    ?GetOverlayLanguageName@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOverlayLanguageName(std::wstring &)
0x18004bb6e  mov     r14d, eax
0x18004bb71  test    eax, eax
0x18004bb73  jns     short loc_18004BB90
0x18004bb75  cmp     qword ptr [rdi+18h], 8
0x18004bb7a  jb      short loc_18004BB7F
0x18004bb7c  mov     rdi, [rdi]
0x18004bb7f  lea     rax, aFailedToDeterm_5; "Failed to determine language name from "...
0x18004bb86  mov     edx, 9EEh
0x18004bb8b  jmp     loc_18004BADA
0x18004bb90  lea     rdx, [rbp+57h+var_80]
0x18004bb94  cmp     [rbp+57h+var_68], 8
0x18004bb99  cmovnb  rdx, [rbp+57h+var_80]
0x18004bb9e  mov     rcx, [rsi+10h]
0x18004bba2  lea     r9, [rbp+57h+var_88]
0x18004bba6  mov     rcx, [rcx+250h]
0x18004bbad  call    AddOverlayLanguageToListOfUILanguages
0x18004bbb2  mov     edi, eax
0x18004bbb4  test    eax, eax
0x18004bbb6  jns     short loc_18004BC28
0x18004bbb8  lea     rdx, [rbp+57h+var_80]
0x18004bbbc  cmp     [rbp+57h+var_68], 8
0x18004bbc1  cmovnb  rdx, [rbp+57h+var_80]
0x18004bbc6  mov     rcx, [rbp+5Fh]; this
0x18004bbca  mov     [rsp+0C0h+var_98], rdx; char *
0x18004bbcf  lea     rax, aFailedToAddLan; "Failed to add language: %ws to the UI L"...
0x18004bbd6  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004bbdb  mov     r9d, edi; char *
0x18004bbde  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bbe5  mov     edx, 9F8h; void *
0x18004bbea  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bbef  nop
0x18004bbf0  cmp     [rbp+57h+var_48], 8
0x18004bbf5  jb      short loc_18004BC01
0x18004bbf7  mov     rcx, [rbp+57h+var_60]
0x18004bbfb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bc01  mov     [rbp+57h+var_48], r12
0x18004bc05  mov     [rbp+57h+var_50], r15
0x18004bc09  mov     word ptr [rbp+57h+var_60], r15w
0x18004bc0e  cmp     [rbp+57h+var_68], 8
0x18004bc13  jb      loc_18004BA6C
0x18004bc19  mov     rcx, [rbp+57h+var_80]
0x18004bc1d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bc23  jmp     loc_18004BA6C
0x18004bc28  cmp     [rbp+57h+var_48], 8
0x18004bc2d  jb      short loc_18004BC39
0x18004bc2f  mov     rcx, [rbp+57h+var_60]
0x18004bc33  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bc39  mov     [rbp+57h+var_48], r12
0x18004bc3d  mov     [rbp+57h+var_50], r15
0x18004bc41  mov     word ptr [rbp+57h+var_60], r15w
0x18004bc46  cmp     [rbp+57h+var_68], 8
0x18004bc4b  jb      short loc_18004BC57
0x18004bc4d  mov     rcx, [rbp+57h+var_80]
0x18004bc51  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bc57  mov     [rbp+57h+var_90], r15b
0x18004bc5b  lea     rdx, [rbp+57h+var_90]; bool *
0x18004bc5f  mov     rcx, rsi; this
0x18004bc62  call    ?IsDependencyTargetPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsDependencyTargetPackage(bool &)
0x18004bc67  mov     edi, eax
0x18004bc69  test    eax, eax
0x18004bc6b  jns     short loc_18004BC8C
0x18004bc6d  add     rsi, 30h ; '0'
0x18004bc71  cmp     qword ptr [rsi+18h], 8
0x18004bc76  jb      short loc_18004BC7B
0x18004bc78  mov     rsi, [rsi]
0x18004bc7b  lea     rax, aFailedToDeterm_8; "Failed to determine if package %ws is a"...
0x18004bc82  mov     edx, 9FDh
0x18004bc87  jmp     loc_18004BA4F
0x18004bc8c  mov     [rbp+57h+var_8C], r15d
0x18004bc90  lea     rdx, [rbp+57h+var_8C]; int *
0x18004bc94  mov     rcx, rsi; this
0x18004bc97  call    ?IsPackageFramework@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEAH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageFramework(int &)
0x18004bc9c  mov     r14d, eax
0x18004bc9f  test    eax, eax
0x18004bca1  jns     short loc_18004BCDF
0x18004bca3  add     rsi, 30h ; '0'
0x18004bca7  cmp     qword ptr [rsi+18h], 8
0x18004bcac  jb      short loc_18004BCB1
0x18004bcae  mov     rsi, [rsi]
0x18004bcb1  mov     rcx, [rbp+5Fh]; this
0x18004bcb5  mov     [rsp+0C0h+var_98], rsi; char *
0x18004bcba  lea     rax, aFailedToDeterm_6; "Failed to determine if package %ws is a"...
0x18004bcc1  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004bcc6  mov     r9d, r14d; char *
0x18004bcc9  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bcd0  mov     edx, 0A01h; void *
0x18004bcd5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bcda  jmp     loc_18004BDB1
0x18004bcdf  cmp     [rbp+57h+var_90], r15b
0x18004bce3  jnz     short loc_18004BCF9
0x18004bce5  cmp     [rbp+57h+var_8C], r15d
0x18004bce9  jz      loc_18004BDB1
0x18004bcef  cmp     [rsi+24h], r15d
0x18004bcf3  jnz     loc_18004BDB1
0x18004bcf9  mov     [rbp+57h+var_68], r12
0x18004bcfd  mov     [rbp+57h+var_70], r15
0x18004bd01  mov     word ptr [rbp+57h+var_80], r15w
0x18004bd06  lea     rdi, [rsi+30h]
0x18004bd0a  cmp     qword ptr [rdi+18h], 8
0x18004bd0f  jb      short loc_18004BD16
0x18004bd11  mov     rdx, [rdi]
0x18004bd14  jmp     short loc_18004BD19
0x18004bd16  mov     rdx, rdi
0x18004bd19  lea     r8, [rbp+57h+var_80]
0x18004bd1d  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x18004bd22  mov     r14d, eax
0x18004bd25  test    eax, eax
0x18004bd27  jns     short loc_18004BD41
0x18004bd29  cmp     qword ptr [rdi+18h], 8
0x18004bd2e  jb      short loc_18004BD33
0x18004bd30  mov     rdi, [rdi]
0x18004bd33  lea     rax, aFailedToObtain_12; "Failed to obtain package family name fo"...
0x18004bd3a  mov     edx, 0A0Bh
0x18004bd3f  jmp     short loc_18004BD83
0x18004bd41  lea     rdx, [rbp+57h+var_80]
0x18004bd45  cmp     [rbp+57h+var_68], 8
0x18004bd4a  cmovnb  rdx, [rbp+57h+var_80]
0x18004bd4f  mov     rcx, [rsi+10h]
0x18004bd53  mov     r8d, 800h
0x18004bd59  mov     rcx, [rcx+248h]
0x18004bd60  call    cs:__imp_UpdatePackageSetupPhase
0x18004bd66  mov     r14d, eax
0x18004bd69  test    eax, eax
0x18004bd6b  jns     short loc_18004BDA0
0x18004bd6d  cmp     qword ptr [rdi+18h], 8
0x18004bd72  jb      short loc_18004BD77
0x18004bd74  mov     rdi, [rdi]
0x18004bd77  lea     rax, aFailedToWriteS_0; "Failed to write setupPhase for package "...
0x18004bd7e  mov     edx, 0A11h; void *
0x18004bd83  mov     [rsp+0C0h+var_98], rdi; char *
0x18004bd88  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004bd8d  mov     r9d, r14d; char *
0x18004bd90  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bd97  mov     rcx, [rbp+5Fh]; this
0x18004bd9b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bda0  cmp     [rbp+57h+var_68], 8
0x18004bda5  jb      short loc_18004BDB1
0x18004bda7  mov     rcx, [rbp+57h+var_80]
0x18004bdab  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004bdb1  mov     eax, r14d
0x18004bdb4  mov     rcx, [rbp+57h+var_40]
0x18004bdb8  xor     rcx, rsp; StackCookie
0x18004bdbb  call    __security_check_cookie
0x18004bdc0  add     rsp, 98h
0x18004bdc7  pop     r15
0x18004bdc9  pop     r14
0x18004bdcb  pop     r12
0x18004bdcd  pop     rdi
0x18004bdce  pop     rsi
0x18004bdcf  pop     rbp
0x18004bdd0  retn
```
