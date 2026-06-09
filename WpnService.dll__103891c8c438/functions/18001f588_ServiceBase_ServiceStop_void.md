# ServiceBase::ServiceStop(void)

- ea: `0x18001f588`
- end: `0x18001f765`
- name: `?ServiceStop@ServiceBase@@QEAAXXZ`
- size: `477`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bb78`
- `0x18002c188`
- `0x18002cbc0`

## callees

- `0x1800109d4`
- `0x18001f588`
- `0x18001f76c`
- `0x18001f7c8`
- `0x18001fa4c`
- `0x18001fa84`
- `0x1800201c8`
- `0x180020e24`
- `0x180025108`
- `0x180026200`
- `0x18002b848`
- `0x18002bb44`
- `0x18002bb9c`
- `0x18002c3e0`
- `0x18002ccd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6c4`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18001f700`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18001f700`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001f6a4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001f6a4`

## string_xrefs

- `0x18001f6e4`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18001f5b0`: `ServiceStopActivity`
- `0x18001f5d1`: `ServiceStopActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceBase::ServiceStop(ServiceBase *this)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  void *v4; // rcx
  signed int LastError; // eax
  unsigned int updated; // eax
  int v7; // r8d
  int v8[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v9[42]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v10[42]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v8,
    (__int64)"ServiceStopActivity");
  *(_QWORD *)v8 = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v9,
    (__int64)"ServiceStopActivity");
  v9[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  ServiceHostTelemetry::ServiceStopActivity::StartActivity(
    (ServiceHostTelemetry::ServiceStopActivity *)v9,
    (const unsigned __int16 *)this + 4);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v10);
  v10[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
    v8,
    (__int64)v9);
  ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity((ServiceHostTelemetry::ServiceStopActivity *)v10);
  ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity((ServiceHostTelemetry::ServiceStopActivity *)v9);
  ServiceHostTelemetry::ServiceBaseStatus<unsigned short (&)[32],unsigned short const (&)[9]>(
    (__int64)this + 8,
    (__int64)L"Stopping");
  if ( *((_DWORD *)this + 31) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (char *)this + 184,
      0);
    v2 = (*(__int64 (__fastcall **)(ServiceBase *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 33));
    LogIfStopSrvFailedAndReturnHr(v2, (char *)this + 8, 1);
    if ( *((_DWORD *)this + 33) )
    {
      v3 = ServiceBase::_SetShutdownRegistryKey(this);
      LogIfStopSrvFailedAndReturnHr(v3, (char *)this + 8, 2);
    }
  }
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    if ( !UnregisterWaitEx(v4, 0) && GetLastError() != 997 )
    {
      *((_DWORD *)this + 27) = GetLastError();
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF2,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
          (const char *)(unsigned int)LastError);
    }
    *((_QWORD *)this + 11) = 0;
  }
  CoFreeUnusedLibrariesEx(0x7530u, 0);
  updated = ServiceBase::_UpdateStatus(this, 1);
  LogIfStopSrvFailedAndReturnHr(updated, (char *)this + 8, 3);
  ServiceHostTelemetry::ServiceStopActivity::Stop(
    (ServiceHostTelemetry::ServiceStopActivity *)v8,
    (const unsigned __int16 *)this + 4,
    v7);
  ServiceHostTelemetry::ServiceBaseStatus<unsigned short (&)[32],unsigned short const (&)[8]>(
    (__int64)this + 8,
    (__int64)L"Stopped");
  ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity((ServiceHostTelemetry::ServiceStopActivity *)v8);
}

```

## disassembly

```asm
0x18001f588  push    rbp
0x18001f58a  push    rbx
0x18001f58b  push    rsi
0x18001f58c  push    rdi
0x18001f58d  lea     rbp, [rsp-328h]
0x18001f595  sub     rsp, 428h
0x18001f59c  mov     rax, cs:__security_cookie
0x18001f5a3  xor     rax, rsp
0x18001f5a6  mov     [rbp+340h+var_30], rax
0x18001f5ad  mov     rbx, rcx
0x18001f5b0  lea     rdx, aServicestopact; "ServiceStopActivity"
0x18001f5b7  lea     rcx, [rsp+440h+var_420]
0x18001f5bc  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001f5c1  lea     rsi, ??_7ServiceStopActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStopActivity::`vftable'
0x18001f5c8  mov     qword ptr [rsp+440h+var_420], rsi; int
0x18001f5cd  lea     rdi, [rbx+8]
0x18001f5d1  lea     rdx, aServicestopact; "ServiceStopActivity"
0x18001f5d8  lea     rcx, [rbp+340h+var_2D0]
0x18001f5dc  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001f5e1  mov     [rbp+340h+var_2D0], rsi
0x18001f5e5  mov     r8d, [rbx+84h]; int
0x18001f5ec  mov     rdx, rdi; unsigned __int16 *
0x18001f5ef  lea     rcx, [rbp+340h+var_2D0]; this
0x18001f5f3  call    ?StartActivity@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGH@Z; ServiceHostTelemetry::ServiceStopActivity::StartActivity(ushort const *,int)
0x18001f5f8  nop
0x18001f5f9  lea     rdx, [rsp+440h+var_420]
0x18001f5fe  lea     rcx, [rbp+340h+var_180]
0x18001f605  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18001f60a  mov     [rbp+340h+var_180], rsi
0x18001f611  lea     rdx, [rbp+340h+var_2D0]
0x18001f615  lea     rcx, [rsp+440h+var_420]
0x18001f61a  call    ??4?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18001f61f  lea     rcx, [rbp+340h+var_180]; this
0x18001f626  call    ??1ServiceStopActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(void)
0x18001f62b  lea     rcx, [rbp+340h+var_2D0]; this
0x18001f62f  call    ??1ServiceStopActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(void)
0x18001f634  lea     rdx, aStopping; "Stopping"
0x18001f63b  mov     rcx, rdi
0x18001f63e  call    ??$ServiceBaseStatus@AEAY0CA@GAEAY08$$CBG@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY08$$CBG@Z; ServiceHostTelemetry::ServiceBaseStatus<ushort (&)[32],ushort const (&)[9]>(ushort (&)[32],ushort const (&)[9])
0x18001f643  xor     esi, esi
0x18001f645  cmp     [rbx+7Ch], esi
0x18001f648  jz      short loc_18001F699
0x18001f64a  lea     rcx, [rbx+0B8h]
0x18001f651  xor     edx, edx
0x18001f653  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001f658  mov     rax, [rbx]
0x18001f65b  mov     edx, [rbx+84h]
0x18001f661  mov     rcx, rbx
0x18001f664  mov     rax, [rax+10h]
0x18001f668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f66d  lea     r8d, [rsi+1]
0x18001f671  mov     rdx, rdi
0x18001f674  mov     ecx, eax
0x18001f676  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18001f67b  cmp     [rbx+84h], esi
0x18001f681  jz      short loc_18001F699
0x18001f683  mov     rcx, rbx; this
0x18001f686  call    ?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ; ServiceBase::_SetShutdownRegistryKey(void)
0x18001f68b  lea     r8d, [rsi+2]
0x18001f68f  mov     rdx, rdi
0x18001f692  mov     ecx, eax
0x18001f694  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18001f699  mov     rcx, [rbx+58h]; WaitHandle
0x18001f69d  test    rcx, rcx
0x18001f6a0  jz      short loc_18001F6F9
0x18001f6a2  xor     edx, edx; CompletionEvent
0x18001f6a4  call    cs:__imp_UnregisterWaitEx
0x18001f6aa  test    eax, eax
0x18001f6ac  jnz     short loc_18001F6F5
0x18001f6ae  call    cs:__imp_GetLastError
0x18001f6b4  cmp     eax, 3E5h
0x18001f6b9  jz      short loc_18001F6F5
0x18001f6bb  call    cs:__imp_GetLastError
0x18001f6c1  mov     [rbx+6Ch], eax
0x18001f6c4  call    cs:__imp_GetLastError
0x18001f6ca  test    eax, eax
0x18001f6cc  jle     short loc_18001F6D6
0x18001f6ce  movzx   eax, ax
0x18001f6d1  or      eax, 80070000h
0x18001f6d6  mov     rcx, [rbp+348h]; this
0x18001f6dd  test    eax, eax
0x18001f6df  jns     short loc_18001F6F5
0x18001f6e1  mov     r9d, eax; char *
0x18001f6e4  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f6eb  mov     edx, 0F2h; void *
0x18001f6f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f6f5  mov     [rbx+58h], rsi
0x18001f6f9  xor     edx, edx; dwReserved
0x18001f6fb  mov     ecx, 7530h; dwUnloadDelay
0x18001f700  call    cs:__imp_CoFreeUnusedLibrariesEx
0x18001f706  mov     edx, 1; unsigned int
0x18001f70b  mov     rcx, rbx; this
0x18001f70e  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18001f713  mov     r8d, 3
0x18001f719  mov     rdx, rdi
0x18001f71c  mov     ecx, eax
0x18001f71e  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18001f723  mov     rdx, rdi; unsigned __int16 *
0x18001f726  lea     rcx, [rsp+440h+var_420]; this
0x18001f72b  call    ?Stop@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z; ServiceHostTelemetry::ServiceStopActivity::Stop(ushort const *,long)
0x18001f730  lea     rdx, aStopped; "Stopped"
0x18001f737  mov     rcx, rdi
0x18001f73a  call    ??$ServiceBaseStatus@AEAY0CA@GAEAY07$$CBG@ServiceHostTelemetry@@SAXAEAY0CA@GAEAY07$$CBG@Z; ServiceHostTelemetry::ServiceBaseStatus<ushort (&)[32],ushort const (&)[8]>(ushort (&)[32],ushort const (&)[8])
0x18001f73f  nop
0x18001f740  lea     rcx, [rsp+440h+var_420]; this
0x18001f745  call    ??1ServiceStopActivity@ServiceHostTelemetry@@QEAA@XZ; ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(void)
0x18001f74a  mov     rcx, [rbp+340h+var_30]
0x18001f751  xor     rcx, rsp; StackCookie
0x18001f754  call    __security_check_cookie
0x18001f759  add     rsp, 428h
0x18001f760  pop     rdi
0x18001f761  pop     rsi
0x18001f762  pop     rbx
0x18001f763  pop     rbp
0x18001f764  retn
```
