# wil::init_once_nothrow__lambda_17dd76c73f987773c5982a698c2403da___

- ea: `0x18007b17c`
- end: `0x18007b288`
- name: `wil::init_once_nothrow__lambda_17dd76c73f987773c5982a698c2403da___`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007b560`

## callees

- `0x18000b5c0`
- `0x180044408`
- `0x180044514`
- `0x180047048`
- `0x180047068`
- `0x18007b17c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007b1a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007b1a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b264`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b27a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b264`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007b27a`
- `RMCLIENT!HamConnectToServer` at `0x18007b214`
- `RMCLIENT!HamConnectToServer` at `0x18007b214`
- `RMCLIENT!HamDisconnectFromServer` at `0x18007b1eb`
- `RMCLIENT!HamDisconnectFromServer` at `0x18007b1eb`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_17dd76c73f987773c5982a698c2403da___(
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
             (void *)0x114,
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
0x18007b17c  mov     rax, rsp
0x18007b17f  mov     [rax+18h], r8
0x18007b183  mov     [rax+10h], dl
0x18007b186  push    rbx; int
0x18007b187  sub     rsp, 20h
0x18007b18b  xor     r9d, r9d; lpContext
0x18007b18e  mov     dword ptr [rax+10h], 0
0x18007b195  lea     r8, [rax+10h]; fPending
0x18007b199  xor     edx, edx; dwFlags
0x18007b19b  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b1a2  call    cs:__imp___std_init_once_begin_initialize
0x18007b1a8  test    eax, eax
0x18007b1aa  jnz     short loc_18007B1C7
0x18007b1ac  mov     rcx, [rsp+28h]; this
0x18007b1b1  lea     r8, aWil; "wil"
0x18007b1b8  mov     edx, 37Ah; void *
0x18007b1bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007b1c2  jmp     loc_18007B282
0x18007b1c7  cmp     [rsp+28h+arg_8], 0
0x18007b1cc  jz      loc_18007B280
0x18007b1d2  mov     rbx, cs:?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b1d9  test    rbx, rbx
0x18007b1dc  jz      short loc_18007B1FB
0x18007b1de  lea     rcx, [rsp+28h+arg_10]; this
0x18007b1e3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b1e8  mov     rcx, rbx
0x18007b1eb  call    cs:__imp_HamDisconnectFromServer
0x18007b1f1  lea     rcx, [rsp+28h+arg_10]; this
0x18007b1f6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b1fb  lea     rdx, ?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b202  mov     cs:?s_hamConnectionContext@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?HamDisconnectFromServer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&HamDisconnectFromServer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> s_hamConnectionContext
0x18007b20d  lea     rcx, ?HamCallback@HamActivityWrapper@@SAXPEAU_HAM_ACTIVITY_CALLBACK_PAYLOAD@@@Z; HamActivityWrapper::HamCallback(_HAM_ACTIVITY_CALLBACK_PAYLOAD *)
0x18007b214  call    cs:__imp_HamConnectToServer
0x18007b21a  test    eax, eax
0x18007b21c  jns     short loc_18007B26E
0x18007b21e  mov     rcx, [rsp+28h]; this
0x18007b223  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007b22a  mov     r9d, eax; char *
0x18007b22d  mov     edx, 114h; void *
0x18007b232  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007b237  mov     ebx, eax
0x18007b239  test    eax, eax
0x18007b23b  jns     short loc_18007B26E
0x18007b23d  mov     rcx, [rsp+28h]; this
0x18007b242  lea     r8, aWil; "wil"
0x18007b249  mov     r9d, eax; char *
0x18007b24c  mov     edx, 37Fh; void *
0x18007b251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b256  xor     r8d, r8d; lpContext
0x18007b259  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b260  lea     edx, [r8+4]; dwFlags
0x18007b264  call    cs:__imp_InitOnceComplete
0x18007b26a  mov     eax, ebx
0x18007b26c  jmp     short loc_18007B282
0x18007b26e  xor     r8d, r8d; lpContext
0x18007b271  lea     rcx, ?s_HamConnectionInit@@3T_RTL_RUN_ONCE@@A; lpInitOnce
0x18007b278  xor     edx, edx; dwFlags
0x18007b27a  call    cs:__imp_InitOnceComplete
0x18007b280  xor     eax, eax
0x18007b282  add     rsp, 20h
0x18007b286  pop     rbx
0x18007b287  retn
```
