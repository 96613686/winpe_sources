# MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(MsixPackage::Provisioning::Library::MsixAdapterCollection *)

- ea: `0x1800452e8`
- end: `0x1800456dc`
- name: `?DetermineInstalledLocationOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAVMsixAdapterCollection@234@@Z`
- size: `1012`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, struct MsixPackage::Provisioning::Library::MsixAdapterCollection *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800452e8`
- `0x18004961c`

## callees

- `0x18000cfe8`
- `0x18001bf0c`
- `0x18001c5b8`
- `0x180038d54`
- `0x180038de4`
- `0x180039e9c`
- `0x1800452e8`
- `0x1800456e4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004538e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004538e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004547a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004567f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004547a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004567f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800456b3`

## string_xrefs

- `0x18004534b`: `Failed to load AppxDeploymentClient.DLL.`
- `0x18004535a`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x1800453ee`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180045427`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004545b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800454cd`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045512`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800455dc`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004564b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045500`: `Failed to get installed location of package '%ws' because it's not staged`
- `0x18004544c`: `Failed to get installed location of package '%ws'.`
- `0x180045380`: `AppxGetPackageInstalledLocation`
- `0x1800453df`: `Unable to GetProcAddress 'AppxGetInstalledLocation'`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        struct MsixPackage::Provisioning::Library::MsixAdapterCollection *a2)
{
  __int64 v4; // r14
  char *v5; // rdi
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
  char *StringRawBuffer; // rax
  unsigned __int64 v19; // r8
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
LABEL_21:
      if ( *((_QWORD *)this + 9) >= 8u )
        v5 = *(char **)v5;
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
        goto LABEL_21;
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
        goto LABEL_21;
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
      StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
      if ( *(_WORD *)StringRawBuffer )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&StringRawBuffer[2 * v19] );
      }
      else
      {
        v19 = 0;
      }
      std::wstring::assign((_QWORD *)this + 14, StringRawBuffer, v19);
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
              v5 = *(char **)v5;
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
              goto LABEL_59;
          }
          else if ( v24 < 0 )
          {
LABEL_59:
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
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)IsInstalled);
      if ( (_DWORD)v29 )
        *((_DWORD *)this + 6) = 3;
      if ( *((_QWORD *)this + 9) >= 8u )
        v5 = *(char **)v5;
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
0x1800452e8  mov     rax, rsp
0x1800452eb  mov     [rax+10h], rbx
0x1800452ef  mov     [rax+20h], rsi
0x1800452f3  push    rdi
0x1800452f4  push    r12
0x1800452f6  push    r13
0x1800452f8  push    r14
0x1800452fa  push    r15
0x1800452fc  sub     rsp, 40h
0x180045300  mov     r13, rdx
0x180045303  mov     rsi, rcx
0x180045306  xor     r12d, r12d
0x180045309  mov     [rax+18h], r12
0x18004530d  mov     r14, [rcx+10h]
0x180045311  xor     ecx, ecx; string
0x180045313  call    cs:__imp_WindowsDeleteString
0x180045319  mov     [rsp+68h+string], r12
0x180045321  lea     rdi, [rsi+30h]
0x180045325  cmp     qword ptr [rdi+18h], 8
0x18004532a  jb      short loc_180045331
0x18004532c  mov     r15, [rdi]
0x18004532f  jmp     short loc_180045334
0x180045331  mov     r15, rdi
0x180045334  lea     rcx, [r14+140h]
0x18004533b  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)
0x180045340  mov     ebx, eax
0x180045342  test    eax, eax
0x180045344  jns     short loc_180045370
0x180045346  mov     rcx, [rsp+68h]; this
0x18004534b  lea     rax, aFailedToLoadAp; "Failed to load AppxDeploymentClient.DLL"...
0x180045352  mov     qword ptr [rsp+68h+var_48], rax; int
0x180045357  mov     r9d, ebx; char *
0x18004535a  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045361  mov     edx, 17Bh; void *
0x180045366  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004536b  jmp     loc_180045438
0x180045370  mov     rax, [r14+190h]
0x180045377  test    rax, rax
0x18004537a  jnz     loc_180045409
0x180045380  lea     rdx, aAppxgetpackage; "AppxGetPackageInstalledLocation"
0x180045387  mov     rcx, [r14+148h]; hModule
0x18004538e  call    cs:__imp_GetProcAddress
0x180045394  mov     [r14+190h], rax
0x18004539b  test    rax, rax
0x18004539e  jnz     short loc_180045409
0x1800453a0  call    cs:__imp_GetLastError
0x1800453a6  test    eax, eax
0x1800453a8  jle     short loc_1800453B4
0x1800453aa  movzx   eax, ax
0x1800453ad  or      eax, 80070000h
0x1800453b2  test    eax, eax
0x1800453b4  jns     short loc_1800453D5
0x1800453b6  call    cs:__imp_GetLastError
0x1800453bc  mov     ebx, eax
0x1800453be  test    eax, eax
0x1800453c0  jle     short loc_1800453CB
0x1800453c2  movzx   ebx, ax
0x1800453c5  or      ebx, 80070000h
0x1800453cb  test    ebx, ebx
0x1800453cd  jns     loc_180045487
0x1800453d3  jmp     short loc_1800453DA
0x1800453d5  mov     ebx, 80004005h
0x1800453da  mov     rcx, [rsp+68h]; this
0x1800453df  lea     rax, aUnableToGetpro_15; "Unable to GetProcAddress 'AppxGetInstal"...
0x1800453e6  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800453eb  mov     r9d, ebx; char *
0x1800453ee  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800453f5  mov     edx, 183h; void *
0x1800453fa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800453ff  test    ebx, ebx
0x180045401  jns     loc_180045487
0x180045407  jmp     short loc_180045438
0x180045409  lea     rdx, [rsp+68h+string]
0x180045411  mov     rcx, r15
0x180045414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045419  mov     ebx, eax
0x18004541b  test    eax, eax
0x18004541d  jns     short loc_180045487
0x18004541f  mov     rcx, [rsp+68h]; this
0x180045424  mov     r9d, eax; char *
0x180045427  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004542e  mov     edx, 187h; void *
0x180045433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045438  cmp     qword ptr [rdi+18h], 8
0x18004543d  jb      short loc_180045442
0x18004543f  mov     rdi, [rdi]
0x180045442  mov     rcx, [rsp+68h]; this
0x180045447  mov     [rsp+68h+var_40], rdi; char *
0x18004544c  lea     rax, aFailedToGetIns_0; "Failed to get installed location of pac"...
0x180045453  mov     qword ptr [rsp+68h+var_48], rax; int
0x180045458  mov     r9d, ebx; char *
0x18004545b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045462  mov     edx, 313h; void *
0x180045467  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004546c  nop
0x18004546d  mov     rcx, [rsp+68h+string]; string
0x180045475  test    rcx, rcx
0x180045478  jz      short loc_180045480
0x18004547a  call    cs:__imp_WindowsDeleteString
0x180045480  mov     eax, ebx
0x180045482  jmp     loc_1800456C1
0x180045487  mov     rcx, [rsp+68h+string]; string
0x18004548f  test    rcx, rcx
0x180045492  jnz     loc_180045541
0x180045498  mov     dword ptr [rsp+68h+arg_0], r12d
0x18004549d  mov     rcx, [rsi+10h]
0x1800454a1  add     rcx, 140h; this
0x1800454a8  cmp     qword ptr [rdi+18h], 8
0x1800454ad  jb      short loc_1800454B4
0x1800454af  mov     rdx, [rdi]
0x1800454b2  jmp     short loc_1800454B7
0x1800454b4  mov     rdx, rdi; unsigned __int16 *
0x1800454b7  lea     r8, [rsp+68h+arg_0]; int *
0x1800454bc  call    ?GetApplicabilityIsInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::GetApplicabilityIsInstalled(ushort const *,int *)
0x1800454c1  mov     rcx, [rsp+68h]; this
0x1800454c6  test    eax, eax
0x1800454c8  jns     short loc_1800454DE
0x1800454ca  mov     r9d, eax; char *
0x1800454cd  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800454d4  mov     edx, 322h; void *
0x1800454d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800454de  cmp     dword ptr [rsp+68h+arg_0], r12d
0x1800454e3  jz      short loc_1800454EC
0x1800454e5  mov     dword ptr [rsi+18h], 3
0x1800454ec  cmp     qword ptr [rdi+18h], 8
0x1800454f1  jb      short loc_1800454F6
0x1800454f3  mov     rdi, [rdi]
0x1800454f6  mov     rcx, [rsp+68h]; this
0x1800454fb  mov     [rsp+68h+var_40], rdi; char *
0x180045500  lea     rax, aFailedToGetIns; "Failed to get installed location of pac"...
0x180045507  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004550c  mov     r9d, 80070057h; char *
0x180045512  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045519  mov     edx, 328h; void *
0x18004551e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045523  nop
0x180045524  mov     rcx, [rsp+68h+string]; string
0x18004552c  test    rcx, rcx
0x18004552f  jz      short loc_180045537
0x180045531  call    cs:__imp_WindowsDeleteString
0x180045537  mov     eax, 80070057h
0x18004553c  jmp     loc_1800456C1
0x180045541  xor     edx, edx; length
0x180045543  call    cs:__imp_WindowsGetStringRawBuffer
0x180045549  cmp     [rax], r12w
0x18004554d  jnz     short loc_180045554
0x18004554f  mov     r8, r12
0x180045552  jmp     short loc_180045562
0x180045554  or      r8, 0FFFFFFFFFFFFFFFFh
0x180045558  inc     r8
0x18004555b  cmp     [rax+r8*2], r12w
0x180045560  jnz     short loc_180045558
0x180045562  lea     rcx, [rsi+70h]; void *
0x180045566  mov     rdx, rax; Src
0x180045569  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004556e  test    r13, r13
0x180045571  jz      loc_1800456A6
0x180045577  cmp     dword ptr [rsi+24h], 1
0x18004557b  ja      loc_1800456A6
0x180045581  mov     r15, [r13+18h]
0x180045585  sub     r15, [r13+10h]
0x180045589  sar     r15, 3
0x18004558d  mov     r14d, r12d
0x180045590  cmp     r14d, r15d
0x180045593  jnb     loc_1800456A6
0x180045599  mov     [rsp+68h+arg_0], r12
0x18004559e  lea     r8, [rsp+68h+arg_0]
0x1800455a3  mov     edx, r14d
0x1800455a6  mov     rcx, r13
0x1800455a9  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x1800455ae  mov     ebx, eax
0x1800455b0  test    eax, eax
0x1800455b2  jns     short loc_18004561F
0x1800455b4  cmp     qword ptr [rdi+18h], 8
0x1800455b9  jb      short loc_1800455BE
0x1800455bb  mov     rdi, [rdi]
0x1800455be  mov     rcx, [rsp+68h]; this
0x1800455c3  mov     [rsp+68h+var_38], rdi
0x1800455c8  mov     dword ptr [rsp+68h+var_40], r14d; char *
0x1800455cd  lea     rax, aFailedToObtain_5; "Failed to obtain dependency package %d "...
0x1800455d4  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800455d9  mov     r9d, ebx; char *
0x1800455dc  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800455e3  mov     edx, 33Bh; void *
0x1800455e8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800455ed  nop
0x1800455ee  mov     rcx, [rsp+68h+arg_0]
0x1800455f3  test    rcx, rcx
0x1800455f6  jz      short loc_180045605
0x1800455f8  mov     rax, [rcx]
0x1800455fb  mov     rax, [rax+10h]
0x1800455ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045604  nop
0x180045605  mov     rcx, [rsp+68h+string]; string
0x18004560d  test    rcx, rcx
0x180045610  jz      short loc_180045618
0x180045612  call    cs:__imp_WindowsDeleteString
0x180045618  mov     eax, ebx
0x18004561a  jmp     loc_1800456C1
0x18004561f  xor     edx, edx; struct MsixPackage::Provisioning::Library::MsixAdapterCollection *
0x180045621  mov     rbx, [rsp+68h+arg_0]
0x180045626  mov     rcx, rbx; this
0x180045629  call    ?DetermineInstalledLocationOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DetermineInstalledLocationOnline(MsixPackage::Provisioning::Library::MsixAdapterCollection *)
0x18004562e  mov     esi, eax
0x180045630  cmp     eax, 80070057h
0x180045635  jnz     short loc_18004563F
0x180045637  cmp     dword ptr [rbx+18h], 3
0x18004563b  jnz     short loc_180045643
0x18004563d  jmp     short loc_180045689
0x18004563f  test    esi, esi
0x180045641  jns     short loc_180045689
0x180045643  mov     rcx, [rsp+68h]; this
0x180045648  mov     r9d, esi; char *
0x18004564b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045652  mov     edx, 34Fh; void *
0x180045657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004565c  nop
0x18004565d  test    rbx, rbx
0x180045660  jz      short loc_180045672
0x180045662  mov     rax, [rbx]
0x180045665  mov     rcx, rbx
0x180045668  mov     rax, [rax+10h]
0x18004566c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045671  nop
0x180045672  mov     rcx, [rsp+68h+string]; string
0x18004567a  test    rcx, rcx
0x18004567d  jz      short loc_180045685
0x18004567f  call    cs:__imp_WindowsDeleteString
0x180045685  mov     eax, esi
0x180045687  jmp     short loc_1800456C1
0x180045689  test    rbx, rbx
0x18004568c  jz      short loc_18004569E
0x18004568e  mov     rax, [rbx]
0x180045691  mov     rcx, rbx
0x180045694  mov     rax, [rax+10h]
0x180045698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004569d  nop
0x18004569e  inc     r14d
0x1800456a1  jmp     loc_180045590
0x1800456a6  mov     rcx, [rsp+68h+string]; string
0x1800456ae  test    rcx, rcx
0x1800456b1  jz      short loc_1800456B9
0x1800456b3  call    cs:__imp_WindowsDeleteString
0x1800456b9  xor     eax, eax
0x1800456bb  jmp     short loc_1800456C1
0x1800456bd  mov     eax, dword ptr [rsp+68h+arg_0]
0x1800456c1  lea     r11, [rsp+68h+var_28]
0x1800456c6  mov     rbx, [r11+38h]
0x1800456ca  mov     rsi, [r11+48h]
0x1800456ce  mov     rsp, r11
0x1800456d1  pop     r15
0x1800456d3  pop     r14
0x1800456d5  pop     r13
0x1800456d7  pop     r12
0x1800456d9  pop     rdi
0x1800456da  retn
```
