# ChangeApplicationServices::ReportItemChangeApplied(ISyncChange *)

- ea: `0x180049520`
- end: `0x180049942`
- name: `?ReportItemChangeApplied@ChangeApplicationServices@@UEAAJPEAUISyncChange@@@Z`
- size: `1058`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChange *)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x18000a0f0`
- `0x18000a9e0`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x18001ff00`
- `0x180046a54`
- `0x180046bb0`
- `0x180046f80`
- `0x1800472c0`
- `0x1800487b0`
- `0x18004882c`
- `0x180049520`
- `0x18004a8fc`
- `0x180074730`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x18004956e`: `ChangeApplicationServices::ReportItemChangeApplied`
- `0x180049903`: `ChangeApplicationServices::ReportItemChangeApplied`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportItemChangeApplied(
        ChangeApplicationServices *this,
        struct ISyncChange *a2)
{
  __int64 v2; // r13
  char v4; // r12
  PVOID *v6; // rcx
  int v7; // edi
  ChangeApplicationServices *v8; // rcx
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // r14
  int HashValue; // eax
  int v16; // ecx
  int ExistingBucket; // eax
  void *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v23; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v25[4]; // [rsp+40h] [rbp-20h] BYREF
  int v26; // [rsp+44h] [rbp-1Ch]
  __int64 v27; // [rsp+48h] [rbp-18h]
  _BYTE v28[4]; // [rsp+50h] [rbp-10h] BYREF
  int v29; // [rsp+54h] [rbp-Ch]
  __int64 v30; // [rsp+58h] [rbp-8h]
  struct ISyncKnowledge *v31; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  v4 = 0;
  LODWORD(v31) = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportItemChangeApplied");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( (unsigned int)(*((_DWORD *)this + 9) - 2) <= 1 )
    {
      if ( *((_DWORD *)this + 56) )
      {
        v7 = -2147217370;
      }
      else
      {
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        v7 = ((__int64 (__fastcall *)(struct ISyncChange *, struct ISyncKnowledge **))a2->lpVtbl->GetMadeWithKnowledge)(
               a2,
               &v31);
        if ( v7 >= 0 )
        {
          if ( v31 )
            v7 = ChangeApplicationServices::ValidateIdParameters(
                   v8,
                   (ChangeApplicationServices *)((char *)this + 40),
                   v31);
          else
            v7 = -2147217399;
        }
        SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v31);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      v7 = -2147217407;
    }
  }
  else
  {
    v7 = -2147467261;
  }
  v29 = 0;
  v30 = 0;
  if ( v7 < 0 )
    goto LABEL_60;
  v7 = SyncId::InitializeForRetrieval((SyncId *)v28, (ChangeApplicationServices *)((char *)this + 48));
  if ( v7 < 0 )
    goto LABEL_59;
  LODWORD(v31) = (unsigned __int16)v29;
  v7 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64, struct ISyncKnowledge **))a2->lpVtbl->GetRootItemId)(
         a2,
         v30 + 4,
         &v31);
  if ( v7 < 0 )
    goto LABEL_59;
  v32 = 0;
  if ( !(unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
                           (char *)this + 176,
                           v28,
                           &v32) )
  {
    v18 = SeAlloc(0x50u);
    if ( v18 )
    {
      v19 = SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(&v31, a2, 1);
      v20 = ItemChangeApplicationStatus::ItemChangeApplicationStatus(v18, 0, v19);
      v4 = 1;
    }
    else
    {
      v20 = 0;
    }
    v7 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v32, v20);
    if ( (v4 & 1) != 0 )
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v31);
    if ( v7 >= 0 )
      v7 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
             (char *)this + 176,
             v28,
             &v32);
    goto LABEL_56;
  }
  v9 = v32;
  if ( *(_DWORD *)(v32 + 20) != 1 )
    v7 = -2147217407;
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( v7 < 0 )
    goto LABEL_48;
  v10 = ((__int64 (__fastcall *)(struct ISyncChange *, __int64 *))a2->lpVtbl->GetChangeUnits)(a2, &v23);
  v7 = v10;
  if ( v10 == -2147217393 )
  {
    v7 = 0;
  }
  else if ( v10 < 0 )
  {
    goto LABEL_48;
  }
  if ( !v23 || !*(_DWORD *)(v9 + 72) )
  {
LABEL_47:
    *(_DWORD *)(v9 + 20) = 0;
    goto LABEL_48;
  }
  v11 = (*(__int64 (**)(void))(*(_QWORD *)v23 + 40LL))();
  v26 = 0;
  v7 = v11;
  v27 = 0;
  if ( v11 >= 0 )
  {
    v12 = SyncId::InitializeForRetrieval((SyncId *)v25, (ChangeApplicationServices *)((char *)this + 56));
    v2 = v27;
    v7 = v12;
  }
  while ( v7 >= 0 )
  {
    ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, 1, &v33);
    v7 = v13;
    if ( v13 == 1 )
    {
      v7 = 0;
      SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v33);
      break;
    }
    if ( v13 >= 0 )
    {
      LODWORD(v31) = (unsigned __int16)v26;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, struct ISyncKnowledge **))(*(_QWORD *)v33 + 32LL))(
             v33,
             v2 + 4,
             &v31);
    }
    v24 = 0;
    if ( v7 >= 0
      && (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                            v9 + 56,
                            v25,
                            &v24) )
    {
      if ( *(_DWORD *)(v24 + 20) == 1 )
      {
        v7 = -2147217407;
        goto LABEL_44;
      }
      if ( !*(_DWORD *)(v24 + 20) )
      {
        v14 = *(_QWORD *)(v9 + 64);
        LODWORD(v31) = 0;
        if ( !v14 )
          goto LABEL_43;
        HashValue = SyncId::GetHashValue((SyncId *)v25);
        ExistingBucket = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FindExistingBucket(
                           v16,
                           HashValue,
                           (unsigned int)v25,
                           v14,
                           *(_DWORD *)(v9 + 56),
                           (__int64)&v31);
        v7 = ExistingBucket;
        if ( !ExistingBucket )
        {
          *(_BYTE *)(32LL * (unsigned int)v31 + v14 + 24) &= ~1u;
          --*(_DWORD *)(v9 + 72);
          goto LABEL_44;
        }
        if ( ExistingBucket == 1 )
LABEL_43:
          v7 = -2147024809;
      }
    }
LABEL_44:
    SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v24);
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v33);
  }
  SyncId::~SyncId((SyncId *)v25);
  if ( v7 >= 0 )
    goto LABEL_47;
LABEL_48:
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v23);
LABEL_56:
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v32);
  if ( v7 >= 0 )
  {
    ++*((_DWORD *)this + 54);
    v21 = *((_QWORD *)this + 19);
    if ( v21 )
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
             v21,
             *((unsigned int *)this + 54),
             *((unsigned int *)this + 55));
  }
LABEL_59:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_60:
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      29,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportItemChangeApplied",
      v7);
  SyncId::~SyncId((SyncId *)v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180049520  mov     [rsp-38h+arg_0], rbx
0x180049525  push    rbp
0x180049526  push    rsi
0x180049527  push    rdi
0x180049528  push    r12
0x18004952a  push    r13
0x18004952c  push    r14
0x18004952e  push    r15
0x180049530  mov     rbp, rsp
0x180049533  sub     rsp, 60h
0x180049537  xor     r13d, r13d
0x18004953a  mov     r14, rdx
0x18004953d  mov     r12d, r13d
0x180049540  mov     dword ptr [rbp+arg_8], r13d
0x180049544  mov     rsi, rcx
0x180049547  mov     rcx, cs:WPP_GLOBAL_Control
0x18004954e  lea     rax, WPP_GLOBAL_Control
0x180049555  cmp     rcx, rax
0x180049558  jz      short loc_180049588
0x18004955a  test    byte ptr [rcx+1Ch], 80h
0x18004955e  jz      short loc_180049588
0x180049560  cmp     byte ptr [rcx+19h], 5
0x180049564  jb      short loc_180049588
0x180049566  mov     rcx, [rcx+10h]
0x18004956a  lea     edx, [r13+1Ch]
0x18004956e  lea     r9, aChangeapplicat_37; "ChangeApplicationServices::ReportItemCh"...
0x180049575  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004957c  call    WPP_SF_s
0x180049581  mov     rcx, cs:WPP_GLOBAL_Control
0x180049588  test    r14, r14
0x18004958b  jnz     short loc_180049594
0x18004958d  mov     edi, 80004003h
0x180049592  jmp     short loc_180049603
0x180049594  mov     eax, [rsi+24h]
0x180049597  sub     eax, 2
0x18004959a  cmp     eax, 1
0x18004959d  jbe     short loc_1800495A6
0x18004959f  mov     edi, 80041001h
0x1800495a4  jmp     short loc_180049603
0x1800495a6  cmp     [rsi+0E0h], r13d
0x1800495ad  jz      short loc_1800495B6
0x1800495af  mov     edi, 80041026h
0x1800495b4  jmp     short loc_180049603
0x1800495b6  lea     rcx, [rbp+arg_8]
0x1800495ba  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x1800495bf  mov     rcx, [r14]
0x1800495c2  lea     rdx, [rbp+arg_8]
0x1800495c6  mov     rax, [rcx+50h]
0x1800495ca  mov     rcx, r14
0x1800495cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495d2  mov     edi, eax
0x1800495d4  test    eax, eax
0x1800495d6  js      short loc_1800495F3
0x1800495d8  mov     r8, [rbp+arg_8]; struct ISyncKnowledge *
0x1800495dc  test    r8, r8
0x1800495df  jnz     short loc_1800495E8
0x1800495e1  mov     edi, 80041009h
0x1800495e6  jmp     short loc_1800495F3
0x1800495e8  lea     rdx, [rsi+28h]; struct IdDescription *
0x1800495ec  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x1800495f1  mov     edi, eax
0x1800495f3  lea     rcx, [rbp+arg_8]
0x1800495f7  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x1800495fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180049603  mov     [rbp+var_C], r13d
0x180049607  mov     [rbp+var_8], r13
0x18004960b  test    edi, edi
0x18004960d  js      loc_1800498E7
0x180049613  lea     rdx, [rsi+30h]; struct IdFormat *
0x180049617  lea     rcx, [rbp+var_10]; this
0x18004961b  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180049620  mov     edi, eax
0x180049622  test    eax, eax
0x180049624  js      loc_1800498E0
0x18004962a  movzx   eax, word ptr [rbp+var_C]
0x18004962e  lea     r8, [rbp+arg_8]
0x180049632  mov     rdx, [rbp+var_8]
0x180049636  mov     rcx, r14
0x180049639  mov     dword ptr [rbp+arg_8], eax
0x18004963c  add     rdx, 4
0x180049640  mov     rax, [r14]
0x180049643  mov     rax, [rax+20h]
0x180049647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004964c  mov     edi, eax
0x18004964e  test    eax, eax
0x180049650  js      loc_1800498E0
0x180049656  lea     r15, [rsi+0B0h]
0x18004965d  mov     [rbp+arg_10], r13
0x180049661  mov     rcx, r15
0x180049664  lea     r8, [rbp+arg_10]
0x180049668  lea     rdx, [rbp+var_10]
0x18004966c  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x180049671  test    al, al
0x180049673  jz      loc_180049838
0x180049679  mov     rbx, [rbp+arg_10]
0x18004967d  lea     rcx, [rbp+var_30]
0x180049681  mov     eax, 80041001h
0x180049686  cmp     dword ptr [rbx+14h], 1
0x18004968a  cmovnz  edi, eax
0x18004968d  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180049692  test    edi, edi
0x180049694  js      loc_18004982D
0x18004969a  mov     rax, [r14]
0x18004969d  lea     rdx, [rbp+var_30]
0x1800496a1  mov     rcx, r14
0x1800496a4  mov     rax, [rax+48h]
0x1800496a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496ad  mov     edi, eax
0x1800496af  cmp     eax, 8004100Fh
0x1800496b4  jnz     short loc_1800496BB
0x1800496b6  mov     edi, r13d
0x1800496b9  jmp     short loc_1800496C3
0x1800496bb  test    eax, eax
0x1800496bd  js      loc_18004982D
0x1800496c3  mov     rcx, [rbp+var_30]
0x1800496c7  test    rcx, rcx
0x1800496ca  jz      loc_180049829
0x1800496d0  cmp     [rbx+48h], r13d
0x1800496d4  jbe     loc_180049829
0x1800496da  mov     rax, [rcx]
0x1800496dd  mov     rax, [rax+28h]
0x1800496e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496e6  mov     [rbp+var_1C], r13d
0x1800496ea  mov     edi, eax
0x1800496ec  mov     [rbp+var_18], r13
0x1800496f0  test    eax, eax
0x1800496f2  js      short loc_180049707
0x1800496f4  lea     rdx, [rsi+38h]; struct IdFormat *
0x1800496f8  lea     rcx, [rbp+var_20]; this
0x1800496fc  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180049701  mov     r13, [rbp+var_18]
0x180049705  mov     edi, eax
0x180049707  test    edi, edi
0x180049709  js      loc_180049819
0x18004970f  lea     rcx, [rbp+arg_18]
0x180049713  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180049718  mov     rcx, [rbp+var_30]
0x18004971c  lea     r8, [rbp+arg_18]
0x180049720  xor     r9d, r9d
0x180049723  mov     rax, [rcx]
0x180049726  lea     edx, [r9+1]
0x18004972a  mov     rax, [rax+18h]
0x18004972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049733  mov     edi, eax
0x180049735  cmp     eax, 1
0x180049738  jz      loc_180049808
0x18004973e  test    eax, eax
0x180049740  js      short loc_180049763
0x180049742  mov     rcx, [rbp+arg_18]
0x180049746  lea     rdx, [r13+4]
0x18004974a  movzx   eax, word ptr [rbp+var_1C]
0x18004974e  lea     r8, [rbp+arg_8]
0x180049752  mov     dword ptr [rbp+arg_8], eax
0x180049755  mov     rax, [rcx]
0x180049758  mov     rax, [rax+20h]
0x18004975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049761  mov     edi, eax
0x180049763  mov     [rbp+var_28], r12
0x180049767  test    edi, edi
0x180049769  js      loc_1800497F1
0x18004976f  lea     r8, [rbp+var_28]
0x180049773  lea     rdx, [rbp+var_20]
0x180049777  lea     rcx, [rbx+38h]
0x18004977b  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180049780  test    al, al
0x180049782  jz      short loc_1800497F1
0x180049784  mov     rax, [rbp+var_28]
0x180049788  cmp     dword ptr [rax+14h], 1
0x18004978c  jnz     short loc_180049795
0x18004978e  mov     edi, 80041001h
0x180049793  jmp     short loc_1800497F1
0x180049795  cmp     [rax+14h], r12d
0x180049799  jnz     short loc_1800497F1
0x18004979b  mov     r14, [rbx+40h]
0x18004979f  mov     dword ptr [rbp+arg_8], r12d
0x1800497a3  test    r14, r14
0x1800497a6  jz      short loc_1800497EC
0x1800497a8  lea     rcx, [rbp+var_20]; this
0x1800497ac  call    ?GetHashValue@SyncId@@QEBAKXZ; SyncId::GetHashValue(void)
0x1800497b1  mov     edx, eax
0x1800497b3  lea     r8, [rbp+var_20]
0x1800497b7  lea     rax, [rbp+arg_8]
0x1800497bb  mov     r9, r14
0x1800497be  mov     [rsp+60h+var_38], rax
0x1800497c3  mov     eax, [rbx+38h]
0x1800497c6  mov     [rsp+60h+var_40], eax
0x1800497ca  call    ?FindExistingBucket@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@AEBAJKAEBVSyncId@@PEAV?$TableBucket@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@KPEAK@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FindExistingBucket(ulong,SyncId const &,TableBucket<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext> *,ulong,ulong *)
0x1800497cf  mov     edi, eax
0x1800497d1  test    eax, eax
0x1800497d3  jnz     short loc_1800497E7
0x1800497d5  mov     eax, dword ptr [rbp+arg_8]
0x1800497d8  shl     rax, 5
0x1800497dc  and     byte ptr [rax+r14+18h], 0FEh
0x1800497e2  dec     dword ptr [rbx+48h]
0x1800497e5  jmp     short loc_1800497F1
0x1800497e7  cmp     eax, 1
0x1800497ea  jnz     short loc_1800497F1
0x1800497ec  mov     edi, 80070057h
0x1800497f1  lea     rcx, [rbp+var_28]
0x1800497f5  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x1800497fa  lea     rcx, [rbp+arg_18]
0x1800497fe  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049803  jmp     loc_180049707
0x180049808  xor     r13d, r13d
0x18004980b  lea     rcx, [rbp+arg_18]
0x18004980f  mov     edi, r13d
0x180049812  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049817  jmp     short loc_18004981C
0x180049819  xor     r13d, r13d
0x18004981c  lea     rcx, [rbp+var_20]; this
0x180049820  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180049825  test    edi, edi
0x180049827  js      short loc_18004982D
0x180049829  mov     [rbx+14h], r13d
0x18004982d  lea     rcx, [rbp+var_30]
0x180049831  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049836  jmp     short loc_1800498A6
0x180049838  mov     ecx, 50h ; 'P'; unsigned __int64
0x18004983d  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049842  mov     rbx, rax
0x180049845  test    rax, rax
0x180049848  jz      short loc_180049870
0x18004984a  mov     edi, 1
0x18004984f  lea     rcx, [rbp+arg_8]
0x180049853  mov     r8d, edi
0x180049856  mov     rdx, r14
0x180049859  call    ??0?$SharedRefPtr@UISyncChange@@@@QEAA@PEAUISyncChange@@H@Z; SharedRefPtr<ISyncChange>::SharedRefPtr<ISyncChange>(ISyncChange *,int)
0x18004985e  mov     r8, rax
0x180049861  xor     edx, edx
0x180049863  mov     rcx, rbx
0x180049866  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x18004986b  mov     r12d, edi
0x18004986e  jmp     short loc_180049873
0x180049870  mov     rax, r13
0x180049873  mov     rdx, rax
0x180049876  lea     rcx, [rbp+arg_10]
0x18004987a  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x18004987f  mov     edi, eax
0x180049881  test    r12b, 1
0x180049885  jz      short loc_180049890
0x180049887  lea     rcx, [rbp+arg_8]
0x18004988b  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049890  test    edi, edi
0x180049892  js      short loc_1800498A6
0x180049894  lea     r8, [rbp+arg_10]
0x180049898  mov     rcx, r15
0x18004989b  lea     rdx, [rbp+var_10]
0x18004989f  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x1800498a4  mov     edi, eax
0x1800498a6  lea     rcx, [rbp+arg_10]
0x1800498aa  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x1800498af  test    edi, edi
0x1800498b1  js      short loc_1800498E0
0x1800498b3  inc     dword ptr [rsi+0D8h]
0x1800498b9  mov     rcx, [rsi+98h]
0x1800498c0  test    rcx, rcx
0x1800498c3  jz      short loc_1800498E0
0x1800498c5  mov     rax, [rcx]
0x1800498c8  mov     r8d, [rsi+0DCh]
0x1800498cf  mov     edx, [rsi+0D8h]
0x1800498d5  mov     rax, [rax+40h]
0x1800498d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498de  mov     edi, eax
0x1800498e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800498e7  lea     rax, WPP_GLOBAL_Control
0x1800498ee  cmp     rcx, rax
0x1800498f1  jz      short loc_18004991F
0x1800498f3  test    byte ptr [rcx+1Ch], 80h
0x1800498f7  jz      short loc_18004991F
0x1800498f9  cmp     byte ptr [rcx+19h], 5
0x1800498fd  jb      short loc_18004991F
0x1800498ff  mov     rcx, [rcx+10h]
0x180049903  lea     r9, aChangeapplicat_37; "ChangeApplicationServices::ReportItemCh"...
0x18004990a  mov     edx, 1Dh
0x18004990f  mov     [rsp+60h+var_40], edi
0x180049913  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x18004991a  call    WPP_SF_sD
0x18004991f  lea     rcx, [rbp+var_10]; this
0x180049923  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180049928  mov     rbx, [rsp+60h+arg_0]
0x180049930  mov     eax, edi
0x180049932  add     rsp, 60h
0x180049936  pop     r15
0x180049938  pop     r14
0x18004993a  pop     r13
0x18004993c  pop     r12
0x18004993e  pop     rdi
0x18004993f  pop     rsi
0x180049940  pop     rbp
0x180049941  retn
```
