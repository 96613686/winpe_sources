# MsixPackage::Provisioning::Library::MsixPackageAdapter::WriteSetupPhaseForPackageTypesRequiringFullRegistration(void)

- ea: `0x18004fc1c`
- end: `0x180050026`
- name: `?WriteSetupPhaseForPackageTypesRequiringFullRegistration@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `1034`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18004c884`
- `0x1800502c8`

## callees

- `0x18003d4ec`
- `0x180041770`
- `0x18004a4d4`
- `0x18004b408`
- `0x18004b664`
- `0x18004b7d4`
- `0x18004fc1c`
- `0x18006c5f0`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004fd27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe53`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe93`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fff9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fd27`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe53`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe6f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fe93`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fff9`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004fd64`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004ffa8`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004fd64`
- `AppXAllUserStore!UpdatePackageSetupPhase` at `0x18004ffa8`

## string_xrefs

- `0x18004fc78`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004fd0f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004fe0e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ff11`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ffde`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004fd81`: `Failed to write setupPhase for package %ws`
- `0x18004ffc5`: `Failed to write setupPhase for package %ws`

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
0x18004fc1c  push    rbp
0x18004fc1e  push    rsi
0x18004fc1f  push    rdi
0x18004fc20  push    r12
0x18004fc22  push    r14
0x18004fc24  push    r15
0x18004fc26  lea     rbp, [rsp-2Fh]
0x18004fc2b  sub     rsp, 98h
0x18004fc32  mov     rax, cs:__security_cookie
0x18004fc39  xor     rax, rsp
0x18004fc3c  mov     [rbp+57h+var_40], rax
0x18004fc40  mov     rsi, rcx
0x18004fc43  xor     r15d, r15d
0x18004fc46  mov     [rbp+57h+var_90], r15b
0x18004fc4a  lea     rdx, [rbp+57h+var_90]; bool *
0x18004fc4e  call    ?IsLanguageOverlayPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsLanguageOverlayPackage(bool &)
0x18004fc53  mov     edi, eax
0x18004fc55  test    eax, eax
0x18004fc57  jns     short loc_18004FC97
0x18004fc59  add     rsi, 30h ; '0'
0x18004fc5d  cmp     qword ptr [rsi+18h], 8
0x18004fc62  jb      short loc_18004FC67
0x18004fc64  mov     rsi, [rsi]
0x18004fc67  lea     rax, aFailedToDeterm_11; "Failed to determine if package %ws is a"...
0x18004fc6e  mov     edx, 9D6h; void *
0x18004fc73  mov     [rsp+0C0h+var_98], rsi; char *
0x18004fc78  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004fc7f  mov     r9d, edi; char *
0x18004fc82  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004fc87  mov     rcx, [rbp+5Fh]; this
0x18004fc8b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fc90  mov     eax, edi
0x18004fc92  jmp     loc_180050008
0x18004fc97  mov     r12d, 7
0x18004fc9d  cmp     [rbp+57h+var_90], r15b
0x18004fca1  jz      loc_18004FE9F
0x18004fca7  mov     [rbp+57h+var_88], r15d
0x18004fcab  mov     [rbp+57h+var_68], r12
0x18004fcaf  mov     [rbp+57h+var_70], r15
0x18004fcb3  mov     word ptr [rbp+57h+var_80], r15w
0x18004fcb8  mov     [rbp+57h+var_48], r12
0x18004fcbc  mov     [rbp+57h+var_50], r15
0x18004fcc0  mov     word ptr [rbp+57h+var_60], r15w
0x18004fcc5  lea     rdi, [rsi+30h]
0x18004fcc9  cmp     qword ptr [rdi+18h], 8
0x18004fcce  jb      short loc_18004FCD5
0x18004fcd0  mov     rdx, [rdi]
0x18004fcd3  jmp     short loc_18004FCD8
0x18004fcd5  mov     rdx, rdi
0x18004fcd8  lea     r8, [rbp+57h+var_60]
0x18004fcdc  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x18004fce1  mov     r14d, eax
0x18004fce4  test    eax, eax
0x18004fce6  jns     short loc_18004FD45
0x18004fce8  cmp     qword ptr [rdi+18h], 8
0x18004fced  jb      short loc_18004FCF2
0x18004fcef  mov     rdi, [rdi]
0x18004fcf2  lea     rax, aFailedToObtain_12; "Failed to obtain package family name fo"...
0x18004fcf9  mov     edx, 9E2h; void *
0x18004fcfe  mov     [rsp+0C0h+var_98], rdi; char *
0x18004fd03  mov     rcx, [rbp+5Fh]; this
0x18004fd07  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004fd0c  mov     r9d, r14d; char *
0x18004fd0f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004fd16  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fd1b  nop
0x18004fd1c  cmp     [rbp+57h+var_48], 8
0x18004fd21  jb      short loc_18004FD33
0x18004fd23  mov     rcx, [rbp+57h+var_60]
0x18004fd27  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fd2e  nop     dword ptr [rax+rax+00h]
0x18004fd33  mov     [rbp+57h+var_48], r12
0x18004fd37  mov     [rbp+57h+var_50], r15
0x18004fd3b  mov     word ptr [rbp+57h+var_60], r15w
0x18004fd40  jmp     loc_18004FFEE
0x18004fd45  lea     rdx, [rbp+57h+var_60]
0x18004fd49  cmp     [rbp+57h+var_48], 8
0x18004fd4e  cmovnb  rdx, [rbp+57h+var_60]
0x18004fd53  mov     rcx, [rsi+10h]
0x18004fd57  mov     r8d, 1
0x18004fd5d  mov     rcx, [rcx+248h]
0x18004fd64  call    cs:__imp_UpdatePackageSetupPhase
0x18004fd6b  nop     dword ptr [rax+rax+00h]
0x18004fd70  mov     r14d, eax
0x18004fd73  test    eax, eax
0x18004fd75  jns     short loc_18004FD92
0x18004fd77  cmp     qword ptr [rdi+18h], 8
0x18004fd7c  jb      short loc_18004FD81
0x18004fd7e  mov     rdi, [rdi]
0x18004fd81  lea     rax, aFailedToWriteS_0; "Failed to write setupPhase for package "...
0x18004fd88  mov     edx, 9E8h
0x18004fd8d  jmp     loc_18004FCFE
0x18004fd92  lea     rdx, [rbp+57h+var_80]
0x18004fd96  mov     rcx, rsi
0x18004fd99  call    ?GetOverlayLanguageName@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetOverlayLanguageName(std::wstring &)
0x18004fd9e  mov     r14d, eax
0x18004fda1  test    eax, eax
0x18004fda3  jns     short loc_18004FDC0
0x18004fda5  cmp     qword ptr [rdi+18h], 8
0x18004fdaa  jb      short loc_18004FDAF
0x18004fdac  mov     rdi, [rdi]
0x18004fdaf  lea     rax, aFailedToDeterm_5; "Failed to determine language name from "...
0x18004fdb6  mov     edx, 9EEh
0x18004fdbb  jmp     loc_18004FCFE
0x18004fdc0  lea     rdx, [rbp+57h+var_80]
0x18004fdc4  cmp     [rbp+57h+var_68], 8
0x18004fdc9  cmovnb  rdx, [rbp+57h+var_80]
0x18004fdce  mov     rcx, [rsi+10h]
0x18004fdd2  lea     r9, [rbp+57h+var_88]
0x18004fdd6  mov     rcx, [rcx+250h]
0x18004fddd  call    AddOverlayLanguageToListOfUILanguages
0x18004fde2  mov     edi, eax
0x18004fde4  test    eax, eax
0x18004fde6  jns     short loc_18004FE64
0x18004fde8  lea     rdx, [rbp+57h+var_80]
0x18004fdec  cmp     [rbp+57h+var_68], 8
0x18004fdf1  cmovnb  rdx, [rbp+57h+var_80]
0x18004fdf6  mov     rcx, [rbp+5Fh]; this
0x18004fdfa  mov     [rsp+0C0h+var_98], rdx; char *
0x18004fdff  lea     rax, aFailedToAddLan; "Failed to add language: %ws to the UI L"...
0x18004fe06  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004fe0b  mov     r9d, edi; char *
0x18004fe0e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004fe15  mov     edx, 9F8h; void *
0x18004fe1a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fe1f  nop
0x18004fe20  cmp     [rbp+57h+var_48], 8
0x18004fe25  jb      short loc_18004FE37
0x18004fe27  mov     rcx, [rbp+57h+var_60]
0x18004fe2b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fe32  nop     dword ptr [rax+rax+00h]
0x18004fe37  mov     [rbp+57h+var_48], r12
0x18004fe3b  mov     [rbp+57h+var_50], r15
0x18004fe3f  mov     word ptr [rbp+57h+var_60], r15w
0x18004fe44  cmp     [rbp+57h+var_68], 8
0x18004fe49  jb      loc_18004FC90
0x18004fe4f  mov     rcx, [rbp+57h+var_80]
0x18004fe53  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fe5a  nop     dword ptr [rax+rax+00h]
0x18004fe5f  jmp     loc_18004FC90
0x18004fe64  cmp     [rbp+57h+var_48], 8
0x18004fe69  jb      short loc_18004FE7B
0x18004fe6b  mov     rcx, [rbp+57h+var_60]
0x18004fe6f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fe76  nop     dword ptr [rax+rax+00h]
0x18004fe7b  mov     [rbp+57h+var_48], r12
0x18004fe7f  mov     [rbp+57h+var_50], r15
0x18004fe83  mov     word ptr [rbp+57h+var_60], r15w
0x18004fe88  cmp     [rbp+57h+var_68], 8
0x18004fe8d  jb      short loc_18004FE9F
0x18004fe8f  mov     rcx, [rbp+57h+var_80]
0x18004fe93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fe9a  nop     dword ptr [rax+rax+00h]
0x18004fe9f  mov     [rbp+57h+var_90], r15b
0x18004fea3  lea     rdx, [rbp+57h+var_90]; bool *
0x18004fea7  mov     rcx, rsi; this
0x18004feaa  call    ?IsDependencyTargetPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsDependencyTargetPackage(bool &)
0x18004feaf  mov     edi, eax
0x18004feb1  test    eax, eax
0x18004feb3  jns     short loc_18004FED4
0x18004feb5  add     rsi, 30h ; '0'
0x18004feb9  cmp     qword ptr [rsi+18h], 8
0x18004febe  jb      short loc_18004FEC3
0x18004fec0  mov     rsi, [rsi]
0x18004fec3  lea     rax, aFailedToDeterm_8; "Failed to determine if package %ws is a"...
0x18004feca  mov     edx, 9FDh
0x18004fecf  jmp     loc_18004FC73
0x18004fed4  mov     [rbp+57h+var_8C], r15d
0x18004fed8  lea     rdx, [rbp+57h+var_8C]; int *
0x18004fedc  mov     rcx, rsi; this
0x18004fedf  call    ?IsPackageFramework@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEAH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageFramework(int &)
0x18004fee4  mov     r14d, eax
0x18004fee7  test    eax, eax
0x18004fee9  jns     short loc_18004FF27
0x18004feeb  add     rsi, 30h ; '0'
0x18004feef  cmp     qword ptr [rsi+18h], 8
0x18004fef4  jb      short loc_18004FEF9
0x18004fef6  mov     rsi, [rsi]
0x18004fef9  mov     rcx, [rbp+5Fh]; this
0x18004fefd  mov     [rsp+0C0h+var_98], rsi; char *
0x18004ff02  lea     rax, aFailedToDeterm_6; "Failed to determine if package %ws is a"...
0x18004ff09  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004ff0e  mov     r9d, r14d; char *
0x18004ff11  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ff18  mov     edx, 0A01h; void *
0x18004ff1d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ff22  jmp     loc_180050005
0x18004ff27  cmp     [rbp+57h+var_90], r15b
0x18004ff2b  jnz     short loc_18004FF41
0x18004ff2d  cmp     [rbp+57h+var_8C], r15d
0x18004ff31  jz      loc_180050005
0x18004ff37  cmp     [rsi+24h], r15d
0x18004ff3b  jnz     loc_180050005
0x18004ff41  mov     [rbp+57h+var_68], r12
0x18004ff45  mov     [rbp+57h+var_70], r15
0x18004ff49  mov     word ptr [rbp+57h+var_80], r15w
0x18004ff4e  lea     rdi, [rsi+30h]
0x18004ff52  cmp     qword ptr [rdi+18h], 8
0x18004ff57  jb      short loc_18004FF5E
0x18004ff59  mov     rdx, [rdi]
0x18004ff5c  jmp     short loc_18004FF61
0x18004ff5e  mov     rdx, rdi
0x18004ff61  lea     r8, [rbp+57h+var_80]
0x18004ff65  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x18004ff6a  mov     r14d, eax
0x18004ff6d  test    eax, eax
0x18004ff6f  jns     short loc_18004FF89
0x18004ff71  cmp     qword ptr [rdi+18h], 8
0x18004ff76  jb      short loc_18004FF7B
0x18004ff78  mov     rdi, [rdi]
0x18004ff7b  lea     rax, aFailedToObtain_12; "Failed to obtain package family name fo"...
0x18004ff82  mov     edx, 0A0Bh
0x18004ff87  jmp     short loc_18004FFD1
0x18004ff89  lea     rdx, [rbp+57h+var_80]
0x18004ff8d  cmp     [rbp+57h+var_68], 8
0x18004ff92  cmovnb  rdx, [rbp+57h+var_80]
0x18004ff97  mov     rcx, [rsi+10h]
0x18004ff9b  mov     r8d, 800h
0x18004ffa1  mov     rcx, [rcx+248h]
0x18004ffa8  call    cs:__imp_UpdatePackageSetupPhase
0x18004ffaf  nop     dword ptr [rax+rax+00h]
0x18004ffb4  mov     r14d, eax
0x18004ffb7  test    eax, eax
0x18004ffb9  jns     short loc_18004FFEE
0x18004ffbb  cmp     qword ptr [rdi+18h], 8
0x18004ffc0  jb      short loc_18004FFC5
0x18004ffc2  mov     rdi, [rdi]
0x18004ffc5  lea     rax, aFailedToWriteS_0; "Failed to write setupPhase for package "...
0x18004ffcc  mov     edx, 0A11h; void *
0x18004ffd1  mov     [rsp+0C0h+var_98], rdi; char *
0x18004ffd6  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004ffdb  mov     r9d, r14d; char *
0x18004ffde  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ffe5  mov     rcx, [rbp+5Fh]; this
0x18004ffe9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ffee  cmp     [rbp+57h+var_68], 8
0x18004fff3  jb      short loc_180050005
0x18004fff5  mov     rcx, [rbp+57h+var_80]
0x18004fff9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180050000  nop     dword ptr [rax+rax+00h]
0x180050005  mov     eax, r14d
0x180050008  mov     rcx, [rbp+57h+var_40]
0x18005000c  xor     rcx, rsp; StackCookie
0x18005000f  call    __security_check_cookie
0x180050014  add     rsp, 98h
0x18005001b  pop     r15
0x18005001d  pop     r14
0x18005001f  pop     r12
0x180050021  pop     rdi
0x180050022  pop     rsi
0x180050023  pop     rbp
0x180050024  retn
```
