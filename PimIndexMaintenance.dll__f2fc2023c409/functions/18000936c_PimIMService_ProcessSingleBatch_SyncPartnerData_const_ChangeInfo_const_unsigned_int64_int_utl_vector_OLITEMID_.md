# PimIMService::ProcessSingleBatch(SyncPartnerData const &,ChangeInfo const *,unsigned __int64,int &,utl::vector<OLITEMID,utl::allocator<OLITEMID>> &,int &)

- ea: `0x18000936c`
- end: `0x1800096c5`
- name: `?ProcessSingleBatch@PimIMService@@AEAAJAEBUSyncPartnerData@@PEBUChangeInfo@@_KAEAHAEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@3@Z`
- size: `857`
- prototype: `__int64 __usercall@<rax>(PimIMService *this@<rcx>, struct SyncPartnerData *@<rdx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009250`

## callees

- `0x180002da8`
- `0x180003a50`
- `0x180004260`
- `0x18000428c`
- `0x180004670`
- `0x180004704`
- `0x180004aa8`
- `0x18000568c`
- `0x1800067c0`
- `0x180006f48`
- `0x180007968`
- `0x1800086a0`
- `0x18000936c`
- `0x18000c5b8`
- `0x18000c734`
- `0x18000c790`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800093c9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009461`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180009604`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::ProcessSingleBatch(
        struct IndexedFiltering::IIndexManager **this,
        struct SyncPartnerData *a2,
        __int64 a3,
        unsigned __int64 a4,
        _DWORD *a5,
        __int64 a6,
        _DWORD *a7)
{
  __int64 v10; // rcx
  int IndexManager; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  char v14; // al
  void *v15; // rax
  unsigned __int64 i; // rbx
  __int64 v17; // rdi
  int v18; // eax
  void *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  __int64 v28; // [rsp+50h] [rbp-D8h] BYREF
  unsigned __int64 v29; // [rsp+58h] [rbp-D0h] BYREF
  struct IndexedFiltering::IIndexManager *v30; // [rsp+60h] [rbp-C8h] BYREF
  int v31; // [rsp+68h] [rbp-C0h] BYREF
  int v32; // [rsp+6Ch] [rbp-BCh] BYREF
  unsigned int *v33; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int **v34; // [rsp+78h] [rbp-B0h] BYREF
  char v35; // [rsp+80h] [rbp-A8h]
  _QWORD v36[3]; // [rsp+88h] [rbp-A0h] BYREF
  char v37; // [rsp+A0h] [rbp-88h]
  _DWORD v38[14]; // [rsp+A8h] [rbp-80h] BYREF

  v29 = a4;
  if ( a4 != 1 && !*a5 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      1801);
  *a7 = 0;
  TransactionData::TransactionData((TransactionData *)v38);
  LODWORD(v28) = 0;
  v36[0] = v38;
  v36[1] = &v30;
  v36[2] = &v28;
  v30 = 0;
  v37 = 1;
  if ( *a5 )
  {
    IndexManager = PimIMService::GetIndexManager(this, 0, 1, &v30);
    v12 = IndexManager;
    if ( IndexManager < 0 )
    {
      v13 = 1820;
LABEL_9:
      Log_HREvent(
        (unsigned int)IndexManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v13);
      goto LABEL_36;
    }
    IndexManager = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager *))(*(_QWORD *)v30 + 48LL))(v30);
    v12 = IndexManager;
    if ( IndexManager < 0 )
    {
      v13 = 1822;
      goto LABEL_9;
    }
    v38[6] = 1;
    LODWORD(v28) = 2;
  }
  v33 = (unsigned int *)&v29;
  v14 = Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v15 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v15, &v29, 4, 0, -1);
    v14 = Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits;
  }
  if ( (v14 & 0x20) != 0 )
    McTemplateU0qq_EventWriteTransfer(v10, PIMIndex_ProcessingContacts, (unsigned int)v29, *((unsigned int *)a2 + 7));
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McTemplateU0q_EventWriteTransfer(v10, HANDLE_CHANGES_START, *v33);
  v35 = 1;
  v34 = &v33;
  for ( i = 0; i < v29; ++i )
  {
    v31 = 0;
    v17 = a3 + 32 * i;
    v18 = PimIMService::HandleChange(
            this,
            a2,
            (const struct ChangeInfo *)v17,
            (struct TransactionData *)v38,
            (enum PimIMService::PreProcessResult *)&v31);
    v32 = v18;
    if ( v18 < 0 )
    {
      if ( v18 == -2147023781 )
      {
        tlx::_UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___::__UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___(&v34);
        v12 = -2147023781;
        goto LABEL_36;
      }
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
      {
        v19 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v19, v21, (unsigned int)v20, a3 + 32 * i, v20, &v32, v20, 0, -1, v28);
      }
      v22 = *(_QWORD *)(a6 + 8);
      if ( v22 == *(_QWORD *)(a6 + 16) )
      {
        if ( !(unsigned __int8)utl::vector<OLITEMID,utl::allocator<OLITEMID>>::_PushBackOne2<OLITEMID const &>(
                                 a6,
                                 a3 + 32 * i) )
        {
          v12 = -2147024882;
          v23 = 1862;
          v24 = 2147942414LL;
          v25 = 0;
LABEL_28:
          Log_HREvent(
            v24,
            v25,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            v23);
          tlx::_UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___::__UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___(&v34);
          goto LABEL_36;
        }
      }
      else
      {
        *(_QWORD *)v22 = *(_QWORD *)v17;
        *(_DWORD *)(v22 + 8) = *(_DWORD *)(v17 + 8);
        *(_QWORD *)(a6 + 8) += 12LL;
      }
    }
  }
  if ( v38[0] )
  {
    *a7 = 1;
    v26 = PimIMService::CommitChanges(this, a2, (struct TransactionData *)v38);
    v12 = v26;
    if ( v26 < 0 )
    {
      v23 = 1873;
      v25 = 1;
      v24 = (unsigned int)v26;
      goto LABEL_28;
    }
    v37 = 0;
  }
  else
  {
    *a7 = 0;
  }
  tlx::_UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___::__UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___(&v34);
  v12 = 0;
LABEL_36:
  tlx::_UndoSolo__lambda_c8de69298b5a95a22ee9a7c3ac3f244b___::__UndoSolo__lambda_c8de69298b5a95a22ee9a7c3ac3f244b___(v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
  TransactionData::~TransactionData((TransactionData *)v38);
  return v12;
}

```

## disassembly

```asm
0x18000936c  push    rbx
0x18000936e  push    rsi
0x18000936f  push    rdi
0x180009370  push    r12
0x180009372  push    r13
0x180009374  push    r14
0x180009376  push    r15
0x180009378  sub     rsp, 0F0h
0x18000937f  mov     rax, cs:__security_cookie
0x180009386  xor     rax, rsp
0x180009389  mov     [rsp+128h+var_48], rax
0x180009391  mov     r14, [rsp+128h+arg_28]
0x180009399  xor     edi, edi
0x18000939b  mov     rsi, [rsp+128h+arg_30]
0x1800093a3  mov     r12, r8
0x1800093a6  mov     rbx, [rsp+128h+arg_20]
0x1800093ae  mov     r13, rdx
0x1800093b1  mov     [rsp+128h+var_D0], r9
0x1800093b6  mov     r15, rcx
0x1800093b9  cmp     r9, 1
0x1800093bd  jz      short loc_1800093D5
0x1800093bf  cmp     [rbx], edi
0x1800093c1  jnz     short loc_1800093D5
0x1800093c3  mov     r8d, 709h
0x1800093c9  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800093d0  call    Log_AssertionEvent
0x1800093d5  lea     rcx, [rsp+128h+var_80]; this
0x1800093dd  mov     [rsi], edi
0x1800093df  call    ??0TransactionData@@QEAA@XZ; TransactionData::TransactionData(void)
0x1800093e4  lea     rax, [rsp+128h+var_80]
0x1800093ec  mov     dword ptr [rsp+128h+var_D8], edi
0x1800093f0  mov     [rsp+128h+var_A0], rax
0x1800093f8  lea     rax, [rsp+128h+var_C8]
0x1800093fd  mov     [rsp+128h+var_98], rax
0x180009405  lea     rax, [rsp+128h+var_D8]
0x18000940a  mov     [rsp+128h+var_90], rax
0x180009412  mov     [rsp+128h+var_C8], rdi
0x180009417  mov     [rsp+128h+var_88], 1
0x18000941f  cmp     [rbx], edi
0x180009421  jz      short loc_18000948C
0x180009423  xor     edx, edx; int
0x180009425  lea     r9, [rsp+128h+var_C8]; struct IndexedFiltering::IIndexManager **
0x18000942a  mov     rcx, r15; this
0x18000942d  lea     r8d, [rdx+1]; int
0x180009431  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x180009436  mov     ebx, eax
0x180009438  test    eax, eax
0x18000943a  jns     short loc_180009444
0x18000943c  mov     r9d, 71Ch
0x180009442  jmp     short loc_180009461
0x180009444  mov     rcx, [rsp+128h+var_C8]
0x180009449  mov     rax, [rcx]
0x18000944c  mov     rax, [rax+30h]
0x180009450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009455  mov     ebx, eax
0x180009457  test    eax, eax
0x180009459  jns     short loc_180009479
0x18000945b  mov     r9d, 71Eh
0x180009461  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009468  mov     edx, 1
0x18000946d  mov     ecx, eax
0x18000946f  call    Log_HREvent
0x180009474  jmp     loc_18000967C
0x180009479  mov     [rsp+128h+var_68], 1
0x180009484  mov     dword ptr [rsp+128h+var_D8], 2
0x18000948c  lea     rax, [rsp+128h+var_D0]
0x180009491  mov     [rsp+128h+var_B8], rax
0x180009496  mov     eax, cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits
0x18000949c  test    al, 4
0x18000949e  jz      short loc_1800094D3
0x1800094a0  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800094a5  mov     rdx, rax; void *
0x1800094a8  mov     [rsp+128h+var_100], 0FFFFFFFFFFFFFFFFh
0x1800094b1  mov     r9d, 4
0x1800094b7  mov     [rsp+128h+var_108], rdi
0x1800094bc  lea     r8, [rsp+128h+var_D0]
0x1800094c1  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800094c8  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800094cd  mov     eax, cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits
0x1800094d3  test    al, 20h
0x1800094d5  jz      short loc_1800094EC
0x1800094d7  mov     r9d, [r13+1Ch]
0x1800094db  lea     rdx, PIMIndex_ProcessingContacts
0x1800094e2  mov     r8d, dword ptr [rsp+128h+var_D0]
0x1800094e7  call    McTemplateU0qq_EventWriteTransfer
0x1800094ec  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x1800094f3  jz      short loc_180009509
0x1800094f5  mov     r8, [rsp+128h+var_B8]
0x1800094fa  lea     rdx, HANDLE_CHANGES_START
0x180009501  mov     r8d, [r8]
0x180009504  call    McTemplateU0q_EventWriteTransfer
0x180009509  lea     rax, [rsp+128h+var_B8]
0x18000950e  mov     [rsp+128h+var_A8], 1
0x180009516  mov     [rsp+128h+var_B0], rax
0x18000951b  mov     rbx, rdi
0x18000951e  cmp     rbx, [rsp+128h+var_D0]
0x180009523  jnb     loc_18000962D
0x180009529  mov     [rsp+128h+var_C0], edi
0x18000952d  lea     rax, [rsp+128h+var_C0]
0x180009532  mov     rdi, rbx
0x180009535  mov     [rsp+128h+var_108], rax; enum PimIMService::PreProcessResult *
0x18000953a  shl     rdi, 5
0x18000953e  lea     r9, [rsp+128h+var_80]; struct TransactionData *
0x180009546  add     rdi, r12
0x180009549  mov     rdx, r13; struct SyncPartnerData *
0x18000954c  mov     r8, rdi; struct ChangeInfo *
0x18000954f  mov     rcx, r15; this
0x180009552  call    ?HandleChange@PimIMService@@AEAAJAEBUSyncPartnerData@@AEBUChangeInfo@@PEAUTransactionData@@AEAW4PreProcessResult@1@@Z; PimIMService::HandleChange(SyncPartnerData const &,ChangeInfo const &,TransactionData *,PimIMService::PreProcessResult &)
0x180009557  mov     [rsp+128h+var_BC], eax
0x18000955b  test    eax, eax
0x18000955d  jns     short loc_1800095DA
0x18000955f  cmp     eax, 8007045Bh
0x180009564  jz      loc_18000961C
0x18000956a  mov     ecx, 4
0x18000956f  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, cl
0x180009575  jz      short loc_1800095BD
0x180009577  lea     r8, [rdi+8]
0x18000957b  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180009580  mov     [rsp+128h+var_E0], 0FFFFFFFFFFFFFFFFh
0x180009589  mov     rdx, rax; void *
0x18000958c  mov     [rsp+128h+var_E8], 0
0x180009595  lea     rax, [rsp+128h+var_BC]
0x18000959a  mov     [rsp+128h+var_F0], rcx
0x18000959f  mov     r9d, ecx
0x1800095a2  mov     [rsp+128h+var_F8], rax
0x1800095a7  mov     [rsp+128h+var_100], rcx
0x1800095ac  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800095b3  mov     [rsp+128h+var_108], rdi
0x1800095b8  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800095bd  mov     rcx, [r14+8]
0x1800095c1  cmp     rcx, [r14+10h]
0x1800095c5  jz      short loc_1800095E4
0x1800095c7  movsd   xmm0, qword ptr [rdi]
0x1800095cb  movsd   qword ptr [rcx], xmm0
0x1800095cf  mov     eax, [rdi+8]
0x1800095d2  mov     [rcx+8], eax
0x1800095d5  add     qword ptr [r14+8], 0Ch
0x1800095da  xor     edi, edi
0x1800095dc  inc     rbx
0x1800095df  jmp     loc_18000951E
0x1800095e4  mov     rdx, rdi
0x1800095e7  mov     rcx, r14
0x1800095ea  call    ??$_PushBackOne2@AEBUOLITEMID@@@?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@AEAA_NAEBUOLITEMID@@@Z; utl::vector<OLITEMID,utl::allocator<OLITEMID>>::_PushBackOne2<OLITEMID const &>(OLITEMID const &)
0x1800095ef  xor     edi, edi
0x1800095f1  test    al, al
0x1800095f3  jnz     short loc_1800095DC
0x1800095f5  mov     ebx, 8007000Eh
0x1800095fa  mov     r9d, 746h
0x180009600  mov     ecx, ebx
0x180009602  xor     edx, edx
0x180009604  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000960b  call    Log_HREvent
0x180009610  lea     rcx, [rsp+128h+var_B0]
0x180009615  call    tlx___UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25_______UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___
0x18000961a  jmp     short loc_18000967C
0x18000961c  lea     rcx, [rsp+128h+var_B0]
0x180009621  call    tlx___UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25_______UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___
0x180009626  mov     ebx, 8007045Bh
0x18000962b  jmp     short loc_18000967C
0x18000962d  cmp     [rsp+128h+var_80], edi
0x180009634  jbe     short loc_18000966E
0x180009636  lea     r8, [rsp+128h+var_80]; struct TransactionData *
0x18000963e  mov     dword ptr [rsi], 1
0x180009644  mov     rdx, r13; struct SyncPartnerData *
0x180009647  mov     rcx, r15; this
0x18000964a  call    ?CommitChanges@PimIMService@@AEAAJAEBUSyncPartnerData@@PEAUTransactionData@@@Z; PimIMService::CommitChanges(SyncPartnerData const &,TransactionData *)
0x18000964f  mov     ebx, eax
0x180009651  test    eax, eax
0x180009653  jns     short loc_180009664
0x180009655  mov     r9d, 751h
0x18000965b  mov     edx, 1
0x180009660  mov     ecx, eax
0x180009662  jmp     short loc_180009604
0x180009664  mov     [rsp+128h+var_88], dil
0x18000966c  jmp     short loc_180009670
0x18000966e  mov     [rsi], edi
0x180009670  lea     rcx, [rsp+128h+var_B0]
0x180009675  call    tlx___UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25_______UndoSolo__lambda_a6a14a85b197b6c66be05557463f6a25___
0x18000967a  mov     ebx, edi
0x18000967c  lea     rcx, [rsp+128h+var_A0]
0x180009684  call    tlx___UndoSolo__lambda_c8de69298b5a95a22ee9a7c3ac3f244b_______UndoSolo__lambda_c8de69298b5a95a22ee9a7c3ac3f244b___
0x180009689  lea     rcx, [rsp+128h+var_C8]
0x18000968e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009693  lea     rcx, [rsp+128h+var_80]; this
0x18000969b  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x1800096a0  mov     eax, ebx
0x1800096a2  mov     rcx, [rsp+128h+var_48]
0x1800096aa  xor     rcx, rsp; StackCookie
0x1800096ad  call    __security_check_cookie
0x1800096b2  add     rsp, 0F0h
0x1800096b9  pop     r15
0x1800096bb  pop     r14
0x1800096bd  pop     r13
0x1800096bf  pop     r12
0x1800096c1  pop     rdi
0x1800096c2  pop     rsi
0x1800096c3  pop     rbx
0x1800096c4  retn
```
