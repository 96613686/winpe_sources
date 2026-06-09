# MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)

- ea: `0x18003bf94`
- end: `0x18003c40b`
- name: `?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `1143`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032f28`
- `0x180035260`
- `0x18003925c`
- `0x18003e128`

## callees

- `0x18001bf0c`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e60`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003b764`
- `0x18003bf94`
- `0x180040400`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003c29a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c37f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c3c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c29a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c37f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003c3c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c3b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c007`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003c007`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003c328`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003c328`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003c22f`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003c22f`

## string_xrefs

- `0x18003c065`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c0b4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c11a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c1b9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c209`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c26c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c350`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c091`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c1e6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003c199`: `An attempt to obtain ownership on the root folder %ws`
- `0x18003c10b`: `Failed to close writer on file %ws.`
- `0x18003c08a`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges`
- `0x18003c1df`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges`
- `0x18003c045`: `Sharing violation while attempting to write %ws.Provision XML file not updated.`
- `0x18003c349`: `Failed while copying file %ws`
- `0x18003c2ed`: `AppxProvisioning.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  int v4; // eax
  void *v5; // rbx
  int v6; // eax
  const char *v7; // r9
  __int64 result; // rax
  char *v9; // rdi
  char *v10; // rdx
  unsigned __int64 v11; // r8
  LPCWSTR *v12; // r8
  int v13; // eax
  void *v14; // rbx
  int v15; // eax
  LPCWSTR *v16; // rcx
  int v17; // esi
  LPCWSTR *v18; // rdx
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rdi
  const WCHAR *v21; // rcx
  unsigned int LastErrorMsg; // edi
  LPVOID pv; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-60h] BYREF
  char v25; // [rsp+48h] [rbp-50h]
  __int64 v26; // [rsp+50h] [rbp-48h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v28; // [rsp+68h] [rbp-30h]
  unsigned __int64 v29; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v26 = 0;
    v24[0] = this;
    v24[1] = &v26;
    v25 = 1;
    if ( !*((_QWORD *)this + 91) )
    {
LABEL_12:
      v25 = 0;
      lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v24);
      return 0;
    }
    v2 = *((_QWORD *)this + 90);
    *((_QWORD *)this + 90) = 0;
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    Sleep(0x3E8u);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 91) + 40LL))(*((_QWORD *)this + 91));
    if ( v3 == -2147024864 )
    {
      pv = 0;
      v4 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             (char *)&pv,
             L"Sharing violation while attempting to write %ws.Provision XML file not updated.");
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19D,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v4);
      v5 = pv;
      v6 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
             pv,
             L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
             L"MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges",
             422);
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A6,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v6);
      if ( v5 )
        CoTaskMemFree(v5);
      goto LABEL_12;
    }
    if ( v3 >= 0 )
    {
      v29 = 7;
      v28 = 0;
      LOWORD(lpNewFileName[0]) = 0;
      v10 = (char *)*((_QWORD *)this + 72);
      if ( *(_WORD *)v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
      }
      else
      {
        v11 = 0;
      }
      std::wstring::assign(lpNewFileName, v10, v11);
      pv = 0;
      v12 = lpNewFileName;
      if ( v29 >= 8 )
        v12 = (LPCWSTR *)lpNewFileName[0];
      v13 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&pv,
              L"An attempt to obtain ownership on the root folder %ws",
              v12);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B6,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v13);
      v14 = pv;
      v15 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              pv,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
              L"MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges",
              446);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1BE,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v15);
      v16 = lpNewFileName;
      if ( v29 >= 8 )
        v16 = (LPCWSTR *)lpNewFileName[0];
      v17 = TakeOwnershipOnFolder(v16, 0, &v26);
      if ( v17 >= 0 )
      {
        std::wstring::append(lpNewFileName, (char *)L"\\", pszSrc[0] != 0);
        std::wstring::append(lpNewFileName, (char *)L"AppxProvisioning.xml", 0x14u);
        v19 = (const WCHAR *)lpNewFileName;
        if ( v29 >= 8 )
          v19 = lpNewFileName[0];
        v20 = (const WCHAR *)((char *)this + 688);
        if ( *((_QWORD *)v20 + 3) < 8u )
          v21 = v20;
        else
          v21 = *(const WCHAR **)v20;
        if ( CopyFileW(v21, v19, 0) )
        {
          if ( v14 )
            CoTaskMemFree(v14);
          if ( v29 >= 8 )
            operator delete((void *)lpNewFileName[0]);
          goto LABEL_12;
        }
        if ( *((_QWORD *)v20 + 3) >= 8u )
          v20 = *(const WCHAR **)v20;
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x1C8,
                         (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
                         "Failed while copying file %ws",
                         (const char *)v20,
                         0);
        if ( v14 )
          CoTaskMemFree(v14);
        if ( v29 >= 8 )
          operator delete((void *)lpNewFileName[0]);
        v29 = 7;
        v28 = 0;
        LOWORD(lpNewFileName[0]) = 0;
        v25 = 0;
        lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v24);
        result = LastErrorMsg;
      }
      else
      {
        v18 = lpNewFileName;
        if ( v29 >= 8 )
          v18 = (LPCWSTR *)lpNewFileName[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1C1,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed while trying to take ownership of '%ws'",
          (const char *)v18);
        if ( v14 )
          CoTaskMemFree(v14);
        if ( v29 >= 8 )
          operator delete((void *)lpNewFileName[0]);
        v29 = 7;
        v28 = 0;
        LOWORD(lpNewFileName[0]) = 0;
        v25 = 0;
        lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v24);
        result = (unsigned int)v17;
      }
    }
    else
    {
      v9 = (char *)this + 688;
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(char **)v9;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v3,
        (int)"Failed to close writer on file %ws.",
        v9);
      v25 = 0;
      lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v24);
      result = (unsigned int)v3;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CD,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18003bf94  mov     r11, rsp
0x18003bf97  mov     [r11+10h], rbx
0x18003bf9b  mov     [r11+18h], rsi
0x18003bf9f  push    rdi
0x18003bfa0  push    r14
0x18003bfa2  push    r15
0x18003bfa4  sub     rsp, 80h
0x18003bfab  mov     rax, cs:__security_cookie
0x18003bfb2  xor     rax, rsp
0x18003bfb5  mov     [rsp+98h+var_20], rax
0x18003bfba  mov     rdi, rcx
0x18003bfbd  xor     r14d, r14d
0x18003bfc0  mov     [r11-48h], r14
0x18003bfc4  mov     [r11-60h], rcx
0x18003bfc8  lea     rax, [r11-48h]
0x18003bfcc  mov     [r11-58h], rax
0x18003bfd0  mov     [rsp+98h+var_50], 1
0x18003bfd5  cmp     [rcx+2D8h], r14
0x18003bfdc  jz      loc_18003C3CC
0x18003bfe2  mov     rcx, [rcx+2D0h]
0x18003bfe9  mov     [rdi+2D0h], r14
0x18003bff0  test    rcx, rcx
0x18003bff3  jz      short loc_18003C002
0x18003bff5  mov     rax, [rcx]
0x18003bff8  mov     rax, [rax+10h]
0x18003bffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c001  nop
0x18003c002  mov     ecx, 3E8h; dwMilliseconds
0x18003c007  call    cs:__imp_Sleep
0x18003c00d  mov     rcx, [rdi+2D8h]
0x18003c014  mov     rax, [rcx]
0x18003c017  mov     rax, [rax+28h]
0x18003c01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c020  mov     ebx, eax
0x18003c022  mov     esi, 80070020h
0x18003c027  cmp     eax, esi
0x18003c029  jnz     loc_18003C0E9
0x18003c02f  mov     [rsp+98h+pv], r14
0x18003c034  lea     r8, [rdi+2B0h]
0x18003c03b  cmp     qword ptr [r8+18h], 8
0x18003c040  jb      short loc_18003C045
0x18003c042  mov     r8, [r8]
0x18003c045  lea     rdx, aSharingViolati; "Sharing violation while attempting to w"...
0x18003c04c  lea     rcx, [rsp+98h+pv]
0x18003c051  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003c056  mov     rcx, [rsp+98h]; this
0x18003c05e  test    eax, eax
0x18003c060  jns     short loc_18003C076
0x18003c062  mov     r9d, eax; char *
0x18003c065  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c06c  mov     edx, 19Dh; void *
0x18003c071  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c076  mov     dword ptr [rsp+98h+var_70], esi
0x18003c07a  mov     dword ptr [rsp+98h+var_78], 2; int
0x18003c082  mov     edi, 1A6h
0x18003c087  mov     r9d, edi
0x18003c08a  lea     r8, aMsixpackagePro_3; "MsixPackage::Provisioning::Library::Msi"...
0x18003c091  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c098  mov     rbx, [rsp+98h+pv]
0x18003c09d  mov     rcx, rbx
0x18003c0a0  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003c0a5  mov     rcx, [rsp+98h]; this
0x18003c0ad  test    eax, eax
0x18003c0af  jns     short loc_18003C0C3
0x18003c0b1  mov     r9d, eax; char *
0x18003c0b4  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c0bb  mov     edx, edi; void *
0x18003c0bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c0c2  nop
0x18003c0c3  test    rbx, rbx
0x18003c0c6  jz      short loc_18003C0D2
0x18003c0c8  mov     rcx, rbx; pv
0x18003c0cb  call    cs:__imp_CoTaskMemFree
0x18003c0d1  nop
0x18003c0d2  mov     [rsp+98h+var_50], r14b
0x18003c0d7  lea     rcx, [rsp+98h+var_60]
0x18003c0dc  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003c0e1  nop
0x18003c0e2  xor     eax, eax
0x18003c0e4  jmp     loc_18003C3E4
0x18003c0e9  test    ebx, ebx
0x18003c0eb  jns     short loc_18003C143
0x18003c0ed  add     rdi, 2B0h
0x18003c0f4  cmp     qword ptr [rdi+18h], 8
0x18003c0f9  jb      short loc_18003C0FE
0x18003c0fb  mov     rdi, [rdi]
0x18003c0fe  mov     rcx, [rsp+98h]; this
0x18003c106  mov     [rsp+98h+var_70], rdi; char *
0x18003c10b  lea     rax, aFailedToCloseW; "Failed to close writer on file %ws."
0x18003c112  mov     [rsp+98h+var_78], rax; int
0x18003c117  mov     r9d, ebx; char *
0x18003c11a  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c121  mov     edx, 1ABh; void *
0x18003c126  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c12b  nop
0x18003c12c  mov     [rsp+98h+var_50], r14b
0x18003c131  lea     rcx, [rsp+98h+var_60]
0x18003c136  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003c13b  nop
0x18003c13c  mov     eax, ebx
0x18003c13e  jmp     loc_18003C3E4
0x18003c143  mov     r15d, 7
0x18003c149  mov     [rsp+98h+var_28], r15
0x18003c14e  mov     [rsp+98h+var_30], r14
0x18003c153  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003c159  mov     rdx, [rdi+240h]; Src
0x18003c160  cmp     [rdx], r14w
0x18003c164  jnz     short loc_18003C16B
0x18003c166  mov     r8, r14
0x18003c169  jmp     short loc_18003C179
0x18003c16b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003c16f  inc     r8
0x18003c172  cmp     [rdx+r8*2], r14w
0x18003c177  jnz     short loc_18003C16F
0x18003c179  lea     rcx, [rsp+98h+lpNewFileName]; void *
0x18003c17e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003c183  mov     [rsp+98h+pv], r14
0x18003c188  lea     r8, [rsp+98h+lpNewFileName]
0x18003c18d  cmp     [rsp+98h+var_28], 8
0x18003c193  cmovnb  r8, [rsp+98h+lpNewFileName]
0x18003c199  lea     rdx, aAnAttemptToObt; "An attempt to obtain ownership on the r"...
0x18003c1a0  lea     rcx, [rsp+98h+pv]
0x18003c1a5  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003c1aa  mov     rcx, [rsp+98h]; this
0x18003c1b2  test    eax, eax
0x18003c1b4  jns     short loc_18003C1CA
0x18003c1b6  mov     r9d, eax; char *
0x18003c1b9  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c1c0  mov     edx, 1B6h; void *
0x18003c1c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c1ca  mov     dword ptr [rsp+98h+var_70], r14d
0x18003c1cf  mov     dword ptr [rsp+98h+var_78], 2; int
0x18003c1d7  mov     esi, 1BEh
0x18003c1dc  mov     r9d, esi
0x18003c1df  lea     r8, aMsixpackagePro_3; "MsixPackage::Provisioning::Library::Msi"...
0x18003c1e6  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c1ed  mov     rbx, [rsp+98h+pv]
0x18003c1f2  mov     rcx, rbx
0x18003c1f5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003c1fa  mov     rcx, [rsp+98h]; this
0x18003c202  test    eax, eax
0x18003c204  jns     short loc_18003C217
0x18003c206  mov     r9d, eax; char *
0x18003c209  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c210  mov     edx, esi; void *
0x18003c212  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c217  lea     rcx, [rsp+98h+lpNewFileName]
0x18003c21c  cmp     [rsp+98h+var_28], 8
0x18003c222  cmovnb  rcx, [rsp+98h+lpNewFileName]
0x18003c228  lea     r8, [rsp+98h+var_48]
0x18003c22d  xor     edx, edx
0x18003c22f  call    cs:__imp_TakeOwnershipOnFolder
0x18003c235  mov     esi, eax
0x18003c237  test    eax, eax
0x18003c239  jns     loc_18003C2C7
0x18003c23f  lea     rdx, [rsp+98h+lpNewFileName]
0x18003c244  cmp     [rsp+98h+var_28], 8
0x18003c24a  cmovnb  rdx, [rsp+98h+lpNewFileName]
0x18003c250  mov     rcx, [rsp+98h]; this
0x18003c258  mov     [rsp+98h+var_70], rdx; char *
0x18003c25d  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x18003c264  mov     [rsp+98h+var_78], rax; int
0x18003c269  mov     r9d, esi; char *
0x18003c26c  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c273  mov     edx, 1C1h; void *
0x18003c278  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c27d  nop
0x18003c27e  test    rbx, rbx
0x18003c281  jz      short loc_18003C28D
0x18003c283  mov     rcx, rbx; pv
0x18003c286  call    cs:__imp_CoTaskMemFree
0x18003c28c  nop
0x18003c28d  cmp     [rsp+98h+var_28], 8
0x18003c293  jb      short loc_18003C2A0
0x18003c295  mov     rcx, [rsp+98h+lpNewFileName]
0x18003c29a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c2a0  mov     [rsp+98h+var_28], r15
0x18003c2a5  mov     [rsp+98h+var_30], r14
0x18003c2aa  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003c2b0  mov     [rsp+98h+var_50], r14b
0x18003c2b5  lea     rcx, [rsp+98h+var_60]
0x18003c2ba  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003c2bf  nop
0x18003c2c0  mov     eax, esi
0x18003c2c2  jmp     loc_18003C3E4
0x18003c2c7  mov     r8, r14
0x18003c2ca  cmp     word ptr cs:pszSrc, r14w; "\\"
0x18003c2d2  setnz   r8b
0x18003c2d6  lea     rdx, pszSrc; "\\"
0x18003c2dd  lea     rcx, [rsp+98h+lpNewFileName]; Src
0x18003c2e2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003c2e7  mov     r8d, 14h
0x18003c2ed  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18003c2f4  lea     rcx, [rsp+98h+lpNewFileName]; Src
0x18003c2f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003c2fe  lea     rdx, [rsp+98h+lpNewFileName]
0x18003c303  cmp     [rsp+98h+var_28], 8
0x18003c309  cmovnb  rdx, [rsp+98h+lpNewFileName]; lpNewFileName
0x18003c30f  add     rdi, 2B0h
0x18003c316  cmp     qword ptr [rdi+18h], 8
0x18003c31b  jb      short loc_18003C322
0x18003c31d  mov     rcx, [rdi]
0x18003c320  jmp     short loc_18003C325
0x18003c322  mov     rcx, rdi; lpExistingFileName
0x18003c325  xor     r8d, r8d; bFailIfExists
0x18003c328  call    cs:__imp_CopyFileW
0x18003c32e  test    eax, eax
0x18003c330  jnz     short loc_18003C3A9
0x18003c332  cmp     qword ptr [rdi+18h], 8
0x18003c337  jb      short loc_18003C33C
0x18003c339  mov     rdi, [rdi]
0x18003c33c  mov     rcx, [rsp+98h]; this
0x18003c344  mov     [rsp+98h+var_78], rdi; char *
0x18003c349  lea     r9, aFailedWhileCop_0; "Failed while copying file %ws"
0x18003c350  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c357  mov     edx, 1C8h; void *
0x18003c35c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003c361  mov     edi, eax
0x18003c363  test    rbx, rbx
0x18003c366  jz      short loc_18003C372
0x18003c368  mov     rcx, rbx; pv
0x18003c36b  call    cs:__imp_CoTaskMemFree
0x18003c371  nop
0x18003c372  cmp     [rsp+98h+var_28], 8
0x18003c378  jb      short loc_18003C385
0x18003c37a  mov     rcx, [rsp+98h+lpNewFileName]
0x18003c37f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c385  mov     [rsp+98h+var_28], r15
0x18003c38a  mov     [rsp+98h+var_30], r14
0x18003c38f  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003c395  mov     [rsp+98h+var_50], r14b
0x18003c39a  lea     rcx, [rsp+98h+var_60]
0x18003c39f  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003c3a4  nop
0x18003c3a5  mov     eax, edi
0x18003c3a7  jmp     short loc_18003C3E4
0x18003c3a9  test    rbx, rbx
0x18003c3ac  jz      short loc_18003C3B8
0x18003c3ae  mov     rcx, rbx; pv
0x18003c3b1  call    cs:__imp_CoTaskMemFree
0x18003c3b7  nop
0x18003c3b8  cmp     [rsp+98h+var_28], 8
0x18003c3be  jb      short loc_18003C3CC
0x18003c3c0  mov     rcx, [rsp+98h+lpNewFileName]
0x18003c3c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003c3cb  nop
0x18003c3cc  mov     [rsp+98h+var_50], r14b
0x18003c3d1  lea     rcx, [rsp+98h+var_60]
0x18003c3d6  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003c3db  nop
0x18003c3dc  xor     eax, eax
0x18003c3de  jmp     short loc_18003C3E4
0x18003c3e0  mov     eax, dword ptr [rsp+98h+pv]
0x18003c3e4  mov     rcx, [rsp+98h+var_20]
0x18003c3e9  xor     rcx, rsp; StackCookie
0x18003c3ec  call    __security_check_cookie
0x18003c3f1  lea     r11, [rsp+98h+var_18]
0x18003c3f9  mov     rbx, [r11+28h]
0x18003c3fd  mov     rsi, [r11+30h]
0x18003c401  mov     rsp, r11
0x18003c404  pop     r15
0x18003c406  pop     r14
0x18003c408  pop     rdi
0x18003c409  retn
```
