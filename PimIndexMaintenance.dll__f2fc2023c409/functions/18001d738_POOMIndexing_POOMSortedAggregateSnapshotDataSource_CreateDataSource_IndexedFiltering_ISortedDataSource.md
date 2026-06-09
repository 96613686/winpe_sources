# POOMIndexing::POOMSortedAggregateSnapshotDataSource::CreateDataSource(IndexedFiltering::ISortedDataSource * *)

- ea: `0x18001d738`
- end: `0x18001d8de`
- name: `?CreateDataSource@POOMSortedAggregateSnapshotDataSource@POOMIndexing@@SAJPEAPEAUISortedDataSource@IndexedFiltering@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(struct IndexedFiltering::ISortedDataSource **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800150d8`

## callees

- `0x1800012fc`
- `0x18000428c`
- `0x18001d738`
- `0x18001dcf0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d7e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d7e8`

## pseudocode

```c
__int64 __fastcall POOMIndexing::POOMSortedAggregateSnapshotDataSource::CreateDataSource(
        struct IndexedFiltering::ISortedDataSource **a1)
{
  struct IndexedFiltering::ISortedDataSource *v2; // rax
  __int64 v3; // r8
  struct IndexedFiltering::ISortedDataSource *v4; // rbx
  HRESULT v5; // eax
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rcx
  LPVOID v11; // rdi
  int v12; // eax
  __int64 v13; // r8
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  struct IndexedFiltering::ISortedDataSource *v16; // [rsp+60h] [rbp+30h] BYREF

  v2 = (struct IndexedFiltering::ISortedDataSource *)operator new(0x30u);
  v4 = v2;
  if ( !v2 )
  {
    v16 = 0;
    v7 = -2147024882;
    Log_HREvent_8(2147942414LL, 0, v3, 30);
    goto LABEL_14;
  }
  v16 = v2;
  *(_QWORD *)v2 = &IndexedFiltering::ISortedDataSource::`vftable';
  *((_QWORD *)v2 + 1) = &IndexedFiltering::IStaticFilter::`vftable';
  *((_QWORD *)v2 + 2) = &_CUnknownBase::`vftable';
  *((_DWORD *)v2 + 6) = 1;
  *(_QWORD *)v2 = &POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `IndexedFiltering::ISortedDataSource'};
  *((_QWORD *)v2 + 1) = &POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `IndexedFiltering::IReadableDataSource'};
  *((_QWORD *)v2 + 2) = &POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `CUnknownPrivate'};
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_Application, 0, 1u, &IID_IPOutlookApp3, &ppv);
  v7 = v5;
  if ( v5 < 0 )
  {
    v8 = 40;
LABEL_4:
    v9 = (unsigned int)v5;
    goto LABEL_5;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, 0);
  v7 = v5;
  if ( v5 < 0 )
  {
    v8 = 42;
    goto LABEL_4;
  }
  v10 = *((_QWORD *)v4 + 5);
  v11 = ppv;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  *((_QWORD *)v4 + 5) = v11;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = (*(__int64 (__fastcall **)(struct IndexedFiltering::ISortedDataSource *))(*(_QWORD *)v4 + 56LL))(v4);
  v7 = v12;
  if ( v12 >= 0 )
  {
    v16 = 0;
    *a1 = v4;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    v7 = 0;
    goto LABEL_14;
  }
  Log_HREvent_8((unsigned int)v12, 1, v13, 62);
  v8 = 44;
  v9 = v7;
LABEL_5:
  Log_HREvent_8(v9, 1, v6, v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_14:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  return v7;
}

```

## disassembly

```asm
0x18001d738  mov     [rsp-18h+arg_0], rbx
0x18001d73d  mov     [rsp-18h+arg_18], rsi
0x18001d742  push    rbp
0x18001d743  push    rdi
0x18001d744  push    r15
0x18001d746  mov     rbp, rsp
0x18001d749  sub     rsp, 30h
0x18001d74d  mov     rsi, rcx
0x18001d750  mov     ecx, 30h ; '0'; Size
0x18001d755  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d75a  mov     rbx, rax
0x18001d75d  test    rax, rax
0x18001d760  jz      loc_18001D8A6
0x18001d766  lea     rax, ??_7ISortedDataSource@IndexedFiltering@@6B@; const IndexedFiltering::ISortedDataSource::`vftable'
0x18001d76d  mov     [rbp+arg_10], rbx
0x18001d771  mov     [rbx], rax
0x18001d774  lea     r9, IID_IPOutlookApp3; riid
0x18001d77b  lea     rax, ??_7IStaticFilter@IndexedFiltering@@6B@; const IndexedFiltering::IStaticFilter::`vftable'
0x18001d782  mov     r15d, 1
0x18001d788  mov     [rbx+8], rax
0x18001d78c  lea     rcx, CLSID_Application; rclsid
0x18001d793  lea     rax, ??_7_CUnknownBase@@6B@; const _CUnknownBase::`vftable'
0x18001d79a  mov     r8d, r15d; dwClsContext
0x18001d79d  mov     [rbx+10h], rax
0x18001d7a1  xor     edx, edx; pUnkOuter
0x18001d7a3  mov     [rbx+18h], r15d
0x18001d7a7  lea     rax, ??_7POOMSortedAggregateSnapshotDataSource@POOMIndexing@@6BISortedDataSource@IndexedFiltering@@@; const POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `IndexedFiltering::ISortedDataSource'}
0x18001d7ae  mov     [rbx], rax
0x18001d7b1  lea     rax, ??_7POOMSortedAggregateSnapshotDataSource@POOMIndexing@@6BIReadableDataSource@IndexedFiltering@@@; const POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `IndexedFiltering::IReadableDataSource'}
0x18001d7b8  mov     [rbx+8], rax
0x18001d7bc  lea     rax, ??_7POOMSortedAggregateSnapshotDataSource@POOMIndexing@@6BCUnknownPrivate@@@; const POOMIndexing::POOMSortedAggregateSnapshotDataSource::`vftable'{for `CUnknownPrivate'}
0x18001d7c3  mov     [rbx+10h], rax
0x18001d7c7  lea     rax, [rbp+arg_8]
0x18001d7cb  mov     qword ptr [rbx+20h], 0
0x18001d7d3  mov     qword ptr [rbx+28h], 0
0x18001d7db  mov     [rbp+arg_8], 0
0x18001d7e3  mov     [rsp+30h+ppv], rax; ppv
0x18001d7e8  call    cs:__imp_CoCreateInstance
0x18001d7ee  mov     edi, eax
0x18001d7f0  test    eax, eax
0x18001d7f2  jns     short loc_18001D810
0x18001d7f4  lea     r9d, [r15+27h]
0x18001d7f8  mov     ecx, eax
0x18001d7fa  mov     edx, r15d
0x18001d7fd  call    Log_HREvent_8
0x18001d802  lea     rcx, [rbp+arg_8]
0x18001d806  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d80b  jmp     loc_18001D8C0
0x18001d810  mov     rcx, [rbp+arg_8]
0x18001d814  xor     edx, edx
0x18001d816  mov     rax, [rcx]
0x18001d819  mov     rax, [rax+38h]
0x18001d81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d822  mov     edi, eax
0x18001d824  test    eax, eax
0x18001d826  jns     short loc_18001D830
0x18001d828  mov     r9d, 2Ah ; '*'
0x18001d82e  jmp     short loc_18001D7F8
0x18001d830  mov     rcx, [rbx+28h]
0x18001d834  mov     rdi, [rbp+arg_8]
0x18001d838  test    rcx, rcx
0x18001d83b  jz      short loc_18001D849
0x18001d83d  mov     rax, [rcx]
0x18001d840  mov     rax, [rax+10h]
0x18001d844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d849  mov     [rbx+28h], rdi
0x18001d84d  mov     rcx, rdi
0x18001d850  mov     rax, [rdi]
0x18001d853  mov     rax, [rax+8]
0x18001d857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85c  mov     rax, [rbx]
0x18001d85f  mov     rcx, rbx
0x18001d862  mov     rax, [rax+38h]
0x18001d866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d86b  mov     edi, eax
0x18001d86d  test    eax, eax
0x18001d86f  jns     short loc_18001D88E
0x18001d871  mov     r9d, 3Eh ; '>'
0x18001d877  mov     edx, r15d
0x18001d87a  mov     ecx, eax
0x18001d87c  call    Log_HREvent_8
0x18001d881  mov     r9d, 2Ch ; ','
0x18001d887  mov     ecx, edi
0x18001d889  jmp     loc_18001D7FA
0x18001d88e  lea     rcx, [rbp+arg_8]
0x18001d892  mov     [rbp+arg_10], 0
0x18001d89a  mov     [rsi], rbx
0x18001d89d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d8a2  xor     edi, edi
0x18001d8a4  jmp     short loc_18001D8C0
0x18001d8a6  xor     edx, edx
0x18001d8a8  mov     [rbp+arg_10], 0
0x18001d8b0  mov     edi, 8007000Eh
0x18001d8b5  mov     ecx, edi
0x18001d8b7  lea     r9d, [rdx+1Eh]
0x18001d8bb  call    Log_HREvent_8
0x18001d8c0  lea     rcx, [rbp+arg_10]
0x18001d8c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d8c9  mov     rbx, [rsp+30h+arg_0]
0x18001d8ce  mov     eax, edi
0x18001d8d0  mov     rsi, [rsp+30h+arg_18]
0x18001d8d5  add     rsp, 30h
0x18001d8d9  pop     r15
0x18001d8db  pop     rdi
0x18001d8dc  pop     rbp
0x18001d8dd  retn
```
