# ContainerManagerApi::TryEnsureMachineIsRunning(ulong)

- ea: `0x180021e50`
- end: `0x180022121`
- name: `?TryEnsureMachineIsRunning@ContainerManagerApi@@UEAA?AW4RemoteMachineStatus@ICrossMachineCommunicationServices@@K@Z`
- size: `721`
- prototype: `enum ICrossMachineCommunicationServices::RemoteMachineStatus __high(unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007344`
- `0x1800161b8`
- `0x180018868`
- `0x180021d9c`
- `0x180021e50`
- `0x1800221d8`
- `0x180022204`
- `0x180022254`
- `0x1800225a0`
- `0x1800225c8`
- `0x180022870`
- `0x18002a514`
- `0x180031540`
- `0x180043680`
- `0x180043a8c`
- `0x18007f5f4`
- `0x180080130`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800220c9`
- `msvcp_win!_Mtx_unlock` at `0x1800220c9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180021f98`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180021f98`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021ea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021ea3`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180021f3d`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180021f3d`

## string_xrefs

- `0x180021f4e`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180021fbb`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180021ff6`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180022016`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ContainerManagerApi::TryEnsureMachineIsRunning(__int64 a1, DWORD a2)
{
  _OWORD *v4; // r14
  char *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r15
  int started; // eax
  void **v9; // rax
  void *v10; // rcx
  void **v11; // rax
  void *v12; // rcx
  DWORD v13; // eax
  const char *v14; // r9
  _DWORD *v16; // rax
  int v17; // r8d
  int v18; // [rsp+20h] [rbp-A9h]
  const char *v19; // [rsp+28h] [rbp-A1h]
  __int64 v20; // [rsp+38h] [rbp-91h] BYREF
  __int64 v21; // [rsp+40h] [rbp-89h]
  HANDLE Handles[2]; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v23[2]; // [rsp+58h] [rbp-71h] BYREF
  _QWORD v24[2]; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v25[16]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v26[40]; // [rsp+88h] [rbp-41h] BYREF
  ULONGLONG TickCount64; // [rsp+B0h] [rbp-19h]
  char v28; // [rsp+B8h] [rbp-11h]
  __int128 v29; // [rsp+C0h] [rbp-9h]
  char v30; // [rsp+D0h] [rbp+7h] BYREF
  __int128 v31; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v4 = (_OWORD *)(a1 + 8);
  ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::GetValue((_Mtx_t)ContainerManagerApi::s_clientContainerActivities);
  if ( v28 )
  {
    TickCount64 = GetTickCount64();
    v26[32] = 1;
    ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::InsertOrAssign<ContainerManagerApi::ClientContainerActivityData>((_Mtx_t)ContainerManagerApi::s_clientContainerActivities);
  }
  else
  {
    v5 = (char *)operator new(0x50u);
    *(_OWORD *)v5 = 0;
    *((_DWORD *)v5 + 2) = 1;
    *((_DWORD *)v5 + 3) = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<ContainerManagerApi::ClientActivityContext>::`vftable';
    v5[16] = 0;
    anonymous_namespace_::ContainerActivityStartedContext::ContainerActivityStartedContext(v5 + 24);
    *((_OWORD *)v5 + 4) = *v4;
    v23[0] = v5 + 16;
    v23[1] = v5;
    ContainerManagerApi::GetContainerActivity(a1, &v20, v6, 0x2711u);
    v7 = v21;
    started = CmsStartActivityAsync(v21, ContainerManagerApi::ClientActivityNotificationCallback, v5 + 16);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
        (const char *)(unsigned int)started,
        v18);
    v9 = (void **)*((_QWORD *)v5 + 4);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    Handles[0] = v10;
    v11 = (void **)*((_QWORD *)v5 + 6);
    if ( v11 )
      v12 = *v11;
    else
      v12 = 0;
    Handles[1] = v12;
    v13 = WaitForMultipleObjects(2u, Handles, 0, a2);
    if ( v13 == 258 )
    {
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
        (const char *)0x5B4,
        (unsigned int)"ContainerManagerApi::TryEnsureMachineIsRunning: Timed out waiting for container acitivity to start.",
        v19);
      ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)&v20);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v5);
      std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(v26);
      return 1;
    }
    if ( v13 >= 2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
        v14);
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
        (const char *)0x80004005LL,
        v18);
    v16 = operator new(0x20u);
    *(_OWORD *)v16 = 0;
    v16[2] = 1;
    v16[3] = 1;
    *(_QWORD *)v16 = &std::_Ref_count_obj2<ContainerManagerApi::ContainerActivityGuard>::`vftable';
    *((_QWORD *)v16 + 2) = v20;
    v20 = 0;
    *((_QWORD *)v16 + 3) = v7;
    v21 = 0;
    v24[0] = v16 + 4;
    v24[1] = v16;
    v29 = 0;
    std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(
      v25,
      v23);
    v31 = *v4;
    std::_Mutex_base::lock((std::_Mutex_base *)ContainerManagerApi::s_clientContainerActivities);
    std::_Hash<std::_Umap_traits<_GUID,ContainerManagerApi::ClientContainerActivityData,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ContainerManagerApi::ClientContainerActivityData>>,0>>::emplace<std::piecewise_construct_t const &,std::tuple<_GUID>,std::tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>>(
      (unsigned int)&dword_1800C4940,
      (unsigned int)&v30,
      v17,
      (unsigned int)&v31,
      (__int64)v24);
    _Mtx_unlock((_Mtx_t)ContainerManagerApi::s_clientContainerActivities);
    std::tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>::~tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>(v24);
    ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)&v20);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v5);
  }
  std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(v26);
  return 0;
}

```

## disassembly

```asm
0x180021e50  mov     [rsp-8+arg_10], rbx
0x180021e55  mov     [rsp-8+arg_18], rsi
0x180021e5a  push    rbp
0x180021e5b  push    rdi
0x180021e5c  push    r12
0x180021e5e  push    r14
0x180021e60  push    r15
0x180021e62  lea     rbp, [rsp-37h]
0x180021e67  sub     rsp, 100h
0x180021e6e  mov     rax, cs:__security_cookie
0x180021e75  xor     rax, rsp
0x180021e78  mov     [rbp+57h+var_30], rax
0x180021e7c  mov     r12d, edx
0x180021e7f  mov     r15, rcx
0x180021e82  lea     r14, [rcx+8]
0x180021e86  mov     r8, r14
0x180021e89  lea     rdx, [rbp+57h+var_98]
0x180021e8d  lea     rdi, ?s_clientContainerActivities@ContainerManagerApi@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@@@A; SmartLeak<ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>> ContainerManagerApi::s_clientContainerActivities
0x180021e94  mov     rcx, rdi; _Mtx_t
0x180021e97  call    ?GetValue@?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@QEBA?AV?$optional@UClientContainerActivityData@ContainerManagerApi@@@std@@AEBU_GUID@@@Z; ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::GetValue(_GUID const &)
0x180021e9c  nop
0x180021e9d  cmp     [rbp+57h+var_68], 0
0x180021ea1  jz      short loc_180021EC9
0x180021ea3  call    cs:__imp_GetTickCount64
0x180021ea9  mov     [rbp+57h+var_70], rax
0x180021ead  mov     ebx, 1
0x180021eb2  mov     [rbp+57h+var_78], bl
0x180021eb5  lea     r8, [rbp+57h+var_98]
0x180021eb9  mov     rdx, r14
0x180021ebc  mov     rcx, rdi; _Mtx_t
0x180021ebf  call    ??$InsertOrAssign@UClientContainerActivityData@ContainerManagerApi@@@?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@QEAAXAEBU_GUID@@$$QEAUClientContainerActivityData@ContainerManagerApi@@@Z; ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>::InsertOrAssign<ContainerManagerApi::ClientContainerActivityData>(_GUID const &,ContainerManagerApi::ClientContainerActivityData &&)
0x180021ec4  jmp     loc_1800220EE
0x180021ec9  mov     ecx, 50h ; 'P'; Size
0x180021ece  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021ed3  mov     rsi, rax
0x180021ed6  mov     [rsp+120h+var_F0], rax
0x180021edb  xorps   xmm0, xmm0
0x180021ede  movups  xmmword ptr [rax], xmm0
0x180021ee1  mov     ebx, 1
0x180021ee6  mov     [rax+8], ebx
0x180021ee9  mov     [rax+0Ch], ebx
0x180021eec  lea     rax, ??_7?$_Ref_count_obj2@UClientActivityContext@ContainerManagerApi@@@std@@6B@; const std::_Ref_count_obj2<ContainerManagerApi::ClientActivityContext>::`vftable'
0x180021ef3  mov     [rsi], rax
0x180021ef6  lea     rdi, [rsi+10h]
0x180021efa  mov     byte ptr [rdi], 0
0x180021efd  lea     rcx, [rdi+8]
0x180021f01  call    _anonymous_namespace___ContainerActivityStartedContext__ContainerActivityStartedContext
0x180021f06  movups  xmm0, xmmword ptr [r14]
0x180021f0a  movdqu  xmmword ptr [rdi+30h], xmm0
0x180021f0f  mov     [rbp+57h+var_C8], rdi
0x180021f13  mov     [rbp+57h+var_C0], rsi
0x180021f17  mov     r9d, 2711h
0x180021f1d  lea     rdx, [rsp+120h+var_E8]
0x180021f22  mov     rcx, r15
0x180021f25  call    ?GetContainerActivity@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z; ContainerManagerApi::GetContainerActivity(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)
0x180021f2a  nop
0x180021f2b  mov     r8, rdi
0x180021f2e  lea     rdx, ?ClientActivityNotificationCallback@ContainerManagerApi@@CAXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z; ContainerManagerApi::ClientActivityNotificationCallback(_CMS_ACTIVITY_NOTIFICATION *,void *)
0x180021f35  mov     r15, [rsp+120h+var_E0]
0x180021f3a  mov     rcx, r15
0x180021f3d  call    cs:__imp_CmsStartActivityAsync
0x180021f43  mov     rcx, [rbp+5Fh]; this
0x180021f47  test    eax, eax
0x180021f49  jns     short loc_180021F60
0x180021f4b  mov     r9d, eax; char *
0x180021f4e  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021f55  mov     edx, 152h; void *
0x180021f5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021f60  mov     rax, [rdi+10h]
0x180021f64  test    rax, rax
0x180021f67  jz      short loc_180021F6E
0x180021f69  mov     rcx, [rax]
0x180021f6c  jmp     short loc_180021F70
0x180021f6e  xor     ecx, ecx
0x180021f70  mov     [rsp+120h+Handles], rcx
0x180021f75  mov     rax, [rdi+20h]
0x180021f79  test    rax, rax
0x180021f7c  jz      short loc_180021F83
0x180021f7e  mov     rcx, [rax]
0x180021f81  jmp     short loc_180021F85
0x180021f83  xor     ecx, ecx
0x180021f85  mov     [rbp+57h+var_D0], rcx
0x180021f89  mov     r9d, r12d; dwMilliseconds
0x180021f8c  xor     r8d, r8d; bWaitAll
0x180021f8f  lea     rdx, [rsp+120h+Handles]; lpHandles
0x180021f94  lea     ecx, [r8+2]; nCount
0x180021f98  call    cs:__imp_WaitForMultipleObjects
0x180021f9e  mov     rcx, [rbp+5Fh]; this
0x180021fa2  cmp     eax, 102h
0x180021fa7  jnz     short loc_180021FF1
0x180021fa9  lea     rax, aContainermanag; "ContainerManagerApi::TryEnsureMachineIs"...
0x180021fb0  mov     qword ptr [rsp+120h+var_100], rax; unsigned int
0x180021fb5  mov     r9d, 5B4h; char *
0x180021fbb  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021fc2  mov     edx, 15Bh; void *
0x180021fc7  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180021fcc  nop
0x180021fcd  lea     rcx, [rsp+120h+var_E8]; this
0x180021fd2  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x180021fd7  nop
0x180021fd8  mov     rcx, rsi; this
0x180021fdb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021fe0  nop
0x180021fe1  lea     rcx, [rbp+57h+var_98]
0x180021fe5  call    ??1?$_Optional_destruct_base@UClientContainerActivityData@ContainerManagerApi@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(void)
0x180021fea  mov     eax, ebx
0x180021fec  jmp     loc_1800220F9
0x180021ff1  cmp     eax, 2
0x180021ff4  jb      short loc_180022008
0x180021ff6  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021ffd  mov     edx, 15Eh; void *
0x180022002  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022008  mov     rcx, [rbp+5Fh]; this
0x18002200c  test    eax, eax
0x18002200e  jz      short loc_180022028
0x180022010  mov     r9d, 80004005h; char *
0x180022016  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x18002201d  mov     edx, 160h; void *
0x180022022  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022028  mov     ecx, 20h ; ' '; Size
0x18002202d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022032  mov     [rsp+120h+var_F0], rax
0x180022037  xorps   xmm0, xmm0
0x18002203a  movups  xmmword ptr [rax], xmm0
0x18002203d  mov     [rax+8], ebx
0x180022040  mov     [rax+0Ch], ebx
0x180022043  lea     rcx, ??_7?$_Ref_count_obj2@VContainerActivityGuard@ContainerManagerApi@@@std@@6B@; const std::_Ref_count_obj2<ContainerManagerApi::ContainerActivityGuard>::`vftable'
0x18002204a  mov     [rax], rcx
0x18002204d  lea     rdx, [rax+10h]
0x180022051  mov     rcx, [rsp+120h+var_E8]
0x180022056  mov     [rdx], rcx
0x180022059  mov     [rsp+120h+var_E8], 0
0x180022062  mov     [rdx+8], r15
0x180022066  mov     [rsp+120h+var_E0], 0
0x18002206f  mov     [rbp+57h+var_B8], rdx
0x180022073  mov     [rbp+57h+var_B0], rax
0x180022077  movdqu  [rbp+57h+var_60], xmm0
0x18002207c  lea     rdx, [rbp+57h+var_C8]
0x180022080  lea     rcx, [rbp+57h+var_A8]
0x180022084  call    ??0?$shared_ptr@UHwndAndViewIdConversionData@CoreUiSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData> const &)
0x180022089  nop
0x18002208a  movups  xmm0, xmmword ptr [r14]
0x18002208e  movdqu  [rbp+57h+var_40], xmm0
0x180022093  lea     rbx, ?s_clientContainerActivities@ContainerManagerApi@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@@@@@A; SmartLeak<ThreadSafeMap<_GUID,ContainerManagerApi::ClientContainerActivityData>> ContainerManagerApi::s_clientContainerActivities
0x18002209a  mov     [rsp+120h+var_F0], rbx
0x18002209f  mov     rcx, rbx; this
0x1800220a2  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800220a7  nop
0x1800220a8  lea     rax, [rbp+57h+var_B8]
0x1800220ac  mov     qword ptr [rsp+120h+var_100], rax
0x1800220b1  lea     r9, [rbp+57h+var_40]
0x1800220b5  lea     rdx, [rbp+57h+var_50]
0x1800220b9  lea     rcx, dword_1800C4940
0x1800220c0  call    ??$emplace@AEBUpiecewise_construct_t@std@@V?$tuple@U_GUID@@@2@V?$tuple@V?$shared_ptr@UClientActivityContext@ContainerManagerApi@@@std@@V?$shared_ptr@VContainerActivityGuard@ContainerManagerApi@@@2@@2@@?$_Hash@V?$_Umap_traits@U_GUID@@UClientContainerActivityData@ContainerManagerApi@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UClientContainerActivityData@ContainerManagerApi@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@UClientContainerActivityData@ContainerManagerApi@@@std@@@std@@@std@@@std@@_N@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@U_GUID@@@1@$$QEAV?$tuple@V?$shared_ptr@UClientActivityContext@ContainerManagerApi@@@std@@V?$shared_ptr@VContainerActivityGuard@ContainerManagerApi@@@2@@1@@Z; std::_Hash<std::_Umap_traits<_GUID,ContainerManagerApi::ClientContainerActivityData,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ContainerManagerApi::ClientContainerActivityData>>,0>>::emplace<std::piecewise_construct_t const &,std::tuple<_GUID>,std::tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>>(std::piecewise_construct_t const &,std::tuple<_GUID> &&,std::tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>> &&)
0x1800220c5  nop
0x1800220c6  mov     rcx, rbx; _Mtx_t
0x1800220c9  call    cs:__imp__Mtx_unlock
0x1800220cf  nop
0x1800220d0  lea     rcx, [rbp+57h+var_B8]
0x1800220d4  call    ??1?$tuple@V?$shared_ptr@UClientActivityContext@ContainerManagerApi@@@std@@V?$shared_ptr@VContainerActivityGuard@ContainerManagerApi@@@2@@std@@QEAA@XZ; std::tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>::~tuple<std::shared_ptr<ContainerManagerApi::ClientActivityContext>,std::shared_ptr<ContainerManagerApi::ContainerActivityGuard>>(void)
0x1800220d9  nop
0x1800220da  lea     rcx, [rsp+120h+var_E8]; this
0x1800220df  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x1800220e4  nop
0x1800220e5  mov     rcx, rsi; this
0x1800220e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800220ed  nop
0x1800220ee  lea     rcx, [rbp+57h+var_98]
0x1800220f2  call    ??1?$_Optional_destruct_base@UClientContainerActivityData@ContainerManagerApi@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>::~_Optional_destruct_base<ContainerManagerApi::ClientContainerActivityData,0>(void)
0x1800220f7  xor     eax, eax
0x1800220f9  mov     rcx, [rbp+57h+var_30]
0x1800220fd  xor     rcx, rsp; StackCookie
0x180022100  call    __security_check_cookie
0x180022105  lea     r11, [rsp+120h+var_20]
0x18002210d  mov     rbx, [r11+40h]
0x180022111  mov     rsi, [r11+48h]
0x180022115  mov     rsp, r11
0x180022118  pop     r15
0x18002211a  pop     r14
0x18002211c  pop     r12
0x18002211e  pop     rdi
0x18002211f  pop     rbp
0x180022120  retn
```
