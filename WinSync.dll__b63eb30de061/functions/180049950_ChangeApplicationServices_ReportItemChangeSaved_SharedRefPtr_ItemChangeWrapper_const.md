# ChangeApplicationServices::ReportItemChangeSaved(SharedRefPtr<ItemChangeWrapper> const &)

- ea: `0x180049950`
- end: `0x180049bee`
- name: `?ReportItemChangeSaved@ChangeApplicationServices@@UEAAJAEBV?$SharedRefPtr@VItemChangeWrapper@@@@@Z`
- size: `670`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task`

## callees

- `0x180005e8c`
- `0x1800084ec`
- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180046bb0`
- `0x180046dc4`
- `0x180046f80`
- `0x1800472c0`
- `0x1800487b0`
- `0x18004882c`
- `0x180049950`
- `0x180074678`
- `0x180074730`
- `0x180094010`

## string_xrefs

- `0x180049990`: `ChangeApplicationServices::ReportItemChangeSaved`
- `0x180049baf`: `ChangeApplicationServices::ReportItemChangeSaved`

## pseudocode

```c
__int64 __fastcall ChangeApplicationServices::ReportItemChangeSaved(__int64 a1, __int64 *a2)
{
  unsigned int v4; // r12d
  __int64 v5; // rdx
  char v6; // al
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rbx
  int v10; // esi
  void *v11; // rax
  __int64 NextElement; // rax
  void *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD v17[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+90h] [rbp+50h] BYREF
  __int64 v19; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReportItemChangeSaved");
  }
  v4 = 0;
  v5 = *a2 + 152;
  v18 = 0;
  v6 = HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(a1 + 168, v5, &v18);
  v7 = *a2;
  if ( v6 )
  {
    v8 = 0;
    v9 = v18;
    if ( !*(_DWORD *)(v7 + 232) || *(_DWORD *)(v18 + 20) == 1 )
    {
      if ( !*(_DWORD *)(v18 + 20) )
      {
        v8 = -2147217379;
        goto LABEL_32;
      }
LABEL_19:
      v10 = 0;
      goto LABEL_29;
    }
    v10 = 1;
    do
    {
      v19 = 0;
      if ( v8 >= 0 )
      {
        v17[0] = *(_QWORD *)(v7 + 248);
        if ( !(unsigned __int8)HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(
                                 v9 + 56,
                                 *(_QWORD *)(v17[0] + 8LL * v4) + 80LL,
                                 &v19) )
        {
          v11 = SeAlloc(0x28u);
          if ( v11 )
            v11 = (void *)ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(v11, 0);
          v8 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v19, v11);
          if ( v8 >= 0 )
            v8 = HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
                   v9 + 56,
                   *(_QWORD *)(v17[0] + 8LL * v4) + 80LL,
                   &v19);
        }
      }
      SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v19);
      v7 = *a2;
      ++v4;
    }
    while ( v4 < *(_DWORD *)(*a2 + 232) );
    v17[0] = v9 + 56;
    v17[1] = 0;
    if ( v8 >= 0 )
    {
      while ( 1 )
      {
        NextElement = TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(v17);
        if ( !NextElement )
          goto LABEL_29;
        if ( *(_DWORD *)(*(_QWORD *)(NextElement + 16) + 20LL) )
          goto LABEL_19;
      }
    }
  }
  else
  {
    v19 = 0;
    v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &IID_ISyncChange, &v19);
    if ( v8 >= 0 )
    {
      v13 = SeAlloc(0x50u);
      v14 = v13 ? ItemChangeApplicationStatus::ItemChangeApplicationStatus(v13, 0, &v19) : 0LL;
      v8 = SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(&v18, v14);
      if ( v8 >= 0 )
        v8 = HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(
               a1 + 168,
               *a2 + 152,
               &v18);
    }
    SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(&v19);
    v10 = 1;
    if ( v8 >= 0 )
    {
LABEL_29:
      if ( v10 )
      {
        ++*(_DWORD *)(a1 + 208);
        v15 = *(_QWORD *)(a1 + 144);
        if ( v15 )
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                 v15,
                 *(unsigned int *)(a1 + 208),
                 *(unsigned int *)(a1 + 212));
      }
    }
  }
LABEL_32:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      (unsigned int)"ChangeApplicationServices::ReportItemChangeSaved",
      v8);
  }
  SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049950  mov     [rsp-38h+arg_0], rbx
0x180049955  push    rbp
0x180049956  push    rsi
0x180049957  push    rdi
0x180049958  push    r12
0x18004995a  push    r13
0x18004995c  push    r14
0x18004995e  push    r15
0x180049960  mov     rbp, rsp
0x180049963  sub     rsp, 40h
0x180049967  mov     r13, rdx
0x18004996a  mov     r15, rcx
0x18004996d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049974  lea     rax, WPP_GLOBAL_Control
0x18004997b  cmp     rcx, rax
0x18004997e  jz      short loc_1800499A8
0x180049980  test    byte ptr [rcx+1Ch], 80h
0x180049984  jz      short loc_1800499A8
0x180049986  cmp     byte ptr [rcx+19h], 5
0x18004998a  jb      short loc_1800499A8
0x18004998c  mov     rcx, [rcx+10h]
0x180049990  lea     r9, aChangeapplicat_34; "ChangeApplicationServices::ReportItemCh"...
0x180049997  mov     edx, 28h ; '('
0x18004999c  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x1800499a3  call    WPP_SF_s
0x1800499a8  mov     rdx, [r13+0]
0x1800499ac  lea     rbx, [r15+0A8h]
0x1800499b3  mov     esi, 98h
0x1800499b8  lea     r8, [rbp+arg_10]
0x1800499bc  xor     r12d, r12d
0x1800499bf  add     rdx, rsi
0x1800499c2  mov     rcx, rbx
0x1800499c5  mov     [rbp+arg_10], r12
0x1800499c9  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeConflictExclusions@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeConflictExclusions@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeConflictExclusions>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeConflictExclusions> &)
0x1800499ce  mov     rcx, [r13+0]
0x1800499d2  test    al, al
0x1800499d4  jz      loc_180049ADE
0x1800499da  mov     edi, r12d
0x1800499dd  mov     rbx, [rbp+arg_10]
0x1800499e1  cmp     [rcx+0E8h], r12d
0x1800499e8  jbe     loc_180049ACE
0x1800499ee  cmp     dword ptr [rbx+14h], 1
0x1800499f2  jz      loc_180049ACE
0x1800499f8  lea     esi, [r12+1]
0x1800499fd  mov     [rbp+arg_18], 0
0x180049a05  test    edi, edi
0x180049a07  js      short loc_180049A76
0x180049a09  mov     rax, [rcx+0F8h]
0x180049a10  lea     r8, [rbp+arg_18]
0x180049a14  mov     r14d, r12d
0x180049a17  lea     rcx, [rbx+38h]
0x180049a1b  mov     [rbp+var_10], rax
0x180049a1f  mov     rdx, [rax+r14*8]
0x180049a23  add     rdx, 50h ; 'P'
0x180049a27  call    ?LookupItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::LookupItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> &)
0x180049a2c  test    al, al
0x180049a2e  jnz     short loc_180049A76
0x180049a30  mov     ecx, 28h ; '('; unsigned __int64
0x180049a35  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049a3a  test    rax, rax
0x180049a3d  jz      short loc_180049A49
0x180049a3f  xor     edx, edx
0x180049a41  mov     rcx, rax
0x180049a44  call    ??0ChangeUnitChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@@Z; ChangeUnitChangeApplicationStatus::ChangeUnitChangeApplicationStatus(ChangeApplicationReportStatus)
0x180049a49  mov     rdx, rax
0x180049a4c  lea     rcx, [rbp+arg_18]
0x180049a50  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049a55  mov     edi, eax
0x180049a57  test    eax, eax
0x180049a59  js      short loc_180049A76
0x180049a5b  mov     rdx, [rbp+var_10]
0x180049a5f  lea     r8, [rbp+arg_18]
0x180049a63  lea     rcx, [rbx+38h]
0x180049a67  mov     rdx, [rdx+r14*8]
0x180049a6b  add     rdx, 50h ; 'P'
0x180049a6f  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ChangeUnitChangeApplicationStatus> const &)
0x180049a74  mov     edi, eax
0x180049a76  lea     rcx, [rbp+arg_18]
0x180049a7a  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x180049a7f  mov     rcx, [r13+0]
0x180049a83  inc     r12d
0x180049a86  cmp     r12d, [rcx+0E8h]
0x180049a8d  jb      loc_1800499FD
0x180049a93  add     rbx, 38h ; '8'
0x180049a97  xor     r12d, r12d
0x180049a9a  mov     [rbp+var_10], rbx
0x180049a9e  mov     [rbp+var_8], r12
0x180049aa2  test    edi, edi
0x180049aa4  js      loc_180049B8C
0x180049aaa  lea     rcx, [rbp+var_10]
0x180049aae  call    ?GetNextElement@?$TableEnumerator@VSyncId@@HVDefaultHashTableContext@@@@QEAAPEAV?$TableElement@VSyncId@@HVDefaultHashTableContext@@@@XZ; TableEnumerator<SyncId,int,DefaultHashTableContext>::GetNextElement(void)
0x180049ab3  test    rax, rax
0x180049ab6  jz      loc_180049B59
0x180049abc  mov     rax, [rax+10h]
0x180049ac0  cmp     [rax+14h], r12d
0x180049ac4  jz      short loc_180049AAA
0x180049ac6  mov     esi, r12d
0x180049ac9  jmp     loc_180049B59
0x180049ace  cmp     [rbx+14h], r12d
0x180049ad2  jnz     short loc_180049AC6
0x180049ad4  mov     edi, 8004101Dh
0x180049ad9  jmp     loc_180049B8C
0x180049ade  mov     [rbp+arg_18], r12
0x180049ae2  lea     r8, [rbp+arg_18]
0x180049ae6  mov     rax, [rcx]
0x180049ae9  lea     rdx, IID_ISyncChange
0x180049af0  mov     rax, [rax]
0x180049af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049af8  mov     edi, eax
0x180049afa  test    eax, eax
0x180049afc  js      short loc_180049B47
0x180049afe  mov     ecx, 50h ; 'P'; unsigned __int64
0x180049b03  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180049b08  test    rax, rax
0x180049b0b  jz      short loc_180049B1D
0x180049b0d  lea     r8, [rbp+arg_18]
0x180049b11  xor     edx, edx
0x180049b13  mov     rcx, rax
0x180049b16  call    ??0ItemChangeApplicationStatus@@QEAA@W4ChangeApplicationReportStatus@@AEBV?$SharedRefPtr@UISyncChange@@@@@Z; ItemChangeApplicationStatus::ItemChangeApplicationStatus(ChangeApplicationReportStatus,SharedRefPtr<ISyncChange> const &)
0x180049b1b  jmp     short loc_180049B20
0x180049b1d  mov     rax, r12
0x180049b20  mov     rdx, rax
0x180049b23  lea     rcx, [rbp+arg_10]
0x180049b27  call    ?Attach@?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAAJPEAVChangeUnitChangeApplicationStatus@@H@Z; SharedRefPtr<ChangeUnitChangeApplicationStatus>::Attach(ChangeUnitChangeApplicationStatus *,int)
0x180049b2c  mov     edi, eax
0x180049b2e  test    eax, eax
0x180049b30  js      short loc_180049B47
0x180049b32  mov     rdx, [r13+0]
0x180049b36  lea     r8, [rbp+arg_10]
0x180049b3a  add     rdx, rsi
0x180049b3d  mov     rcx, rbx
0x180049b40  call    ?AddItem@?$HashTable@VSyncId@@V?$SharedRefPtr@VItemChangeApplicationStatus@@@@VDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBV?$SharedRefPtr@VItemChangeApplicationStatus@@@@@Z; HashTable<SyncId,SharedRefPtr<ItemChangeApplicationStatus>,DefaultHashTableContext>::AddItem(SyncId const &,SharedRefPtr<ItemChangeApplicationStatus> const &)
0x180049b45  mov     edi, eax
0x180049b47  lea     rcx, [rbp+arg_18]
0x180049b4b  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180049b50  mov     esi, 1
0x180049b55  test    edi, edi
0x180049b57  js      short loc_180049B8C
0x180049b59  test    esi, esi
0x180049b5b  jz      short loc_180049B8C
0x180049b5d  inc     dword ptr [r15+0D0h]
0x180049b64  mov     rcx, [r15+90h]
0x180049b6b  test    rcx, rcx
0x180049b6e  jz      short loc_180049B8C
0x180049b70  mov     rax, [rcx]
0x180049b73  mov     r8d, [r15+0D4h]
0x180049b7a  mov     edx, [r15+0D0h]
0x180049b81  mov     rax, [rax+40h]
0x180049b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b8a  mov     edi, eax
0x180049b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b93  lea     rax, WPP_GLOBAL_Control
0x180049b9a  cmp     rcx, rax
0x180049b9d  jz      short loc_180049BCB
0x180049b9f  test    byte ptr [rcx+1Ch], 80h
0x180049ba3  jz      short loc_180049BCB
0x180049ba5  cmp     byte ptr [rcx+19h], 5
0x180049ba9  jb      short loc_180049BCB
0x180049bab  mov     rcx, [rcx+10h]
0x180049baf  lea     r9, aChangeapplicat_34; "ChangeApplicationServices::ReportItemCh"...
0x180049bb6  mov     edx, 29h ; ')'
0x180049bbb  mov     [rsp+40h+var_20], edi
0x180049bbf  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180049bc6  call    WPP_SF_sD
0x180049bcb  lea     rcx, [rbp+arg_10]
0x180049bcf  call    ??1?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@QEAA@XZ; SharedRefPtr<ChangeUnitChangeApplicationStatus>::~SharedRefPtr<ChangeUnitChangeApplicationStatus>(void)
0x180049bd4  mov     rbx, [rsp+40h+arg_0]
0x180049bdc  mov     eax, edi
0x180049bde  add     rsp, 40h
0x180049be2  pop     r15
0x180049be4  pop     r14
0x180049be6  pop     r13
0x180049be8  pop     r12
0x180049bea  pop     rdi
0x180049beb  pop     rsi
0x180049bec  pop     rbp
0x180049bed  retn
```
