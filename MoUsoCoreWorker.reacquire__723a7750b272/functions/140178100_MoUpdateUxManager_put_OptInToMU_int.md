# MoUpdateUxManager::put_OptInToMU(int)

- ea: `0x140178100`
- end: `0x1401785ee`
- name: `?put_OptInToMU@MoUpdateUxManager@@UEAAJH@Z`
- size: `1262`
- prototype: `__int64 __fastcall(MoUpdateUxManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140036040`

## callees

- `0x14003fd58`
- `0x14003ff28`
- `0x140040184`
- `0x1400407f8`
- `0x140045404`
- `0x140072104`
- `0x14007224c`
- `0x14016b1e8`
- `0x140178100`
- `0x14017d664`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140178158`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140178158`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1401781d1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1401781d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140178211`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1401781aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1401781aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1401783a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1401783b7`
- `OLEAUT32!__imp_SysFreeString` at `0x140178471`
- `OLEAUT32!__imp_SysFreeString` at `0x140178482`
- `OLEAUT32!__imp_SysFreeString` at `0x1401784fa`
- `OLEAUT32!__imp_SysFreeString` at `0x14017850b`
- `OLEAUT32!__imp_SysFreeString` at `0x140178557`
- `OLEAUT32!__imp_SysFreeString` at `0x140178568`
- `OLEAUT32!__imp_SysFreeString` at `0x1401783a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1401783b7`
- `OLEAUT32!__imp_SysFreeString` at `0x140178471`
- `OLEAUT32!__imp_SysFreeString` at `0x140178482`
- `OLEAUT32!__imp_SysFreeString` at `0x1401784fa`
- `OLEAUT32!__imp_SysFreeString` at `0x14017850b`
- `OLEAUT32!__imp_SysFreeString` at `0x140178557`
- `OLEAUT32!__imp_SysFreeString` at `0x140178568`
- `OLEAUT32!__imp_VariantClear` at `0x140178372`
- `OLEAUT32!__imp_VariantClear` at `0x140178372`

## string_xrefs

- `0x1401785db`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140178174`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x1401781ed`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140178272`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140178387`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x140178452`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x1401784db`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall MoUpdateUxManager::put_OptInToMU(MoUpdateUxManager *this, int a2)
{
  char *Thread; // rbx
  const char *v4; // r9
  unsigned int LastError; // edi
  DWORD v6; // eax
  const char *v7; // r9
  DWORD v8; // edi
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rax
  LONGLONG v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  int v16; // ebx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-88h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-88h]
  BSTR v19[2]; // [rsp+30h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-68h] BYREF
  VARIANTARG v21; // [rsp+60h] [rbp-48h] BYREF
  DWORD ExitCode[2]; // [rsp+80h] [rbp-28h] BYREF
  __int64 *v23; // [rsp+88h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( g_coreWorkerShuttingDown )
    return 2149884189LL;
  if ( a2 )
  {
    Thread = (char *)CreateThread(0, 0, MoUpdateUxManager::AddMuServiceThreadProc, 0, 0, 0);
    if ( ((unsigned __int64)(Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x231,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
                    v4);
      if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(Thread);
      return LastError;
    }
    v6 = WaitForSingleObjectEx(Thread, 0xFFFFFFFF, 0);
    if ( v6 != 258 && v6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xAD8,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    ExitCode[0] = 0;
    GetExitCodeThread(Thread, ExitCode);
    v8 = ExitCode[0];
    if ( (ExitCode[0] & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x237,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
        (const char *)ExitCode[0],
        dwCreationFlagsa);
      CloseHandle(Thread);
      return v8;
    }
    CloseHandle(Thread);
    return 0;
  }
  v23 = 0;
  wil::CoCreateInstance<UpdateSession,IUpdateSession3,wil::err_exception_policy>(&v23);
  *(_QWORD *)ExitCode = 0;
  v9 = *v23;
  *(_QWORD *)ExitCode = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, DWORD *))(v9 + 136))(v23, ExitCode);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
      (const char *)(unsigned int)v10,
      dwCreationFlags);
    if ( *(_QWORD *)ExitCode )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ExitCode + 16LL))(*(_QWORD *)ExitCode);
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
    return v11;
  }
  v19[0] = 0;
  v12 = (_QWORD *)Windows::Strings::to_wstring(&v21, &USO_SERVICE_MU);
  v13 = v12[2];
  if ( v12[3] > 7u )
    v12 = (_QWORD *)*v12;
  *(_QWORD *)&pvarg.vt = v12;
  pvarg.llVal = v13;
  Windows::Strings::to_bstr(v19, &pvarg);
  std::wstring::~wstring(&v21);
  bstrString = 0;
  wil::make_bstr(&bstrString, L"AllowWarningUI");
  v14 = **(_QWORD **)ExitCode;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v21 = pvarg;
  v15 = (*(__int64 (__fastcall **)(_QWORD, BSTR, VARIANTARG *))(v14 + 104))(*(_QWORD *)ExitCode, bstrString, &v21);
  VariantClear(&pvarg);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
      (const char *)(unsigned int)v15,
      dwCreationFlags);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v19[0] )
      SysFreeString(v19[0]);
    if ( *(_QWORD *)ExitCode )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ExitCode + 16LL))(*(_QWORD *)ExitCode);
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
    return (unsigned int)v15;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)ExitCode + 88LL))(*(_QWORD *)ExitCode, v19[0]);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl'::`2'::impl) )
  {
    if ( v16 != -2145091564 && (unsigned int)(v16 + 2145091542) > 2 )
    {
      if ( v16 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
          (const char *)(unsigned int)v16,
          dwCreationFlags);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v19[0] )
        SysFreeString(v19[0]);
      if ( *(_QWORD *)ExitCode )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ExitCode + 16LL))(*(_QWORD *)ExitCode);
      if ( v23 )
        (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
      return (unsigned int)v16;
    }
LABEL_57:
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v19[0] )
      SysFreeString(v19[0]);
    if ( *(_QWORD *)ExitCode )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ExitCode + 16LL))(*(_QWORD *)ExitCode);
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
    return 0;
  }
  if ( v16 == -2145091564 )
    goto LABEL_57;
  if ( v16 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
      (const char *)(unsigned int)v16,
      dwCreationFlags);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v19[0] )
    SysFreeString(v19[0]);
  if ( *(_QWORD *)ExitCode )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ExitCode + 16LL))(*(_QWORD *)ExitCode);
  if ( v23 )
    (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140178100  mov     [rsp+arg_0], rbx
0x140178105  mov     [rsp+arg_8], rsi
0x14017810a  push    rdi
0x14017810b  sub     rsp, 0A0h
0x140178112  mov     rax, cs:__security_cookie
0x140178119  xor     rax, rsp
0x14017811c  mov     [rsp+0A8h+var_10], rax
0x140178124  xor     esi, esi
0x140178126  cmp     cs:?g_coreWorkerShuttingDown@@3_NA, sil; bool g_coreWorkerShuttingDown
0x14017812d  jz      short loc_140178139
0x14017812f  mov     eax, 8024A11Dh
0x140178134  jmp     loc_1401785AE
0x140178139  test    edx, edx
0x14017813b  jz      loc_14017821C
0x140178141  mov     [rsp+0A8h+lpThreadId], rsi; lpThreadId
0x140178146  mov     [rsp+0A8h+dwCreationFlags], esi; int
0x14017814a  xor     r9d, r9d; lpParameter
0x14017814d  lea     r8, ?AddMuServiceThreadProc@MoUpdateUxManager@@CAKPEAX@Z; lpStartAddress
0x140178154  xor     edx, edx; dwStackSize
0x140178156  xor     ecx, ecx; lpThreadAttributes
0x140178158  call    cs:__imp_CreateThread
0x14017815e  mov     rbx, rax
0x140178161  inc     rax
0x140178164  test    rax, 0FFFFFFFFFFFFFFFEh
0x14017816a  jnz     short loc_1401781A1
0x14017816c  mov     rcx, [rsp+0A8h]; this
0x140178174  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14017817b  mov     edx, 231h; void *
0x140178180  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140178185  mov     edi, eax
0x140178187  lea     rcx, [rbx-1]
0x14017818b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14017818f  ja      short loc_14017819A
0x140178191  mov     rcx, rbx; hObject
0x140178194  call    cs:__imp_CloseHandle
0x14017819a  mov     eax, edi
0x14017819c  jmp     loc_1401785AE
0x1401781a1  xor     r8d, r8d; bAlertable
0x1401781a4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1401781a7  mov     rcx, rbx; hHandle
0x1401781aa  call    cs:__imp_WaitForSingleObjectEx
0x1401781b0  cmp     eax, 102h
0x1401781b5  jz      short loc_1401781BF
0x1401781b7  test    eax, eax
0x1401781b9  jnz     loc_1401785D3
0x1401781bf  mov     [rsp+0A8h+ExitCode], esi
0x1401781c6  lea     rdx, [rsp+0A8h+ExitCode]; lpExitCode
0x1401781ce  mov     rcx, rbx; hThread
0x1401781d1  call    cs:__imp_GetExitCodeThread
0x1401781d7  mov     edi, [rsp+0A8h+ExitCode]
0x1401781de  test    edi, edi
0x1401781e0  jns     short loc_14017820E
0x1401781e2  mov     rcx, [rsp+0A8h]; this
0x1401781ea  mov     r9d, edi; char *
0x1401781ed  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1401781f4  mov     edx, 237h; void *
0x1401781f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401781fe  mov     rcx, rbx; hObject
0x140178201  call    cs:__imp_CloseHandle
0x140178207  mov     eax, edi
0x140178209  jmp     loc_1401785AE
0x14017820e  mov     rcx, rbx; hObject
0x140178211  call    cs:__imp_CloseHandle
0x140178217  jmp     loc_1401785A3
0x14017821c  mov     [rsp+0A8h+var_20], rsi
0x140178224  lea     rcx, [rsp+0A8h+var_20]
0x14017822c  call    ??$CoCreateInstance@VUpdateSession@@UIUpdateSession3@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateSession3@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSession,IUpdateSession3,wil::err_exception_policy>(ulong)
0x140178231  nop
0x140178232  mov     qword ptr [rsp+0A8h+ExitCode], rsi
0x14017823a  mov     rcx, [rsp+0A8h+var_20]
0x140178242  mov     rax, [rcx]
0x140178245  mov     qword ptr [rsp+0A8h+ExitCode], rsi
0x14017824d  lea     rdx, [rsp+0A8h+ExitCode]
0x140178255  mov     rax, [rax+88h]
0x14017825c  call    _guard_dispatch_icall
0x140178261  mov     ebx, eax
0x140178263  test    eax, eax
0x140178265  jns     short loc_1401782BF
0x140178267  mov     rcx, [rsp+0A8h]; this
0x14017826f  mov     r9d, eax; char *
0x140178272  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140178279  mov     edx, 23Eh; void *
0x14017827e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140178283  nop
0x140178284  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x14017828c  test    rcx, rcx
0x14017828f  jz      short loc_14017829E
0x140178291  mov     rax, [rcx]
0x140178294  mov     rax, [rax+10h]
0x140178298  call    _guard_dispatch_icall
0x14017829d  nop
0x14017829e  mov     rcx, [rsp+0A8h+var_20]
0x1401782a6  test    rcx, rcx
0x1401782a9  jz      short loc_1401782B8
0x1401782ab  mov     rax, [rcx]
0x1401782ae  mov     rax, [rax+10h]
0x1401782b2  call    _guard_dispatch_icall
0x1401782b7  nop
0x1401782b8  mov     eax, ebx
0x1401782ba  jmp     loc_1401785AE
0x1401782bf  mov     [rsp+0A8h+var_78], rsi
0x1401782c4  lea     rdx, ?USO_SERVICE_MU@@3U_GUID@@B; _GUID const USO_SERVICE_MU
0x1401782cb  lea     rcx, [rsp+0A8h+var_48]
0x1401782d0  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; Windows::Strings::to_wstring(_GUID const &)
0x1401782d5  nop
0x1401782d6  mov     rcx, [rax+10h]
0x1401782da  cmp     qword ptr [rax+18h], 7
0x1401782df  jbe     short loc_1401782E4
0x1401782e1  mov     rax, [rax]
0x1401782e4  mov     qword ptr [rsp+0A8h+pvarg], rax
0x1401782e9  mov     qword ptr [rsp+0A8h+pvarg+8], rcx
0x1401782ee  lea     rdx, [rsp+0A8h+pvarg]
0x1401782f3  lea     rcx, [rsp+0A8h+var_78]
0x1401782f8  call    ?to_bstr@Strings@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@4@@Z; Windows::Strings::to_bstr(wil::basic_zstring_view<wchar_t>)
0x1401782fd  nop
0x1401782fe  lea     rcx, [rsp+0A8h+var_48]
0x140178303  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140178308  mov     [rsp+0A8h+bstrString], rsi
0x140178310  lea     rdx, aAllowwarningui; "AllowWarningUI"
0x140178317  lea     rcx, [rsp+0A8h+bstrString]
0x14017831f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x140178324  nop
0x140178325  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x14017832d  mov     rax, [rcx]
0x140178330  mov     edx, 0Bh
0x140178335  mov     word ptr [rsp+0A8h+pvarg], dx
0x14017833a  mov     word ptr [rsp+0A8h+pvarg+8], si
0x14017833f  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x140178344  movaps  [rsp+0A8h+var_48], xmm0
0x140178349  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x14017834f  movsd   [rsp+0A8h+var_38], xmm1
0x140178355  lea     r8, [rsp+0A8h+var_48]
0x14017835a  mov     rdx, [rsp+0A8h+bstrString]
0x140178362  mov     rax, [rax+68h]
0x140178366  call    _guard_dispatch_icall
0x14017836b  mov     ebx, eax
0x14017836d  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x140178372  call    cs:__imp_VariantClear
0x140178378  test    ebx, ebx
0x14017837a  jns     short loc_1401783F9
0x14017837c  mov     rcx, [rsp+0A8h]; this
0x140178384  mov     r9d, ebx; char *
0x140178387  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14017838e  mov     edx, 244h; void *
0x140178393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140178398  nop
0x140178399  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x1401783a1  test    rcx, rcx
0x1401783a4  jz      short loc_1401783AD
0x1401783a6  call    cs:__imp_SysFreeString
0x1401783ac  nop
0x1401783ad  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x1401783b2  test    rcx, rcx
0x1401783b5  jz      short loc_1401783BE
0x1401783b7  call    cs:__imp_SysFreeString
0x1401783bd  nop
0x1401783be  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x1401783c6  test    rcx, rcx
0x1401783c9  jz      short loc_1401783D8
0x1401783cb  mov     rax, [rcx]
0x1401783ce  mov     rax, [rax+10h]
0x1401783d2  call    _guard_dispatch_icall
0x1401783d7  nop
0x1401783d8  mov     rcx, [rsp+0A8h+var_20]
0x1401783e0  test    rcx, rcx
0x1401783e3  jz      short loc_1401783F2
0x1401783e5  mov     rax, [rcx]
0x1401783e8  mov     rax, [rax+10h]
0x1401783ec  call    _guard_dispatch_icall
0x1401783f1  nop
0x1401783f2  mov     eax, ebx
0x1401783f4  jmp     loc_1401785AE
0x1401783f9  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x140178401  mov     rax, [rcx]
0x140178404  mov     rdx, [rsp+0A8h+var_78]
0x140178409  mov     rax, [rax+58h]
0x14017840d  call    _guard_dispatch_icall
0x140178412  mov     ebx, eax
0x140178414  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::GetImpl(void)'::`2'::impl
0x14017841b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UnknownServiceSubcategories>::__private_IsEnabled(void)
0x140178420  test    al, al
0x140178422  jz      loc_1401784C4
0x140178428  cmp     ebx, 80248014h
0x14017842e  jz      loc_14017854A
0x140178434  lea     eax, [rbx+7FDB7FD6h]
0x14017843a  cmp     eax, 2
0x14017843d  jbe     loc_14017854A
0x140178443  test    ebx, ebx
0x140178445  jns     short loc_140178464
0x140178447  mov     rcx, [rsp+0A8h]; this
0x14017844f  mov     r9d, ebx; char *
0x140178452  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140178459  mov     edx, 249h; void *
0x14017845e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140178463  nop
0x140178464  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x14017846c  test    rcx, rcx
0x14017846f  jz      short loc_140178478
0x140178471  call    cs:__imp_SysFreeString
0x140178477  nop
0x140178478  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x14017847d  test    rcx, rcx
0x140178480  jz      short loc_140178489
0x140178482  call    cs:__imp_SysFreeString
0x140178488  nop
0x140178489  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x140178491  test    rcx, rcx
0x140178494  jz      short loc_1401784A3
0x140178496  mov     rax, [rcx]
0x140178499  mov     rax, [rax+10h]
0x14017849d  call    _guard_dispatch_icall
0x1401784a2  nop
0x1401784a3  mov     rcx, [rsp+0A8h+var_20]
0x1401784ab  test    rcx, rcx
0x1401784ae  jz      short loc_1401784BD
0x1401784b0  mov     rax, [rcx]
0x1401784b3  mov     rax, [rax+10h]
0x1401784b7  call    _guard_dispatch_icall
0x1401784bc  nop
0x1401784bd  mov     eax, ebx
0x1401784bf  jmp     loc_1401785AE
0x1401784c4  cmp     ebx, 80248014h
0x1401784ca  jz      short loc_14017854A
0x1401784cc  test    ebx, ebx
0x1401784ce  jns     short loc_1401784ED
0x1401784d0  mov     rcx, [rsp+0A8h]; this
0x1401784d8  mov     r9d, ebx; char *
0x1401784db  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1401784e2  mov     edx, 24Dh; void *
0x1401784e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401784ec  nop
0x1401784ed  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x1401784f5  test    rcx, rcx
0x1401784f8  jz      short loc_140178501
0x1401784fa  call    cs:__imp_SysFreeString
0x140178500  nop
0x140178501  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x140178506  test    rcx, rcx
0x140178509  jz      short loc_140178512
0x14017850b  call    cs:__imp_SysFreeString
0x140178511  nop
0x140178512  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x14017851a  test    rcx, rcx
0x14017851d  jz      short loc_14017852C
0x14017851f  mov     rax, [rcx]
0x140178522  mov     rax, [rax+10h]
0x140178526  call    _guard_dispatch_icall
0x14017852b  nop
0x14017852c  mov     rcx, [rsp+0A8h+var_20]
0x140178534  test    rcx, rcx
0x140178537  jz      short loc_140178546
0x140178539  mov     rax, [rcx]
0x14017853c  mov     rax, [rax+10h]
0x140178540  call    _guard_dispatch_icall
0x140178545  nop
0x140178546  mov     eax, ebx
0x140178548  jmp     short loc_1401785AE
0x14017854a  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140178552  test    rcx, rcx
0x140178555  jz      short loc_14017855E
0x140178557  call    cs:__imp_SysFreeString
0x14017855d  nop
0x14017855e  mov     rcx, [rsp+0A8h+var_78]; bstrString
0x140178563  test    rcx, rcx
0x140178566  jz      short loc_14017856F
0x140178568  call    cs:__imp_SysFreeString
0x14017856e  nop
0x14017856f  mov     rcx, qword ptr [rsp+0A8h+ExitCode]
0x140178577  test    rcx, rcx
0x14017857a  jz      short loc_140178589
0x14017857c  mov     rax, [rcx]
0x14017857f  mov     rax, [rax+10h]
0x140178583  call    _guard_dispatch_icall
0x140178588  nop
0x140178589  mov     rcx, [rsp+0A8h+var_20]
0x140178591  test    rcx, rcx
0x140178594  jz      short loc_1401785A3
0x140178596  mov     rax, [rcx]
0x140178599  mov     rax, [rax+10h]
0x14017859d  call    _guard_dispatch_icall
0x1401785a2  nop
0x1401785a3  xor     eax, eax
0x1401785a5  jmp     short loc_1401785AE
0x1401785a7  mov     eax, [rsp+0A8h+ExitCode]
0x1401785ae  mov     rcx, [rsp+0A8h+var_10]
0x1401785b6  xor     rcx, rsp; StackCookie
0x1401785b9  call    __security_check_cookie
0x1401785be  lea     r11, [rsp+0A8h+var_8]
0x1401785c6  mov     rbx, [r11+10h]
0x1401785ca  mov     rsi, [r11+18h]
0x1401785ce  mov     rsp, r11
0x1401785d1  pop     rdi
0x1401785d2  retn
0x1401785d3  mov     rcx, [rsp+0A8h]; this
0x1401785db  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1401785e2  mov     edx, 0AD8h; void *
0x1401785e7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
