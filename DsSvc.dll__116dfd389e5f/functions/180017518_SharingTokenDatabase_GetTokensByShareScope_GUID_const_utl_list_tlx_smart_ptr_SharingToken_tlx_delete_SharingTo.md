# SharingTokenDatabase::GetTokensByShareScope(_GUID const &,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)

- ea: `0x180017518`
- end: `0x1800177a5`
- name: `?GetTokensByShareScope@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(SharingTokenDatabase *this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012194`

## callees

- `0x180002bac`
- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c758`
- `0x18000f120`
- `0x18000f254`
- `0x18000f4f8`
- `0x180015a64`
- `0x180015da4`
- `0x180015ff4`
- `0x18001601c`
- `0x1800160bc`
- `0x1800160e8`
- `0x180016114`
- `0x180016198`
- `0x180016340`
- `0x180016a94`
- `0x180016bf0`
- `0x180016d68`
- `0x180017140`
- `0x180017518`
- `0x180017a68`
- `0x180017b5c`
- `0x180017f30`

## string_xrefs

- `0x1800176cf`: `SharingTokenDatabase::GetTokensByShareScope`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::GetTokensByShareScope(SharingTokenDatabase *this, __int64 a2, __int64 a3)
{
  int SCBasedOnGuid; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // edx
  int Iterator; // eax
  DbTableIterator *v13; // rbx
  int Next; // eax
  void **v15; // rbx
  __int64 v16; // rcx
  int *v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // rdx
  __int64 v20; // rax
  utl::_RefCountBase *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-29h]
  PVOID P; // [rsp+30h] [rbp-19h] BYREF
  PVOID v25; // [rsp+38h] [rbp-11h] BYREF
  PVOID v26; // [rsp+40h] [rbp-9h] BYREF
  PVOID v27; // [rsp+48h] [rbp-1h] BYREF
  utl::_RefCountBase *v28[2]; // [rsp+50h] [rbp+7h] BYREF
  utl::_RefCountBase *v29[2]; // [rsp+60h] [rbp+17h] BYREF
  void *v30[4]; // [rsp+70h] [rbp+27h] BYREF
  int v31; // [rsp+C8h] [rbp+7Fh] BYREF

  v27 = 0;
  v26 = 0;
  v25 = 0;
  *(_OWORD *)v29 = 0;
  *(_OWORD *)v28 = 0;
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v30);
  P = 0;
  v31 = 0;
  SCBasedOnGuid = SharingTokenDatabase::Initialize(
                    this,
                    (Common *)L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( SCBasedOnGuid < 0 )
    goto LABEL_19;
  v7 = tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(&P);
  SCBasedOnGuid = GetSCBasedOnGuid(a2, v7, &v31);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_19;
  v8 = tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&void tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(&v27);
  SCBasedOnGuid = Database::GetTableAccess<SharingTargetTableAdapter>(this, v8);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_19;
  v9 = (int)v27;
  v10 = tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&void tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(&v26);
  Iterator = DbTableAccess<SharingTargetTableAdapter>::GetIterator(v9, v11, 2, (_DWORD)P, v31, v10);
  SCBasedOnGuid = Iterator;
  if ( Iterator == 1 )
  {
    SCBasedOnGuid = -1055719418;
    goto LABEL_19;
  }
  if ( Iterator < 0 )
  {
LABEL_19:
    utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(a3);
    v17 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v16);
    LODWORD(v23) = SCBasedOnGuid;
    DSLogger::LogError((DSLogger *)v17, L"SharingTokenDatabase::GetTokensByShareScope", 961, L"hr=0x%x.", v23);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, SCBasedOnGuid);
    goto LABEL_20;
  }
  while ( 1 )
  {
    v13 = (DbTableIterator *)v26;
    tlx::replace<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)>(&v25);
    Next = DbObjectIterator<SharingTargetTableAdapter>::GetNext(v13);
    SCBasedOnGuid = Next;
    if ( Next == 1 )
      break;
    if ( Next < 0 )
      goto LABEL_19;
    if ( !v25 )
    {
      SCBasedOnGuid = -2147024809;
      goto LABEL_19;
    }
    v25 = 0;
    if ( !(unsigned __int8)tlx::smart_xxx<SharingTargetTableAdapter *,void (*)(SharingTargetTableAdapter *),&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),0,utl::allocator<int>>::reset(v29)
      || !(unsigned __int8)utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(
                             v30,
                             v29) )
    {
LABEL_11:
      SCBasedOnGuid = -2147024882;
      goto LABEL_19;
    }
  }
  v15 = (void **)v30[0];
  SCBasedOnGuid = 0;
  while ( v15 != v30 )
  {
    SCBasedOnGuid = SharingTokenDatabase::GetToken(this);
    if ( SCBasedOnGuid < 0 )
      goto LABEL_19;
    if ( !(unsigned __int8)utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(
                             a3,
                             v28) )
      goto LABEL_11;
    v15 = (void **)*v15;
  }
LABEL_20:
  ReleaseSC(P, &v31);
  if ( P )
    Common::GlobalHeap::Free(P);
  while ( 1 )
  {
    v18 = v30[0];
    if ( v30[0] == v30 )
      break;
    v19 = (_QWORD *)*((_QWORD *)v30[0] + 1);
    v20 = *(_QWORD *)v30[0];
    *v19 = *(_QWORD *)v30[0];
    *(_QWORD *)(v20 + 8) = v19;
    v21 = (utl::_RefCountBase *)v18[3];
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  }
  v30[2] = 0;
  if ( v28[1] )
    utl::_RefCountBase::_DecStrong(v28[1]);
  if ( v29[1] )
    utl::_RefCountBase::_DecStrong(v29[1]);
  if ( v25 )
    tlx::_delete<SharingTargetTableAdapter>(v25);
  if ( v26 )
    tlx::_delete<DbObjectIterator<SharingToken>>(v26);
  if ( v27 )
    tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(v27);
  return (unsigned int)SCBasedOnGuid;
}

```

## disassembly

```asm
0x180017518  mov     [rsp-8+arg_0], rbx
0x18001751d  mov     [rsp-8+arg_8], rsi
0x180017522  push    rbp
0x180017523  push    rdi
0x180017524  push    r14
0x180017526  lea     rbp, [rsp-47h]
0x18001752b  sub     rsp, 90h
0x180017532  mov     rsi, rcx
0x180017535  mov     [rbp+57h+var_58], 0
0x18001753d  xorps   xmm0, xmm0
0x180017540  mov     [rbp+57h+var_60], 0
0x180017548  xorps   xmm1, xmm1
0x18001754b  mov     [rbp+57h+var_68], 0
0x180017553  lea     rcx, [rbp+57h+var_30]
0x180017557  mov     r14, r8
0x18001755a  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18001755f  mov     rbx, rdx
0x180017562  movdqu  xmmword ptr [rbp+57h+var_50], xmm1
0x180017567  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x18001756c  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180017573  mov     [rbp+57h+P], 0
0x18001757b  mov     rcx, rsi; this
0x18001757e  mov     [rbp+57h+arg_18], 0
0x180017585  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x18001758a  mov     edi, eax
0x18001758c  test    eax, eax
0x18001758e  js      loc_1800176B1
0x180017594  lea     rcx, [rbp+57h+P]
0x180017598  call    ??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)
0x18001759d  mov     rdx, rax
0x1800175a0  lea     r8, [rbp+57h+arg_18]
0x1800175a4  mov     rcx, rbx
0x1800175a7  call    GetSCBasedOnGuid
0x1800175ac  mov     edi, eax
0x1800175ae  test    eax, eax
0x1800175b0  js      loc_1800176B1
0x1800175b6  lea     rcx, [rbp+57h+var_58]
0x1800175ba  call    ??$replace@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbTableAccess<SharingTargetTableAdapter>,&tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)> &)
0x1800175bf  mov     rdx, rax
0x1800175c2  mov     rcx, rsi
0x1800175c5  call    ??$GetTableAccess@VSharingTargetTableAdapter@@@Database@@QEAAJPEAPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; Database::GetTableAccess<SharingTargetTableAdapter>(DbTableAccess<SharingTargetTableAdapter> * *)
0x1800175ca  mov     edi, eax
0x1800175cc  test    eax, eax
0x1800175ce  js      loc_1800176B1
0x1800175d4  mov     rbx, [rbp+57h+var_58]
0x1800175d8  lea     rcx, [rbp+57h+var_60]
0x1800175dc  call    ??$replace@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)> &)
0x1800175e1  mov     r9, [rbp+57h+P]
0x1800175e5  mov     r8d, 2
0x1800175eb  mov     [rsp+0A0h+var_78], rax
0x1800175f0  mov     rcx, rbx
0x1800175f3  mov     eax, [rbp+57h+arg_18]
0x1800175f6  mov     dword ptr [rsp+0A0h+var_80], eax
0x1800175fa  call    ?GetIterator@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJKHPEAU_jetSeekCriteria@@KPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@@Z; DbTableAccess<SharingTargetTableAdapter>::GetIterator(ulong,int,_jetSeekCriteria *,ulong,DbObjectIterator<SharingTargetTableAdapter> * *)
0x1800175ff  mov     edi, eax
0x180017601  cmp     eax, 1
0x180017604  jz      loc_1800176AC
0x18001760a  test    eax, eax
0x18001760c  js      loc_1800176B1
0x180017612  mov     rbx, [rbp+57h+var_60]
0x180017616  lea     rcx, [rbp+57h+var_68]
0x18001761a  call    ??$replace@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVSharingTargetTableAdapter@@AEAV?$auto_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)>(tlx::auto_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)> &)
0x18001761f  mov     rdx, rax
0x180017622  mov     rcx, rbx; this
0x180017625  call    ?GetNext@?$DbObjectIterator@VSharingTargetTableAdapter@@@@QEAAJPEAPEAVSharingTargetTableAdapter@@@Z; DbObjectIterator<SharingTargetTableAdapter>::GetNext(SharingTargetTableAdapter * *)
0x18001762a  mov     edi, eax
0x18001762c  cmp     eax, 1
0x18001762f  jz      short loc_180017672
0x180017631  test    eax, eax
0x180017633  js      short loc_1800176B1
0x180017635  mov     rdx, [rbp+57h+var_68]
0x180017639  test    rdx, rdx
0x18001763c  jz      short loc_18001766B
0x18001763e  lea     rcx, [rbp+57h+var_40]
0x180017642  mov     [rbp+57h+var_68], 0
0x18001764a  call    ?reset@?$smart_xxx@PEAVSharingTargetTableAdapter@@P6AXPEAV1@@Z$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVSharingTargetTableAdapter@@@Z; tlx::smart_xxx<SharingTargetTableAdapter *,void (*)(SharingTargetTableAdapter *),&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),0,utl::allocator<int>>::reset(SharingTargetTableAdapter *)
0x18001764f  test    al, al
0x180017651  jz      short loc_180017664
0x180017653  lea     rdx, [rbp+57h+var_40]
0x180017657  lea     rcx, [rbp+57h+var_30]
0x18001765b  call    ?push_back@?$list@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA_NAEBV?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>> const &)
0x180017660  test    al, al
0x180017662  jnz     short loc_180017612
0x180017664  mov     edi, 8007000Eh
0x180017669  jmp     short loc_1800176B1
0x18001766b  mov     edi, 80070057h
0x180017670  jmp     short loc_1800176B1
0x180017672  mov     rbx, [rbp+57h+var_30]
0x180017676  xor     edi, edi
0x180017678  lea     rax, [rbp+57h+var_30]
0x18001767c  cmp     rbx, rax
0x18001767f  jz      short loc_1800176E8
0x180017681  mov     rdx, [rbx+10h]
0x180017685  lea     r8, [rbp+57h+var_50]
0x180017689  mov     rcx, rsi; this
0x18001768c  call    ?GetToken@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharingTokenDatabase::GetToken(_GUID const &,tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)
0x180017691  mov     edi, eax
0x180017693  test    eax, eax
0x180017695  js      short loc_1800176B1
0x180017697  lea     rdx, [rbp+57h+var_50]
0x18001769b  mov     rcx, r14
0x18001769e  call    ?push_back@?$list@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA_NAEBV?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>> const &)
0x1800176a3  test    al, al
0x1800176a5  jz      short loc_180017664
0x1800176a7  mov     rbx, [rbx]
0x1800176aa  jmp     short loc_180017678
0x1800176ac  mov     edi, 0C1130006h
0x1800176b1  mov     rcx, r14
0x1800176b4  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x1800176b9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800176be  lea     r9, aHr0xX; "hr=0x%x."
0x1800176c5  mov     dword ptr [rsp+0A0h+var_80], edi
0x1800176c9  mov     r8d, 3C1h; unsigned int
0x1800176cf  lea     rdx, aSharingtokenda_6; "SharingTokenDatabase::GetTokensByShareS"...
0x1800176d6  mov     rcx, rax; this
0x1800176d9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800176de  mov     edx, edi; int
0x1800176e0  mov     rcx, rsi; this
0x1800176e3  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x1800176e8  mov     rcx, [rbp+57h+P]
0x1800176ec  lea     rdx, [rbp+57h+arg_18]
0x1800176f0  call    ReleaseSC
0x1800176f5  mov     rcx, [rbp+57h+P]; P
0x1800176f9  test    rcx, rcx
0x1800176fc  jz      short loc_180017703
0x1800176fe  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180017703  mov     rbx, [rbp+57h+var_30]
0x180017707  lea     rax, [rbp+57h+var_30]
0x18001770b  cmp     rbx, rax
0x18001770e  jz      short loc_18001773D
0x180017710  mov     rdx, [rbx+8]
0x180017714  mov     rax, [rbx]
0x180017717  mov     [rdx], rax
0x18001771a  mov     [rax+8], rdx
0x18001771e  mov     rcx, [rbx+18h]; this
0x180017722  test    rcx, rcx
0x180017725  jz      short loc_18001772C
0x180017727  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18001772c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017733  mov     rcx, rbx; void *
0x180017736  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001773b  jmp     short loc_180017703
0x18001773d  mov     rcx, [rbp+57h+var_50+8]; this
0x180017741  mov     [rbp+57h+var_20], 0
0x180017749  test    rcx, rcx
0x18001774c  jz      short loc_180017753
0x18001774e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180017753  mov     rcx, [rbp+57h+var_40+8]; this
0x180017757  test    rcx, rcx
0x18001775a  jz      short loc_180017761
0x18001775c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180017761  mov     rcx, [rbp+57h+var_68]; P
0x180017765  test    rcx, rcx
0x180017768  jz      short loc_18001776F
0x18001776a  call    ??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAVSharingTargetTableAdapter@@@Z; tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)
0x18001776f  mov     rcx, [rbp+57h+var_60]; P
0x180017773  test    rcx, rcx
0x180017776  jz      short loc_18001777D
0x180017778  call    ??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z; tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)
0x18001777d  mov     rcx, [rbp+57h+var_58]; P
0x180017781  test    rcx, rcx
0x180017784  jz      short loc_18001778B
0x180017786  call    ??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z; tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)
0x18001778b  lea     r11, [rsp+0A0h+var_10]
0x180017793  mov     eax, edi
0x180017795  mov     rbx, [r11+20h]
0x180017799  mov     rsi, [r11+28h]
0x18001779d  mov     rsp, r11
0x1800177a0  pop     r14
0x1800177a2  pop     rdi
0x1800177a3  pop     rbp
0x1800177a4  retn
```
