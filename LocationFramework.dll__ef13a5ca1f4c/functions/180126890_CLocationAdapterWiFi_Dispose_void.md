# CLocationAdapterWiFi::Dispose(void)

- ea: `0x180126890`
- end: `0x1801269cb`
- name: `?Dispose@CLocationAdapterWiFi@@UEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(CLocationAdapterWiFi *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f888`
- `0x180012194`
- `0x180012398`
- `0x1800123c0`
- `0x18002ae1c`
- `0x1800393c0`
- `0x180056aac`
- `0x180126814`
- `0x180126890`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801269aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801269aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801269b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801269b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012696b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012696b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180126978`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180126978`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180126985`

## pseudocode

```c
__int64 __fastcall CLocationAdapterWiFi::Dispose(CLocationAdapterWiFi *this)
{
  CLocationAdapterWiFi *v1; // rsi
  struct _TP_WORK *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rdx
  bool v6; // zf
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF

  v1 = (CLocationAdapterWiFi *)((char *)this - 8);
  CLocationAdapterWiFi::UnregisterForServiceNotifications((CLocationAdapterWiFi *)((char *)this - 8));
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v10,
    (char *)this + 120);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = 0;
  v4 = **((_QWORD **)this + 8);
  v9 = v4;
  while ( v4 != *((_QWORD *)this + 8) )
  {
    v5 = *(_QWORD *)(v4 + 32);
    v8 = 0;
    ATL::CComPtrBase<ILocationAdapterBluetoothSink>::CComPtrBase<ILocationAdapterBluetoothSink>(&v8, v5);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(&v9);
    (*(void (__fastcall **)(CLocationAdapterWiFi *, __int64))(*(_QWORD *)v1 + 40LL))(v1, v8);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
    v4 = v9;
  }
  std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>>,0>>::clear((char *)this + 224);
  CLocationAdapterWiFi::CleanUpWlanHandle(v1);
  v6 = *((_QWORD *)this + 24) == 0;
  *((_DWORD *)v1 + 52) = -2147467260;
  if ( !v6 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 41, 1, 0) )
      WaitForSingleObject(*((HANDLE *)this + 24), 0x1388u);
    SetEvent(*((HANDLE *)this + 24));
    CloseHandle(*((HANDLE *)this + 24));
    *((_QWORD *)this + 24) = 0;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v10);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180126890  mov     [rsp+arg_8], rbx
0x180126895  mov     [rsp+arg_10], rsi
0x18012689a  push    rdi
0x18012689b  sub     rsp, 40h
0x18012689f  lea     rsi, [rcx-8]
0x1801268a3  mov     rbx, rcx
0x1801268a6  mov     rcx, rsi; this
0x1801268a9  call    ?UnregisterForServiceNotifications@CLocationAdapterWiFi@@QEAAXXZ; CLocationAdapterWiFi::UnregisterForServiceNotifications(void)
0x1801268ae  lea     rdx, [rbx+78h]
0x1801268b2  lea     rcx, [rsp+48h+var_18]
0x1801268b7  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1801268bc  mov     rdi, [rbx+0A8h]
0x1801268c3  mov     qword ptr [rbx+0A8h], 0
0x1801268ce  mov     rdx, [rbx+40h]
0x1801268d2  mov     rdx, [rdx]
0x1801268d5  mov     [rsp+48h+var_20], rdx
0x1801268da  cmp     rdx, [rbx+40h]
0x1801268de  jz      short loc_180126926
0x1801268e0  mov     rdx, [rdx+20h]
0x1801268e4  lea     rcx, [rsp+48h+var_28]
0x1801268e9  mov     [rsp+48h+var_28], 0
0x1801268f2  call    ??0?$CComPtrBase@UILocationAdapterBluetoothSink@@@ATL@@IEAA@PEAUILocationAdapterBluetoothSink@@@Z; ATL::CComPtrBase<ILocationAdapterBluetoothSink>::CComPtrBase<ILocationAdapterBluetoothSink>(ILocationAdapterBluetoothSink *)
0x1801268f7  lea     rcx, [rsp+48h+var_20]
0x1801268fc  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>>,std::_Iterator_base0>::operator++(void)
0x180126901  mov     r9, [rsi]
0x180126904  mov     rcx, rsi
0x180126907  mov     rdx, [rsp+48h+var_28]
0x18012690c  mov     rax, [r9+28h]
0x180126910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126915  lea     rcx, [rsp+48h+var_28]
0x18012691a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18012691f  mov     rdx, [rsp+48h+var_20]
0x180126924  jmp     short loc_1801268DA
0x180126926  lea     rcx, [rbx+0E0h]
0x18012692d  call    ?clear@?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UILocationUpdateCellSink@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UILocationUpdateCellSink@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UILocationUpdateCellSink@@@ATL@@@ATL@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationUpdateCellSink>>>,0>>::clear(void)
0x180126932  mov     rcx, rsi; this
0x180126935  call    ?CleanUpWlanHandle@CLocationAdapterWiFi@@AEAAJXZ; CLocationAdapterWiFi::CleanUpWlanHandle(void)
0x18012693a  cmp     qword ptr [rbx+0C0h], 0
0x180126942  mov     dword ptr [rsi+0D0h], 80004004h
0x18012694c  mov     esi, 1
0x180126951  jz      short loc_180126996
0x180126953  xor     eax, eax
0x180126955  lock cmpxchg [rbx+0A4h], esi
0x18012695d  jz      short loc_180126971
0x18012695f  mov     rcx, [rbx+0C0h]; hHandle
0x180126966  mov     edx, 1388h; dwMilliseconds
0x18012696b  call    cs:__imp_WaitForSingleObject
0x180126971  mov     rcx, [rbx+0C0h]; hEvent
0x180126978  call    cs:__imp_SetEvent
0x18012697e  mov     rcx, [rbx+0C0h]; hObject
0x180126985  call    cs:__imp_CloseHandle
0x18012698b  mov     qword ptr [rbx+0C0h], 0
0x180126996  lea     rcx, [rsp+48h+var_18]
0x18012699b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1801269a0  test    rdi, rdi
0x1801269a3  jz      short loc_1801269B9
0x1801269a5  mov     edx, esi; fCancelPendingCallbacks
0x1801269a7  mov     rcx, rdi; pwk
0x1801269aa  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801269b0  mov     rcx, rdi; pwk
0x1801269b3  call    cs:__imp_CloseThreadpoolWork
0x1801269b9  mov     rbx, [rsp+48h+arg_8]
0x1801269be  xor     eax, eax
0x1801269c0  mov     rsi, [rsp+48h+arg_10]
0x1801269c5  add     rsp, 40h
0x1801269c9  pop     rdi
0x1801269ca  retn
```
