# CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::Dispose(void)

- ea: `0x1800b7fe0`
- end: `0x1800b815d`
- name: `?Dispose@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@UEAAJXZ`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800afbc4`

## callees

- `0x180012194`
- `0x180012398`
- `0x1800123c0`
- `0x180013660`
- `0x18002ae1c`
- `0x1800451d4`
- `0x1800b7fe0`
- `0x1800bc1cc`
- `0x1800bc1f0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b810f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b812b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b810f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b812b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8118`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8134`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8118`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8142`

## pseudocode

```c
__int64 __fastcall CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::Dispose(
        __int64 a1)
{
  struct _TP_WORK *v2; // rbp
  struct _TP_WORK *v3; // rsi
  __int64 v4; // r14
  void (__fastcall *v5)(__int64, __int64); // rbx
  void *v6; // rbx
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v8, a1 + 96);
  if ( *(_DWORD *)(a1 + 212) )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
  }
  else
  {
    v2 = *(struct _TP_WORK **)(a1 + 192);
    v3 = *(struct _TP_WORK **)(a1 + 160);
    *(_QWORD *)(a1 + 192) = 0;
    *(_QWORD *)(a1 + 160) = 0;
    *(_DWORD *)(a1 + 212) = 1;
    while ( *(_QWORD *)(a1 + 144) )
      CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::RemoveSession(
        a1,
        *(_QWORD *)(**(_QWORD **)(a1 + 136) + 16LL));
    if ( *(_DWORD *)(a1 + 168) )
    {
      v4 = *(_QWORD *)(a1 + 72);
      if ( v4 )
      {
        v5 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 40LL);
        ATL::CComPtrBase<ILocationAdapterBluetoothSink>::CComPtrBase<ILocationAdapterBluetoothSink>(
          &v9,
          (a1 + 8) & -(__int64)(a1 != 0));
        v5(v4, v9);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
        *(_DWORD *)(a1 + 168) = 0;
      }
    }
    if ( *(_QWORD *)(a1 + 72) )
      ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 72), 0);
    v6 = *(void **)(a1 + 176);
    *(_QWORD *)(a1 + 176) = 0;
    ATL::CComPtr<ILocationProvider>::operator=(a1 + 80, 0);
    CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::ReleasePositionListData(a1);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
    if ( v2 )
    {
      WaitForThreadpoolWorkCallbacks(v2, 1);
      CloseThreadpoolWork(v2);
    }
    if ( v3 )
    {
      WaitForThreadpoolWorkCallbacks(v3, 1);
      CloseThreadpoolWork(v3);
    }
    if ( v6 )
      CloseHandle(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b7fe0  mov     [rsp+arg_8], rbx
0x1800b7fe5  mov     [rsp+arg_10], rbp
0x1800b7fea  push    rsi
0x1800b7feb  push    rdi
0x1800b7fec  push    r14
0x1800b7fee  sub     rsp, 30h
0x1800b7ff2  mov     rdi, rcx
0x1800b7ff5  lea     rdx, [rcx+60h]
0x1800b7ff9  lea     rcx, [rsp+48h+var_28]
0x1800b7ffe  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800b8003  cmp     dword ptr [rdi+0D4h], 0
0x1800b800a  jz      short loc_1800B801B
0x1800b800c  lea     rcx, [rsp+48h+var_28]
0x1800b8011  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800b8016  jmp     loc_1800B8148
0x1800b801b  mov     rbp, [rdi+0C0h]
0x1800b8022  mov     rsi, [rdi+0A0h]
0x1800b8029  mov     qword ptr [rdi+0C0h], 0
0x1800b8034  mov     qword ptr [rdi+0A0h], 0
0x1800b803f  mov     dword ptr [rdi+0D4h], 1
0x1800b8049  cmp     qword ptr [rdi+90h], 0
0x1800b8051  jz      short loc_1800B806B
0x1800b8053  mov     rax, [rdi+88h]
0x1800b805a  mov     rcx, rdi
0x1800b805d  mov     rdx, [rax]
0x1800b8060  mov     rdx, [rdx+10h]
0x1800b8064  call    ?RemoveSession@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@AEAAJPEAUILocationSessionInternal@@@Z; CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::RemoveSession(ILocationSessionInternal *)
0x1800b8069  jmp     short loc_1800B8049
0x1800b806b  cmp     dword ptr [rdi+0A8h], 0
0x1800b8072  jz      short loc_1800B80C2
0x1800b8074  mov     r14, [rdi+48h]
0x1800b8078  test    r14, r14
0x1800b807b  jz      short loc_1800B80C2
0x1800b807d  mov     rax, [r14]
0x1800b8080  lea     r8, [rdi+8]
0x1800b8084  mov     rdx, rdi
0x1800b8087  lea     rcx, [rsp+48h+arg_0]
0x1800b808c  neg     rdx
0x1800b808f  mov     rbx, [rax+28h]
0x1800b8093  sbb     rdx, rdx
0x1800b8096  and     rdx, r8
0x1800b8099  call    ??0?$CComPtrBase@UILocationAdapterBluetoothSink@@@ATL@@IEAA@PEAUILocationAdapterBluetoothSink@@@Z; ATL::CComPtrBase<ILocationAdapterBluetoothSink>::CComPtrBase<ILocationAdapterBluetoothSink>(ILocationAdapterBluetoothSink *)
0x1800b809e  mov     rdx, [rsp+48h+arg_0]
0x1800b80a3  mov     rcx, r14
0x1800b80a6  mov     rax, rbx
0x1800b80a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b80ae  lea     rcx, [rsp+48h+arg_0]
0x1800b80b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b80b8  mov     dword ptr [rdi+0A8h], 0
0x1800b80c2  lea     rcx, [rdi+48h]; struct IUnknown **
0x1800b80c6  cmp     qword ptr [rcx], 0
0x1800b80ca  jz      short loc_1800B80D3
0x1800b80cc  xor     edx, edx; struct IUnknown *
0x1800b80ce  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800b80d3  mov     rbx, [rdi+0B0h]
0x1800b80da  lea     rcx, [rdi+50h]
0x1800b80de  xor     edx, edx
0x1800b80e0  mov     qword ptr [rdi+0B0h], 0
0x1800b80eb  call    ??4?$CComPtr@UILocationProvider@@@ATL@@QEAAPEAUILocationProvider@@PEAU2@@Z; ATL::CComPtr<ILocationProvider>::operator=(ILocationProvider *)
0x1800b80f0  mov     rcx, rdi
0x1800b80f3  call    ?ReleasePositionListData@?$CLocationAcquireSingleShotCellTemplate@VCLocationAcquireSingleShotCell@@$1?CLSID_LocationAcquireSingleShotCell@@3U_GUID@@B$0DB@$0DC@UILocationAdapterCell@@UILocationAdapterCellSink@@UILocationCellBeaconInformation@@@@AEAAXXZ; CLocationAcquireSingleShotCellTemplate<CLocationAcquireSingleShotCell,&_GUID const CLSID_LocationAcquireSingleShotCell,49,50,ILocationAdapterCell,ILocationAdapterCellSink,ILocationCellBeaconInformation>::ReleasePositionListData(void)
0x1800b80f8  lea     rcx, [rsp+48h+var_28]
0x1800b80fd  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800b8102  test    rbp, rbp
0x1800b8105  jz      short loc_1800B811E
0x1800b8107  mov     edx, 1; fCancelPendingCallbacks
0x1800b810c  mov     rcx, rbp; pwk
0x1800b810f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b8115  mov     rcx, rbp; pwk
0x1800b8118  call    cs:__imp_CloseThreadpoolWork
0x1800b811e  test    rsi, rsi
0x1800b8121  jz      short loc_1800B813A
0x1800b8123  mov     edx, 1; fCancelPendingCallbacks
0x1800b8128  mov     rcx, rsi; pwk
0x1800b812b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b8131  mov     rcx, rsi; pwk
0x1800b8134  call    cs:__imp_CloseThreadpoolWork
0x1800b813a  test    rbx, rbx
0x1800b813d  jz      short loc_1800B8148
0x1800b813f  mov     rcx, rbx; hObject
0x1800b8142  call    cs:__imp_CloseHandle
0x1800b8148  mov     rbx, [rsp+48h+arg_8]
0x1800b814d  xor     eax, eax
0x1800b814f  mov     rbp, [rsp+48h+arg_10]
0x1800b8154  add     rsp, 30h
0x1800b8158  pop     r14
0x1800b815a  pop     rdi
0x1800b815b  pop     rsi
0x1800b815c  retn
```
