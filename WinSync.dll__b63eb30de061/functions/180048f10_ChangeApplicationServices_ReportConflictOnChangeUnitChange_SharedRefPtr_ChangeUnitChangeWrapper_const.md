# ChangeApplicationServices::ReportConflictOnChangeUnitChange(SharedRefPtr<ChangeUnitChangeWrapper> const &)

- ea: `0x180048f10`
- end: `0x180049112`
- name: `?ReportConflictOnChangeUnitChange@ChangeApplicationServices@@UEAAJAEBV?$SharedRefPtr@VChangeUnitChangeWrapper@@@@@Z`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180046bb0`
- `0x180046dc4`
- `0x180046f80`
- `0x1800472c0`
- `0x1800487b0`
- `0x18004882c`
- `0x180048f10`
- `0x180074678`
- `0x180074730`
- `0x180094010`

## string_xrefs

- `0x180048f4c`: `ChangeApplicationServices::ReportConflictOnChangeUnitChange`
- `0x1800490d1`: `ChangeApplicationServices::ReportConflictOnChangeUnitChange`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportConflictOnChangeUnitChange(__int64 a1, __int64 *a2)
{
  __int64 v4; // r15
  __int64 v5; // rdx
  char v6; // al
  __int64 v7; // rbx
  int v8; // edi
  int v9; // r14d
  __int64 v10; // rcx
  void *v11; // rax
  int v12; // eax
  void *v13; // rax
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportConflictOnChangeUnitChange");
  }
  v4 = a1 + 168;
  v5 = *a2 + 64;
  v16 = 0;
  v6 = HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(a1 + 168, v5, &v16);
  v7 = v16;
  if ( v6 )
  {
    if ( *(_DWORD *)(v16 + 20) != 2 )
    {
      v8 = -2147217407;
      v15 = 0;
      goto LABEL_27;
    }
    v8 = 0;
    v9 = 0;
  }
  else
  {
    v9 = 0;
    v8 = 0;
  }
  if ( !v16 )
  {
    v10 = *a2;
    v15 = 0;
    v9 = 1;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 24LL))(v10, &v15);
    if ( v8 >= 0 )
    {
      v11 = SeAlloc(0x50u);
      if ( v11 )
        v11 = (void *)ItemChangeApplicationStatus::ItemChangeApplicationStatus(v11, 2, &v15);
      v12 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v16, v11);
      v7 = v16;
      v8 = v12;
    }
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v15);
  }
  v15 = 0;
  if ( v8 >= 0 )
  {
    if ( (unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                            v7 + 56,
                            *a2 + 80,
                            &v15) )
    {
      v8 = -2147217407;
      if ( *(_DWORD *)(v15 + 20) == 2 )
        v8 = -2147217379;
    }
    else
    {
      v13 = SeAlloc(0x28u);
      if ( v13 )
        v13 = (void *)ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(v13, 2);
      v8 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v15, v13);
      if ( v8 >= 0 )
      {
        v8 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
               v7 + 56,
               *a2 + 80,
               &v15);
        if ( v8 >= 0 )
        {
          if ( v9 )
            v8 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
                   v4,
                   *a2 + 64,
                   &v16);
        }
      }
    }
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportConflictOnChangeUnitChange",
      v8);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v15);
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180048f10  mov     [rsp-28h+arg_0], rbx
0x180048f15  push    rbp
0x180048f16  push    rsi
0x180048f17  push    rdi
0x180048f18  push    r14
0x180048f1a  push    r15
0x180048f1c  mov     rbp, rsp
0x180048f1f  sub     rsp, 30h
0x180048f23  mov     rsi, rdx
0x180048f26  mov     rbx, rcx
0x180048f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180048f30  lea     rax, WPP_GLOBAL_Control
0x180048f37  cmp     rcx, rax
0x180048f3a  jz      short loc_180048F64
0x180048f3c  test    byte ptr [rcx+1Ch], 80h
0x180048f40  jz      short loc_180048F64
0x180048f42  cmp     byte ptr [rcx+19h], 5
0x180048f46  jb      short loc_180048F64
0x180048f48  mov     rcx, [rcx+10h]
0x180048f4c  lea     r9, aChangeapplicat_32; "ChangeApplicationServices::ReportConfli"...
0x180048f53  mov     edx, 2Ch ; ','
0x180048f58  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048f5f  call    WPP_SF_s
0x180048f64  mov     rdx, [rsi]
0x180048f67  lea     r15, [rbx+0A8h]
0x180048f6e  add     rdx, 40h ; '@'
0x180048f72  mov     [rbp+arg_18], 0
0x180048f7a  mov     rcx, r15
0x180048f7d  lea     r8, [rbp+arg_18]
0x180048f81  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x180048f86  mov     rbx, [rbp+arg_18]
0x180048f8a  test    al, al
0x180048f8c  jz      short loc_180048FAD
0x180048f8e  cmp     dword ptr [rbx+14h], 2
0x180048f92  jnz     short loc_180048F9B
0x180048f94  xor     edi, edi
0x180048f96  xor     r14d, r14d
0x180048f99  jmp     short loc_180048FB2
0x180048f9b  mov     edi, 80041001h
0x180048fa0  mov     [rbp+arg_10], 0
0x180048fa8  jmp     loc_1800490AE
0x180048fad  xor     r14d, r14d
0x180048fb0  xor     edi, edi
0x180048fb2  test    rbx, rbx
0x180048fb5  jnz     short loc_18004900F
0x180048fb7  mov     rcx, [rsi]
0x180048fba  lea     rdx, [rbp+arg_10]
0x180048fbe  mov     [rbp+arg_10], rbx
0x180048fc2  lea     r14d, [rbx+1]
0x180048fc6  mov     rax, [rcx]
0x180048fc9  mov     rax, [rax+18h]
0x180048fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fd2  mov     edi, eax
0x180048fd4  test    eax, eax
0x180048fd6  js      short loc_180049006
0x180048fd8  lea     ecx, [rbx+50h]; unsigned __int64
0x180048fdb  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180048fe0  test    rax, rax
0x180048fe3  jz      short loc_180048FF4
0x180048fe5  lea     r8, [rbp+arg_10]
0x180048fe9  mov     rcx, rax
0x180048fec  lea     edx, [rbx+2]
0x180048fef  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x180048ff4  mov     rdx, rax
0x180048ff7  lea     rcx, [rbp+arg_18]
0x180048ffb  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049000  mov     rbx, [rbp+arg_18]
0x180049004  mov     edi, eax
0x180049006  lea     rcx, [rbp+arg_10]
0x18004900a  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x18004900f  mov     [rbp+arg_10], 0
0x180049017  test    edi, edi
0x180049019  js      loc_1800490AE
0x18004901f  mov     rdx, [rsi]
0x180049022  lea     r8, [rbp+arg_10]
0x180049026  add     rdx, 50h ; 'P'
0x18004902a  lea     rcx, [rbx+38h]
0x18004902e  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180049033  test    al, al
0x180049035  jz      short loc_18004904C
0x180049037  mov     rax, [rbp+arg_10]
0x18004903b  mov     edi, 80041001h
0x180049040  cmp     dword ptr [rax+14h], 2
0x180049044  lea     ecx, [rdi+1Ch]
0x180049047  cmovz   edi, ecx
0x18004904a  jmp     short loc_1800490AE
0x18004904c  mov     ecx, 28h ; '('; unsigned __int64
0x180049051  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049056  test    rax, rax
0x180049059  jz      short loc_180049068
0x18004905b  mov     edx, 2
0x180049060  mov     rcx, rax
0x180049063  call    ??0ChangeUnitChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@@Z; ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(ChangeApplicationReportStatus)
0x180049068  mov     rdx, rax
0x18004906b  lea     rcx, [rbp+arg_10]
0x18004906f  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049074  mov     edi, eax
0x180049076  test    eax, eax
0x180049078  js      short loc_1800490AE
0x18004907a  mov     rdx, [rsi]
0x18004907d  lea     r8, [rbp+arg_10]
0x180049081  add     rdx, 50h ; 'P'
0x180049085  lea     rcx, [rbx+38h]
0x180049089  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> const &)
0x18004908e  mov     edi, eax
0x180049090  test    eax, eax
0x180049092  js      short loc_1800490AE
0x180049094  test    r14d, r14d
0x180049097  jz      short loc_1800490AE
0x180049099  mov     rdx, [rsi]
0x18004909c  lea     r8, [rbp+arg_18]
0x1800490a0  add     rdx, 40h ; '@'
0x1800490a4  mov     rcx, r15
0x1800490a7  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x1800490ac  mov     edi, eax
0x1800490ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800490b5  lea     rax, WPP_GLOBAL_Control
0x1800490bc  cmp     rcx, rax
0x1800490bf  jz      short loc_1800490ED
0x1800490c1  test    byte ptr [rcx+1Ch], 80h
0x1800490c5  jz      short loc_1800490ED
0x1800490c7  cmp     byte ptr [rcx+19h], 5
0x1800490cb  jb      short loc_1800490ED
0x1800490cd  mov     rcx, [rcx+10h]
0x1800490d1  lea     r9, aChangeapplicat_32; "ChangeApplicationServices::ReportConfli"...
0x1800490d8  mov     edx, 2Dh ; '-'
0x1800490dd  mov     [rsp+30h+var_10], edi
0x1800490e1  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800490e8  call    WPP_SF_sD
0x1800490ed  lea     rcx, [rbp+arg_10]
0x1800490f1  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x1800490f6  lea     rcx, [rbp+arg_18]
0x1800490fa  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x1800490ff  mov     rbx, [rsp+30h+arg_0]
0x180049104  mov     eax, edi
0x180049106  add     rsp, 30h
0x18004910a  pop     r15
0x18004910c  pop     r14
0x18004910e  pop     rdi
0x18004910f  pop     rsi
0x180049110  pop     rbp
0x180049111  retn
```
