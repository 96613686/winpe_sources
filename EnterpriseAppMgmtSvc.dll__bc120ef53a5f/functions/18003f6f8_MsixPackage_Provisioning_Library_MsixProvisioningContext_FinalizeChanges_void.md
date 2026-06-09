# MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)

- ea: `0x18003f6f8`
- end: `0x18003fbaf`
- name: `?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `1207`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035f40`
- `0x18003856c`
- `0x18003c81c`
- `0x180041aa0`

## callees

- `0x18001d160`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4b0`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003ee78`
- `0x18003f6f8`
- `0x180043fb4`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa16`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb11`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb63`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa16`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb11`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fb63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fb49`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f76b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f76b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003faaa`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003faaa`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003f99f`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003f99f`

## string_xrefs

- `0x18003f7fb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f956`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f7cf`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f81e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f88a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f929`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f979`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f9e2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003fadc`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f7f4`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges`
- `0x18003f94f`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges`
- `0x18003f7af`: `Sharing violation while attempting to write %ws.Provision XML file not updated.`
- `0x18003fad5`: `Failed while copying file %ws`
- `0x18003f909`: `An attempt to obtain ownership on the root folder %ws`
- `0x18003f87b`: `Failed to close writer on file %ws.`
- `0x18003fa6f`: `AppxProvisioning.xml`

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
  _WORD *v10; // rdx
  __int64 v11; // r8
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
  int v23; // [rsp+20h] [rbp-78h]
  LPVOID pv; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v25[2]; // [rsp+38h] [rbp-60h] BYREF
  char v26; // [rsp+48h] [rbp-50h]
  __int64 v27; // [rsp+50h] [rbp-48h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v29; // [rsp+68h] [rbp-30h]
  unsigned __int64 v30; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v27 = 0;
    v25[0] = this;
    v25[1] = &v27;
    v26 = 1;
    if ( !*((_QWORD *)this + 91) )
    {
LABEL_12:
      v26 = 0;
      lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v25);
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
             &pv,
             L"Sharing violation while attempting to write %ws.Provision XML file not updated.");
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v4,
          v23);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v6,
          2);
      if ( v5 )
        CoTaskMemFree(v5);
      goto LABEL_12;
    }
    if ( v3 >= 0 )
    {
      v30 = 7;
      v29 = 0;
      LOWORD(lpNewFileName[0]) = 0;
      v10 = (_WORD *)*((_QWORD *)this + 72);
      if ( *v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
      }
      std::wstring::assign(lpNewFileName, v10);
      pv = 0;
      v12 = lpNewFileName;
      if ( v30 >= 8 )
        v12 = (LPCWSTR *)lpNewFileName[0];
      v13 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pv,
              L"An attempt to obtain ownership on the root folder %ws",
              v12);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v13,
          v23);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v15,
          2);
      v16 = lpNewFileName;
      if ( v30 >= 8 )
        v16 = (LPCWSTR *)lpNewFileName[0];
      v17 = TakeOwnershipOnFolder(v16, 0, &v27);
      if ( v17 >= 0 )
      {
        std::wstring::append(lpNewFileName, (void *)L"\\");
        std::wstring::append(lpNewFileName, L"AppxProvisioning.xml");
        v19 = (const WCHAR *)lpNewFileName;
        if ( v30 >= 8 )
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
          if ( v30 >= 8 )
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
        if ( v30 >= 8 )
          operator delete((void *)lpNewFileName[0]);
        v30 = 7;
        v29 = 0;
        LOWORD(lpNewFileName[0]) = 0;
        v26 = 0;
        lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v25);
        result = LastErrorMsg;
      }
      else
      {
        v18 = lpNewFileName;
        if ( v30 >= 8 )
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
        if ( v30 >= 8 )
          operator delete((void *)lpNewFileName[0]);
        v30 = 7;
        v29 = 0;
        LOWORD(lpNewFileName[0]) = 0;
        v26 = 0;
        lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v25);
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
      v26 = 0;
      lambda_44bd12cb1c037c219cc57119e5126287_::operator()(v25);
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
0x18003f6f8  mov     r11, rsp
0x18003f6fb  mov     [r11+10h], rbx
0x18003f6ff  mov     [r11+18h], rsi
0x18003f703  push    rdi
0x18003f704  push    r14
0x18003f706  push    r15
0x18003f708  sub     rsp, 80h
0x18003f70f  mov     rax, cs:__security_cookie
0x18003f716  xor     rax, rsp
0x18003f719  mov     [rsp+98h+var_20], rax
0x18003f71e  mov     rdi, rcx
0x18003f721  xor     r14d, r14d
0x18003f724  mov     [r11-48h], r14
0x18003f728  mov     [r11-60h], rcx
0x18003f72c  lea     rax, [r11-48h]
0x18003f730  mov     [r11-58h], rax
0x18003f734  mov     [rsp+98h+var_50], 1
0x18003f739  cmp     [rcx+2D8h], r14
0x18003f740  jz      loc_18003FB70
0x18003f746  mov     rcx, [rcx+2D0h]
0x18003f74d  mov     [rdi+2D0h], r14
0x18003f754  test    rcx, rcx
0x18003f757  jz      short loc_18003F766
0x18003f759  mov     rax, [rcx]
0x18003f75c  mov     rax, [rax+10h]
0x18003f760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f765  nop
0x18003f766  mov     ecx, 3E8h; dwMilliseconds
0x18003f76b  call    cs:__imp_Sleep
0x18003f772  nop     dword ptr [rax+rax+00h]
0x18003f777  mov     rcx, [rdi+2D8h]
0x18003f77e  mov     rax, [rcx]
0x18003f781  mov     rax, [rax+28h]
0x18003f785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f78a  mov     ebx, eax
0x18003f78c  mov     esi, 80070020h
0x18003f791  cmp     eax, esi
0x18003f793  jnz     loc_18003F859
0x18003f799  mov     [rsp+98h+pv], r14
0x18003f79e  lea     r8, [rdi+2B0h]
0x18003f7a5  cmp     qword ptr [r8+18h], 8
0x18003f7aa  jb      short loc_18003F7AF
0x18003f7ac  mov     r8, [r8]
0x18003f7af  lea     rdx, aSharingViolati; "Sharing violation while attempting to w"...
0x18003f7b6  lea     rcx, [rsp+98h+pv]
0x18003f7bb  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003f7c0  mov     rcx, [rsp+98h]; this
0x18003f7c8  test    eax, eax
0x18003f7ca  jns     short loc_18003F7E0
0x18003f7cc  mov     r9d, eax; char *
0x18003f7cf  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f7d6  mov     edx, 19Dh; void *
0x18003f7db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f7e0  mov     dword ptr [rsp+98h+var_70], esi
0x18003f7e4  mov     dword ptr [rsp+98h+var_78], 2; int
0x18003f7ec  mov     edi, 1A6h
0x18003f7f1  mov     r9d, edi
0x18003f7f4  lea     r8, aMsixpackagePro_3; "MsixPackage::Provisioning::Library::Msi"...
0x18003f7fb  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f802  mov     rbx, [rsp+98h+pv]
0x18003f807  mov     rcx, rbx
0x18003f80a  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003f80f  mov     rcx, [rsp+98h]; this
0x18003f817  test    eax, eax
0x18003f819  jns     short loc_18003F82D
0x18003f81b  mov     r9d, eax; char *
0x18003f81e  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f825  mov     edx, edi; void *
0x18003f827  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f82c  nop
0x18003f82d  test    rbx, rbx
0x18003f830  jz      short loc_18003F842
0x18003f832  mov     rcx, rbx; pv
0x18003f835  call    cs:__imp_CoTaskMemFree
0x18003f83c  nop     dword ptr [rax+rax+00h]
0x18003f841  nop
0x18003f842  mov     [rsp+98h+var_50], r14b
0x18003f847  lea     rcx, [rsp+98h+var_60]
0x18003f84c  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003f851  nop
0x18003f852  xor     eax, eax
0x18003f854  jmp     loc_18003FB88
0x18003f859  test    ebx, ebx
0x18003f85b  jns     short loc_18003F8B3
0x18003f85d  add     rdi, 2B0h
0x18003f864  cmp     qword ptr [rdi+18h], 8
0x18003f869  jb      short loc_18003F86E
0x18003f86b  mov     rdi, [rdi]
0x18003f86e  mov     rcx, [rsp+98h]; this
0x18003f876  mov     [rsp+98h+var_70], rdi; char *
0x18003f87b  lea     rax, aFailedToCloseW; "Failed to close writer on file %ws."
0x18003f882  mov     [rsp+98h+var_78], rax; int
0x18003f887  mov     r9d, ebx; char *
0x18003f88a  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f891  mov     edx, 1ABh; void *
0x18003f896  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f89b  nop
0x18003f89c  mov     [rsp+98h+var_50], r14b
0x18003f8a1  lea     rcx, [rsp+98h+var_60]
0x18003f8a6  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003f8ab  nop
0x18003f8ac  mov     eax, ebx
0x18003f8ae  jmp     loc_18003FB88
0x18003f8b3  mov     r15d, 7
0x18003f8b9  mov     [rsp+98h+var_28], r15
0x18003f8be  mov     [rsp+98h+var_30], r14
0x18003f8c3  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003f8c9  mov     rdx, [rdi+240h]; Src
0x18003f8d0  cmp     [rdx], r14w
0x18003f8d4  jnz     short loc_18003F8DB
0x18003f8d6  mov     r8, r14
0x18003f8d9  jmp     short loc_18003F8E9
0x18003f8db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f8df  inc     r8
0x18003f8e2  cmp     [rdx+r8*2], r14w
0x18003f8e7  jnz     short loc_18003F8DF
0x18003f8e9  lea     rcx, [rsp+98h+lpNewFileName]; void *
0x18003f8ee  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003f8f3  mov     [rsp+98h+pv], r14
0x18003f8f8  lea     r8, [rsp+98h+lpNewFileName]
0x18003f8fd  cmp     [rsp+98h+var_28], 8
0x18003f903  cmovnb  r8, [rsp+98h+lpNewFileName]
0x18003f909  lea     rdx, aAnAttemptToObt; "An attempt to obtain ownership on the r"...
0x18003f910  lea     rcx, [rsp+98h+pv]
0x18003f915  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003f91a  mov     rcx, [rsp+98h]; this
0x18003f922  test    eax, eax
0x18003f924  jns     short loc_18003F93A
0x18003f926  mov     r9d, eax; char *
0x18003f929  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f930  mov     edx, 1B6h; void *
0x18003f935  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f93a  mov     dword ptr [rsp+98h+var_70], r14d
0x18003f93f  mov     dword ptr [rsp+98h+var_78], 2; int
0x18003f947  mov     esi, 1BEh
0x18003f94c  mov     r9d, esi
0x18003f94f  lea     r8, aMsixpackagePro_3; "MsixPackage::Provisioning::Library::Msi"...
0x18003f956  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f95d  mov     rbx, [rsp+98h+pv]
0x18003f962  mov     rcx, rbx
0x18003f965  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003f96a  mov     rcx, [rsp+98h]; this
0x18003f972  test    eax, eax
0x18003f974  jns     short loc_18003F987
0x18003f976  mov     r9d, eax; char *
0x18003f979  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f980  mov     edx, esi; void *
0x18003f982  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f987  lea     rcx, [rsp+98h+lpNewFileName]
0x18003f98c  cmp     [rsp+98h+var_28], 8
0x18003f992  cmovnb  rcx, [rsp+98h+lpNewFileName]
0x18003f998  lea     r8, [rsp+98h+var_48]
0x18003f99d  xor     edx, edx
0x18003f99f  call    cs:__imp_TakeOwnershipOnFolder
0x18003f9a6  nop     dword ptr [rax+rax+00h]
0x18003f9ab  mov     esi, eax
0x18003f9ad  test    eax, eax
0x18003f9af  jns     loc_18003FA49
0x18003f9b5  lea     rdx, [rsp+98h+lpNewFileName]
0x18003f9ba  cmp     [rsp+98h+var_28], 8
0x18003f9c0  cmovnb  rdx, [rsp+98h+lpNewFileName]
0x18003f9c6  mov     rcx, [rsp+98h]; this
0x18003f9ce  mov     [rsp+98h+var_70], rdx; char *
0x18003f9d3  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x18003f9da  mov     [rsp+98h+var_78], rax; int
0x18003f9df  mov     r9d, esi; char *
0x18003f9e2  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f9e9  mov     edx, 1C1h; void *
0x18003f9ee  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f9f3  nop
0x18003f9f4  test    rbx, rbx
0x18003f9f7  jz      short loc_18003FA09
0x18003f9f9  mov     rcx, rbx; pv
0x18003f9fc  call    cs:__imp_CoTaskMemFree
0x18003fa03  nop     dword ptr [rax+rax+00h]
0x18003fa08  nop
0x18003fa09  cmp     [rsp+98h+var_28], 8
0x18003fa0f  jb      short loc_18003FA22
0x18003fa11  mov     rcx, [rsp+98h+lpNewFileName]
0x18003fa16  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fa1d  nop     dword ptr [rax+rax+00h]
0x18003fa22  mov     [rsp+98h+var_28], r15
0x18003fa27  mov     [rsp+98h+var_30], r14
0x18003fa2c  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003fa32  mov     [rsp+98h+var_50], r14b
0x18003fa37  lea     rcx, [rsp+98h+var_60]
0x18003fa3c  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003fa41  nop
0x18003fa42  mov     eax, esi
0x18003fa44  jmp     loc_18003FB88
0x18003fa49  mov     r8, r14
0x18003fa4c  cmp     word ptr cs:pszSrc, r14w; "\\"
0x18003fa54  setnz   r8b
0x18003fa58  lea     rdx, pszSrc; "\\"
0x18003fa5f  lea     rcx, [rsp+98h+lpNewFileName]; Src
0x18003fa64  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003fa69  mov     r8d, 14h
0x18003fa6f  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18003fa76  lea     rcx, [rsp+98h+lpNewFileName]; Src
0x18003fa7b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003fa80  lea     rdx, [rsp+98h+lpNewFileName]
0x18003fa85  cmp     [rsp+98h+var_28], 8
0x18003fa8b  cmovnb  rdx, [rsp+98h+lpNewFileName]; lpNewFileName
0x18003fa91  add     rdi, 2B0h
0x18003fa98  cmp     qword ptr [rdi+18h], 8
0x18003fa9d  jb      short loc_18003FAA4
0x18003fa9f  mov     rcx, [rdi]
0x18003faa2  jmp     short loc_18003FAA7
0x18003faa4  mov     rcx, rdi; lpExistingFileName
0x18003faa7  xor     r8d, r8d; bFailIfExists
0x18003faaa  call    cs:__imp_CopyFileW
0x18003fab1  nop     dword ptr [rax+rax+00h]
0x18003fab6  test    eax, eax
0x18003fab8  jnz     loc_18003FB41
0x18003fabe  cmp     qword ptr [rdi+18h], 8
0x18003fac3  jb      short loc_18003FAC8
0x18003fac5  mov     rdi, [rdi]
0x18003fac8  mov     rcx, [rsp+98h]; this
0x18003fad0  mov     [rsp+98h+var_78], rdi; char *
0x18003fad5  lea     r9, aFailedWhileCop_0; "Failed while copying file %ws"
0x18003fadc  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003fae3  mov     edx, 1C8h; void *
0x18003fae8  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003faed  mov     edi, eax
0x18003faef  test    rbx, rbx
0x18003faf2  jz      short loc_18003FB04
0x18003faf4  mov     rcx, rbx; pv
0x18003faf7  call    cs:__imp_CoTaskMemFree
0x18003fafe  nop     dword ptr [rax+rax+00h]
0x18003fb03  nop
0x18003fb04  cmp     [rsp+98h+var_28], 8
0x18003fb0a  jb      short loc_18003FB1D
0x18003fb0c  mov     rcx, [rsp+98h+lpNewFileName]
0x18003fb11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fb18  nop     dword ptr [rax+rax+00h]
0x18003fb1d  mov     [rsp+98h+var_28], r15
0x18003fb22  mov     [rsp+98h+var_30], r14
0x18003fb27  mov     word ptr [rsp+98h+lpNewFileName], r14w
0x18003fb2d  mov     [rsp+98h+var_50], r14b
0x18003fb32  lea     rcx, [rsp+98h+var_60]
0x18003fb37  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003fb3c  nop
0x18003fb3d  mov     eax, edi
0x18003fb3f  jmp     short loc_18003FB88
0x18003fb41  test    rbx, rbx
0x18003fb44  jz      short loc_18003FB56
0x18003fb46  mov     rcx, rbx; pv
0x18003fb49  call    cs:__imp_CoTaskMemFree
0x18003fb50  nop     dword ptr [rax+rax+00h]
0x18003fb55  nop
0x18003fb56  cmp     [rsp+98h+var_28], 8
0x18003fb5c  jb      short loc_18003FB70
0x18003fb5e  mov     rcx, [rsp+98h+lpNewFileName]
0x18003fb63  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fb6a  nop     dword ptr [rax+rax+00h]
0x18003fb6f  nop
0x18003fb70  mov     [rsp+98h+var_50], r14b
0x18003fb75  lea     rcx, [rsp+98h+var_60]
0x18003fb7a  call    _lambda_44bd12cb1c037c219cc57119e5126287___operator__
0x18003fb7f  nop
0x18003fb80  xor     eax, eax
0x18003fb82  jmp     short loc_18003FB88
0x18003fb84  mov     eax, dword ptr [rsp+98h+pv]
0x18003fb88  mov     rcx, [rsp+98h+var_20]
0x18003fb8d  xor     rcx, rsp; StackCookie
0x18003fb90  call    __security_check_cookie
0x18003fb95  lea     r11, [rsp+98h+var_18]
0x18003fb9d  mov     rbx, [r11+28h]
0x18003fba1  mov     rsi, [r11+30h]
0x18003fba5  mov     rsp, r11
0x18003fba8  pop     r15
0x18003fbaa  pop     r14
0x18003fbac  pop     rdi
0x18003fbad  retn
```
