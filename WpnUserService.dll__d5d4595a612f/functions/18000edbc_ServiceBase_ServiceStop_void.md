# ServiceBase::ServiceStop(void)

- ea: `0x18000edbc`
- end: `0x18000f08b`
- name: `?ServiceStop@ServiceBase@@QEAAXXZ`
- size: `719`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ddd4`
- `0x18000e9e8`
- `0x1800101d0`

## callees

- `0x180001c7c`
- `0x180002bc0`
- `0x18000a648`
- `0x18000ce58`
- `0x18000d9a0`
- `0x18000dc1c`
- `0x18000dcdc`
- `0x18000df78`
- `0x18000e2ec`
- `0x18000e554`
- `0x18000edbc`
- `0x18000f28c`
- `0x18000f908`
- `0x180010884`
- `0x18001096c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ef20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ef0f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000ef0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ef18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000ef18`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000efe2`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000efe2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ef82`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ef82`

## string_xrefs

- `0x18000ede8`: `ServiceStopActivity`
- `0x18000ee09`: `ServiceStopActivity`
- `0x18000efc2`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
void __fastcall ServiceBase::ServiceStop(ServiceBase *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  struct _TP_WORK *v5; // r14
  DWORD LastError; // ebx
  int v7; // eax
  int v8; // eax
  void *v9; // rcx
  signed int v10; // eax
  int updated; // eax
  int v12; // r8d
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  const wchar_t *v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[39]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+178h] [rbp+78h]
  _QWORD v20[42]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v21[42]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v18,
    (__int64)"ServiceStopActivity");
  v18[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v20,
    (__int64)"ServiceStopActivity");
  v20[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  ServiceHostTelemetry::ServiceStopActivity::StartActivity(
    (ServiceHostTelemetry::ServiceStopActivity *)v20,
    (const unsigned __int16 *)this + 4,
    *((_DWORD *)this + 33));
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v21,
    (__int64)v18,
    v19 != 0);
  v21[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(
    (__int64)v18,
    (__int64)v20);
  v21[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v21);
  v20[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v20);
  v2 = ServiceHostLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v16 = L"Stopping";
    *(_QWORD *)v17 = (char *)this + 8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&byte_1800154E7,
      v3,
      v4,
      (__int64 **)v17,
      (__int64 **)&v16);
  }
  if ( *((_DWORD *)this + 31) )
  {
    v5 = (struct _TP_WORK *)*((_QWORD *)this + 23);
    if ( v5 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v5, 1);
      CloseThreadpoolWork(v5);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 23) = 0;
    v7 = (*(__int64 (__fastcall **)(ServiceBase *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 33));
    LogIfStopSrvFailedAndReturnHr(v7, (__int64)this + 8, 1);
    if ( *((_DWORD *)this + 33) )
    {
      v8 = ServiceBase::_SetShutdownRegistryKey(this);
      LogIfStopSrvFailedAndReturnHr(v8, (__int64)this + 8, 2);
    }
  }
  v9 = (void *)*((_QWORD *)this + 11);
  if ( v9 )
  {
    if ( !UnregisterWaitEx(v9, 0) && GetLastError() != 997 )
    {
      *((_DWORD *)this + 27) = GetLastError();
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF2,
          (__int64)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
          (const char *)(unsigned int)v10);
    }
    *((_QWORD *)this + 11) = 0;
  }
  CoFreeUnusedLibrariesEx(0x7530u, 0);
  updated = ServiceBase::_UpdateStatus(this, 1);
  LogIfStopSrvFailedAndReturnHr(updated, (__int64)this + 8, 3);
  ServiceHostTelemetry::ServiceStopActivity::Stop(
    (ServiceHostTelemetry::ServiceStopActivity *)v18,
    (const unsigned __int16 *)this + 4,
    v12);
  v13 = ServiceHostLogging::Provider();
  if ( *(_DWORD *)v13 > 5u )
  {
    *(_QWORD *)v17 = L"Stopped";
    v16 = (const wchar_t *)((char *)this + 8);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v13,
      (__int64)&unk_180015478,
      v14,
      v15,
      (__int64 **)&v16,
      (__int64 **)v17);
  }
  v18[0] = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v18);
}

```

## disassembly

```asm
0x18000edbc  push    rbp
0x18000edbe  push    rbx
0x18000edbf  push    rsi
0x18000edc0  push    rdi
0x18000edc1  push    r13
0x18000edc3  push    r14
0x18000edc5  lea     rbp, [rsp-348h]
0x18000edcd  sub     rsp, 448h
0x18000edd4  mov     rax, cs:__security_cookie
0x18000eddb  xor     rax, rsp
0x18000edde  mov     [rbp+370h+var_40], rax
0x18000ede5  mov     rdi, rcx
0x18000ede8  lea     rdx, aServicestopact; "ServiceStopActivity"
0x18000edef  lea     rcx, [rsp+470h+var_430]
0x18000edf4  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000edf9  lea     r13, ??_7ServiceStopActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStopActivity::`vftable'
0x18000ee00  mov     [rsp+470h+var_430], r13
0x18000ee05  lea     rsi, [rdi+8]
0x18000ee09  lea     rdx, aServicestopact; "ServiceStopActivity"
0x18000ee10  lea     rcx, [rbp+370h+var_2E0]
0x18000ee17  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ee1c  mov     [rbp+370h+var_2E0], r13
0x18000ee23  mov     r8d, [rdi+84h]; int
0x18000ee2a  mov     rdx, rsi; unsigned __int16 *
0x18000ee2d  lea     rcx, [rbp+370h+var_2E0]; this
0x18000ee34  call    ?StartActivity@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGH@Z; ServiceHostTelemetry::ServiceStopActivity::StartActivity(ushort const *,int)
0x18000ee39  nop
0x18000ee3a  cmp     [rbp+370h+var_2F8], 0
0x18000ee3e  setnz   r8b
0x18000ee42  lea     rdx, [rsp+470h+var_430]
0x18000ee47  lea     rcx, [rbp+370h+var_190]
0x18000ee4e  call    ??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18000ee53  mov     [rbp+370h+var_190], r13
0x18000ee5a  lea     rdx, [rbp+370h+var_2E0]
0x18000ee61  lea     rcx, [rsp+470h+var_430]
0x18000ee66  call    ??4?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&)
0x18000ee6b  mov     [rbp+370h+var_190], r13
0x18000ee72  lea     rcx, [rbp+370h+var_190]
0x18000ee79  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ee7e  lea     rcx, [rbp+370h+var_190]
0x18000ee85  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ee8a  mov     [rbp+370h+var_2E0], r13
0x18000ee91  lea     rcx, [rbp+370h+var_2E0]
0x18000ee98  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ee9d  lea     rcx, [rbp+370h+var_2E0]
0x18000eea4  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000eea9  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000eeae  mov     ecx, [rax]
0x18000eeb0  cmp     ecx, 5
0x18000eeb3  jbe     short loc_18000EEE9
0x18000eeb5  lea     rcx, aStopping; "Stopping"
0x18000eebc  mov     [rsp+470h+var_440], rcx
0x18000eec1  mov     qword ptr [rsp+470h+var_438], rsi
0x18000eec6  lea     rcx, [rsp+470h+var_440]
0x18000eecb  mov     [rsp+470h+var_448], rcx
0x18000eed0  lea     rcx, [rsp+470h+var_438]
0x18000eed5  mov     qword ptr [rsp+470h+var_450], rcx; int
0x18000eeda  lea     rdx, byte_1800154E7
0x18000eee1  mov     rcx, rax
0x18000eee4  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000eee9  cmp     dword ptr [rdi+7Ch], 0
0x18000eeed  jz      loc_18000EF77
0x18000eef3  mov     r14, [rdi+0B8h]
0x18000eefa  test    r14, r14
0x18000eefd  jz      short loc_18000EF26
0x18000eeff  call    cs:__imp_GetLastError
0x18000ef05  mov     ebx, eax
0x18000ef07  mov     edx, 1; fCancelPendingCallbacks
0x18000ef0c  mov     rcx, r14; pwk
0x18000ef0f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000ef15  mov     rcx, r14; pwk
0x18000ef18  call    cs:__imp_CloseThreadpoolWork
0x18000ef1e  mov     ecx, ebx; dwErrCode
0x18000ef20  call    cs:__imp_SetLastError
0x18000ef26  mov     qword ptr [rdi+0B8h], 0
0x18000ef31  mov     rax, [rdi]
0x18000ef34  mov     edx, [rdi+84h]
0x18000ef3a  mov     rcx, rdi
0x18000ef3d  mov     rax, [rax+10h]
0x18000ef41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef46  mov     r8d, 1
0x18000ef4c  mov     rdx, rsi
0x18000ef4f  mov     ecx, eax
0x18000ef51  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18000ef56  cmp     dword ptr [rdi+84h], 0
0x18000ef5d  jz      short loc_18000EF77
0x18000ef5f  mov     rcx, rdi; this
0x18000ef62  call    ?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ; ServiceBase::_SetShutdownRegistryKey(void)
0x18000ef67  mov     r8d, 2
0x18000ef6d  mov     rdx, rsi
0x18000ef70  mov     ecx, eax
0x18000ef72  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18000ef77  mov     rcx, [rdi+58h]; WaitHandle
0x18000ef7b  test    rcx, rcx
0x18000ef7e  jz      short loc_18000EFDB
0x18000ef80  xor     edx, edx; CompletionEvent
0x18000ef82  call    cs:__imp_UnregisterWaitEx
0x18000ef88  test    eax, eax
0x18000ef8a  jnz     short loc_18000EFD3
0x18000ef8c  call    cs:__imp_GetLastError
0x18000ef92  cmp     eax, 3E5h
0x18000ef97  jz      short loc_18000EFD3
0x18000ef99  call    cs:__imp_GetLastError
0x18000ef9f  mov     [rdi+6Ch], eax
0x18000efa2  call    cs:__imp_GetLastError
0x18000efa8  test    eax, eax
0x18000efaa  jle     short loc_18000EFB4
0x18000efac  movzx   eax, ax
0x18000efaf  or      eax, 80070000h
0x18000efb4  mov     rcx, [rbp+378h]; this
0x18000efbb  test    eax, eax
0x18000efbd  jns     short loc_18000EFD3
0x18000efbf  mov     r9d, eax; char *
0x18000efc2  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000efc9  mov     edx, 0F2h; void *
0x18000efce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000efd3  mov     qword ptr [rdi+58h], 0
0x18000efdb  xor     edx, edx; dwReserved
0x18000efdd  mov     ecx, 7530h; dwUnloadDelay
0x18000efe2  call    cs:__imp_CoFreeUnusedLibrariesEx
0x18000efe8  mov     edx, 1; unsigned int
0x18000efed  mov     rcx, rdi; this
0x18000eff0  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18000eff5  mov     r8d, 3
0x18000effb  mov     rdx, rsi
0x18000effe  mov     ecx, eax
0x18000f000  call    ?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z; LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)
0x18000f005  mov     rdx, rsi; unsigned __int16 *
0x18000f008  lea     rcx, [rsp+470h+var_430]; this
0x18000f00d  call    ?Stop@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z; ServiceHostTelemetry::ServiceStopActivity::Stop(ushort const *,long)
0x18000f012  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f017  mov     ecx, [rax]
0x18000f019  cmp     ecx, 5
0x18000f01c  jbe     short loc_18000F053
0x18000f01e  lea     rcx, aStopped; "Stopped"
0x18000f025  mov     qword ptr [rsp+470h+var_438], rcx
0x18000f02a  mov     [rsp+470h+var_440], rsi
0x18000f02f  lea     rcx, [rsp+470h+var_438]
0x18000f034  mov     [rsp+470h+var_448], rcx
0x18000f039  lea     rcx, [rsp+470h+var_440]
0x18000f03e  mov     qword ptr [rsp+470h+var_450], rcx
0x18000f043  lea     rdx, unk_180015478
0x18000f04a  mov     rcx, rax
0x18000f04d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f052  nop
0x18000f053  mov     [rsp+470h+var_430], r13
0x18000f058  lea     rcx, [rsp+470h+var_430]
0x18000f05d  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000f062  lea     rcx, [rsp+470h+var_430]
0x18000f067  call    ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000f06c  mov     rcx, [rbp+370h+var_40]
0x18000f073  xor     rcx, rsp; StackCookie
0x18000f076  call    __security_check_cookie
0x18000f07b  add     rsp, 448h
0x18000f082  pop     r14
0x18000f084  pop     r13
0x18000f086  pop     rdi
0x18000f087  pop     rsi
0x18000f088  pop     rbx
0x18000f089  pop     rbp
0x18000f08a  retn
```
