# CLocationCrowdsource::Dispose(void)

- ea: `0x1801052e0`
- end: `0x180105440`
- name: `?Dispose@CLocationCrowdsource@@UEAAJXZ`
- size: `352`
- prototype: `__int64 __fastcall(CLocationCrowdsource *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x180013660`
- `0x18003c214`
- `0x180085578`
- `0x180085674`
- `0x1800ad758`
- `0x1800b1230`
- `0x1801052e0`
- `0x18010751c`
- `0x180107c30`
- `0x180133938`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18010534d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18010534d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010535a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010535a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180105313`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180105313`

## pseudocode

```c
__int64 __fastcall CLocationCrowdsource::Dispose(CLocationCrowdsource *this)
{
  void *v2; // rcx
  wil::details *v3; // rdi
  void *v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rcx
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 47) )
  {
    LocationWnfSubscribe_Impl::Unsubscribe((CLocationCrowdsource *)((char *)this + 192));
    v2 = (void *)*((_QWORD *)this + 31);
    if ( v2 )
    {
      PowerSettingUnregisterNotification(v2);
      *((_QWORD *)this + 31) = 0;
    }
    _InterlockedExchange((volatile __int32 *)this + 46, 0);
    ResettableTimer::Dispose((CLocationCrowdsource *)((char *)this + 384));
    CLocationCrowdsource::UnregisterBeaconSink((CLocationCrowdsource *)((char *)this - 40));
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 47), 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 47));
    *((_QWORD *)this + 47) = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl'::`2'::impl) )
    {
      v3 = (wil::details *)*((_QWORD *)this + 9);
      if ( v3 )
      {
        tagETWENCRYPT::~tagETWENCRYPT(*((tagETWENCRYPT **)this + 9));
        wil::details::FreeProcessHeap(v3, v4);
      }
    }
    v5 = *((_QWORD *)this + 37);
    *((_QWORD *)this + 37) = 0;
    if ( v5 )
      std::default_delete<CLocationOrionTelemetry>::operator()();
    if ( *((_QWORD *)this + 34) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 34, 0);
    if ( *((_QWORD *)this + 36) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 36, 0);
    if ( *((_QWORD *)this + 35) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 35, 0);
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      v8,
      (char *)this + 312);
    std::_List_node<CROWDSOURCE_RAWDATA,void *>::_Free_non_head<std::allocator<std::_List_node<CROWDSOURCE_RAWDATA,void *>>>(
      v6,
      *((_QWORD *)this + 45));
    **((_QWORD **)this + 45) = *((_QWORD *)this + 45);
    *(_QWORD *)(*((_QWORD *)this + 45) + 8LL) = *((_QWORD *)this + 45);
    *((_QWORD *)this + 46) = 0;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1801052e0  mov     [rsp+arg_8], rbx
0x1801052e5  push    rdi
0x1801052e6  sub     rsp, 30h
0x1801052ea  cmp     qword ptr [rcx+178h], 0
0x1801052f2  mov     rbx, rcx
0x1801052f5  jz      loc_180105433
0x1801052fb  add     rcx, 0C0h; this
0x180105302  call    ?Unsubscribe@LocationWnfSubscribe_Impl@@QEAAJXZ; LocationWnfSubscribe_Impl::Unsubscribe(void)
0x180105307  mov     rcx, [rbx+0F8h]; RegistrationHandle
0x18010530e  test    rcx, rcx
0x180105311  jz      short loc_180105324
0x180105313  call    cs:__imp_PowerSettingUnregisterNotification
0x180105319  mov     qword ptr [rbx+0F8h], 0
0x180105324  xor     eax, eax
0x180105326  lea     rcx, [rbx+180h]; this
0x18010532d  xchg    eax, [rbx+0B8h]
0x180105333  call    ?Dispose@ResettableTimer@@QEAAXXZ; ResettableTimer::Dispose(void)
0x180105338  lea     rcx, [rbx-28h]; this
0x18010533c  call    ?UnregisterBeaconSink@CLocationCrowdsource@@AEAAXXZ; CLocationCrowdsource::UnregisterBeaconSink(void)
0x180105341  mov     rcx, [rbx+178h]; pwk
0x180105348  mov     edx, 1; fCancelPendingCallbacks
0x18010534d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180105353  mov     rcx, [rbx+178h]; pwk
0x18010535a  call    cs:__imp_CloseThreadpoolWork
0x180105360  mov     qword ptr [rbx+178h], 0
0x18010536b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval> `wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl(void)'::`2'::impl
0x180105372  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(void)
0x180105377  test    al, al
0x180105379  jnz     short loc_180105394
0x18010537b  mov     rdi, [rbx+48h]
0x18010537f  test    rdi, rdi
0x180105382  jz      short loc_180105394
0x180105384  mov     rcx, rdi; this
0x180105387  call    ??1tagETWENCRYPT@@QEAA@XZ; tagETWENCRYPT::~tagETWENCRYPT(void)
0x18010538c  mov     rcx, rdi; this
0x18010538f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180105394  mov     rdx, [rbx+128h]
0x18010539b  mov     qword ptr [rbx+128h], 0
0x1801053a6  test    rdx, rdx
0x1801053a9  jz      short loc_1801053B0
0x1801053ab  call    ??R?$default_delete@VCLocationOrionTelemetry@@@std@@QEBAXPEAVCLocationOrionTelemetry@@@Z; std::default_delete<CLocationOrionTelemetry>::operator()(CLocationOrionTelemetry *)
0x1801053b0  lea     rcx, [rbx+110h]; struct IUnknown **
0x1801053b7  cmp     qword ptr [rcx], 0
0x1801053bb  jz      short loc_1801053C4
0x1801053bd  xor     edx, edx; struct IUnknown *
0x1801053bf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801053c4  lea     rcx, [rbx+120h]; struct IUnknown **
0x1801053cb  cmp     qword ptr [rcx], 0
0x1801053cf  jz      short loc_1801053D8
0x1801053d1  xor     edx, edx; struct IUnknown *
0x1801053d3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801053d8  lea     rcx, [rbx+118h]; struct IUnknown **
0x1801053df  cmp     qword ptr [rcx], 0
0x1801053e3  jz      short loc_1801053EC
0x1801053e5  xor     edx, edx; struct IUnknown *
0x1801053e7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801053ec  lea     rdx, [rbx+138h]
0x1801053f3  lea     rcx, [rsp+38h+var_18]
0x1801053f8  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1801053fd  mov     rdx, [rbx+168h]
0x180105404  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UCROWDSOURCE_RAWDATA@@PEAX@std@@@std@@@?$_List_node@UCROWDSOURCE_RAWDATA@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UCROWDSOURCE_RAWDATA@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<CROWDSOURCE_RAWDATA,void *>::_Free_non_head<std::allocator<std::_List_node<CROWDSOURCE_RAWDATA,void *>>>(std::allocator<std::_List_node<CROWDSOURCE_RAWDATA,void *>> &,std::_List_node<CROWDSOURCE_RAWDATA,void *> *)
0x180105409  mov     rax, [rbx+168h]
0x180105410  lea     rcx, [rsp+38h+var_18]
0x180105415  mov     [rax], rax
0x180105418  mov     rax, [rbx+168h]
0x18010541f  mov     [rax+8], rax
0x180105423  mov     qword ptr [rbx+170h], 0
0x18010542e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180105433  mov     rbx, [rsp+38h+arg_8]
0x180105438  xor     eax, eax
0x18010543a  add     rsp, 30h
0x18010543e  pop     rdi
0x18010543f  retn
```
