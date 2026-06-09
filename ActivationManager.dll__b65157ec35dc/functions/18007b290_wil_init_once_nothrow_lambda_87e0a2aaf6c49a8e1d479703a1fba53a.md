# wil::init_once_nothrow__lambda_87e0a2aaf6c49a8e1d479703a1fba53a___

- ea: `0x18007b290`
- end: `0x18007b39c`
- name: `wil::init_once_nothrow__lambda_87e0a2aaf6c49a8e1d479703a1fba53a___`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007b3a4`

## callees

- `0x18000b5c0`
- `0x180044408`
- `0x180044514`
- `0x180047048`
- `0x180047068`
- `0x18007b290`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007b2b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007b2b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b378`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b38e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b378`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b38e`
- `RMCLIENT!HamConnectToServer` at `0x18007b328`
- `RMCLIENT!HamConnectToServer` at `0x18007b328`
- `RMCLIENT!HamDisconnectFromServer` at `0x18007b2ff`
- `RMCLIENT!HamDisconnectFromServer` at `0x18007b2ff`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_87e0a2aaf6c49a8e1d479703a1fba53a___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  void *v5; // rbx
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL v12; // [rsp+38h] [rbp+10h] BYREF
  __int64 v13; // [rsp+40h] [rbp+18h] BYREF

  v13 = a3;
  v12 = 0;
  if ( !__std_init_once_begin_initialize(&s_HamConnectionInit, 0, &v12, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( v12 )
  {
    v5 = s_hamConnectionContext;
    if ( s_hamConnectionContext )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
      HamDisconnectFromServer(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
    }
    s_hamConnectionContext = 0;
    v6 = HamConnectToServer(HamActivityWrapper::HamCallback, &s_hamConnectionContext);
    if ( v6 < 0 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x26,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
             (const char *)(unsigned int)v6,
             v9);
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"wil",
          (const char *)(unsigned int)v7,
          v10);
        InitOnceComplete(&s_HamConnectionInit, 4u, 0);
        return v8;
      }
    }
    InitOnceComplete(&s_HamConnectionInit, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007b290  mov     rax, rsp
0x18007b293  mov     [rax+18h], r8
0x18007b297  mov     [rax+10h], dl
0x18007b29a  push    rbx; int
0x18007b29b  sub     rsp, 20h
0x18007b29f  xor     r9d, r9d; lpContext
0x18007b2a2  mov     dword ptr [rax+10h], 0
0x18007b2a9  lea     r8, [rax+10h]; fPending
0x18007b2ad  xor     edx, edx; dwFlags
0x18007b2af  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b2b6  call    cs:__imp___std_init_once_begin_initialize
0x18007b2bc  test    eax, eax
0x18007b2be  jnz     short loc_18007B2DB
0x18007b2c0  mov     rcx, [rsp+28h]; this
0x18007b2c5  lea     r8, aWil; "wil"
0x18007b2cc  mov     edx, 37Ah; void *
0x18007b2d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007b2d6  jmp     loc_18007B396
0x18007b2db  cmp     [rsp+28h+arg_8], 0
0x18007b2e0  jz      loc_18007B394
0x18007b2e6  mov     rbx, cs:?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b2ed  test    rbx, rbx
0x18007b2f0  jz      short loc_18007B30F
0x18007b2f2  lea     rcx, [rsp+28h+arg_10]; this
0x18007b2f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b2fc  mov     rcx, rbx
0x18007b2ff  call    cs:__imp_HamDisconnectFromServer
0x18007b305  lea     rcx, [rsp+28h+arg_10]; this
0x18007b30a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b30f  lea     rdx, ?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b316  mov     cs:?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b321  lea     rcx, ?HamCallback@HamActivityWrapper@@SAXPEAU_HAM_ACTIVITY_CALLBACK_PAYLOAD@@@Z; HamActivityWrapper::HamCallback(_HAM_ACTIVITY_CALLBACK_PAYLOAD *)
0x18007b328  call    cs:__imp_HamConnectToServer
0x18007b32e  test    eax, eax
0x18007b330  jns     short loc_18007B382
0x18007b332  mov     rcx, [rsp+28h]; this
0x18007b337  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007b33e  mov     r9d, eax; char *
0x18007b341  mov     edx, 26h ; '&'; void *
0x18007b346  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007b34b  mov     ebx, eax
0x18007b34d  test    eax, eax
0x18007b34f  jns     short loc_18007B382
0x18007b351  mov     rcx, [rsp+28h]; this
0x18007b356  lea     r8, aWil; "wil"
0x18007b35d  mov     r9d, eax; char *
0x18007b360  mov     edx, 37Fh; void *
0x18007b365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b36a  xor     r8d, r8d; lpContext
0x18007b36d  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b374  lea     edx, [r8+4]; dwFlags
0x18007b378  call    cs:__imp_InitOnceComplete
0x18007b37e  mov     eax, ebx
0x18007b380  jmp     short loc_18007B396
0x18007b382  xor     r8d, r8d; lpContext
0x18007b385  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b38c  xor     edx, edx; dwFlags
0x18007b38e  call    cs:__imp_InitOnceComplete
0x18007b394  xor     eax, eax
0x18007b396  add     rsp, 20h
0x18007b39a  pop     rbx
0x18007b39b  retn
```
