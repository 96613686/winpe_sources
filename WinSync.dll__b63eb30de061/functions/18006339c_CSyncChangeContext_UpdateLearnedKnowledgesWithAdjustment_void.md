# CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment(void)

- ea: `0x18006339c`
- end: `0x180063acd`
- name: `?UpdateLearnedKnowledgesWithAdjustment@CSyncChangeContext@@AEAAJXZ`
- size: `1841`
- prototype: `__int64 __fastcall(CSyncChangeContext *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800630ac`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180021bec`
- `0x18006339c`
- `0x180067f28`
- `0x1800709c0`
- `0x180071f70`
- `0x1800721fc`
- `0x180072558`
- `0x180094010`

## string_xrefs

- `0x1800633d6`: `CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment`
- `0x180063a9e`: `CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment`

## pseudocode

```c
__int64 __fastcall CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment(CSyncChangeContext *this)
{
  CSyncChangeWrapper *v2; // rcx
  int v3; // esi
  unsigned __int8 *v4; // r12
  int v5; // eax
  CEnumSyncChangeUnitWrappers *v6; // r15
  int TransferFilters; // ebx
  unsigned int v8; // edx
  unsigned int *v9; // r9
  CSyncChangeUnitWrapper *v10; // rdi
  bool v11; // zf
  __int64 v12; // rcx
  _QWORD *v13; // rax
  struct CEnumSyncChangeUnitWrappers *v14; // rcx
  int v15; // eax
  unsigned int v16; // edx
  unsigned int *v17; // r9
  CSyncChangeUnitWrapper *v18; // rdi
  int v19; // ebx
  int v20; // eax
  unsigned __int8 *v21; // rbx
  struct CEnumSyncChangeUnitWrappers *v22; // rcx
  struct CEnumSyncChangeUnitWrappers *v23; // rcx
  __int64 v24; // r8
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  _QWORD *v28; // rdi
  __int64 v29; // rcx
  struct CEnumSyncChangeUnitWrappers *v30; // rcx
  int v31; // eax
  unsigned int v32; // edx
  unsigned int *v33; // r9
  CSyncChangeUnitWrapper *v34; // rdi
  int v35; // ebx
  int v36; // eax
  unsigned __int8 *v37; // rsi
  _QWORD *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // eax
  CSyncChangeUnitWrapper *v45[3]; // [rsp+30h] [rbp-18h] BYREF
  struct CEnumSyncChangeUnitWrappers *v46; // [rsp+90h] [rbp+48h] BYREF
  __int64 v47; // [rsp+98h] [rbp+50h] BYREF
  struct CEnumSyncChangeUnitWrappers *v48; // [rsp+A0h] [rbp+58h] BYREF
  CSyncChangeUnitWrapper *v49; // [rsp+A8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      "CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment");
  }
  v2 = (CSyncChangeWrapper *)*((_QWORD *)this + 6);
  v3 = 1;
  v46 = 0;
  v4 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v5 = CSyncChangeWrapper::GetChangeUnitWrappers(v2, &v46);
  v6 = v46;
  TransferFilters = v5;
  if ( v5 == -2147217393 )
    goto LABEL_15;
  if ( v5 < 0 )
    goto LABEL_56;
  TransferFilters = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v46 + 40LL))(v46);
  if ( TransferFilters < 0 )
    goto LABEL_56;
  v45[0] = 0;
  do
  {
    TransferFilters = CEnumSyncChangeUnitWrappers::Next(v6, v8, v45, v9);
    if ( TransferFilters )
      break;
    v10 = v45[0];
    LODWORD(v46) = 0;
    TransferFilters = CSyncChangeUnitWrapper::GetTransferFilters(v45[0], (enum SYNC_TRANSFER_FILTER *)&v46);
    if ( TransferFilters >= 0 )
      v3 = ((unsigned int)v46 & 0x80000) != 0 ? v3 : 0;
    (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  while ( v3 );
  if ( TransferFilters == 1 || (v11 = TransferFilters == 0, TransferFilters >= 0) )
  {
LABEL_15:
    TransferFilters = CSyncChangeWrapper::GetRootItemIdInternal(
                        *((CSyncChangeWrapper **)this + 6),
                        (unsigned __int8 **)&v49);
    if ( TransferFilters >= 0 )
    {
      TransferFilters = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 14) + 80LL))(
                          *((_QWORD *)this + 14),
                          &v47);
      if ( TransferFilters >= 0 )
      {
        v12 = *((_QWORD *)this + 16);
        if ( !v12
          || (TransferFilters = (*(__int64 (__fastcall **)(__int64, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)v12 + 80LL))(
                                  v12,
                                  &v48),
              TransferFilters >= 0) )
        {
          if ( v3 )
          {
            v13 = (_QWORD *)*((_QWORD *)this + 22);
            v4 = (unsigned __int8 *)v49;
            v46 = 0;
            TransferFilters = (*(__int64 (__fastcall **)(_QWORD, CSyncChangeUnitWrapper *, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)*v13 + 112LL))(
                                *v13,
                                v49,
                                &v46);
            if ( TransferFilters >= 0 )
            {
              TransferFilters = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v47 + 136LL))(
                                  v47,
                                  v4);
              if ( TransferFilters >= 0 )
              {
                if ( !v48
                  || (TransferFilters = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, unsigned __int8 *))(*(_QWORD *)v48 + 136LL))(
                                          v48,
                                          v4),
                      TransferFilters >= 0) )
                {
                  TransferFilters = (*(__int64 (__fastcall **)(__int64, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v47 + 104LL))(
                                      v47,
                                      v46);
                  if ( TransferFilters >= 0 )
                  {
                    if ( !v48 )
                    {
                      v14 = 0;
                      v48 = v46;
                      v46 = 0;
LABEL_28:
                      if ( v14 )
                        (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v14 + 16LL))(v14);
                      goto LABEL_56;
                    }
                    TransferFilters = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v48 + 104LL))(
                                        v48,
                                        v46);
                  }
                }
              }
            }
            v14 = v46;
            goto LABEL_28;
          }
          v15 = (*(__int64 (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v6 + 40LL))(v6);
          v4 = (unsigned __int8 *)v49;
          TransferFilters = v15;
          if ( v15 < 0 )
          {
LABEL_52:
            if ( TransferFilters == 1 )
              goto LABEL_58;
            goto LABEL_56;
          }
          v49 = 0;
          while ( 1 )
          {
            TransferFilters = CEnumSyncChangeUnitWrappers::Next(v6, v16, &v49, v17);
            if ( TransferFilters )
              goto LABEL_52;
            v18 = v49;
            v19 = 0;
            LODWORD(v46) = 0;
            if ( !(unsigned int)CSyncChangeUnitWrapper::GetError(v49) )
            {
              if ( (int)CSyncChangeUnitWrapper::GetTransferFilters(v18, (enum SYNC_TRANSFER_FILTER *)&v46) < 0 )
                goto LABEL_50;
              v19 = (int)v46;
            }
            if ( (v19 & 0x80000) != 0 )
              break;
LABEL_50:
            (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v18 + 16LL))(v18);
          }
          v45[0] = 0;
          v46 = 0;
          v20 = CSyncChangeUnitWrapper::GetChangeUnitIdInternal(v18, (unsigned __int8 **)v45);
          v21 = (unsigned __int8 *)v45[0];
          if ( v20 < 0
            || (*(int (__fastcall **)(_QWORD, unsigned __int8 *, CSyncChangeUnitWrapper *, struct CEnumSyncChangeUnitWrappers **))(***((_QWORD ***)this + 22) + 120LL))(
                 **((_QWORD **)this + 22),
                 v4,
                 v45[0],
                 &v46) < 0 )
          {
            goto LABEL_46;
          }
          v22 = v48;
          if ( v48 )
          {
            if ( (*(int (__fastcall **)(__int64, unsigned __int8 *, unsigned __int8 *))(*(_QWORD *)v47 + 144LL))(
                   v47,
                   v4,
                   v21) < 0 )
              goto LABEL_46;
            v22 = v48;
          }
          if ( (*(int (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, unsigned __int8 *, unsigned __int8 *))(*(_QWORD *)v22 + 144LL))(
                 v22,
                 v4,
                 v21) >= 0
            && (*(int (__fastcall **)(__int64, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v47 + 104LL))(v47, v46) >= 0 )
          {
            if ( !v48 )
            {
              v23 = 0;
              v48 = v46;
              v46 = 0;
              goto LABEL_47;
            }
            (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v48 + 104LL))(
              v48,
              v46);
          }
LABEL_46:
          v23 = v46;
LABEL_47:
          if ( v23 )
            (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v23 + 16LL))(v23);
          IdParameters::FreeId(v21);
          goto LABEL_50;
        }
      }
    }
    v4 = (unsigned __int8 *)v49;
LABEL_56:
    v11 = TransferFilters == 0;
  }
  if ( !v11 )
    goto LABEL_97;
LABEL_58:
  v24 = *((_QWORD *)this + 23);
  v25 = (__int64 *)(*((_QWORD *)this + 6) + 48LL);
  v49 = 0;
  v26 = *v25;
  if ( *((_DWORD *)this + 39) )
    v27 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, CSyncChangeUnitWrapper **))(v26 + 80))(
            v25,
            v47,
            v24,
            &v49);
  else
    v27 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, CSyncChangeUnitWrapper **))(v26 + 72))(
            v25,
            v47,
            v24,
            &v49);
  TransferFilters = v27;
  if ( v27 < 0 )
    goto LABEL_95;
  if ( !v3 )
  {
    TransferFilters = (*(__int64 (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v6 + 40LL))(v6);
    if ( TransferFilters < 0 )
    {
LABEL_93:
      if ( TransferFilters == 1 )
        TransferFilters = 0;
      goto LABEL_95;
    }
    v45[0] = 0;
    while ( 1 )
    {
      TransferFilters = CEnumSyncChangeUnitWrappers::Next(v6, v32, v45, v33);
      if ( TransferFilters )
        goto LABEL_93;
      v34 = v45[0];
      v35 = 0;
      LODWORD(v46) = 0;
      if ( !(unsigned int)CSyncChangeUnitWrapper::GetError(v45[0]) )
      {
        if ( (int)CSyncChangeUnitWrapper::GetTransferFilters(v34, (enum SYNC_TRANSFER_FILTER *)&v46) < 0 )
          goto LABEL_91;
        v35 = (int)v46;
      }
      if ( (v35 & 0x80000) != 0 )
      {
        v46 = 0;
        v36 = CSyncChangeUnitWrapper::GetChangeUnitIdInternal(v34, (unsigned __int8 **)&v46);
        v37 = (unsigned __int8 *)v46;
        if ( v36 >= 0 )
        {
          v38 = (_QWORD *)((char *)this + 120);
          v39 = *((_QWORD *)this + 15);
          if ( !v39
            || (*(int (__fastcall **)(__int64, unsigned __int8 *, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v39 + 144LL))(
                 v39,
                 v4,
                 v46) >= 0 )
          {
            if ( v49 )
            {
              v46 = 0;
              if ( (*(int (__fastcall **)(CSyncChangeUnitWrapper *, unsigned __int8 *, unsigned __int8 *, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)v49 + 120LL))(
                     v49,
                     v4,
                     v37,
                     &v46) >= 0 )
              {
                if ( *v38 )
                  (*(void (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)*v38 + 104LL))(
                    *v38,
                    v46);
                else
                  (**(void (__fastcall ***)(struct CEnumSyncChangeUnitWrappers *, GUID *, char *))v46)(
                    v46,
                    &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
                    (char *)this + 120);
              }
              if ( v46 )
                (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v46 + 16LL))(v46);
            }
          }
        }
        IdParameters::FreeId(v37);
      }
LABEL_91:
      (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v34 + 16LL))(v34);
    }
  }
  v28 = (_QWORD *)((char *)this + 120);
  v29 = *((_QWORD *)this + 15);
  if ( !v29
    || (TransferFilters = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v29 + 136LL))(v29, v4),
        TransferFilters >= 0) )
  {
    v30 = 0;
    v46 = 0;
    if ( v49 )
    {
      TransferFilters = (*(__int64 (__fastcall **)(CSyncChangeUnitWrapper *, unsigned __int8 *, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)v49 + 112LL))(
                          v49,
                          v4,
                          &v46);
      if ( TransferFilters < 0 )
        goto LABEL_72;
      v30 = v46;
    }
    if ( *v28 )
      v31 = (*(__int64 (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)*v28 + 104LL))(
              *v28,
              v30);
    else
      v31 = (**(__int64 (__fastcall ***)(struct CEnumSyncChangeUnitWrappers *, GUID *, char *))v30)(
              v30,
              &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
              (char *)this + 120);
    TransferFilters = v31;
LABEL_72:
    if ( v46 )
      (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v46 + 16LL))(v46);
  }
LABEL_95:
  if ( v49 )
    (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v49 + 16LL))(v49);
LABEL_97:
  if ( TransferFilters >= 0 )
  {
    TransferFilters = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 104LL))(v47, *((_QWORD *)this + 13));
    if ( TransferFilters >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 16LL))(*((_QWORD *)this + 13));
      v40 = v47;
      v41 = *((_QWORD *)this + 6);
      *((_QWORD *)this + 13) = v47;
      v47 = 0;
      if ( !*(_QWORD *)(v41 + 256)
        || (TransferFilters = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40), TransferFilters >= 0) )
      {
        if ( v48 )
        {
          v42 = *((_QWORD *)this + 15);
          if ( v42 )
            v43 = (*(__int64 (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v42 + 104LL))(
                    *((_QWORD *)this + 15),
                    v48);
          else
            v43 = (**(__int64 (__fastcall ***)(struct CEnumSyncChangeUnitWrappers *, GUID *, char *))v48)(
                    v48,
                    &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
                    (char *)this + 120);
          TransferFilters = v43;
        }
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v48 )
    (*(void (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v48 + 16LL))(v48);
  IdParameters::FreeId(v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      (unsigned int)"CSyncChangeContext::UpdateLearnedKnowledgesWithAdjustment",
      TransferFilters);
  }
  return (unsigned int)TransferFilters;
}

```

## disassembly

```asm
0x18006339c  push    rbp
0x18006339e  push    rbx
0x18006339f  push    rsi
0x1800633a0  push    rdi
0x1800633a1  push    r12
0x1800633a3  push    r13
0x1800633a5  push    r14
0x1800633a7  push    r15
0x1800633a9  mov     rbp, rsp
0x1800633ac  sub     rsp, 48h
0x1800633b0  mov     r14, rcx
0x1800633b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800633ba  lea     rax, WPP_GLOBAL_Control
0x1800633c1  cmp     rcx, rax
0x1800633c4  jz      short loc_1800633EE
0x1800633c6  test    byte ptr [rcx+1Ch], 8
0x1800633ca  jz      short loc_1800633EE
0x1800633cc  cmp     byte ptr [rcx+19h], 5
0x1800633d0  jb      short loc_1800633EE
0x1800633d2  mov     rcx, [rcx+10h]
0x1800633d6  lea     r9, aCsyncchangecon_7; "CSyncChangeContext::UpdateLearnedKnowle"...
0x1800633dd  mov     edx, 15h
0x1800633e2  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x1800633e9  call    WPP_SF_s
0x1800633ee  mov     rcx, [r14+30h]; this
0x1800633f2  lea     rdx, [rbp+arg_0]; struct CEnumSyncChangeUnitWrappers **
0x1800633f6  xor     r13d, r13d
0x1800633f9  mov     esi, 1
0x1800633fe  mov     [rbp+arg_0], r13
0x180063402  mov     r12d, r13d
0x180063405  mov     [rbp+arg_8], r13
0x180063409  mov     [rbp+arg_10], r13
0x18006340d  mov     [rbp+arg_18], r13
0x180063411  call    ?GetChangeUnitWrappers@CSyncChangeWrapper@@QEAAJPEAPEAVCEnumSyncChangeUnitWrappers@@@Z; CSyncChangeWrapper::GetChangeUnitWrappers(CEnumSyncChangeUnitWrappers * *)
0x180063416  mov     r15, [rbp+arg_0]
0x18006341a  mov     ebx, eax
0x18006341c  cmp     eax, 8004100Fh
0x180063421  jz      short loc_1800634A2
0x180063423  test    eax, eax
0x180063425  js      loc_180063744
0x18006342b  mov     rax, [r15]
0x18006342e  mov     rcx, r15
0x180063431  mov     rax, [rax+28h]
0x180063435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006343a  mov     ebx, eax
0x18006343c  test    eax, eax
0x18006343e  js      loc_180063744
0x180063444  mov     [rbp+var_18], r13
0x180063448  lea     r8, [rbp+var_18]; struct CSyncChangeUnitWrapper **
0x18006344c  mov     rcx, r15; this
0x18006344f  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x180063454  mov     ebx, eax
0x180063456  test    eax, eax
0x180063458  jnz     short loc_180063495
0x18006345a  mov     rdi, [rbp+var_18]
0x18006345e  lea     rdx, [rbp+arg_0]; enum SYNC_TRANSFER_FILTER *
0x180063462  mov     rcx, rdi; this
0x180063465  mov     dword ptr [rbp+arg_0], r13d
0x180063469  call    ?GetTransferFilters@CSyncChangeUnitWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x18006346e  mov     ebx, eax
0x180063470  test    eax, eax
0x180063472  js      short loc_180063482
0x180063474  mov     eax, dword ptr [rbp+arg_0]
0x180063477  and     eax, 80000h
0x18006347c  neg     eax
0x18006347e  sbb     eax, eax
0x180063480  and     esi, eax
0x180063482  mov     rax, [rdi]
0x180063485  mov     rcx, rdi
0x180063488  mov     rax, [rax+10h]
0x18006348c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063491  test    esi, esi
0x180063493  jnz     short loc_180063448
0x180063495  cmp     ebx, 1
0x180063498  jz      short loc_1800634A2
0x18006349a  test    ebx, ebx
0x18006349c  js      loc_180063746
0x1800634a2  mov     rcx, [r14+30h]; this
0x1800634a6  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x1800634aa  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x1800634af  mov     ebx, eax
0x1800634b1  test    eax, eax
0x1800634b3  js      loc_180063740
0x1800634b9  mov     rcx, [r14+70h]
0x1800634bd  lea     rdx, [rbp+arg_8]
0x1800634c1  mov     rax, [rcx]
0x1800634c4  mov     rax, [rax+50h]
0x1800634c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634cd  mov     ebx, eax
0x1800634cf  test    eax, eax
0x1800634d1  js      loc_180063740
0x1800634d7  mov     rcx, [r14+80h]
0x1800634de  test    rcx, rcx
0x1800634e1  jz      short loc_1800634FD
0x1800634e3  mov     rax, [rcx]
0x1800634e6  lea     rdx, [rbp+arg_10]
0x1800634ea  mov     rax, [rax+50h]
0x1800634ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634f3  mov     ebx, eax
0x1800634f5  test    eax, eax
0x1800634f7  js      loc_180063740
0x1800634fd  test    esi, esi
0x1800634ff  jz      loc_1800635D1
0x180063505  mov     rax, [r14+0B0h]
0x18006350c  lea     r8, [rbp+arg_0]
0x180063510  mov     r12, [rbp+arg_18]
0x180063514  mov     [rbp+arg_0], r13
0x180063518  mov     rdx, r12
0x18006351b  mov     rcx, [rax]
0x18006351e  mov     rax, [rcx]
0x180063521  mov     rax, [rax+70h]
0x180063525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006352a  mov     ebx, eax
0x18006352c  test    eax, eax
0x18006352e  js      short loc_1800635A2
0x180063530  mov     rcx, [rbp+arg_8]
0x180063534  mov     rdx, r12
0x180063537  mov     rax, [rcx]
0x18006353a  mov     rax, [rax+88h]
0x180063541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063546  mov     ebx, eax
0x180063548  test    eax, eax
0x18006354a  js      short loc_1800635A2
0x18006354c  mov     rcx, [rbp+arg_10]
0x180063550  test    rcx, rcx
0x180063553  jz      short loc_18006356D
0x180063555  mov     rax, [rcx]
0x180063558  mov     rdx, r12
0x18006355b  mov     rax, [rax+88h]
0x180063562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063567  mov     ebx, eax
0x180063569  test    eax, eax
0x18006356b  js      short loc_1800635A2
0x18006356d  mov     rcx, [rbp+arg_8]
0x180063571  mov     rdx, [rbp+arg_0]
0x180063575  mov     rax, [rcx]
0x180063578  mov     rax, [rax+68h]
0x18006357c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063581  mov     ebx, eax
0x180063583  test    eax, eax
0x180063585  js      short loc_1800635A2
0x180063587  mov     rcx, [rbp+arg_10]
0x18006358b  test    rcx, rcx
0x18006358e  jz      short loc_1800635C0
0x180063590  mov     rax, [rcx]
0x180063593  mov     rdx, [rbp+arg_0]
0x180063597  mov     rax, [rax+68h]
0x18006359b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635a0  mov     ebx, eax
0x1800635a2  mov     rcx, [rbp+arg_0]
0x1800635a6  test    rcx, rcx
0x1800635a9  jz      loc_180063744
0x1800635af  mov     rax, [rcx]
0x1800635b2  mov     rax, [rax+10h]
0x1800635b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635bb  jmp     loc_180063744
0x1800635c0  mov     rax, [rbp+arg_0]
0x1800635c4  mov     rcx, r13
0x1800635c7  mov     [rbp+arg_10], rax
0x1800635cb  mov     [rbp+arg_0], rcx
0x1800635cf  jmp     short loc_1800635A6
0x1800635d1  mov     rax, [r15]
0x1800635d4  mov     rcx, r15
0x1800635d7  mov     rax, [rax+28h]
0x1800635db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635e0  mov     r12, [rbp+arg_18]
0x1800635e4  mov     ebx, eax
0x1800635e6  test    eax, eax
0x1800635e8  js      loc_180063728
0x1800635ee  mov     [rbp+arg_18], r13
0x1800635f2  jmp     loc_180063712
0x1800635f7  mov     rdi, [rbp+arg_18]
0x1800635fb  mov     ebx, r13d
0x1800635fe  mov     rcx, rdi; this
0x180063601  mov     dword ptr [rbp+arg_0], ebx
0x180063604  call    ?GetError@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::GetError(void)
0x180063609  test    eax, eax
0x18006360b  jnz     short loc_180063624
0x18006360d  lea     rdx, [rbp+arg_0]; enum SYNC_TRANSFER_FILTER *
0x180063611  mov     rcx, rdi; this
0x180063614  call    ?GetTransferFilters@CSyncChangeUnitWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeUnitWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x180063619  test    eax, eax
0x18006361b  js      loc_180063703
0x180063621  mov     ebx, dword ptr [rbp+arg_0]
0x180063624  bt      ebx, 13h
0x180063628  jnb     loc_180063703
0x18006362e  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x180063632  mov     [rbp+var_18], r13
0x180063636  mov     rcx, rdi; this
0x180063639  mov     [rbp+arg_0], r13
0x18006363d  call    ?GetChangeUnitIdInternal@CSyncChangeUnitWrapper@@QEAAJPEAPEAE@Z; CSyncChangeUnitWrapper::GetChangeUnitIdInternal(uchar * *)
0x180063642  mov     rbx, [rbp+var_18]
0x180063646  test    eax, eax
0x180063648  js      loc_1800636E6
0x18006364e  mov     rax, [r14+0B0h]
0x180063655  lea     r9, [rbp+arg_0]
0x180063659  mov     r8, rbx
0x18006365c  mov     rdx, r12
0x18006365f  mov     rcx, [rax]
0x180063662  mov     rax, [rcx]
0x180063665  mov     rax, [rax+78h]
0x180063669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006366e  test    eax, eax
0x180063670  js      short loc_1800636E6
0x180063672  mov     rcx, [rbp+arg_10]
0x180063676  test    rcx, rcx
0x180063679  jz      short loc_18006369C
0x18006367b  mov     rcx, [rbp+arg_8]
0x18006367f  mov     r8, rbx
0x180063682  mov     rdx, r12
0x180063685  mov     rax, [rcx]
0x180063688  mov     rax, [rax+90h]
0x18006368f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063694  test    eax, eax
0x180063696  js      short loc_1800636E6
0x180063698  mov     rcx, [rbp+arg_10]
0x18006369c  mov     rax, [rcx]
0x18006369f  mov     r8, rbx
0x1800636a2  mov     rdx, r12
0x1800636a5  mov     rax, [rax+90h]
0x1800636ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636b1  test    eax, eax
0x1800636b3  js      short loc_1800636E6
0x1800636b5  mov     rcx, [rbp+arg_8]
0x1800636b9  mov     rdx, [rbp+arg_0]
0x1800636bd  mov     rax, [rcx]
0x1800636c0  mov     rax, [rax+68h]
0x1800636c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636c9  test    eax, eax
0x1800636cb  js      short loc_1800636E6
0x1800636cd  mov     rcx, [rbp+arg_10]
0x1800636d1  test    rcx, rcx
0x1800636d4  jz      short loc_18006372F
0x1800636d6  mov     rax, [rcx]
0x1800636d9  mov     rdx, [rbp+arg_0]
0x1800636dd  mov     rax, [rax+68h]
0x1800636e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636e6  mov     rcx, [rbp+arg_0]
0x1800636ea  test    rcx, rcx
0x1800636ed  jz      short loc_1800636FB
0x1800636ef  mov     rax, [rcx]
0x1800636f2  mov     rax, [rax+10h]
0x1800636f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636fb  mov     rcx, rbx; unsigned __int8 *
0x1800636fe  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180063703  mov     rax, [rdi]
0x180063706  mov     rcx, rdi
0x180063709  mov     rax, [rax+10h]
0x18006370d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063712  lea     r8, [rbp+arg_18]; struct CSyncChangeUnitWrapper **
0x180063716  mov     rcx, r15; this
0x180063719  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x18006371e  mov     ebx, eax
0x180063720  test    eax, eax
0x180063722  jz      loc_1800635F7
0x180063728  cmp     ebx, 1
0x18006372b  jz      short loc_18006374C
0x18006372d  jmp     short loc_180063744
0x18006372f  mov     rax, [rbp+arg_0]
0x180063733  mov     rcx, r13
0x180063736  mov     [rbp+arg_10], rax
0x18006373a  mov     [rbp+arg_0], rcx
0x18006373e  jmp     short loc_1800636EA
0x180063740  mov     r12, [rbp+arg_18]
0x180063744  test    ebx, ebx
0x180063746  jnz     loc_18006398F
0x18006374c  mov     rcx, [r14+30h]
0x180063750  lea     r9, [rbp+arg_18]
0x180063754  mov     r8, [r14+0B8h]
0x18006375b  add     rcx, 30h ; '0'
0x18006375f  mov     rdx, [rbp+arg_8]
0x180063763  mov     [rbp+arg_18], r13
0x180063767  mov     rax, [rcx]
0x18006376a  cmp     [r14+9Ch], r13d
0x180063771  jz      short loc_180063779
0x180063773  mov     rax, [rax+50h]
0x180063777  jmp     short loc_18006377D
0x180063779  mov     rax, [rax+48h]
0x18006377d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063782  mov     ebx, eax
0x180063784  test    eax, eax
0x180063786  js      loc_18006397A
0x18006378c  test    esi, esi
0x18006378e  jz      loc_18006383D
0x180063794  lea     rdi, [r14+78h]
0x180063798  mov     rcx, [rdi]
0x18006379b  test    rcx, rcx
0x18006379e  jz      short loc_1800637BC
0x1800637a0  mov     rax, [rcx]
0x1800637a3  mov     rdx, r12
0x1800637a6  mov     rax, [rax+88h]
0x1800637ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800637b2  mov     ebx, eax
0x1800637b4  test    eax, eax
0x1800637b6  js      loc_18006397A
0x1800637bc  mov     r9, [rbp+arg_18]
0x1800637c0  mov     rcx, r13
0x1800637c3  mov     [rbp+arg_0], rcx
0x1800637c7  test    r9, r9
0x1800637ca  jz      short loc_1800637EC
  ... truncated ...
```
