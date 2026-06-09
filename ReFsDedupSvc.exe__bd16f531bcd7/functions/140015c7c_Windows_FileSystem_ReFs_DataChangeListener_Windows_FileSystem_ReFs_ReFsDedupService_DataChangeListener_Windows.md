# Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>(void)

- ea: `0x140015c7c`
- end: `0x140015ee0`
- name: `??0?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@QEAA@XZ`
- size: `612`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x14000dbe0`
- `0x14000e22c`
- `0x14001425c`
- `0x140014fb4`
- `0x140015ac8`
- `0x140015c7c`
- `0x1400177a8`
- `0x140018f38`
- `0x1400196b8`
- `0x140038e9c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140015d56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140015d56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140015dc2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x140015dc2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140015df4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140015df4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140015e42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140015e42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140015d7e`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x140015ddf`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x140015ddf`

## string_xrefs

- `0x140015c96`: `ReFsDedupServiceSession`
- `0x140015e88`: `Failed to create thread pool worker`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>(
        char *pv)
{
  struct _TP_POOL *Threadpool; // rdi
  const char *v3; // r9
  const char *v4; // r9
  DWORD ActiveProcessorCount; // eax
  PTP_WORK v6; // rdi
  __int64 v7; // rsi
  const char *v9; // [rsp+28h] [rbp-31h]
  const wchar_t *v10; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h]
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+40h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v14; // [rsp+C8h] [rbp+6Fh] BYREF
  void (__stdcall *v15)(PTP_POOL); // [rsp+D0h] [rbp+77h] BYREF
  char v16; // [rsp+D8h] [rbp+7Fh] BYREF

  v10 = L"ReFsDedupServiceSession";
  v11 = 23;
  std::wstring::wstring(pv, &v10);
  *((_QWORD *)pv + 4) = 0;
  *((_DWORD *)pv + 10) = -1;
  *((_OWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 8) = -1;
  *((_QWORD *)pv + 16) = 0;
  v10 = L"ReFsDedupServiceSession";
  v11 = 23;
  Microsoft::Win32::EventTracing::TraceSession::TraceSession(pv + 136, &v10);
  *((_QWORD *)pv + 25) = 2;
  *((_OWORD *)pv + 14) = 0;
  *((_OWORD *)pv + 15) = 0;
  *((_OWORD *)pv + 16) = 0;
  *((_QWORD *)pv + 26) = 0;
  *((_QWORD *)pv + 27) = 0;
  *((_DWORD *)pv + 68) = -1;
  *((_DWORD *)pv + 69) = 0;
  *((_QWORD *)pv + 35) = 0;
  *((_QWORD *)pv + 36) = 0;
  *((_QWORD *)pv + 37) = 0;
  *((_QWORD *)pv + 38) = 0;
  *((_QWORD *)pv + 39) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>();
  *((_QWORD *)pv + 40) = 0;
  *((_QWORD *)pv + 41) = 0;
  *((_QWORD *)pv + 42) = 0;
  Threadpool = CreateThreadpool(0);
  if ( *((_QWORD *)pv + 42) )
  {
    v14 = *((_QWORD *)pv + 42);
    wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
    v15 = CloseThreadpool;
    wistd::invoke<void (*)(_TP_POOL *),_TP_POOL * &>(&v15, &v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
  }
  *((_QWORD *)pv + 42) = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\DataChangeListener.h",
      v3);
  if ( !SetThreadpoolThreadMinimum(Threadpool, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\DataChangeListener.h",
      v4);
  ActiveProcessorCount = GetActiveProcessorCount(0xFFFFu);
  SetThreadpoolThreadMaximum(*((PTP_POOL *)pv + 42), ActiveProcessorCount);
  pcbe.Version = 3;
  memset(&pcbe.CleanupGroup, 0, 44);
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  pcbe.Pool = (PTP_POOL)*((_QWORD *)pv + 42);
  v6 = CreateThreadpoolWork(
         Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::ChangeNotificationWorkerCallBack,
         pv,
         &pcbe);
  v7 = *((_QWORD *)pv + 41);
  if ( v7 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    wil::details::DestroyThreadPoolWork<0>::Destroy(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  *((_QWORD *)pv + 41) = v6;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\DataChangeListener.h",
    (const char *)(v6 == 0),
    (bool)"Failed to create thread pool worker",
    v9);
  return pv;
}

```

## disassembly

```asm
0x140015c7c  mov     [rsp-8+arg_0], rcx
0x140015c81  push    rbp
0x140015c82  push    rbx
0x140015c83  push    rsi
0x140015c84  push    rdi
0x140015c85  push    r15
0x140015c87  lea     rbp, [rsp-37h]
0x140015c8c  sub     rsp, 90h
0x140015c93  mov     rbx, rcx
0x140015c96  lea     rsi, aRefsdedupservi; "ReFsDedupServiceSession"
0x140015c9d  mov     [rbp+57h+var_80], rsi
0x140015ca1  mov     edi, 17h
0x140015ca6  mov     [rbp+57h+var_78], rdi
0x140015caa  lea     rdx, [rbp+57h+var_80]
0x140015cae  call    ??$?0V?$basic_zstring_view@G@wil@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_zstring_view@G@wil@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(wil::basic_zstring_view<ushort> const &,std::allocator<ushort> const &)
0x140015cb3  xor     eax, eax
0x140015cb5  mov     [rbx+20h], rax
0x140015cb9  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x140015cc0  xorps   xmm0, xmm0
0x140015cc3  movups  xmmword ptr [rbx+30h], xmm0
0x140015cc7  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x140015ccf  xor     r15d, r15d
0x140015cd2  mov     [rbx+80h], r15
0x140015cd9  mov     [rbp+57h+var_80], rsi
0x140015cdd  mov     [rbp+57h+var_78], rdi
0x140015ce1  lea     rcx, [rbx+88h]
0x140015ce8  lea     rdx, [rbp+57h+var_80]
0x140015cec  call    ??0TraceSession@EventTracing@Win32@Microsoft@@QEAA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Microsoft::Win32::EventTracing::TraceSession::TraceSession(std::basic_string_view<ushort>)
0x140015cf1  nop
0x140015cf2  lea     rcx, [rbx+0C8h]
0x140015cf9  mov     qword ptr [rcx], 2
0x140015d00  xorps   xmm0, xmm0
0x140015d03  movups  xmmword ptr [rcx+18h], xmm0
0x140015d07  movups  xmmword ptr [rcx+28h], xmm0
0x140015d0b  movups  xmmword ptr [rcx+38h], xmm0
0x140015d0f  mov     [rcx+8], r15
0x140015d13  mov     [rcx+10h], r15
0x140015d17  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x140015d1e  mov     [rcx+4Ch], r15d
0x140015d22  add     rcx, 50h ; 'P'
0x140015d26  mov     [rcx], r15
0x140015d29  mov     [rcx+8], r15
0x140015d2d  mov     [rcx+10h], r15
0x140015d31  mov     [rcx+18h], r15
0x140015d35  mov     [rcx+20h], r15
0x140015d39  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x140015d3e  nop
0x140015d3f  mov     [rbx+140h], r15
0x140015d46  mov     [rbx+148h], r15
0x140015d4d  mov     [rbx+150h], r15
0x140015d54  xor     ecx, ecx; reserved
0x140015d56  call    cs:__imp_CreateThreadpool
0x140015d5d  nop     dword ptr [rax+rax+00h]
0x140015d62  mov     rdi, rax
0x140015d65  mov     rax, [rbx+150h]
0x140015d6c  test    rax, rax
0x140015d6f  jz      short loc_140015D9F
0x140015d71  mov     [rbp+57h+arg_8], rax
0x140015d75  lea     rcx, [rbp+57h+arg_18]; this
0x140015d79  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140015d7e  mov     rcx, cs:__imp_CloseThreadpool
0x140015d85  mov     [rbp+57h+arg_10], rcx
0x140015d89  lea     rdx, [rbp+57h+arg_8]
0x140015d8d  lea     rcx, [rbp+57h+arg_10]
0x140015d91  call    ??$invoke@P6AXPEAU_TP_POOL@@@ZAEAPEAU1@@wistd@@YAX$$QEAP6AXPEAU_TP_POOL@@@ZAEAPEAU1@@Z; wistd::invoke<void (*)(_TP_POOL *),_TP_POOL * &>(void (*&&)(_TP_POOL *),_TP_POOL * &)
0x140015d96  lea     rcx, [rbp+57h+arg_18]; this
0x140015d9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140015d9f  mov     [rbx+150h], rdi
0x140015da6  test    rdi, rdi
0x140015da9  setz    al
0x140015dac  mov     rcx, [rbp+5Fh]; this
0x140015db0  test    al, al
0x140015db2  jnz     loc_140015ECE
0x140015db8  mov     esi, 1
0x140015dbd  mov     edx, esi; cthrdMic
0x140015dbf  mov     rcx, rdi; ptpp
0x140015dc2  call    cs:__imp_SetThreadpoolThreadMinimum
0x140015dc9  nop     dword ptr [rax+rax+00h]
0x140015dce  mov     rcx, [rbp+5Fh]; this
0x140015dd2  test    eax, eax
0x140015dd4  jz      loc_140015EBC
0x140015dda  mov     ecx, 0FFFFh; GroupNumber
0x140015ddf  call    cs:__imp_GetActiveProcessorCount
0x140015de6  nop     dword ptr [rax+rax+00h]
0x140015deb  mov     edx, eax; cthrdMost
0x140015ded  mov     rcx, [rbx+150h]; ptpp
0x140015df4  call    cs:__imp_SetThreadpoolThreadMaximum
0x140015dfb  nop     dword ptr [rax+rax+00h]
0x140015e00  mov     [rbp+57h+pcbe.Version], 3
0x140015e07  xorps   xmm0, xmm0
0x140015e0a  movdqa  xmmword ptr [rbp+57h+pcbe.CleanupGroup], xmm0
0x140015e0f  xorps   xmm1, xmm1
0x140015e12  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm1
0x140015e17  mov     [rbp+57h+pcbe.FinalizationCallback], r15
0x140015e1b  mov     dword ptr [rbp+57h+pcbe.u], r15d
0x140015e1f  mov     [rbp+57h+pcbe.CallbackPriority], esi
0x140015e22  mov     [rbp+57h+pcbe.Size], 48h ; 'H'
0x140015e29  mov     rax, [rbx+150h]
0x140015e30  mov     [rbp+57h+pcbe.Pool], rax
0x140015e34  lea     r8, [rbp+57h+pcbe]; pcbe
0x140015e38  mov     rdx, rbx; pv
0x140015e3b  lea     rcx, ?ChangeNotificationWorkerCallBack@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140015e42  call    cs:__imp_CreateThreadpoolWork
0x140015e49  nop     dword ptr [rax+rax+00h]
0x140015e4e  mov     rdi, rax
0x140015e51  mov     rsi, [rbx+148h]
0x140015e58  test    rsi, rsi
0x140015e5b  jz      short loc_140015E77
0x140015e5d  lea     rcx, [rbp+57h+arg_8]; this
0x140015e61  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140015e66  mov     rcx, rsi
0x140015e69  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x140015e6e  lea     rcx, [rbp+57h+arg_8]; this
0x140015e72  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140015e77  mov     [rbx+148h], rdi
0x140015e7e  test    rdi, rdi
0x140015e81  setz    al
0x140015e84  mov     rcx, [rbp+5Fh]; this
0x140015e88  lea     rdx, aFailedToCreate_1; "Failed to create thread pool worker"
0x140015e8f  mov     qword ptr [rsp+0B0h+var_90], rdx; bool
0x140015e94  movzx   r9d, al; char *
0x140015e98  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\refsdedupsvc\\exe\\D"...
0x140015e9f  mov     edx, 7Eh ; '~'; void *
0x140015ea4  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140015ea9  nop
0x140015eaa  mov     rax, rbx
0x140015ead  add     rsp, 90h
0x140015eb4  pop     r15
0x140015eb6  pop     rdi
0x140015eb7  pop     rsi
0x140015eb8  pop     rbx
0x140015eb9  pop     rbp
0x140015eba  retn
0x140015ebc  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\refsdedupsvc\\exe\\D"...
0x140015ec3  mov     edx, 76h ; 'v'; void *
0x140015ec8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015ece  lea     r8, aOnecoreBaseFsR_12; "onecore\\base\\fs\\refsdedupsvc\\exe\\D"...
0x140015ed5  mov     edx, 73h ; 's'; void *
0x140015eda  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
