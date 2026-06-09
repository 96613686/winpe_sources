# SharingTokenDatabase::CreateToken(SharingToken *,int)

- ea: `0x1800163ec`
- end: `0x1800165b9`
- name: `?CreateToken@SharingTokenDatabase@@QEAAJPEAVSharingToken@@H@Z`
- size: `461`
- prototype: `__int64 __fastcall(SharingTokenDatabase *__hidden this, struct SharingToken *, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f740`

## callees

- `0x180002bac`
- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c758`
- `0x18000f120`
- `0x180014eb0`
- `0x180015998`
- `0x180015cfc`
- `0x180015f2c`
- `0x18001601c`
- `0x18001606c`
- `0x180016114`
- `0x18001616c`
- `0x180016340`
- `0x180016388`
- `0x1800163ec`
- `0x180017020`
- `0x180017a68`
- `0x180017ae0`

## string_xrefs

- `0x180016535`: `SharingTokenDatabase::CreateToken`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::CreateToken(SharingTokenDatabase *this, struct SharingToken *a2, int a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  int TransactedTable; // edi
  __int64 v8; // rax
  DbTable **v9; // r14
  PVOID v10; // rbx
  __int64 v11; // rax
  void **i; // rbx
  int *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // rdx
  __int64 v16; // rax
  utl::_RefCountBase *v17; // rcx
  PVOID P; // [rsp+30h] [rbp-30h] BYREF
  PVOID v20; // [rsp+38h] [rbp-28h] BYREF
  void *v21[4]; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+98h] [rbp+38h] BYREF
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  PVOID v24; // [rsp+A8h] [rbp+48h] BYREF

  v23 = a3;
  v24 = 0;
  v20 = 0;
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v21);
  if ( !v6 )
  {
    TransactedTable = -2147024809;
LABEL_15:
    v13 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
    DSLogger::LogError((DSLogger *)v13, L"SharingTokenDatabase::CreateToken", 415, L"hr=0x%x.", TransactedTable);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, TransactedTable);
    goto LABEL_16;
  }
  TransactedTable = SharingTokenDatabase::Initialize(
                      this,
                      (Common *)L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( TransactedTable < 0 )
    goto LABEL_15;
  v8 = tlx::replace<DbTransactedTableAccess<SharingToken>,&void tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(&v24);
  TransactedTable = Database::GetTransactedTableAccess<SharingToken>(this, v8);
  if ( TransactedTable < 0 )
    goto LABEL_15;
  v9 = (DbTable **)v24;
  P = 0;
  v22 = 0;
  v23 = 0;
  TransactedTable = DbTableDescription<SharingToken>::Serialize(a2, &P, &v22, &v23);
  if ( TransactedTable >= 0 )
    TransactedTable = DbTable::Insert(v9[1], (struct JET_SETCOLUMN *)P, v22, v23);
  Common::GlobalHeap::Free(P);
  if ( TransactedTable < 0 )
    goto LABEL_15;
  TransactedTable = GetSharingTargets(a2, v21);
  if ( TransactedTable < 0 )
    goto LABEL_15;
  v10 = v24;
  v11 = tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&void tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(&v20);
  TransactedTable = DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>(v10, v11);
  if ( TransactedTable < 0 )
    goto LABEL_15;
  for ( i = (void **)v21[0]; i != v21; i = (void **)*i )
  {
    TransactedTable = DbTableAccess<SharingTargetTableAdapter>::Insert(v20, i[2]);
    if ( TransactedTable < 0 )
      goto LABEL_15;
  }
  TransactedTable = DbTransactedTableAccess<SharingToken>::Commit((__int64)v24);
  if ( TransactedTable < 0 )
    goto LABEL_15;
LABEL_16:
  while ( 1 )
  {
    v14 = v21[0];
    if ( v21[0] == v21 )
      break;
    v15 = (_QWORD *)*((_QWORD *)v21[0] + 1);
    v16 = *(_QWORD *)v21[0];
    *v15 = *(_QWORD *)v21[0];
    *(_QWORD *)(v16 + 8) = v15;
    v17 = (utl::_RefCountBase *)v14[3];
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  }
  v21[2] = 0;
  if ( v20 )
    tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(v20);
  if ( v24 )
    tlx::_delete<DbTransactedTableAccess<SharingToken>>(v24);
  return (unsigned int)TransactedTable;
}

```

## disassembly

```asm
0x1800163ec  mov     [rsp-28h+arg_10], r8d
0x1800163f1  push    rbp
0x1800163f2  push    rbx
0x1800163f3  push    rsi
0x1800163f4  push    rdi
0x1800163f5  push    r14
0x1800163f7  mov     rbp, rsp
0x1800163fa  sub     rsp, 60h
0x1800163fe  mov     rsi, rcx
0x180016401  mov     [rbp+arg_18], 0
0x180016409  lea     rcx, [rbp+var_20]
0x18001640d  mov     [rbp+var_28], 0
0x180016415  mov     rbx, rdx
0x180016418  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x18001641d  test    rdx, rdx
0x180016420  jnz     short loc_18001642C
0x180016422  mov     edi, 80070057h
0x180016427  jmp     loc_18001651F
0x18001642c  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180016433  mov     rcx, rsi; this
0x180016436  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x18001643b  mov     edi, eax
0x18001643d  test    eax, eax
0x18001643f  js      loc_18001651F
0x180016445  lea     rcx, [rbp+arg_18]
0x180016449  call    ??$replace@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTransactedTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTransactedTableAccess<SharingToken>,&tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)> &)
0x18001644e  mov     rdx, rax
0x180016451  mov     rcx, rsi
0x180016454  call    ??$GetTransactedTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; Database::GetTransactedTableAccess<SharingToken>(DbTransactedTableAccess<SharingToken> * *)
0x180016459  mov     edi, eax
0x18001645b  test    eax, eax
0x18001645d  js      loc_18001651F
0x180016463  mov     r14, [rbp+arg_18]
0x180016467  lea     r9, [rbp+arg_10]
0x18001646b  lea     r8, [rbp+arg_8]
0x18001646f  mov     [rbp+P], 0
0x180016477  lea     rdx, [rbp+P]
0x18001647b  mov     [rbp+arg_8], 0
0x180016482  mov     rcx, rbx
0x180016485  mov     [rbp+arg_10], 0
0x18001648c  call    ?Serialize@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAUJET_SETCOLUMN@@AEAKAEAH@Z; DbTableDescription<SharingToken>::Serialize(SharingToken *,JET_SETCOLUMN * *,ulong &,int &)
0x180016491  mov     edi, eax
0x180016493  test    eax, eax
0x180016495  js      short loc_1800164AE
0x180016497  mov     r9d, [rbp+arg_10]; int
0x18001649b  mov     r8d, [rbp+arg_8]; unsigned int
0x18001649f  mov     rdx, [rbp+P]; struct JET_SETCOLUMN *
0x1800164a3  mov     rcx, [r14+8]; this
0x1800164a7  call    ?Insert@DbTable@@QEAAJPEAUJET_SETCOLUMN@@KH@Z; DbTable::Insert(JET_SETCOLUMN *,ulong,int)
0x1800164ac  mov     edi, eax
0x1800164ae  mov     rcx, [rbp+P]; P
0x1800164b2  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800164b7  test    edi, edi
0x1800164b9  js      short loc_18001651F
0x1800164bb  lea     rdx, [rbp+var_20]
0x1800164bf  mov     rcx, rbx
0x1800164c2  call    GetSharingTargets
0x1800164c7  mov     edi, eax
0x1800164c9  test    eax, eax
0x1800164cb  js      short loc_18001651F
0x1800164cd  mov     rbx, [rbp+arg_18]
0x1800164d1  lea     rcx, [rbp+var_28]
0x1800164d5  call    ??$replace@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)> &)
0x1800164da  mov     rdx, rax
0x1800164dd  mov     rcx, rbx
0x1800164e0  call    ??$GetDependentTableAccess@VSharingTargetTableAdapter@@@?$DbTableAccess@VSharingToken@@@@QEAAJPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; DbTableAccess<SharingToken>::GetDependentTableAccess<SharingTargetTableAdapter>(DbTableAccess<SharingTargetTableAdapter> * *)
0x1800164e5  mov     edi, eax
0x1800164e7  test    eax, eax
0x1800164e9  js      short loc_18001651F
0x1800164eb  mov     rbx, [rbp+var_20]
0x1800164ef  lea     rax, [rbp+var_20]
0x1800164f3  cmp     rbx, rax
0x1800164f6  jz      short loc_180016510
0x1800164f8  mov     rdx, [rbx+10h]
0x1800164fc  mov     rcx, [rbp+var_28]
0x180016500  call    ?Insert@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z; DbTableAccess<SharingTargetTableAdapter>::Insert(SharingTargetTableAdapter *)
0x180016505  mov     edi, eax
0x180016507  test    eax, eax
0x180016509  js      short loc_18001651F
0x18001650b  mov     rbx, [rbx]
0x18001650e  jmp     short loc_1800164EF
0x180016510  mov     rcx, [rbp+arg_18]
0x180016514  call    ?Commit@?$DbTransactedTableAccess@VSharingToken@@@@QEAAJXZ; DbTransactedTableAccess<SharingToken>::Commit(void)
0x180016519  mov     edi, eax
0x18001651b  test    eax, eax
0x18001651d  jns     short loc_18001654E
0x18001651f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180016524  lea     r9, aHr0xX; "hr=0x%x."
0x18001652b  mov     [rsp+60h+var_40], edi
0x18001652f  mov     r8d, 19Fh; unsigned int
0x180016535  lea     rdx, aSharingtokenda_5; "SharingTokenDatabase::CreateToken"
0x18001653c  mov     rcx, rax; this
0x18001653f  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180016544  mov     edx, edi; int
0x180016546  mov     rcx, rsi; this
0x180016549  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x18001654e  mov     rbx, [rbp+var_20]
0x180016552  lea     rax, [rbp+var_20]
0x180016556  cmp     rbx, rax
0x180016559  jz      short loc_180016588
0x18001655b  mov     rdx, [rbx+8]
0x18001655f  mov     rax, [rbx]
0x180016562  mov     [rdx], rax
0x180016565  mov     [rax+8], rdx
0x180016569  mov     rcx, [rbx+18h]; this
0x18001656d  test    rcx, rcx
0x180016570  jz      short loc_180016577
0x180016572  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180016577  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001657e  mov     rcx, rbx; void *
0x180016581  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016586  jmp     short loc_18001654E
0x180016588  mov     rcx, [rbp+var_28]; P
0x18001658c  mov     [rbp+var_10], 0
0x180016594  test    rcx, rcx
0x180016597  jz      short loc_18001659E
0x180016599  call    ??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)
0x18001659e  mov     rcx, [rbp+arg_18]; P
0x1800165a2  test    rcx, rcx
0x1800165a5  jz      short loc_1800165AC
0x1800165a7  call    ??$_delete@V?$DbTransactedTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTransactedTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTransactedTableAccess<SharingToken>>(DbTransactedTableAccess<SharingToken> *)
0x1800165ac  mov     eax, edi
0x1800165ae  add     rsp, 60h
0x1800165b2  pop     r14
0x1800165b4  pop     rdi
0x1800165b5  pop     rsi
0x1800165b6  pop     rbx
0x1800165b7  pop     rbp
0x1800165b8  retn
```
