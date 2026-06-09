# SharingTokenDatabase::DeleteToken(SharingToken *)

- ea: `0x18001669c`
- end: `0x180016865`
- name: `?DeleteToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(SharingTokenDatabase *__hidden this, struct SharingToken *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800120ac`

## callees

- `0x180002bac`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c758`
- `0x18000f120`
- `0x180014770`
- `0x18001577c`
- `0x180015934`
- `0x180015cfc`
- `0x180015f2c`
- `0x18001601c`
- `0x18001606c`
- `0x180016114`
- `0x18001616c`
- `0x180016340`
- `0x180016388`
- `0x1800165c0`
- `0x18001669c`
- `0x180017020`
- `0x180017a68`

## string_xrefs

- `0x1800167e1`: `SharingTokenDatabase::DeleteToken`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::DeleteToken(SharingTokenDatabase *this, struct SharingToken *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  int TransactedTable; // edi
  __int64 v7; // rax
  JET_SESID **v8; // r14
  PVOID v9; // rbx
  __int64 v10; // rax
  void **i; // rbx
  int *v12; // rax
  _QWORD *v13; // rbx
  _QWORD *v14; // rdx
  __int64 v15; // rax
  utl::_RefCountBase *v16; // rcx
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  void *v19[3]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+38h] BYREF
  PVOID v21; // [rsp+90h] [rbp+40h] BYREF
  struct _jetSeekCriteria *v22; // [rsp+98h] [rbp+48h] BYREF

  v21 = 0;
  P = 0;
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v19);
  if ( !v5 )
  {
    TransactedTable = -2147024809;
LABEL_17:
    v12 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
    DSLogger::LogError((DSLogger *)v12, L"SharingTokenDatabase::DeleteToken", 545, L"hr=0x%x.", TransactedTable);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, TransactedTable);
    goto LABEL_18;
  }
  TransactedTable = SharingTokenDatabase::Initialize(
                      this,
                      (Common *)L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( TransactedTable < 0 )
    goto LABEL_17;
  v7 = tlx::replace<DbTransactedTableAccess<SharingToken>,&void tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(&v21);
  TransactedTable = Database::GetTransactedTableAccess<SharingToken>(this, v7);
  if ( TransactedTable < 0 )
    goto LABEL_17;
  v8 = (JET_SESID **)v21;
  v22 = 0;
  v20 = 0;
  TransactedTable = DbTableDescription<SharingToken>::GetSCBasedOnPK(a2, &v22, &v20);
  if ( TransactedTable >= 0 )
    TransactedTable = DbTable::Delete(v8[1], v22, v20);
  DbTableDescription<SharingToken>::ReleaseSC(&v22, v20);
  if ( TransactedTable == 1 )
  {
    TransactedTable = -1055719418;
    goto LABEL_17;
  }
  if ( TransactedTable < 0 )
    goto LABEL_17;
  TransactedTable = GetSharingTargets(a2, v19);
  if ( TransactedTable < 0 )
    goto LABEL_17;
  v9 = v21;
  v10 = tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&void tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(&P);
  TransactedTable = DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>(v9, v10);
  if ( TransactedTable < 0 )
    goto LABEL_17;
  for ( i = (void **)v19[0]; i != v19; i = (void **)*i )
  {
    TransactedTable = DbTableAccess<SharingTargetTableAdapter>::Delete(P, i[2]);
    if ( TransactedTable < 0 )
      goto LABEL_17;
  }
  TransactedTable = DbTransactedTableAccess<SharingToken>::Commit((__int64)v21);
  if ( TransactedTable < 0 )
    goto LABEL_17;
LABEL_18:
  while ( 1 )
  {
    v13 = v19[0];
    if ( v19[0] == v19 )
      break;
    v14 = (_QWORD *)*((_QWORD *)v19[0] + 1);
    v15 = *(_QWORD *)v19[0];
    *v14 = *(_QWORD *)v19[0];
    *(_QWORD *)(v15 + 8) = v14;
    v16 = (utl::_RefCountBase *)v13[3];
    if ( v16 )
      utl::_RefCountBase::_DecStrong(v16);
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
  }
  v19[2] = 0;
  if ( P )
    tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(P);
  if ( v21 )
    tlx::_delete<DbTransactedTableAccess<SharingToken>>(v21);
  return (unsigned int)TransactedTable;
}

```

## disassembly

```asm
0x18001669c  push    rbp
0x18001669e  push    rbx
0x18001669f  push    rsi
0x1800166a0  push    rdi
0x1800166a1  push    r14
0x1800166a3  mov     rbp, rsp
0x1800166a6  sub     rsp, 50h
0x1800166aa  mov     rsi, rcx
0x1800166ad  mov     [rbp+arg_10], 0
0x1800166b5  lea     rcx, [rbp+var_18]
0x1800166b9  mov     [rbp+P], 0
0x1800166c1  mov     rbx, rdx
0x1800166c4  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x1800166c9  test    rdx, rdx
0x1800166cc  jnz     short loc_1800166D8
0x1800166ce  mov     edi, 80070057h
0x1800166d3  jmp     loc_1800167CB
0x1800166d8  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x1800166df  mov     rcx, rsi; this
0x1800166e2  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x1800166e7  mov     edi, eax
0x1800166e9  test    eax, eax
0x1800166eb  js      loc_1800167CB
0x1800166f1  lea     rcx, [rbp+arg_10]
0x1800166f5  call    ??$replace@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)> &)
0x1800166fa  mov     rdx, rax
0x1800166fd  mov     rcx, rsi
0x180016700  call    ??$GetTransactedTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; Database::GetTransactedTableAccess<SharingToken>(DbTransactedTableAccess<SharingToken> * *)
0x180016705  mov     edi, eax
0x180016707  test    eax, eax
0x180016709  js      loc_1800167CB
0x18001670f  mov     r14, [rbp+arg_10]
0x180016713  lea     r8, [rbp+arg_8]
0x180016717  lea     rdx, [rbp+arg_18]
0x18001671b  mov     [rbp+arg_18], 0
0x180016723  mov     rcx, rbx
0x180016726  mov     [rbp+arg_8], 0
0x18001672d  call    ?GetSCBasedOnPK@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAU_jetSeekCriteria@@AEAK@Z; DbTableDescription<SharingToken>::GetSCBasedOnPK(SharingToken *,_jetSeekCriteria * *,ulong &)
0x180016732  mov     edi, eax
0x180016734  test    eax, eax
0x180016736  js      short loc_18001674B
0x180016738  mov     r8d, [rbp+arg_8]; unsigned int
0x18001673c  mov     rdx, [rbp+arg_18]; struct _jetSeekCriteria *
0x180016740  mov     rcx, [r14+8]; this
0x180016744  call    ?Delete@DbTable@@QEAAJPEAU_jetSeekCriteria@@KK@Z; DbTable::Delete(_jetSeekCriteria *,ulong,ulong)
0x180016749  mov     edi, eax
0x18001674b  mov     edx, [rbp+arg_8]
0x18001674e  lea     rcx, [rbp+arg_18]
0x180016752  call    ?ReleaseSC@?$DbTableDescription@VSharingToken@@@@SAXPEAPEAU_jetSeekCriteria@@K@Z; DbTableDescription<SharingToken>::ReleaseSC(_jetSeekCriteria * *,ulong)
0x180016757  cmp     edi, 1
0x18001675a  jnz     short loc_180016763
0x18001675c  mov     edi, 0C1130006h
0x180016761  jmp     short loc_1800167CB
0x180016763  test    edi, edi
0x180016765  js      short loc_1800167CB
0x180016767  lea     rdx, [rbp+var_18]
0x18001676b  mov     rcx, rbx
0x18001676e  call    GetSharingTargets
0x180016773  mov     edi, eax
0x180016775  test    eax, eax
0x180016777  js      short loc_1800167CB
0x180016779  mov     rbx, [rbp+arg_10]
0x18001677d  lea     rcx, [rbp+P]
0x180016781  call    ??$replace@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)> &)
0x180016786  mov     rdx, rax
0x180016789  mov     rcx, rbx
0x18001678c  call    ??$GetDependentTableAccess@VSharingTargetTableAdapter@@@?$DbTableAccess@VSharingToken@@@@QEAAJPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>(DbTableAccess<SharingTargetTableAdapter> * *)
0x180016791  mov     edi, eax
0x180016793  test    eax, eax
0x180016795  js      short loc_1800167CB
0x180016797  mov     rbx, [rbp+var_18]
0x18001679b  lea     rax, [rbp+var_18]
0x18001679f  cmp     rbx, rax
0x1800167a2  jz      short loc_1800167BC
0x1800167a4  mov     rdx, [rbx+10h]
0x1800167a8  mov     rcx, [rbp+P]
0x1800167ac  call    ?Delete@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z; DbTableAccess<SharingTargetTableAdapter>::Delete(SharingTargetTableAdapter *)
0x1800167b1  mov     edi, eax
0x1800167b3  test    eax, eax
0x1800167b5  js      short loc_1800167CB
0x1800167b7  mov     rbx, [rbx]
0x1800167ba  jmp     short loc_18001679B
0x1800167bc  mov     rcx, [rbp+arg_10]
0x1800167c0  call    ?Commit@?$DbTransactedTableAccess@VSharingToken@@@@QEAAJXZ; DbTransactedTableAccess<SharingToken>::Commit(void)
0x1800167c5  mov     edi, eax
0x1800167c7  test    eax, eax
0x1800167c9  jns     short loc_1800167FA
0x1800167cb  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800167d0  lea     r9, aHr0xX; "hr=0x%x."
0x1800167d7  mov     [rsp+50h+var_30], edi
0x1800167db  mov     r8d, 221h; unsigned int
0x1800167e1  lea     rdx, aSharingtokenda_7; "SharingTokenDatabase::DeleteToken"
0x1800167e8  mov     rcx, rax; this
0x1800167eb  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800167f0  mov     edx, edi; int
0x1800167f2  mov     rcx, rsi; this
0x1800167f5  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x1800167fa  mov     rbx, [rbp+var_18]
0x1800167fe  lea     rax, [rbp+var_18]
0x180016802  cmp     rbx, rax
0x180016805  jz      short loc_180016834
0x180016807  mov     rdx, [rbx+8]
0x18001680b  mov     rax, [rbx]
0x18001680e  mov     [rdx], rax
0x180016811  mov     [rax+8], rdx
0x180016815  mov     rcx, [rbx+18h]; this
0x180016819  test    rcx, rcx
0x18001681c  jz      short loc_180016823
0x18001681e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180016823  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001682a  mov     rcx, rbx; void *
0x18001682d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016832  jmp     short loc_1800167FA
0x180016834  mov     rcx, [rbp+P]; P
0x180016838  mov     [rbp+var_8], 0
0x180016840  test    rcx, rcx
0x180016843  jz      short loc_18001684A
0x180016845  call    ??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)
0x18001684a  mov     rcx, [rbp+arg_10]; P
0x18001684e  test    rcx, rcx
0x180016851  jz      short loc_180016858
0x180016853  call    ??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)
0x180016858  mov     eax, edi
0x18001685a  add     rsp, 50h
0x18001685e  pop     r14
0x180016860  pop     rdi
0x180016861  pop     rsi
0x180016862  pop     rbx
0x180016863  pop     rbp
0x180016864  retn
```
