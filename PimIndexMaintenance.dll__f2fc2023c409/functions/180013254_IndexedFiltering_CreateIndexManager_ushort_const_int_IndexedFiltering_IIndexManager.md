# IndexedFiltering::CreateIndexManager(ushort const *,int,IndexedFiltering::IIndexManager * *)

- ea: `0x180013254`
- end: `0x1800133e3`
- name: `?CreateIndexManager@IndexedFiltering@@YAJPEBGHPEAPEAUIIndexManager@1@@Z`
- size: `399`
- prototype: `__int64 __fastcall(IndexedFiltering *this, const unsigned __int16 *, __int64, struct IndexedFiltering::IIndexManager **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005d30`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x180013254`
- `0x1800133ec`
- `0x18001a008`
- `0x18001a908`
- `0x18001ab40`
- `0x1800211f2`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x18001330b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::CreateIndexManager(
        IndexedFiltering *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct IndexedFiltering::IIndexManager **a4)
{
  int v5; // esi
  struct IPOutlookApp3 *v6; // rcx
  struct IPOutlookAggregateCollection *v7; // r8
  __int64 i; // rdi
  int DataSource; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // r9d
  __int64 j; // rdi
  struct IndexedFiltering::ISortedDataSource *v16; // rcx
  const unsigned __int16 *v18; // [rsp+20h] [rbp-E0h]
  struct IndexedFiltering::IWritableDataSource *v19; // [rsp+40h] [rbp-C0h] BYREF
  struct IndexedFiltering::IndexManager *v20; // [rsp+48h] [rbp-B8h] BYREF
  struct IndexedFiltering::ISortedDataSource *v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  _BYTE v24[1040]; // [rsp+80h] [rbp-80h] BYREF

  v20 = 0;
  v23 = 0;
  v5 = (int)a2;
  v19 = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  memcpy_0(v24, &gc_contactsIndexSources, sizeof(v24));
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
  {
    DataSource = POOMSortedAggregateDataSource::CreateDataSource(
                   v6,
                   (struct tagSQLCESORTORDERSPEC *)&v24[208 * (unsigned int)i + 60],
                   v7,
                   &v21[i]);
    v10 = DataSource;
    if ( DataSource < 0 )
    {
      Log_HREvent_5((unsigned int)DataSource, 1, v7, 87);
      v11 = 63;
      v12 = v10;
LABEL_6:
      Log_HREvent(
        v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        v11);
      goto LABEL_13;
    }
  }
  v13 = POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(
          &GUID_a0430635_057d_4803_9ba7_be9cb04e78e4,
          (void **)&v19);
  v10 = v13;
  if ( v13 < 0 )
  {
    v11 = 70;
LABEL_9:
    v12 = (unsigned int)v13;
    goto LABEL_6;
  }
  v13 = IndexedFiltering::IndexManager::CreateInstance(
          v19,
          v21,
          (const struct IndexedFiltering::_IndexSourceData *)v24,
          v14,
          v18,
          v5,
          &v20);
  v10 = v13;
  if ( v13 < 0 )
  {
    v11 = 79;
    goto LABEL_9;
  }
  v10 = (**(__int64 (__fastcall ***)(struct IndexedFiltering::IndexManager *, GUID *, __int64))v20)(
          v20,
          &IID_IIndexManager,
          a3);
LABEL_13:
  for ( j = 0; j != 5; ++j )
  {
    v16 = v21[j];
    if ( v16 )
      (*(void (__fastcall **)(struct IndexedFiltering::ISortedDataSource *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  return v10;
}

```

## disassembly

```asm
0x180013254  mov     [rsp-8+arg_0], rbx
0x180013259  mov     [rsp-8+arg_18], rsi
0x18001325e  push    rbp
0x18001325f  push    rdi
0x180013260  push    r14
0x180013262  lea     rbp, [rsp-3A0h]
0x18001326a  sub     rsp, 4A0h
0x180013271  mov     rax, cs:__security_cookie
0x180013278  xor     rax, rsp
0x18001327b  mov     [rbp+3B0h+var_20], rax
0x180013282  xorps   xmm0, xmm0
0x180013285  mov     [rsp+4B0h+var_468], 0
0x18001328e  xor     eax, eax
0x180013290  lea     rcx, [rbp+3B0h+var_430]; void *
0x180013294  mov     r14, r8
0x180013297  mov     [rsp+4B0h+var_440], rax
0x18001329c  mov     esi, edx
0x18001329e  mov     [rsp+4B0h+var_470], rax
0x1800132a3  mov     r8d, 410h; Size
0x1800132a9  lea     rdx, ?gc_contactsIndexSources@@3QBU_IndexSourceData@IndexedFiltering@@B; Src
0x1800132b0  movups  xmmword ptr [rsp+4B0h+var_460], xmm0
0x1800132b5  movups  [rsp+4B0h+var_450], xmm0
0x1800132ba  call    memcpy_0
0x1800132bf  xor     edi, edi
0x1800132c1  cmp     edi, 5
0x1800132c4  jnb     short loc_180013319
0x1800132c6  mov     eax, edi
0x1800132c8  lea     r9, [rsp+4B0h+var_460]
0x1800132cd  imul    rax, 0D0h
0x1800132d4  lea     rdx, [rbp+3B0h+var_3F4]
0x1800132d8  add     rdx, rax; struct tagSQLCESORTORDERSPEC *
0x1800132db  lea     r9, [r9+rdi*8]; struct IndexedFiltering::ISortedDataSource **
0x1800132df  call    ?CreateDataSource@POOMSortedAggregateDataSource@@SAJPEAUIPOutlookApp3@@PEAUtagSQLCESORTORDERSPEC@@PEAUIPOutlookAggregateCollection@@PEAPEAUISortedDataSource@IndexedFiltering@@@Z; POOMSortedAggregateDataSource::CreateDataSource(IPOutlookApp3 *,tagSQLCESORTORDERSPEC *,IPOutlookAggregateCollection *,IndexedFiltering::ISortedDataSource * *)
0x1800132e4  mov     ebx, eax
0x1800132e6  test    eax, eax
0x1800132e8  js      short loc_1800132EE
0x1800132ea  inc     edi
0x1800132ec  jmp     short loc_1800132C1
0x1800132ee  mov     edx, 1
0x1800132f3  mov     ecx, ebx
0x1800132f5  lea     r9d, [rdx+56h]
0x1800132f9  call    Log_HREvent_5
0x1800132fe  mov     r9d, 3Fh ; '?'
0x180013304  mov     ecx, ebx
0x180013306  mov     edx, 1
0x18001330b  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013312  call    Log_HREvent
0x180013317  jmp     short loc_180013385
0x180013319  lea     rdx, [rsp+4B0h+var_470]; void **
0x18001331e  lea     rcx, _GUID_a0430635_057d_4803_9ba7_be9cb04e78e4; struct _GUID *
0x180013325  call    ?CreateDataSource@UnifiedStoreAggregateDataSource@POOMIndexing@@SAJAEBU_GUID@@PEAPEAX@Z; POOMIndexing::UnifiedStoreAggregateDataSource::CreateDataSource(_GUID const &,void * *)
0x18001332a  mov     ebx, eax
0x18001332c  test    eax, eax
0x18001332e  jns     short loc_18001333A
0x180013330  mov     r9d, 46h ; 'F'
0x180013336  mov     ecx, eax
0x180013338  jmp     short loc_180013306
0x18001333a  mov     rcx, [rsp+4B0h+var_470]; struct IndexedFiltering::IWritableDataSource *
0x18001333f  lea     rax, [rsp+4B0h+var_468]
0x180013344  mov     [rsp+4B0h+var_480], rax; struct IndexedFiltering::IndexManager **
0x180013349  lea     r8, [rbp+3B0h+var_430]; struct IndexedFiltering::_IndexSourceData *
0x18001334d  lea     rdx, [rsp+4B0h+var_460]; struct IndexedFiltering::ISortedDataSource **
0x180013352  mov     [rsp+4B0h+var_488], esi; int
0x180013356  call    ?CreateInstance@IndexManager@IndexedFiltering@@SAJPEAUIWritableDataSource@2@PEAPEAUISortedDataSource@2@PEBU_IndexSourceData@2@IPEBGHPEAPEAV12@@Z; IndexedFiltering::IndexManager::CreateInstance(IndexedFiltering::IWritableDataSource *,IndexedFiltering::ISortedDataSource * *,IndexedFiltering::_IndexSourceData const *,uint,ushort const *,int,IndexedFiltering::IndexManager * *)
0x18001335b  mov     ebx, eax
0x18001335d  test    eax, eax
0x18001335f  jns     short loc_180013369
0x180013361  mov     r9d, 4Fh ; 'O'
0x180013367  jmp     short loc_180013336
0x180013369  mov     rcx, [rsp+4B0h+var_468]
0x18001336e  lea     rdx, IID_IIndexManager
0x180013375  mov     r8, r14
0x180013378  mov     rax, [rcx]
0x18001337b  mov     rax, [rax]
0x18001337e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013383  mov     ebx, eax
0x180013385  xor     edi, edi
0x180013387  mov     rcx, [rsp+rdi*8+4B0h+var_460]
0x18001338c  test    rcx, rcx
0x18001338f  jz      short loc_18001339D
0x180013391  mov     rax, [rcx]
0x180013394  mov     rax, [rax+10h]
0x180013398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339d  inc     rdi
0x1800133a0  cmp     rdi, 5
0x1800133a4  jnz     short loc_180013387
0x1800133a6  lea     rcx, [rsp+4B0h+var_470]
0x1800133ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133b0  lea     rcx, [rsp+4B0h+var_468]
0x1800133b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133ba  mov     eax, ebx
0x1800133bc  mov     rcx, [rbp+3B0h+var_20]
0x1800133c3  xor     rcx, rsp; StackCookie
0x1800133c6  call    __security_check_cookie
0x1800133cb  lea     r11, [rsp+4B0h+var_10]
0x1800133d3  mov     rbx, [r11+20h]
0x1800133d7  mov     rsi, [r11+38h]
0x1800133db  mov     rsp, r11
0x1800133de  pop     r14
0x1800133e0  pop     rdi
0x1800133e1  pop     rbp
0x1800133e2  retn
```
