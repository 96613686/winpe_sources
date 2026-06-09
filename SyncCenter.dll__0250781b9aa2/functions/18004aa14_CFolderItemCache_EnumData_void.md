# CFolderItemCache::_EnumData(void)

- ea: `0x18004aa14`
- end: `0x18004ab7f`
- name: `?_EnumData@CFolderItemCache@@AEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CFolderItemCache *this, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004b51c`

## callees

- `0x180008abc`
- `0x18000ab48`
- `0x18000ab8c`
- `0x1800134e8`
- `0x180013ab0`
- `0x180015f6c`
- `0x18004aa14`
- `0x18004ab88`
- `0x18004aca0`
- `0x18004aeec`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ab57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004ab57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ab1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ab1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004aae5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004aa79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004aa79`

## pseudocode

```c
__int64 __fastcall CFolderItemCache::_EnumData(CFolderItemCache *this, __int64 a2, int a3)
{
  int v3; // ecx
  HRESULT Instance; // ebx
  int v5; // r8d
  __int64 v6; // rcx
  int v7; // eax
  struct _DPA *v8; // rdi
  int v9; // r14d
  int i; // esi
  struct CCachedHandler *Ptr; // rax
  CFolderItemCache *v12; // rcx
  __int64 v13; // rcx
  struct IPrivSyncMgrHandlerDataStore *ppv; // [rsp+30h] [rbp-20h] BYREF
  HDPA hdpa[2]; // [rsp+38h] [rbp-18h] BYREF

  if ( (Microsoft_Windows_mobsyncEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)SyncMgrTraceId_HandlerCacheEnum_Start,
      a3,
      1,
      (__int64)hdpa);
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_SyncMgrp, 0, 5u, &GUID_1df997e7_21c2_4258_a795_49c5d8869bd2, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    hdpa[0] = 0;
    CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(hdpa);
    v7 = CFolderItemCache::_EnumHandlers(v6, ppv, hdpa);
    v8 = hdpa[0];
    Instance = v7;
    if ( v7 >= 0 )
    {
      if ( hdpa[0] )
      {
        v9 = *(_DWORD *)hdpa[0];
        for ( i = 0; i < v9; ++i )
        {
          Ptr = (struct CCachedHandler *)DPA_GetPtr(v8, i);
          CFolderItemCache::_EnumItems(v12, ppv, Ptr);
        }
      }
    }
    EnterCriticalSection(&stru_180070D50);
    CFolderItemCache::_MoveUpdateRegistrations(v13, &::hdpa, hdpa);
    CDPA<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>::DestroyCallback(&::hdpa);
    hdpa[0] = 0;
    ::hdpa = v8;
    LeaveCriticalSection(&stru_180070D50);
    CDPA_Base<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>::~CDPA_Base<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>(hdpa);
  }
  if ( (Microsoft_Windows_mobsyncEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v3, (unsigned int)SyncMgrTraceId_HandlerCacheEnum_Stop, v5, 1, (__int64)hdpa);
  SetEvent(hEvent);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004aa14  push    rbp
0x18004aa16  push    rbx
0x18004aa17  push    rsi
0x18004aa18  push    rdi
0x18004aa19  push    r14
0x18004aa1b  mov     rbp, rsp
0x18004aa1e  sub     rsp, 50h
0x18004aa22  mov     rax, cs:__security_cookie
0x18004aa29  xor     rax, rsp
0x18004aa2c  mov     [rbp+var_8], rax
0x18004aa30  test    cs:Microsoft_Windows_mobsyncEnableBits, 1
0x18004aa37  jz      short loc_18004AA54
0x18004aa39  lea     rax, [rbp+hdpa]
0x18004aa3d  mov     r9d, 1
0x18004aa43  lea     rdx, SyncMgrTraceId_HandlerCacheEnum_Start
0x18004aa4a  mov     [rsp+50h+ppv], rax
0x18004aa4f  call    McGenEventWrite_EtwEventWriteTransfer
0x18004aa54  xor     edx, edx; pUnkOuter
0x18004aa56  mov     [rbp+var_20], 0
0x18004aa5e  lea     rax, [rbp+var_20]
0x18004aa62  lea     r9, _GUID_1df997e7_21c2_4258_a795_49c5d8869bd2; riid
0x18004aa69  mov     [rsp+50h+ppv], rax; ppv
0x18004aa6e  lea     rcx, CLSID_SyncMgrp; rclsid
0x18004aa75  lea     r8d, [rdx+5]; dwClsContext
0x18004aa79  call    cs:__imp_CoCreateInstance
0x18004aa7f  mov     ebx, eax
0x18004aa81  test    eax, eax
0x18004aa83  js      loc_18004AB2C
0x18004aa89  lea     rcx, [rbp+hdpa]
0x18004aa8d  mov     [rbp+hdpa], 0
0x18004aa95  call    ?Create@?$CDPA_Base@UISyncClientFolderItem@@V?$CTContainer_PolicyUnOwned@UISyncClientFolderItem@@@@@@QEAAHH@Z; CDPA_Base<ISyncClientFolderItem,CTContainer_PolicyUnOwned<ISyncClientFolderItem>>::Create(int)
0x18004aa9a  mov     rdx, [rbp+var_20]
0x18004aa9e  lea     r8, [rbp+hdpa]
0x18004aaa2  call    ?_EnumHandlers@CFolderItemCache@@AEAAJPEAUIPrivSyncMgrHandlerDataStore@@PEAV?$CDPA@VCCachedHandler@@V?$CTContainer_PolicyUnOwned@VCCachedHandler@@@@@@@Z; CFolderItemCache::_EnumHandlers(IPrivSyncMgrHandlerDataStore *,CDPA<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>> *)
0x18004aaa7  mov     rdi, [rbp+hdpa]
0x18004aaab  mov     ebx, eax
0x18004aaad  test    eax, eax
0x18004aaaf  js      short loc_18004AADE
0x18004aab1  test    rdi, rdi
0x18004aab4  jz      short loc_18004AADE
0x18004aab6  mov     r14d, [rdi]
0x18004aab9  xor     esi, esi
0x18004aabb  test    r14d, r14d
0x18004aabe  jle     short loc_18004AADE
0x18004aac0  movsxd  rdx, esi; i
0x18004aac3  mov     rcx, rdi; hdpa
0x18004aac6  call    DPA_GetPtr
0x18004aacb  mov     rdx, [rbp+var_20]; struct IPrivSyncMgrHandlerDataStore *
0x18004aacf  mov     r8, rax; struct CCachedHandler *
0x18004aad2  call    ?_EnumItems@CFolderItemCache@@AEAAJPEAUIPrivSyncMgrHandlerDataStore@@PEAVCCachedHandler@@@Z; CFolderItemCache::_EnumItems(IPrivSyncMgrHandlerDataStore *,CCachedHandler *)
0x18004aad7  inc     esi
0x18004aad9  cmp     esi, r14d
0x18004aadc  jl      short loc_18004AAC0
0x18004aade  lea     rcx, stru_180070D50; lpCriticalSection
0x18004aae5  call    cs:__imp_EnterCriticalSection
0x18004aaeb  lea     r8, [rbp+hdpa]
0x18004aaef  lea     rdx, hdpa
0x18004aaf6  call    ?_MoveUpdateRegistrations@CFolderItemCache@@AEBAXPEAV?$CDPA@VCCachedHandler@@V?$CTContainer_PolicyUnOwned@VCCachedHandler@@@@@@0@Z; CFolderItemCache::_MoveUpdateRegistrations(CDPA<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>> *,CDPA<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>> *)
0x18004aafb  lea     rcx, hdpa
0x18004ab02  call    ?DestroyCallback@?$CDPA@VCCachedHandler@@V?$CTContainer_PolicyUnOwned@VCCachedHandler@@@@@@QEAAXP6AHPEAVCCachedHandler@@PEAX@Z1@Z; CDPA<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>::DestroyCallback(int (*)(CCachedHandler *,void *),void *)
0x18004ab07  lea     rcx, stru_180070D50; lpCriticalSection
0x18004ab0e  mov     [rbp+hdpa], 0
0x18004ab16  mov     qword ptr cs:hdpa, rdi
0x18004ab1d  call    cs:__imp_LeaveCriticalSection
0x18004ab23  lea     rcx, [rbp+hdpa]
0x18004ab27  call    ??1?$CDPA_Base@VCCachedHandler@@V?$CTContainer_PolicyUnOwned@VCCachedHandler@@@@@@QEAA@XZ; CDPA_Base<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>::~CDPA_Base<CCachedHandler,CTContainer_PolicyUnOwned<CCachedHandler>>(void)
0x18004ab2c  test    cs:Microsoft_Windows_mobsyncEnableBits, 1
0x18004ab33  jz      short loc_18004AB50
0x18004ab35  lea     rax, [rbp+hdpa]
0x18004ab39  mov     r9d, 1
0x18004ab3f  lea     rdx, SyncMgrTraceId_HandlerCacheEnum_Stop
0x18004ab46  mov     [rsp+50h+ppv], rax
0x18004ab4b  call    McGenEventWrite_EtwEventWriteTransfer
0x18004ab50  mov     rcx, cs:hEvent; hEvent
0x18004ab57  call    cs:__imp_SetEvent
0x18004ab5d  lea     rcx, [rbp+var_20]
0x18004ab61  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ab66  mov     eax, ebx
0x18004ab68  mov     rcx, [rbp+var_8]
0x18004ab6c  xor     rcx, rsp; StackCookie
0x18004ab6f  call    __security_check_cookie
0x18004ab74  add     rsp, 50h
0x18004ab78  pop     r14
0x18004ab7a  pop     rdi
0x18004ab7b  pop     rsi
0x18004ab7c  pop     rbx
0x18004ab7d  pop     rbp
0x18004ab7e  retn
```
