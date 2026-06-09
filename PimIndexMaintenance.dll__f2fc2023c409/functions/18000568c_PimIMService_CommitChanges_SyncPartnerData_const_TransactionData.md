# PimIMService::CommitChanges(SyncPartnerData const &,TransactionData *)

- ea: `0x18000568c`
- end: `0x1800058c2`
- name: `?CommitChanges@PimIMService@@AEAAJAEBUSyncPartnerData@@PEAUTransactionData@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct IndexedFiltering::IIndexManager **this, const struct SyncPartnerData *, struct TransactionData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000936c`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180003d38`
- `0x18000428c`
- `0x180004310`
- `0x18000463c`
- `0x18000568c`
- `0x180005e1c`
- `0x180006f48`
- `0x1800086a0`
- `0x180009aa4`
- `0x18000c734`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800056e7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::CommitChanges(
        struct IndexedFiltering::IIndexManager **this,
        const struct SyncPartnerData *a2,
        struct TransactionData *a3)
{
  bool v6; // zf
  int IndexManager; // eax
  int v8; // ebx
  __int64 v9; // rcx
  MetadataUpdates **v10; // r15
  int MetadataUpdates; // eax
  __int64 v12; // rcx
  int v13; // r14d
  _BYTE v15[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-38h] BYREF
  struct IndexedFiltering::IIndexManager *v18; // [rsp+40h] [rbp-30h] BYREF
  unsigned int *v19; // [rsp+48h] [rbp-28h] BYREF
  unsigned int **v20; // [rsp+50h] [rbp-20h] BYREF
  char v21; // [rsp+58h] [rbp-18h]

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      COMMIT_CHANGES_START,
      a3,
      1,
      &v20);
  v15[1] = 1;
  if ( !a3 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2002);
  v6 = *((_DWORD *)a3 + 6) == 0;
  v16 = *(_DWORD *)a3;
  if ( !v6 )
  {
    v18 = 0;
    IndexManager = PimIMService::GetIndexManager(this, 0, 0, &v18);
    v8 = IndexManager;
    if ( IndexManager < 0 )
    {
      Log_HREvent(
        (unsigned int)IndexManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2012);
LABEL_24:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
      goto LABEL_21;
    }
    v17 = (unsigned __int64)(this + 23) & -(__int64)(this != 0);
    if ( !v17 )
    {
      v8 = -2147467262;
      Log_HREvent(
        2147500034LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2016);
      goto LABEL_23;
    }
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)((unsigned __int64)(this + 23) & -(__int64)(this != 0)) + 8LL))((unsigned __int64)(this + 23) & -(__int64)(this != 0));
    v10 = this + 36;
    if ( this[36] )
      Log_AssertionEvent(
        v9,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2018);
    MetadataUpdates = MetadataUpdates::CreateMetadataUpdates(a2, (char *)a3 + 32, this + 36);
    v13 = MetadataUpdates;
    if ( MetadataUpdates < 0 )
    {
      Log_HREvent(
        (unsigned int)MetadataUpdates,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2023);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
      v8 = v13;
      goto LABEL_24;
    }
    v19 = &v16;
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
      McTemplateU0q_EventWriteTransfer(v12, END_TRANSACTION_START, v16);
    v20 = &v19;
    v21 = 1;
    v8 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager *, __int64, unsigned __int64))(*(_QWORD *)v18 + 56LL))(
           v18,
           3,
           (unsigned __int64)(this + 23) & -(__int64)(this != 0));
    if ( *v10 )
      tlx::_delete<MetadataUpdates>(*v10);
    *v10 = 0;
    if ( v8 < 0 )
    {
      Log_HREvent(
        (unsigned int)v8,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        2036);
      tlx::_UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___::__UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___(&v20);
LABEL_23:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
      goto LABEL_24;
    }
    tlx::_UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___::__UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___(&v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  }
  PimIMService::SendCustomEvent((PimIMService *)this, a3);
  v8 = 0;
LABEL_21:
  tlx::_UndoSolo__lambda_372ec39241f3d5e4c07cbb03bc7aaaff___::__UndoSolo__lambda_372ec39241f3d5e4c07cbb03bc7aaaff___(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000568c  push    rbp
0x18000568e  push    rbx
0x18000568f  push    rsi
0x180005690  push    rdi
0x180005691  push    r13
0x180005693  push    r14
0x180005695  push    r15
0x180005697  mov     rbp, rsp
0x18000569a  sub     rsp, 70h
0x18000569e  mov     rax, cs:__security_cookie
0x1800056a5  xor     rax, rsp
0x1800056a8  mov     [rbp+var_10], rax
0x1800056ac  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x1800056b3  mov     rdi, r8
0x1800056b6  mov     r14, rdx
0x1800056b9  mov     rsi, rcx
0x1800056bc  mov     r15d, 1
0x1800056c2  jz      short loc_1800056E3
0x1800056c4  lea     rax, [rbp+var_20]
0x1800056c8  mov     r9d, r15d
0x1800056cb  lea     rdx, COMMIT_CHANGES_START
0x1800056d2  mov     [rsp+70h+var_50], rax
0x1800056d7  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x1800056de  call    McGenEventWrite_EventWriteTransfer
0x1800056e3  mov     [rbp+var_3F], r15b
0x1800056e7  lea     r13, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800056ee  test    rdi, rdi
0x1800056f1  jnz     short loc_180005701
0x1800056f3  mov     r8d, 7D2h
0x1800056f9  mov     rdx, r13
0x1800056fc  call    Log_AssertionEvent
0x180005701  cmp     dword ptr [rdi+18h], 0
0x180005705  mov     eax, [rdi]
0x180005707  mov     [rbp+var_3C], eax
0x18000570a  jz      loc_180005864
0x180005710  lea     r9, [rbp+var_30]; struct IndexedFiltering::IIndexManager **
0x180005714  mov     [rbp+var_30], 0
0x18000571c  xor     r8d, r8d; int
0x18000571f  xor     edx, edx; int
0x180005721  mov     rcx, rsi; this
0x180005724  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x180005729  mov     ebx, eax
0x18000572b  test    eax, eax
0x18000572d  jns     short loc_180005747
0x18000572f  mov     r9d, 7DCh
0x180005735  mov     r8, r13
0x180005738  mov     edx, r15d
0x18000573b  mov     ecx, eax
0x18000573d  call    Log_HREvent
0x180005742  jmp     loc_1800058B7
0x180005747  mov     rax, rsi
0x18000574a  lea     rcx, [rsi+0B8h]
0x180005751  neg     rax
0x180005754  sbb     rbx, rbx
0x180005757  and     rbx, rcx
0x18000575a  mov     [rbp+var_38], rbx
0x18000575e  jz      loc_180005897
0x180005764  mov     rax, [rbx]
0x180005767  mov     rcx, rbx
0x18000576a  mov     rax, [rax+8]
0x18000576e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005773  lea     r15, [rsi+120h]
0x18000577a  cmp     qword ptr [r15], 0
0x18000577e  jz      short loc_18000578E
0x180005780  mov     r8d, 7E2h
0x180005786  mov     rdx, r13
0x180005789  call    Log_AssertionEvent
0x18000578e  lea     rdx, [rdi+20h]
0x180005792  mov     r8, r15
0x180005795  mov     rcx, r14
0x180005798  call    ?CreateMetadataUpdates@MetadataUpdates@@SAJAEBUSyncPartnerData@@AEAV?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAV?$auto_ptr@UMetadataUpdates@@$1??$_delete@UMetadataUpdates@@@tlx@@YAXPEAU1@@Z@tlx@@@Z; MetadataUpdates::CreateMetadataUpdates(SyncPartnerData const &,utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>> &,tlx::auto_ptr<MetadataUpdates,&tlx::_delete<MetadataUpdates>(MetadataUpdates *)> &)
0x18000579d  mov     r14d, eax
0x1800057a0  test    eax, eax
0x1800057a2  jns     short loc_1800057CA
0x1800057a4  mov     r9d, 7E7h
0x1800057aa  mov     r8, r13
0x1800057ad  mov     edx, 1
0x1800057b2  mov     ecx, eax
0x1800057b4  call    Log_HREvent
0x1800057b9  lea     rcx, [rbp+var_38]
0x1800057bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800057c2  mov     ebx, r14d
0x1800057c5  jmp     loc_1800058B7
0x1800057ca  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x1800057d1  lea     rax, [rbp+var_3C]
0x1800057d5  mov     [rbp+var_28], rax
0x1800057d9  jz      short loc_1800057EB
0x1800057db  mov     r8d, [rbp+var_3C]
0x1800057df  lea     rdx, END_TRANSACTION_START
0x1800057e6  call    McTemplateU0q_EventWriteTransfer
0x1800057eb  mov     rcx, [rbp+var_30]
0x1800057ef  lea     rax, [rbp+var_28]
0x1800057f3  mov     [rbp+var_20], rax
0x1800057f7  mov     r8, rbx
0x1800057fa  mov     edx, 3
0x1800057ff  mov     [rbp+var_18], 1
0x180005803  mov     rax, [rcx]
0x180005806  mov     rax, [rax+38h]
0x18000580a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000580f  mov     rcx, [r15]; Block
0x180005812  mov     ebx, eax
0x180005814  test    rcx, rcx
0x180005817  jz      short loc_18000581E
0x180005819  call    ??$_delete@UMetadataUpdates@@@tlx@@YAXPEAUMetadataUpdates@@@Z; tlx::_delete<MetadataUpdates>(MetadataUpdates *)
0x18000581e  mov     qword ptr [r15], 0
0x180005825  test    ebx, ebx
0x180005827  jns     short loc_180005849
0x180005829  mov     r9d, 7F4h
0x18000582f  mov     r8, r13
0x180005832  mov     edx, 1
0x180005837  mov     ecx, ebx
0x180005839  call    Log_HREvent
0x18000583e  lea     rcx, [rbp+var_20]
0x180005842  call    tlx___UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2_______UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___
0x180005847  jmp     short loc_1800058AE
0x180005849  lea     rcx, [rbp+var_20]
0x18000584d  call    tlx___UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2_______UndoSolo__lambda_9a143be453da6c4eb24f3183d2ea53b2___
0x180005852  lea     rcx, [rbp+var_38]
0x180005856  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000585b  lea     rcx, [rbp+var_30]
0x18000585f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005864  mov     rdx, rdi; struct TransactionData *
0x180005867  mov     rcx, rsi; this
0x18000586a  call    ?SendCustomEvent@PimIMService@@AEAAJPEBUTransactionData@@@Z; PimIMService::SendCustomEvent(TransactionData const *)
0x18000586f  xor     ebx, ebx
0x180005871  lea     rcx, [rbp+var_40]
0x180005875  call    tlx___UndoSolo__lambda_372ec39241f3d5e4c07cbb03bc7aaaff_______UndoSolo__lambda_372ec39241f3d5e4c07cbb03bc7aaaff___
0x18000587a  mov     eax, ebx
0x18000587c  mov     rcx, [rbp+var_10]
0x180005880  xor     rcx, rsp; StackCookie
0x180005883  call    __security_check_cookie
0x180005888  add     rsp, 70h
0x18000588c  pop     r15
0x18000588e  pop     r14
0x180005890  pop     r13
0x180005892  pop     rdi
0x180005893  pop     rsi
0x180005894  pop     rbx
0x180005895  pop     rbp
0x180005896  retn
0x180005897  mov     ebx, 80004002h
0x18000589c  mov     r9d, 7E0h
0x1800058a2  mov     ecx, ebx
0x1800058a4  mov     r8, r13
0x1800058a7  xor     edx, edx
0x1800058a9  call    Log_HREvent
0x1800058ae  lea     rcx, [rbp+var_38]
0x1800058b2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800058b7  lea     rcx, [rbp+var_30]
0x1800058bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800058c0  jmp     short loc_180005871
```
