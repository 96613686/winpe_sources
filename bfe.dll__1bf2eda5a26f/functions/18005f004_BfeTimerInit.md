# BfeTimerInit

- ea: `0x18005f004`
- end: `0x18005f168`
- name: `BfeTimerInit`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f0a0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x1800238b4`
- `0x180055904`
- `0x18005ac70`
- `0x18005c314`
- `0x18005ea54`
- `0x18005f004`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005f0a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005f0a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005f0e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005f0e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005f0d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005f0d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005f0e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f0f7`

## string_xrefs

- `0x18005f02f`: `gBfeTimerTracking.InitializeThreadpool`
- `0x18005f0c8`: `CreateThreadpool`
- `0x18005f0fd`: `CreateThreadpoolCleanupGroup`

## pseudocode

```c
__int64 __fastcall BfeTimerInit(BfeTimerTracking *a1)
{
  int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rax
  PTP_POOL Threadpool; // rax
  struct _TP_POOL *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rcx
  const char *v8; // rdx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  __int64 v10; // rbx
  PTP_POOL ptpp; // [rsp+30h] [rbp+8h] BYREF
  struct _TP_CLEANUP_GROUP *v13; // [rsp+38h] [rbp+10h] BYREF

  ptpp = 0;
  v13 = 0;
  v1 = BfeTimerTracking::InitializeThreadpool(a1);
  if ( v1 >= 0 )
  {
    gBfeTimerCallBackEnvironment.Version = 3;
    *(_OWORD *)&gBfeTimerCallBackEnvironment.RaceDll = 0;
    gBfeTimerCallBackEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    gBfeTimerCallBackEnvironment.Pool = 0;
    gBfeTimerCallBackEnvironment.CleanupGroup = 0;
    gBfeTimerCallBackEnvironment.CleanupGroupCancelCallback = 0;
    gBfeTimerCallBackEnvironment.FinalizationCallback = 0;
    gBfeTimerCallBackEnvironment.u.Flags = 0;
    gBfeTimerCallBackEnvironment.Size = 72;
    Threadpool = CreateThreadpool(0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
      &ptpp,
      Threadpool);
    v5 = ptpp;
    if ( ptpp )
    {
      SetThreadpoolThreadMinimum(ptpp, 1u);
      SetThreadpoolThreadMaximum(v5, 1u);
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      v13 = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        v10 = 0;
        gBfeTimerCallBackEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
        v13 = 0;
        gBfeTimerCallBackEnvironment.CleanupGroupCancelCallback = 0;
        ptpp = 0;
        gBfeTimerCallBackEnvironment.Pool = v5;
        goto LABEL_11;
      }
      LastError = GetLastError();
      v8 = "CreateThreadpoolCleanupGroup";
    }
    else
    {
      LastError = GetLastError();
      v8 = "CreateThreadpool";
    }
    v3 = WfpReportSysErrorAsWinError(v7, v8, LastError);
  }
  else
  {
    v3 = WfpReportSysErrorAsHResult(v2, "gBfeTimerTracking.InitializeThreadpool", (unsigned int)v1, 1);
  }
  v10 = v3;
  if ( v3 )
    WfpReportError(v3, "BfeTimerInit");
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>(&v13);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(&ptpp);
  return v10;
}

```

## disassembly

```asm
0x18005f004  mov     [rsp+arg_10], rbx
0x18005f009  push    rdi
0x18005f00a  sub     rsp, 20h
0x18005f00e  mov     [rsp+28h+ptpp], 0
0x18005f017  mov     [rsp+28h+arg_8], 0
0x18005f020  call    ?InitializeThreadpool@BfeTimerTracking@@QEAAJXZ; BfeTimerTracking::InitializeThreadpool(void)
0x18005f025  test    eax, eax
0x18005f027  jns     short loc_18005F043
0x18005f029  mov     r9d, 1
0x18005f02f  lea     rdx, aGbfetimertrack_0; "gBfeTimerTracking.InitializeThreadpool"
0x18005f036  mov     r8d, eax
0x18005f039  call    WfpReportSysErrorAsHResult
0x18005f03e  jmp     loc_18005F10C
0x18005f043  xorps   xmm0, xmm0
0x18005f046  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f050  mov     ebx, 1
0x18005f055  movdqa  xmmword ptr cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f05d  xor     ecx, ecx; reserved
0x18005f05f  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f065  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f070  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f07b  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f086  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f091  mov     dword ptr cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f09b  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f0a5  call    cs:__imp_CreateThreadpool
0x18005f0ab  mov     rdx, rax
0x18005f0ae  lea     rcx, [rsp+28h+ptpp]
0x18005f0b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18005f0b8  mov     rdi, [rsp+28h+ptpp]
0x18005f0bd  test    rdi, rdi
0x18005f0c0  jnz     short loc_18005F0D1
0x18005f0c2  call    cs:__imp_GetLastError
0x18005f0c8  lea     rdx, aCreatethreadpo_1; "CreateThreadpool"
0x18005f0cf  jmp     short loc_18005F104
0x18005f0d1  mov     edx, ebx; cthrdMic
0x18005f0d3  mov     rcx, rdi; ptpp
0x18005f0d6  call    cs:__imp_SetThreadpoolThreadMinimum
0x18005f0dc  mov     edx, ebx; cthrdMost
0x18005f0de  mov     rcx, rdi; ptpp
0x18005f0e1  call    cs:__imp_SetThreadpoolThreadMaximum
0x18005f0e7  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18005f0ed  mov     [rsp+28h+arg_8], rax
0x18005f0f2  test    rax, rax
0x18005f0f5  jnz     short loc_18005F125
0x18005f0f7  call    cs:__imp_GetLastError
0x18005f0fd  lea     rdx, aCreatethreadpo; "CreateThreadpoolCleanupGroup"
0x18005f104  mov     r8d, eax
0x18005f107  call    WfpReportSysErrorAsWinError
0x18005f10c  mov     rbx, rax
0x18005f10f  test    rax, rax
0x18005f112  jz      short loc_18005F146
0x18005f114  lea     rdx, aBfetimerinit; "BfeTimerInit"
0x18005f11b  mov     rcx, rax
0x18005f11e  call    WfpReportError
0x18005f123  jmp     short loc_18005F146
0x18005f125  xor     ebx, ebx
0x18005f127  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f12e  mov     [rsp+28h+arg_8], rbx
0x18005f133  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rbx; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f13a  mov     [rsp+28h+ptpp], rbx
0x18005f13f  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18005f146  lea     rcx, [rsp+28h+arg_8]
0x18005f14b  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>(void)
0x18005f150  lea     rcx, [rsp+28h+ptpp]
0x18005f155  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18005f15a  mov     rax, rbx
0x18005f15d  mov     rbx, [rsp+28h+arg_10]
0x18005f162  add     rsp, 20h
0x18005f166  pop     rdi
0x18005f167  retn
```
