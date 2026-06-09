# CChangeApplier::DetectUpdateDeleteConflictOnChangeUnit(__MIDL___MIDL_itf_winsync_0000_0000_0002,uchar *,CSyncChangeWrapper *,CEnumSyncChangeUnitWrappers *,CSyncChangeWrapper *,CEnumSyncChangeUnitWrappers *,int,int,int *)

- ea: `0x180039638`
- end: `0x180039941`
- name: `?DetectUpdateDeleteConflictOnChangeUnit@CChangeApplier@@AEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@PEAEPEAVCSyncChangeWrapper@@PEAVCEnumSyncChangeUnitWrappers@@23HHPEAH@Z`
- size: `777`
- prototype: `__int64 __fastcall(struct ISyncKnowledge **this, __int64, unsigned __int8 *, struct CSyncChangeWrapper *, struct CEnumSyncChangeUnitWrappers *, struct CSyncChangeWrapper *, struct CEnumSyncChangeUnitWrappers *, int, int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800392b4`

## callees

- `0x18001ae20`
- `0x180035600`
- `0x180036eb4`
- `0x1800371e0`
- `0x180039638`
- `0x18003e1e8`
- `0x180066f20`
- `0x18006cc00`
- `0x1800709c0`
- `0x180071b20`
- `0x180072974`
- `0x180094010`

## string_xrefs

- `0x18003990a`: `CChangeApplier::DetectUpdateDeleteConflictOnChangeUnit`

## pseudocode

```c
__int64 __fastcall CChangeApplier::DetectUpdateDeleteConflictOnChangeUnit(
        struct ISyncKnowledge **this,
        __int64 a2,
        unsigned __int8 *a3,
        struct CSyncChangeWrapper *a4,
        struct CEnumSyncChangeUnitWrappers *a5,
        struct CSyncChangeWrapper *a6,
        struct CEnumSyncChangeUnitWrappers *a7,
        int a8,
        int a9,
        int *a10)
{
  enum __MIDL___MIDL_itf_winsync_0000_0000_0002 v11; // ebx
  int v13; // eax
  int v14; // edi
  unsigned int v15; // edx
  unsigned int *v16; // r9
  struct CEnumSyncChangeUnitWrappers *v17; // rbx
  struct ISyncCallback *v18; // rdx
  int v19; // eax
  unsigned int v20; // edx
  unsigned int *v21; // r9
  struct CEnumSyncChangeUnitWrappers *v22; // rbx
  int v23; // edi
  int v24; // eax
  CChangeApplier *v25; // rcx
  CSyncChangeUnitWrapper *v26; // r15
  int v27; // ebx
  unsigned int v28; // edx
  unsigned int *v29; // r9
  CChangeApplier *v30; // rcx
  CSyncChangeUnitWrapper *v31; // rbx
  int v32; // edi
  struct ISyncCallback *v33; // rdx
  CSyncChangeUnitWrapper *v35[2]; // [rsp+30h] [rbp-10h] BYREF
  enum __MIDL___MIDL_itf_winsync_0000_0000_0002 v36; // [rsp+78h] [rbp+38h]
  int v37; // [rsp+80h] [rbp+40h]

  v36 = (int)a2;
  v11 = (int)a2;
  v37 = 0;
  if ( !a7 )
  {
    if ( !a8 )
    {
      v13 = CChangeApplier::ContainsChangeVersionWrapper((CChangeApplier *)this, this[60], a6);
      v14 = v13;
      if ( v13 != 1 )
      {
        if ( v13 )
          goto LABEL_38;
        v14 = CSyncChangeWrapper::AddTransferFilter(a4, 3);
        if ( v14 < 0 )
          goto LABEL_38;
        v14 = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)a5 + 40LL))(a5);
        if ( v14 < 0 )
          goto LABEL_38;
        a7 = 0;
        do
        {
          v14 = CEnumSyncChangeUnitWrappers::Next(a5, v15, &a7, v16);
          if ( v14 )
            break;
          v17 = a7;
          v14 = CSyncChangeUnitWrapper::AddTransferFilter(a7, 3);
          (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v17 + 16LL))(v17);
        }
        while ( v14 >= 0 );
        if ( v14 < 0 )
          goto LABEL_38;
        v18 = (struct ISyncCallback *)this[50];
        if ( !v18 )
          goto LABEL_14;
        v19 = CChangeApplier::ChangeNotificationWrapper((CChangeApplier *)this, v18, a4);
LABEL_13:
        v14 = v19;
        if ( v19 >= 0 )
        {
LABEL_14:
          v14 = 1;
          goto LABEL_38;
        }
        goto LABEL_38;
      }
    }
    v37 = 1;
    if ( (*(int (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, __int64, unsigned __int8 *))(*(_QWORD *)a5 + 40LL))(
           a5,
           a2,
           a3) < 0 )
    {
LABEL_31:
      v14 = CSyncChangeWrapper::SetConflict(a4, a6, 0, 1);
      if ( v14 < 0 )
        goto LABEL_38;
      v19 = CChangeApplier::HandleConflict((CChangeApplier *)this, v11, a4, 1, a9, 0);
      goto LABEL_13;
    }
    a7 = 0;
    do
    {
      if ( (unsigned int)CEnumSyncChangeUnitWrappers::Next(a5, v20, &a7, v21) )
        break;
      v22 = a7;
      v23 = CSyncChangeUnitWrapper::SetConflict(a7);
      (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    while ( v23 >= 0 );
LABEL_30:
    v11 = v36;
    goto LABEL_31;
  }
  v35[0] = 0;
  v24 = CEnumSyncChangeUnitWrappers::Next(a7, a2, v35, (unsigned int *)a4);
  v14 = v24;
  if ( !v24 )
  {
    v26 = v35[0];
    if ( !a8 )
    {
      v14 = CChangeApplier::ContainsChangeUnitVersionWrapper(v25, this[60], v35[0]);
      if ( v14 != 1 )
      {
        (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_38;
      }
    }
    v37 = 1;
    v27 = CSyncChangeUnitWrapper::SetConflict(v26);
    (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 >= 0 )
    {
      do
      {
        if ( (unsigned int)CEnumSyncChangeUnitWrappers::Next(a7, v28, v35, v29) )
          break;
        v31 = v35[0];
        if ( !a8 )
        {
          v32 = CChangeApplier::ContainsChangeUnitVersionWrapper(v30, this[60], v35[0]);
          if ( v32 != 1 )
            continue;
        }
        v32 = CSyncChangeUnitWrapper::SetConflict(v31);
        (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      while ( v32 >= 0 );
    }
    goto LABEL_30;
  }
  if ( v24 == 1 )
  {
    v14 = CSyncChangeWrapper::AddTransferFilter(a4, 3);
    if ( v14 >= 0 )
    {
      v33 = (struct ISyncCallback *)this[50];
      if ( !v33 )
        goto LABEL_14;
      v14 = CChangeApplier::ChangeNotificationWrapper((CChangeApplier *)this, v33, a4);
      if ( v14 >= 0 )
        v14 = 1;
    }
  }
LABEL_38:
  *a10 = v37;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      221,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::DetectUpdateDeleteConflictOnChangeUnit",
      v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180039638  mov     rax, rsp
0x18003963b  mov     [rax+8], rbx
0x18003963f  mov     [rax+20h], rsi
0x180039643  mov     [rax+18h], r8
0x180039647  mov     [rax+10h], edx
0x18003964a  push    rbp
0x18003964b  push    rdi
0x18003964c  push    r12
0x18003964e  push    r14
0x180039650  push    r15
0x180039652  mov     rbp, rsp
0x180039655  sub     rsp, 40h
0x180039659  cmp     [rbp+arg_30], 0
0x18003965e  mov     r12, r9
0x180039661  mov     ebx, edx
0x180039663  mov     [rbp+arg_10], 0
0x18003966a  mov     r14, rcx
0x18003966d  jnz     loc_1800397A4
0x180039673  cmp     [rbp+arg_38], 0
0x180039677  mov     esi, 1
0x18003967c  jnz     loc_180039744
0x180039682  mov     r8, [rbp+arg_28]; struct CSyncChangeWrapper *
0x180039686  mov     rdx, [rcx+1E0h]; struct ISyncKnowledge *
0x18003968d  call    ?ContainsChangeVersionWrapper@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAVCSyncChangeWrapper@@@Z; CChangeApplier::ContainsChangeVersionWrapper(ISyncKnowledge *,CSyncChangeWrapper *)
0x180039692  mov     edi, eax
0x180039694  cmp     eax, esi
0x180039696  jz      loc_180039744
0x18003969c  test    eax, eax
0x18003969e  jnz     loc_1800398DE
0x1800396a4  lea     edx, [rsi+2]
0x1800396a7  mov     rcx, r12
0x1800396aa  call    ?AddTransferFilter@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x1800396af  mov     edi, eax
0x1800396b1  test    eax, eax
0x1800396b3  js      loc_1800398DE
0x1800396b9  mov     r15, [rbp+arg_20]
0x1800396bd  mov     rcx, r15
0x1800396c0  mov     rax, [r15]
0x1800396c3  mov     rax, [rax+28h]
0x1800396c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396cc  mov     edi, eax
0x1800396ce  test    eax, eax
0x1800396d0  js      loc_1800398DE
0x1800396d6  mov     [rbp+arg_30], 0
0x1800396de  lea     r8, [rbp+arg_30]; struct CSyncChangeUnitWrapper **
0x1800396e2  mov     rcx, r15; this
0x1800396e5  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x1800396ea  mov     edi, eax
0x1800396ec  test    eax, eax
0x1800396ee  jnz     short loc_180039714
0x1800396f0  mov     rbx, [rbp+arg_30]
0x1800396f4  lea     edx, [rax+3]
0x1800396f7  mov     rcx, rbx
0x1800396fa  call    ?AddTransferFilter@CSyncChangeUnitWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x1800396ff  mov     edi, eax
0x180039701  mov     rcx, rbx
0x180039704  mov     rax, [rbx]
0x180039707  mov     rax, [rax+10h]
0x18003970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039710  test    edi, edi
0x180039712  jns     short loc_1800396DE
0x180039714  test    edi, edi
0x180039716  js      loc_1800398DE
0x18003971c  mov     rdx, [r14+190h]; struct ISyncCallback *
0x180039723  test    rdx, rdx
0x180039726  jz      short loc_18003973D
0x180039728  mov     r8, r12; struct CSyncChangeWrapper *
0x18003972b  mov     rcx, r14; this
0x18003972e  call    ?ChangeNotificationWrapper@CChangeApplier@@AEAAJPEAUISyncCallback@@PEAVCSyncChangeWrapper@@@Z; CChangeApplier::ChangeNotificationWrapper(ISyncCallback *,CSyncChangeWrapper *)
0x180039733  mov     edi, eax
0x180039735  test    eax, eax
0x180039737  js      loc_1800398DE
0x18003973d  mov     edi, esi
0x18003973f  jmp     loc_1800398DE
0x180039744  mov     r15, [rbp+arg_20]
0x180039748  mov     rcx, r15
0x18003974b  mov     [rbp+arg_10], esi
0x18003974e  mov     rax, [r15]
0x180039751  mov     rax, [rax+28h]
0x180039755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003975a  test    eax, eax
0x18003975c  js      loc_180039869
0x180039762  mov     [rbp+arg_30], 0
0x18003976a  lea     r8, [rbp+arg_30]; struct CSyncChangeUnitWrapper **
0x18003976e  mov     rcx, r15; this
0x180039771  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x180039776  test    eax, eax
0x180039778  jnz     loc_180039866
0x18003977e  mov     rbx, [rbp+arg_30]
0x180039782  mov     rcx, rbx; this
0x180039785  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x18003978a  mov     rdx, [rbx]
0x18003978d  mov     edi, eax
0x18003978f  mov     rcx, rbx
0x180039792  mov     rax, [rdx+10h]
0x180039796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003979b  test    edi, edi
0x18003979d  jns     short loc_18003976A
0x18003979f  jmp     loc_180039866
0x1800397a4  mov     rcx, [rbp+arg_30]; this
0x1800397a8  lea     r8, [rbp+var_10]; struct CSyncChangeUnitWrapper **
0x1800397ac  mov     [rbp+var_10], 0
0x1800397b4  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x1800397b9  mov     edi, eax
0x1800397bb  mov     esi, 1
0x1800397c0  test    eax, eax
0x1800397c2  jnz     loc_1800398A5
0x1800397c8  mov     r15, [rbp+var_10]
0x1800397cc  cmp     [rbp+arg_38], eax
0x1800397cf  jnz     short loc_1800397FA
0x1800397d1  mov     rdx, [r14+1E0h]; struct ISyncKnowledge *
0x1800397d8  mov     r8, r15; struct CSyncChangeUnitWrapper *
0x1800397db  call    ?ContainsChangeUnitVersionWrapper@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAVCSyncChangeUnitWrapper@@@Z; CChangeApplier::ContainsChangeUnitVersionWrapper(ISyncKnowledge *,CSyncChangeUnitWrapper *)
0x1800397e0  mov     edi, eax
0x1800397e2  cmp     eax, esi
0x1800397e4  jz      short loc_1800397FA
0x1800397e6  mov     rax, [r15]
0x1800397e9  mov     rcx, r15
0x1800397ec  mov     rax, [rax+10h]
0x1800397f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397f5  jmp     loc_1800398DE
0x1800397fa  mov     rcx, r15; this
0x1800397fd  mov     [rbp+arg_10], esi
0x180039800  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x180039805  mov     rcx, [r15]
0x180039808  mov     ebx, eax
0x18003980a  mov     rax, [rcx+10h]
0x18003980e  mov     rcx, r15
0x180039811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039816  test    ebx, ebx
0x180039818  js      short loc_180039866
0x18003981a  mov     rcx, [rbp+arg_30]; this
0x18003981e  lea     r8, [rbp+var_10]; struct CSyncChangeUnitWrapper **
0x180039822  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x180039827  test    eax, eax
0x180039829  jnz     short loc_180039866
0x18003982b  mov     rbx, [rbp+var_10]
0x18003982f  cmp     [rbp+arg_38], eax
0x180039832  jnz     short loc_180039849
0x180039834  mov     rdx, [r14+1E0h]; struct ISyncKnowledge *
0x18003983b  mov     r8, rbx; struct CSyncChangeUnitWrapper *
0x18003983e  call    ?ContainsChangeUnitVersionWrapper@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAVCSyncChangeUnitWrapper@@@Z; CChangeApplier::ContainsChangeUnitVersionWrapper(ISyncKnowledge *,CSyncChangeUnitWrapper *)
0x180039843  mov     edi, eax
0x180039845  cmp     eax, esi
0x180039847  jnz     short loc_180039853
0x180039849  mov     rcx, rbx; this
0x18003984c  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x180039851  mov     edi, eax
0x180039853  mov     rax, [rbx]
0x180039856  mov     rcx, rbx
0x180039859  mov     rax, [rax+10h]
0x18003985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039862  test    edi, edi
0x180039864  jns     short loc_18003981A
0x180039866  mov     ebx, [rbp+arg_8]
0x180039869  mov     rdx, [rbp+arg_28]; struct CSyncChangeWrapper *
0x18003986d  mov     r9d, esi; int
0x180039870  xor     r8d, r8d; struct CSyncChangeWrapper *
0x180039873  mov     rcx, r12; this
0x180039876  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x18003987b  mov     edi, eax
0x18003987d  test    eax, eax
0x18003987f  js      short loc_1800398DE
0x180039881  mov     eax, [rbp+arg_40]
0x180039884  mov     r9d, esi; int
0x180039887  mov     [rsp+40h+var_18], 0; int
0x18003988f  mov     r8, r12; struct CSyncChangeWrapper *
0x180039892  mov     edx, ebx; enum __MIDL___MIDL_itf_winsync_0000_0000_0002
0x180039894  mov     [rsp+40h+var_20], eax; int
0x180039898  mov     rcx, r14; this
0x18003989b  call    ?HandleConflict@CChangeApplier@@AEAAJW4__MIDL___MIDL_itf_winsync_0000_0000_0002@@PEAVCSyncChangeWrapper@@HHH@Z; CChangeApplier::HandleConflict(__MIDL___MIDL_itf_winsync_0000_0000_0002,CSyncChangeWrapper *,int,int,int)
0x1800398a0  jmp     loc_180039733
0x1800398a5  cmp     eax, esi
0x1800398a7  jnz     short loc_1800398DE
0x1800398a9  mov     edx, 3
0x1800398ae  mov     rcx, r12
0x1800398b1  call    ?AddTransferFilter@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::AddTransferFilter(SYNC_TRANSFER_FILTER)
0x1800398b6  mov     edi, eax
0x1800398b8  test    eax, eax
0x1800398ba  js      short loc_1800398DE
0x1800398bc  mov     rdx, [r14+190h]; struct ISyncCallback *
0x1800398c3  test    rdx, rdx
0x1800398c6  jz      loc_18003973D
0x1800398cc  mov     r8, r12; struct CSyncChangeWrapper *
0x1800398cf  mov     rcx, r14; this
0x1800398d2  call    ?ChangeNotificationWrapper@CChangeApplier@@AEAAJPEAUISyncCallback@@PEAVCSyncChangeWrapper@@@Z; CChangeApplier::ChangeNotificationWrapper(ISyncCallback *,CSyncChangeWrapper *)
0x1800398d7  test    eax, eax
0x1800398d9  mov     edi, eax
0x1800398db  cmovns  edi, esi
0x1800398de  mov     rax, [rbp+arg_48]
0x1800398e2  mov     ecx, [rbp+arg_10]
0x1800398e5  mov     [rax], ecx
0x1800398e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398ee  lea     rax, WPP_GLOBAL_Control
0x1800398f5  cmp     rcx, rax
0x1800398f8  jz      short loc_180039926
0x1800398fa  test    byte ptr [rcx+1Ch], 8
0x1800398fe  jz      short loc_180039926
0x180039900  cmp     byte ptr [rcx+19h], 5
0x180039904  jb      short loc_180039926
0x180039906  mov     rcx, [rcx+10h]
0x18003990a  lea     r9, aCchangeapplier_106; "CChangeApplier::DetectUpdateDeleteConfl"...
0x180039911  mov     edx, 0DDh
0x180039916  mov     [rsp+40h+var_20], edi
0x18003991a  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180039921  call    WPP_SF_sD
0x180039926  lea     r11, [rsp+40h+var_s0]
0x18003992b  mov     eax, edi
0x18003992d  mov     rbx, [r11+30h]
0x180039931  mov     rsi, [r11+48h]
0x180039935  mov     rsp, r11
0x180039938  pop     r15
0x18003993a  pop     r14
0x18003993c  pop     r12
0x18003993e  pop     rdi
0x18003993f  pop     rbp
0x180039940  retn
```
