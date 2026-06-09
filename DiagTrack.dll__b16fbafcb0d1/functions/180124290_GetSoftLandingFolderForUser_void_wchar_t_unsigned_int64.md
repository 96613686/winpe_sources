# GetSoftLandingFolderForUser(void *,wchar_t *,unsigned __int64)

- ea: `0x180124290`
- end: `0x18012443c`
- name: `?GetSoftLandingFolderForUser@@YAJPEAXPEA_W_K@Z`
- size: `428`
- prototype: `__int64 __fastcall(HANDLE hToken, WCHAR *lpPathName, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012417c`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x180124290`
- `0x1801ddba8`
- `0x1802364a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012434e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012434e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180124344`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180124344`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18012431e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18012431e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180124361`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801243e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180124361`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801243e1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180124331`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180124331`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x180124372`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x1801243d0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x180124372`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseState` at `0x1801243d0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1801242cb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1801242cb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x1801242fc`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x1801242fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall GetSoftLandingFolderForUser(HANDLE hToken, WCHAR *lpPathName, __int64 a3)
{
  __int64 v5; // rax
  const char *v6; // r9
  __int64 v7; // rbx
  const char *v8; // r9
  HRESULT v9; // eax
  HRESULT v10; // esi
  DWORD v11; // edi
  __int64 v13; // rdx
  unsigned int v14; // edi
  int LastError; // eax
  unsigned int v16; // ebx
  unsigned int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v19; // [rsp+50h] [rbp+18h] BYREF
  __int64 v20; // [rsp+58h] [rbp+20h] BYREF

  v19 = a3;
  if ( !(unsigned __int8)IsOpenStateExplicitPresent() || !(unsigned __int8)IsOpenStateExplicitPresent() )
    return 2147942527LL;
  v5 = OpenStateExplicit(hToken, L"Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy");
  v20 = v5;
  v7 = v5;
  if ( !v5 )
  {
    v13 = 22;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
                  v6);
    goto LABEL_24;
  }
  v19 = 260;
  if ( !(unsigned int)GetStateFolder(v5, 1, lpPathName, &v19) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x19,
            (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
            v8);
LABEL_15:
    CloseState(v7);
    return v14;
  }
  v19 = 260;
  v9 = PathCchCombine(lpPathName, 0x104u, lpPathName, L"Tips");
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
      (const char *)(unsigned int)v9,
      v17);
    v14 = v10;
    goto LABEL_15;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v13 = 31;
    goto LABEL_23;
  }
  if ( CreateDirectoryW(lpPathName, 0) || (v11 = GetLastError(), v11 == 183) )
  {
    if ( RevertToSelf() )
    {
      CloseState(v7);
      return 0;
    }
    v13 = 43;
    goto LABEL_23;
  }
  if ( !RevertToSelf() )
  {
    v13 = 38;
    goto LABEL_23;
  }
  if ( v11 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x27,
                  (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
                  (const char *)v11,
                  v17);
LABEL_24:
    v16 = LastError;
    goto LABEL_25;
  }
  v16 = 0;
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v20);
  return v16;
}

```

## disassembly

```asm
0x180124290  mov     [rsp+arg_0], rbx
0x180124295  mov     [rsp+arg_10], r8
0x18012429a  push    rbp
0x18012429b  push    rsi
0x18012429c  push    rdi; unsigned int
0x18012429d  sub     rsp, 20h
0x1801242a1  mov     rdi, rdx
0x1801242a4  mov     rbp, rcx
0x1801242a7  call    IsOpenStateExplicitPresent
0x1801242ac  test    al, al
0x1801242ae  jz      loc_180124387
0x1801242b4  call    IsOpenStateExplicitPresent
0x1801242b9  test    al, al
0x1801242bb  jz      loc_180124387
0x1801242c1  lea     rdx, ?c_ContentDeliveryManagerPackageFamilyName@Shared@CreativeFramework@@3QBGB; "Microsoft.Windows.ContentDeliveryManage"...
0x1801242c8  mov     rcx, rbp
0x1801242cb  call    cs:__imp_OpenStateExplicit
0x1801242d1  mov     [rsp+38h+arg_18], rax
0x1801242d6  mov     rbx, rax
0x1801242d9  test    rax, rax
0x1801242dc  jz      loc_18012438E
0x1801242e2  mov     esi, 104h
0x1801242e7  lea     r9, [rsp+38h+arg_10]
0x1801242ec  mov     r8, rdi
0x1801242ef  mov     [rsp+38h+arg_10], rsi
0x1801242f4  mov     edx, 1
0x1801242f9  mov     rcx, rax
0x1801242fc  call    cs:__imp_GetStateFolder
0x180124302  test    eax, eax
0x180124304  jz      loc_180124398
0x18012430a  lea     r9, aTips; "Tips"
0x180124311  mov     [rsp+38h+arg_10], rsi
0x180124316  mov     r8, rdi; pszPathIn
0x180124319  mov     edx, esi; cchPathOut
0x18012431b  mov     rcx, rdi; pszPathOut
0x18012431e  call    cs:__imp_PathCchCombine
0x180124324  mov     esi, eax
0x180124326  test    eax, eax
0x180124328  js      loc_1801243B2
0x18012432e  mov     rcx, rbp; hToken
0x180124331  call    cs:__imp_ImpersonateLoggedOnUser
0x180124337  test    eax, eax
0x180124339  jz      loc_1801243DA
0x18012433f  xor     edx, edx; lpSecurityAttributes
0x180124341  mov     rcx, rdi; lpPathName
0x180124344  call    cs:__imp_CreateDirectoryW
0x18012434a  test    eax, eax
0x18012434c  jnz     short loc_180124361
0x18012434e  call    cs:__imp_GetLastError
0x180124354  mov     edi, eax
0x180124356  cmp     eax, 0B7h
0x18012435b  jnz     loc_1801243E1
0x180124361  call    cs:__imp_RevertToSelf
0x180124367  test    eax, eax
0x180124369  jz      loc_180124413
0x18012436f  mov     rcx, rbx
0x180124372  call    cs:__imp_CloseState
0x180124378  xor     eax, eax
0x18012437a  mov     rbx, [rsp+38h+arg_0]
0x18012437f  add     rsp, 20h
0x180124383  pop     rdi
0x180124384  pop     rsi
0x180124385  pop     rbp
0x180124386  retn
0x180124387  mov     eax, 8007007Fh
0x18012438c  jmp     short loc_18012437A
0x18012438e  mov     edx, 16h
0x180124393  jmp     loc_180124418
0x180124398  mov     rcx, [rsp+38h]; this
0x18012439d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x1801243a4  mov     edx, 19h; void *
0x1801243a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801243ae  mov     edi, eax
0x1801243b0  jmp     short loc_1801243CD
0x1801243b2  mov     rcx, [rsp+38h]; this
0x1801243b7  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x1801243be  mov     r9d, esi; char *
0x1801243c1  mov     edx, 1Dh; void *
0x1801243c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801243cb  mov     edi, esi
0x1801243cd  mov     rcx, rbx
0x1801243d0  call    cs:__imp_CloseState
0x1801243d6  mov     eax, edi
0x1801243d8  jmp     short loc_18012437A
0x1801243da  mov     edx, 1Fh
0x1801243df  jmp     short loc_180124418
0x1801243e1  call    cs:__imp_RevertToSelf
0x1801243e7  test    eax, eax
0x1801243e9  jnz     short loc_1801243F0
0x1801243eb  lea     edx, [rax+26h]
0x1801243ee  jmp     short loc_180124418
0x1801243f0  test    edi, edi
0x1801243f2  jz      short loc_18012440F
0x1801243f4  mov     rcx, [rsp+38h]; this
0x1801243f9  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x180124400  mov     r9d, edi; char *
0x180124403  mov     edx, 27h ; '''; void *
0x180124408  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18012440d  jmp     short loc_180124429
0x18012440f  xor     ebx, ebx
0x180124411  jmp     short loc_18012442B
0x180124413  mov     edx, 2Bh ; '+'; void *
0x180124418  mov     rcx, [rsp+38h]; this
0x18012441d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x180124424  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180124429  mov     ebx, eax
0x18012442b  lea     rcx, [rsp+38h+arg_18]
0x180124430  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180124435  mov     eax, ebx
0x180124437  jmp     loc_18012437A
```
