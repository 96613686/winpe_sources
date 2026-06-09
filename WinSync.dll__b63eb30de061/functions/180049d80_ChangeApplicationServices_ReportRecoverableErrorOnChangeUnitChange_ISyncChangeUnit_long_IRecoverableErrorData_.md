# ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange(ISyncChangeUnit *,long,IRecoverableErrorData *,__MIDL___MIDL_itf_winsync_0000_0000_0001,__MIDL___MIDL_itf_winsync_0000_0000_0003)

- ea: `0x180049d80`
- end: `0x18004a068`
- name: `?ReportRecoverableErrorOnChangeUnitChange@ChangeApplicationServices@@UEAAJPEAUISyncChangeUnit@@JPEAUIRecoverableErrorData@@W4__MIDL___MIDL_itf_winsync_0000_0000_0001@@W4__MIDL___MIDL_itf_winsync_0000_0000_0003@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChangeUnit *, int, struct IRecoverableErrorData *, enum __MIDL___MIDL_itf_winsync_0000_0000_0001, enum __MIDL___MIDL_itf_winsync_0000_0000_0003)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180005f20`
- `0x18000a0f0`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x180046a54`
- `0x180046bb0`
- `0x180046dc4`
- `0x180046f80`
- `0x1800472c0`
- `0x1800487b0`
- `0x18004882c`
- `0x180049d80`
- `0x180074630`
- `0x180074730`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x180049dd2`: `ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange`
- `0x18004a00c`: `ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange(
        ChangeApplicationServices *this,
        struct ISyncChangeUnit *a2,
        unsigned int a3,
        struct IRecoverableErrorData *a4,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0001 a5,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0003 a6)
{
  int v6; // r15d
  char v8; // r12
  struct ISyncChangeUnitVtbl *lpVtbl; // rax
  int v12; // eax
  int v13; // edi
  __int64 v14; // rsi
  char v15; // al
  __int64 v16; // rbx
  char v17; // al
  __int64 *v18; // rax
  void *v19; // rax
  void *v20; // rax
  void *v21; // rdi
  __int64 v22; // rax
  __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  __int64 v25; // [rsp+38h] [rbp-40h] BYREF
  __int64 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v28[4]; // [rsp+50h] [rbp-28h] BYREF
  int v29; // [rsp+54h] [rbp-24h]
  __int64 v30; // [rsp+58h] [rbp-20h]
  _BYTE v31[4]; // [rsp+60h] [rbp-18h] BYREF
  int v32; // [rsp+64h] [rbp-14h]
  __int64 v33; // [rsp+68h] [rbp-10h]

  v6 = 0;
  v8 = 0;
  LODWORD(v24) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange");
  }
  lpVtbl = a2->lpVtbl;
  v26 = 0;
  v12 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, __int64 *))lpVtbl->GetItemChange)(a2, &v26);
  v32 = 0;
  v13 = v12;
  v33 = 0;
  if ( v12 >= 0 )
  {
    v13 = SyncId::InitializeForRetrieval((SyncId *)v31, (ChangeApplicationServices *)((char *)this + 40));
    if ( v13 >= 0 )
    {
      LODWORD(v24) = (unsigned __int16)v32;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, v33 + 4, &v24);
    }
  }
  v29 = 0;
  v30 = 0;
  if ( v13 >= 0 )
  {
    v13 = SyncId::InitializeForRetrieval((SyncId *)v28, (ChangeApplicationServices *)((char *)this + 48));
    if ( v13 >= 0 )
    {
      LODWORD(v24) = (unsigned __int16)v29;
      v13 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, __int64, __int64 *))a2->lpVtbl->GetChangeUnitId)(
              a2,
              v30 + 4,
              &v24);
    }
  }
  v24 = 0;
  v14 = 0;
  v25 = 0;
  if ( v13 >= 0 )
  {
    v15 = HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
            (char *)this + 168,
            v31,
            &v24);
    v16 = v24;
    if ( v15 )
    {
      if ( *(_DWORD *)(v24 + 20) != 1
        || (v17 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                    v24 + 56,
                    v28,
                    &v25),
            v14 = v25,
            v17)
        && *(_DWORD *)(v25 + 20) != 1 )
      {
        v13 = -2147217407;
        goto LABEL_34;
      }
      v6 = 1;
      if ( v25 )
      {
        v18 = (__int64 *)SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v27, a4, 1);
        *(_DWORD *)(v14 + 24) = a3;
        SharedRefPtr<IClockVector>::operator=((__int64 *)(v14 + 32), v18);
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v27);
      }
    }
    if ( !v16 )
    {
      v19 = SeAlloc(0x50u);
      if ( v19 )
        v19 = (void *)ItemChangeApplicationStatus::ItemChangeApplicationStatus(v19, 1, &v26);
      v13 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v24, v19);
      if ( v13 < 0 )
        goto LABEL_34;
      v16 = v24;
    }
    if ( v14 )
      goto LABEL_32;
    v20 = SeAlloc(0x28u);
    v21 = v20;
    if ( v20 )
    {
      v22 = SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v27, a4, 1);
      v20 = (void *)ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(v21, a3, v22);
      v8 = 1;
    }
    v13 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v25, v20);
    if ( (v8 & 1) != 0 )
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v27);
    if ( v13 >= 0 )
    {
      v13 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
              v16 + 56,
              v28,
              &v25);
      if ( v13 >= 0 )
      {
        *(_DWORD *)(v16 + 44) = a6;
        *(_DWORD *)(v16 + 40) = a5;
LABEL_32:
        if ( !v6 )
          v13 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
                  (char *)this + 168,
                  v31,
                  &v24);
      }
    }
  }
LABEL_34:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportRecoverableErrorOnChangeUnitChange",
      v13);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v25);
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v24);
  SyncId::~SyncId((SyncId *)v28);
  SyncId::~SyncId((SyncId *)v31);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180049d80  mov     [rsp-40h+arg_10], r8d
0x180049d85  push    rbp
0x180049d86  push    rbx
0x180049d87  push    rsi
0x180049d88  push    rdi
0x180049d89  push    r12
0x180049d8b  push    r13
0x180049d8d  push    r14
0x180049d8f  push    r15
0x180049d91  mov     rbp, rsp
0x180049d94  sub     rsp, 78h
0x180049d98  xor     r15d, r15d
0x180049d9b  mov     r13, r9
0x180049d9e  mov     r12d, r15d
0x180049da1  mov     dword ptr [rbp+var_48], r15d
0x180049da5  mov     rsi, rdx
0x180049da8  mov     r14, rcx
0x180049dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180049db2  lea     rax, WPP_GLOBAL_Control
0x180049db9  cmp     rcx, rax
0x180049dbc  jz      short loc_180049DE5
0x180049dbe  test    byte ptr [rcx+1Ch], 80h
0x180049dc2  jz      short loc_180049DE5
0x180049dc4  cmp     byte ptr [rcx+19h], 5
0x180049dc8  jb      short loc_180049DE5
0x180049dca  mov     rcx, [rcx+10h]
0x180049dce  lea     edx, [r15+26h]
0x180049dd2  lea     r9, aChangeapplicat_47; "ChangeApplicationServices::ReportRecove"...
0x180049dd9  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049de0  call    WPP_SF_s
0x180049de5  mov     rax, [rsi]
0x180049de8  lea     rdx, [rbp+var_38]
0x180049dec  mov     rcx, rsi
0x180049def  mov     [rbp+var_38], r15
0x180049df3  mov     rax, [rax+18h]
0x180049df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dfc  mov     [rbp+var_14], r15d
0x180049e00  mov     edi, eax
0x180049e02  mov     [rbp+var_10], r15
0x180049e06  test    eax, eax
0x180049e08  js      short loc_180049E42
0x180049e0a  lea     rdx, [r14+28h]; struct IdFormat *
0x180049e0e  lea     rcx, [rbp+var_18]; this
0x180049e12  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180049e17  mov     edi, eax
0x180049e19  test    eax, eax
0x180049e1b  js      short loc_180049E42
0x180049e1d  mov     rcx, [rbp+var_38]
0x180049e21  lea     r8, [rbp+var_48]
0x180049e25  movzx   eax, word ptr [rbp+var_14]
0x180049e29  mov     rdx, [rbp+var_10]
0x180049e2d  mov     dword ptr [rbp+var_48], eax
0x180049e30  add     rdx, 4
0x180049e34  mov     rax, [rcx]
0x180049e37  mov     rax, [rax+20h]
0x180049e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e40  mov     edi, eax
0x180049e42  mov     [rbp+var_24], r15d
0x180049e46  mov     [rbp+var_20], r15
0x180049e4a  test    edi, edi
0x180049e4c  js      short loc_180049E85
0x180049e4e  lea     rdx, [r14+30h]; struct IdFormat *
0x180049e52  lea     rcx, [rbp+var_28]; this
0x180049e56  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180049e5b  mov     edi, eax
0x180049e5d  test    eax, eax
0x180049e5f  js      short loc_180049E85
0x180049e61  movzx   eax, word ptr [rbp+var_24]
0x180049e65  lea     r8, [rbp+var_48]
0x180049e69  mov     rdx, [rbp+var_20]
0x180049e6d  mov     rcx, rsi
0x180049e70  mov     dword ptr [rbp+var_48], eax
0x180049e73  add     rdx, 4
0x180049e77  mov     rax, [rsi]
0x180049e7a  mov     rax, [rax+20h]
0x180049e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e83  mov     edi, eax
0x180049e85  mov     [rbp+var_48], r15
0x180049e89  mov     rsi, r15
0x180049e8c  mov     [rbp+var_40], r15
0x180049e90  test    edi, edi
0x180049e92  js      loc_180049FE9
0x180049e98  lea     r8, [rbp+var_48]
0x180049e9c  lea     rdx, [rbp+var_18]
0x180049ea0  lea     rcx, [r14+0A8h]
0x180049ea7  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x180049eac  mov     rbx, [rbp+var_48]
0x180049eb0  test    al, al
0x180049eb2  jz      short loc_180049F18
0x180049eb4  cmp     dword ptr [rbx+14h], 1
0x180049eb8  jnz     short loc_180049ED9
0x180049eba  lea     rcx, [rbx+38h]
0x180049ebe  lea     r8, [rbp+var_40]
0x180049ec2  lea     rdx, [rbp+var_28]
0x180049ec6  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180049ecb  mov     rsi, [rbp+var_40]
0x180049ecf  test    al, al
0x180049ed1  jz      short loc_180049EE3
0x180049ed3  cmp     dword ptr [rsi+14h], 1
0x180049ed7  jz      short loc_180049EE3
0x180049ed9  mov     edi, 80041001h
0x180049ede  jmp     loc_180049FE9
0x180049ee3  mov     r15d, 1
0x180049ee9  test    rsi, rsi
0x180049eec  jz      short loc_180049F18
0x180049eee  mov     r8d, r15d
0x180049ef1  lea     rcx, [rbp+var_30]
0x180049ef5  mov     rdx, r13
0x180049ef8  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x180049efd  mov     ecx, [rbp+arg_10]
0x180049f00  mov     rdx, rax
0x180049f03  mov     [rsi+18h], ecx
0x180049f06  lea     rcx, [rsi+20h]
0x180049f0a  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x180049f0f  lea     rcx, [rbp+var_30]
0x180049f13  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049f18  test    rbx, rbx
0x180049f1b  jnz     short loc_180049F53
0x180049f1d  lea     ecx, [rbx+50h]; unsigned __int64
0x180049f20  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049f25  test    rax, rax
0x180049f28  jz      short loc_180049F39
0x180049f2a  lea     r8, [rbp+var_38]
0x180049f2e  mov     rcx, rax
0x180049f31  lea     edx, [rbx+1]
0x180049f34  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x180049f39  mov     rdx, rax
0x180049f3c  lea     rcx, [rbp+var_48]
0x180049f40  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049f45  mov     edi, eax
0x180049f47  test    eax, eax
0x180049f49  js      loc_180049FE9
0x180049f4f  mov     rbx, [rbp+var_48]
0x180049f53  test    rsi, rsi
0x180049f56  jnz     short loc_180049FCE
0x180049f58  lea     ecx, [rsi+28h]; unsigned __int64
0x180049f5b  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049f60  mov     rdi, rax
0x180049f63  test    rax, rax
0x180049f66  jz      short loc_180049F8A
0x180049f68  lea     r8d, [rsi+1]
0x180049f6c  mov     rdx, r13
0x180049f6f  lea     rcx, [rbp+var_30]
0x180049f73  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x180049f78  mov     edx, [rbp+arg_10]
0x180049f7b  mov     r8, rax
0x180049f7e  mov     rcx, rdi
0x180049f81  call    ??0ChangeUnitChangeApplicationStatus@@QEAA@JAEBV?$SharedRefPtr@UIRecoverableErrorData@@@@@Z; ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(long,SharedRefPtr<IRecoverableErrorData> const &)
0x180049f86  lea     r12d, [rsi+1]
0x180049f8a  mov     rdx, rax
0x180049f8d  lea     rcx, [rbp+var_40]
0x180049f91  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049f96  mov     edi, eax
0x180049f98  test    r12b, 1
0x180049f9c  jz      short loc_180049FA7
0x180049f9e  lea     rcx, [rbp+var_30]
0x180049fa2  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049fa7  test    edi, edi
0x180049fa9  js      short loc_180049FE9
0x180049fab  lea     rcx, [rbx+38h]
0x180049faf  lea     r8, [rbp+var_40]
0x180049fb3  lea     rdx, [rbp+var_28]
0x180049fb7  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> const &)
0x180049fbc  mov     edi, eax
0x180049fbe  test    eax, eax
0x180049fc0  js      short loc_180049FE9
0x180049fc2  mov     eax, [rbp+arg_28]
0x180049fc5  mov     [rbx+2Ch], eax
0x180049fc8  mov     eax, [rbp+arg_20]
0x180049fcb  mov     [rbx+28h], eax
0x180049fce  test    r15d, r15d
0x180049fd1  jnz     short loc_180049FE9
0x180049fd3  lea     r8, [rbp+var_48]
0x180049fd7  lea     rdx, [rbp+var_18]
0x180049fdb  lea     rcx, [r14+0A8h]
0x180049fe2  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x180049fe7  mov     edi, eax
0x180049fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ff0  lea     rax, WPP_GLOBAL_Control
0x180049ff7  cmp     rcx, rax
0x180049ffa  jz      short loc_18004A028
0x180049ffc  test    byte ptr [rcx+1Ch], 80h
0x18004a000  jz      short loc_18004A028
0x18004a002  cmp     byte ptr [rcx+19h], 5
0x18004a006  jb      short loc_18004A028
0x18004a008  mov     rcx, [rcx+10h]
0x18004a00c  lea     r9, aChangeapplicat_47; "ChangeApplicationServices::ReportRecove"...
0x18004a013  mov     edx, 27h ; '''
0x18004a018  mov     [rsp+78h+var_58], edi
0x18004a01c  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a023  call    WPP_SF_sD
0x18004a028  lea     rcx, [rbp+var_40]
0x18004a02c  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x18004a031  lea     rcx, [rbp+var_48]
0x18004a035  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x18004a03a  lea     rcx, [rbp+var_28]; this
0x18004a03e  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004a043  lea     rcx, [rbp+var_18]; this
0x18004a047  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004a04c  lea     rcx, [rbp+var_38]
0x18004a050  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a055  mov     eax, edi
0x18004a057  add     rsp, 78h
0x18004a05b  pop     r15
0x18004a05d  pop     r14
0x18004a05f  pop     r13
0x18004a061  pop     r12
0x18004a063  pop     rdi
0x18004a064  pop     rsi
0x18004a065  pop     rbx
0x18004a066  pop     rbp
0x18004a067  retn
```
