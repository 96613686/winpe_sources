# MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(void)

- ea: `0x18004f030`
- end: `0x18004f758`
- name: `?StagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `1832`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004a6c4`
- `0x18004c884`
- `0x1800506a4`

## callees

- `0x18001d160`
- `0x18003c6d4`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003efd0`
- `0x180043000`
- `0x1800435f4`
- `0x18004b664`
- `0x18004b7d4`
- `0x18004e8dc`
- `0x18004e944`
- `0x18004f030`
- `0x180059274`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004f26f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f30b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f38c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f439`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f4c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f598`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f669`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f6ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f711`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f26f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f30b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f38c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f439`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f4c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f598`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f669`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f6ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004f711`

## string_xrefs

- `0x18004f125`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f2ec`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f36d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f403`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f48f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f518`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f562`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f64a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f6cd`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f3f4`: `failed to retrieve manifest reader for package %ws`
- `0x18004f6be`: `Failed while setting framework package ACLs on directory %ws`
- `0x18004f63b`: `Failed while setting Package SID ACE on directory %ws`

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
  _WORD *v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // r8
  const char *v13; // rdi
  char *v14; // rdx
  __int64 v15; // r8
  char *v16; // rdx
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // rax
  char *v21; // rdx
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
  std::wstring::assign(Src, (void *)L"\\\\?\\");
  v10 = *(_WORD **)(*((_QWORD *)this + 2) + 560LL);
  v11 = -1;
  if ( *v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
  }
  std::wstring::append(Src, v10);
  std::wstring::append(Src, (void *)L"\\");
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
  std::wstring::append(Src, v14);
  std::wstring::assign((char *)this + 112, L"%SYSTEMDRIVE%\\Program Files\\WindowsApps");
  std::wstring::append((char *)this + 112, (void *)L"\\");
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
  std::wstring::append((char *)this + 112, v16);
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
LABEL_43:
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
    goto LABEL_43;
  if ( *((_QWORD *)this + 9) < 8u )
    v21 = (char *)this + 48;
  else
    v21 = *(char **)v13;
  v22 = MsixPackage::Provisioning::Library::MsixProvisioningContext::AddPackageToImage(*((_QWORD *)this + 2), v21, v3);
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
    goto LABEL_108;
  }
  v34 = Src;
  if ( v43 >= 8 )
    v34 = (void **)Src[0];
  v35 = MsixPackage::Provisioning::Library::MsixPackageAdapter::SetFrameworkACLs(v23, v34, v30);
  if ( v35 >= 0 )
  {
LABEL_108:
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
0x18004f030  mov     [rsp+arg_8], rbx
0x18004f035  mov     [rsp+arg_10], rsi
0x18004f03a  push    rdi
0x18004f03b  push    r12
0x18004f03d  push    r13
0x18004f03f  push    r14
0x18004f041  push    r15
0x18004f043  sub     rsp, 80h
0x18004f04a  mov     rax, cs:__security_cookie
0x18004f051  xor     rax, rsp
0x18004f054  mov     [rsp+0A8h+var_30], rax
0x18004f059  mov     rbx, rcx
0x18004f05c  mov     esi, 2
0x18004f061  cmp     [rcx+18h], esi
0x18004f064  jl      short loc_18004F06D
0x18004f066  xor     eax, eax
0x18004f068  jmp     loc_18004F72D
0x18004f06d  mov     [rsp+0A8h+var_60], rbx
0x18004f072  mov     [rsp+0A8h+var_58], 1
0x18004f077  xor     r13d, r13d
0x18004f07a  mov     r14d, r13d
0x18004f07d  mov     r12b, r13b
0x18004f080  mov     [rsp+0A8h+var_78], r13b
0x18004f085  mov     [rsp+0A8h+var_74], r13d
0x18004f08a  mov     ecx, [rcx+24h]
0x18004f08d  test    ecx, ecx
0x18004f08f  jz      short loc_18004F0A5
0x18004f091  sub     ecx, 1
0x18004f094  jz      short loc_18004F0E0
0x18004f096  sub     ecx, 1
0x18004f099  jz      short loc_18004F0D8
0x18004f09b  sub     ecx, 1
0x18004f09e  jz      short loc_18004F0D0
0x18004f0a0  cmp     ecx, 1
0x18004f0a3  jnz     short loc_18004F0AB
0x18004f0a5  mov     r14d, 1
0x18004f0ab  cmp     [rbx+108h], r13d
0x18004f0b2  jnz     short loc_18004F0E5
0x18004f0b4  mov     rax, [rbx+0D0h]
0x18004f0bb  cmp     [rax+0A0h], r13d
0x18004f0c2  jz      short loc_18004F0E5
0x18004f0c4  cmp     dword ptr [rbx+24h], 1
0x18004f0c8  jz      short loc_18004F0E5
0x18004f0ca  or      r14d, 10h
0x18004f0ce  jmp     short loc_18004F0EF
0x18004f0d0  mov     r14d, 8
0x18004f0d6  jmp     short loc_18004F0AB
0x18004f0d8  mov     r14d, 4
0x18004f0de  jmp     short loc_18004F0AB
0x18004f0e0  mov     r14d, esi
0x18004f0e3  jmp     short loc_18004F0AB
0x18004f0e5  cmp     [rbx+1Ch], r13d
0x18004f0e9  jz      short loc_18004F0EF
0x18004f0eb  or      r14d, 20h
0x18004f0ef  mov     rcx, [rbx+10h]; this
0x18004f0f3  call    ?TakeOwnershipOfSingleInstanceRoot@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(void)
0x18004f0f8  mov     edi, eax
0x18004f0fa  test    eax, eax
0x18004f0fc  jns     short loc_18004F141
0x18004f0fe  mov     rdx, [rbx+10h]
0x18004f102  mov     rcx, [rsp+0A8h]; this
0x18004f10a  mov     rdx, [rdx+230h]
0x18004f111  mov     [rsp+0A8h+var_80], rdx; char *
0x18004f116  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x18004f11d  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004f122  mov     r9d, edi; char *
0x18004f125  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f12c  mov     edx, 384h; void *
0x18004f131  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f136  nop
0x18004f137  mov     [rbx+18h], esi
0x18004f13a  mov     eax, edi
0x18004f13c  jmp     loc_18004F72D
0x18004f141  mov     [rsp+0A8h+var_38], 7
0x18004f14a  mov     [rsp+0A8h+var_40], r13
0x18004f14f  mov     word ptr [rsp+0A8h+Src], r13w
0x18004f155  mov     r8d, 4
0x18004f15b  lea     rdx, asc_18007A250; "\\\\?\\"
0x18004f162  lea     rcx, [rsp+0A8h+Src]; void *
0x18004f167  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004f16c  nop
0x18004f16d  mov     rax, [rbx+10h]
0x18004f171  mov     rdx, [rax+230h]; void *
0x18004f178  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004f17c  cmp     [rdx], r13w
0x18004f180  jnz     short loc_18004F187
0x18004f182  mov     r8, r13
0x18004f185  jmp     short loc_18004F194
0x18004f187  mov     r8, rsi
0x18004f18a  inc     r8
0x18004f18d  cmp     [rdx+r8*2], r13w
0x18004f192  jnz     short loc_18004F18A
0x18004f194  lea     rcx, [rsp+0A8h+Src]; Src
0x18004f199  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004f19e  mov     r8, r13
0x18004f1a1  cmp     word ptr cs:pszSrc, r13w; "\\"
0x18004f1a9  setnz   r8b
0x18004f1ad  lea     rdx, pszSrc; "\\"
0x18004f1b4  lea     rcx, [rsp+0A8h+Src]; Src
0x18004f1b9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004f1be  lea     rdi, [rbx+30h]
0x18004f1c2  cmp     qword ptr [rdi+18h], 8
0x18004f1c7  jb      short loc_18004F1CE
0x18004f1c9  mov     rdx, [rdi]
0x18004f1cc  jmp     short loc_18004F1D1
0x18004f1ce  mov     rdx, rdi; void *
0x18004f1d1  cmp     [rdx], r13w
0x18004f1d5  jnz     short loc_18004F1DC
0x18004f1d7  mov     r8, r13
0x18004f1da  jmp     short loc_18004F1E9
0x18004f1dc  mov     r8, rsi
0x18004f1df  inc     r8
0x18004f1e2  cmp     [rdx+r8*2], r13w
0x18004f1e7  jnz     short loc_18004F1DF
0x18004f1e9  lea     rcx, [rsp+0A8h+Src]; Src
0x18004f1ee  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004f1f3  lea     r15, [rbx+70h]
0x18004f1f7  mov     r8d, 27h ; '''
0x18004f1fd  lea     rdx, aSystemdrivePro; "%SYSTEMDRIVE%\\Program Files\\WindowsAp"...
0x18004f204  mov     rcx, r15; void *
0x18004f207  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004f20c  mov     r8, r13
0x18004f20f  cmp     word ptr cs:pszSrc, r13w; "\\"
0x18004f217  setnz   r8b
0x18004f21b  lea     rdx, pszSrc; "\\"
0x18004f222  mov     rcx, r15; Src
0x18004f225  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004f22a  cmp     qword ptr [rdi+18h], 8
0x18004f22f  jb      short loc_18004F236
0x18004f231  mov     rdx, [rdi]
0x18004f234  jmp     short loc_18004F239
0x18004f236  mov     rdx, rdi; void *
0x18004f239  cmp     [rdx], r13w
0x18004f23d  jnz     short loc_18004F244
0x18004f23f  mov     rsi, r13
0x18004f242  jmp     short loc_18004F24E
0x18004f244  inc     rsi
0x18004f247  cmp     [rdx+rsi*2], r13w
0x18004f24c  jnz     short loc_18004F244
0x18004f24e  mov     r8, rsi
0x18004f251  mov     rcx, r15; Src
0x18004f254  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004f259  cmp     [rbx+110h], r13d
0x18004f260  jz      short loc_18004F28A
0x18004f262  cmp     [rsp+0A8h+var_38], 8
0x18004f268  jb      short loc_18004F27C
0x18004f26a  mov     rcx, [rsp+0A8h+Src]
0x18004f26f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f276  nop     dword ptr [rax+rax+00h]
0x18004f27b  nop
0x18004f27c  mov     dword ptr [rbx+18h], 2
0x18004f283  xor     eax, eax
0x18004f285  jmp     loc_18004F72D
0x18004f28a  lea     rdx, [rsp+0A8h+Src]
0x18004f28f  cmp     [rsp+0A8h+var_38], 8
0x18004f295  cmovnb  rdx, [rsp+0A8h+Src]; unsigned __int16 *
0x18004f29b  mov     rcx, [rbx+0D0h]; this
0x18004f2a2  call    ?Unpack@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::PackageMonikerToPayload::Unpack(ushort const *)
0x18004f2a7  mov     esi, eax
0x18004f2a9  cmp     eax, 80040154h
0x18004f2ae  jnz     short loc_18004F2B7
0x18004f2b0  mov     esi, 0C1570114h
0x18004f2b5  jmp     short loc_18004F2BB
0x18004f2b7  test    eax, eax
0x18004f2b9  jns     short loc_18004F326
0x18004f2bb  mov     rax, [rbx+0D0h]
0x18004f2c2  add     rax, 38h ; '8'
0x18004f2c6  cmp     qword ptr [rax+18h], 8
0x18004f2cb  jb      short loc_18004F2D0
0x18004f2cd  mov     rax, [rax]
0x18004f2d0  mov     rcx, [rsp+0A8h]; this
0x18004f2d8  mov     [rsp+0A8h+var_80], rax; char *
0x18004f2dd  lea     rax, aFailedToUnpack_2; "Failed to Unpack package '%ws'"
0x18004f2e4  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004f2e9  mov     r9d, esi; char *
0x18004f2ec  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f2f3  mov     edx, 3A1h; void *
0x18004f2f8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f2fd  nop
0x18004f2fe  cmp     [rsp+0A8h+var_38], 8
0x18004f304  jb      short loc_18004F318
0x18004f306  mov     rcx, [rsp+0A8h+Src]
0x18004f30b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f312  nop     dword ptr [rax+rax+00h]
0x18004f317  nop
0x18004f318  mov     dword ptr [rbx+18h], 2
0x18004f31f  mov     eax, esi
0x18004f321  jmp     loc_18004F72D
0x18004f326  cmp     qword ptr [rdi+18h], 8
0x18004f32b  jb      short loc_18004F332
0x18004f32d  mov     rdx, [rdi]
0x18004f330  jmp     short loc_18004F335
0x18004f332  mov     rdx, rdi
0x18004f335  mov     r8d, r14d
0x18004f338  mov     rcx, [rbx+10h]
0x18004f33c  call    ?AddPackageToImage@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGW4ProvisionPackageProperty@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::AddPackageToImage(ushort const *,ProvisionPackageProperty)
0x18004f341  mov     esi, eax
0x18004f343  test    eax, eax
0x18004f345  jns     short loc_18004F3A7
0x18004f347  cmp     qword ptr [rdi+18h], 8
0x18004f34c  jb      short loc_18004F351
0x18004f34e  mov     rdi, [rdi]
0x18004f351  mov     rcx, [rsp+0A8h]; this
0x18004f359  mov     [rsp+0A8h+var_80], rdi; char *
0x18004f35e  lea     rax, aFailedToAddPac_0; "failed to add package %ws to provision "...
0x18004f365  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004f36a  mov     r9d, esi; char *
0x18004f36d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f374  mov     edx, 3A6h; void *
0x18004f379  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f37e  nop
0x18004f37f  cmp     [rsp+0A8h+var_38], 8
0x18004f385  jb      short loc_18004F399
0x18004f387  mov     rcx, [rsp+0A8h+Src]
0x18004f38c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f393  nop     dword ptr [rax+rax+00h]
0x18004f398  nop
0x18004f399  mov     dword ptr [rbx+18h], 2
0x18004f3a0  mov     eax, esi
0x18004f3a2  jmp     loc_18004F72D
0x18004f3a7  mov     [rsp+0A8h+var_68], r13
0x18004f3ac  mov     rcx, [rbx+0F0h]
0x18004f3b3  test    rcx, rcx
0x18004f3b6  jz      loc_18004F5D6
0x18004f3bc  mov     [rsp+0A8h+var_70], r13
0x18004f3c1  mov     rax, [rcx]
0x18004f3c4  mov     [rsp+0A8h+var_70], r13
0x18004f3c9  lea     rdx, [rsp+0A8h+var_70]
0x18004f3ce  mov     rax, [rax+38h]
0x18004f3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3d7  mov     esi, eax
0x18004f3d9  test    eax, eax
0x18004f3db  jns     short loc_18004F454
0x18004f3dd  cmp     qword ptr [rdi+18h], 8
0x18004f3e2  jb      short loc_18004F3E7
0x18004f3e4  mov     rdi, [rdi]
0x18004f3e7  mov     rcx, [rsp+0A8h]; this
0x18004f3ef  mov     [rsp+0A8h+var_80], rdi; char *
0x18004f3f4  lea     rax, aFailedToRetrie_1; "failed to retrieve manifest reader for "...
0x18004f3fb  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004f400  mov     r9d, esi; char *
0x18004f403  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f40a  mov     edx, 3AFh; void *
0x18004f40f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f414  nop
0x18004f415  mov     rcx, [rsp+0A8h+var_70]
0x18004f41a  test    rcx, rcx
0x18004f41d  jz      short loc_18004F42C
0x18004f41f  mov     rax, [rcx]
0x18004f422  mov     rax, [rax+10h]
0x18004f426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f42b  nop
0x18004f42c  cmp     [rsp+0A8h+var_38], 8
0x18004f432  jb      short loc_18004F446
0x18004f434  mov     rcx, [rsp+0A8h+Src]
0x18004f439  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f440  nop     dword ptr [rax+rax+00h]
0x18004f445  nop
0x18004f446  mov     dword ptr [rbx+18h], 2
0x18004f44d  mov     eax, esi
0x18004f44f  jmp     loc_18004F72D
0x18004f454  lea     rdx, [rsp+0A8h+var_68]
0x18004f459  lea     rcx, [rsp+0A8h+var_70]
0x18004f45e  call    ?GetAppxAllUserStoreAllowExecuteFlag@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJAEBV?$com_ptr_t@UIAppxManifestReader@@Uerr_returncode_policy@wil@@@wil@@PEAW4Flags@AppxAllUserStore@@@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::GetAppxAllUserStoreAllowExecuteFlag(wil::com_ptr_t<IAppxManifestReader,wil::err_returncode_policy> const &,AppxAllUserStore::Flags *)
0x18004f463  mov     esi, eax
0x18004f465  test    eax, eax
0x18004f467  jns     short loc_18004F4E0
0x18004f469  cmp     qword ptr [rdi+18h], 8
0x18004f46e  jb      short loc_18004F473
0x18004f470  mov     rdi, [rdi]
0x18004f473  mov     rcx, [rsp+0A8h]; this
0x18004f47b  mov     [rsp+0A8h+var_80], rdi; char *
0x18004f480  lea     rax, aFailedToRetrie; "failed to retrieve appxalluserstore fla"...
0x18004f487  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18004f48c  mov     r9d, esi; char *
0x18004f48f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f496  mov     edx, 3B4h; void *
0x18004f49b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f4a0  nop
0x18004f4a1  mov     rcx, [rsp+0A8h+var_70]
0x18004f4a6  test    rcx, rcx
0x18004f4a9  jz      short loc_18004F4B8
0x18004f4ab  mov     rax, [rcx]
0x18004f4ae  mov     rax, [rax+10h]
0x18004f4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4b7  nop
0x18004f4b8  cmp     [rsp+0A8h+var_38], 8
0x18004f4be  jb      short loc_18004F4D2
0x18004f4c0  mov     rcx, [rsp+0A8h+Src]
0x18004f4c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004f4cc  nop     dword ptr [rax+rax+00h]
0x18004f4d1  nop
0x18004f4d2  mov     dword ptr [rbx+18h], 2
0x18004f4d9  mov     eax, esi
0x18004f4db  jmp     loc_18004F72D
0x18004f4e0  cmp     qword ptr [rdi+18h], 8
0x18004f4e5  jb      short loc_18004F4EC
0x18004f4e7  mov     rsi, [rdi]
0x18004f4ea  jmp     short loc_18004F4EF
0x18004f4ec  mov     rsi, rdi
  ... truncated ...
```
