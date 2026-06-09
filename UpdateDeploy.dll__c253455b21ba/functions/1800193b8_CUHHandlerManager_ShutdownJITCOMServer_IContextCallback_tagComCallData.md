# CUHHandlerManager::ShutdownJITCOMServer(IContextCallback *,tagComCallData *)

- ea: `0x1800193b8`
- end: `0x18001963b`
- name: `?ShutdownJITCOMServer@CUHHandlerManager@@QEAAJPEAUIContextCallback@@PEAUtagComCallData@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(CUHHandlerManager *__hidden this, struct IContextCallback *, struct tagComCallData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019c38`

## callees

- `0x180003180`
- `0x180007b18`
- `0x180007b9c`
- `0x1800110fc`
- `0x1800193b8`
- `0x18001a90c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019613`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019613`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001957f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001957f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019507`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001945d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800194c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001945d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800194c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019442`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019442`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019603`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019603`

## string_xrefs

- `0x180019515`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019565`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800195c5`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18001949a`: `Software\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUHHandlerManager::ShutdownJITCOMServer(
        CUHHandlerManager *this,
        struct IContextCallback *a2,
        struct tagComCallData *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  unsigned int v10; // eax
  unsigned int v11; // r8d
  const char *v12; // r9
  const char *v13; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  int v17; // [rsp+40h] [rbp-20h] BYREF
  HKEY v18; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v17 = 0;
  hKey = 0;
  v18 = 0;
  v6 = CCoInit::Initialize((CCoInit *)&v17, (unsigned int)a2, 1);
  if ( v6 < 0 )
  {
    v7 = 1193;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    goto LABEL_27;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &hKey) >= 0 )
  {
    v8 = RegDeleteKeyExW(hKey, (LPCWSTR)this + 248, 0, 0);
    if ( v8 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x4B1, v9, (const char *)v8, phkResulta);
  }
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &v18) >= 0 )
  {
    v10 = RegDeleteKeyExW(v18, (LPCWSTR)this + 200, 0, 0);
    if ( v10 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x4BA, v11, (const char *)v10, phkResult);
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = 1213;
    goto LABEL_21;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    v7 = 1214;
    goto LABEL_21;
  }
  if ( !ResetEvent(*((HANDLE *)this + 46)) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x4BF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      v12);
  phkResult = 5;
  v6 = ((__int64 (__fastcall *)(struct IContextCallback *, int (*)(struct tagComCallData *), struct tagComCallData *, GUID *))a2->lpVtbl->ContextCallback)(
         a2,
         DisconnectCallback,
         a3,
         &GUID_000001da_0000_0000_c000_000000000046);
  if ( v6 < 0 )
  {
    v7 = 1217;
    goto LABEL_21;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 46), 0x1388u) == 258 )
    WUTrace(0, 0, 0x1000000, 3, 0, L"UH: DisconnectCallback wait timed out");
  if ( !CloseHandle(*((HANDLE *)this + 46)) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x4C8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      v13);
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 94) = 0;
  v6 = 0;
LABEL_27:
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v17 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800193b8  mov     [rsp-28h+arg_18], rbx
0x1800193bd  push    rbp
0x1800193be  push    rsi
0x1800193bf  push    rdi
0x1800193c0  push    r14
0x1800193c2  push    r15
0x1800193c4  mov     rbp, rsp
0x1800193c7  sub     rsp, 60h
0x1800193cb  mov     rax, cs:__security_cookie
0x1800193d2  xor     rax, rsp
0x1800193d5  mov     [rbp+var_8], rax
0x1800193d9  mov     r14, r8
0x1800193dc  mov     rsi, rdx
0x1800193df  mov     rdi, rcx
0x1800193e2  xor     r15d, r15d
0x1800193e5  mov     [rbp+var_20], r15d
0x1800193e9  mov     [rbp+hKey], r15
0x1800193ed  mov     [rbp+var_18], r15
0x1800193f1  mov     r8b, 1; bool
0x1800193f4  lea     rcx, [rbp+var_20]; this
0x1800193f8  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x1800193fd  mov     ebx, eax
0x1800193ff  test    eax, eax
0x180019401  jns     short loc_18001940D
0x180019403  mov     edx, 4A9h
0x180019408  jmp     loc_18001955E
0x18001940d  mov     rcx, [rbp+hKey]; hKey
0x180019411  test    rcx, rcx
0x180019414  jz      short loc_180019420
0x180019416  call    cs:__imp_RegCloseKey
0x18001941c  mov     [rbp+hKey], r15
0x180019420  lea     rax, [rbp+hKey]
0x180019424  mov     [rsp+60h+phkResult], rax; unsigned int
0x180019429  mov     ebx, 20006h
0x18001942e  mov     r9d, ebx; samDesired
0x180019431  xor     r8d, r8d; ulOptions
0x180019434  lea     rdx, SubKey; "Software\\Classes\\AppID"
0x18001943b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019442  call    cs:__imp_RegOpenKeyExW
0x180019448  test    eax, eax
0x18001944a  js      short loc_180019478
0x18001944c  lea     rdx, [rdi+1F0h]; lpSubKey
0x180019453  xor     r9d, r9d; Reserved
0x180019456  xor     r8d, r8d; samDesired
0x180019459  mov     rcx, [rbp+hKey]; hKey
0x18001945d  call    cs:__imp_RegDeleteKeyExW
0x180019463  mov     rcx, [rbp+28h]; this
0x180019467  test    eax, eax
0x180019469  jz      short loc_180019478
0x18001946b  mov     r9d, eax; char *
0x18001946e  mov     edx, 4B1h; void *
0x180019473  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180019478  mov     rcx, [rbp+var_18]; hKey
0x18001947c  test    rcx, rcx
0x18001947f  jz      short loc_18001948B
0x180019481  call    cs:__imp_RegCloseKey
0x180019487  mov     [rbp+var_18], r15
0x18001948b  lea     rax, [rbp+var_18]
0x18001948f  mov     [rsp+60h+phkResult], rax; unsigned int
0x180019494  mov     r9d, ebx; samDesired
0x180019497  xor     r8d, r8d; ulOptions
0x18001949a  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x1800194a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800194a8  call    cs:__imp_RegOpenKeyExW
0x1800194ae  test    eax, eax
0x1800194b0  js      short loc_1800194DE
0x1800194b2  lea     rdx, [rdi+190h]; lpSubKey
0x1800194b9  xor     r9d, r9d; Reserved
0x1800194bc  xor     r8d, r8d; samDesired
0x1800194bf  mov     rcx, [rbp+var_18]; hKey
0x1800194c3  call    cs:__imp_RegDeleteKeyExW
0x1800194c9  mov     rcx, [rbp+28h]; this
0x1800194cd  test    eax, eax
0x1800194cf  jz      short loc_1800194DE
0x1800194d1  mov     r9d, eax; char *
0x1800194d4  mov     edx, 4BAh; void *
0x1800194d9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800194de  test    rsi, rsi
0x1800194e1  jnz     short loc_1800194EF
0x1800194e3  mov     ebx, 80004003h
0x1800194e8  mov     edx, 4BDh
0x1800194ed  jmp     short loc_18001955E
0x1800194ef  test    r14, r14
0x1800194f2  jnz     short loc_180019500
0x1800194f4  mov     ebx, 80004003h
0x1800194f9  mov     edx, 4BEh
0x1800194fe  jmp     short loc_18001955E
0x180019500  mov     rcx, [rdi+170h]; hEvent
0x180019507  call    cs:__imp_ResetEvent
0x18001950d  mov     rcx, [rbp+28h]; this
0x180019511  test    eax, eax
0x180019513  jnz     short loc_180019526
0x180019515  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001951c  mov     edx, 4BFh; void *
0x180019521  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180019526  mov     rax, [rsi]
0x180019529  mov     [rsp+60h+var_38], r15
0x18001952e  mov     dword ptr [rsp+60h+phkResult], 5; int
0x180019536  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x18001953d  mov     r8, r14
0x180019540  lea     rdx, ?DisconnectCallback@@YAJPEAUtagComCallData@@@Z; DisconnectCallback(tagComCallData *)
0x180019547  mov     rcx, rsi
0x18001954a  mov     rax, [rax+18h]
0x18001954e  call    _guard_dispatch_icall
0x180019553  mov     ebx, eax
0x180019555  test    eax, eax
0x180019557  jns     short loc_180019573
0x180019559  mov     edx, 4C1h; void *
0x18001955e  mov     rcx, [rbp+28h]; this
0x180019562  mov     r9d, ebx; char *
0x180019565  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001956c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019571  jmp     short loc_1800195E7
0x180019573  mov     edx, 1388h; dwMilliseconds
0x180019578  mov     rcx, [rdi+170h]; hHandle
0x18001957f  call    cs:__imp_WaitForSingleObject
0x180019585  cmp     eax, 102h
0x18001958a  jnz     short loc_1800195B0
0x18001958c  lea     rax, aUhDisconnectca; "UH: DisconnectCallback wait timed out"
0x180019593  mov     [rsp+60h+var_38], rax
0x180019598  mov     [rsp+60h+phkResult], r15
0x18001959d  xor     edx, edx
0x18001959f  xor     ecx, ecx
0x1800195a1  lea     r9d, [rdx+3]
0x1800195a5  mov     r8d, 1000000h
0x1800195ab  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800195b0  mov     rcx, [rdi+170h]; hObject
0x1800195b7  call    cs:__imp_CloseHandle
0x1800195bd  mov     rcx, [rbp+28h]; this
0x1800195c1  test    eax, eax
0x1800195c3  jnz     short loc_1800195D6
0x1800195c5  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800195cc  mov     edx, 4C8h; void *
0x1800195d1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800195d6  mov     [rdi+170h], r15
0x1800195dd  mov     [rdi+178h], r15d
0x1800195e4  mov     ebx, r15d
0x1800195e7  mov     rcx, [rbp+var_18]; hKey
0x1800195eb  test    rcx, rcx
0x1800195ee  jz      short loc_1800195FA
0x1800195f0  call    cs:__imp_RegCloseKey
0x1800195f6  mov     [rbp+var_18], r15
0x1800195fa  mov     rcx, [rbp+hKey]; hKey
0x1800195fe  test    rcx, rcx
0x180019601  jz      short loc_18001960D
0x180019603  call    cs:__imp_RegCloseKey
0x180019609  mov     [rbp+hKey], r15
0x18001960d  cmp     [rbp+var_20], r15d
0x180019611  jz      short loc_180019619
0x180019613  call    cs:__imp_CoUninitialize
0x180019619  mov     eax, ebx
0x18001961b  mov     rcx, [rbp+var_8]
0x18001961f  xor     rcx, rsp; StackCookie
0x180019622  call    __security_check_cookie
0x180019627  mov     rbx, [rsp+60h+arg_18]
0x18001962f  add     rsp, 60h
0x180019633  pop     r15
0x180019635  pop     r14
0x180019637  pop     rdi
0x180019638  pop     rsi
0x180019639  pop     rbp
0x18001963a  retn
```
