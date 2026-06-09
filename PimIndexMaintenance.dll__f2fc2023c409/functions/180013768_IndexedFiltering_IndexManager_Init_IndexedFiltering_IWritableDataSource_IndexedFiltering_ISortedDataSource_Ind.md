# IndexedFiltering::IndexManager::Init(IndexedFiltering::IWritableDataSource *,IndexedFiltering::ISortedDataSource * *,IndexedFiltering::_IndexSourceData const *,uint,ushort const *,int)

- ea: `0x180013768`
- end: `0x180013b79`
- name: `?Init@IndexManager@IndexedFiltering@@IEAAJPEAUIWritableDataSource@2@PEAPEAUISortedDataSource@2@PEBU_IndexSourceData@2@IPEBGH@Z`
- size: `1041`
- prototype: `__int64 __fastcall(ESESession **this, struct IndexedFiltering::IWritableDataSource *, struct IndexedFiltering::ISortedDataSource **, const struct IndexedFiltering::_IndexSourceData *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x1800133ec`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000b5f4`
- `0x18000e634`
- `0x18000ee40`
- `0x18000f7e0`
- `0x180012b24`
- `0x180012e98`
- `0x180013124`
- `0x180013734`
- `0x180013768`
- `0x180016978`
- `0x18001706c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800139ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013a22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800139ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013a22`

## string_xrefs

- `0x1800137a1`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x1800139c9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013b2f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013b4e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::Init(
        ESESession **this,
        struct IndexedFiltering::IWritableDataSource *a2,
        struct IndexedFiltering::ISortedDataSource **a3,
        const struct IndexedFiltering::_IndexSourceData *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        unsigned int a7)
{
  int IndexingStoreVolumePath; // ebx
  __int64 v12; // r9
  struct ESESession **v13; // rbx
  ESEDataSource *v14; // rcx
  unsigned __int64 Instance; // rax
  unsigned int v16; // edi
  ESESession *v17; // rdi
  int (__fastcall *v18)(ESESession *, __int64, const unsigned __int16 **); // rbx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 i; // r14
  ESESession *v23; // rcx
  int v24; // eax
  ESESession *v25; // rcx
  unsigned __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  ESESession *v31; // rdx
  ESESession *v32; // rax
  ESESession *v33; // rdx
  ESESession *v34; // rax
  __int64 j; // r14
  ESESession *v36; // rcx
  ESESession *v37; // rcx
  int v38; // r15d
  unsigned __int64 *v39; // rax
  int v41; // [rsp+40h] [rbp-40h] BYREF
  int v42; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int64 v43; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v44; // [rsp+50h] [rbp-30h] BYREF
  unsigned int *v45; // [rsp+58h] [rbp-28h] BYREF
  unsigned int *v46; // [rsp+60h] [rbp-20h] BYREF
  ESESession *v47; // [rsp+68h] [rbp-18h] BYREF
  __int64 v48; // [rsp+70h] [rbp-10h] BYREF

  IndexingStoreVolumePath = GetIndexingStoreVolumePath((__int64)(this + 20));
  if ( IndexingStoreVolumePath >= 0 )
  {
    IndexingStoreVolumePath = ESEDataSource::EnsureDBInitialized((ESEDataSource *)&g_dataSource, 0);
    if ( IndexingStoreVolumePath < 0 )
    {
      v12 = 607;
      goto LABEL_3;
    }
    v13 = (struct ESESession **)tlx::replace<ESESession,&void tlx::_delete<ESESession>(ESESession *)>(this + 15);
    Instance = ESEDataSource::GetInstance(v14);
    IndexingStoreVolumePath = ESESession::CreateInstance(Instance, 0, v13);
    if ( IndexingStoreVolumePath < 0 )
    {
      v12 = 609;
      goto LABEL_3;
    }
    IndexingStoreVolumePath = ESESession::EnsureIndexInfoTable(this[15]);
    if ( IndexingStoreVolumePath < 0 )
    {
      v12 = 611;
      goto LABEL_3;
    }
    v16 = a7;
    IndexingStoreVolumePath = (*((__int64 (__fastcall **)(ESESession **, _QWORD, struct IndexedFiltering::IWritableDataSource *, struct IndexedFiltering::ISortedDataSource **, const struct IndexedFiltering::_IndexSourceData *, int))*this
                               + 11))(
                                this,
                                a7,
                                a2,
                                a3,
                                a4,
                                5);
    if ( IndexingStoreVolumePath < 0 )
    {
      v12 = 619;
      goto LABEL_3;
    }
    if ( !v16 )
    {
      IndexingStoreVolumePath = IndexedFiltering::IndexManager::CheckDataSourceAndIndexConsistency((IndexedFiltering::IndexManager *)this);
      if ( IndexingStoreVolumePath < 0 )
      {
        v12 = 623;
        goto LABEL_3;
      }
    }
    v17 = this[3];
    v45 = 0;
    LODWORD(a6) = 0;
    v18 = *(int (__fastcall **)(ESESession *, __int64, const unsigned __int16 **))(*(_QWORD *)v17 + 40LL);
    v19 = tlx::replace<unsigned long,&void _LocalFreer<unsigned long>(unsigned long *)>(&v45);
    if ( v18(v17, v19, &a6) >= 0 )
    {
      v20 = (unsigned int)a6;
      v21 = (unsigned __int64)this[25] + (unsigned int)a6;
      if ( v21 < (unsigned int)a6 )
      {
        this[25] = (ESESession *)-1LL;
        v27 = 632;
        v28 = 1;
        IndexingStoreVolumePath = -2147024362;
        goto LABEL_26;
      }
      this[25] = (ESESession *)v21;
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 28); i = (unsigned int)(i + 1) )
    {
      v23 = this[i + 9];
      v41 = 0;
      v24 = (*(__int64 (__fastcall **)(ESESession *, int *))(*(_QWORD *)v23 + 32LL))(v23, &v41);
      IndexingStoreVolumePath = v24;
      if ( v24 < 0 )
      {
        v27 = 639;
        goto LABEL_35;
      }
      v25 = this[i + 9];
      v48 = 0;
      a5 = 0;
      v24 = (*(__int64 (__fastcall **)(ESESession *, __int64 *, unsigned int *))(*(_QWORD *)v25 + 24LL))(v25, &v48, &a5);
      IndexingStoreVolumePath = v24;
      if ( v24 < 0 )
      {
        v27 = 644;
LABEL_35:
        v29 = (unsigned int)v24;
        goto LABEL_36;
      }
      v20 = a5;
      if ( (v41 & 0x20) != 0 )
      {
        v26 = (unsigned __int64)this[27] + a5;
        if ( v26 < a5 )
        {
          this[27] = (ESESession *)-1LL;
          v27 = 652;
          goto LABEL_31;
        }
        this[27] = (ESESession *)v26;
      }
      else
      {
        v30 = (unsigned __int64)this[25] + a5;
        if ( v30 < a5 )
        {
          this[25] = (ESESession *)-1LL;
          v27 = 648;
LABEL_31:
          IndexingStoreVolumePath = -2147024362;
          v29 = 2147942934LL;
LABEL_36:
          v28 = 1;
          goto LABEL_37;
        }
        this[25] = (ESESession *)v30;
      }
    }
    v31 = this[25];
    if ( !v31 || (v32 = (ESESession *)LocalAlloc(0, 4LL * (_QWORD)v31), (this[24] = v32) != 0) )
    {
      v33 = this[27];
      if ( !v33 || (v34 = (ESESession *)LocalAlloc(0, 4LL * (_QWORD)v33), (this[26] = v34) != 0) )
      {
        v44 = 0;
        if ( (_DWORD)a6 )
          IndexedFiltering::IndexManager::AddIndexedProperties(
            (IndexedFiltering::IndexManager *)this,
            1,
            v45,
            (unsigned int)a6,
            &v44);
        v47 = 0;
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 28); j = (unsigned int)(j + 1) )
        {
          v36 = this[j + 9];
          v42 = 0;
          v24 = (*(__int64 (__fastcall **)(ESESession *, int *))(*(_QWORD *)v36 + 32LL))(v36, &v42);
          IndexingStoreVolumePath = v24;
          if ( v24 < 0 )
          {
            v27 = 690;
            goto LABEL_35;
          }
          v37 = this[j + 9];
          v46 = 0;
          v38 = v42 & 0x20;
          LODWORD(v43) = 0;
          v24 = (*(__int64 (__fastcall **)(ESESession *, unsigned int **, unsigned __int64 *))(*(_QWORD *)v37 + 24LL))(
                  v37,
                  &v46,
                  &v43);
          IndexingStoreVolumePath = v24;
          if ( v24 < 0 )
          {
            v27 = 695;
            goto LABEL_35;
          }
          v39 = (unsigned __int64 *)&v47;
          if ( !v38 )
            v39 = &v44;
          IndexedFiltering::IndexManager::AddIndexedProperties(
            (IndexedFiltering::IndexManager *)this,
            v38 == 0,
            v46,
            (unsigned int)v43,
            v39);
        }
        if ( (ESESession *)v44 != this[25] )
          Log_AssertionEvent(
            v20,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
            700);
        if ( v47 != this[27] )
          Log_AssertionEvent(
            v20,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
            701);
        IndexingStoreVolumePath = 0;
LABEL_61:
        auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(&v45);
        return (unsigned int)IndexingStoreVolumePath;
      }
      v27 = 672;
    }
    else
    {
      v27 = 664;
    }
    v28 = 0;
    IndexingStoreVolumePath = -2147024882;
LABEL_26:
    v29 = (unsigned int)IndexingStoreVolumePath;
LABEL_37:
    Log_HREvent(
      v29,
      v28,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      v27);
    goto LABEL_61;
  }
  v12 = 604;
LABEL_3:
  Log_HREvent(
    (unsigned int)IndexingStoreVolumePath,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
    v12);
  return (unsigned int)IndexingStoreVolumePath;
}

```

## disassembly

```asm
0x180013768  push    rbp
0x18001376a  push    rbx
0x18001376b  push    rsi
0x18001376c  push    rdi
0x18001376d  push    r12
0x18001376f  push    r14
0x180013771  push    r15
0x180013773  mov     rbp, rsp
0x180013776  sub     rsp, 80h
0x18001377d  mov     rsi, rcx
0x180013780  mov     r14, r9
0x180013783  add     rcx, 0A0h
0x18001378a  mov     r15, r8
0x18001378d  mov     r12, rdx
0x180013790  call    ?GetIndexingStoreVolumePath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetIndexingStoreVolumePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180013795  mov     ebx, eax
0x180013797  test    eax, eax
0x180013799  jns     short loc_1800137B9
0x18001379b  mov     r9d, 25Ch
0x1800137a1  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800137a8  mov     edx, 1
0x1800137ad  mov     ecx, ebx
0x1800137af  call    Log_HREvent
0x1800137b4  jmp     loc_180013B65
0x1800137b9  xor     edx, edx; unsigned __int16 *
0x1800137bb  lea     rcx, ?g_dataSource@@3VESEDataSource@@A; this
0x1800137c2  call    ?EnsureDBInitialized@ESEDataSource@@QEAAJPEBG@Z; ESEDataSource::EnsureDBInitialized(ushort const *)
0x1800137c7  mov     ebx, eax
0x1800137c9  test    eax, eax
0x1800137cb  jns     short loc_1800137D5
0x1800137cd  mov     r9d, 25Fh
0x1800137d3  jmp     short loc_1800137A1
0x1800137d5  lea     rcx, [rsi+78h]
0x1800137d9  call    ??$replace@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVESESession@@AEAV?$auto_ptr@VESESession@@$1??$_delete@VESESession@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<ESESession,&tlx::_delete<ESESession>(ESESession *)>(tlx::auto_ptr<ESESession,&tlx::_delete<ESESession>(ESESession *)> &)
0x1800137de  mov     rbx, rax
0x1800137e1  call    ?GetInstance@ESEDataSource@@QEAA?B_KXZ; ESEDataSource::GetInstance(void)
0x1800137e6  mov     r8, rbx; struct ESESession **
0x1800137e9  xor     edx, edx; int
0x1800137eb  mov     rcx, rax; unsigned __int64
0x1800137ee  call    ?CreateInstance@ESESession@@SAJ_KHPEAPEAV1@@Z; ESESession::CreateInstance(unsigned __int64,int,ESESession * *)
0x1800137f3  mov     ebx, eax
0x1800137f5  test    eax, eax
0x1800137f7  jns     short loc_180013801
0x1800137f9  mov     r9d, 261h
0x1800137ff  jmp     short loc_1800137A1
0x180013801  mov     rcx, [rsi+78h]; this
0x180013805  call    ?EnsureIndexInfoTable@ESESession@@QEAAJXZ; ESESession::EnsureIndexInfoTable(void)
0x18001380a  mov     ebx, eax
0x18001380c  test    eax, eax
0x18001380e  jns     short loc_180013818
0x180013810  mov     r9d, 263h
0x180013816  jmp     short loc_1800137A1
0x180013818  mov     rax, [rsi]
0x18001381b  mov     r9, r15
0x18001381e  mov     edi, [rbp+arg_30]
0x180013821  mov     r8, r12
0x180013824  mov     [rsp+80h+var_58], 5
0x18001382c  mov     edx, edi
0x18001382e  mov     rcx, rsi
0x180013831  mov     [rsp+80h+var_60], r14
0x180013836  mov     rax, [rax+58h]
0x18001383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001383f  mov     ebx, eax
0x180013841  test    eax, eax
0x180013843  jns     short loc_180013850
0x180013845  mov     r9d, 26Bh
0x18001384b  jmp     loc_1800137A1
0x180013850  test    edi, edi
0x180013852  jnz     short loc_18001386D
0x180013854  mov     rcx, rsi; this
0x180013857  call    ?CheckDataSourceAndIndexConsistency@IndexManager@IndexedFiltering@@AEAAJXZ; IndexedFiltering::IndexManager::CheckDataSourceAndIndexConsistency(void)
0x18001385c  mov     ebx, eax
0x18001385e  test    eax, eax
0x180013860  jns     short loc_18001386D
0x180013862  mov     r9d, 26Fh
0x180013868  jmp     loc_1800137A1
0x18001386d  mov     rdi, [rsi+18h]
0x180013871  lea     rcx, [rbp+var_28]
0x180013875  mov     [rbp+var_28], 0
0x18001387d  mov     dword ptr [rbp+arg_28], 0
0x180013884  mov     rax, [rdi]
0x180013887  mov     rbx, [rax+28h]
0x18001388b  call    ??$replace@K$1??$_LocalFreer@K@@YAXPEAK@Z@tlx@@YAPEAPEAKAEAV?$auto_array_ptr@K$1??$_LocalFreer@K@@YAXPEAK@Z@0@@Z; tlx::replace<ulong,&_LocalFreer<ulong>(ulong *)>(tlx::auto_array_ptr<ulong,&_LocalFreer<ulong>(ulong *)> &)
0x180013890  mov     rdx, rax
0x180013893  lea     r8, [rbp+arg_28]
0x180013897  mov     rax, rbx
0x18001389a  mov     rcx, rdi
0x18001389d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138a2  test    eax, eax
0x1800138a4  js      short loc_1800138C3
0x1800138a6  mov     ecx, dword ptr [rbp+arg_28]
0x1800138a9  mov     rdx, [rsi+0C8h]
0x1800138b0  add     rdx, rcx
0x1800138b3  cmp     rdx, rcx
0x1800138b6  jb      loc_18001394D
0x1800138bc  mov     [rsi+0C8h], rdx
0x1800138c3  xor     r14d, r14d
0x1800138c6  lea     edi, [r14+1]
0x1800138ca  cmp     r14d, [rsi+70h]
0x1800138ce  jnb     loc_1800139DA
0x1800138d4  mov     rcx, [rsi+r14*8+48h]
0x1800138d9  lea     rdx, [rbp+var_40]
0x1800138dd  mov     [rbp+var_40], 0
0x1800138e4  mov     rax, [rcx]
0x1800138e7  mov     rax, [rax+20h]
0x1800138eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f0  mov     ebx, eax
0x1800138f2  test    eax, eax
0x1800138f4  js      loc_1800139BF
0x1800138fa  mov     rcx, [rsi+r14*8+48h]
0x1800138ff  lea     r8, [rbp+arg_20]
0x180013903  mov     [rbp+var_10], 0
0x18001390b  lea     rdx, [rbp+var_10]
0x18001390f  mov     [rbp+arg_20], 0
0x180013916  mov     rax, [rcx]
0x180013919  mov     rax, [rax+18h]
0x18001391d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013922  mov     ebx, eax
0x180013924  test    eax, eax
0x180013926  js      loc_1800139B7
0x18001392c  test    byte ptr [rbp+var_40], 20h
0x180013930  mov     ecx, [rbp+arg_20]
0x180013933  jz      short loc_18001396C
0x180013935  mov     rdx, [rsi+0D8h]
0x18001393c  add     rdx, rcx
0x18001393f  cmp     rdx, rcx
0x180013942  jb      short loc_18001398A
0x180013944  mov     [rsi+0D8h], rdx
0x18001394b  jmp     short loc_180013982
0x18001394d  mov     qword ptr [rsi+0C8h], 0FFFFFFFFFFFFFFFFh
0x180013958  mov     r9d, 278h
0x18001395e  mov     edx, 1
0x180013963  mov     ebx, 80070216h
0x180013968  mov     ecx, ebx
0x18001396a  jmp     short loc_1800139C9
0x18001396c  mov     rdx, [rsi+0C8h]
0x180013973  add     rdx, rcx
0x180013976  cmp     rdx, rcx
0x180013979  jb      short loc_1800139A4
0x18001397b  mov     [rsi+0C8h], rdx
0x180013982  add     r14d, edi
0x180013985  jmp     loc_1800138CA
0x18001398a  mov     qword ptr [rsi+0D8h], 0FFFFFFFFFFFFFFFFh
0x180013995  mov     r9d, 28Ch
0x18001399b  mov     ebx, 80070216h
0x1800139a0  mov     ecx, ebx
0x1800139a2  jmp     short loc_1800139C7
0x1800139a4  mov     qword ptr [rsi+0C8h], 0FFFFFFFFFFFFFFFFh
0x1800139af  mov     r9d, 288h
0x1800139b5  jmp     short loc_18001399B
0x1800139b7  mov     r9d, 284h
0x1800139bd  jmp     short loc_1800139C5
0x1800139bf  mov     r9d, 27Fh
0x1800139c5  mov     ecx, eax
0x1800139c7  mov     edx, edi
0x1800139c9  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800139d0  call    Log_HREvent
0x1800139d5  jmp     loc_180013B5C
0x1800139da  mov     rdx, [rsi+0C8h]
0x1800139e1  test    rdx, rdx
0x1800139e4  jz      short loc_180013A10
0x1800139e6  shl     rdx, 2; uBytes
0x1800139ea  xor     ecx, ecx; uFlags
0x1800139ec  call    cs:__imp_LocalAlloc
0x1800139f2  mov     [rsi+0C0h], rax
0x1800139f9  test    rax, rax
0x1800139fc  jnz     short loc_180013A10
0x1800139fe  mov     r9d, 298h
0x180013a04  xor     edx, edx
0x180013a06  mov     ebx, 8007000Eh
0x180013a0b  jmp     loc_180013968
0x180013a10  mov     rdx, [rsi+0D8h]
0x180013a17  test    rdx, rdx
0x180013a1a  jz      short loc_180013A3C
0x180013a1c  shl     rdx, 2; uBytes
0x180013a20  xor     ecx, ecx; uFlags
0x180013a22  call    cs:__imp_LocalAlloc
0x180013a28  mov     [rsi+0D0h], rax
0x180013a2f  test    rax, rax
0x180013a32  jnz     short loc_180013A3C
0x180013a34  mov     r9d, 2A0h
0x180013a3a  jmp     short loc_180013A04
0x180013a3c  mov     eax, dword ptr [rbp+arg_28]
0x180013a3f  mov     [rbp+var_30], 0
0x180013a47  test    eax, eax
0x180013a49  jz      short loc_180013A65
0x180013a4b  mov     r8, [rbp+var_28]; unsigned int *
0x180013a4f  mov     r9d, eax; unsigned __int64
0x180013a52  lea     rax, [rbp+var_30]
0x180013a56  mov     edx, edi; int
0x180013a58  mov     rcx, rsi; this
0x180013a5b  mov     [rsp+80h+var_60], rax; unsigned __int64 *
0x180013a60  call    ?AddIndexedProperties@IndexManager@IndexedFiltering@@AEAAXHPEAK_KPEA_K@Z; IndexedFiltering::IndexManager::AddIndexedProperties(int,ulong *,unsigned __int64,unsigned __int64 *)
0x180013a65  mov     [rbp+var_18], 0
0x180013a6d  xor     r14d, r14d
0x180013a70  cmp     r14d, [rsi+70h]
0x180013a74  jnb     loc_180013B1C
0x180013a7a  mov     rcx, [rsi+r14*8+48h]
0x180013a7f  lea     rdx, [rbp+var_3C]
0x180013a83  mov     [rbp+var_3C], 0
0x180013a8a  mov     rax, [rcx]
0x180013a8d  mov     rax, [rax+20h]
0x180013a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a96  mov     ebx, eax
0x180013a98  test    eax, eax
0x180013a9a  js      short loc_180013B11
0x180013a9c  mov     rcx, [rsi+r14*8+48h]
0x180013aa1  lea     r8, [rbp+var_38]
0x180013aa5  mov     r15d, [rbp+var_3C]
0x180013aa9  lea     rdx, [rbp+var_20]
0x180013aad  mov     [rbp+var_20], 0
0x180013ab5  and     r15d, 20h
0x180013ab9  mov     dword ptr [rbp+var_38], 0
0x180013ac0  mov     rax, [rcx]
0x180013ac3  mov     rax, [rax+18h]
0x180013ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013acc  mov     ebx, eax
0x180013ace  test    eax, eax
0x180013ad0  js      short loc_180013B06
0x180013ad2  mov     r9d, dword ptr [rbp+var_38]; unsigned __int64
0x180013ad6  lea     rcx, [rbp+var_30]
0x180013ada  mov     r8, [rbp+var_20]; unsigned int *
0x180013ade  lea     rax, [rbp+var_18]
0x180013ae2  test    r15d, r15d
0x180013ae5  cmovz   rax, rcx
0x180013ae9  xor     edx, edx
0x180013aeb  test    r15d, r15d
0x180013aee  mov     [rsp+80h+var_60], rax; unsigned __int64 *
0x180013af3  mov     rcx, rsi; this
0x180013af6  setz    dl; int
0x180013af9  call    ?AddIndexedProperties@IndexManager@IndexedFiltering@@AEAAXHPEAK_KPEA_K@Z; IndexedFiltering::IndexManager::AddIndexedProperties(int,ulong *,unsigned __int64,unsigned __int64 *)
0x180013afe  add     r14d, edi
0x180013b01  jmp     loc_180013A70
0x180013b06  mov     r9d, 2B7h
0x180013b0c  jmp     loc_1800139C5
0x180013b11  mov     r9d, 2B2h
0x180013b17  jmp     loc_1800139C5
0x180013b1c  mov     rax, [rsi+0C8h]
0x180013b23  cmp     [rbp+var_30], rax
0x180013b27  jz      short loc_180013B3B
0x180013b29  mov     r8d, 2BCh
0x180013b2f  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013b36  call    Log_AssertionEvent
0x180013b3b  mov     rax, [rsi+0D8h]
0x180013b42  cmp     [rbp+var_18], rax
0x180013b46  jz      short loc_180013B5A
0x180013b48  mov     r8d, 2BDh
0x180013b4e  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013b55  call    Log_AssertionEvent
0x180013b5a  xor     ebx, ebx
0x180013b5c  lea     rcx, [rbp+var_28]
0x180013b60  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x180013b65  mov     eax, ebx
0x180013b67  add     rsp, 80h
0x180013b6e  pop     r15
0x180013b70  pop     r14
0x180013b72  pop     r12
0x180013b74  pop     rdi
0x180013b75  pop     rsi
0x180013b76  pop     rbx
0x180013b77  pop     rbp
0x180013b78  retn
```
