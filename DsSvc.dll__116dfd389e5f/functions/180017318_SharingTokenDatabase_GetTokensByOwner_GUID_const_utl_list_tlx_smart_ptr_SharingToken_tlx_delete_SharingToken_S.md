# SharingTokenDatabase::GetTokensByOwner(_GUID const &,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)

- ea: `0x180017318`
- end: `0x18001750f`
- name: `?GetTokensByOwner@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(SharingTokenDatabase *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800134f4`

## callees

- `0x180006f78`
- `0x18000be3c`
- `0x18000bf80`
- `0x18000c65c`
- `0x18000f120`
- `0x18000f254`
- `0x18000f4f8`
- `0x18000f5e4`
- `0x180015e68`
- `0x180015ff4`
- `0x180016044`
- `0x1800160bc`
- `0x1800160e8`
- `0x180016140`
- `0x1800161c4`
- `0x180016340`
- `0x180016b40`
- `0x180016c60`
- `0x180016d68`
- `0x180016dec`
- `0x180017318`
- `0x180017a68`
- `0x180017b5c`

## string_xrefs

- `0x18001748c`: `SharingTokenDatabase::GetTokensByOwner`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::GetTokensByOwner(SharingTokenDatabase *this, __int64 a2, __int64 a3)
{
  int SCBasedOnGuid; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  int Iterator; // eax
  DbTableIterator *v12; // rbx
  int Next; // eax
  __int64 v14; // rcx
  int *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-40h]
  PVOID P; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  PVOID v20; // [rsp+40h] [rbp-20h] BYREF
  PVOID v21; // [rsp+48h] [rbp-18h] BYREF
  utl::_RefCountBase *v22[2]; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+98h] [rbp+38h] BYREF

  v21 = 0;
  v20 = 0;
  v19 = 0;
  *(_OWORD *)v22 = 0;
  P = 0;
  v23 = 0;
  SCBasedOnGuid = SharingTokenDatabase::Initialize(
                    this,
                    (Common *)L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\");
  if ( SCBasedOnGuid < 0 )
    goto LABEL_16;
  v7 = tlx::replace<_jetSeekCriteria,&void tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(&P);
  SCBasedOnGuid = GetSCBasedOnGuid(a2, v7, &v23);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_16;
  v8 = tlx::replace<DbTableAccess<SharingToken>,&void tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(&v21);
  SCBasedOnGuid = Database::GetTableAccess<SharingToken>(this, v8);
  if ( SCBasedOnGuid < 0 )
    goto LABEL_16;
  v9 = (int)v21;
  v10 = tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&void tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(&v20);
  Iterator = DbTableAccess<SharingToken>::GetIterator(v9, 1, 3, (_DWORD)P, v23, v10);
  SCBasedOnGuid = Iterator;
  if ( Iterator == 1 )
  {
    SCBasedOnGuid = -1055719418;
    goto LABEL_16;
  }
  if ( Iterator < 0 )
  {
LABEL_16:
    utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(a3);
    v15 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v14);
    LODWORD(v17) = SCBasedOnGuid;
    DSLogger::LogError((DSLogger *)v15, L"SharingTokenDatabase::GetTokensByOwner", 787, L"hr=0x%x.", v17);
    SharingTokenDatabase::CheckAndSetRecoveryState(this, SCBasedOnGuid);
    goto LABEL_17;
  }
  while ( 1 )
  {
    v12 = (DbTableIterator *)v20;
    tlx::replace<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *)>(&v19);
    Next = DbObjectIterator<SharingToken>::GetNext(v12);
    SCBasedOnGuid = Next;
    if ( Next == 1 )
      break;
    if ( Next < 0 )
      goto LABEL_16;
    if ( !v19 )
    {
      SCBasedOnGuid = -2147024809;
      goto LABEL_16;
    }
    v19 = 0;
    if ( (unsigned __int8)tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(v22) )
    {
      SCBasedOnGuid = SharingTokenDatabase::GetShareScope((__int64)this, v22);
      if ( SCBasedOnGuid < 0 )
        goto LABEL_16;
      if ( (unsigned __int8)utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&void tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(
                              a3,
                              v22) )
        continue;
    }
    SCBasedOnGuid = -2147024882;
    goto LABEL_16;
  }
  SCBasedOnGuid = 0;
LABEL_17:
  ReleaseSC(P, &v23);
  if ( P )
    Common::GlobalHeap::Free(P);
  if ( v22[1] )
    utl::_RefCountBase::_DecStrong(v22[1]);
  if ( v19 )
    tlx::_delete<DbEnumFilter>(v19);
  if ( v20 )
    tlx::_delete<DbObjectIterator<SharingToken>>(v20);
  if ( v21 )
    tlx::_delete<DbTableAccess<SharingToken>>(v21);
  return (unsigned int)SCBasedOnGuid;
}

```

## disassembly

```asm
0x180017318  mov     [rsp-18h+arg_0], rbx
0x18001731d  mov     [rsp-18h+arg_8], rsi
0x180017322  push    rbp
0x180017323  push    rdi
0x180017324  push    r14
0x180017326  mov     rbp, rsp
0x180017329  sub     rsp, 60h
0x18001732d  mov     rsi, rdx
0x180017330  mov     [rbp+var_18], 0
0x180017338  xorps   xmm0, xmm0
0x18001733b  mov     [rbp+var_20], 0
0x180017343  lea     rdx, pszPathIn; "\\Data\\Users\\System\\AppData\\Local\\"...
0x18001734a  mov     [rbp+var_28], 0
0x180017352  movdqu  xmmword ptr [rbp+var_10], xmm0
0x180017357  mov     r14, r8
0x18001735a  mov     [rbp+P], 0
0x180017362  mov     rdi, rcx
0x180017365  mov     [rbp+arg_18], 0
0x18001736c  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x180017371  mov     ebx, eax
0x180017373  test    eax, eax
0x180017375  js      loc_18001746E
0x18001737b  lea     rcx, [rbp+P]
0x18001737f  call    ??$replace@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_jetSeekCriteria@@AEAV?$auto_ptr@U_jetSeekCriteria@@$1??$_delete@U_jetSeekCriteria@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)>(tlx::auto_ptr<_jetSeekCriteria,&tlx::_delete<_jetSeekCriteria>(_jetSeekCriteria *)> &)
0x180017384  mov     rdx, rax
0x180017387  lea     r8, [rbp+arg_18]
0x18001738b  mov     rcx, rsi
0x18001738e  call    GetSCBasedOnGuid
0x180017393  mov     ebx, eax
0x180017395  test    eax, eax
0x180017397  js      loc_18001746E
0x18001739d  lea     rcx, [rbp+var_18]
0x1800173a1  call    ??$replace@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbTableAccess@VSharingToken@@@@AEAV?$auto_ptr@V?$DbTableAccess@VSharingToken@@@@$1??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)>(tlx::auto_ptr<DbTableAccess<SharingToken>,&tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)> &)
0x1800173a6  mov     rdx, rax
0x1800173a9  mov     rcx, rdi
0x1800173ac  call    ??$GetTableAccess@VSharingToken@@@Database@@QEAAJPEAPEAV?$DbTableAccess@VSharingToken@@@@@Z; Database::GetTableAccess<SharingToken>(DbTableAccess<SharingToken> * *)
0x1800173b1  mov     ebx, eax
0x1800173b3  test    eax, eax
0x1800173b5  js      loc_18001746E
0x1800173bb  mov     rbx, [rbp+var_18]
0x1800173bf  lea     rcx, [rbp+var_20]
0x1800173c3  call    ??$replace@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAV?$DbObjectIterator@VSharingTargetTableAdapter@@@@AEAV?$auto_ptr@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@$1??$_delete@V?$DbObjectIterator@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)>(tlx::auto_ptr<DbObjectIterator<SharingTargetTableAdapter>,&tlx::_delete<DbObjectIterator<SharingTargetTableAdapter>>(DbObjectIterator<SharingTargetTableAdapter> *)> &)
0x1800173c8  mov     r9, [rbp+P]
0x1800173cc  mov     edx, 1
0x1800173d1  mov     [rsp+60h+var_38], rax
0x1800173d6  mov     rcx, rbx
0x1800173d9  mov     eax, [rbp+arg_18]
0x1800173dc  mov     dword ptr [rsp+60h+var_40], eax
0x1800173e0  lea     r8d, [rdx+2]
0x1800173e4  call    ?GetIterator@?$DbTableAccess@VSharingToken@@@@QEAAJKHPEAU_jetSeekCriteria@@KPEAPEAV?$DbObjectIterator@VSharingToken@@@@@Z; DbTableAccess<SharingToken>::GetIterator(ulong,int,_jetSeekCriteria *,ulong,DbObjectIterator<SharingToken> * *)
0x1800173e9  mov     ebx, eax
0x1800173eb  cmp     eax, 1
0x1800173ee  jz      short loc_180017469
0x1800173f0  test    eax, eax
0x1800173f2  js      short loc_18001746E
0x1800173f4  mov     rbx, [rbp+var_20]
0x1800173f8  lea     rcx, [rbp+var_28]
0x1800173fc  call    ??$replace@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@tlx@@YAPEAPEAVSharingToken@@AEAV?$auto_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@Z@0@@Z; tlx::replace<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)>(tlx::auto_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *)> &)
0x180017401  mov     rdx, rax
0x180017404  mov     rcx, rbx; this
0x180017407  call    ?GetNext@?$DbObjectIterator@VSharingToken@@@@QEAAJPEAPEAVSharingToken@@@Z; DbObjectIterator<SharingToken>::GetNext(SharingToken * *)
0x18001740c  mov     ebx, eax
0x18001740e  cmp     eax, 1
0x180017411  jz      short loc_180017465
0x180017413  test    eax, eax
0x180017415  js      short loc_18001746E
0x180017417  mov     rdx, [rbp+var_28]
0x18001741b  test    rdx, rdx
0x18001741e  jz      short loc_18001745E
0x180017420  lea     rcx, [rbp+var_10]
0x180017424  mov     [rbp+var_28], 0
0x18001742c  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAA_NPEAVSharingToken@@@Z; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(SharingToken *)
0x180017431  test    al, al
0x180017433  jz      short loc_180017457
0x180017435  lea     rdx, [rbp+var_10]
0x180017439  mov     rcx, rdi
0x18001743c  call    ?GetShareScope@SharingTokenDatabase@@AEAAJAEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharingTokenDatabase::GetShareScope(tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)
0x180017441  mov     ebx, eax
0x180017443  test    eax, eax
0x180017445  js      short loc_18001746E
0x180017447  lea     rdx, [rbp+var_10]
0x18001744b  mov     rcx, r14
0x18001744e  call    ?push_back@?$list@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA_NAEBV?$smart_ptr@VSharingTargetTableAdapter@@$1??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; utl::list<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>>>>::push_back(tlx::smart_ptr<SharingTargetTableAdapter,&tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *),utl::allocator<int>> const &)
0x180017453  test    al, al
0x180017455  jnz     short loc_1800173F4
0x180017457  mov     ebx, 8007000Eh
0x18001745c  jmp     short loc_18001746E
0x18001745e  mov     ebx, 80070057h
0x180017463  jmp     short loc_18001746E
0x180017465  xor     ebx, ebx
0x180017467  jmp     short loc_1800174A5
0x180017469  mov     ebx, 0C1130006h
0x18001746e  mov     rcx, r14
0x180017471  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x180017476  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001747b  lea     r9, aHr0xX; "hr=0x%x."
0x180017482  mov     dword ptr [rsp+60h+var_40], ebx
0x180017486  mov     r8d, 313h; unsigned int
0x18001748c  lea     rdx, aSharingtokenda_9; "SharingTokenDatabase::GetTokensByOwner"
0x180017493  mov     rcx, rax; this
0x180017496  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001749b  mov     edx, ebx; int
0x18001749d  mov     rcx, rdi; this
0x1800174a0  call    ?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z; SharingTokenDatabase::CheckAndSetRecoveryState(long)
0x1800174a5  mov     rcx, [rbp+P]
0x1800174a9  lea     rdx, [rbp+arg_18]
0x1800174ad  call    ReleaseSC
0x1800174b2  mov     rcx, [rbp+P]; P
0x1800174b6  test    rcx, rcx
0x1800174b9  jz      short loc_1800174C0
0x1800174bb  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800174c0  mov     rcx, [rbp+var_10+8]; this
0x1800174c4  test    rcx, rcx
0x1800174c7  jz      short loc_1800174CE
0x1800174c9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800174ce  mov     rcx, [rbp+var_28]
0x1800174d2  test    rcx, rcx
0x1800174d5  jz      short loc_1800174DC
0x1800174d7  call    ??$_delete@VDbEnumFilter@@@tlx@@YAXPEAVDbEnumFilter@@@Z; tlx::_delete<DbEnumFilter>(DbEnumFilter *)
0x1800174dc  mov     rcx, [rbp+var_20]; P
0x1800174e0  test    rcx, rcx
0x1800174e3  jz      short loc_1800174EA
0x1800174e5  call    ??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z; tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)
0x1800174ea  mov     rcx, [rbp+var_18]; P
0x1800174ee  test    rcx, rcx
0x1800174f1  jz      short loc_1800174F8
0x1800174f3  call    ??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingToken@@@@@Z; tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)
0x1800174f8  lea     r11, [rsp+60h+var_s0]
0x1800174fd  mov     eax, ebx
0x1800174ff  mov     rbx, [r11+20h]
0x180017503  mov     rsi, [r11+28h]
0x180017507  mov     rsp, r11
0x18001750a  pop     r14
0x18001750c  pop     rdi
0x18001750d  pop     rbp
0x18001750e  retn
```
