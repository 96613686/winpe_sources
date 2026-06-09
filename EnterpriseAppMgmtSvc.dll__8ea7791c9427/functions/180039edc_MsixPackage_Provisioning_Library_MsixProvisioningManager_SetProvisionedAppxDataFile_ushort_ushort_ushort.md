# MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(ushort *,ushort *,ushort *)

- ea: `0x180039edc`
- end: `0x18003a672`
- name: `?SetProvisionedAppxDataFile@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG00@Z`
- size: `1942`
- prototype: `static int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032f28`
- `0x1800335d8`
- `0x180035260`

## callees

- `0x18001bdfc`
- `0x18001bf0c`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180032b74`
- `0x180039e60`
- `0x180039e9c`
- `0x180039edc`
- `0x18003ae3c`
- `0x180040400`
- `0x18005e658`
- `0x18005ed60`
- `0x18005f684`
- `0x18005fd24`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003a0d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a102`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a26e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a29f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a3f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a425`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a51d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a56d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a59e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a5be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a60e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a63f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a0d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a102`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a26e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a29f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a3f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a425`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a51d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a56d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a59e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a5be`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a60e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a63f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a139`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a1c8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003a1c8`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003a36c`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003a36c`

## string_xrefs

- `0x18003a09c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a176`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a1ef`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a23a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a2eb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a33b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a3b1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a4f8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a1db`: `Failed while setting attributes to custom data directory %ws`
- `0x18003a1b7`: `Failed while constructing path to custom data directory %ws`
- `0x18003a19a`: `Failed while trying to create custom data directory %ws`
- `0x18003a167`: `Failed while trying to determine whether custom data directory %ws exists`
- `0x18003a095`: `Failed while verifying directory '%ws' exists`
- `0x18003a318`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003a4f1`: `Failed while copying custom data file to %ws`
- `0x18003a3a2`: `Failed while trying to take ownership of package custom data directory '%ws'`
- `0x18003a311`: `MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile`
- `0x18003a22b`: `Failed while trying to ensure custom data directory '%ws' exists`
- `0x18003a2cb`: `An attempt to obtain ownership on the root folder %ws and its children`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(
        unsigned __int16 *a1,
        char *a2,
        char *a3)
{
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
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
  LPVOID pv; // [rsp+30h] [rbp-108h] BYREF
  _QWORD v32[2]; // [rsp+38h] [rbp-100h] BYREF
  char v33; // [rsp+48h] [rbp-F0h]
  __int64 v34; // [rsp+50h] [rbp-E8h] BYREF
  __int16 v35; // [rsp+58h] [rbp-E0h]
  __int64 v36; // [rsp+68h] [rbp-D0h]
  __int64 v37; // [rsp+70h] [rbp-C8h]
  __int16 v38; // [rsp+78h] [rbp-C0h]
  __int64 v39; // [rsp+88h] [rbp-B0h]
  __int64 v40; // [rsp+90h] [rbp-A8h]
  char *v41[2]; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-90h]
  unsigned __int64 v43; // [rsp+B0h] [rbp-88h]
  void *Src[3]; // [rsp+B8h] [rbp-80h] BYREF
  unsigned __int64 v45; // [rsp+D0h] [rbp-68h]
  char *v46[2]; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v47; // [rsp+E8h] [rbp-50h]
  unsigned __int64 v48; // [rsp+F0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v37 = 7;
  v36 = 0;
  v35 = 0;
  v40 = 7;
  v39 = 0;
  v38 = 0;
  v34 = 0;
  v45 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  v6 = -1;
  if ( *(_WORD *)a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&a3[2 * v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::assign(Src, a3, v7);
  std::wstring::append(Src, (char *)L"\\", pszSrc[0] != 0);
  if ( *(_WORD *)a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&a2[2 * v8] );
  }
  else
  {
    v8 = 0;
  }
  std::wstring::append(Src, a2, v8);
  v43 = 7;
  v42 = 0;
  LOWORD(v41[0]) = 0;
  std::wstring::assign((void **)v41, Src, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( aMicrosoftSyste[0] )
  {
    v9 = -1;
    do
      ++v9;
    while ( aMicrosoftSyste[v9] );
  }
  else
  {
    v9 = 0;
  }
  std::wstring::append(v41, (char *)aMicrosoftSyste, v9);
  v32[0] = &v34;
  v32[1] = v41;
  v33 = 1;
  v10 = Src;
  if ( v45 >= 8 )
    v10 = (void **)Src[0];
  if ( !(unsigned int)DirectoryExists(v10) )
  {
    v11 = (const char *)Src;
    if ( v45 >= 8 )
      v11 = (const char *)Src[0];
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x41A,
                     (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
                     "Failed while verifying directory '%ws' exists",
                     v11);
    v33 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v32);
    if ( v43 >= 8 )
      operator delete(v41[0]);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( v45 >= 8 )
      operator delete(Src[0]);
    return LastErrorMsg;
  }
  v14 = (char *)v41;
  if ( v43 >= 8 )
    v14 = v41[0];
  if ( (unsigned int)DirectoryExists(v14) )
    goto LABEL_46;
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
LABEL_39:
    v20 = (const char *)v41;
    if ( v43 >= 8 )
      v20 = v41[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x41E,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed while trying to ensure custom data directory '%ws' exists",
      v20);
    v33 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v32);
    if ( v43 >= 8 )
      operator delete(v41[0]);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( v45 >= 8 )
      operator delete(Src[0]);
    return (unsigned int)v16;
  }
  if ( (unsigned int)CreatePath(v14) )
  {
    v19 = (const WCHAR *)PrepareUnicodePathEx((unsigned __int16 *)v14);
    if ( v19 )
    {
      if ( SetFileAttributesW(v19, 6u) )
        goto LABEL_46;
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
    goto LABEL_39;
LABEL_46:
  pv = 0;
  v21 = v41;
  if ( v43 >= 8 )
    v21 = (char **)v41[0];
  v22 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (char *)&pv,
          L"An attempt to obtain ownership on the root folder %ws and its children",
          v21);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x425,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v22);
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
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v24);
  v25 = v41;
  if ( v43 >= 8 )
    v25 = (char **)v41[0];
  v26 = TakeOwnershipOnFolder(v25, 1, &v34);
  if ( v26 >= 0 )
  {
    v48 = 7;
    v47 = 0;
    LOWORD(v46[0]) = 0;
    std::wstring::assign((void **)v46, (void **)v41, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( aCustomData[0] )
    {
      do
        ++v6;
      while ( aCustomData[v6] );
    }
    else
    {
      v6 = 0;
    }
    std::wstring::append(v46, (char *)aCustomData, v6);
    v28 = v46;
    if ( v48 >= 8 )
      v28 = (char **)v46[0];
    if ( (unsigned int)CopyFileWithAttributesEx2(a1, v28, 0, 0, 0, 0) )
    {
      if ( v48 >= 8 )
        operator delete(v46[0]);
      v48 = 7;
      v47 = 0;
      LOWORD(v46[0]) = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      v33 = 0;
      lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v32);
      if ( v43 >= 8 )
        operator delete(v41[0]);
      v43 = 7;
      v42 = 0;
      LOWORD(v41[0]) = 0;
      if ( v45 >= 8 )
        operator delete(Src[0]);
      return 0;
    }
    else
    {
      v29 = (const char *)v46;
      if ( v48 >= 8 )
        v29 = v46[0];
      v30 = wil::details::in1diag3::Return_GetLastErrorMsg(
              retaddr,
              (void *)0x43E,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
              "Failed while copying custom data file to %ws",
              v29);
      if ( v48 >= 8 )
        operator delete(v46[0]);
      v48 = 7;
      v47 = 0;
      LOWORD(v46[0]) = 0;
      if ( v23 )
        CoTaskMemFree(v23);
      v33 = 0;
      lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v32);
      if ( v43 >= 8 )
        operator delete(v41[0]);
      v43 = 7;
      v42 = 0;
      LOWORD(v41[0]) = 0;
      if ( v45 >= 8 )
        operator delete(Src[0]);
      return v30;
    }
  }
  else
  {
    v27 = (const char *)v41;
    if ( v43 >= 8 )
      v27 = v41[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v26,
      (int)"Failed while trying to take ownership of package custom data directory '%ws'",
      v27);
    if ( v23 )
      CoTaskMemFree(v23);
    v33 = 0;
    lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(v32);
    if ( v43 >= 8 )
      operator delete(v41[0]);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( v45 >= 8 )
      operator delete(Src[0]);
    return (unsigned int)v26;
  }
}

```

## disassembly

```asm
0x180039edc  mov     r11, rsp
0x180039edf  push    rbx
0x180039ee0  push    rsi
0x180039ee1  push    rdi
0x180039ee2  push    r12
0x180039ee4  push    r13
0x180039ee6  push    r14
0x180039ee8  push    r15
0x180039eea  sub     rsp, 100h
0x180039ef1  mov     rax, cs:__security_cookie
0x180039ef8  xor     rax, rsp
0x180039efb  mov     [rsp+138h+var_40], rax
0x180039f03  mov     r9, r8
0x180039f06  mov     rbx, rdx
0x180039f09  mov     r14, rcx
0x180039f0c  mov     r13d, 7
0x180039f12  mov     [rsp+138h+var_C8], r13
0x180039f17  xor     r15d, r15d
0x180039f1a  mov     [rsp+138h+var_D0], r15
0x180039f1f  mov     [rsp+138h+var_E0], r15w
0x180039f25  mov     [r11-0A8h], r13
0x180039f2c  mov     [r11-0B0h], r15
0x180039f33  mov     [rsp+138h+var_C0], r15w
0x180039f39  mov     [rsp+138h+var_E8], r15
0x180039f3e  mov     [r11-68h], r13
0x180039f42  mov     [r11-70h], r15
0x180039f46  mov     [r11-80h], r15w
0x180039f4b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039f4f  cmp     [r8], r15w
0x180039f53  jnz     short loc_180039F5A
0x180039f55  mov     r8d, r15d
0x180039f58  jmp     short loc_180039F67
0x180039f5a  mov     r8, rsi
0x180039f5d  inc     r8
0x180039f60  cmp     [r9+r8*2], r15w
0x180039f65  jnz     short loc_180039F5D
0x180039f67  mov     rdx, r9; Src
0x180039f6a  lea     rcx, [rsp+138h+Src]; void *
0x180039f72  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180039f77  mov     r8, r15
0x180039f7a  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180039f82  setnz   r8b
0x180039f86  lea     rdx, pszSrc; "\\"
0x180039f8d  lea     rcx, [rsp+138h+Src]; Src
0x180039f95  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180039f9a  cmp     [rbx], r15w
0x180039f9e  jnz     short loc_180039FA5
0x180039fa0  mov     r8, r15
0x180039fa3  jmp     short loc_180039FB2
0x180039fa5  mov     r8, rsi
0x180039fa8  inc     r8
0x180039fab  cmp     [rbx+r8*2], r15w
0x180039fb0  jnz     short loc_180039FA8
0x180039fb2  mov     rdx, rbx; void *
0x180039fb5  lea     rcx, [rsp+138h+Src]; Src
0x180039fbd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180039fc2  mov     [rsp+138h+var_88], r13
0x180039fca  mov     [rsp+138h+var_90], r15
0x180039fd2  mov     word ptr [rsp+138h+var_A0], r15w
0x180039fdb  mov     r9, rsi
0x180039fde  xor     r8d, r8d
0x180039fe1  lea     rdx, [rsp+138h+Src]
0x180039fe9  lea     rcx, [rsp+138h+var_A0]; void *
0x180039ff1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180039ff6  nop
0x180039ff7  lea     rdx, aMicrosoftSyste; "\\microsoft.system.package.metadata"
0x180039ffe  cmp     word ptr cs:aMicrosoftSyste, r15w; "\\microsoft.system.package.metadata"
0x18003a006  jnz     short loc_18003A00D
0x18003a008  mov     r8, r15
0x18003a00b  jmp     short loc_18003A01A
0x18003a00d  mov     r8, rsi
0x18003a010  inc     r8
0x18003a013  cmp     [rdx+r8*2], r15w
0x18003a018  jnz     short loc_18003A010
0x18003a01a  lea     rcx, [rsp+138h+var_A0]; Src
0x18003a022  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003a027  lea     rax, [rsp+138h+var_E8]
0x18003a02c  mov     [rsp+138h+var_100], rax
0x18003a031  lea     rax, [rsp+138h+var_A0]
0x18003a039  mov     [rsp+138h+var_F8], rax
0x18003a03e  mov     [rsp+138h+var_F0], 1
0x18003a043  lea     rcx, [rsp+138h+Src]
0x18003a04b  mov     r12d, 8
0x18003a051  cmp     [rsp+138h+var_68], r12
0x18003a059  cmovnb  rcx, [rsp+138h+Src]
0x18003a062  call    DirectoryExists
0x18003a067  test    eax, eax
0x18003a069  jnz     loc_18003A110
0x18003a06f  lea     rax, [rsp+138h+Src]
0x18003a077  cmp     [rsp+138h+var_68], r12
0x18003a07f  cmovnb  rax, [rsp+138h+Src]
0x18003a088  mov     rcx, [rsp+138h]; this
0x18003a090  mov     [rsp+138h+var_118], rax; char *
0x18003a095  lea     r9, aFailedWhileVer_0; "Failed while verifying directory '%ws' "...
0x18003a09c  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a0a3  mov     edx, 41Ah; void *
0x18003a0a8  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003a0ad  mov     ebx, eax
0x18003a0af  mov     [rsp+138h+var_F0], r15b
0x18003a0b4  lea     rcx, [rsp+138h+var_100]
0x18003a0b9  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003a0be  nop
0x18003a0bf  cmp     [rsp+138h+var_88], r12
0x18003a0c7  jb      short loc_18003A0D7
0x18003a0c9  mov     rcx, [rsp+138h+var_A0]
0x18003a0d1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a0d7  mov     [rsp+138h+var_88], r13
0x18003a0df  mov     [rsp+138h+var_90], r15
0x18003a0e7  mov     word ptr [rsp+138h+var_A0], r15w
0x18003a0f0  cmp     [rsp+138h+var_68], r12
0x18003a0f8  jb      short loc_18003A109
0x18003a0fa  mov     rcx, [rsp+138h+Src]
0x18003a102  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a108  nop
0x18003a109  mov     eax, ebx
0x18003a10b  jmp     loc_18003A64E
0x18003a110  lea     rbx, [rsp+138h+var_A0]
0x18003a118  cmp     [rsp+138h+var_88], r12
0x18003a120  cmovnb  rbx, [rsp+138h+var_A0]
0x18003a129  mov     rcx, rbx
0x18003a12c  call    DirectoryExists
0x18003a131  test    eax, eax
0x18003a133  jnz     loc_18003A2AD
0x18003a139  call    cs:__imp_GetLastError
0x18003a13f  test    eax, eax
0x18003a141  jle     short loc_18003A14B
0x18003a143  movzx   eax, ax
0x18003a146  or      eax, 80070000h
0x18003a14b  mov     edi, r15d
0x18003a14e  cmp     eax, 80070003h
0x18003a153  cmovnz  edi, eax
0x18003a156  test    edi, edi
0x18003a158  jns     short loc_18003A189
0x18003a15a  mov     rcx, [rsp+138h]; this
0x18003a162  mov     [rsp+138h+var_110], rbx; char *
0x18003a167  lea     rax, aFailedWhileTry_2; "Failed while trying to determine whethe"...
0x18003a16e  mov     [rsp+138h+var_118], rax; int
0x18003a173  mov     r9d, edi; char *
0x18003a176  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a17d  mov     edx, 3D7h; void *
0x18003a182  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a187  jmp     short loc_18003A205
0x18003a189  mov     rcx, rbx
0x18003a18c  call    CreatePath
0x18003a191  test    eax, eax
0x18003a193  jnz     short loc_18003A1A3
0x18003a195  mov     edx, 3DDh
0x18003a19a  lea     r9, aFailedWhileTry_1; "Failed while trying to create custom da"...
0x18003a1a1  jmp     short loc_18003A1E2
0x18003a1a3  xor     edx, edx
0x18003a1a5  mov     rcx, rbx; unsigned __int16 *
0x18003a1a8  call    PrepareUnicodePathEx
0x18003a1ad  test    rax, rax
0x18003a1b0  jnz     short loc_18003A1C0
0x18003a1b2  mov     edx, 3E4h
0x18003a1b7  lea     r9, aFailedWhileCon; "Failed while constructing path to custo"...
0x18003a1be  jmp     short loc_18003A1E2
0x18003a1c0  mov     edx, 6; dwFileAttributes
0x18003a1c5  mov     rcx, rax; lpFileName
0x18003a1c8  call    cs:__imp_SetFileAttributesW
0x18003a1ce  test    eax, eax
0x18003a1d0  jnz     loc_18003A2AD
0x18003a1d6  mov     edx, 3E9h; void *
0x18003a1db  lea     r9, aFailedWhileSet_2; "Failed while setting attributes to cust"...
0x18003a1e2  mov     rcx, [rsp+138h]; this
0x18003a1ea  mov     [rsp+138h+var_118], rbx; char *
0x18003a1ef  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a1f6  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003a1fb  mov     edi, eax
0x18003a1fd  test    eax, eax
0x18003a1ff  jns     loc_18003A2AD
0x18003a205  lea     rax, [rsp+138h+var_A0]
0x18003a20d  cmp     [rsp+138h+var_88], r12
0x18003a215  cmovnb  rax, [rsp+138h+var_A0]
0x18003a21e  mov     rcx, [rsp+138h]; this
0x18003a226  mov     [rsp+138h+var_110], rax; char *
0x18003a22b  lea     rax, aFailedWhileTry_3; "Failed while trying to ensure custom da"...
0x18003a232  mov     [rsp+138h+var_118], rax; int
0x18003a237  mov     r9d, edi; char *
0x18003a23a  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a241  mov     edx, 41Eh; void *
0x18003a246  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a24b  nop
0x18003a24c  mov     [rsp+138h+var_F0], r15b
0x18003a251  lea     rcx, [rsp+138h+var_100]
0x18003a256  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003a25b  nop
0x18003a25c  cmp     [rsp+138h+var_88], r12
0x18003a264  jb      short loc_18003A274
0x18003a266  mov     rcx, [rsp+138h+var_A0]
0x18003a26e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a274  mov     [rsp+138h+var_88], r13
0x18003a27c  mov     [rsp+138h+var_90], r15
0x18003a284  mov     word ptr [rsp+138h+var_A0], r15w
0x18003a28d  cmp     [rsp+138h+var_68], r12
0x18003a295  jb      short loc_18003A2A6
0x18003a297  mov     rcx, [rsp+138h+Src]
0x18003a29f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a2a5  nop
0x18003a2a6  mov     eax, edi
0x18003a2a8  jmp     loc_18003A64E
0x18003a2ad  mov     [rsp+138h+pv], r15
0x18003a2b2  lea     r8, [rsp+138h+var_A0]
0x18003a2ba  cmp     [rsp+138h+var_88], r12
0x18003a2c2  cmovnb  r8, [rsp+138h+var_A0]
0x18003a2cb  lea     rdx, aAnAttemptToObt_0; "An attempt to obtain ownership on the r"...
0x18003a2d2  lea     rcx, [rsp+138h+pv]
0x18003a2d7  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003a2dc  mov     rcx, [rsp+138h]; this
0x18003a2e4  test    eax, eax
0x18003a2e6  jns     short loc_18003A2FC
0x18003a2e8  mov     r9d, eax; char *
0x18003a2eb  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a2f2  mov     edx, 425h; void *
0x18003a2f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a2fc  mov     dword ptr [rsp+138h+var_110], r15d
0x18003a301  mov     dword ptr [rsp+138h+var_118], 2; int
0x18003a309  mov     edi, 42Dh
0x18003a30e  mov     r9d, edi
0x18003a311  lea     r8, aMsixpackagePro_25; "MsixPackage::Provisioning::Library::Msi"...
0x18003a318  lea     rdx, aOnecoreAdminAp_14; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a31f  mov     rbx, [rsp+138h+pv]
0x18003a324  mov     rcx, rbx
0x18003a327  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003a32c  mov     rcx, [rsp+138h]; this
0x18003a334  test    eax, eax
0x18003a336  jns     short loc_18003A349
0x18003a338  mov     r9d, eax; char *
0x18003a33b  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a342  mov     edx, edi; void *
0x18003a344  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a349  lea     rcx, [rsp+138h+var_A0]
0x18003a351  cmp     [rsp+138h+var_88], r12
0x18003a359  cmovnb  rcx, [rsp+138h+var_A0]
0x18003a362  lea     r8, [rsp+138h+var_E8]
0x18003a367  mov     edx, 1
0x18003a36c  call    cs:__imp_TakeOwnershipOnFolder
0x18003a372  mov     edi, eax
0x18003a374  test    eax, eax
0x18003a376  jns     loc_18003A433
0x18003a37c  lea     rdx, [rsp+138h+var_A0]
0x18003a384  cmp     [rsp+138h+var_88], r12
0x18003a38c  cmovnb  rdx, [rsp+138h+var_A0]
0x18003a395  mov     rcx, [rsp+138h]; this
0x18003a39d  mov     [rsp+138h+var_110], rdx; char *
0x18003a3a2  lea     rax, aFailedWhileTry_4; "Failed while trying to take ownership o"...
0x18003a3a9  mov     [rsp+138h+var_118], rax; int
0x18003a3ae  mov     r9d, edi; char *
0x18003a3b1  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a3b8  mov     edx, 434h; void *
0x18003a3bd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a3c2  nop
0x18003a3c3  test    rbx, rbx
0x18003a3c6  jz      short loc_18003A3D2
0x18003a3c8  mov     rcx, rbx; pv
0x18003a3cb  call    cs:__imp_CoTaskMemFree
0x18003a3d1  nop
0x18003a3d2  mov     [rsp+138h+var_F0], r15b
0x18003a3d7  lea     rcx, [rsp+138h+var_100]
0x18003a3dc  call    _lambda_374c045654eb315feffd7d269a1c6ea2___operator__
0x18003a3e1  nop
0x18003a3e2  cmp     [rsp+138h+var_88], r12
0x18003a3ea  jb      short loc_18003A3FA
0x18003a3ec  mov     rcx, [rsp+138h+var_A0]
0x18003a3f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a3fa  mov     [rsp+138h+var_88], r13
0x18003a402  mov     [rsp+138h+var_90], r15
0x18003a40a  mov     word ptr [rsp+138h+var_A0], r15w
0x18003a413  cmp     [rsp+138h+var_68], r12
0x18003a41b  jb      short loc_18003A42C
0x18003a41d  mov     rcx, [rsp+138h+Src]
0x18003a425  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a42b  nop
0x18003a42c  mov     eax, edi
0x18003a42e  jmp     loc_18003A64E
0x18003a433  mov     [rsp+138h+var_48], r13
0x18003a43b  mov     [rsp+138h+var_50], r15
0x18003a443  mov     word ptr [rsp+138h+var_60], r15w
0x18003a44c  mov     r9, rsi
0x18003a44f  xor     r8d, r8d
0x18003a452  lea     rdx, [rsp+138h+var_A0]
0x18003a45a  lea     rcx, [rsp+138h+var_60]; void *
0x18003a462  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003a467  lea     rdx, aCustomData; "\\Custom.data"
0x18003a46e  cmp     word ptr cs:aCustomData, r15w; "\\Custom.data"
0x18003a476  jnz     short loc_18003A47D
0x18003a478  mov     rsi, r15
0x18003a47b  jmp     short loc_18003A487
0x18003a47d  inc     rsi
0x18003a480  cmp     [rdx+rsi*2], r15w
0x18003a485  jnz     short loc_18003A47D
0x18003a487  mov     r8, rsi
0x18003a48a  lea     rcx, [rsp+138h+var_60]; Src
0x18003a492  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003a497  lea     rdx, [rsp+138h+var_60]
0x18003a49f  cmp     [rsp+138h+var_48], r12
0x18003a4a7  cmovnb  rdx, [rsp+138h+var_60]
0x18003a4b0  mov     [rsp+138h+var_118], r15
0x18003a4b5  xor     r9d, r9d
0x18003a4b8  xor     r8d, r8d
  ... truncated ...
```
