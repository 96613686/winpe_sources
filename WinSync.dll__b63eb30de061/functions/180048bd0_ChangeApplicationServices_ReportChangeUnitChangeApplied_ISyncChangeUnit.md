# ChangeApplicationServices::ReportChangeUnitChangeApplied(ISyncChangeUnit *)

- ea: `0x180048bd0`
- end: `0x180048f06`
- name: `?ReportChangeUnitChangeApplied@ChangeApplicationServices@@UEAAJPEAUISyncChangeUnit@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(ChangeApplicationServices *__hidden this, struct ISyncChangeUnit *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x180007584`
- `0x18000a0f0`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x180046bb0`
- `0x180046dc4`
- `0x180046f80`
- `0x1800472c0`
- `0x1800487b0`
- `0x18004882c`
- `0x180048bd0`
- `0x18004a8fc`
- `0x180074678`
- `0x180074730`
- `0x18008387c`
- `0x180094010`

## string_xrefs

- `0x180048c0c`: `ChangeApplicationServices::ReportChangeUnitChangeApplied`
- `0x180048ea7`: `ChangeApplicationServices::ReportChangeUnitChangeApplied`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportChangeUnitChangeApplied(
        ChangeApplicationServices *this,
        struct ISyncChangeUnit *a2)
{
  int v4; // esi
  char *v5; // rbx
  __int64 v6; // rbx
  char *v7; // r15
  int v8; // r14d
  char v9; // al
  struct ISyncKnowledge *v10; // rdi
  char v11; // al
  bool v12; // zf
  ChangeApplicationServices *v13; // rcx
  void *v14; // rax
  void *v15; // rax
  _BYTE v17[4]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+34h] [rbp-1Ch]
  __int64 v19; // [rsp+38h] [rbp-18h]
  _BYTE v20[4]; // [rsp+40h] [rbp-10h] BYREF
  int v21; // [rsp+44h] [rbp-Ch]
  __int64 v22; // [rsp+48h] [rbp-8h]
  struct ISyncKnowledge *v23; // [rsp+88h] [rbp+38h] BYREF
  __int64 v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportChangeUnitChangeApplied");
  }
  if ( !a2 )
  {
    v4 = -2147467261;
LABEL_9:
    v24 = 0;
LABEL_10:
    v5 = (char *)this + 40;
    goto LABEL_11;
  }
  if ( (unsigned int)(*((_DWORD *)this + 9) - 2) > 1 )
  {
    v4 = -2147217407;
    goto LABEL_9;
  }
  v12 = *((_DWORD *)this + 56) == 0;
  v24 = 0;
  if ( !v12 )
  {
    v4 = -2147217370;
    goto LABEL_10;
  }
  v4 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, __int64 *))a2->lpVtbl->GetItemChange)(a2, &v24);
  if ( v4 < 0 )
    goto LABEL_10;
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  v5 = (char *)this + 40;
  v4 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)v24 + 80LL))(v24, &v23);
  if ( v4 >= 0 )
  {
    if ( v23 )
      v4 = ChangeApplicationServices::ValidateIdParameters(v13, (ChangeApplicationServices *)((char *)this + 40), v23);
    else
      v4 = -2147217399;
  }
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v23);
LABEL_11:
  v21 = 0;
  v22 = 0;
  if ( v4 >= 0 )
  {
    v4 = SyncId::InitializeForRetrieval((SyncId *)v20, (const struct IdFormat *)(v5 + 8));
    if ( v4 >= 0 )
    {
      LODWORD(v23) = (unsigned __int16)v21;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, struct ISyncKnowledge **))(*(_QWORD *)v24 + 32LL))(
             v24,
             v22 + 4,
             &v23);
    }
  }
  v18 = 0;
  v19 = 0;
  if ( v4 >= 0 )
  {
    v4 = SyncId::InitializeForRetrieval((SyncId *)v17, (const struct IdFormat *)(v5 + 16));
    if ( v4 >= 0 )
    {
      LODWORD(v23) = (unsigned __int16)v18;
      v4 = ((__int64 (__fastcall *)(struct ISyncChangeUnit *, __int64, struct ISyncKnowledge **))a2->lpVtbl->GetChangeUnitId)(
             a2,
             v19 + 4,
             &v23);
    }
  }
  v6 = 0;
  v23 = 0;
  v25 = 0;
  if ( v4 >= 0 )
  {
    v7 = (char *)this + 176;
    v8 = 0;
    v9 = HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(
           (char *)this + 176,
           v20,
           &v23);
    v10 = v23;
    if ( v9 )
    {
      if ( HIDWORD(v23[2].lpVtbl) != 1
        || (v11 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                    &v23[7],
                    v17,
                    &v25),
            v6 = v25,
            v11)
        && *(_DWORD *)(v25 + 20) != 1 )
      {
        v4 = -2147217407;
        goto LABEL_45;
      }
      v8 = 1;
      if ( v25 )
        *(_DWORD *)(v25 + 20) = 0;
    }
    if ( v10 )
      goto LABEL_38;
    v14 = SeAlloc(0x50u);
    if ( v14 )
      v14 = (void *)ItemChangeApplicationStatus::ItemChangeApplicationStatus(v14, 1, &v24);
    v4 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v23, v14);
    if ( v4 >= 0 )
    {
      v10 = v23;
LABEL_38:
      if ( v6 )
        goto LABEL_43;
      v15 = SeAlloc(0x28u);
      if ( v15 )
        v15 = (void *)ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(v15, 0);
      v4 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v25, v15);
      if ( v4 >= 0 )
      {
        v4 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
               &v10[7],
               v17,
               &v25);
        if ( v4 >= 0 )
        {
LABEL_43:
          if ( !v8 )
            v4 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
                   v7,
                   v20,
                   &v23);
        }
      }
    }
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportChangeUnitChangeApplied",
      v4);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v25);
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v23);
  SyncId::~SyncId((SyncId *)v17);
  SyncId::~SyncId((SyncId *)v20);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180048bd0  mov     [rsp-28h+arg_0], rbx
0x180048bd5  push    rbp
0x180048bd6  push    rsi
0x180048bd7  push    rdi
0x180048bd8  push    r14
0x180048bda  push    r15
0x180048bdc  mov     rbp, rsp
0x180048bdf  sub     rsp, 50h
0x180048be3  mov     r14, rdx
0x180048be6  mov     rdi, rcx
0x180048be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180048bf0  lea     rax, WPP_GLOBAL_Control
0x180048bf7  cmp     rcx, rax
0x180048bfa  jz      short loc_180048C24
0x180048bfc  test    byte ptr [rcx+1Ch], 80h
0x180048c00  jz      short loc_180048C24
0x180048c02  cmp     byte ptr [rcx+19h], 5
0x180048c06  jb      short loc_180048C24
0x180048c08  mov     rcx, [rcx+10h]
0x180048c0c  lea     r9, aChangeapplicat_44; "ChangeApplicationServices::ReportChange"...
0x180048c13  mov     edx, 1Eh
0x180048c18  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048c1f  call    WPP_SF_s
0x180048c24  test    r14, r14
0x180048c27  jnz     short loc_180048C30
0x180048c29  mov     esi, 80004003h
0x180048c2e  jmp     short loc_180048C44
0x180048c30  mov     eax, [rdi+24h]
0x180048c33  sub     eax, 2
0x180048c36  cmp     eax, 1
0x180048c39  jbe     loc_180048D58
0x180048c3f  mov     esi, 80041001h
0x180048c44  mov     [rbp+arg_10], 0
0x180048c4c  lea     rbx, [rdi+28h]
0x180048c50  mov     [rbp+var_C], 0
0x180048c57  mov     [rbp+var_8], 0
0x180048c5f  test    esi, esi
0x180048c61  js      short loc_180048C9B
0x180048c63  lea     rdx, [rbx+8]; struct IdFormat *
0x180048c67  lea     rcx, [rbp+var_10]; this
0x180048c6b  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180048c70  mov     esi, eax
0x180048c72  test    eax, eax
0x180048c74  js      short loc_180048C9B
0x180048c76  mov     rcx, [rbp+arg_10]
0x180048c7a  lea     r8, [rbp+arg_8]
0x180048c7e  movzx   eax, word ptr [rbp+var_C]
0x180048c82  mov     rdx, [rbp+var_8]
0x180048c86  mov     dword ptr [rbp+arg_8], eax
0x180048c89  add     rdx, 4
0x180048c8d  mov     rax, [rcx]
0x180048c90  mov     rax, [rax+20h]
0x180048c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c99  mov     esi, eax
0x180048c9b  mov     [rbp+var_1C], 0
0x180048ca2  mov     [rbp+var_18], 0
0x180048caa  test    esi, esi
0x180048cac  js      short loc_180048CE5
0x180048cae  lea     rdx, [rbx+10h]; struct IdFormat *
0x180048cb2  lea     rcx, [rbp+var_20]; this
0x180048cb6  call    ?InitializeForRetrieval@SyncId@@QEAAJAEBUIdFormat@@@Z; SyncId::InitializeForRetrieval(IdFormat const &)
0x180048cbb  mov     esi, eax
0x180048cbd  test    eax, eax
0x180048cbf  js      short loc_180048CE5
0x180048cc1  movzx   eax, word ptr [rbp+var_1C]
0x180048cc5  lea     r8, [rbp+arg_8]
0x180048cc9  mov     rdx, [rbp+var_18]
0x180048ccd  mov     rcx, r14
0x180048cd0  mov     dword ptr [rbp+arg_8], eax
0x180048cd3  add     rdx, 4
0x180048cd7  mov     rax, [r14]
0x180048cda  mov     rax, [rax+20h]
0x180048cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ce3  mov     esi, eax
0x180048ce5  xor     ebx, ebx
0x180048ce7  mov     [rbp+arg_8], 0
0x180048cef  mov     [rbp+arg_18], rbx
0x180048cf3  test    esi, esi
0x180048cf5  js      loc_180048E84
0x180048cfb  lea     r15, [rdi+0B0h]
0x180048d02  xor     r14d, r14d
0x180048d05  mov     rcx, r15
0x180048d08  lea     r8, [rbp+arg_8]
0x180048d0c  lea     rdx, [rbp+var_10]
0x180048d10  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x180048d15  mov     rdi, [rbp+arg_8]
0x180048d19  test    al, al
0x180048d1b  jz      loc_180048DF1
0x180048d21  cmp     dword ptr [rdi+14h], 1
0x180048d25  jnz     short loc_180048D4E
0x180048d27  lea     rcx, [rdi+38h]
0x180048d2b  lea     r8, [rbp+arg_18]
0x180048d2f  lea     rdx, [rbp+var_20]
0x180048d33  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180048d38  mov     rbx, [rbp+arg_18]
0x180048d3c  test    al, al
0x180048d3e  jz      loc_180048DDF
0x180048d44  cmp     dword ptr [rbx+14h], 1
0x180048d48  jz      loc_180048DDF
0x180048d4e  mov     esi, 80041001h
0x180048d53  jmp     loc_180048E84
0x180048d58  cmp     dword ptr [rdi+0E0h], 0
0x180048d5f  mov     [rbp+arg_10], 0
0x180048d67  jz      short loc_180048D73
0x180048d69  mov     esi, 80041026h
0x180048d6e  jmp     loc_180048C4C
0x180048d73  mov     rax, [r14]
0x180048d76  lea     rdx, [rbp+arg_10]
0x180048d7a  mov     rcx, r14
0x180048d7d  mov     rax, [rax+18h]
0x180048d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d86  mov     esi, eax
0x180048d88  test    eax, eax
0x180048d8a  js      loc_180048C4C
0x180048d90  lea     rcx, [rbp+arg_8]
0x180048d94  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180048d99  mov     rcx, [rbp+arg_10]
0x180048d9d  lea     rdx, [rbp+arg_8]
0x180048da1  mov     rax, [rcx]
0x180048da4  mov     rax, [rax+50h]
0x180048da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dad  lea     rbx, [rdi+28h]
0x180048db1  mov     esi, eax
0x180048db3  test    eax, eax
0x180048db5  js      short loc_180048DD1
0x180048db7  mov     r8, [rbp+arg_8]; struct ISyncKnowledge *
0x180048dbb  test    r8, r8
0x180048dbe  jz      short loc_180048DCC
0x180048dc0  mov     rdx, rbx; struct IdDescription *
0x180048dc3  call    ?ValidateIdParameters@ChangeApplicationServices@@AEAAJAEBUIdDescription@@PEAUISyncKnowledge@@@Z; ChangeApplicationServices::ValidateIdParameters(IdDescription const &,ISyncKnowledge *)
0x180048dc8  mov     esi, eax
0x180048dca  jmp     short loc_180048DD1
0x180048dcc  mov     esi, 80041009h
0x180048dd1  lea     rcx, [rbp+arg_8]
0x180048dd5  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048dda  jmp     loc_180048C50
0x180048ddf  mov     r14d, 1
0x180048de5  test    rbx, rbx
0x180048de8  jz      short loc_180048DF1
0x180048dea  mov     dword ptr [rbx+14h], 0
0x180048df1  test    rdi, rdi
0x180048df4  jnz     short loc_180048E28
0x180048df6  lea     ecx, [rdi+50h]; unsigned __int64
0x180048df9  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180048dfe  test    rax, rax
0x180048e01  jz      short loc_180048E12
0x180048e03  lea     r8, [rbp+arg_10]
0x180048e07  mov     rcx, rax
0x180048e0a  lea     edx, [rdi+1]
0x180048e0d  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x180048e12  mov     rdx, rax
0x180048e15  lea     rcx, [rbp+arg_8]
0x180048e19  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180048e1e  mov     esi, eax
0x180048e20  test    eax, eax
0x180048e22  js      short loc_180048E84
0x180048e24  mov     rdi, [rbp+arg_8]
0x180048e28  test    rbx, rbx
0x180048e2b  jnz     short loc_180048E6D
0x180048e2d  lea     ecx, [rbx+28h]; unsigned __int64
0x180048e30  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180048e35  test    rax, rax
0x180048e38  jz      short loc_180048E44
0x180048e3a  xor     edx, edx
0x180048e3c  mov     rcx, rax
0x180048e3f  call    ??0ChangeUnitChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@@Z; ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(ChangeApplicationReportStatus)
0x180048e44  mov     rdx, rax
0x180048e47  lea     rcx, [rbp+arg_18]
0x180048e4b  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180048e50  mov     esi, eax
0x180048e52  test    eax, eax
0x180048e54  js      short loc_180048E84
0x180048e56  lea     rcx, [rdi+38h]
0x180048e5a  lea     r8, [rbp+arg_18]
0x180048e5e  lea     rdx, [rbp+var_20]
0x180048e62  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> const &)
0x180048e67  mov     esi, eax
0x180048e69  test    eax, eax
0x180048e6b  js      short loc_180048E84
0x180048e6d  test    r14d, r14d
0x180048e70  jnz     short loc_180048E84
0x180048e72  lea     r8, [rbp+arg_8]
0x180048e76  mov     rcx, r15
0x180048e79  lea     rdx, [rbp+var_10]
0x180048e7d  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x180048e82  mov     esi, eax
0x180048e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e8b  lea     rax, WPP_GLOBAL_Control
0x180048e92  cmp     rcx, rax
0x180048e95  jz      short loc_180048EC3
0x180048e97  test    byte ptr [rcx+1Ch], 80h
0x180048e9b  jz      short loc_180048EC3
0x180048e9d  cmp     byte ptr [rcx+19h], 5
0x180048ea1  jb      short loc_180048EC3
0x180048ea3  mov     rcx, [rcx+10h]
0x180048ea7  lea     r9, aChangeapplicat_44; "ChangeApplicationServices::ReportChange"...
0x180048eae  mov     edx, 1Fh
0x180048eb3  mov     [rsp+50h+var_30], esi
0x180048eb7  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048ebe  call    WPP_SF_sD
0x180048ec3  lea     rcx, [rbp+arg_18]
0x180048ec7  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x180048ecc  lea     rcx, [rbp+arg_8]
0x180048ed0  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x180048ed5  lea     rcx, [rbp+var_20]; this
0x180048ed9  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180048ede  lea     rcx, [rbp+var_10]; this
0x180048ee2  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180048ee7  lea     rcx, [rbp+arg_10]
0x180048eeb  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180048ef0  mov     rbx, [rsp+50h+arg_0]
0x180048ef8  mov     eax, esi
0x180048efa  add     rsp, 50h
0x180048efe  pop     r15
0x180048f00  pop     r14
0x180048f02  pop     rdi
0x180048f03  pop     rsi
0x180048f04  pop     rbp
0x180048f05  retn
```
