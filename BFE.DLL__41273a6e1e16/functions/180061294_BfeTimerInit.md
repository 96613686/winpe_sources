# BfeTimerInit

- ea: `0x180061294`
- end: `0x18006141d`
- name: `BfeTimerInit`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180040330`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180025fe4`
- `0x18005774c`
- `0x18005caf4`
- `0x18005e324`
- `0x180060c8c`
- `0x180061294`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180061335`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180061335`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180061383`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180061383`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180061372`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180061372`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18006138f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18006138f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613a5`

## string_xrefs

- `0x1800612bf`: `gBfeTimerTracking.InitializeThreadpool`
- `0x180061364`: `CreateThreadpool`
- `0x1800613b1`: `CreateThreadpoolCleanupGroup`

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
0x180061294  mov     [rsp+arg_10], rbx
0x180061299  push    rdi
0x18006129a  sub     rsp, 20h
0x18006129e  mov     [rsp+28h+ptpp], 0
0x1800612a7  mov     [rsp+28h+arg_8], 0
0x1800612b0  call    ?InitializeThreadpool@BfeTimerTracking@@QEAAJXZ; BfeTimerTracking::InitializeThreadpool(void)
0x1800612b5  test    eax, eax
0x1800612b7  jns     short loc_1800612D3
0x1800612b9  mov     r9d, 1
0x1800612bf  lea     rdx, aGbfetimertrack_0; "gBfeTimerTracking.InitializeThreadpool"
0x1800612c6  mov     r8d, eax
0x1800612c9  call    WfpReportSysErrorAsHResult
0x1800612ce  jmp     loc_1800613C0
0x1800612d3  xorps   xmm0, xmm0
0x1800612d6  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800612e0  mov     ebx, 1
0x1800612e5  movdqa  xmmword ptr cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800612ed  xor     ecx, ecx; reserved
0x1800612ef  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800612f5  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x180061300  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18006130b  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x180061316  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x180061321  mov     dword ptr cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x18006132b  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x180061335  call    cs:__imp_CreateThreadpool
0x18006133c  nop     dword ptr [rax+rax+00h]
0x180061341  mov     rdx, rax
0x180061344  lea     rcx, [rsp+28h+ptpp]
0x180061349  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18006134e  mov     rdi, [rsp+28h+ptpp]
0x180061353  test    rdi, rdi
0x180061356  jnz     short loc_18006136D
0x180061358  call    cs:__imp_GetLastError
0x18006135f  nop     dword ptr [rax+rax+00h]
0x180061364  lea     rdx, aCreatethreadpo_1; "CreateThreadpool"
0x18006136b  jmp     short loc_1800613B8
0x18006136d  mov     edx, ebx; cthrdMic
0x18006136f  mov     rcx, rdi; ptpp
0x180061372  call    cs:__imp_SetThreadpoolThreadMinimum
0x180061379  nop     dword ptr [rax+rax+00h]
0x18006137e  mov     edx, ebx; cthrdMost
0x180061380  mov     rcx, rdi; ptpp
0x180061383  call    cs:__imp_SetThreadpoolThreadMaximum
0x18006138a  nop     dword ptr [rax+rax+00h]
0x18006138f  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180061396  nop     dword ptr [rax+rax+00h]
0x18006139b  mov     [rsp+28h+arg_8], rax
0x1800613a0  test    rax, rax
0x1800613a3  jnz     short loc_1800613D9
0x1800613a5  call    cs:__imp_GetLastError
0x1800613ac  nop     dword ptr [rax+rax+00h]
0x1800613b1  lea     rdx, aCreatethreadpo; "CreateThreadpoolCleanupGroup"
0x1800613b8  mov     r8d, eax
0x1800613bb  call    WfpReportSysErrorAsWinError
0x1800613c0  mov     rbx, rax
0x1800613c3  test    rax, rax
0x1800613c6  jz      short loc_1800613FA
0x1800613c8  lea     rdx, aBfetimerinit; "BfeTimerInit"
0x1800613cf  mov     rcx, rax
0x1800613d2  call    WfpReportError
0x1800613d7  jmp     short loc_1800613FA
0x1800613d9  xor     ebx, ebx
0x1800613db  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800613e2  mov     [rsp+28h+arg_8], rbx
0x1800613e7  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rbx; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800613ee  mov     [rsp+28h+ptpp], rbx
0x1800613f3  mov     cs:?gBfeTimerCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 gBfeTimerCallBackEnvironment ...
0x1800613fa  lea     rcx, [rsp+28h+arg_8]
0x1800613ff  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>(void)
0x180061404  lea     rcx, [rsp+28h+ptpp]
0x180061409  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18006140e  mov     rax, rbx
0x180061411  mov     rbx, [rsp+28h+arg_10]
0x180061416  add     rsp, 20h
0x18006141a  pop     rdi
0x18006141b  retn
```
