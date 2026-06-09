# CMapiStore::~CMapiStore(void)

- ea: `0x180032e18`
- end: `0x180033032`
- name: `??1CMapiStore@@UEAA@XZ`
- size: `538`
- prototype: `void __fastcall(CMapiStore *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180033100`

## callees

- `0x18000ad14`
- `0x1800113ec`
- `0x180011884`
- `0x180022920`
- `0x180032e18`
- `0x1800330c4`
- `0x180033154`
- `0x180034f64`
- `0x180035000`
- `0x18003509c`
- `0x180035138`
- `0x18003519c`
- `0x180037388`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032eab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032eab`

## string_xrefs

- `0x180032eb5`: `CMapiStore::~CMapiStore(%s) Deleted`

## pseudocode

```c
void __fastcall CMapiStore::~CMapiStore(CMapiStore *this)
{
  unsigned int v2; // edx
  CEntryId *v3; // rcx
  __int64 *v4; // rdi
  __int64 v5; // rcx
  unsigned int v6; // esi

  *(_QWORD *)this = &CMapiStore::`vftable';
  CMapiStore::RemoveAllSinks(this);
  CMapiStore::RemoveAllFolderNotifyProps(this);
  v3 = (CEntryId *)*((_QWORD *)this + 4);
  if ( v3 )
    CEntryId::`scalar deleting destructor'(v3, v2);
  v4 = (__int64 *)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
  {
    CLogger::Info(L"CMapiStore::~CMapiStore(%s) Releasing pMsgStore", *((_QWORD *)this + 8));
    v5 = *v4;
    *v4 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( *v4 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 6, 0);
    CLogger::Info(L"CMapiStore::~CMapiStore(%s) Released pMsgStore (refCnt=%d)", *((_QWORD *)this + 8), v6);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  CLogger::Info(L"CMapiStore::~CMapiStore(%s) Deleted", *((_QWORD *)this + 8));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 83) - 24LL));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 79);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 77) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 76) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 75) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 74) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 73) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 72) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 71) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 70) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 69) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 68) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 67) - 24LL));
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,_GUID,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<_GUID>>::RemoveAll((char *)this + 464);
  ATL::CAtlMap<_GUID,CFolderNotificationProps *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CFolderNotificationProps *>>::RemoveAll((char *)this + 392);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll((char *)this + 320);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll((char *)this + 248);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>((char *)this + 232);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>((char *)this + 216);
  ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>((char *)this + 200);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 18) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 8) - 24LL));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 6);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 5) - 24LL));
  CEntryId::FreeBuffer((CMapiStore *)((char *)this + 16));
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180032e18  mov     [rsp+arg_0], rbx
0x180032e1d  mov     [rsp+arg_8], rsi
0x180032e22  push    rdi
0x180032e23  sub     rsp, 20h
0x180032e27  mov     rbx, rcx
0x180032e2a  lea     rax, ??_7CMapiStore@@6B@; const CMapiStore::`vftable'
0x180032e31  mov     [rcx], rax
0x180032e34  call    ?RemoveAllSinks@CMapiStore@@QEAAJXZ; CMapiStore::RemoveAllSinks(void)
0x180032e39  mov     rcx, rbx; this
0x180032e3c  call    ?RemoveAllFolderNotifyProps@CMapiStore@@QEAAXXZ; CMapiStore::RemoveAllFolderNotifyProps(void)
0x180032e41  mov     rcx, [rbx+20h]; this
0x180032e45  test    rcx, rcx
0x180032e48  jz      short loc_180032E4F
0x180032e4a  call    ??_GCEntryId@@QEAAPEAXI@Z; CEntryId::`scalar deleting destructor'(uint)
0x180032e4f  lea     rdi, [rbx+30h]
0x180032e53  cmp     qword ptr [rdi], 0
0x180032e57  jz      short loc_180032EA4
0x180032e59  mov     rdx, [rbx+40h]
0x180032e5d  lea     rcx, aCmapistoreCmap_4; "CMapiStore::~CMapiStore(%s) Releasing p"...
0x180032e64  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180032e69  mov     rcx, [rdi]
0x180032e6c  mov     qword ptr [rdi], 0
0x180032e73  mov     rax, [rcx]
0x180032e76  mov     rax, [rax+10h]
0x180032e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e7f  mov     esi, eax
0x180032e81  cmp     qword ptr [rdi], 0
0x180032e85  jz      short loc_180032E91
0x180032e87  xor     edx, edx; struct IUnknown *
0x180032e89  mov     rcx, rdi; struct IUnknown **
0x180032e8c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180032e91  mov     r8d, esi
0x180032e94  mov     rdx, [rbx+40h]
0x180032e98  lea     rcx, aCmapistoreCmap_2; "CMapiStore::~CMapiStore(%s) Released pM"...
0x180032e9f  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180032ea4  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180032eab  call    cs:__imp_DeleteCriticalSection
0x180032eb1  mov     rdx, [rbx+40h]
0x180032eb5  lea     rcx, aCmapistoreCmap; "CMapiStore::~CMapiStore(%s) Deleted"
0x180032ebc  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180032ec1  mov     rcx, [rbx+298h]
0x180032ec8  mov     esi, 18h
0x180032ecd  sub     rcx, rsi; this
0x180032ed0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032ed5  lea     rcx, [rbx+278h]
0x180032edc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ee1  mov     rcx, [rbx+268h]
0x180032ee8  sub     rcx, rsi; this
0x180032eeb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032ef0  mov     rcx, [rbx+260h]
0x180032ef7  sub     rcx, rsi; this
0x180032efa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032eff  mov     rcx, [rbx+258h]
0x180032f06  sub     rcx, rsi; this
0x180032f09  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f0e  mov     rcx, [rbx+250h]
0x180032f15  sub     rcx, rsi; this
0x180032f18  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f1d  mov     rcx, [rbx+248h]
0x180032f24  sub     rcx, rsi; this
0x180032f27  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f2c  mov     rcx, [rbx+240h]
0x180032f33  sub     rcx, rsi; this
0x180032f36  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f3b  mov     rcx, [rbx+238h]
0x180032f42  sub     rcx, rsi; this
0x180032f45  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f4a  mov     rcx, [rbx+230h]
0x180032f51  sub     rcx, rsi; this
0x180032f54  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f59  mov     rcx, [rbx+228h]
0x180032f60  sub     rcx, rsi; this
0x180032f63  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f68  mov     rcx, [rbx+220h]
0x180032f6f  sub     rcx, rsi; this
0x180032f72  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f77  mov     rcx, [rbx+218h]
0x180032f7e  sub     rcx, rsi; this
0x180032f81  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032f86  lea     rcx, [rbx+1D0h]
0x180032f8d  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@U_GUID@@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@U_GUID@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,_GUID,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<_GUID>>::RemoveAll(void)
0x180032f92  lea     rcx, [rbx+188h]
0x180032f99  call    ?RemoveAll@?$CAtlMap@U_GUID@@PEAVCFolderNotificationProps@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAVCFolderNotificationProps@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<_GUID,CFolderNotificationProps *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CFolderNotificationProps *>>::RemoveAll(void)
0x180032f9e  lea     rcx, [rbx+140h]
0x180032fa5  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x180032faa  lea     rcx, [rbx+0F8h]
0x180032fb1  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::RemoveAll(void)
0x180032fb6  lea     rcx, [rbx+0E8h]
0x180032fbd  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x180032fc2  lea     rcx, [rbx+0D8h]
0x180032fc9  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x180032fce  lea     rcx, [rbx+0C8h]
0x180032fd5  call    ??1?$CSimpleArray@PEAXV?$CSimpleArrayEqualHelper@PEAX@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>::~CSimpleArray<void *,ATL::CSimpleArrayEqualHelper<void *>>(void)
0x180032fda  mov     rcx, [rbx+90h]
0x180032fe1  sub     rcx, rsi; this
0x180032fe4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032fe9  mov     rcx, [rbx+40h]
0x180032fed  sub     rcx, rsi; this
0x180032ff0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032ff5  lea     rcx, [rbx+38h]
0x180032ff9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ffe  mov     rcx, rdi
0x180033001  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180033006  mov     rcx, [rbx+28h]
0x18003300a  sub     rcx, rsi; this
0x18003300d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180033012  lea     rcx, [rbx+10h]; this
0x180033016  call    ?FreeBuffer@CEntryId@@AEAAXXZ; CEntryId::FreeBuffer(void)
0x18003301b  mov     dword ptr [rbx+10h], 0
0x180033022  mov     rbx, [rsp+28h+arg_0]
0x180033027  mov     rsi, [rsp+28h+arg_8]
0x18003302c  add     rsp, 20h
0x180033030  pop     rdi
0x180033031  retn
```
