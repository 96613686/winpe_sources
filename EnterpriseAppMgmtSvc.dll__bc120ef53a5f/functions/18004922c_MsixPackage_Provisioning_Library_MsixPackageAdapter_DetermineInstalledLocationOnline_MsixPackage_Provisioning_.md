# MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(MsixPackage::Provisioning::Library::MsixAdapterCollection *)

- ea: `0x18004922c`
- end: `0x18004965c`
- name: `?DetermineInstalledLocationOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAVMsixAdapterCollection@234@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, struct MsixPackage::Provisioning::Library::MsixAdapterCollection *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004922c`
- `0x18004d724`

## callees

- `0x18000d3dc`
- `0x18001d160`
- `0x18001d65c`
- `0x18003c2c0`
- `0x18003c350`
- `0x18003d4ec`
- `0x18004922c`
- `0x180049664`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800492d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800492d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004930c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004930c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800494ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800494ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800493d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800495f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004962d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800493d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800495f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004962d`

## string_xrefs

- `0x180049295`: `Failed to load AppxDeploymentClient.DLL.`
- `0x1800492a4`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004934a`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180049383`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x1800493b7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004942f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049474`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004954a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800495bf`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800493a8`: `Failed to get installed location of package '%ws'.`
- `0x180049462`: `Failed to get installed location of package '%ws' because it's not staged`
- `0x1800492ca`: `AppxGetPackageInstalledLocation`
- `0x18004933b`: `Unable to GetProcAddress 'AppxGetInstalledLocation'`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        struct MsixPackage::Provisioning::Library::MsixAdapterCollection *a2)
{
  __int64 v4; // r14
  const char *v5; // rdi
  char *v6; // r15
  int Dynamic; // eax
  unsigned int v8; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v11; // sf
  signed int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 result; // rax
  const unsigned __int16 *v16; // rdx
  int IsInstalled; // eax
  WCHAR *StringRawBuffer; // rax
  __int64 v19; // r8
  __int64 v20; // r15
  unsigned int i; // r14d
  int v22; // ebx
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v23; // rbx
  int v24; // eax
  unsigned int v25; // esi
  int v26; // [rsp+20h] [rbp-48h]
  char *v27; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v29; // [rsp+70h] [rbp+8h] BYREF
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  string = 0;
  v4 = *((_QWORD *)this + 2);
  WindowsDeleteString(0);
  string = 0;
  v5 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v6 = (char *)this + 48;
  else
    v6 = *(char **)v5;
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(v4 + 320);
  try
  {
    v8 = Dynamic;
    if ( Dynamic < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
        (const char *)(unsigned int)Dynamic,
        (int)"Failed to load AppxDeploymentClient.DLL.",
        v27);
LABEL_20:
      if ( *((_QWORD *)this + 9) >= 8u )
        v5 = *(const char **)v5;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x313,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)v8,
        (int)"Failed to get installed location of package '%ws'.",
        v5);
      if ( string )
        WindowsDeleteString(string);
      return v8;
    }
    ProcAddress = *(FARPROC *)(v4 + 400);
    if ( ProcAddress
      || (ProcAddress = GetProcAddress(*(HMODULE *)(v4 + 328), "AppxGetPackageInstalledLocation"),
          (*(_QWORD *)(v4 + 400) = ProcAddress) != 0) )
    {
      v13 = ((__int64 (__fastcall *)(char *, HSTRING *))ProcAddress)(v6, &string);
      v8 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x187,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)(unsigned int)v13,
          v26);
        goto LABEL_20;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError < 0;
      if ( LastError > 0 )
        v11 = 1;
      if ( !v11 )
      {
        v8 = -2147467259;
LABEL_17:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)v8,
          (int)"Unable to GetProcAddress 'AppxGetInstalledLocation'",
          v27);
        goto LABEL_20;
      }
      v12 = GetLastError();
      v8 = v12;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
        goto LABEL_17;
    }
    if ( string )
    {
      StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      if ( *StringRawBuffer )
      {
        v19 = -1;
        do
          ++v19;
        while ( StringRawBuffer[v19] );
      }
      std::wstring::assign((char *)this + 112, StringRawBuffer);
      if ( a2 && *((_DWORD *)this + 9) <= 1u )
      {
        v20 = (__int64)(*((_QWORD *)a2 + 3) - *((_QWORD *)a2 + 2)) >> 3;
        for ( i = 0; i < (unsigned int)v20; ++i )
        {
          v29 = 0;
          v22 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
                  a2,
                  i,
                  &v29);
          if ( v22 < 0 )
          {
            if ( *((_QWORD *)v5 + 3) >= 8u )
              v5 = *(const char **)v5;
            LODWORD(v27) = i;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x33B,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v22,
              (int)"Failed to obtain dependency package %d for package '%ws'",
              v27,
              v5);
            if ( v29 )
              (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v29 + 16LL))(v29);
            if ( string )
              WindowsDeleteString(string);
            return (unsigned int)v22;
          }
          v23 = v29;
          v24 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(v29, 0);
          v25 = v24;
          if ( v24 == -2147024809 )
          {
            if ( *((_DWORD *)v23 + 6) != 3 )
              goto LABEL_57;
          }
          else if ( v24 < 0 )
          {
LABEL_57:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x34F,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v24,
              v26);
            if ( v23 )
              (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v23 + 16LL))(v23);
            if ( string )
              WindowsDeleteString(string);
            return v25;
          }
          if ( v23 )
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
      if ( string )
        WindowsDeleteString(string);
      result = 0;
    }
    else
    {
      LODWORD(v29) = 0;
      if ( *((_QWORD *)this + 9) < 8u )
        v16 = (const unsigned __int16 *)((char *)this + 48);
      else
        v16 = *(const unsigned __int16 **)v5;
      IsInstalled = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(
                      (MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *)(*((_QWORD *)this + 2) + 320LL),
                      v16,
                      (int *)&v29);
      if ( IsInstalled < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x322,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)IsInstalled,
          v26);
      if ( (_DWORD)v29 )
        *((_DWORD *)this + 6) = 3;
      if ( *((_QWORD *)this + 9) >= 8u )
        v5 = *(const char **)v5;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x328,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)0x80070057LL,
        (int)"Failed to get installed location of package '%ws' because it's not staged",
        v5);
      if ( string )
        WindowsDeleteString(string);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x355,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18004922c  mov     rax, rsp
0x18004922f  mov     [rax+10h], rbx
0x180049233  mov     [rax+20h], rsi
0x180049237  push    rdi
0x180049238  push    r12
0x18004923a  push    r13
0x18004923c  push    r14
0x18004923e  push    r15
0x180049240  sub     rsp, 40h
0x180049244  mov     r13, rdx
0x180049247  mov     rsi, rcx
0x18004924a  xor     r12d, r12d
0x18004924d  mov     [rax+18h], r12
0x180049251  mov     r14, [rcx+10h]
0x180049255  xor     ecx, ecx; string
0x180049257  call    cs:__imp_WindowsDeleteString
0x18004925e  nop     dword ptr [rax+rax+00h]
0x180049263  mov     [rsp+68h+string], r12
0x18004926b  lea     rdi, [rsi+30h]
0x18004926f  cmp     qword ptr [rdi+18h], 8
0x180049274  jb      short loc_18004927B
0x180049276  mov     r15, [rdi]
0x180049279  jmp     short loc_18004927E
0x18004927b  mov     r15, rdi
0x18004927e  lea     rcx, [r14+140h]
0x180049285  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x18004928a  mov     ebx, eax
0x18004928c  test    eax, eax
0x18004928e  jns     short loc_1800492BA
0x180049290  mov     rcx, [rsp+68h]; this
0x180049295  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x18004929c  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800492a1  mov     r9d, ebx; char *
0x1800492a4  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800492ab  mov     edx, 17Bh; void *
0x1800492b0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800492b5  jmp     loc_180049394
0x1800492ba  mov     rax, [r14+190h]
0x1800492c1  test    rax, rax
0x1800492c4  jnz     loc_180049365
0x1800492ca  lea     rdx, aAppxgetpackage; "AppxGetPackageInstalledLocation"
0x1800492d1  mov     rcx, [r14+148h]; hModule
0x1800492d8  call    cs:__imp_GetProcAddress
0x1800492df  nop     dword ptr [rax+rax+00h]
0x1800492e4  mov     [r14+190h], rax
0x1800492eb  test    rax, rax
0x1800492ee  jnz     short loc_180049365
0x1800492f0  call    cs:__imp_GetLastError
0x1800492f7  nop     dword ptr [rax+rax+00h]
0x1800492fc  test    eax, eax
0x1800492fe  jle     short loc_18004930A
0x180049300  movzx   eax, ax
0x180049303  or      eax, 80070000h
0x180049308  test    eax, eax
0x18004930a  jns     short loc_180049331
0x18004930c  call    cs:__imp_GetLastError
0x180049313  nop     dword ptr [rax+rax+00h]
0x180049318  mov     ebx, eax
0x18004931a  test    eax, eax
0x18004931c  jle     short loc_180049327
0x18004931e  movzx   ebx, ax
0x180049321  or      ebx, 80070000h
0x180049327  test    ebx, ebx
0x180049329  jns     loc_1800493E9
0x18004932f  jmp     short loc_180049336
0x180049331  mov     ebx, 80004005h
0x180049336  mov     rcx, [rsp+68h]; this
0x18004933b  lea     rax, aUnableToGetpro_15; "Unable to GetProcAddress 'AppxGetInstal"...
0x180049342  mov     qword ptr [rsp+68h+var_48], rax; int
0x180049347  mov     r9d, ebx; char *
0x18004934a  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049351  mov     edx, 183h; void *
0x180049356  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004935b  test    ebx, ebx
0x18004935d  jns     loc_1800493E9
0x180049363  jmp     short loc_180049394
0x180049365  lea     rdx, [rsp+68h+string]
0x18004936d  mov     rcx, r15
0x180049370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049375  mov     ebx, eax
0x180049377  test    eax, eax
0x180049379  jns     short loc_1800493E9
0x18004937b  mov     rcx, [rsp+68h]; this
0x180049380  mov     r9d, eax; char *
0x180049383  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004938a  mov     edx, 187h; void *
0x18004938f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049394  cmp     qword ptr [rdi+18h], 8
0x180049399  jb      short loc_18004939E
0x18004939b  mov     rdi, [rdi]
0x18004939e  mov     rcx, [rsp+68h]; this
0x1800493a3  mov     [rsp+68h+var_40], rdi; char *
0x1800493a8  lea     rax, aFailedToGetIns_0; "Failed to get installed location of pac"...
0x1800493af  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800493b4  mov     r9d, ebx; char *
0x1800493b7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800493be  mov     edx, 313h; void *
0x1800493c3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800493c8  nop
0x1800493c9  mov     rcx, [rsp+68h+string]; string
0x1800493d1  test    rcx, rcx
0x1800493d4  jz      short loc_1800493E2
0x1800493d6  call    cs:__imp_WindowsDeleteString
0x1800493dd  nop     dword ptr [rax+rax+00h]
0x1800493e2  mov     eax, ebx
0x1800493e4  jmp     loc_180049641
0x1800493e9  mov     rcx, [rsp+68h+string]; string
0x1800493f1  test    rcx, rcx
0x1800493f4  jnz     loc_1800494A9
0x1800493fa  mov     dword ptr [rsp+68h+arg_0], r12d
0x1800493ff  mov     rcx, [rsi+10h]
0x180049403  add     rcx, 140h; this
0x18004940a  cmp     qword ptr [rdi+18h], 8
0x18004940f  jb      short loc_180049416
0x180049411  mov     rdx, [rdi]
0x180049414  jmp     short loc_180049419
0x180049416  mov     rdx, rdi; unsigned __int16 *
0x180049419  lea     r8, [rsp+68h+arg_0]; int *
0x18004941e  call    ?GetApplicabilityIsInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(ushort const *,int *)
0x180049423  mov     rcx, [rsp+68h]; this
0x180049428  test    eax, eax
0x18004942a  jns     short loc_180049440
0x18004942c  mov     r9d, eax; char *
0x18004942f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049436  mov     edx, 322h; void *
0x18004943b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049440  cmp     dword ptr [rsp+68h+arg_0], r12d
0x180049445  jz      short loc_18004944E
0x180049447  mov     dword ptr [rsi+18h], 3
0x18004944e  cmp     qword ptr [rdi+18h], 8
0x180049453  jb      short loc_180049458
0x180049455  mov     rdi, [rdi]
0x180049458  mov     rcx, [rsp+68h]; this
0x18004945d  mov     [rsp+68h+var_40], rdi; char *
0x180049462  lea     rax, aFailedToGetIns; "Failed to get installed location of pac"...
0x180049469  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004946e  mov     r9d, 80070057h; char *
0x180049474  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004947b  mov     edx, 328h; void *
0x180049480  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049485  nop
0x180049486  mov     rcx, [rsp+68h+string]; string
0x18004948e  test    rcx, rcx
0x180049491  jz      short loc_18004949F
0x180049493  call    cs:__imp_WindowsDeleteString
0x18004949a  nop     dword ptr [rax+rax+00h]
0x18004949f  mov     eax, 80070057h
0x1800494a4  jmp     loc_180049641
0x1800494a9  xor     edx, edx; length
0x1800494ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800494b2  nop     dword ptr [rax+rax+00h]
0x1800494b7  cmp     [rax], r12w
0x1800494bb  jnz     short loc_1800494C2
0x1800494bd  mov     r8, r12
0x1800494c0  jmp     short loc_1800494D0
0x1800494c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800494c6  inc     r8
0x1800494c9  cmp     [rax+r8*2], r12w
0x1800494ce  jnz     short loc_1800494C6
0x1800494d0  lea     rcx, [rsi+70h]; void *
0x1800494d4  mov     rdx, rax; Src
0x1800494d7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800494dc  test    r13, r13
0x1800494df  jz      loc_180049620
0x1800494e5  cmp     dword ptr [rsi+24h], 1
0x1800494e9  ja      loc_180049620
0x1800494ef  mov     r15, [r13+18h]
0x1800494f3  sub     r15, [r13+10h]
0x1800494f7  sar     r15, 3
0x1800494fb  mov     r14d, r12d
0x1800494fe  cmp     r14d, r15d
0x180049501  jnb     loc_180049620
0x180049507  mov     [rsp+68h+arg_0], r12
0x18004950c  lea     r8, [rsp+68h+arg_0]
0x180049511  mov     edx, r14d
0x180049514  mov     rcx, r13
0x180049517  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004951c  mov     ebx, eax
0x18004951e  test    eax, eax
0x180049520  jns     short loc_180049593
0x180049522  cmp     qword ptr [rdi+18h], 8
0x180049527  jb      short loc_18004952C
0x180049529  mov     rdi, [rdi]
0x18004952c  mov     rcx, [rsp+68h]; this
0x180049531  mov     [rsp+68h+var_38], rdi
0x180049536  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x18004953b  lea     rax, aFailedToObtain_5; "Failed to obtain dependency package %d "...
0x180049542  mov     qword ptr [rsp+68h+var_48], rax; int
0x180049547  mov     r9d, ebx; char *
0x18004954a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049551  mov     edx, 33Bh; void *
0x180049556  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004955b  nop
0x18004955c  mov     rcx, [rsp+68h+arg_0]
0x180049561  test    rcx, rcx
0x180049564  jz      short loc_180049573
0x180049566  mov     rax, [rcx]
0x180049569  mov     rax, [rax+10h]
0x18004956d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049572  nop
0x180049573  mov     rcx, [rsp+68h+string]; string
0x18004957b  test    rcx, rcx
0x18004957e  jz      short loc_18004958C
0x180049580  call    cs:__imp_WindowsDeleteString
0x180049587  nop     dword ptr [rax+rax+00h]
0x18004958c  mov     eax, ebx
0x18004958e  jmp     loc_180049641
0x180049593  xor     edx, edx; struct MsixPackage::Provisioning::Library::MsixAdapterCollection *
0x180049595  mov     rbx, [rsp+68h+arg_0]
0x18004959a  mov     rcx, rbx; this
0x18004959d  call    ?DetermineInstalledLocationOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(MsixPackage::Provisioning::Library::MsixAdapterCollection *)
0x1800495a2  mov     esi, eax
0x1800495a4  cmp     eax, 80070057h
0x1800495a9  jnz     short loc_1800495B3
0x1800495ab  cmp     dword ptr [rbx+18h], 3
0x1800495af  jnz     short loc_1800495B7
0x1800495b1  jmp     short loc_180049603
0x1800495b3  test    esi, esi
0x1800495b5  jns     short loc_180049603
0x1800495b7  mov     rcx, [rsp+68h]; this
0x1800495bc  mov     r9d, esi; char *
0x1800495bf  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800495c6  mov     edx, 34Fh; void *
0x1800495cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800495d0  nop
0x1800495d1  test    rbx, rbx
0x1800495d4  jz      short loc_1800495E6
0x1800495d6  mov     rax, [rbx]
0x1800495d9  mov     rcx, rbx
0x1800495dc  mov     rax, [rax+10h]
0x1800495e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495e5  nop
0x1800495e6  mov     rcx, [rsp+68h+string]; string
0x1800495ee  test    rcx, rcx
0x1800495f1  jz      short loc_1800495FF
0x1800495f3  call    cs:__imp_WindowsDeleteString
0x1800495fa  nop     dword ptr [rax+rax+00h]
0x1800495ff  mov     eax, esi
0x180049601  jmp     short loc_180049641
0x180049603  test    rbx, rbx
0x180049606  jz      short loc_180049618
0x180049608  mov     rax, [rbx]
0x18004960b  mov     rcx, rbx
0x18004960e  mov     rax, [rax+10h]
0x180049612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049617  nop
0x180049618  inc     r14d
0x18004961b  jmp     loc_1800494FE
0x180049620  mov     rcx, [rsp+68h+string]; string
0x180049628  test    rcx, rcx
0x18004962b  jz      short loc_180049639
0x18004962d  call    cs:__imp_WindowsDeleteString
0x180049634  nop     dword ptr [rax+rax+00h]
0x180049639  xor     eax, eax
0x18004963b  jmp     short loc_180049641
0x18004963d  mov     eax, dword ptr [rsp+68h+arg_0]
0x180049641  lea     r11, [rsp+68h+var_28]
0x180049646  mov     rbx, [r11+38h]
0x18004964a  mov     rsi, [r11+48h]
0x18004964e  mov     rsp, r11
0x180049651  pop     r15
0x180049653  pop     r14
0x180049655  pop     r13
0x180049657  pop     r12
0x180049659  pop     rdi
0x18004965a  retn
```
