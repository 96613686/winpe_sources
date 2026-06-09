# CLocationSession::Dispose(void)

- ea: `0x180068960`
- end: `0x180068aa2`
- name: `?Dispose@CLocationSession@@UEAAJXZ`
- size: `322`
- prototype: `__int64 __fastcall(CLocationSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180050990`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x1800164e4`
- `0x180016c7c`
- `0x180017028`
- `0x18002a618`
- `0x180068960`
- `0x1800696fc`
- `0x180083170`
- `0x180085674`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068a02`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180068a02`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068a0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180068a0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068a38`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180068a94`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180068a94`

## pseudocode

```c
__int64 __fastcall CLocationSession::Dispose(CLocationSession *this)
{
  CLocationSessionState *v2; // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  struct _TP_WORK *v4; // rcx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v6,
    (char *)this + 1080);
  if ( *((_BYTE *)this + 1072) )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v6);
  }
  else
  {
    *((_BYTE *)this + 1072) = 1;
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v6);
    LocationWnfSubscribe_Impl::Unsubscribe((CLocationSession *)((char *)this + 1008));
    (*(void (__fastcall **)(CLocationSession *))(*(_QWORD *)this + 32LL))(this);
    v2 = (CLocationSessionState *)*((_QWORD *)this + 45);
    if ( v2 )
    {
      CLocationSessionState::Uninitialize(v2);
      v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 45);
      if ( v3 )
        (**v3)(v3, 1);
      *((_QWORD *)this + 45) = 0;
    }
    v4 = (struct _TP_WORK *)*((_QWORD *)this + 46);
    if ( v4 )
    {
      WaitForThreadpoolWorkCallbacks(v4, 1);
      CloseThreadpoolWork(*((PTP_WORK *)this + 46));
      *((_QWORD *)this + 46) = 0;
    }
    if ( *((_QWORD *)this + 12) )
    {
      CLocationSession::SignalNotificationHandle(this, 1);
      CloseHandle(*((HANDLE *)this + 12));
      *((_QWORD *)this + 12) = 0;
    }
    std::list<ATL::CAdapt<ATL::CComPtr<ILocationInformation>>>::clear((char *)this + 184);
    std::_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>::clear((char *)this + 1120);
    if ( *((_QWORD *)this + 132) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 72LL))(*((_QWORD *)this + 133));
    CLocationSession::StopShowingInuseIcon(this);
    CLocationSession::StopCapabilityAccessUsageSession(this);
    CoFreeUnusedLibrariesEx(0x7530u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180068960  push    rbx
0x180068962  sub     rsp, 30h
0x180068966  mov     rbx, rcx
0x180068969  lea     rdx, [rcx+438h]
0x180068970  lea     rcx, [rsp+38h+var_18]
0x180068975  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18006897a  cmp     byte ptr [rbx+430h], 0
0x180068981  lea     rcx, [rsp+38h+var_18]
0x180068986  jz      short loc_180068992
0x180068988  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18006898d  jmp     loc_180068A9A
0x180068992  mov     byte ptr [rbx+430h], 1
0x180068999  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18006899e  lea     rcx, [rbx+3F0h]; this
0x1800689a5  call    ?Unsubscribe@LocationWnfSubscribe_Impl@@QEAAJXZ; LocationWnfSubscribe_Impl::Unsubscribe(void)
0x1800689aa  mov     rax, [rbx]
0x1800689ad  mov     rcx, rbx
0x1800689b0  mov     rax, [rax+20h]
0x1800689b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689b9  mov     rcx, [rbx+168h]; this
0x1800689c0  test    rcx, rcx
0x1800689c3  jz      short loc_1800689F1
0x1800689c5  call    ?Uninitialize@CLocationSessionState@@QEAAXXZ; CLocationSessionState::Uninitialize(void)
0x1800689ca  mov     rcx, [rbx+168h]
0x1800689d1  test    rcx, rcx
0x1800689d4  jz      short loc_1800689E6
0x1800689d6  mov     rax, [rcx]
0x1800689d9  mov     edx, 1
0x1800689de  mov     rax, [rax]
0x1800689e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689e6  mov     qword ptr [rbx+168h], 0
0x1800689f1  mov     rcx, [rbx+170h]; pwk
0x1800689f8  test    rcx, rcx
0x1800689fb  jz      short loc_180068A20
0x1800689fd  mov     edx, 1; fCancelPendingCallbacks
0x180068a02  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180068a08  mov     rcx, [rbx+170h]; pwk
0x180068a0f  call    cs:__imp_CloseThreadpoolWork
0x180068a15  mov     qword ptr [rbx+170h], 0
0x180068a20  cmp     qword ptr [rbx+60h], 0
0x180068a25  jz      short loc_180068A46
0x180068a27  mov     edx, 1; int
0x180068a2c  mov     rcx, rbx; this
0x180068a2f  call    ?SignalNotificationHandle@CLocationSession@@IEAAJH@Z; CLocationSession::SignalNotificationHandle(int)
0x180068a34  mov     rcx, [rbx+60h]; hObject
0x180068a38  call    cs:__imp_CloseHandle
0x180068a3e  mov     qword ptr [rbx+60h], 0
0x180068a46  lea     rcx, [rbx+0B8h]
0x180068a4d  call    ?clear@?$list@V?$CAdapt@V?$CComPtr@UILocationInformation@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UILocationInformation@@@ATL@@@ATL@@@std@@@std@@QEAAXXZ; std::list<ATL::CAdapt<ATL::CComPtr<ILocationInformation>>>::clear(void)
0x180068a52  lea     rcx, [rbx+460h]
0x180068a59  call    ?clear@?$_Tree@V?$_Tmap_traits@W4LOCATION_POSITIONINGENGINE@@U?$pair@UPOSITIONINFO_COORDINATE@@UPOSITIONINFO_STATUS@@@std@@U?$less@W4LOCATION_POSITIONINGENGINE@@@3@V?$allocator@U?$pair@$$CBW4LOCATION_POSITIONINGENGINE@@U?$pair@UPOSITIONINFO_COORDINATE@@UPOSITIONINFO_STATUS@@@std@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>::clear(void)
0x180068a5e  mov     rdx, [rbx+420h]
0x180068a65  test    rdx, rdx
0x180068a68  jz      short loc_180068A7D
0x180068a6a  mov     rcx, [rbx+428h]
0x180068a71  mov     rax, [rcx]
0x180068a74  mov     rax, [rax+48h]
0x180068a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a7d  mov     rcx, rbx; this
0x180068a80  call    ?StopShowingInuseIcon@CLocationSession@@IEAAXXZ; CLocationSession::StopShowingInuseIcon(void)
0x180068a85  mov     rcx, rbx; this
0x180068a88  call    ?StopCapabilityAccessUsageSession@CLocationSession@@IEAAXXZ; CLocationSession::StopCapabilityAccessUsageSession(void)
0x180068a8d  xor     edx, edx; dwReserved
0x180068a8f  mov     ecx, 7530h; dwUnloadDelay
0x180068a94  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180068a9a  xor     eax, eax
0x180068a9c  add     rsp, 30h
0x180068aa0  pop     rbx
0x180068aa1  retn
```
