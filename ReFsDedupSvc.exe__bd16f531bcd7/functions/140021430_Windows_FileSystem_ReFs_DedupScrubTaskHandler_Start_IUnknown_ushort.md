# Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x140021430`
- end: `0x140021709`
- name: `?Start@DedupScrubTaskHandler@ReFs@FileSystem@Windows@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `729`
- prototype: `__int64 __fastcall(Windows::FileSystem::ReFs::DedupScrubTaskHandler *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004870`
- `0x1400117bc`
- `0x140015bc4`
- `0x140016bf8`
- `0x1400194a0`
- `0x14001b6a4`
- `0x14001b6d8`
- `0x14001b880`
- `0x14001bfc4`
- `0x14001c148`
- `0x14001c61c`
- `0x14001d850`
- `0x14001f45c`
- `0x140020660`
- `0x140020abc`
- `0x140020d10`
- `0x140020db8`
- `0x140020e48`
- `0x140021430`
- `0x140021710`
- `0x140033d3c`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x140021496`
- `OLEAUT32!__imp_SysStringLen` at `0x140021496`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140021560`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140021560`

## string_xrefs

- `0x140021456`: `DedupScrubTask`
- `0x1400214f4`: `onecore\base\fs\refsdedupsvc\exe\dedupscrubtaskhandler.cpp`
- `0x14002157d`: `onecore\base\fs\refsdedupsvc\exe\dedupscrubtaskhandler.cpp`
- `0x1400216b9`: `onecore\base\fs\refsdedupsvc\exe\dedupscrubtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start(
        Windows::FileSystem::ReFs::DedupScrubTaskHandler *this,
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
  v28[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::StartActivity(
    (Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28,
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
          v14 = Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1_::_lambda_1__0(
                  (unsigned int)v29,
                  v12,
                  (unsigned int)v28,
                  v13,
                  (__int64)this);
          v16 = (_BYTE *)std::async__Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1___(
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
          Windows::FileSystem::ReFs::DedupScrubTaskHandler::Start_::_3_::_lambda_1_::__lambda_1_(v29);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v25);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(v26);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(&ppStm);
          std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v24);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupscrubtaskhandler.cpp",
            (const char *)(unsigned int)v10,
            v19);
          wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(&ppStm);
          std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(&v24);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28);
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupscrubtaskhandler.cpp",
          (const char *)0x80070490LL,
          (int)"Specified volume is no longer monitored",
          v20);
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28);
        result = 2147943568LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupscrubtaskhandler.cpp",
        (const char *)0x8000000ELL,
        v19);
      Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28);
      result = 2147483662LL;
    }
  }
  catch ( ... )
  {
    LODWORD(ppStm) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x64,
                       (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\dedupscrubtaskhandler.cpp",
                       v8);
    Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask *)v28);
    return (unsigned int)ppStm;
  }
  return result;
}

```

## disassembly

```asm
0x140021430  push    rbx
0x140021432  push    rsi
0x140021433  push    rdi
0x140021434  sub     rsp, 350h
0x14002143b  mov     rax, cs:__security_cookie
0x140021442  xor     rax, rsp
0x140021445  mov     [rsp+368h+var_28], rax
0x14002144d  mov     rbx, r8
0x140021450  mov     rdi, rdx
0x140021453  mov     rsi, rcx
0x140021456  lea     rdx, aDedupscrubtask; "DedupScrubTask"
0x14002145d  lea     rcx, [rsp+368h+var_2E8]; struct wil::details::IFailureCallback *
0x140021465  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14002146a  lea     rax, ??_7DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::`vftable'
0x140021471  mov     [rsp+368h+var_2E8], rax
0x140021479  mov     rdx, rbx; unsigned __int16 *
0x14002147c  lea     rcx, [rsp+368h+var_2E8]; this
0x140021484  call    ?StartActivity@DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXPEAG@Z; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::StartActivity(ushort *)
0x140021489  nop
0x14002148a  test    rbx, rbx
0x14002148d  jz      loc_1400216A9
0x140021493  mov     rcx, rbx; pbstr
0x140021496  call    cs:__imp_SysStringLen
0x14002149d  nop     dword ptr [rax+rax+00h]
0x1400214a2  test    eax, eax
0x1400214a4  jz      loc_1400216A9
0x1400214aa  mov     rdx, rbx; lpsz
0x1400214ad  lea     rcx, [rsp+368h+pclsid]; pclsid
0x1400214b2  call    ?to_guid@Client@COM@Microsoft@@YA?AU_GUID@@PEBG@Z; Microsoft::COM::Client::to_guid(ushort const *)
0x1400214b7  movups  xmm0, xmmword ptr [rax]
0x1400214ba  movdqu  [rsp+368h+var_320], xmm0
0x1400214c0  lea     r8, [rsp+368h+var_320]
0x1400214c5  lea     rdx, [rsp+368h+var_330]
0x1400214ca  call    ?FindVolume@ReFsDedupService@ReFs@FileSystem@Windows@@QEAA?AV?$shared_ptr@VDedupVolume@ReFs@FileSystem@Windows@@@std@@AEBU_GUID@@@Z; Windows::FileSystem::ReFs::ReFsDedupService::FindVolume(_GUID const &)
0x1400214cf  nop
0x1400214d0  cmp     [rsp+368h+var_330], 0
0x1400214d6  jnz     short loc_14002152A
0x1400214d8  mov     rcx, [rsp+368h]; this
0x1400214e0  lea     rax, aSpecifiedVolum; "Specified volume is no longer monitored"
0x1400214e7  mov     qword ptr [rsp+368h+var_348], rax; int
0x1400214ec  mov     ebx, 80070490h
0x1400214f1  mov     r9d, ebx; char *
0x1400214f4  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x1400214fb  mov     edx, 3Eh ; '>'; void *
0x140021500  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140021505  nop
0x140021506  mov     rcx, [rsp+368h+var_328]; this
0x14002150b  test    rcx, rcx
0x14002150e  jz      short loc_140021516
0x140021510  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140021515  nop
0x140021516  lea     rcx, [rsp+368h+var_2E8]; this
0x14002151e  call    ??1DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask(void)
0x140021523  mov     eax, ebx
0x140021525  jmp     loc_1400216ED
0x14002152a  lea     rdx, [rsi+18h]
0x14002152e  lea     rcx, [rsp+368h+var_320]
0x140021533  call    ??0?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@AEAVOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@Z; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(Microsoft::Win32::Locks::OwnerTrackingSharedMutex &)
0x140021538  nop
0x140021539  lea     rcx, [rsi+38h]
0x14002153d  lea     rdx, [rsp+368h+var_330]
0x140021542  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x140021547  nop
0x140021548  mov     [rsp+368h+ppStm], 0
0x140021551  lea     r8, [rsp+368h+ppStm]; ppStm
0x140021556  mov     rdx, rdi; pUnk
0x140021559  lea     rcx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a; riid
0x140021560  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x140021567  nop     dword ptr [rax+rax+00h]
0x14002156c  mov     ebx, eax
0x14002156e  test    eax, eax
0x140021570  jns     short loc_1400215C9
0x140021572  mov     rcx, [rsp+368h]; this
0x14002157a  mov     r9d, eax; char *
0x14002157d  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x140021584  mov     edx, 44h ; 'D'; void *
0x140021589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002158e  nop
0x14002158f  lea     rcx, [rsp+368h+ppStm]
0x140021594  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140021599  nop
0x14002159a  lea     rcx, [rsp+368h+var_320]
0x14002159f  call    ??1?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@XZ; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(void)
0x1400215a4  nop
0x1400215a5  mov     rcx, [rsp+368h+var_328]; this
0x1400215aa  test    rcx, rcx
0x1400215ad  jz      short loc_1400215B5
0x1400215af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400215b4  nop
0x1400215b5  lea     rcx, [rsp+368h+var_2E8]; this
0x1400215bd  call    ??1DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask(void)
0x1400215c2  mov     eax, ebx
0x1400215c4  jmp     loc_1400216ED
0x1400215c9  lea     rdx, [rsp+368h+ppStm]
0x1400215ce  lea     rcx, [rsp+368h+var_308]
0x1400215d3  call    ??0?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy>(wil::com_ptr_t<ITaskHandlerStatus,wil::err_exception_policy> const &)
0x1400215d8  mov     rbx, rax
0x1400215db  mov     rdx, rsi
0x1400215de  lea     rcx, [rsp+368h+var_310]
0x1400215e3  call    ??0?$com_ptr_t@UITaskHandler@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUITaskHandler@@@Z; wil::com_ptr_t<ITaskHandler,wil::err_exception_policy>::com_ptr_t<ITaskHandler,wil::err_exception_policy>(ITaskHandler *)
0x1400215e8  nop
0x1400215e9  mov     qword ptr [rsp+368h+var_348], rsi
0x1400215ee  mov     r9, rax
0x1400215f1  lea     r8, [rsp+368h+var_2E8]
0x1400215f9  mov     rdx, rbx
0x1400215fc  lea     rcx, [rsp+368h+var_198]
0x140021604  call    _Windows__FileSystem__ReFs__DedupScrubTaskHandler__Start____3____lambda_1____lambda_1__0
0x140021609  nop
0x14002160a  mov     r8, rax
0x14002160d  lea     rcx, [rsp+368h+pclsid]
0x140021612  call    std__async__Windows__FileSystem__ReFs__DedupScrubTaskHandler__Start____3____lambda_1___
0x140021617  mov     rdi, rax
0x14002161a  lea     rbx, [rsi+28h]
0x14002161e  cmp     rbx, rax
0x140021621  jz      short loc_140021643
0x140021623  mov     rcx, [rbx]
0x140021626  test    rcx, rcx
0x140021629  jz      short loc_140021630
0x14002162b  call    ?_Release@?$_Associated_state@J@std@@QEAAXXZ; std::_Associated_state<long>::_Release(void)
0x140021630  mov     rax, [rdi]
0x140021633  mov     qword ptr [rdi], 0
0x14002163a  mov     [rbx], rax
0x14002163d  mov     al, [rdi+8]
0x140021640  mov     [rbx+8], al
0x140021643  lea     rcx, [rsp+368h+pclsid]
0x140021648  call    ??1?$_State_manager@J@std@@QEAA@XZ; std::_State_manager<long>::~_State_manager<long>(void)
0x14002164d  nop
0x14002164e  lea     rcx, [rsp+368h+var_198]
0x140021656  call    _Windows__FileSystem__ReFs__DedupScrubTaskHandler__Start____3____lambda_1_____lambda_1_
0x14002165b  nop
0x14002165c  lea     rcx, [rsp+368h+var_310]
0x140021661  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140021666  nop
0x140021667  lea     rcx, [rsp+368h+var_308]
0x14002166c  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x140021671  nop
0x140021672  lea     rcx, [rsp+368h+ppStm]
0x140021677  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14002167c  nop
0x14002167d  lea     rcx, [rsp+368h+var_320]
0x140021682  call    ??1?$unique_lock@VOwnerTrackingSharedMutex@Locks@Win32@Microsoft@@@std@@QEAA@XZ; std::unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>::~unique_lock<Microsoft::Win32::Locks::OwnerTrackingSharedMutex>(void)
0x140021687  nop
0x140021688  mov     rcx, [rsp+368h+var_328]; this
0x14002168d  test    rcx, rcx
0x140021690  jz      short loc_140021698
0x140021692  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140021697  nop
0x140021698  lea     rcx, [rsp+368h+var_2E8]; this
0x1400216a0  call    ??1DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask(void)
0x1400216a5  xor     eax, eax
0x1400216a7  jmp     short loc_1400216ED
0x1400216a9  mov     rcx, [rsp+368h]; this
0x1400216b1  mov     ebx, 8000000Eh
0x1400216b6  mov     r9d, ebx; char *
0x1400216b9  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\refsdedupsvc\\exe\\d"...
0x1400216c0  mov     edx, 3Ah ; ':'; void *
0x1400216c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400216ca  nop
0x1400216cb  lea     rcx, [rsp+368h+var_2E8]; this
0x1400216d3  call    ??1DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask(void)
0x1400216d8  mov     eax, ebx
0x1400216da  jmp     short loc_1400216ED
0x1400216dc  lea     rcx, [rsp+368h+var_2E8]; this
0x1400216e4  call    ??1DedupScrubTask@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::DedupScrubTask::~DedupScrubTask(void)
0x1400216e9  mov     eax, dword ptr [rsp+368h+ppStm]
0x1400216ed  mov     rcx, [rsp+368h+var_28]
0x1400216f5  xor     rcx, rsp; StackCookie
0x1400216f8  call    __security_check_cookie
0x1400216fd  add     rsp, 350h
0x140021704  pop     rdi
0x140021705  pop     rsi
0x140021706  pop     rbx
0x140021707  retn
```
