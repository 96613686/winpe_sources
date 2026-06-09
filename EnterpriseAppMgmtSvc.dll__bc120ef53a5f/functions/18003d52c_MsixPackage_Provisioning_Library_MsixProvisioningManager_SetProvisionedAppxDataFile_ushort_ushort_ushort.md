# MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(ushort *,ushort *,ushort *)

- ea: `0x18003d52c`
- end: `0x18003dd31`
- name: `?SetProvisionedAppxDataFile@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG00@Z`
- size: `2053`
- prototype: `static int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035f40`
- `0x180036618`
- `0x18003856c`

## callees

- `0x18001d050`
- `0x18001d160`
- `0x18001d65c`
- `0x180034d7c`
- `0x180035b2c`
- `0x18003d4b0`
- `0x18003d4ec`
- `0x18003d52c`
- `0x18003e50c`
- `0x180043fb4`
- `0x180063410`
- `0x180063c48`
- `0x180064654`
- `0x180064e8c`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003d721`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d758`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d8d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d910`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003da77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003daae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dbac`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc08`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc65`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dcc1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dcf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d721`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d758`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d8d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003d910`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003da77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003daae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dbac`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc08`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dc65`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dcc1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003dcf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dc92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d795`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003d82d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003d82d`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003d9e3`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003d9e3`

## string_xrefs

- `0x18003d6ec`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d7d8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d85a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d8a5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d962`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d9b2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003da2e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003db87`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003d7ff`: `Failed while trying to create custom data directory %ws`
- `0x18003d7c9`: `Failed while trying to determine whether custom data directory %ws exists`
- `0x18003d846`: `Failed while setting attributes to custom data directory %ws`
- `0x18003d81c`: `Failed while constructing path to custom data directory %ws`
- `0x18003d988`: `MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile`
- `0x18003d896`: `Failed while trying to ensure custom data directory '%ws' exists`
- `0x18003d6e5`: `Failed while verifying directory '%ws' exists`
- `0x18003d98f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003db80`: `Failed while copying custom data file to %ws`
- `0x18003da1f`: `Failed while trying to take ownership of package custom data directory '%ws'`
- `0x18003d942`: `An attempt to obtain ownership on the root folder %ws and its children`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v6; // rsi
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  void **v10; // rcx
  const char *v11; // rax
  unsigned int LastErrorMsg; // ebx
  char *v14; // rbx
  signed int LastError; // eax
  int v16; // edi
  __int64 v17; // rdx
  const char *v18; // r9
  const WCHAR *v19; // rax
  const char *v20; // rax
  char **v21; // r8
  int v22; // eax
  void *v23; // rbx
  int v24; // eax
  char **v25; // rcx
  int v26; // edi
  const char *v27; // rdx
  char **v28; // rdx
  const char *v29; // rax
  unsigned int v30; // edi
  int v31; // [rsp+20h] [rbp-118h]
  LPVOID pv; // [rsp+30h] [rbp-108h] BYREF
  _QWORD v33[2]; // [rsp+38h] [rbp-100h] BYREF
  char v34; // [rsp+48h] [rbp-F0h]
  __int64 v35; // [rsp+50h] [rbp-E8h] BYREF
  __int16 v36; // [rsp+58h] [rbp-E0h]
  __int64 v37; // [rsp+68h] [rbp-D0h]
  __int64 v38; // [rsp+70h] [rbp-C8h]
  __int16 v39; // [rsp+78h] [rbp-C0h]
  __int64 v40; // [rsp+88h] [rbp-B0h]
  __int64 v41; // [rsp+90h] [rbp-A8h]
  char *v42[2]; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-90h]
  unsigned __int64 v44; // [rsp+B0h] [rbp-88h]
  void *Src[3]; // [rsp+B8h] [rbp-80h] BYREF
  unsigned __int64 v46; // [rsp+D0h] [rbp-68h]
  char *v47[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-50h]
  unsigned __int64 v49; // [rsp+F0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v38 = 7;
  v37 = 0;
  v36 = 0;
  v41 = 7;
  v40 = 0;
  v39 = 0;
  v35 = 0;
  v46 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v6 = -1;
  if ( *a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
  }
  std::wstring::assign(Src, a3);
  std::wstring::append(Src, (void *)L"\\");
  if ( *a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  std::wstring::append(Src, a2);
  v44 = 7;
  v43 = 0;
  LOWORD(v42[0]) = 0;
  std::wstring::assign(v42);
  if ( aMicrosoftSyste[0] )
  {
    v9 = -1;
    do
      ++v9;
    while ( aMicrosoftSyste[v9] );
  }
  std::wstring::append(v42, aMicrosoftSyste);
  v33[0] = &v35;
  v33[1] = v42;
  v34 = 1;
  v10 = Src;
  if ( v46 >= 8 )
    v10 = (void **)Src[0];
  if ( !(unsigned int)DirectoryExists(v10) )
  {
    v11 = (const char *)Src;
    if ( v46 >= 8 )
      v11 = (const char *)Src[0];
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x41A,
                     (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
                     "Failed while verifying directory '%ws' exists",
                     v11);
    v34 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v33);
    if ( v44 >= 8 )
      operator delete(v42[0]);
    v44 = 7;
    v43 = 0;
    LOWORD(v42[0]) = 0;
    if ( v46 >= 8 )
      operator delete(Src[0]);
    return LastErrorMsg;
  }
  v14 = (char *)v42;
  if ( v44 >= 8 )
    v14 = v42[0];
  if ( (unsigned int)DirectoryExists(v14) )
    goto LABEL_43;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v16 = 0;
  if ( LastError != -2147024893 )
    v16 = LastError;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3D7,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed while trying to determine whether custom data directory %ws exists",
      v14);
LABEL_36:
    v20 = (const char *)v42;
    if ( v44 >= 8 )
      v20 = v42[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x41E,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed while trying to ensure custom data directory '%ws' exists",
      v20);
    v34 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v33);
    if ( v44 >= 8 )
      operator delete(v42[0]);
    v44 = 7;
    v43 = 0;
    LOWORD(v42[0]) = 0;
    if ( v46 >= 8 )
      operator delete(Src[0]);
    return (unsigned int)v16;
  }
  if ( (unsigned int)CreatePath(v14) )
  {
    v19 = (const WCHAR *)PrepareUnicodePathEx((unsigned __int16 *)v14);
    if ( v19 )
    {
      if ( SetFileAttributesW(v19, 6u) )
        goto LABEL_43;
      v17 = 1001;
      v18 = "Failed while setting attributes to custom data directory %ws";
    }
    else
    {
      v17 = 996;
      v18 = "Failed while constructing path to custom data directory %ws";
    }
  }
  else
  {
    v17 = 989;
    v18 = "Failed while trying to create custom data directory %ws";
  }
  v16 = wil::details::in1diag3::Return_GetLastErrorMsg(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          v18,
          v14);
  if ( v16 < 0 )
    goto LABEL_36;
LABEL_43:
  pv = 0;
  v21 = v42;
  if ( v44 >= 8 )
    v21 = (char **)v42[0];
  v22 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          L"An attempt to obtain ownership on the root folder %ws and its children",
          v21);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x425,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v22,
      v31);
  v23 = pv;
  v24 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
          pv,
          L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          L"MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile",
          1069);
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v24,
      2);
  v25 = v42;
  if ( v44 >= 8 )
    v25 = (char **)v42[0];
  v26 = TakeOwnershipOnFolder(v25, 1, &v35);
  if ( v26 >= 0 )
  {
    v49 = 7;
    v48 = 0;
    LOWORD(v47[0]) = 0;
    std::wstring::assign(v47);
    if ( aCustomData[0] )
    {
      do
        ++v6;
      while ( aCustomData[v6] );
    }
    std::wstring::append(v47, aCustomData);
    v28 = v47;
    if ( v49 >= 8 )
      v28 = (char **)v47[0];
    if ( (unsigned int)CopyFileWithAttributesEx2(a1, v28, 0, 0, 0, 0) )
    {
      if ( v49 >= 8 )
        operator delete(v47[0]);
      v49 = 7;
      v48 = 0;
      LOWORD(v47[0]) = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      v34 = 0;
      lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v33);
      if ( v44 >= 8 )
        operator delete(v42[0]);
      v44 = 7;
      v43 = 0;
      LOWORD(v42[0]) = 0;
      if ( v46 >= 8 )
        operator delete(Src[0]);
      return 0;
    }
    else
    {
      v29 = (const char *)v47;
      if ( v49 >= 8 )
        v29 = v47[0];
      v30 = wil::details::in1diag3::Return_GetLastErrorMsg(
              retaddr,
              (void *)0x43E,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
              "Failed while copying custom data file to %ws",
              v29);
      if ( v49 >= 8 )
        operator delete(v47[0]);
      v49 = 7;
      v48 = 0;
      LOWORD(v47[0]) = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      v34 = 0;
      lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v33);
      if ( v44 >= 8 )
        operator delete(v42[0]);
      v44 = 7;
      v43 = 0;
      LOWORD(v42[0]) = 0;
      if ( v46 >= 8 )
        operator delete(Src[0]);
      return v30;
    }
  }
  else
  {
    v27 = (const char *)v42;
    if ( v44 >= 8 )
      v27 = v42[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v26,
      (int)"Failed while trying to take ownership of package custom data directory '%ws'",
      v27);
    if ( v23 )
      CoTaskMemFree(v23);
    v34 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v33);
    if ( v44 >= 8 )
      operator delete(v42[0]);
    v44 = 7;
    v43 = 0;
    LOWORD(v42[0]) = 0;
    if ( v46 >= 8 )
      operator delete(Src[0]);
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x18003d52c  mov     r11, rsp
0x18003d52f  push    rbx
0x18003d530  push    rsi
0x18003d531  push    rdi
0x18003d532  push    r12
0x18003d534  push    r13
0x18003d536  push    r14
0x18003d538  push    r15
0x18003d53a  sub     rsp, 100h
0x18003d541  mov     rax, cs:__security_cookie
0x18003d548  xor     rax, rsp
0x18003d54b  mov     [rsp+138h+var_40], rax
0x18003d553  mov     r9, r8
0x18003d556  mov     rbx, rdx
0x18003d559  mov     r14, rcx
0x18003d55c  mov     r13d, 7
0x18003d562  mov     [rsp+138h+var_C8], r13
0x18003d567  xor     r15d, r15d
0x18003d56a  mov     [rsp+138h+var_D0], r15
0x18003d56f  mov     [rsp+138h+var_E0], r15w
0x18003d575  mov     [r11-0A8h], r13
0x18003d57c  mov     [r11-0B0h], r15
0x18003d583  mov     [rsp+138h+var_C0], r15w
0x18003d589  mov     [rsp+138h+var_E8], r15
0x18003d58e  mov     [r11-68h], r13
0x18003d592  mov     [r11-70h], r15
0x18003d596  mov     [r11-80h], r15w
0x18003d59b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003d59f  cmp     [r8], r15w
0x18003d5a3  jnz     short loc_18003D5AA
0x18003d5a5  mov     r8d, r15d
0x18003d5a8  jmp     short loc_18003D5B7
0x18003d5aa  mov     r8, rsi
0x18003d5ad  inc     r8
0x18003d5b0  cmp     [r9+r8*2], r15w
0x18003d5b5  jnz     short loc_18003D5AD
0x18003d5b7  mov     rdx, r9; Src
0x18003d5ba  lea     rcx, [rsp+138h+Src]; void *
0x18003d5c2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003d5c7  mov     r8, r15
0x18003d5ca  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003d5d2  setnz   r8b
0x18003d5d6  lea     rdx, pszSrc; "\\"
0x18003d5dd  lea     rcx, [rsp+138h+Src]; Src
0x18003d5e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003d5ea  cmp     [rbx], r15w
0x18003d5ee  jnz     short loc_18003D5F5
0x18003d5f0  mov     r8, r15
0x18003d5f3  jmp     short loc_18003D602
0x18003d5f5  mov     r8, rsi
0x18003d5f8  inc     r8
0x18003d5fb  cmp     [rbx+r8*2], r15w
0x18003d600  jnz     short loc_18003D5F8
0x18003d602  mov     rdx, rbx; void *
0x18003d605  lea     rcx, [rsp+138h+Src]; Src
0x18003d60d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003d612  mov     [rsp+138h+var_88], r13
0x18003d61a  mov     [rsp+138h+var_90], r15
0x18003d622  mov     word ptr [rsp+138h+var_A0], r15w
0x18003d62b  mov     r9, rsi
0x18003d62e  xor     r8d, r8d
0x18003d631  lea     rdx, [rsp+138h+Src]
0x18003d639  lea     rcx, [rsp+138h+var_A0]; void *
0x18003d641  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003d646  nop
0x18003d647  lea     rdx, aMicrosoftSyste; "\\microsoft.system.package.metadata"
0x18003d64e  cmp     word ptr cs:aMicrosoftSyste, r15w; "\\microsoft.system.package.metadata"
0x18003d656  jnz     short loc_18003D65D
0x18003d658  mov     r8, r15
0x18003d65b  jmp     short loc_18003D66A
0x18003d65d  mov     r8, rsi
0x18003d660  inc     r8
0x18003d663  cmp     [rdx+r8*2], r15w
0x18003d668  jnz     short loc_18003D660
0x18003d66a  lea     rcx, [rsp+138h+var_A0]; Src
0x18003d672  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003d677  lea     rax, [rsp+138h+var_E8]
0x18003d67c  mov     [rsp+138h+var_100], rax
0x18003d681  lea     rax, [rsp+138h+var_A0]
0x18003d689  mov     [rsp+138h+var_F8], rax
0x18003d68e  mov     [rsp+138h+var_F0], 1
0x18003d693  lea     rcx, [rsp+138h+Src]
0x18003d69b  mov     r12d, 8
0x18003d6a1  cmp     [rsp+138h+var_68], r12
0x18003d6a9  cmovnb  rcx, [rsp+138h+Src]
0x18003d6b2  call    DirectoryExists
0x18003d6b7  test    eax, eax
0x18003d6b9  jnz     loc_18003D76C
0x18003d6bf  lea     rax, [rsp+138h+Src]
0x18003d6c7  cmp     [rsp+138h+var_68], r12
0x18003d6cf  cmovnb  rax, [rsp+138h+Src]
0x18003d6d8  mov     rcx, [rsp+138h]; this
0x18003d6e0  mov     [rsp+138h+var_118], rax; char *
0x18003d6e5  lea     r9, aFailedWhileVer_0; "Failed while verifying directory '%ws' "...
0x18003d6ec  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d6f3  mov     edx, 41Ah; void *
0x18003d6f8  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003d6fd  mov     ebx, eax
0x18003d6ff  mov     [rsp+138h+var_F0], r15b
0x18003d704  lea     rcx, [rsp+138h+var_100]
0x18003d709  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003d70e  nop
0x18003d70f  cmp     [rsp+138h+var_88], r12
0x18003d717  jb      short loc_18003D72D
0x18003d719  mov     rcx, [rsp+138h+var_A0]
0x18003d721  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003d728  nop     dword ptr [rax+rax+00h]
0x18003d72d  mov     [rsp+138h+var_88], r13
0x18003d735  mov     [rsp+138h+var_90], r15
0x18003d73d  mov     word ptr [rsp+138h+var_A0], r15w
0x18003d746  cmp     [rsp+138h+var_68], r12
0x18003d74e  jb      short loc_18003D765
0x18003d750  mov     rcx, [rsp+138h+Src]
0x18003d758  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003d75f  nop     dword ptr [rax+rax+00h]
0x18003d764  nop
0x18003d765  mov     eax, ebx
0x18003d767  jmp     loc_18003DD0D
0x18003d76c  lea     rbx, [rsp+138h+var_A0]
0x18003d774  cmp     [rsp+138h+var_88], r12
0x18003d77c  cmovnb  rbx, [rsp+138h+var_A0]
0x18003d785  mov     rcx, rbx
0x18003d788  call    DirectoryExists
0x18003d78d  test    eax, eax
0x18003d78f  jnz     loc_18003D924
0x18003d795  call    cs:__imp_GetLastError
0x18003d79c  nop     dword ptr [rax+rax+00h]
0x18003d7a1  test    eax, eax
0x18003d7a3  jle     short loc_18003D7AD
0x18003d7a5  movzx   eax, ax
0x18003d7a8  or      eax, 80070000h
0x18003d7ad  mov     edi, r15d
0x18003d7b0  cmp     eax, 80070003h
0x18003d7b5  cmovnz  edi, eax
0x18003d7b8  test    edi, edi
0x18003d7ba  jns     short loc_18003D7EE
0x18003d7bc  mov     rcx, [rsp+138h]; this
0x18003d7c4  mov     [rsp+138h+var_110], rbx; char *
0x18003d7c9  lea     rax, aFailedWhileTry_2; "Failed while trying to determine whethe"...
0x18003d7d0  mov     [rsp+138h+var_118], rax; int
0x18003d7d5  mov     r9d, edi; char *
0x18003d7d8  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d7df  mov     edx, 3D7h; void *
0x18003d7e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003d7e9  jmp     loc_18003D870
0x18003d7ee  mov     rcx, rbx
0x18003d7f1  call    CreatePath
0x18003d7f6  test    eax, eax
0x18003d7f8  jnz     short loc_18003D808
0x18003d7fa  mov     edx, 3DDh
0x18003d7ff  lea     r9, aFailedWhileTry_1; "Failed while trying to create custom da"...
0x18003d806  jmp     short loc_18003D84D
0x18003d808  xor     edx, edx
0x18003d80a  mov     rcx, rbx; unsigned __int16 *
0x18003d80d  call    PrepareUnicodePathEx
0x18003d812  test    rax, rax
0x18003d815  jnz     short loc_18003D825
0x18003d817  mov     edx, 3E4h
0x18003d81c  lea     r9, aFailedWhileCon; "Failed while constructing path to custo"...
0x18003d823  jmp     short loc_18003D84D
0x18003d825  mov     edx, 6; dwFileAttributes
0x18003d82a  mov     rcx, rax; lpFileName
0x18003d82d  call    cs:__imp_SetFileAttributesW
0x18003d834  nop     dword ptr [rax+rax+00h]
0x18003d839  test    eax, eax
0x18003d83b  jnz     loc_18003D924
0x18003d841  mov     edx, 3E9h; void *
0x18003d846  lea     r9, aFailedWhileSet_2; "Failed while setting attributes to cust"...
0x18003d84d  mov     rcx, [rsp+138h]; this
0x18003d855  mov     [rsp+138h+var_118], rbx; char *
0x18003d85a  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d861  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003d866  mov     edi, eax
0x18003d868  test    eax, eax
0x18003d86a  jns     loc_18003D924
0x18003d870  lea     rax, [rsp+138h+var_A0]
0x18003d878  cmp     [rsp+138h+var_88], r12
0x18003d880  cmovnb  rax, [rsp+138h+var_A0]
0x18003d889  mov     rcx, [rsp+138h]; this
0x18003d891  mov     [rsp+138h+var_110], rax; char *
0x18003d896  lea     rax, aFailedWhileTry_3; "Failed while trying to ensure custom da"...
0x18003d89d  mov     [rsp+138h+var_118], rax; int
0x18003d8a2  mov     r9d, edi; char *
0x18003d8a5  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d8ac  mov     edx, 41Eh; void *
0x18003d8b1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003d8b6  nop
0x18003d8b7  mov     [rsp+138h+var_F0], r15b
0x18003d8bc  lea     rcx, [rsp+138h+var_100]
0x18003d8c1  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003d8c6  nop
0x18003d8c7  cmp     [rsp+138h+var_88], r12
0x18003d8cf  jb      short loc_18003D8E5
0x18003d8d1  mov     rcx, [rsp+138h+var_A0]
0x18003d8d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003d8e0  nop     dword ptr [rax+rax+00h]
0x18003d8e5  mov     [rsp+138h+var_88], r13
0x18003d8ed  mov     [rsp+138h+var_90], r15
0x18003d8f5  mov     word ptr [rsp+138h+var_A0], r15w
0x18003d8fe  cmp     [rsp+138h+var_68], r12
0x18003d906  jb      short loc_18003D91D
0x18003d908  mov     rcx, [rsp+138h+Src]
0x18003d910  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003d917  nop     dword ptr [rax+rax+00h]
0x18003d91c  nop
0x18003d91d  mov     eax, edi
0x18003d91f  jmp     loc_18003DD0D
0x18003d924  mov     [rsp+138h+pv], r15
0x18003d929  lea     r8, [rsp+138h+var_A0]
0x18003d931  cmp     [rsp+138h+var_88], r12
0x18003d939  cmovnb  r8, [rsp+138h+var_A0]
0x18003d942  lea     rdx, aAnAttemptToObt_0; "An attempt to obtain ownership on the r"...
0x18003d949  lea     rcx, [rsp+138h+pv]
0x18003d94e  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003d953  mov     rcx, [rsp+138h]; this
0x18003d95b  test    eax, eax
0x18003d95d  jns     short loc_18003D973
0x18003d95f  mov     r9d, eax; char *
0x18003d962  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d969  mov     edx, 425h; void *
0x18003d96e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d973  mov     dword ptr [rsp+138h+var_110], r15d
0x18003d978  mov     dword ptr [rsp+138h+var_118], 2; int
0x18003d980  mov     edi, 42Dh
0x18003d985  mov     r9d, edi
0x18003d988  lea     r8, aMsixpackagePro_25; "MsixPackage::Provisioning::Library::Msi"...
0x18003d98f  lea     rdx, aOnecoreAdminAp_14; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d996  mov     rbx, [rsp+138h+pv]
0x18003d99b  mov     rcx, rbx
0x18003d99e  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003d9a3  mov     rcx, [rsp+138h]; this
0x18003d9ab  test    eax, eax
0x18003d9ad  jns     short loc_18003D9C0
0x18003d9af  mov     r9d, eax; char *
0x18003d9b2  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003d9b9  mov     edx, edi; void *
0x18003d9bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d9c0  lea     rcx, [rsp+138h+var_A0]
0x18003d9c8  cmp     [rsp+138h+var_88], r12
0x18003d9d0  cmovnb  rcx, [rsp+138h+var_A0]
0x18003d9d9  lea     r8, [rsp+138h+var_E8]
0x18003d9de  mov     edx, 1
0x18003d9e3  call    cs:__imp_TakeOwnershipOnFolder
0x18003d9ea  nop     dword ptr [rax+rax+00h]
0x18003d9ef  mov     edi, eax
0x18003d9f1  test    eax, eax
0x18003d9f3  jns     loc_18003DAC2
0x18003d9f9  lea     rdx, [rsp+138h+var_A0]
0x18003da01  cmp     [rsp+138h+var_88], r12
0x18003da09  cmovnb  rdx, [rsp+138h+var_A0]
0x18003da12  mov     rcx, [rsp+138h]; this
0x18003da1a  mov     [rsp+138h+var_110], rdx; char *
0x18003da1f  lea     rax, aFailedWhileTry_4; "Failed while trying to take ownership o"...
0x18003da26  mov     [rsp+138h+var_118], rax; int
0x18003da2b  mov     r9d, edi; char *
0x18003da2e  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003da35  mov     edx, 434h; void *
0x18003da3a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003da3f  nop
0x18003da40  test    rbx, rbx
0x18003da43  jz      short loc_18003DA55
0x18003da45  mov     rcx, rbx; pv
0x18003da48  call    cs:__imp_CoTaskMemFree
0x18003da4f  nop     dword ptr [rax+rax+00h]
0x18003da54  nop
0x18003da55  mov     [rsp+138h+var_F0], r15b
0x18003da5a  lea     rcx, [rsp+138h+var_100]
0x18003da5f  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003da64  nop
0x18003da65  cmp     [rsp+138h+var_88], r12
0x18003da6d  jb      short loc_18003DA83
0x18003da6f  mov     rcx, [rsp+138h+var_A0]
0x18003da77  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003da7e  nop     dword ptr [rax+rax+00h]
0x18003da83  mov     [rsp+138h+var_88], r13
0x18003da8b  mov     [rsp+138h+var_90], r15
0x18003da93  mov     word ptr [rsp+138h+var_A0], r15w
0x18003da9c  cmp     [rsp+138h+var_68], r12
0x18003daa4  jb      short loc_18003DABB
0x18003daa6  mov     rcx, [rsp+138h+Src]
0x18003daae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003dab5  nop     dword ptr [rax+rax+00h]
0x18003daba  nop
0x18003dabb  mov     eax, edi
0x18003dabd  jmp     loc_18003DD0D
0x18003dac2  mov     [rsp+138h+var_48], r13
0x18003daca  mov     [rsp+138h+var_50], r15
0x18003dad2  mov     word ptr [rsp+138h+var_60], r15w
0x18003dadb  mov     r9, rsi
0x18003dade  xor     r8d, r8d
0x18003dae1  lea     rdx, [rsp+138h+var_A0]
0x18003dae9  lea     rcx, [rsp+138h+var_60]; void *
0x18003daf1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003daf6  lea     rdx, aCustomData; "\\Custom.data"
0x18003dafd  cmp     word ptr cs:aCustomData, r15w; "\\Custom.data"
0x18003db05  jnz     short loc_18003DB0C
0x18003db07  mov     rsi, r15
0x18003db0a  jmp     short loc_18003DB16
0x18003db0c  inc     rsi
0x18003db0f  cmp     [rdx+rsi*2], r15w
  ... truncated ...
```
