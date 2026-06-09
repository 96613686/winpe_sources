# ChangeApplicationServices::ReportRecoverableErrorOnItemChange(ISyncChange *,long,IRecoverableErrorData *,__MIDL___MIDL_itf_winsync_0000_0000_0001,__MIDL___MIDL_itf_winsync_0000_0000_0003)

- ea: `0x18004a1d0`
- end: `0x18004a551`
- name: `?ReportRecoverableErrorOnItemChange@ChangeApplicationServices@@UEAAJPEAUISyncChange@@JPEAUIRecoverableErrorData@@W4__MIDL___MIDL_itf_winsync_0000_0000_0001@@W4__MIDL___MIDL_itf_winsync_0000_0000_0003@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChange *, int, struct IRecoverableErrorData *, enum __MIDL___MIDL_itf_winsync_0000_0000_0001, enum __MIDL___MIDL_itf_winsync_0000_0000_0003)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180005f20`
- `0x180007584`
- `0x18000a0f0`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x180046a54`
- `0x180046bb0`
- `0x180046f80`
- `0x1800472c0`
- `0x180047c90`
- `0x1800487b0`
- `0x18004882c`
- `0x18004a1d0`
- `0x1800746b0`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x18004a227`: `ChangeApplicationServices::ReportRecoverableErrorOnItemChange`
- `0x18004a507`: `ChangeApplicationServices::ReportRecoverableErrorOnItemChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportRecoverableErrorOnItemChange(
        ChangeApplicationServices *this,
        struct ISyncChange *a2,
        int a3,
        struct IRecoverableErrorData *a4,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0001 a5,
        enum __MIDL___MIDL_itf_winsync_0000_0000_0003 a6)
{
  char v6; // di
  struct IRecoverableErrorData *v7; // r13
  int v10; // ebx
  char *v11; // r12
  __int64 v12; // rdi
  int v13; // eax
  int v14; // eax
  __int64 v15; // r13
  int v16; // eax
  int v17; // eax
  __int64 *v18; // rax
  void *v19; // rax
  int v20; // r15d
  int v21; // ebx
  int v22; // eax
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-30h] BYREF
  __int64 v27; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v28[4]; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+54h] [rbp-1Ch]
  __int64 v30; // [rsp+58h] [rbp-18h]
  _BYTE v31[4]; // [rsp+60h] [rbp-10h] BYREF
  int v32; // [rsp+64h] [rbp-Ch]
  __int64 v33; // [rsp+68h] [rbp-8h]

  v6 = 0;
  v7 = a4;
  LODWORD(v24) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportRecoverableErrorOnItemChange");
  }
  v29 = 0;
  v30 = 0;
  v10 = SyncId::InitializeForRetrieval((SyncId *)v28, (ChangeApplicationServices *)((char *)this + 40));
  if ( v10 >= 0 )
  {
    LODWORD(v24) = (unsigned __int16)v29;
    v10 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64, __int64 *))a2->lpVtbl->GetRootItemId)(
            a2,
            v30 + 4,
            &v24);
  }
  v25 = 0;
  if ( v10 >= 0 )
  {
    v11 = (char *)this + 168;
    if ( (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
                            (char *)this + 168,
                            v28,
                            &v25) )
    {
      v12 = v25;
      if ( *(_DWORD *)(v25 + 20) != 1 )
        v10 = -2147217407;
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      if ( v10 < 0 )
        goto LABEL_32;
      v13 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64 *))a2->lpVtbl->GetChangeUnits)(a2, &v27);
      v10 = v13;
      if ( v13 == -2147217393 )
      {
        v10 = 0;
      }
      else if ( v13 < 0 )
      {
        goto LABEL_32;
      }
      if ( v27 && *(_DWORD *)(v12 + 72) )
      {
        v14 = (*(__int64 (**)(void))(*(_QWORD *)v27 + 40LL))();
        v32 = 0;
        v10 = v14;
        v33 = 0;
        v15 = 0;
        if ( v14 >= 0 )
        {
          v16 = SyncId::InitializeForRetrieval((SyncId *)v31, (ChangeApplicationServices *)((char *)this + 48));
          v15 = v33;
          v10 = v16;
        }
        while ( v10 >= 0 )
        {
          ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
          v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 24LL))(v27, 1, &v26);
          v10 = v17;
          if ( v17 == 1 )
          {
            v10 = 0;
            SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
            HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FreeHashTable(v12 + 56);
            break;
          }
          if ( v17 >= 0 )
          {
            LODWORD(v24) = (unsigned __int16)v32;
            v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, v15 + 4, &v24);
          }
          v24 = 0;
          if ( v10 >= 0
            && (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                                  v12 + 56,
                                  v31,
                                  &v24)
            && !*(_DWORD *)(v24 + 20) )
          {
            v10 = -2147217407;
          }
          SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v24);
          SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
        }
        SyncId::~SyncId((SyncId *)v31);
        if ( v10 < 0 )
          goto LABEL_32;
        v7 = a4;
      }
      v18 = (__int64 *)SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v26, v7, 1);
      *(_DWORD *)(v12 + 24) = a3;
      SharedRefPtr<IClockVector>::operator=((__int64 *)(v12 + 32), v18);
      *(_DWORD *)(v12 + 40) = a5;
      *(_DWORD *)(v12 + 44) = a6;
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
LABEL_32:
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v27);
      goto LABEL_41;
    }
    v19 = SeAlloc(0x50u);
    v20 = (int)v19;
    if ( v19 )
    {
      v21 = SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v26, a2, 1);
      v22 = SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v27, v7, 1);
      v19 = (void *)ItemChangeApplicationStatus::ItemChangeApplicationStatus(v20, a3, v22, v21, a5, a6);
      v6 = 3;
    }
    v10 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v25, v19);
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v27);
    }
    if ( (v6 & 1) != 0 )
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v26);
    if ( v10 >= 0 )
      v10 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(v11, v28, &v25);
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportRecoverableErrorOnItemChange",
      v10);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v25);
  SyncId::~SyncId((SyncId *)v28);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004a1d0  mov     rax, rsp
0x18004a1d3  mov     [rax+8], rbx
0x18004a1d7  mov     [rax+10h], rdi
0x18004a1db  mov     [rax+20h], r9
0x18004a1df  mov     [rax+18h], r8d
0x18004a1e3  push    rbp
0x18004a1e4  push    r12
0x18004a1e6  push    r13
0x18004a1e8  push    r14
0x18004a1ea  push    r15
0x18004a1ec  mov     rbp, rsp
0x18004a1ef  sub     rsp, 70h
0x18004a1f3  xor     edi, edi
0x18004a1f5  mov     r13, r9
0x18004a1f8  mov     dword ptr [rbp+var_40], edi
0x18004a1fb  mov     r14, rdx
0x18004a1fe  mov     r15, rcx
0x18004a201  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a208  lea     rax, WPP_GLOBAL_Control
0x18004a20f  cmp     rcx, rax
0x18004a212  jz      short loc_18004A23A
0x18004a214  test    byte ptr [rcx+1Ch], 80h
0x18004a218  jz      short loc_18004A23A
0x18004a21a  cmp     byte ptr [rcx+19h], 5
0x18004a21e  jb      short loc_18004A23A
0x18004a220  mov     rcx, [rcx+10h]
0x18004a224  lea     edx, [rdi+24h]
0x18004a227  lea     r9, aChangeapplicat_45; "ChangeApplicationServices::ReportRecove"...
0x18004a22e  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a235  call    WPP_SF_s
0x18004a23a  lea     rdx, [r15+28h]; struct IdFormat *
0x18004a23e  mov     [rbp+var_1C], edi
0x18004a241  lea     rcx, [rbp+var_20]; this
0x18004a245  mov     [rbp+var_18], rdi
0x18004a249  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004a24e  mov     ebx, eax
0x18004a250  test    eax, eax
0x18004a252  js      short loc_18004A278
0x18004a254  movzx   eax, word ptr [rbp+var_1C]
0x18004a258  lea     r8, [rbp+var_40]
0x18004a25c  mov     rdx, [rbp+var_18]
0x18004a260  mov     rcx, r14
0x18004a263  mov     dword ptr [rbp+var_40], eax
0x18004a266  add     rdx, 4
0x18004a26a  mov     rax, [r14]
0x18004a26d  mov     rax, [rax+20h]
0x18004a271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a276  mov     ebx, eax
0x18004a278  mov     [rbp+var_38], rdi
0x18004a27c  test    ebx, ebx
0x18004a27e  js      loc_18004A4E4
0x18004a284  lea     r12, [r15+0A8h]
0x18004a28b  mov     rcx, r12
0x18004a28e  lea     r8, [rbp+var_38]
0x18004a292  lea     rdx, [rbp+var_20]
0x18004a296  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x18004a29b  test    al, al
0x18004a29d  jz      loc_18004A442
0x18004a2a3  mov     rdi, [rbp+var_38]
0x18004a2a7  lea     rcx, [rbp+var_28]
0x18004a2ab  mov     eax, 80041001h
0x18004a2b0  cmp     dword ptr [rdi+14h], 1
0x18004a2b4  cmovnz  ebx, eax
0x18004a2b7  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004a2bc  xor     r12d, r12d
0x18004a2bf  test    ebx, ebx
0x18004a2c1  js      loc_18004A434
0x18004a2c7  mov     rax, [r14]
0x18004a2ca  lea     rdx, [rbp+var_28]
0x18004a2ce  mov     rcx, r14
0x18004a2d1  mov     rax, [rax+48h]
0x18004a2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2da  mov     ebx, eax
0x18004a2dc  cmp     eax, 8004100Fh
0x18004a2e1  jnz     short loc_18004A2E8
0x18004a2e3  mov     ebx, r12d
0x18004a2e6  jmp     short loc_18004A2F0
0x18004a2e8  test    eax, eax
0x18004a2ea  js      loc_18004A434
0x18004a2f0  mov     rcx, [rbp+var_28]
0x18004a2f4  test    rcx, rcx
0x18004a2f7  jz      loc_18004A3FB
0x18004a2fd  cmp     [rdi+48h], r12d
0x18004a301  jbe     loc_18004A3FB
0x18004a307  mov     rax, [rcx]
0x18004a30a  mov     rax, [rax+28h]
0x18004a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a313  mov     [rbp+var_C], r12d
0x18004a317  mov     ebx, eax
0x18004a319  mov     [rbp+var_8], r12
0x18004a31d  mov     r13, r12
0x18004a320  test    eax, eax
0x18004a322  js      short loc_18004A337
0x18004a324  lea     rdx, [r15+30h]; struct IdFormat *
0x18004a328  lea     rcx, [rbp+var_10]; this
0x18004a32c  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x18004a331  mov     r13, [rbp+var_8]
0x18004a335  mov     ebx, eax
0x18004a337  mov     r15d, 80041001h
0x18004a33d  test    ebx, ebx
0x18004a33f  js      loc_18004A3EA
0x18004a345  lea     rcx, [rbp+var_30]
0x18004a349  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18004a34e  mov     rcx, [rbp+var_28]
0x18004a352  lea     r8, [rbp+var_30]
0x18004a356  xor     r9d, r9d
0x18004a359  mov     rax, [rcx]
0x18004a35c  lea     edx, [r9+1]
0x18004a360  mov     rax, [rax+18h]
0x18004a364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a369  mov     ebx, eax
0x18004a36b  cmp     eax, 1
0x18004a36e  jz      short loc_18004A3D5
0x18004a370  test    eax, eax
0x18004a372  js      short loc_18004A395
0x18004a374  mov     rcx, [rbp+var_30]
0x18004a378  lea     rdx, [r13+4]
0x18004a37c  movzx   eax, word ptr [rbp+var_C]
0x18004a380  lea     r8, [rbp+var_40]
0x18004a384  mov     dword ptr [rbp+var_40], eax
0x18004a387  mov     rax, [rcx]
0x18004a38a  mov     rax, [rax+20h]
0x18004a38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a393  mov     ebx, eax
0x18004a395  mov     [rbp+var_40], r12
0x18004a399  test    ebx, ebx
0x18004a39b  js      short loc_18004A3BE
0x18004a39d  lea     r8, [rbp+var_40]
0x18004a3a1  lea     rdx, [rbp+var_10]
0x18004a3a5  lea     rcx, [rdi+38h]
0x18004a3a9  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x18004a3ae  test    al, al
0x18004a3b0  jz      short loc_18004A3BE
0x18004a3b2  mov     rax, [rbp+var_40]
0x18004a3b6  cmp     [rax+14h], r12d
0x18004a3ba  cmovz   ebx, r15d
0x18004a3be  lea     rcx, [rbp+var_40]
0x18004a3c2  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x18004a3c7  lea     rcx, [rbp+var_30]
0x18004a3cb  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a3d0  jmp     loc_18004A33D
0x18004a3d5  lea     rcx, [rbp+var_30]
0x18004a3d9  mov     ebx, r12d
0x18004a3dc  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a3e1  lea     rcx, [rdi+38h]
0x18004a3e5  call    ?FreeHashTable@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@AEAAXXZ; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FreeHashTable(void)
0x18004a3ea  lea     rcx, [rbp+var_10]; this
0x18004a3ee  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004a3f3  test    ebx, ebx
0x18004a3f5  js      short loc_18004A434
0x18004a3f7  mov     r13, [rbp+arg_18]
0x18004a3fb  mov     r8d, 1
0x18004a401  lea     rcx, [rbp+var_30]
0x18004a405  mov     rdx, r13
0x18004a408  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x18004a40d  mov     edx, [rbp+arg_10]
0x18004a410  lea     rcx, [rdi+20h]
0x18004a414  mov     [rdi+18h], edx
0x18004a417  mov     rdx, rax
0x18004a41a  call    ??4?$SharedRefPtr@UIClockVector@@@@QEAAAEAV0@AEBV0@@Z; SharedRefPtr<IClockVector>::operator=(SharedRefPtr<IClockVector> const &)
0x18004a41f  mov     eax, [rbp+arg_20]
0x18004a422  lea     rcx, [rbp+var_30]
0x18004a426  mov     [rdi+28h], eax
0x18004a429  mov     eax, [rbp+arg_28]
0x18004a42c  mov     [rdi+2Ch], eax
0x18004a42f  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a434  lea     rcx, [rbp+var_28]
0x18004a438  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a43d  jmp     loc_18004A4E4
0x18004a442  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004a447  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18004a44c  mov     r15, rax
0x18004a44f  test    rax, rax
0x18004a452  jz      short loc_18004A49F
0x18004a454  mov     r8d, 1
0x18004a45a  lea     rcx, [rbp+var_30]
0x18004a45e  mov     rdx, r14
0x18004a461  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x18004a466  mov     r8d, 1
0x18004a46c  lea     rcx, [rbp+var_28]
0x18004a470  mov     rdx, r13
0x18004a473  mov     rbx, rax
0x18004a476  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x18004a47b  mov     ecx, [rbp+arg_28]
0x18004a47e  mov     r9, rbx
0x18004a481  mov     edx, [rbp+arg_10]
0x18004a484  mov     r8, rax
0x18004a487  mov     [rsp+70h+var_48], ecx
0x18004a48b  mov     ecx, [rbp+arg_20]
0x18004a48e  mov     [rsp+70h+var_50], ecx
0x18004a492  mov     rcx, r15
0x18004a495  call    ??0ItemChangeApplicationStatus@@QEAA@JAEBV?$SharedRefPtr@UIRecoverableErrorData@@@@AEBV?$SharedRefPtr@UISyncChange@@@@W4__MIDL___MIDL_itf_winsync_0000_0000_0001@@W4__MIDL___MIDL_itf_winsync_0000_0000_0003@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(long,SharedRefPtr<IRecoverableErrorData> const &,SharedRefPtr<ISyncChange> const &,__MIDL___MIDL_itf_winsync_0000_0000_0001,__MIDL___MIDL_itf_winsync_0000_0000_0003)
0x18004a49a  mov     edi, 3
0x18004a49f  mov     rdx, rax
0x18004a4a2  lea     rcx, [rbp+var_38]
0x18004a4a6  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x18004a4ab  mov     ebx, eax
0x18004a4ad  test    dil, 2
0x18004a4b1  jz      short loc_18004A4BF
0x18004a4b3  and     edi, 0FFFFFFFDh
0x18004a4b6  lea     rcx, [rbp+var_28]
0x18004a4ba  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a4bf  test    dil, 1
0x18004a4c3  jz      short loc_18004A4CE
0x18004a4c5  lea     rcx, [rbp+var_30]
0x18004a4c9  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004a4ce  test    ebx, ebx
0x18004a4d0  js      short loc_18004A4E4
0x18004a4d2  lea     r8, [rbp+var_38]
0x18004a4d6  mov     rcx, r12
0x18004a4d9  lea     rdx, [rbp+var_20]
0x18004a4dd  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x18004a4e2  mov     ebx, eax
0x18004a4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4eb  lea     rax, WPP_GLOBAL_Control
0x18004a4f2  cmp     rcx, rax
0x18004a4f5  jz      short loc_18004A523
0x18004a4f7  test    byte ptr [rcx+1Ch], 80h
0x18004a4fb  jz      short loc_18004A523
0x18004a4fd  cmp     byte ptr [rcx+19h], 5
0x18004a501  jb      short loc_18004A523
0x18004a503  mov     rcx, [rcx+10h]
0x18004a507  lea     r9, aChangeapplicat_45; "ChangeApplicationServices::ReportRecove"...
0x18004a50e  mov     edx, 25h ; '%'
0x18004a513  mov     [rsp+70h+var_50], ebx
0x18004a517  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004a51e  call    WPP_SF_sD
0x18004a523  lea     rcx, [rbp+var_38]
0x18004a527  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x18004a52c  lea     rcx, [rbp+var_20]; this
0x18004a530  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18004a535  lea     r11, [rsp+70h+var_s0]
0x18004a53a  mov     eax, ebx
0x18004a53c  mov     rbx, [r11+30h]
0x18004a540  mov     rdi, [r11+38h]
0x18004a544  mov     rsp, r11
0x18004a547  pop     r15
0x18004a549  pop     r14
0x18004a54b  pop     r13
0x18004a54d  pop     r12
0x18004a54f  pop     rbp
0x18004a550  retn
```
