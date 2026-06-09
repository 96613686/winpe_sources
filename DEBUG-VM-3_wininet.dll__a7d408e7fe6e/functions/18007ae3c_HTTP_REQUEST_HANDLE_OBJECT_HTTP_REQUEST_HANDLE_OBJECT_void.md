# HTTP_REQUEST_HANDLE_OBJECT::~HTTP_REQUEST_HANDLE_OBJECT(void)

- ea: `0x18007ae3c`
- end: `0x18007b974`
- name: `??1HTTP_REQUEST_HANDLE_OBJECT@@EEAA@XZ`
- size: `2872`
- prototype: `void __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801140e0`

## callees

- `0x180020fc4`
- `0x180028284`
- `0x180033f84`
- `0x18007580c`
- `0x18007ad20`
- `0x18007ae3c`
- `0x18007ba18`
- `0x18007bbb8`
- `0x18007c03c`
- `0x18007c0b4`
- `0x18007c4d4`
- `0x18007c580`
- `0x18007c628`
- `0x18007c6f4`
- `0x180086ae8`
- `0x1800874cc`
- `0x1800cfe18`
- `0x1800db8f8`
- `0x1800e70b4`
- `0x1800f7360`
- `0x18010da5c`
- `0x180126d40`
- `0x1801327f4`
- `0x18013d774`
- `0x18013ed20`
- `0x180141ad8`
- `0x18014a3a4`
- `0x18014ca90`
- `0x18015edf0`
- `0x180194d0c`
- `0x1801d4be8`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e5e10`
- `0x1801e76e4`
- `0x1801e8ecc`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b334`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b38b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b3b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b334`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b38b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007b3b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b47c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b6c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b7c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b7f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b859`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b021`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b47c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b6c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b7c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b7f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b822`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b859`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b6b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b6b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b86b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b69d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b86b`

## pseudocode

```c
void __fastcall HTTP_REQUEST_HANDLE_OBJECT::~HTTP_REQUEST_HANDLE_OBJECT(HTTP_REQUEST_HANDLE_OBJECT *this)
{
  __int64 v2; // rbp
  __int64 v3; // r14
  __int64 v4; // r15
  _QWORD *ThreadInfo; // rdi
  __int64 v6; // rsi
  __int64 v7; // rsi
  unsigned int v8; // eax
  int v9; // ecx
  int v10; // eax
  CPushSyncBlock *v11; // rcx
  void *v12; // rcx
  void *v13; // r8
  unsigned __int64 v14; // rdx
  CAppCacheHandle *v15; // rcx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  PWC *v19; // rcx
  CDependentHost *v20; // rcx
  CDependentHostList *v21; // rcx
  CPreConnectData *v22; // rcx
  void *v23; // r8
  void *v24; // r8
  void *v25; // r8
  __int64 v26; // rcx
  void *v27; // r8
  void *v28; // r8
  __int64 v29; // rdi
  unsigned __int32 v30; // esi
  void *v31; // r8
  void *v32; // rcx
  WebSocketLibrary *v33; // rcx
  __int64 v34; // rcx
  void *v35; // rcx
  __int64 v36; // rcx
  CBlockFsmSync *v37; // rcx
  CBlockFsmSync *v38; // rcx
  __int64 v39; // rdx
  WCHAR *v40; // r8
  CBlockFsmSync *v41; // rdi
  CBlockFsmSync *v42; // rdi
  WCHAR *v43; // r8
  __int64 v44; // rcx
  void *v45; // rcx
  __int64 v46; // rcx
  void *v47; // r8
  unsigned int v48; // edx
  WxFastHeapAllocator *v49; // rcx
  unsigned int v50; // edx
  WxFastHeapAllocator *v51; // rcx
  CBlockFsmSync *v52; // rdi
  CBlockFsmSync *v53; // rcx
  int v54; // eax
  bool v55; // zf
  const WCHAR *v56; // rcx

  *(_QWORD *)this = &HTTP_REQUEST_HANDLE_OBJECT::`vftable';
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_q(1032, 13, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, this);
  v2 = 0;
  v3 = 0;
  v4 = 0;
  ThreadInfo = (_QWORD *)InternetGetThreadInfo();
  HTTP_REQUEST_HANDLE_OBJECT::RequestLog(this);
  if ( ThreadInfo )
  {
    v2 = ThreadInfo[6];
    v3 = ThreadInfo[7];
    v4 = ThreadInfo[5];
    v6 = *((_QWORD *)this + 16);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqqqq(
        1025,
        43,
        (unsigned int)&WPP_269ea9d0988239ed4fc21e863914335a_Traceguids,
        (_DWORD)ThreadInfo,
        v2,
        v6,
        v3,
        (__int64)this);
    ThreadInfo[6] = v6;
    ThreadInfo[7] = this;
    v7 = *((_QWORD *)this + 23);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qPP(1025, 42, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, ThreadInfo);
    ThreadInfo[5] = v7;
  }
  v8 = *((_DWORD *)this + 1319);
  v9 = v8 & 3;
  if ( (v8 & 3) == 0 )
  {
    v10 = (v8 >> 2) & 3;
    goto LABEL_11;
  }
  v54 = v8 & 0xC;
  if ( !v54 )
  {
    v10 = *((_DWORD *)this + 1319) & 3;
    goto LABEL_11;
  }
  if ( v9 == 1 )
  {
    if ( v54 == 4 )
    {
      v10 = 1;
      goto LABEL_11;
    }
LABEL_140:
    v55 = v54 == 12;
    v10 = 2;
    if ( !v55 )
      goto LABEL_11;
    goto LABEL_141;
  }
  if ( v9 != 3 )
    goto LABEL_140;
LABEL_141:
  v10 = 3;
LABEL_11:
  HTTP_REQUEST_HANDLE_OBJECT::CloseConnection(this, v10 != 0);
  v11 = (CPushSyncBlock *)*((_QWORD *)this + 713);
  if ( v11 )
  {
    CPushSyncBlock::Closed(v11);
    CPushSyncBlock::Release(*((CPushSyncBlock **)this + 713));
    *((_QWORD *)this + 713) = 0;
  }
  if ( ThreadInfo )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqqqq(
        1025,
        43,
        (unsigned int)&WPP_269ea9d0988239ed4fc21e863914335a_Traceguids,
        (_DWORD)ThreadInfo,
        ThreadInfo[6],
        v2,
        ThreadInfo[7],
        v3);
    ThreadInfo[6] = v2;
    ThreadInfo[7] = v3;
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qPP(1025, 42, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, ThreadInfo);
    ThreadInfo[5] = v4;
  }
  v12 = (void *)*((_QWORD *)this + 631);
  if ( v12 != (void *)-1LL )
  {
    CloseHandle(v12);
    v56 = (const WCHAR *)*((_QWORD *)this + 632);
    *((_QWORD *)this + 631) = -1;
    DeleteFileW(v56);
  }
  v13 = (void *)*((_QWORD *)this + 632);
  if ( v13 )
  {
    HeapFree(g_hWxProcessHeap, 0, v13);
    *((_QWORD *)this + 632) = 0;
  }
  if ( *((_DWORD *)this + 179) )
    HTTP_REQUEST_HANDLE_OBJECT::LocalEndCacheWrite(this, *((_DWORD *)this + 134));
  if ( *((_DWORD *)this + 178) )
    HTTP_REQUEST_HANDLE_OBJECT::FreeCacheInfo(this);
  else
    HTTP_REQUEST_HANDLE_OBJECT::UrlCacheUnlock(this, 1);
  v15 = (CAppCacheHandle *)*((_QWORD *)this + 628);
  if ( v15 )
  {
    CAppCacheHandle::Release(v15);
    *((_QWORD *)this + 628) = 0;
  }
  if ( (*((_DWORD *)this + 1319) & 0x8000) != 0 )
    *((_DWORD *)this + 164) = 0;
  v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 653);
  if ( v16 )
  {
    (**v16)(v16, 1);
    *((_QWORD *)this + 653) = 0;
  }
  v17 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 654);
  if ( v17 )
  {
    (**v17)(v17, 1);
    *((_QWORD *)this + 654) = 0;
  }
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 655);
  if ( v18 )
    (**v18)(v18, 1);
  v19 = (PWC *)*((_QWORD *)this + 656);
  if ( v19 )
  {
    PWC::Dereference(v19);
    *((_QWORD *)this + 656) = 0;
  }
  v20 = (CDependentHost *)*((_QWORD *)this + 710);
  if ( v20 )
  {
    CDependentHost::Release(v20);
    *((_QWORD *)this + 710) = 0;
  }
  v21 = (CDependentHostList *)*((_QWORD *)this + 709);
  if ( v21 )
  {
    CDependentHostList::Release(v21);
    *((_QWORD *)this + 709) = 0;
  }
  v22 = (CPreConnectData *)*((_QWORD *)this + 711);
  if ( v22 )
  {
    if ( *((_DWORD *)this + 1424) )
      CPreConnectData::Cancel(v22);
    CPreConnectData::Release(*((CPreConnectData **)this + 711));
    *((_QWORD *)this + 711) = 0;
  }
  v23 = (void *)*((_QWORD *)this + 613);
  if ( v23 )
  {
    HeapFree(g_hWxProcessHeap, 0, v23);
    *((_QWORD *)this + 613) = 0;
  }
  *((_QWORD *)this + 614) = 0;
  *((_DWORD *)this + 1232) = 0;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_dsddsd(
      (_DWORD)v22,
      v14,
      (_DWORD)v23,
      *((_DWORD *)this + 1323),
      *((_QWORD *)this + 660),
      *((_WORD *)this + 2644),
      -1,
      0,
      0);
  v24 = (void *)*((_QWORD *)this + 660);
  if ( v24 )
    HeapFree(g_hWxProcessHeap, 0, v24);
  *((_QWORD *)this + 660) = 0;
  *((_WORD *)this + 2644) = 0;
  *((_DWORD *)this + 1323) = -1;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 27, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, 0);
  v25 = (void *)*((_QWORD *)this + 662);
  if ( v25 )
    HeapFree(g_hWxProcessHeap, 0, v25);
  *((_QWORD *)this + 662) = 0;
  *((_WORD *)this + 2652) = 0;
  v26 = *((_QWORD *)this + 664);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    *((_QWORD *)this + 664) = 0;
  }
  v27 = (void *)*((_QWORD *)this + 156);
  if ( v27 )
  {
    HeapFree(g_hWxProcessHeap, 0, v27);
    *((_QWORD *)this + 156) = 0;
  }
  v28 = (void *)*((_QWORD *)this + 673);
  if ( v28 )
  {
    HeapFree(g_hWxProcessHeap, 0, v28);
    *((_QWORD *)this + 673) = 0;
  }
  v29 = *((_QWORD *)this + 666);
  if ( v29 )
  {
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_qsd(1032, 16, (_DWORD)v28, v29, *(_QWORD *)(v29 + 832), *(_DWORD *)(v29 + 16));
    v30 = _InterlockedDecrement((volatile signed __int32 *)(v29 + 16));
    if ( !v30 )
    {
      SECURITY_CACHE_LIST_ENTRY::~SECURITY_CACHE_LIST_ENTRY((SECURITY_CACHE_LIST_ENTRY *)v29);
      operator delete((void *)v29, 0x398u);
    }
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_d(1032, 17, &WPP_c739a4d1cc5f3596af17db4ca44bd9b2_Traceguids, v30);
    *((_QWORD *)this + 666) = 0;
  }
  v31 = (void *)*((_QWORD *)this + 705);
  if ( v31 )
  {
    HeapFree(g_hWxProcessHeap, 0, v31);
    *((_QWORD *)this + 705) = 0;
  }
  v32 = (void *)*((_QWORD *)this + 706);
  if ( v32 != (void *)-1LL )
  {
    CloseHandle(v32);
    *((_QWORD *)this + 706) = -1;
  }
  v33 = (WebSocketLibrary *)*((_QWORD *)this + 129);
  if ( v33 )
  {
    WebSocketLibrary::`scalar deleting destructor'(v33, v14);
    *((_QWORD *)this + 129) = 0;
  }
  v34 = *((_QWORD *)this + 151);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v34 + 72LL))(v34, 0, 1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 151) + 8LL))(*((_QWORD *)this + 151));
    *((_QWORD *)this + 151) = 0;
  }
  v35 = (void *)*((_QWORD *)this + 127);
  if ( v35 )
  {
    operator delete(v35, v14);
    *((_QWORD *)this + 127) = 0;
  }
  v36 = *((_QWORD *)this + 135);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v36 + 72LL))(v36, 0, 1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 135) + 8LL))(*((_QWORD *)this + 135));
    *((_QWORD *)this + 135) = 0;
  }
  WxHeapFree<_WX_AVL_TABLE>((char *)this + 1064);
  v37 = (CBlockFsmSync *)*((_QWORD *)this + 714);
  *((_DWORD *)this + 268) = 0;
  if ( v37 )
  {
    CBlockFsmSync::Cancel(v37);
    v52 = (CBlockFsmSync *)*((_QWORD *)this + 714);
    if ( v52 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v52, 0xFFFFFFFF) == 1 )
      {
        CBlockFsmSync::~CBlockFsmSync(v52);
        operator delete(v52, 0x58u);
      }
      *((_QWORD *)this + 714) = 0;
    }
  }
  v38 = (CBlockFsmSync *)*((_QWORD *)this + 715);
  if ( v38 )
  {
    CBlockFsmSync::Cancel(v38);
    v53 = (CBlockFsmSync *)*((_QWORD *)this + 715);
    if ( v53 )
    {
      CBlockFsmSync::Release(v53);
      *((_QWORD *)this + 715) = 0;
    }
  }
  HTTP_REQUEST_HANDLE_OBJECT::TerminateHttpExtension(this);
  HTTP_REQUEST_HANDLE_OBJECT::TerminateRequestTrace(this);
  HTTP_REQUEST_HANDLE_OBJECT::TerminateResponseTrace(this);
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 14, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids);
  v40 = (WCHAR *)*((_QWORD *)this + 728);
  if ( v40 != &Data && v40 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(*((_QWORD *)this + 728));
    else
      HeapFree(g_hWxProcessHeap, 0, v40);
  }
  *((_QWORD *)this + 728) = &Data;
  *((_QWORD *)this + 729) = 0;
  v41 = (CBlockFsmSync *)*((_QWORD *)this + 715);
  if ( v41 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)v41) )
    {
      CBlockFsmSync::~CBlockFsmSync(v41);
      operator delete(v41, 0x58u);
    }
    *((_QWORD *)this + 715) = 0;
  }
  v42 = (CBlockFsmSync *)*((_QWORD *)this + 714);
  if ( v42 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)v42) )
    {
      CBlockFsmSync::~CBlockFsmSync(v42);
      operator delete(v42, 0x58u);
    }
    *((_QWORD *)this + 714) = 0;
  }
  v43 = (WCHAR *)*((_QWORD *)this + 677);
  if ( v43 != &Data && v43 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(*((_QWORD *)this + 677));
    else
      HeapFree(g_hWxProcessHeap, 0, v43);
  }
  *((_QWORD *)this + 677) = &Data;
  *((_QWORD *)this + 678) = 0;
  v44 = *((_QWORD *)this + 664);
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    *((_QWORD *)this + 664) = 0;
  }
  v45 = (void *)*((_QWORD *)this + 647);
  if ( v45 )
  {
    DestroyDecompression(v45);
    *((_QWORD *)this + 647) = 0;
  }
  v46 = *((_QWORD *)this + 648);
  if ( v46 )
  {
    BrotliDecoderDestroyInstance(v46, v39);
    *((_QWORD *)this + 648) = 0;
  }
  v47 = (void *)*((_QWORD *)this + 649);
  if ( v47 )
    HeapFree(g_hWxProcessHeap, 0, v47);
  *((_QWORD *)this + 649) = 0;
  *((_QWORD *)this + 650) = 0;
  *((_QWORD *)this + 651) = 0;
  *((_QWORD *)this + 652) = 0;
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_q(1032, 17, &WPP_764547bcea91352f6757a10208e155bd_Traceguids, (char *)this + 3104);
  CHttpHeaders::_RemoveAllHeaders((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 3104));
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 18, &WPP_764547bcea91352f6757a10208e155bd_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4848));
  v49 = (WxFastHeapAllocator *)*((_QWORD *)this + 586);
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49, 0xFFFFFFFF) == 1 )
      WxFastHeapAllocator::`scalar deleting destructor'(v49, v48);
    *((_QWORD *)this + 586) = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_q(1032, 17, &WPP_764547bcea91352f6757a10208e155bd_Traceguids, (char *)this + 1280);
  CHttpHeaders::_RemoveAllHeaders((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280));
  if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
    WPP_SF_(1032, 18, &WPP_764547bcea91352f6757a10208e155bd_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3024));
  v51 = (WxFastHeapAllocator *)*((_QWORD *)this + 358);
  if ( v51 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v51, 0xFFFFFFFF) == 1 )
      WxFastHeapAllocator::`scalar deleting destructor'(v51, v50);
    *((_QWORD *)this + 358) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(this);
}

```

## disassembly

```asm
0x18007ae3c  push    rbx
0x18007ae3e  push    rbp
0x18007ae3f  push    rsi
0x18007ae40  push    rdi
0x18007ae41  push    r12
0x18007ae43  push    r13
0x18007ae45  push    r14
0x18007ae47  push    r15
0x18007ae49  sub     rsp, 68h
0x18007ae4d  lea     rax, ??_7HTTP_REQUEST_HANDLE_OBJECT@@6B@; const HTTP_REQUEST_HANDLE_OBJECT::`vftable'
0x18007ae54  mov     rbx, rcx
0x18007ae57  mov     [rcx], rax
0x18007ae5a  mov     r13d, 1
0x18007ae60  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007ae67  jnz     loc_18007B541
0x18007ae6d  call    InternetGetThreadInfo
0x18007ae72  xor     r12d, r12d
0x18007ae75  mov     rcx, rbx; this
0x18007ae78  mov     ebp, r12d
0x18007ae7b  mov     r14d, r12d
0x18007ae7e  mov     r15d, r12d
0x18007ae81  mov     rdi, rax
0x18007ae84  call    ?RequestLog@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXXZ; HTTP_REQUEST_HANDLE_OBJECT::RequestLog(void)
0x18007ae89  test    rdi, rdi
0x18007ae8c  jz      short loc_18007AECE
0x18007ae8e  mov     rbp, [rdi+30h]
0x18007ae92  mov     r14, [rdi+38h]
0x18007ae96  mov     r15, [rdi+28h]
0x18007ae9a  mov     rsi, [rbx+80h]
0x18007aea1  test    byte ptr cs:xmmword_180266B60, 2
0x18007aea8  jnz     loc_18007B585
0x18007aeae  mov     [rdi+30h], rsi
0x18007aeb2  mov     [rdi+38h], rbx
0x18007aeb6  mov     rsi, [rbx+0B8h]
0x18007aebd  test    byte ptr cs:xmmword_180266B60, 2
0x18007aec4  jnz     loc_18007B5B7
0x18007aeca  mov     [rdi+28h], rsi
0x18007aece  mov     eax, [rbx+149Ch]
0x18007aed4  mov     edx, 3
0x18007aed9  mov     ecx, eax
0x18007aedb  and     ecx, edx
0x18007aedd  jnz     loc_18007B5E3
0x18007aee3  shr     eax, 2
0x18007aee6  and     eax, edx
0x18007aee8  test    eax, eax
0x18007aeea  mov     edx, r12d
0x18007aeed  mov     rcx, rbx; this
0x18007aef0  setnz   dl; int
0x18007aef3  call    ?CloseConnection@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKH@Z; HTTP_REQUEST_HANDLE_OBJECT::CloseConnection(int)
0x18007aef8  mov     rcx, [rbx+1648h]; this
0x18007aeff  test    rcx, rcx
0x18007af02  jnz     loc_18007B61A
0x18007af08  test    rdi, rdi
0x18007af0b  jz      short loc_18007AF33
0x18007af0d  test    byte ptr cs:xmmword_180266B60, 2
0x18007af14  jnz     loc_18007B637
0x18007af1a  mov     [rdi+30h], rbp
0x18007af1e  mov     [rdi+38h], r14
0x18007af22  test    byte ptr cs:xmmword_180266B60, 2
0x18007af29  jnz     loc_18007B671
0x18007af2f  mov     [rdi+28h], r15
0x18007af33  mov     rcx, [rbx+13B8h]; hObject
0x18007af3a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18007af3e  cmp     rcx, rbp
0x18007af41  jnz     loc_18007B69D
0x18007af47  mov     r8, [rbx+13C0h]; lpMem
0x18007af4e  test    r8, r8
0x18007af51  jnz     loc_18007B6BC
0x18007af57  cmp     [rbx+2CCh], r12d
0x18007af5e  jnz     loc_18007B6D7
0x18007af64  mov     rcx, rbx; this
0x18007af67  cmp     [rbx+2C8h], r12d
0x18007af6e  jnz     loc_18007B487
0x18007af74  mov     edx, r13d; int
0x18007af77  call    ?UrlCacheUnlock@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXH@Z; HTTP_REQUEST_HANDLE_OBJECT::UrlCacheUnlock(int)
0x18007af7c  mov     rcx, [rbx+13A0h]; this
0x18007af83  test    rcx, rcx
0x18007af86  jnz     loc_18007B6EA
0x18007af8c  test    dword ptr [rbx+149Ch], 8000h
0x18007af96  jnz     loc_18007B6FB
0x18007af9c  mov     rcx, [rbx+1468h]
0x18007afa3  test    rcx, rcx
0x18007afa6  jnz     loc_18007B707
0x18007afac  mov     rcx, [rbx+1470h]
0x18007afb3  test    rcx, rcx
0x18007afb6  jnz     loc_18007B721
0x18007afbc  mov     rcx, [rbx+1478h]
0x18007afc3  test    rcx, rcx
0x18007afc6  jnz     loc_18007B73B
0x18007afcc  mov     rcx, [rbx+1480h]; this
0x18007afd3  test    rcx, rcx
0x18007afd6  jnz     loc_18007B74E
0x18007afdc  mov     rcx, [rbx+1630h]; this
0x18007afe3  test    rcx, rcx
0x18007afe6  jnz     loc_18007B4F5
0x18007afec  mov     rcx, [rbx+1628h]; this
0x18007aff3  test    rcx, rcx
0x18007aff6  jnz     loc_18007B4E4
0x18007affc  mov     rcx, [rbx+1638h]; this
0x18007b003  test    rcx, rcx
0x18007b006  jnz     loc_18007B75F
0x18007b00c  mov     r8, [rbx+1328h]; lpMem
0x18007b013  test    r8, r8
0x18007b016  jz      short loc_18007B02E
0x18007b018  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007b01f  xor     edx, edx; dwFlags
0x18007b021  call    cs:__imp_HeapFree
0x18007b027  mov     [rbx+1328h], r12
0x18007b02e  mov     [rbx+1330h], r12
0x18007b035  mov     [rbx+1340h], r12d
0x18007b03c  test    byte ptr cs:xmmword_180266B60, 2
0x18007b043  jnz     loc_18007B785
0x18007b049  mov     r8, [rbx+14A0h]; lpMem
0x18007b050  test    r8, r8
0x18007b053  jnz     loc_18007B7BB
0x18007b059  mov     [rbx+14A0h], r12
0x18007b060  mov     [rbx+14A8h], r12w
0x18007b068  mov     [rbx+14ACh], ebp
0x18007b06e  test    byte ptr cs:xmmword_180266B60, 2
0x18007b075  jnz     loc_18007B7CF
0x18007b07b  mov     r8, [rbx+14B0h]; lpMem
0x18007b082  test    r8, r8
0x18007b085  jnz     loc_18007B7ED
0x18007b08b  mov     [rbx+14B0h], r12
0x18007b092  mov     [rbx+14B8h], r12w
0x18007b09a  mov     rcx, [rbx+14C0h]
0x18007b0a1  test    rcx, rcx
0x18007b0a4  jnz     loc_18007B801
0x18007b0aa  mov     r8, [rbx+4E0h]; lpMem
0x18007b0b1  test    r8, r8
0x18007b0b4  jz      short loc_18007B0CC
0x18007b0b6  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007b0bd  xor     edx, edx; dwFlags
0x18007b0bf  call    cs:__imp_HeapFree
0x18007b0c5  mov     [rbx+4E0h], r12
0x18007b0cc  mov     r8, [rbx+1508h]; lpMem
0x18007b0d3  test    r8, r8
0x18007b0d6  jnz     loc_18007B819
0x18007b0dc  mov     rdi, [rbx+14D0h]
0x18007b0e3  mov     r15d, 11h
0x18007b0e9  test    rdi, rdi
0x18007b0ec  jz      short loc_18007B11E
0x18007b0ee  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b0f5  jnz     loc_18007B517
0x18007b0fb  mov     esi, ebp
0x18007b0fd  lock xadd [rdi+10h], esi
0x18007b102  add     esi, ebp
0x18007b104  jz      loc_18007B4A2
0x18007b10a  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b111  jnz     loc_18007B834
0x18007b117  mov     [rbx+14D0h], r12
0x18007b11e  mov     r8, [rbx+1608h]; lpMem
0x18007b125  test    r8, r8
0x18007b128  jnz     loc_18007B850
0x18007b12e  mov     rcx, [rbx+1610h]; hObject
0x18007b135  cmp     rcx, rbp
0x18007b138  jnz     loc_18007B86B
0x18007b13e  mov     rcx, [rbx+408h]; this
0x18007b145  test    rcx, rcx
0x18007b148  jnz     loc_18007B87D
0x18007b14e  mov     rcx, [rbx+4B8h]
0x18007b155  test    rcx, rcx
0x18007b158  jnz     loc_18007B88E
0x18007b15e  mov     rcx, [rbx+3F8h]; void *
0x18007b165  test    rcx, rcx
0x18007b168  jnz     loc_18007B8BE
0x18007b16e  mov     rcx, [rbx+438h]
0x18007b175  test    rcx, rcx
0x18007b178  jnz     loc_18007B8CF
0x18007b17e  lea     rcx, [rbx+428h]
0x18007b185  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x18007b18a  mov     rcx, [rbx+1650h]; this
0x18007b191  mov     r14d, 58h ; 'X'
0x18007b197  mov     [rbx+430h], r12d
0x18007b19e  test    rcx, rcx
0x18007b1a1  jnz     loc_18007B3D7
0x18007b1a7  mov     rcx, [rbx+1658h]; this
0x18007b1ae  test    rcx, rcx
0x18007b1b1  jnz     loc_18007B55F
0x18007b1b7  mov     rcx, rbx; this
0x18007b1ba  call    ?TerminateHttpExtension@HTTP_REQUEST_HANDLE_OBJECT@@AEAAXXZ; HTTP_REQUEST_HANDLE_OBJECT::TerminateHttpExtension(void)
0x18007b1bf  mov     rcx, rbx; this
0x18007b1c2  call    ?TerminateRequestTrace@HTTP_REQUEST_HANDLE_OBJECT@@AEAAXXZ; HTTP_REQUEST_HANDLE_OBJECT::TerminateRequestTrace(void)
0x18007b1c7  mov     rcx, rbx; this
0x18007b1ca  call    ?TerminateResponseTrace@HTTP_REQUEST_HANDLE_OBJECT@@AEAAXXZ; HTTP_REQUEST_HANDLE_OBJECT::TerminateResponseTrace(void)
0x18007b1cf  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b1d6  jnz     loc_18007B8FF
0x18007b1dc  mov     r8, [rbx+16C0h]; lpMem
0x18007b1e3  lea     rsi, Data
0x18007b1ea  cmp     r8, rsi
0x18007b1ed  jz      short loc_18007B210
0x18007b1ef  test    r8, r8
0x18007b1f2  jz      short loc_18007B210
0x18007b1f4  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18007b1fb  jnz     loc_18007B4BC
0x18007b201  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007b208  xor     edx, edx; dwFlags
0x18007b20a  call    cs:__imp_HeapFree
0x18007b210  mov     [rbx+16C0h], rsi
0x18007b217  mov     [rbx+16C8h], r12
0x18007b21e  mov     rdi, [rbx+1658h]
0x18007b225  test    rdi, rdi
0x18007b228  jz      short loc_18007B23F
0x18007b22a  mov     eax, ebp
0x18007b22c  lock xadd [rdi], eax
0x18007b230  add     eax, ebp
0x18007b232  jz      loc_18007B41A
0x18007b238  mov     [rbx+1658h], r12
0x18007b23f  mov     rdi, [rbx+1650h]
0x18007b246  test    rdi, rdi
0x18007b249  jz      short loc_18007B260
0x18007b24b  mov     eax, ebp
0x18007b24d  lock xadd [rdi], eax
0x18007b251  add     eax, ebp
0x18007b253  jz      loc_18007B432
0x18007b259  mov     [rbx+1650h], r12
0x18007b260  mov     r8, [rbx+1528h]; lpMem
0x18007b267  cmp     r8, rsi
0x18007b26a  jz      short loc_18007B28D
0x18007b26c  test    r8, r8
0x18007b26f  jz      short loc_18007B28D
0x18007b271  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18007b278  jnz     loc_18007B4D0
0x18007b27e  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007b285  xor     edx, edx; dwFlags
0x18007b287  call    cs:__imp_HeapFree
0x18007b28d  mov     [rbx+1528h], rsi
0x18007b294  mov     [rbx+1530h], r12
0x18007b29b  mov     rcx, [rbx+14C0h]
0x18007b2a2  test    rcx, rcx
0x18007b2a5  jnz     loc_18007B402
0x18007b2ab  mov     rcx, [rbx+1438h]; void *
0x18007b2b2  test    rcx, rcx
0x18007b2b5  jnz     loc_18007B491
0x18007b2bb  mov     rcx, [rbx+1440h]
0x18007b2c2  test    rcx, rcx
0x18007b2c5  jnz     loc_18007B506
0x18007b2cb  mov     r8, [rbx+1448h]; lpMem
0x18007b2d2  test    r8, r8
0x18007b2d5  jnz     loc_18007B473
0x18007b2db  mov     [rbx+1448h], r12
0x18007b2e2  lea     rdi, [rbx+0C20h]
0x18007b2e9  mov     [rbx+1450h], r12
0x18007b2f0  mov     [rbx+1458h], r12
0x18007b2f7  mov     [rbx+1460h], r12
0x18007b2fe  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b305  lea     rsi, WPP_764547bcea91352f6757a10208e155bd_Traceguids
0x18007b30c  jnz     loc_18007B91A
0x18007b312  mov     rcx, rdi; this
0x18007b315  call    ?_RemoveAllHeaders@CHttpHeaders@@AEAAXXZ; CHttpHeaders::_RemoveAllHeaders(void)
0x18007b31a  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b321  mov     r14d, 12h
0x18007b327  jnz     loc_18007B932
0x18007b32d  lea     rcx, [rdi+6D0h]; lpCriticalSection
0x18007b334  call    cs:__imp_DeleteCriticalSection
0x18007b33a  mov     rcx, [rdi+630h]; this
0x18007b341  test    rcx, rcx
0x18007b344  jz      short loc_18007B35B
0x18007b346  mov     eax, ebp
0x18007b348  lock xadd [rcx], eax
0x18007b34c  add     eax, ebp
0x18007b34e  jz      loc_18007B45F
0x18007b354  mov     [rdi+630h], r12
0x18007b35b  lea     rdi, [rbx+500h]
0x18007b362  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b369  jnz     loc_18007B947
0x18007b36f  mov     rcx, rdi; this
0x18007b372  call    ?_RemoveAllHeaders@CHttpHeaders@@AEAAXXZ; CHttpHeaders::_RemoveAllHeaders(void)
0x18007b377  test    byte ptr cs:xmmword_180266B60+1, r13b
0x18007b37e  jnz     loc_18007B95F
0x18007b384  lea     rcx, [rdi+6D0h]; lpCriticalSection
0x18007b38b  call    cs:__imp_DeleteCriticalSection
0x18007b391  mov     rcx, [rdi+630h]; this
0x18007b398  test    rcx, rcx
0x18007b39b  jz      short loc_18007B3B2
0x18007b39d  mov     eax, ebp
0x18007b39f  lock xadd [rcx], eax
0x18007b3a3  add     eax, ebp
0x18007b3a5  jz      loc_18007B469
0x18007b3ab  mov     [rdi+630h], r12
0x18007b3b2  lea     rcx, [rbx+448h]; lpCriticalSection
0x18007b3b9  call    cs:__imp_DeleteCriticalSection
0x18007b3bf  mov     rcx, rbx; this
0x18007b3c2  add     rsp, 68h
0x18007b3c6  pop     r15
0x18007b3c8  pop     r14
0x18007b3ca  pop     r13
0x18007b3cc  pop     r12
0x18007b3ce  pop     rdi
0x18007b3cf  pop     rsi
0x18007b3d0  pop     rbp
0x18007b3d1  pop     rbx
0x18007b3d2  jmp     ??1INTERNET_CONNECT_HANDLE_OBJECT@@MEAA@XZ; INTERNET_CONNECT_HANDLE_OBJECT::~INTERNET_CONNECT_HANDLE_OBJECT(void)
0x18007b3d7  call    ?Cancel@CBlockFsmSync@@QEAAXXZ; CBlockFsmSync::Cancel(void)
0x18007b3dc  mov     rdi, [rbx+1650h]
0x18007b3e3  test    rdi, rdi
0x18007b3e6  jz      loc_18007B1A7
0x18007b3ec  mov     eax, ebp
0x18007b3ee  lock xadd [rdi], eax
0x18007b3f2  add     eax, ebp
  ... truncated ...
```
