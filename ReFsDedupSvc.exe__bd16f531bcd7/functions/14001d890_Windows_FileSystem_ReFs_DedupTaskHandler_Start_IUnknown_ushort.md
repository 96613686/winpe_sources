# Windows::FileSystem::ReFs::DedupTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x14001d890`
- end: `0x14001db69`
- name: `?Start@DedupTaskHandler@ReFs@FileSystem@Windows@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `729`
- prototype: `__int64 __fastcall(Windows::FileSystem::ReFs::DedupTaskHandler *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004870`
- `0x1400117bc`
- `0x140015bc4`
- `0x140016bf8`
- `0x1400194a0`
- `0x14001abfc`
- `0x14001b158`
- `0x14001b6a4`
- `0x14001b6d8`
- `0x14001b880`
- `0x14001be28`
- `0x14001bfc4`
- `0x14001c148`
- `0x14001c1f4`
- `0x14001c61c`
- `0x14001d850`
- `0x14001d890`
- `0x14001db70`
- `0x14001f45c`
- `0x140020660`
- `0x140033d3c`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x14001d8f6`
- `OLEAUT32!__imp_SysStringLen` at `0x14001d8f6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001d9c0`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001d9c0`

## string_xrefs

- `0x14001d8b6`: `DedupTask`
- `0x14001d954`: `onecore\base\fs\refsdedupsvc\exe\deduptaskhandler.cpp`
- `0x14001d9dd`: `onecore\base\fs\refsdedupsvc\exe\deduptaskhandler.cpp`
- `0x14001db19`: `onecore\base\fs\refsdedupsvc\exe\deduptaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall Windows::FileSystem::ReFs::DedupTaskHandler::Start(
        Windows::FileSystem::ReFs::DedupTaskHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rcx
  const char *v8; // r9
  __int64 result; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  int v12; // ebx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  _BYTE *v16; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // rax
  int v19; // [rsp+20h] [rbp-348h]
  const char *v20; // [rsp+28h] [rbp-340h]
  LPSTREAM ppStm; // [rsp+30h] [rbp-338h] BYREF
  __int64 v22; // [rsp+38h] [rbp-330h] BYREF
  std::_Ref_count_base *v23; // [rsp+40h] [rbp-328h]
  __int128 v24; // [rsp+48h] [rbp-320h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-310h] BYREF
  _BYTE v26[8]; // [rsp+60h] [rbp-308h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-300h] BYREF
  _QWORD v28[42]; // [rsp+80h] [rbp-2E8h] BYREF
  _BYTE v29[368]; // [rsp+1D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v28);
  v28[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::StartActivity(
    (Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28,
    a3);
  try
  {
    if ( a3 && SysStringLen(a3) )
    {
      v24 = (__int128)*Microsoft::COM::Client::to_guid(&pclsid, a3, v6);
      Windows::FileSystem::ReFs::ReFsDedupService::FindVolume(v7, &v22, &v24);
      if ( v22 )
      {
        std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(
          &v24,
          (char *)this + 24);
        std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
          (char *)this + 56,
          &v22);
        ppStm = 0;
        v10 = CoMarshalInterThreadInterfaceInStream(&GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a, a2, &ppStm);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(
                  v26,
                  &ppStm);
          v13 = wil::com_ptr_t<ITaskHandler,wil::err_exception_policy>::com_ptr_t<ITaskHandler,wil::err_exception_policy>(
                  v25,
                  this);
          v14 = Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1_::_lambda_1__0(
                  (unsigned int)v29,
                  v12,
                  (unsigned int)v28,
                  v13,
                  (__int64)this);
          v16 = (_BYTE *)std::async__Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1___(
                           &pclsid,
                           v15,
                           v14);
          v17 = (_QWORD *)((char *)this + 40);
          if ( (char *)this + 40 != v16 )
          {
            if ( *v17 )
              std::_Associated_state<long>::_Release();
            v18 = *(_QWORD *)v16;
            *(_QWORD *)v16 = 0;
            *v17 = v18;
            *((_BYTE *)this + 48) = v16[8];
          }
          std::_State_manager<long>::~_State_manager<long>(&pclsid);
          Windows::FileSystem::ReFs::DedupTaskHandler::Start_::_3_::_lambda_1_::__lambda_1_(v29);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v25);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v26);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(&ppStm);
          std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v24);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\deduptaskhandler.cpp",
            (const char *)(unsigned int)v10,
            v19);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(&ppStm);
          std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v24);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28);
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\deduptaskhandler.cpp",
          (const char *)0x80070490LL,
          (int)"Specified volume is no longer monitored",
          v20);
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28);
        result = 2147943568LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\deduptaskhandler.cpp",
        (const char *)0x8000000ELL,
        v19);
      Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28);
      result = 2147483662LL;
    }
  }
  catch ( ... )
  {
    LODWORD(ppStm) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x64,
                       (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\deduptaskhandler.cpp",
                       v8);
    Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask *)v28);
    return (unsigned int)ppStm;
  }
  return result;
}

```

## disassembly

```asm
0x14001d890  push    rbx
0x14001d892  push    rsi
0x14001d893  push    rdi
0x14001d894  sub     rsp, 350h
0x14001d89b  mov     rax, cs:__security_cookie
0x14001d8a2  xor     rax, rsp
0x14001d8a5  mov     [rsp+368h+var_28], rax
0x14001d8ad  mov     rbx, r8
0x14001d8b0  mov     rdi, rdx
0x14001d8b3  mov     rsi, rcx
0x14001d8b6  lea     rdx, aDeduptask; "DedupTask"
0x14001d8bd  lea     rcx, [rsp+368h+var_2E8]; struct wil::details::IFailureCallback *
0x14001d8c5  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001d8ca  lea     rax, ??_7DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::`vftable'
0x14001d8d1  mov     [rsp+368h+var_2E8], rax
0x14001d8d9  mov     rdx, rbx; unsigned __int16 *
0x14001d8dc  lea     rcx, [rsp+368h+var_2E8]; this
0x14001d8e4  call    ?StartActivity@DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXPEAG@Z; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::StartActivity(ushort *)
0x14001d8e9  nop
0x14001d8ea  test    rbx, rbx
0x14001d8ed  jz      loc_14001DB09
0x14001d8f3  mov     rcx, rbx; pbstr
0x14001d8f6  call    cs:__imp_SysStringLen
0x14001d8fd  nop     dword ptr [rax+rax+00h]
0x14001d902  test    eax, eax
0x14001d904  jz      loc_14001DB09
0x14001d90a  mov     rdx, rbx; lpsz
0x14001d90d  lea     rcx, [rsp+368h+pclsid]; pclsid
0x14001d912  call    ?to_guid@Client@COM@Microsoft@@YA?AU_GUID@@PEBG@Z; Microsoft::COM::Client::to_guid(ushort const *)
0x14001d917  movups  xmm0, xmmword ptr [rax]
0x14001d91a  movdqu  [rsp+368h+var_320], xmm0
0x14001d920  lea     r8, [rsp+368h+var_320]
0x14001d925  lea     rdx, [rsp+368h+var_330]
0x14001d92a  call    ?FindVolume@ReFsDedupService@ReFs@FileSystem@Windows@@QEAA?AV?$shared_ptr@VDedupVolume@ReFs@FileSystem@Windows@@@std@@AEBU_GUID@@@Z; Windows::FileSystem::ReFs::ReFsDedupService::FindVolume(_GUID const &)
0x14001d92f  nop
0x14001d930  cmp     [rsp+368h+var_330], 0
0x14001d936  jnz     short loc_14001D98A
0x14001d938  mov     rcx, [rsp+368h]; this
0x14001d940  lea     rax, aSpecifiedVolum; "Specified volume is no longer monitored"
0x14001d947  mov     qword ptr [rsp+368h+var_348], rax; int
0x14001d94c  mov     ebx, 80070490h
0x14001d951  mov     r9d, ebx; char *
0x14001d954  lea     r8, aOnecoreBaseFsR_37; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x14001d95b  mov     edx, 3Eh ; '>'; void *
0x14001d960  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14001d965  nop
0x14001d966  mov     rcx, [rsp+368h+var_328]; this
0x14001d96b  test    rcx, rcx
0x14001d96e  jz      short loc_14001D976
0x14001d970  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001d975  nop
0x14001d976  lea     rcx, [rsp+368h+var_2E8]; this
0x14001d97e  call    ??1DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask(void)
0x14001d983  mov     eax, ebx
0x14001d985  jmp     loc_14001DB4D
0x14001d98a  lea     rdx, [rsi+18h]
0x14001d98e  lea     rcx, [rsp+368h+var_320]
0x14001d993  call    ??0?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@AEAVOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@Z; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(Microsoft::Win32::Locks::OwnerTrackingSharedMutex &)
0x14001d998  nop
0x14001d999  lea     rcx, [rsi+38h]
0x14001d99d  lea     rdx, [rsp+368h+var_330]
0x14001d9a2  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x14001d9a7  nop
0x14001d9a8  mov     [rsp+368h+ppStm], 0
0x14001d9b1  lea     r8, [rsp+368h+ppStm]; ppStm
0x14001d9b6  mov     rdx, rdi; pUnk
0x14001d9b9  lea     rcx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a; riid
0x14001d9c0  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x14001d9c7  nop     dword ptr [rax+rax+00h]
0x14001d9cc  mov     ebx, eax
0x14001d9ce  test    eax, eax
0x14001d9d0  jns     short loc_14001DA29
0x14001d9d2  mov     rcx, [rsp+368h]; this
0x14001d9da  mov     r9d, eax; char *
0x14001d9dd  lea     r8, aOnecoreBaseFsR_37; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x14001d9e4  mov     edx, 44h ; 'D'; void *
0x14001d9e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d9ee  nop
0x14001d9ef  lea     rcx, [rsp+368h+ppStm]
0x14001d9f4  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14001d9f9  nop
0x14001d9fa  lea     rcx, [rsp+368h+var_320]
0x14001d9ff  call    ??1?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@XZ; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(void)
0x14001da04  nop
0x14001da05  mov     rcx, [rsp+368h+var_328]; this
0x14001da0a  test    rcx, rcx
0x14001da0d  jz      short loc_14001DA15
0x14001da0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001da14  nop
0x14001da15  lea     rcx, [rsp+368h+var_2E8]; this
0x14001da1d  call    ??1DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask(void)
0x14001da22  mov     eax, ebx
0x14001da24  jmp     loc_14001DB4D
0x14001da29  lea     rdx, [rsp+368h+ppStm]
0x14001da2e  lea     rcx, [rsp+368h+var_308]
0x14001da33  call    ??0?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy> const &)
0x14001da38  mov     rbx, rax
0x14001da3b  mov     rdx, rsi
0x14001da3e  lea     rcx, [rsp+368h+var_310]
0x14001da43  call    ??0?$com_ptr_t@UITaskHandler@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUITaskHandler@@@Z; wil::com_ptr_t<ITaskHandler,wil::err_exception_policy>::com_ptr_t<ITaskHandler,wil::err_exception_policy>(ITaskHandler *)
0x14001da48  nop
0x14001da49  mov     qword ptr [rsp+368h+var_348], rsi
0x14001da4e  mov     r9, rax
0x14001da51  lea     r8, [rsp+368h+var_2E8]
0x14001da59  mov     rdx, rbx
0x14001da5c  lea     rcx, [rsp+368h+var_198]
0x14001da64  call    _Windows__FileSystem__ReFs__DedupTaskHandler__Start____3____lambda_1____lambda_1__0
0x14001da69  nop
0x14001da6a  mov     r8, rax
0x14001da6d  lea     rcx, [rsp+368h+pclsid]
0x14001da72  call    std__async__Windows__FileSystem__ReFs__DedupTaskHandler__Start____3____lambda_1___
0x14001da77  mov     rdi, rax
0x14001da7a  lea     rbx, [rsi+28h]
0x14001da7e  cmp     rbx, rax
0x14001da81  jz      short loc_14001DAA3
0x14001da83  mov     rcx, [rbx]
0x14001da86  test    rcx, rcx
0x14001da89  jz      short loc_14001DA90
0x14001da8b  call    ?_Release@?$_Associated_state@J@std@@QEAAXXZ; std::_Associated_state<long>::_Release(void)
0x14001da90  mov     rax, [rdi]
0x14001da93  mov     qword ptr [rdi], 0
0x14001da9a  mov     [rbx], rax
0x14001da9d  mov     al, [rdi+8]
0x14001daa0  mov     [rbx+8], al
0x14001daa3  lea     rcx, [rsp+368h+pclsid]
0x14001daa8  call    ??1?$_State_manager@J@std@@QEAA@XZ; std::_State_manager<long>::~_State_manager<long>(void)
0x14001daad  nop
0x14001daae  lea     rcx, [rsp+368h+var_198]
0x14001dab6  call    _Windows__FileSystem__ReFs__DedupTaskHandler__Start____3____lambda_1_____lambda_1_
0x14001dabb  nop
0x14001dabc  lea     rcx, [rsp+368h+var_310]
0x14001dac1  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14001dac6  nop
0x14001dac7  lea     rcx, [rsp+368h+var_308]
0x14001dacc  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14001dad1  nop
0x14001dad2  lea     rcx, [rsp+368h+ppStm]
0x14001dad7  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14001dadc  nop
0x14001dadd  lea     rcx, [rsp+368h+var_320]
0x14001dae2  call    ??1?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@XZ; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(void)
0x14001dae7  nop
0x14001dae8  mov     rcx, [rsp+368h+var_328]; this
0x14001daed  test    rcx, rcx
0x14001daf0  jz      short loc_14001DAF8
0x14001daf2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001daf7  nop
0x14001daf8  lea     rcx, [rsp+368h+var_2E8]; this
0x14001db00  call    ??1DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask(void)
0x14001db05  xor     eax, eax
0x14001db07  jmp     short loc_14001DB4D
0x14001db09  mov     rcx, [rsp+368h]; this
0x14001db11  mov     ebx, 8000000Eh
0x14001db16  mov     r9d, ebx; char *
0x14001db19  lea     r8, aOnecoreBaseFsR_37; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x14001db20  mov     edx, 3Ah ; ':'; void *
0x14001db25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001db2a  nop
0x14001db2b  lea     rcx, [rsp+368h+var_2E8]; this
0x14001db33  call    ??1DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask(void)
0x14001db38  mov     eax, ebx
0x14001db3a  jmp     short loc_14001DB4D
0x14001db3c  lea     rcx, [rsp+368h+var_2E8]; this
0x14001db44  call    ??1DedupTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupTask::~DedupTask(void)
0x14001db49  mov     eax, dword ptr [rsp+368h+ppStm]
0x14001db4d  mov     rcx, [rsp+368h+var_28]
0x14001db55  xor     rcx, rsp; StackCookie
0x14001db58  call    __security_check_cookie
0x14001db5d  add     rsp, 350h
0x14001db64  pop     rdi
0x14001db65  pop     rsi
0x14001db66  pop     rbx
0x14001db67  retn
```
