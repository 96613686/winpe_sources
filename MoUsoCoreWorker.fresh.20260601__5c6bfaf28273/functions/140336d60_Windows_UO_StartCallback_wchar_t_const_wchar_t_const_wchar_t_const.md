# Windows::UO::StartCallback(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140336d60`
- end: `0x1403371c9`
- name: `?StartCallback@UO@Windows@@YAJPEB_W00@Z`
- size: `1129`
- prototype: `__int64 __fastcall(Windows::UO *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14033a200`
- `0x14033a7b0`

## callees

- `0x1400407f8`
- `0x140045404`
- `0x140073e58`
- `0x14007489c`
- `0x14012d864`
- `0x14017416c`
- `0x14024898c`
- `0x140254ca4`
- `0x140312df0`
- `0x140336d60`
- `0x14033b508`
- `0x140374388`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14033709a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14033709a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140336fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140337003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403370e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140337115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140336fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140337003`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403370e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140337115`

## string_xrefs

- `0x140336ede`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x140336f86`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x140336fe7`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x1403370bd`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x14033713d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x140337162`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x140337187`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOUpdate.cpp`
- `0x1403370b6`: `LegacyUOUpdate unable to invoke callback for [%ws] : [%ws]`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall Windows::UO::StartCallback(
        Windows::UO *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  _QWORD *System; // rax
  bool v7; // r14
  Windows::Trust *v8; // rcx
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _WORD *v14; // rax
  _QWORD *v15; // r8
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  void *v19; // rbx
  struct _PROCESS_INFORMATION *v20; // rdx
  unsigned int LastErrorMsg; // edi
  struct _PROCESS_INFORMATION *v22; // rdx
  int bInheritHandles; // [rsp+20h] [rbp-148h]
  LPVOID pv[2]; // [rsp+50h] [rbp-118h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-108h] BYREF
  const wchar_t *v26; // [rsp+70h] [rbp-F8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-F0h]
  _QWORD v28[3]; // [rsp+80h] [rbp-E8h] BYREF
  unsigned __int64 v29; // [rsp+98h] [rbp-D0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  LODWORD(pv[0]) = 0;
  if ( !this || !*(_WORD *)this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    return 2147942487LL;
  }
  if ( !a2 || !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    return 2147942487LL;
  }
  if ( !a3 || !*a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    return 2147942487LL;
  }
  Windows::PathVerification::VerifyUpdaterPath(v28, this, a2);
  System = (_QWORD *)SystemInterface::Service::GetSystem(&v26);
  v7 = 1;
  LODWORD(pv[0]) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*System + 184LL))(*System) )
    v7 = !Windows::Trust::IsUMCIEnabled(v8);
  v9 = (volatile signed __int32 *)v27;
  v10 = -1;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( v7 )
  {
    v11 = v28;
    if ( v29 > 7 )
      v11 = (_QWORD *)v28[0];
    do
      ++v10;
    while ( *((_WORD *)v11 + v10) );
    v25[0] = v11;
    v25[1] = v10;
    if ( !(unsigned __int8)Windows::Trust::IsSelfSignedOrCatalogSignedFile(v25) )
    {
      v12 = v28;
      if ( v29 > 7 )
        v12 = (_QWORD *)v28[0];
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x35,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
        (const char *)0x80070005LL,
        (int)"InvalidSignature.  Caller: [%ws] Cmdline: [%ws]",
        (const char *)this,
        v12);
      std::wstring::~wstring(v28);
      return 2147942405LL;
    }
  }
  memset(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  pv[0] = 0;
  v14 = v28;
  if ( v29 > 7 )
    v14 = (_WORD *)v28[0];
  v15 = v28;
  if ( *v14 == 34 )
  {
    if ( v29 > 7 )
      v15 = (_QWORD *)v28[0];
    v16 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            pv,
            L"%ws %ws",
            v15,
            a3);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
        (const char *)(unsigned int)v16,
        bInheritHandles);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
LABEL_29:
      std::wstring::~wstring(v28);
      return v17;
    }
  }
  else
  {
    if ( v29 > 7 )
      v15 = (_QWORD *)v28[0];
    v18 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            pv,
            L"\"%ws\" %ws",
            v15,
            a3);
    v17 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
        (const char *)(unsigned int)v18,
        bInheritHandles);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
      goto LABEL_29;
    }
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v19 = pv[0];
  v25[0] = pv[0];
  v26 = L"Starting callback: {}";
  v27 = 21;
  SystemInterface::Log<wchar_t *>(&v26, v25);
  if ( CreateProcessW(0, (LPWSTR)v19, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v20);
    if ( v19 )
      CoTaskMemFree(v19);
    std::wstring::~wstring(v28);
    return 0;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x57,
                     (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOUpdate.cpp",
                     "LegacyUOUpdate unable to invoke callback for [%ws] : [%ws]",
                     (const char *)this,
                     v19);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v22);
    if ( v19 )
      CoTaskMemFree(v19);
    std::wstring::~wstring(v28);
    return LastErrorMsg;
  }
}

```

## disassembly

```asm
0x140336d60  mov     [rsp+arg_18], rbx
0x140336d65  push    rsi
0x140336d66  push    rdi
0x140336d67  push    r12
0x140336d69  push    r14
0x140336d6b  push    r15
0x140336d6d  sub     rsp, 140h
0x140336d74  mov     rax, cs:__security_cookie
0x140336d7b  xor     rax, rsp
0x140336d7e  mov     [rsp+168h+var_38], rax
0x140336d86  mov     r15, r8
0x140336d89  mov     rsi, rcx
0x140336d8c  xor     r12d, r12d
0x140336d8f  mov     dword ptr [rsp+168h+pv], r12d
0x140336d94  test    rcx, rcx
0x140336d97  jz      loc_140337177
0x140336d9d  cmp     [rcx], r12w
0x140336da1  jz      loc_140337177
0x140336da7  test    rdx, rdx
0x140336daa  jz      loc_140337152
0x140336db0  cmp     [rdx], r12w
0x140336db4  jz      loc_140337152
0x140336dba  test    r8, r8
0x140336dbd  jz      loc_14033712D
0x140336dc3  cmp     [r8], r12w
0x140336dc7  jz      loc_14033712D
0x140336dcd  mov     r8, rdx
0x140336dd0  mov     rdx, rcx
0x140336dd3  lea     rcx, [rsp+168h+var_E8]
0x140336ddb  call    ?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)
0x140336de0  nop
0x140336de1  lea     rcx, [rsp+168h+var_F8]
0x140336de6  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x140336deb  nop
0x140336dec  lea     r14d, [r12+1]
0x140336df1  mov     dword ptr [rsp+168h+pv], r14d
0x140336df6  mov     rcx, [rax]
0x140336df9  mov     rax, [rcx]
0x140336dfc  mov     rax, [rax+0B8h]
0x140336e03  call    _guard_dispatch_icall
0x140336e08  test    al, al
0x140336e0a  jz      short loc_140336E18
0x140336e0c  call    ?IsUMCIEnabled@Trust@Windows@@YA_NXZ; Windows::Trust::IsUMCIEnabled(void)
0x140336e11  test    al, al
0x140336e13  jz      short loc_140336E18
0x140336e15  mov     r14b, r12b
0x140336e18  mov     rbx, [rsp+168h+var_F0]
0x140336e1d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140336e21  test    rbx, rbx
0x140336e24  jz      short loc_140336E59
0x140336e26  mov     eax, edi
0x140336e28  lock xadd [rbx+8], eax
0x140336e2d  add     eax, edi
0x140336e2f  jnz     short loc_140336E59
0x140336e31  mov     rax, [rbx]
0x140336e34  mov     rcx, rbx
0x140336e37  mov     rax, [rax]
0x140336e3a  call    _guard_dispatch_icall
0x140336e3f  mov     eax, edi
0x140336e41  lock xadd [rbx+0Ch], eax
0x140336e46  add     eax, edi
0x140336e48  jnz     short loc_140336E59
0x140336e4a  mov     rax, [rbx]
0x140336e4d  mov     rcx, rbx
0x140336e50  mov     rax, [rax+8]
0x140336e54  call    _guard_dispatch_icall
0x140336e59  test    r14b, r14b
0x140336e5c  jz      loc_140336F04
0x140336e62  lea     rax, [rsp+168h+var_E8]
0x140336e6a  cmp     [rsp+168h+var_D0], 7
0x140336e73  cmova   rax, [rsp+168h+var_E8]
0x140336e7c  inc     rdi
0x140336e7f  cmp     [rax+rdi*2], r12w
0x140336e84  jnz     short loc_140336E7C
0x140336e86  mov     [rsp+168h+var_108], rax
0x140336e8b  mov     [rsp+168h+var_100], rdi
0x140336e90  lea     rcx, [rsp+168h+var_108]
0x140336e95  call    ?IsSelfSignedOrCatalogSignedFile@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsSelfSignedOrCatalogSignedFile(wil::basic_zstring_view<wchar_t>,bool)
0x140336e9a  test    al, al
0x140336e9c  jnz     short loc_140336F04
0x140336e9e  lea     rax, [rsp+168h+var_E8]
0x140336ea6  cmp     [rsp+168h+var_D0], 7
0x140336eaf  cmova   rax, [rsp+168h+var_E8]
0x140336eb8  mov     rcx, [rsp+168h]; this
0x140336ec0  mov     [rsp+168h+lpEnvironment], rax
0x140336ec5  mov     qword ptr [rsp+168h+dwCreationFlags], rsi; char *
0x140336eca  lea     rax, aInvalidsignatu; "InvalidSignature.  Caller: [%ws] Cmdlin"...
0x140336ed1  mov     qword ptr [rsp+168h+bInheritHandles], rax; int
0x140336ed6  mov     ebx, 80070005h
0x140336edb  mov     r9d, ebx; char *
0x140336ede  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140336ee5  mov     edx, 35h ; '5'; void *
0x140336eea  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140336eef  nop
0x140336ef0  lea     rcx, [rsp+168h+var_E8]
0x140336ef8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140336efd  mov     eax, ebx
0x140336eff  jmp     loc_1403371A0
0x140336f04  xor     edx, edx; Val
0x140336f06  lea     r8d, [rdx+64h]; Size
0x140336f0a  lea     rcx, [rsp+168h+StartupInfo+4]; void *
0x140336f12  call    memset
0x140336f17  mov     [rsp+168h+StartupInfo.cb], 68h ; 'h'
0x140336f22  mov     [rsp+168h+pv], r12
0x140336f27  lea     rax, [rsp+168h+var_E8]
0x140336f2f  mov     rcx, [rsp+168h+var_E8]
0x140336f37  mov     rdx, [rsp+168h+var_D0]
0x140336f3f  cmp     rdx, 7
0x140336f43  cmova   rax, rcx
0x140336f47  lea     r8, [rsp+168h+var_E8]
0x140336f4f  mov     r9, r15
0x140336f52  cmp     word ptr [rax], 22h ; '"'
0x140336f56  jnz     short loc_140336FBD
0x140336f58  cmp     rdx, 7
0x140336f5c  cmova   r8, rcx
0x140336f60  lea     rdx, aWsWs_1; "%ws %ws"
0x140336f67  lea     rcx, [rsp+168h+pv]
0x140336f6c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x140336f71  mov     ebx, eax
0x140336f73  test    eax, eax
0x140336f75  jns     loc_14033701E
0x140336f7b  mov     rcx, [rsp+168h]; this
0x140336f83  mov     r9d, eax; char *
0x140336f86  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140336f8d  mov     edx, 41h ; 'A'; void *
0x140336f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140336f97  nop
0x140336f98  mov     rcx, [rsp+168h+pv]; pv
0x140336f9d  test    rcx, rcx
0x140336fa0  jz      short loc_140336FA9
0x140336fa2  call    cs:__imp_CoTaskMemFree
0x140336fa8  nop
0x140336fa9  lea     rcx, [rsp+168h+var_E8]
0x140336fb1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140336fb6  mov     eax, ebx
0x140336fb8  jmp     loc_1403371A0
0x140336fbd  cmp     rdx, 7
0x140336fc1  cmova   r8, rcx
0x140336fc5  lea     rdx, aWsWs; "\"%ws\" %ws"
0x140336fcc  lea     rcx, [rsp+168h+pv]
0x140336fd1  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x140336fd6  mov     ebx, eax
0x140336fd8  test    eax, eax
0x140336fda  jns     short loc_14033701E
0x140336fdc  mov     rcx, [rsp+168h]; this
0x140336fe4  mov     r9d, eax; char *
0x140336fe7  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140336fee  mov     edx, 45h ; 'E'; void *
0x140336ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140336ff8  nop
0x140336ff9  mov     rcx, [rsp+168h+pv]; pv
0x140336ffe  test    rcx, rcx
0x140337001  jz      short loc_14033700A
0x140337003  call    cs:__imp_CoTaskMemFree
0x140337009  nop
0x14033700a  lea     rcx, [rsp+168h+var_E8]
0x140337012  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140337017  mov     eax, ebx
0x140337019  jmp     loc_1403371A0
0x14033701e  xorps   xmm0, xmm0
0x140337021  xor     eax, eax
0x140337023  movups  xmmword ptr [rsp+168h+ProcessInformation.hProcess], xmm0
0x14033702b  mov     qword ptr [rsp+168h+ProcessInformation.dwProcessId], rax
0x140337033  mov     rbx, [rsp+168h+pv]
0x140337038  mov     [rsp+168h+var_108], rbx
0x14033703d  lea     rax, aStartingCallba; "Starting callback: {}"
0x140337044  mov     [rsp+168h+var_F8], rax
0x140337049  mov     [rsp+168h+var_F0], 15h
0x140337052  lea     rdx, [rsp+168h+var_108]
0x140337057  lea     rcx, [rsp+168h+var_F8]
0x14033705c  call    ??$Log@PEA_W@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEA_W@Z; SystemInterface::Log<wchar_t *>(std::wstring_view,wchar_t * &&)
0x140337061  lea     rax, [rsp+168h+ProcessInformation]
0x140337069  mov     [rsp+168h+lpProcessInformation], rax; lpProcessInformation
0x14033706e  lea     rax, [rsp+168h+StartupInfo]
0x140337076  mov     [rsp+168h+lpStartupInfo], rax; lpStartupInfo
0x14033707b  mov     [rsp+168h+lpCurrentDirectory], r12; lpCurrentDirectory
0x140337080  mov     [rsp+168h+lpEnvironment], r12; lpEnvironment
0x140337085  mov     [rsp+168h+dwCreationFlags], r12d; dwCreationFlags
0x14033708a  mov     [rsp+168h+bInheritHandles], r12d; bInheritHandles
0x14033708f  xor     r9d, r9d; lpThreadAttributes
0x140337092  xor     r8d, r8d; lpProcessAttributes
0x140337095  mov     rdx, rbx; lpCommandLine
0x140337098  xor     ecx, ecx; lpApplicationName
0x14033709a  call    cs:__imp_CreateProcessW
0x1403370a0  test    eax, eax
0x1403370a2  jnz     short loc_1403370FF
0x1403370a4  mov     rcx, [rsp+168h]; this
0x1403370ac  mov     qword ptr [rsp+168h+dwCreationFlags], rbx
0x1403370b1  mov     qword ptr [rsp+168h+bInheritHandles], rsi; char *
0x1403370b6  lea     r9, aLegacyuoupdate_2; "LegacyUOUpdate unable to invoke callbac"...
0x1403370bd  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403370c4  lea     edx, [rax+57h]; void *
0x1403370c7  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1403370cc  mov     edi, eax
0x1403370ce  lea     rcx, [rsp+168h+ProcessInformation]; this
0x1403370d6  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1403370db  nop
0x1403370dc  test    rbx, rbx
0x1403370df  jz      short loc_1403370EB
0x1403370e1  mov     rcx, rbx; pv
0x1403370e4  call    cs:__imp_CoTaskMemFree
0x1403370ea  nop
0x1403370eb  lea     rcx, [rsp+168h+var_E8]
0x1403370f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403370f8  mov     eax, edi
0x1403370fa  jmp     loc_1403371A0
0x1403370ff  lea     rcx, [rsp+168h+ProcessInformation]; this
0x140337107  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14033710c  nop
0x14033710d  test    rbx, rbx
0x140337110  jz      short loc_14033711C
0x140337112  mov     rcx, rbx; pv
0x140337115  call    cs:__imp_CoTaskMemFree
0x14033711b  nop
0x14033711c  lea     rcx, [rsp+168h+var_E8]
0x140337124  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140337129  xor     eax, eax
0x14033712b  jmp     short loc_1403371A0
0x14033712d  mov     rcx, [rsp+168h]; this
0x140337135  mov     ebx, 80070057h
0x14033713a  mov     r9d, ebx; char *
0x14033713d  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140337144  mov     edx, 2Bh ; '+'; void *
0x140337149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14033714e  mov     eax, ebx
0x140337150  jmp     short loc_1403371A0
0x140337152  mov     rcx, [rsp+168h]; this
0x14033715a  mov     ebx, 80070057h
0x14033715f  mov     r9d, ebx; char *
0x140337162  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140337169  mov     edx, 2Ah ; '*'; void *
0x14033716e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140337173  mov     eax, ebx
0x140337175  jmp     short loc_1403371A0
0x140337177  mov     rcx, [rsp+168h]; this
0x14033717f  mov     ebx, 80070057h
0x140337184  mov     r9d, ebx; char *
0x140337187  lea     r8, aCW1SSrcOrchest_47; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14033718e  mov     edx, 29h ; ')'; void *
0x140337193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140337198  mov     eax, ebx
0x14033719a  jmp     short loc_1403371A0
0x14033719c  mov     eax, dword ptr [rsp+168h+pv]
0x1403371a0  mov     rcx, [rsp+168h+var_38]
0x1403371a8  xor     rcx, rsp; StackCookie
0x1403371ab  call    __security_check_cookie
0x1403371b0  mov     rbx, [rsp+168h+arg_18]
0x1403371b8  add     rsp, 140h
0x1403371bf  pop     r15
0x1403371c1  pop     r14
0x1403371c3  pop     r12
0x1403371c5  pop     rdi
0x1403371c6  pop     rsi
0x1403371c7  retn
```
