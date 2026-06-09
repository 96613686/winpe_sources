# CChangeApplier::UpdateVersionsForKnowledgeConflict(void)

- ea: `0x180022490`
- end: `0x1800227a8`
- name: `?UpdateVersionsForKnowledgeConflict@CChangeApplier@@AEAAJXZ`
- size: `792`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x1800374b8`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180022490`
- `0x1800227b0`
- `0x180067f28`
- `0x18006a580`
- `0x18006ce54`
- `0x18006cff8`
- `0x1800709c0`
- `0x1800724ac`
- `0x180093270`
- `0x180094010`

## string_xrefs

- `0x1800224d4`: `CChangeApplier::UpdateVersionsForKnowledgeConflict`
- `0x180022771`: `CChangeApplier::UpdateVersionsForKnowledgeConflict`

## pseudocode

```c
__int64 __fastcall CChangeApplier::UpdateVersionsForKnowledgeConflict(CChangeApplier *this)
{
  CSyncChangeWrapper *v2; // rcx
  int TransferFilters; // ebx
  CSyncChangeWrapper *v4; // rcx
  int v5; // eax
  CSyncChangeWrapper *v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  _DWORD *v9; // rcx
  struct IAsynchronousNotifyingChangeApplierTarget *v10; // rdx
  CSyncChangeWrapper *v11; // rcx
  CEnumSyncChangeUnitWrappers *v12; // rsi
  unsigned int v13; // edx
  unsigned int *v14; // r9
  struct CSyncChangeUnitWrapper *v15; // r14
  __int64 v16; // rax
  CEnumSyncChangeUnitWrappers *v17; // rcx
  enum __MIDL___MIDL_itf_winsync_0000_0000_0005 v19; // [rsp+30h] [rbp-38h] BYREF
  struct CEnumSyncChangeUnitWrappers *v20; // [rsp+38h] [rbp-30h] BYREF
  struct _SYNC_VERSION v21; // [rsp+40h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      267,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::UpdateVersionsForKnowledgeConflict");
  }
  v2 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
  v19 = SRA_DEFER;
  TransferFilters = CSyncChangeWrapper::GetTransferFilters(v2, (enum SYNC_TRANSFER_FILTER *)&v19);
  if ( TransferFilters >= 0 && v19 != 32 )
  {
    v4 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
    *(_QWORD *)&v21.dwLastUpdatingReplicaKey = 0;
    v5 = CSyncChangeWrapper::GetWinnerChange(v4, (struct CSyncChangeWrapper **)&v21);
    TransferFilters = v5;
    if ( v5 == 1 )
    {
      v6 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
      v20 = 0;
      v7 = CSyncChangeWrapper::GetChangeUnitWrappers(v6, &v20);
      TransferFilters = v7;
      if ( v7 == -2147217393 )
      {
        v8 = *((_QWORD *)this + 68);
        v19 = SRA_DEFER;
        TransferFilters = (*(__int64 (__fastcall **)(__int64, enum __MIDL___MIDL_itf_winsync_0000_0000_0005 *))(*(_QWORD *)v8 + 56LL))(
                            v8,
                            &v19);
        if ( TransferFilters >= 0 && (unsigned int)(v19 - 1) <= 2 )
        {
          v9 = (_DWORD *)*((_QWORD *)this + 68);
          v21 = 0;
          if ( !v9[45]
            || (v20 = 0,
                TransferFilters = (*(__int64 (__fastcall **)(_DWORD *, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)v9 + 24LL))(
                                    v9,
                                    &v20),
                TransferFilters >= 0)
            && (TransferFilters = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, _QWORD, struct _SYNC_VERSION *))(*(_QWORD *)v20 + 48LL))(
                                    v20,
                                    *((_QWORD *)this + 15),
                                    &v21),
                (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v20 + 16LL))(v20),
                TransferFilters >= 0) )
          {
            v10 = (struct IAsynchronousNotifyingChangeApplierTarget *)*((_QWORD *)this + 16);
            v11 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
            v20 = 0;
            TransferFilters = CSyncChangeWrapper::SetConflictWinnerVersion(v11, v10, (unsigned __int64 *)&v20, &v21, 0);
            if ( TransferFilters >= 0 )
              TransferFilters = (*(__int64 (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers *))(**((_QWORD **)this + 64) + 40LL))(
                                  *((_QWORD *)this + 64),
                                  v20);
          }
        }
        goto LABEL_33;
      }
      if ( v7 < 0 )
        goto LABEL_33;
      v12 = v20;
      TransferFilters = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v20 + 40LL))(v20);
      if ( TransferFilters >= 0 )
      {
        *(_QWORD *)&v21.dwLastUpdatingReplicaKey = 0;
        v20 = 0;
        do
        {
          TransferFilters = CEnumSyncChangeUnitWrappers::Next(v12, v13, (struct CSyncChangeUnitWrapper **)&v21, v14);
          if ( TransferFilters )
            break;
          v15 = *(struct CSyncChangeUnitWrapper **)&v21.dwLastUpdatingReplicaKey;
          v19 = SRA_DEFER;
          TransferFilters = CSyncChangeUnitWrapper::GetResolveAction(
                              *(CSyncChangeUnitWrapper **)&v21.dwLastUpdatingReplicaKey,
                              &v19);
          if ( TransferFilters >= 0 && (unsigned int)(v19 - 1) <= 2 )
          {
            TransferFilters = (*(__int64 (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers **))(**((_QWORD **)this + 16) + 56LL))(
                                *((_QWORD *)this + 16),
                                &v20);
            if ( TransferFilters >= 0 )
              TransferFilters = CSyncChangeWrapper::SetConflictWinnerVersionOnChangeUnit(
                                  *((CSyncChangeWrapper **)this + 68),
                                  v15,
                                  (unsigned __int64)v20);
          }
          (*(void (__fastcall **)(struct CSyncChangeUnitWrapper *))(*(_QWORD *)v15 + 16LL))(v15);
        }
        while ( TransferFilters >= 0 );
        if ( TransferFilters >= 0 )
        {
          if ( !v20
            || (TransferFilters = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 40LL))(*((_QWORD *)this + 64)),
                TransferFilters >= 0) )
          {
            TransferFilters = (*(__int64 (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v12 + 40LL))(v12);
          }
        }
      }
      v16 = *(_QWORD *)v12;
      v17 = v12;
    }
    else
    {
      if ( v5 )
        goto LABEL_33;
      v17 = *(CEnumSyncChangeUnitWrappers **)&v21.dwLastUpdatingReplicaKey;
      v16 = **(_QWORD **)&v21.dwLastUpdatingReplicaKey;
    }
    (*(void (__fastcall **)(CEnumSyncChangeUnitWrappers *))(v16 + 16))(v17);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      268,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::UpdateVersionsForKnowledgeConflict",
      TransferFilters);
  }
  return (unsigned int)TransferFilters;
}

```

## disassembly

```asm
0x180022490  push    rbp
0x180022492  push    rbx
0x180022493  push    rsi
0x180022494  push    rdi
0x180022495  push    r12
0x180022497  push    r14
0x180022499  mov     rbp, rsp
0x18002249c  sub     rsp, 68h
0x1800224a0  mov     rax, cs:__security_cookie
0x1800224a7  xor     rax, rsp
0x1800224aa  mov     [rbp+var_18], rax
0x1800224ae  mov     rdi, rcx
0x1800224b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224b8  lea     r12, WPP_GLOBAL_Control
0x1800224bf  cmp     rcx, r12
0x1800224c2  jz      short loc_1800224EC
0x1800224c4  test    byte ptr [rcx+1Ch], 8
0x1800224c8  jz      short loc_1800224EC
0x1800224ca  cmp     byte ptr [rcx+19h], 5
0x1800224ce  jb      short loc_1800224EC
0x1800224d0  mov     rcx, [rcx+10h]
0x1800224d4  lea     r9, aCchangeapplier_24; "CChangeApplier::UpdateVersionsForKnowle"...
0x1800224db  mov     edx, 10Bh
0x1800224e0  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800224e7  call    WPP_SF_s
0x1800224ec  mov     rcx, [rdi+220h]; this
0x1800224f3  lea     rdx, [rbp+var_38]; enum SYNC_TRANSFER_FILTER *
0x1800224f7  mov     [rbp+var_38], 0
0x1800224fe  call    ?GetTransferFilters@CSyncChangeWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x180022503  mov     ebx, eax
0x180022505  test    eax, eax
0x180022507  js      loc_180022755
0x18002250d  cmp     [rbp+var_38], 20h ; ' '
0x180022511  jz      loc_180022755
0x180022517  mov     rcx, [rdi+220h]; this
0x18002251e  lea     rdx, [rbp+var_28]; struct CSyncChangeWrapper **
0x180022522  mov     qword ptr [rbp+var_28.dwLastUpdatingReplicaKey], 0
0x18002252a  call    ?GetWinnerChange@CSyncChangeWrapper@@QEAAJPEAPEAV1@@Z; CSyncChangeWrapper::GetWinnerChange(CSyncChangeWrapper * *)
0x18002252f  mov     ebx, eax
0x180022531  cmp     eax, 1
0x180022534  jnz     loc_180022741
0x18002253a  mov     rcx, [rdi+220h]; this
0x180022541  lea     rdx, [rbp+var_30]; struct CEnumSyncChangeUnitWrappers **
0x180022545  mov     [rbp+var_30], 0
0x18002254d  call    ?GetChangeUnitWrappers@CSyncChangeWrapper@@QEAAJPEAPEAVCEnumSyncChangeUnitWrappers@@@Z; CSyncChangeWrapper::GetChangeUnitWrappers(CEnumSyncChangeUnitWrappers * *)
0x180022552  mov     ebx, eax
0x180022554  cmp     eax, 8004100Fh
0x180022559  jnz     loc_180022653
0x18002255f  mov     rcx, [rdi+220h]
0x180022566  lea     rdx, [rbp+var_38]
0x18002256a  mov     [rbp+var_38], 0
0x180022571  mov     rax, [rcx]
0x180022574  mov     rax, [rax+38h]
0x180022578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002257d  mov     ebx, eax
0x18002257f  test    eax, eax
0x180022581  js      loc_180022755
0x180022587  mov     eax, [rbp+var_38]
0x18002258a  dec     eax
0x18002258c  cmp     eax, 2
0x18002258f  ja      loc_180022755
0x180022595  mov     rcx, [rdi+220h]
0x18002259c  xorps   xmm0, xmm0
0x18002259f  movups  xmmword ptr [rbp+var_28.dwLastUpdatingReplicaKey], xmm0
0x1800225a3  cmp     dword ptr [rcx+0B4h], 0
0x1800225aa  jz      short loc_180022600
0x1800225ac  mov     [rbp+var_30], 0
0x1800225b4  lea     rdx, [rbp+var_30]
0x1800225b8  mov     rax, [rcx]
0x1800225bb  mov     rax, [rax+18h]
0x1800225bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225c4  mov     ebx, eax
0x1800225c6  test    eax, eax
0x1800225c8  js      loc_180022755
0x1800225ce  mov     rcx, [rbp+var_30]
0x1800225d2  lea     r8, [rbp+var_28]
0x1800225d6  mov     rdx, [rdi+78h]
0x1800225da  mov     rax, [rcx]
0x1800225dd  mov     rax, [rax+30h]
0x1800225e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225e6  mov     rcx, [rbp+var_30]
0x1800225ea  mov     ebx, eax
0x1800225ec  mov     rax, [rcx]
0x1800225ef  mov     rax, [rax+10h]
0x1800225f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f8  test    ebx, ebx
0x1800225fa  js      loc_180022755
0x180022600  mov     rdx, [rdi+80h]; struct IAsynchronousNotifyingChangeApplierTarget *
0x180022607  lea     r9, [rbp+var_28]; struct _SYNC_VERSION *
0x18002260b  mov     rcx, [rdi+220h]; this
0x180022612  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180022616  mov     [rbp+var_30], 0
0x18002261e  mov     [rsp+68h+var_48], 0; int
0x180022626  call    ?SetConflictWinnerVersion@CSyncChangeWrapper@@QEAAJPEAUIAsynchronousNotifyingChangeApplierTarget@@PEA_KPEAU_SYNC_VERSION@@H@Z; CSyncChangeWrapper::SetConflictWinnerVersion(IAsynchronousNotifyingChangeApplierTarget *,unsigned __int64 *,_SYNC_VERSION *,int)
0x18002262b  mov     ebx, eax
0x18002262d  test    eax, eax
0x18002262f  js      loc_180022755
0x180022635  mov     rcx, [rdi+200h]
0x18002263c  mov     rdx, [rbp+var_30]
0x180022640  mov     rax, [rcx]
0x180022643  mov     rax, [rax+28h]
0x180022647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002264c  mov     ebx, eax
0x18002264e  jmp     loc_180022755
0x180022653  test    eax, eax
0x180022655  js      loc_180022755
0x18002265b  mov     rsi, [rbp+var_30]
0x18002265f  mov     rcx, rsi
0x180022662  mov     rax, [rsi]
0x180022665  mov     rax, [rax+28h]
0x180022669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002266e  mov     ebx, eax
0x180022670  test    eax, eax
0x180022672  js      loc_180022739
0x180022678  mov     qword ptr [rbp+var_28.dwLastUpdatingReplicaKey], 0
0x180022680  mov     [rbp+var_30], 0
0x180022688  lea     r8, [rbp+var_28]; struct CSyncChangeUnitWrapper **
0x18002268c  mov     rcx, rsi; this
0x18002268f  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x180022694  mov     ebx, eax
0x180022696  test    eax, eax
0x180022698  jnz     short loc_180022702
0x18002269a  mov     r14, qword ptr [rbp+var_28.dwLastUpdatingReplicaKey]
0x18002269e  lea     rdx, [rbp+var_38]; enum __MIDL___MIDL_itf_winsync_0000_0000_0005 *
0x1800226a2  mov     rcx, r14; this
0x1800226a5  mov     [rbp+var_38], eax
0x1800226a8  call    ?GetResolveAction@CSyncChangeUnitWrapper@@QEAAJPEAW4__MIDL___MIDL_itf_winsync_0000_0000_0005@@@Z; CSyncChangeUnitWrapper::GetResolveAction(__MIDL___MIDL_itf_winsync_0000_0000_0005 *)
0x1800226ad  mov     ebx, eax
0x1800226af  test    eax, eax
0x1800226b1  js      short loc_1800226EF
0x1800226b3  mov     eax, [rbp+var_38]
0x1800226b6  dec     eax
0x1800226b8  cmp     eax, 2
0x1800226bb  ja      short loc_1800226EF
0x1800226bd  mov     rcx, [rdi+80h]
0x1800226c4  lea     rdx, [rbp+var_30]
0x1800226c8  mov     rax, [rcx]
0x1800226cb  mov     rax, [rax+38h]
0x1800226cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d4  mov     ebx, eax
0x1800226d6  test    eax, eax
0x1800226d8  js      short loc_1800226EF
0x1800226da  mov     r8, [rbp+var_30]; unsigned __int64
0x1800226de  mov     rdx, r14; struct CSyncChangeUnitWrapper *
0x1800226e1  mov     rcx, [rdi+220h]; this
0x1800226e8  call    ?SetConflictWinnerVersionOnChangeUnit@CSyncChangeWrapper@@QEAAJPEAVCSyncChangeUnitWrapper@@_K@Z; CSyncChangeWrapper::SetConflictWinnerVersionOnChangeUnit(CSyncChangeUnitWrapper *,unsigned __int64)
0x1800226ed  mov     ebx, eax
0x1800226ef  mov     rax, [r14]
0x1800226f2  mov     rcx, r14
0x1800226f5  mov     rax, [rax+10h]
0x1800226f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226fe  test    ebx, ebx
0x180022700  jns     short loc_180022688
0x180022702  test    ebx, ebx
0x180022704  js      short loc_180022739
0x180022706  mov     rdx, [rbp+var_30]
0x18002270a  test    rdx, rdx
0x18002270d  jz      short loc_180022728
0x18002270f  mov     rcx, [rdi+200h]
0x180022716  mov     rax, [rcx]
0x180022719  mov     rax, [rax+28h]
0x18002271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022722  mov     ebx, eax
0x180022724  test    eax, eax
0x180022726  js      short loc_180022739
0x180022728  mov     rax, [rsi]
0x18002272b  mov     rcx, rsi
0x18002272e  mov     rax, [rax+28h]
0x180022732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022737  mov     ebx, eax
0x180022739  mov     rax, [rsi]
0x18002273c  mov     rcx, rsi
0x18002273f  jmp     short loc_18002274C
0x180022741  test    eax, eax
0x180022743  jnz     short loc_180022755
0x180022745  mov     rcx, qword ptr [rbp+var_28.dwLastUpdatingReplicaKey]
0x180022749  mov     rax, [rcx]
0x18002274c  mov     rax, [rax+10h]
0x180022750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002275c  cmp     rcx, r12
0x18002275f  jz      short loc_18002278D
0x180022761  test    byte ptr [rcx+1Ch], 8
0x180022765  jz      short loc_18002278D
0x180022767  cmp     byte ptr [rcx+19h], 5
0x18002276b  jb      short loc_18002278D
0x18002276d  mov     rcx, [rcx+10h]
0x180022771  lea     r9, aCchangeapplier_24; "CChangeApplier::UpdateVersionsForKnowle"...
0x180022778  mov     edx, 10Ch
0x18002277d  mov     [rsp+68h+var_48], ebx
0x180022781  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180022788  call    WPP_SF_sD
0x18002278d  mov     eax, ebx
0x18002278f  mov     rcx, [rbp+var_18]
0x180022793  xor     rcx, rsp; StackCookie
0x180022796  call    __security_check_cookie
0x18002279b  add     rsp, 68h
0x18002279f  pop     r14
0x1800227a1  pop     r12
0x1800227a3  pop     rdi
0x1800227a4  pop     rsi
0x1800227a5  pop     rbx
0x1800227a6  pop     rbp
0x1800227a7  retn
```
