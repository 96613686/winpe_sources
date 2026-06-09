# Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(ushort const *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::CoTaskMemFreeDeleter> &)

- ea: `0x180023c50`
- end: `0x180023ff7`
- name: `?GetAppContainerFolderPathFromPfn@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEBGAEAV?$unique_ptr@PEAXUCoTaskMemFreeDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800750c0`
- `0x1800d4e70`

## callees

- `0x18000bd40`
- `0x180023c50`
- `0x180024000`
- `0x1800349d0`
- `0x1800565a0`
- `0x18007c220`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023c99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023c99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023cb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023cb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180023d39`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180023d39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023fe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023df3`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023d6b`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023e41`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023f11`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023f71`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023fbe`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023d6b`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023e41`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023f11`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023f71`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180023fbe`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x180023dcc`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x180023e06`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x180023dcc`
- `api-ms-win-appmodel-state-l1-2-0!GetStateRootFolder` at `0x180023e06`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180023cf1`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180023cf1`

## string_xrefs

- `0x180023d0c`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180023e14`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180023ee9`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180023f22`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180023f9b`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(
        __int64 a1,
        void **a2)
{
  bool v4; // zf
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  BOOL v7; // r14d
  void *v8; // rdi
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // rsi
  __int64 v12; // rdx
  unsigned int LastError; // ebx
  __int64 v15; // rax
  void *v16; // rcx
  HANDLE CurrentProcess; // rax
  BOOL v18; // ebx
  const char *v19; // r9
  _WORD *v20; // rbx
  const char *v21; // r9
  unsigned int v22; // edi
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  _WORD *v26; // rax
  __int64 v27; // r8
  const wchar_t *v28; // rdx
  _WORD *i; // rax
  _WORD *v30; // rcx
  unsigned int v31; // ebx
  void *TokenHandle; // [rsp+28h] [rbp-18h] BYREF
  char v33; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v35; // [rsp+80h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+48h] BYREF

  v35 = 0;
  hObject = 0;
  v4 = NtCurrentTeb()->IsImpersonating == 0;
  TokenHandle = 0;
  v33 = 1;
  if ( v4 )
  {
    CurrentProcess = GetCurrentProcess();
    v18 = OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle);
    if ( v33 )
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        TokenHandle);
    if ( !v18 )
    {
      v12 = 177;
      goto LABEL_9;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    v7 = OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle);
    if ( v33 )
    {
      v8 = TokenHandle;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hObject);
      hObject = v8;
    }
    if ( !v7 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xAD,
                    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
                    v6);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return LastError;
    }
  }
  v9 = OpenStateExplicit(hObject, a1);
  v11 = v9;
  if ( !v9 )
  {
    v12 = 181;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
                  v10);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&hObject);
    return LastError;
  }
  if ( (unsigned int)GetStateRootFolder(v9, 0, &v35) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)0x8000FFFFLL,
      (int)&hObject);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&hObject);
    CloseState(v11);
    return 2147549183LL;
  }
  else if ( GetLastError() == 122 )
  {
    v20 = CoTaskMemAlloc((unsigned int)(2 * v35 + 10));
    if ( (unsigned int)GetStateRootFolder(v11, v20, &v35) )
    {
      v23 = 2147483646;
      v24 = (unsigned int)(v35 + 5);
      if ( (unsigned __int64)(v24 - 1) <= 0x7FFFFFFE )
      {
        v25 = (unsigned int)v24;
        v26 = v20;
        do
        {
          if ( !*v26 )
          {
            v15 = v24 - v25;
            goto LABEL_12;
          }
          ++v26;
          --v25;
        }
        while ( v25 );
        v15 = 0;
LABEL_12:
        if ( v25 )
        {
          v27 = v24 - v15;
          v28 = L"\\AC";
          for ( i = &v20[v15]; v27; --v27 )
          {
            if ( !v23 )
              break;
            if ( !*v28 )
              break;
            *i++ = *v28++;
            --v23;
          }
          v30 = i - 1;
          if ( v27 )
            v30 = i;
          *v30 = 0;
        }
      }
      if ( PathFileExistsW(v20) )
      {
        v16 = *a2;
        *a2 = v20;
        if ( v16 )
          CoTaskMemFree(v16);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        CloseState(v11);
        return 0;
      }
      else
      {
        if ( v20 )
          CoTaskMemFree(v20);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        CloseState(v11);
        return 2147942402LL;
      }
    }
    else
    {
      v22 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xBB,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
              v21);
      if ( v20 )
        CoTaskMemFree(v20);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&hObject);
      CloseState(v11);
      return v22;
    }
  }
  else
  {
    v31 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xB8,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
            v19);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CloseState(v11);
    return v31;
  }
}

```

## disassembly

```asm
0x180023c50  mov     [rsp-28h+arg_8], rbx
0x180023c55  push    rbp
0x180023c56  push    rsi
0x180023c57  push    rdi
0x180023c58  push    r12
0x180023c5a  push    r15
0x180023c5c  mov     rbp, rsp
0x180023c5f  sub     rsp, 40h
0x180023c63  xor     r12d, r12d
0x180023c66  mov     r15, rdx
0x180023c69  mov     [rbp+arg_10], r12d
0x180023c6d  mov     rsi, rcx
0x180023c70  mov     [rbp+hObject], r12
0x180023c74  mov     eax, gs:179Ch
0x180023c7c  test    eax, eax
0x180023c7e  lea     rax, [rbp+hObject]
0x180023c82  mov     [rbp+TokenHandle], r12
0x180023c86  mov     [rbp+var_20], rax
0x180023c8a  mov     [rbp+var_10], 1
0x180023c8e  jz      loc_180023D84
0x180023c94  mov     [rsp+40h+arg_0], r14
0x180023c99  call    cs:__imp_GetCurrentThread
0x180023c9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023ca3  mov     edx, 2000000h; DesiredAccess
0x180023ca8  mov     rcx, rax; ThreadHandle
0x180023cab  mov     r8d, 1; OpenAsSelf
0x180023cb1  call    cs:__imp_OpenThreadToken
0x180023cb7  mov     r14d, eax
0x180023cba  cmp     [rbp+var_10], r12b
0x180023cbe  jz      short loc_180023CDC
0x180023cc0  mov     rbx, [rbp+var_20]
0x180023cc4  mov     rdi, [rbp+TokenHandle]
0x180023cc8  mov     rcx, [rbx]; hObject
0x180023ccb  lea     rdx, [rcx-1]
0x180023ccf  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180023cd3  jbe     loc_180023F8D
0x180023cd9  mov     [rbx], rdi
0x180023cdc  test    r14d, r14d
0x180023cdf  mov     r14, [rsp+40h+arg_0]
0x180023ce4  jz      loc_180023F1E
0x180023cea  mov     rcx, [rbp+hObject]
0x180023cee  mov     rdx, rsi
0x180023cf1  call    cs:__imp_OpenStateExplicit
0x180023cf7  mov     rsi, rax
0x180023cfa  test    rax, rax
0x180023cfd  jnz     loc_180023DC3
0x180023d03  mov     edx, 0B5h; void *
0x180023d08  mov     rcx, [rbp+28h]; this
0x180023d0c  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180023d13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023d18  lea     rcx, [rbp+hObject]; this
0x180023d1c  mov     ebx, eax
0x180023d1e  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180023d23  mov     eax, ebx
0x180023d25  jmp     short loc_180023D73
0x180023d27  mov     rax, r8
0x180023d2a  sub     rax, rcx
0x180023d2d  test    rcx, rcx
0x180023d30  jnz     loc_180023E9C
0x180023d36  mov     rcx, rbx; pszPath
0x180023d39  call    cs:__imp_PathFileExistsW
0x180023d3f  test    eax, eax
0x180023d41  jz      loc_180023F52
0x180023d47  mov     rcx, [r15]; pv
0x180023d4a  mov     [r15], rbx
0x180023d4d  test    rcx, rcx
0x180023d50  jnz     loc_180023FE1
0x180023d56  mov     rcx, [rbp+hObject]; hObject
0x180023d5a  lea     rax, [rcx-1]
0x180023d5e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023d62  jbe     loc_180023FEC
0x180023d68  mov     rcx, rsi
0x180023d6b  call    cs:__imp_CloseState
0x180023d71  xor     eax, eax
0x180023d73  mov     rbx, [rsp+40h+arg_8]
0x180023d78  add     rsp, 40h
0x180023d7c  pop     r15
0x180023d7e  pop     r12
0x180023d80  pop     rdi
0x180023d81  pop     rsi
0x180023d82  pop     rbp
0x180023d83  retn
0x180023d84  call    cs:__imp_GetCurrentProcess
0x180023d8a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180023d8e  mov     edx, 2000000h; DesiredAccess
0x180023d93  mov     rcx, rax; ProcessHandle
0x180023d96  call    cs:__imp_OpenProcessToken
0x180023d9c  mov     ebx, eax
0x180023d9e  cmp     [rbp+var_10], r12b
0x180023da2  jz      short loc_180023DB1
0x180023da4  mov     rdx, [rbp+TokenHandle]
0x180023da8  mov     rcx, [rbp+var_20]
0x180023dac  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023db1  test    ebx, ebx
0x180023db3  jnz     loc_180023CEA
0x180023db9  mov     edx, 0B1h
0x180023dbe  jmp     loc_180023D08
0x180023dc3  lea     r8, [rbp+arg_10]
0x180023dc7  xor     edx, edx
0x180023dc9  mov     rcx, rsi
0x180023dcc  call    cs:__imp_GetStateRootFolder
0x180023dd2  test    eax, eax
0x180023dd4  jnz     loc_180023F97
0x180023dda  call    cs:__imp_GetLastError
0x180023de0  cmp     eax, 7Ah ; 'z'
0x180023de3  jnz     loc_180023EE5
0x180023de9  mov     eax, [rbp+arg_10]
0x180023dec  lea     ecx, ds:0Ah[rax*2]; cb
0x180023df3  call    cs:__imp_CoTaskMemAlloc
0x180023df9  lea     r8, [rbp+arg_10]
0x180023dfd  mov     rcx, rsi
0x180023e00  mov     rdx, rax
0x180023e03  mov     rbx, rax
0x180023e06  call    cs:__imp_GetStateRootFolder
0x180023e0c  test    eax, eax
0x180023e0e  jnz     short loc_180023E5A
0x180023e10  mov     rcx, [rbp+28h]; this
0x180023e14  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180023e1b  mov     edx, 0BBh; void *
0x180023e20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e25  mov     edi, eax
0x180023e27  test    rbx, rbx
0x180023e2a  jz      short loc_180023E35
0x180023e2c  mov     rcx, rbx; pv
0x180023e2f  call    cs:__imp_CoTaskMemFree
0x180023e35  lea     rcx, [rbp+hObject]; this
0x180023e39  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180023e3e  mov     rcx, rsi
0x180023e41  call    cs:__imp_CloseState
0x180023e47  mov     eax, edi
0x180023e49  mov     rbx, [rsp+40h+arg_8]
0x180023e4e  add     rsp, 40h
0x180023e52  pop     r15
0x180023e54  pop     r12
0x180023e56  pop     rdi
0x180023e57  pop     rsi
0x180023e58  pop     rbp
0x180023e59  retn
0x180023e5a  mov     eax, [rbp+arg_10]
0x180023e5d  mov     r9d, 7FFFFFFEh
0x180023e63  add     eax, 5
0x180023e66  mov     r8d, eax
0x180023e69  dec     rax
0x180023e6c  cmp     rax, r9
0x180023e6f  ja      loc_180023D36
0x180023e75  mov     ecx, r8d
0x180023e78  mov     rax, rbx
0x180023e7b  nop     dword ptr [rax+rax+00h]
0x180023e80  cmp     [rax], r12w
0x180023e84  jz      loc_180023D27
0x180023e8a  add     rax, 2
0x180023e8e  sub     rcx, 1
0x180023e92  jnz     short loc_180023E80
0x180023e94  mov     rax, r12
0x180023e97  jmp     loc_180023D2D
0x180023e9c  sub     r8, rax
0x180023e9f  lea     rdx, aAc; "\\AC"
0x180023ea6  lea     rax, [rbx+rax*2]
0x180023eaa  jz      short loc_180023ED1
0x180023eac  nop     dword ptr [rax+00h]
0x180023eb0  test    r9, r9
0x180023eb3  jz      short loc_180023ED1
0x180023eb5  movzx   ecx, word ptr [rdx]
0x180023eb8  test    cx, cx
0x180023ebb  jz      short loc_180023ED1
0x180023ebd  mov     [rax], cx
0x180023ec0  add     rdx, 2
0x180023ec4  add     rax, 2
0x180023ec8  dec     r9
0x180023ecb  sub     r8, 1
0x180023ecf  jnz     short loc_180023EB0
0x180023ed1  test    r8, r8
0x180023ed4  lea     rcx, [rax-2]
0x180023ed8  cmovnz  rcx, rax
0x180023edc  mov     [rcx], r12w
0x180023ee0  jmp     loc_180023D36
0x180023ee5  mov     rcx, [rbp+28h]; this
0x180023ee9  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180023ef0  mov     edx, 0B8h; void *
0x180023ef5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023efa  mov     rcx, [rbp+hObject]; hObject
0x180023efe  mov     ebx, eax
0x180023f00  lea     rdx, [rcx-1]
0x180023f04  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180023f08  jbe     loc_180023FCE
0x180023f0e  mov     rcx, rsi
0x180023f11  call    cs:__imp_CloseState
0x180023f17  mov     eax, ebx
0x180023f19  jmp     loc_180023D73
0x180023f1e  mov     rcx, [rbp+28h]; this
0x180023f22  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180023f29  mov     edx, 0ADh; void *
0x180023f2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023f33  mov     rcx, [rbp+hObject]; hObject
0x180023f37  mov     ebx, eax
0x180023f39  lea     rdx, [rcx-1]
0x180023f3d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180023f41  ja      loc_180023D23
0x180023f47  call    cs:__imp_CloseHandle
0x180023f4d  jmp     loc_180023D23
0x180023f52  test    rbx, rbx
0x180023f55  jz      short loc_180023F60
0x180023f57  mov     rcx, rbx; pv
0x180023f5a  call    cs:__imp_CoTaskMemFree
0x180023f60  mov     rcx, [rbp+hObject]; hObject
0x180023f64  lea     rax, [rcx-1]
0x180023f68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023f6c  jbe     short loc_180023FD9
0x180023f6e  mov     rcx, rsi
0x180023f71  call    cs:__imp_CloseState
0x180023f77  mov     rbx, [rsp+40h+arg_8]
0x180023f7c  mov     eax, 80070002h
0x180023f81  add     rsp, 40h
0x180023f85  pop     r15
0x180023f87  pop     r12
0x180023f89  pop     rdi
0x180023f8a  pop     rsi
0x180023f8b  pop     rbp
0x180023f8c  retn
0x180023f8d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180023f92  jmp     loc_180023CD9
0x180023f97  mov     rcx, [rbp+28h]; this
0x180023f9b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180023fa2  mov     r9d, 8000FFFFh; char *
0x180023fa8  mov     edx, 0B7h; void *
0x180023fad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fb2  lea     rcx, [rbp+hObject]; this
0x180023fb6  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180023fbb  mov     rcx, rsi
0x180023fbe  call    cs:__imp_CloseState
0x180023fc4  mov     eax, 8000FFFFh
0x180023fc9  jmp     loc_180023D73
0x180023fce  call    cs:__imp_CloseHandle
0x180023fd4  jmp     loc_180023F0E
0x180023fd9  call    cs:__imp_CloseHandle
0x180023fdf  jmp     short loc_180023F6E
0x180023fe1  call    cs:__imp_CoTaskMemFree
0x180023fe7  jmp     loc_180023D56
0x180023fec  call    cs:__imp_CloseHandle
0x180023ff2  jmp     loc_180023D68
```
