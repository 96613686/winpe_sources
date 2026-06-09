# MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(void)

- ea: `0x18004ae64`
- end: `0x18004b556`
- name: `?StagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `1778`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800466d4`
- `0x1800487bc`
- `0x18004c440`

## callees

- `0x18001bf0c`
- `0x180039124`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003b8b0`
- `0x18003f580`
- `0x18003fae4`
- `0x180047610`
- `0x180047780`
- `0x18004a744`
- `0x18004a7a4`
- `0x18004ae64`
- `0x180054cdc`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004b0a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b139`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b1b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b25b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b2e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b3ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b479`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b4f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b515`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b0a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b139`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b1b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b25b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b2e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b3ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b479`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b4f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004b515`

## string_xrefs

- `0x18004af59`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b11a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b195`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b225`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b2ab`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b32e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b378`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b45a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b4d7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b216`: `failed to retrieve manifest reader for package %ws`
- `0x18004b44b`: `Failed while setting Package SID ACE on directory %ws`
- `0x18004b4c8`: `Failed while setting framework package ACLs on directory %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this)
{
  unsigned int v3; // r14d
  bool v4; // r12
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // edi
  char *v10; // rdx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r8
  const char *v13; // rdi
  char *v14; // rdx
  unsigned __int64 v15; // r8
  char *v16; // rdx
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // rax
  const char *v21; // rdx
  int v22; // esi
  __int64 *v23; // rcx
  __int64 v24; // rax
  int v25; // esi
  int AppxAllUserStoreAllowExecuteFlag; // esi
  const char *v27; // rsi
  unsigned int IsLanguageOverlayPackage; // eax
  int IsPackageFramework; // esi
  __int64 v30; // r8
  const char *v31; // rdx
  int v32; // edi
  const char *v33; // rdx
  void **v34; // rdx
  int v35; // edi
  const char *v36; // rdx
  bool v37; // [rsp+30h] [rbp-78h] BYREF
  int v38; // [rsp+34h] [rbp-74h] BYREF
  __int64 *v39; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v40[2]; // [rsp+40h] [rbp-68h] BYREF
  char v41; // [rsp+50h] [rbp-58h]
  void *Src[3]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int64 v43; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( *((int *)this + 6) >= 2 )
    return 0;
  v40[1] = this;
  v41 = 1;
  v3 = 0;
  v4 = 0;
  v37 = 0;
  v38 = 0;
  v5 = *((_DWORD *)this + 9);
  if ( !v5 )
    goto LABEL_8;
  v6 = v5 - 1;
  if ( !v6 )
  {
    v3 = 2;
    goto LABEL_9;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v3 = 4;
    goto LABEL_9;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v3 = 8;
    goto LABEL_9;
  }
  if ( v8 == 1 )
LABEL_8:
    v3 = 1;
LABEL_9:
  if ( *((_DWORD *)this + 66) || !*(_DWORD *)(*((_QWORD *)this + 26) + 160LL) || *((_DWORD *)this + 9) == 1 )
  {
    if ( *((_DWORD *)this + 7) )
      v3 |= 0x20u;
  }
  else
  {
    v3 |= 0x10u;
  }
  v9 = MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(*((MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2));
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x384,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v9,
      (int)"Failed while trying to take ownership of '%ws'",
      *(const char **)(*((_QWORD *)this + 2) + 560LL));
    *((_DWORD *)this + 6) = 2;
    return (unsigned int)v9;
  }
  v43 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src, (char *)L"\\\\?\\", 4u);
  v10 = *(char **)(*((_QWORD *)this + 2) + 560LL);
  v11 = -1;
  if ( *(_WORD *)v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v10[2 * v12] );
  }
  else
  {
    v12 = 0;
  }
  std::wstring::append(Src, v10, v12);
  std::wstring::append(Src, (char *)L"\\", pszSrc[0] != 0);
  v13 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v14 = (char *)this + 48;
  else
    v14 = *(char **)v13;
  if ( *(_WORD *)v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v14[2 * v15] );
  }
  else
  {
    v15 = 0;
  }
  std::wstring::append(Src, v14, v15);
  std::wstring::assign((_QWORD *)this + 14, (char *)L"%SYSTEMDRIVE%\\Program Files\\WindowsApps", 0x27u);
  std::wstring::append((_QWORD *)this + 14, (char *)L"\\", pszSrc[0] != 0);
  if ( *((_QWORD *)this + 9) < 8u )
    v16 = (char *)this + 48;
  else
    v16 = *(char **)v13;
  if ( *(_WORD *)v16 )
  {
    do
      ++v11;
    while ( *(_WORD *)&v16[2 * v11] );
  }
  else
  {
    v11 = 0;
  }
  std::wstring::append((_QWORD *)this + 14, v16, v11);
  if ( *((_DWORD *)this + 68) )
  {
    if ( v43 >= 8 )
      operator delete(Src[0]);
    *((_DWORD *)this + 6) = 2;
    return 0;
  }
  v17 = (const unsigned __int16 *)Src;
  if ( v43 >= 8 )
    v17 = (const unsigned __int16 *)Src[0];
  v18 = MsixPackage::Provisioning::Library::PackageMonikerToPayload::Unpack(
          *((MsixPackage::Provisioning::Library::PackageMonikerToPayload **)this + 26),
          v17);
  v19 = v18;
  if ( v18 == -2147221164 )
  {
    v19 = -1051262700;
LABEL_46:
    v20 = (const char *)(*((_QWORD *)this + 26) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 26) + 80LL) >= 8u )
      v20 = *(const char **)v20;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)v19,
      (int)"Failed to Unpack package '%ws'",
      v20);
    if ( v43 >= 8 )
      operator delete(Src[0]);
    *((_DWORD *)this + 6) = 2;
    return v19;
  }
  if ( v18 < 0 )
    goto LABEL_46;
  if ( *((_QWORD *)this + 9) < 8u )
    v21 = (char *)this + 48;
  else
    v21 = *(const char **)v13;
  v22 = MsixPackage::Provisioning::Library::MsixProvisioningContext::AddPackageToImage(
          *((MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
          v21,
          v3);
  if ( v22 < 0 )
  {
    if ( *((_QWORD *)this + 9) >= 8u )
      v13 = *(const char **)v13;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v22,
      (int)"failed to add package %ws to provision list.",
      v13);
    if ( v43 >= 8 )
      operator delete(Src[0]);
    *((_DWORD *)this + 6) = 2;
    return (unsigned int)v22;
  }
  v40[0] = 0;
  v23 = (__int64 *)*((_QWORD *)this + 30);
  if ( v23 )
  {
    v39 = 0;
    v24 = *v23;
    v39 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v24 + 56))(v23, &v39);
    if ( v25 < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v13 = *(const char **)v13;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3AF,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v25,
        (int)"failed to retrieve manifest reader for package %ws",
        v13);
      if ( v39 )
        (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
      if ( v43 >= 8 )
        operator delete(Src[0]);
      *((_DWORD *)this + 6) = 2;
      return (unsigned int)v25;
    }
    AppxAllUserStoreAllowExecuteFlag = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetAppxAllUserStoreAllowExecuteFlag(
                                         &v39,
                                         v40);
    if ( AppxAllUserStoreAllowExecuteFlag < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v13 = *(const char **)v13;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)AppxAllUserStoreAllowExecuteFlag,
        (int)"failed to retrieve appxalluserstore flags for package %ws",
        v13);
      if ( v39 )
        (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
      if ( v43 >= 8 )
        operator delete(Src[0]);
      *((_DWORD *)this + 6) = 2;
      return (unsigned int)AppxAllUserStoreAllowExecuteFlag;
    }
    if ( *((_QWORD *)this + 9) < 8u )
      v27 = (char *)this + 48;
    else
      v27 = *(const char **)v13;
    IsLanguageOverlayPackage = MsixPackage::Provisioning::Library::MsixPackageAdapter::IsLanguageOverlayPackage(
                                 this,
                                 &v37);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)IsLanguageOverlayPackage,
      (int)"Failed to determine if package %ws is a language overlay package",
      v27);
    IsPackageFramework = MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageFramework(this, &v38);
    if ( IsPackageFramework < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v13 = *(const char **)v13;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3BF,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)IsPackageFramework,
        (int)"Failed to determine if package %ws is a framework package",
        v13);
      if ( v39 )
        (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
      if ( v43 >= 8 )
        operator delete(Src[0]);
      *((_DWORD *)this + 6) = 2;
      return (unsigned int)IsPackageFramework;
    }
    v23 = v39;
    if ( v39 )
      (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
    v4 = v37;
    v30 = v40[0];
  }
  else
  {
    v30 = 8;
  }
  if ( *((_DWORD *)this + 9) != 3 && !v4 && !v38 )
  {
    v31 = (const char *)Src;
    if ( v43 >= 8 )
      v31 = (const char *)Src[0];
    v32 = MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs((__int64)this, v31, v30);
    if ( v32 < 0 )
    {
      v33 = (const char *)Src;
      if ( v43 >= 8 )
        v33 = (const char *)Src[0];
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3CD,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v32,
        (int)"Failed while setting Package SID ACE on directory %ws",
        v33);
      if ( v43 >= 8 )
        operator delete(Src[0]);
      *((_DWORD *)this + 6) = 2;
      return (unsigned int)v32;
    }
    goto LABEL_111;
  }
  v34 = Src;
  if ( v43 >= 8 )
    v34 = (void **)Src[0];
  v35 = MsixPackage::Provisioning::Library::MsixPackageAdapter::SetFrameworkACLs(v23, v34, v30);
  if ( v35 >= 0 )
  {
LABEL_111:
    if ( v43 >= 8 )
      operator delete(Src[0]);
    *((_DWORD *)this + 6) = 2;
    return 0;
  }
  v36 = (const char *)Src;
  if ( v43 >= 8 )
    v36 = (const char *)Src[0];
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x3C9,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v35,
    (int)"Failed while setting framework package ACLs on directory %ws",
    v36);
  if ( v43 >= 8 )
    operator delete(Src[0]);
  *((_DWORD *)this + 6) = 2;
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x18004ae64  mov     [rsp+arg_8], rbx
0x18004ae69  mov     [rsp+arg_10], rsi
0x18004ae6e  push    rdi
0x18004ae6f  push    r12
0x18004ae71  push    r13
0x18004ae73  push    r14
0x18004ae75  push    r15
0x18004ae77  sub     rsp, 80h
0x18004ae7e  mov     rax, cs:__security_cookie
0x18004ae85  xor     rax, rsp
0x18004ae88  mov     [rsp+0A8h+var_30], rax
0x18004ae8d  mov     rbx, rcx
0x18004ae90  mov     esi, 2
0x18004ae95  cmp     [rcx+18h], esi
0x18004ae98  jl      short loc_18004AEA1
0x18004ae9a  xor     eax, eax
0x18004ae9c  jmp     loc_18004B52B
0x18004aea1  mov     [rsp+0A8h+var_60], rbx
0x18004aea6  mov     [rsp+0A8h+var_58], 1
0x18004aeab  xor     r13d, r13d
0x18004aeae  mov     r14d, r13d
0x18004aeb1  mov     r12b, r13b
0x18004aeb4  mov     [rsp+0A8h+var_78], r13b
0x18004aeb9  mov     [rsp+0A8h+var_74], r13d
0x18004aebe  mov     ecx, [rcx+24h]
0x18004aec1  test    ecx, ecx
0x18004aec3  jz      short loc_18004AED9
0x18004aec5  sub     ecx, 1
0x18004aec8  jz      short loc_18004AF14
0x18004aeca  sub     ecx, 1
0x18004aecd  jz      short loc_18004AF0C
0x18004aecf  sub     ecx, 1
0x18004aed2  jz      short loc_18004AF04
0x18004aed4  cmp     ecx, 1
0x18004aed7  jnz     short loc_18004AEDF
0x18004aed9  mov     r14d, 1
0x18004aedf  cmp     [rbx+108h], r13d
0x18004aee6  jnz     short loc_18004AF19
0x18004aee8  mov     rax, [rbx+0D0h]
0x18004aeef  cmp     [rax+0A0h], r13d
0x18004aef6  jz      short loc_18004AF19
0x18004aef8  cmp     dword ptr [rbx+24h], 1
0x18004aefc  jz      short loc_18004AF19
0x18004aefe  or      r14d, 10h
0x18004af02  jmp     short loc_18004AF23
0x18004af04  mov     r14d, 8
0x18004af0a  jmp     short loc_18004AEDF
0x18004af0c  mov     r14d, 4
0x18004af12  jmp     short loc_18004AEDF
0x18004af14  mov     r14d, esi
0x18004af17  jmp     short loc_18004AEDF
0x18004af19  cmp     [rbx+1Ch], r13d
0x18004af1d  jz      short loc_18004AF23
0x18004af1f  or      r14d, 20h
0x18004af23  mov     rcx, [rbx+10h]; this
0x18004af27  call    ?TakeOwnershipOfSingleInstanceRoot@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(void)
0x18004af2c  mov     edi, eax
0x18004af2e  test    eax, eax
0x18004af30  jns     short loc_18004AF75
0x18004af32  mov     rdx, [rbx+10h]
0x18004af36  mov     rcx, [rsp+0A8h]; this
0x18004af3e  mov     rdx, [rdx+230h]
0x18004af45  mov     [rsp+0A8h+var_80], rdx; char *
0x18004af4a  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x18004af51  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004af56  mov     r9d, edi; char *
0x18004af59  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004af60  mov     edx, 384h; void *
0x18004af65  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004af6a  nop
0x18004af6b  mov     [rbx+18h], esi
0x18004af6e  mov     eax, edi
0x18004af70  jmp     loc_18004B52B
0x18004af75  mov     [rsp+0A8h+var_38], 7
0x18004af7e  mov     [rsp+0A8h+var_40], r13
0x18004af83  mov     word ptr [rsp+0A8h+Src], r13w
0x18004af89  mov     r8d, 4
0x18004af8f  lea     rdx, asc_180074250; "\\\\?\\"
0x18004af96  lea     rcx, [rsp+0A8h+Src]; void *
0x18004af9b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004afa0  nop
0x18004afa1  mov     rax, [rbx+10h]
0x18004afa5  mov     rdx, [rax+230h]; void *
0x18004afac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004afb0  cmp     [rdx], r13w
0x18004afb4  jnz     short loc_18004AFBB
0x18004afb6  mov     r8, r13
0x18004afb9  jmp     short loc_18004AFC8
0x18004afbb  mov     r8, rsi
0x18004afbe  inc     r8
0x18004afc1  cmp     [rdx+r8*2], r13w
0x18004afc6  jnz     short loc_18004AFBE
0x18004afc8  lea     rcx, [rsp+0A8h+Src]; Src
0x18004afcd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004afd2  mov     r8, r13
0x18004afd5  cmp     word ptr cs:pszSrc, r13w; "\\"
0x18004afdd  setnz   r8b
0x18004afe1  lea     rdx, pszSrc; "\\"
0x18004afe8  lea     rcx, [rsp+0A8h+Src]; Src
0x18004afed  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004aff2  lea     rdi, [rbx+30h]
0x18004aff6  cmp     qword ptr [rdi+18h], 8
0x18004affb  jb      short loc_18004B002
0x18004affd  mov     rdx, [rdi]
0x18004b000  jmp     short loc_18004B005
0x18004b002  mov     rdx, rdi; void *
0x18004b005  cmp     [rdx], r13w
0x18004b009  jnz     short loc_18004B010
0x18004b00b  mov     r8, r13
0x18004b00e  jmp     short loc_18004B01D
0x18004b010  mov     r8, rsi
0x18004b013  inc     r8
0x18004b016  cmp     [rdx+r8*2], r13w
0x18004b01b  jnz     short loc_18004B013
0x18004b01d  lea     rcx, [rsp+0A8h+Src]; Src
0x18004b022  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004b027  lea     r15, [rbx+70h]
0x18004b02b  mov     r8d, 27h ; '''
0x18004b031  lea     rdx, aSystemdrivePro; "%SYSTEMDRIVE%\\Program Files\\WindowsAp"...
0x18004b038  mov     rcx, r15; void *
0x18004b03b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004b040  mov     r8, r13
0x18004b043  cmp     word ptr cs:pszSrc, r13w; "\\"
0x18004b04b  setnz   r8b
0x18004b04f  lea     rdx, pszSrc; "\\"
0x18004b056  mov     rcx, r15; Src
0x18004b059  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004b05e  cmp     qword ptr [rdi+18h], 8
0x18004b063  jb      short loc_18004B06A
0x18004b065  mov     rdx, [rdi]
0x18004b068  jmp     short loc_18004B06D
0x18004b06a  mov     rdx, rdi; void *
0x18004b06d  cmp     [rdx], r13w
0x18004b071  jnz     short loc_18004B078
0x18004b073  mov     rsi, r13
0x18004b076  jmp     short loc_18004B082
0x18004b078  inc     rsi
0x18004b07b  cmp     [rdx+rsi*2], r13w
0x18004b080  jnz     short loc_18004B078
0x18004b082  mov     r8, rsi
0x18004b085  mov     rcx, r15; Src
0x18004b088  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004b08d  cmp     [rbx+110h], r13d
0x18004b094  jz      short loc_18004B0B8
0x18004b096  cmp     [rsp+0A8h+var_38], 8
0x18004b09c  jb      short loc_18004B0AA
0x18004b09e  mov     rcx, [rsp+0A8h+Src]
0x18004b0a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004b0a9  nop
0x18004b0aa  mov     dword ptr [rbx+18h], 2
0x18004b0b1  xor     eax, eax
0x18004b0b3  jmp     loc_18004B52B
0x18004b0b8  lea     rdx, [rsp+0A8h+Src]
0x18004b0bd  cmp     [rsp+0A8h+var_38], 8
0x18004b0c3  cmovnb  rdx, [rsp+0A8h+Src]; unsigned __int16 *
0x18004b0c9  mov     rcx, [rbx+0D0h]; this
0x18004b0d0  call    ?Unpack@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::PackageMonikerToPayload::Unpack(ushort const *)
0x18004b0d5  mov     esi, eax
0x18004b0d7  cmp     eax, 80040154h
0x18004b0dc  jnz     short loc_18004B0E5
0x18004b0de  mov     esi, 0C1570114h
0x18004b0e3  jmp     short loc_18004B0E9
0x18004b0e5  test    eax, eax
0x18004b0e7  jns     short loc_18004B14E
0x18004b0e9  mov     rax, [rbx+0D0h]
0x18004b0f0  add     rax, 38h ; '8'
0x18004b0f4  cmp     qword ptr [rax+18h], 8
0x18004b0f9  jb      short loc_18004B0FE
0x18004b0fb  mov     rax, [rax]
0x18004b0fe  mov     rcx, [rsp+0A8h]; this
0x18004b106  mov     [rsp+0A8h+var_80], rax; char *
0x18004b10b  lea     rax, aFailedToUnpack_2; "Failed to Unpack package '%ws'"
0x18004b112  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004b117  mov     r9d, esi; char *
0x18004b11a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b121  mov     edx, 3A1h; void *
0x18004b126  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b12b  nop
0x18004b12c  cmp     [rsp+0A8h+var_38], 8
0x18004b132  jb      short loc_18004B140
0x18004b134  mov     rcx, [rsp+0A8h+Src]
0x18004b139  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004b13f  nop
0x18004b140  mov     dword ptr [rbx+18h], 2
0x18004b147  mov     eax, esi
0x18004b149  jmp     loc_18004B52B
0x18004b14e  cmp     qword ptr [rdi+18h], 8
0x18004b153  jb      short loc_18004B15A
0x18004b155  mov     rdx, [rdi]
0x18004b158  jmp     short loc_18004B15D
0x18004b15a  mov     rdx, rdi
0x18004b15d  mov     r8d, r14d
0x18004b160  mov     rcx, [rbx+10h]
0x18004b164  call    ?AddPackageToImage@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGW4ProvisionPackageProperty@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::AddPackageToImage(ushort const *,ProvisionPackageProperty)
0x18004b169  mov     esi, eax
0x18004b16b  test    eax, eax
0x18004b16d  jns     short loc_18004B1C9
0x18004b16f  cmp     qword ptr [rdi+18h], 8
0x18004b174  jb      short loc_18004B179
0x18004b176  mov     rdi, [rdi]
0x18004b179  mov     rcx, [rsp+0A8h]; this
0x18004b181  mov     [rsp+0A8h+var_80], rdi; char *
0x18004b186  lea     rax, aFailedToAddPac_0; "failed to add package %ws to provision "...
0x18004b18d  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004b192  mov     r9d, esi; char *
0x18004b195  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b19c  mov     edx, 3A6h; void *
0x18004b1a1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b1a6  nop
0x18004b1a7  cmp     [rsp+0A8h+var_38], 8
0x18004b1ad  jb      short loc_18004B1BB
0x18004b1af  mov     rcx, [rsp+0A8h+Src]
0x18004b1b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004b1ba  nop
0x18004b1bb  mov     dword ptr [rbx+18h], 2
0x18004b1c2  mov     eax, esi
0x18004b1c4  jmp     loc_18004B52B
0x18004b1c9  mov     [rsp+0A8h+var_68], r13
0x18004b1ce  mov     rcx, [rbx+0F0h]
0x18004b1d5  test    rcx, rcx
0x18004b1d8  jz      loc_18004B3E6
0x18004b1de  mov     [rsp+0A8h+var_70], r13
0x18004b1e3  mov     rax, [rcx]
0x18004b1e6  mov     [rsp+0A8h+var_70], r13
0x18004b1eb  lea     rdx, [rsp+0A8h+var_70]
0x18004b1f0  mov     rax, [rax+38h]
0x18004b1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1f9  mov     esi, eax
0x18004b1fb  test    eax, eax
0x18004b1fd  jns     short loc_18004B270
0x18004b1ff  cmp     qword ptr [rdi+18h], 8
0x18004b204  jb      short loc_18004B209
0x18004b206  mov     rdi, [rdi]
0x18004b209  mov     rcx, [rsp+0A8h]; this
0x18004b211  mov     [rsp+0A8h+var_80], rdi; char *
0x18004b216  lea     rax, aFailedToRetrie_1; "failed to retrieve manifest reader for "...
0x18004b21d  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004b222  mov     r9d, esi; char *
0x18004b225  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b22c  mov     edx, 3AFh; void *
0x18004b231  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b236  nop
0x18004b237  mov     rcx, [rsp+0A8h+var_70]
0x18004b23c  test    rcx, rcx
0x18004b23f  jz      short loc_18004B24E
0x18004b241  mov     rax, [rcx]
0x18004b244  mov     rax, [rax+10h]
0x18004b248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b24d  nop
0x18004b24e  cmp     [rsp+0A8h+var_38], 8
0x18004b254  jb      short loc_18004B262
0x18004b256  mov     rcx, [rsp+0A8h+Src]
0x18004b25b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004b261  nop
0x18004b262  mov     dword ptr [rbx+18h], 2
0x18004b269  mov     eax, esi
0x18004b26b  jmp     loc_18004B52B
0x18004b270  lea     rdx, [rsp+0A8h+var_68]
0x18004b275  lea     rcx, [rsp+0A8h+var_70]
0x18004b27a  call    ?GetAppxAllUserStoreAllowExecuteFlag@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJAEBV?$com_ptr_t@UIAppxManifestReader@@Uerr_returncode_policy@wil@@@wil@@PEAW4Flags@AppxAllUserStore@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetAppxAllUserStoreAllowExecuteFlag(wil::com_ptr_t<IAppxManifestReader,wil::err_returncode_policy> const &,AppxAllUserStore::Flags *)
0x18004b27f  mov     esi, eax
0x18004b281  test    eax, eax
0x18004b283  jns     short loc_18004B2F6
0x18004b285  cmp     qword ptr [rdi+18h], 8
0x18004b28a  jb      short loc_18004B28F
0x18004b28c  mov     rdi, [rdi]
0x18004b28f  mov     rcx, [rsp+0A8h]; this
0x18004b297  mov     [rsp+0A8h+var_80], rdi; char *
0x18004b29c  lea     rax, aFailedToRetrie; "failed to retrieve appxalluserstore fla"...
0x18004b2a3  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004b2a8  mov     r9d, esi; char *
0x18004b2ab  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b2b2  mov     edx, 3B4h; void *
0x18004b2b7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b2bc  nop
0x18004b2bd  mov     rcx, [rsp+0A8h+var_70]
0x18004b2c2  test    rcx, rcx
0x18004b2c5  jz      short loc_18004B2D4
0x18004b2c7  mov     rax, [rcx]
0x18004b2ca  mov     rax, [rax+10h]
0x18004b2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2d3  nop
0x18004b2d4  cmp     [rsp+0A8h+var_38], 8
0x18004b2da  jb      short loc_18004B2E8
0x18004b2dc  mov     rcx, [rsp+0A8h+Src]
0x18004b2e1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004b2e7  nop
0x18004b2e8  mov     dword ptr [rbx+18h], 2
0x18004b2ef  mov     eax, esi
0x18004b2f1  jmp     loc_18004B52B
0x18004b2f6  cmp     qword ptr [rdi+18h], 8
0x18004b2fb  jb      short loc_18004B302
0x18004b2fd  mov     rsi, [rdi]
0x18004b300  jmp     short loc_18004B305
0x18004b302  mov     rsi, rdi
0x18004b305  lea     rdx, [rsp+0A8h+var_78]; bool *
0x18004b30a  mov     rcx, rbx; this
0x18004b30d  call    ?IsLanguageOverlayPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::IsLanguageOverlayPackage(bool &)
0x18004b312  mov     rcx, [rsp+0A8h]; this
0x18004b31a  mov     [rsp+0A8h+var_80], rsi; char *
  ... truncated ...
```
