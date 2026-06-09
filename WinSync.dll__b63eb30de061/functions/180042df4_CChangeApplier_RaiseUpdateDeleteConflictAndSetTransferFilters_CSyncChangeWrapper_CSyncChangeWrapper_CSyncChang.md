# CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters(CSyncChangeWrapper *,CSyncChangeWrapper *,CSyncChangeWrapper *)

- ea: `0x180042df4`
- end: `0x18004336d`
- name: `?RaiseUpdateDeleteConflictAndSetTransferFilters@CChangeApplier@@AEAAJPEAVCSyncChangeWrapper@@00@Z`
- size: `1401`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct CSyncChangeWrapper *, struct CSyncChangeWrapper *, struct CSyncChangeWrapper *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x18003f34c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180021bec`
- `0x180035724`
- `0x180042df4`
- `0x180067f28`
- `0x18006cc00`
- `0x18006cd94`
- `0x18006d9c8`
- `0x18006e608`
- `0x18006ef64`
- `0x1800709c0`
- `0x180072974`
- `0x180094010`

## string_xrefs

- `0x180042e3b`: `CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters`
- `0x18004333e`: `CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters`

## pseudocode

```c
__int64 __fastcall CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters(
        CChangeApplier *this,
        struct CSyncChangeWrapper *a2,
        struct CSyncChangeWrapper *a3,
        struct ISyncKnowledge *a4)
{
  struct CSyncChangeWrapper *v4; // r13
  PVOID *v8; // rcx
  CEnumSyncChangeUnitWrappers *v9; // rdi
  int RootItemIdInternal; // ebx
  __int64 v11; // rdx
  CChangeConflict *v12; // rax
  CChangeConflict *v13; // r14
  int v14; // eax
  unsigned int v15; // edx
  unsigned int *v16; // r9
  int v17; // eax
  CSyncChangeUnitWrapper *v18; // r13
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  unsigned __int8 *v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned int v26; // [rsp+40h] [rbp-38h] BYREF
  struct IChangeConflict *v27; // [rsp+48h] [rbp-30h] BYREF
  struct CEnumSyncChangeUnitWrappers *v28; // [rsp+50h] [rbp-28h] BYREF
  __int64 v29; // [rsp+58h] [rbp-20h] BYREF
  CSyncChangeUnitWrapper *v30[3]; // [rsp+60h] [rbp-18h] BYREF
  struct ISyncKnowledge *v31; // [rsp+D8h] [rbp+60h] BYREF

  v31 = a4;
  v4 = (struct CSyncChangeWrapper *)a4;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      147,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  RootItemIdInternal = -2147467261;
  if ( v4 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        v11 = *((_QWORD *)this + 50);
        v26 = 0;
        if ( v11 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          RootItemIdInternal = CSyncChangeWrapper::SetConflict(a3, v4, 0, 1);
          if ( RootItemIdInternal >= 0 )
          {
            RootItemIdInternal = (**(__int64 (__fastcall ***)(struct CSyncChangeWrapper *, GUID *, struct IChangeConflict **))a3)(
                                   a3,
                                   &GUID_014ebf97_9f20_4f7a_bdd4_25979c77c002,
                                   &v27);
            if ( RootItemIdInternal >= 0 )
            {
              RootItemIdInternal = -2147024882;
              v12 = (CChangeConflict *)SeAlloc(0x38u);
              if ( v12 )
              {
                v13 = CChangeConflict::CChangeConflict(v12, v27, this);
                if ( v13 )
                {
                  RootItemIdInternal = CChangeApplier::ChangeState((__int64)this, 18);
                  if ( RootItemIdInternal >= 0 )
                  {
                    RootItemIdInternal = CSyncChangeWrapper::SetConflictFilter(v4, 1, 1);
                    if ( RootItemIdInternal >= 0 )
                      RootItemIdInternal = CSyncChangeWrapper::SetConflictFilter(a3, 1, 1);
                  }
                  v28 = 0;
                  if ( RootItemIdInternal >= 0 )
                  {
                    v14 = CSyncChangeWrapper::GetChangeUnitWrappers(a3, &v28);
                    RootItemIdInternal = v14;
                    if ( v14 == -2147217393 || v14 >= 0 )
                    {
                      v9 = v28;
                      if ( v28 )
                      {
                        RootItemIdInternal = (*(__int64 (__fastcall **)(struct CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v28 + 40LL))(v28);
                        while ( RootItemIdInternal >= 0 )
                        {
                          v30[0] = 0;
                          v17 = CEnumSyncChangeUnitWrappers::Next(v9, v15, v30, v16);
                          RootItemIdInternal = v17;
                          if ( v17 == 1 )
                          {
                            v4 = (struct CSyncChangeWrapper *)v31;
                            goto LABEL_29;
                          }
                          v18 = v30[0];
                          if ( v17 >= 0 )
                            RootItemIdInternal = CSyncChangeUnitWrapper::SetConflict(v30[0]);
                          if ( v18 )
                            (*(void (__fastcall **)(CSyncChangeUnitWrapper *))(*(_QWORD *)v18 + 16LL))(v18);
                        }
                      }
                      else
                      {
LABEL_29:
                        v19 = (*(__int64 (__fastcall **)(_QWORD, CChangeConflict *))(**((_QWORD **)this + 50) + 40LL))(
                                *((_QWORD *)this + 50),
                                v13);
                        RootItemIdInternal = v19;
                        if ( v19 == -2147217374 || v19 >= 0 )
                        {
                          RootItemIdInternal = CChangeApplier::ChangeState((__int64)this, 19);
                          if ( RootItemIdInternal >= 0 )
                          {
                            RootItemIdInternal = CSyncChangeWrapper::SetConflictFilter(v4, 0, 0);
                            if ( RootItemIdInternal >= 0 )
                            {
                              RootItemIdInternal = CSyncChangeWrapper::SetConflictFilter(a3, 0, 0);
                              if ( RootItemIdInternal >= 0 )
                                RootItemIdInternal = ((__int64 (__fastcall *)(struct IChangeConflict *, unsigned int *))v27->lpVtbl->GetResolveActionForChange)(
                                                       v27,
                                                       &v26);
                            }
                          }
                        }
                      }
                    }
                    else
                    {
                      v9 = v28;
                    }
                  }
                  (*(void (__fastcall **)(CChangeConflict *))(*(_QWORD *)v13 + 16LL))(v13);
                  if ( v9 )
                    (*(void (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v9 + 16LL))(v9);
                  v9 = 0;
                }
              }
            }
            ((void (__fastcall *)(struct IChangeConflict *))v27->lpVtbl->Release)(v27);
          }
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 16LL))(*((_QWORD *)this + 50));
          if ( RootItemIdInternal < 0 )
            goto LABEL_74;
          if ( ((v26 - 1) & 0xFFFFFFFD) == 0 )
          {
            RootItemIdInternal = CSyncChangeWrapper::SetConflict(a2, a3, 0, 0);
            if ( RootItemIdInternal >= 0 )
            {
              v31 = 0;
              RootItemIdInternal = CSyncChangeWrapper::GetRootItemIdInternal(a2, (unsigned __int8 **)&v31);
              if ( RootItemIdInternal >= 0 )
              {
                v30[0] = 0;
                v21 = CSyncChangeWrapper::GetRootItemIdInternal(a3, (unsigned __int8 **)v30);
                v22 = (unsigned __int8 *)v31;
                RootItemIdInternal = v21;
                if ( v21 >= 0 )
                {
                  v23 = *((_QWORD *)this + 16);
                  v28 = 0;
                  v27 = 0;
                  v31 = 0;
                  v29 = 0;
                  RootItemIdInternal = (*(__int64 (__fastcall **)(__int64, struct CEnumSyncChangeUnitWrappers **))(*(_QWORD *)v23 + 56LL))(
                                         v23,
                                         &v28);
                  if ( RootItemIdInternal >= 0 )
                  {
                    RootItemIdInternal = (*(__int64 (__fastcall **)(_QWORD, struct CEnumSyncChangeUnitWrappers *))(**((_QWORD **)this + 64) + 40LL))(
                                           *((_QWORD *)this + 64),
                                           v28);
                    if ( RootItemIdInternal >= 0 )
                    {
                      RootItemIdInternal = (*(__int64 (__fastcall **)(char *, struct IChangeConflict **))(*((_QWORD *)a2 + 1) + 80LL))(
                                             (char *)a2 + 8,
                                             &v27);
                      if ( RootItemIdInternal >= 0 )
                      {
                        RootItemIdInternal = ((__int64 (__fastcall *)(struct IChangeConflict *, struct ISyncKnowledge **))v27->lpVtbl->SetResolveActionForChangeUnit)(
                                               v27,
                                               &v31);
                        if ( RootItemIdInternal >= 0 )
                        {
                          RootItemIdInternal = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, __int64 *))(**((_QWORD **)this + 64) + 112LL))(
                                                 *((_QWORD *)this + 64),
                                                 v22,
                                                 &v29);
                          if ( RootItemIdInternal >= 0 )
                          {
                            RootItemIdInternal = ((__int64 (__fastcall *)(struct ISyncKnowledge *, __int64))v31->lpVtbl->Union)(
                                                   v31,
                                                   v29);
                            if ( RootItemIdInternal >= 0 )
                            {
                              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 8LL))(*((_QWORD *)this + 64));
                              v9 = (CEnumSyncChangeUnitWrappers *)*((_QWORD *)this + 64);
                              RootItemIdInternal = CSyncChangeWrapper::SetNewMerge(
                                                     a2,
                                                     *((unsigned __int8 **)this + 15),
                                                     v22,
                                                     (unsigned __int8 *)v30[0],
                                                     1u,
                                                     v31,
                                                     (struct ISyncKnowledge *)v9,
                                                     (unsigned __int64)v28);
                              if ( RootItemIdInternal >= 0 )
                              {
                                v24 = 4098;
                                if ( v26 != 3 )
                                  v24 = 1026;
                                RootItemIdInternal = CSyncChangeWrapper::SetTransferFilters(a2, v24);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  if ( v27 )
                    ((void (__fastcall *)(struct IChangeConflict *))v27->lpVtbl->Release)(v27);
                  if ( v31 )
                    ((void (__fastcall *)(struct ISyncKnowledge *))v31->lpVtbl->Release)(v31);
                  if ( v29 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                  if ( v9 )
                    (*(void (__fastcall **)(CEnumSyncChangeUnitWrappers *))(*(_QWORD *)v9 + 16LL))(v9);
                  IdParameters::FreeId((unsigned __int8 *)v30[0]);
                }
                IdParameters::FreeId(v22);
              }
            }
            goto LABEL_74;
          }
          if ( v26 == 2 )
          {
            RootItemIdInternal = CSyncChangeWrapper::SetConflict(a2, a3, 0, 1);
            if ( RootItemIdInternal < 0 )
              goto LABEL_74;
            RootItemIdInternal = (*(__int64 (__fastcall **)(struct CSyncChangeWrapper *, _QWORD))(*(_QWORD *)a2 + 64LL))(
                                   a2,
                                   v26);
            if ( RootItemIdInternal < 0 )
              goto LABEL_74;
            v20 = 2;
          }
          else if ( v26 == 4 )
          {
            if ( *((_DWORD *)this + 162) || (v20 = 32, *((int *)this + 163) <= 0) )
              v20 = 16;
          }
          else
          {
            v20 = 32;
          }
          RootItemIdInternal = CSyncChangeWrapper::SetTransferFilters(a2, v20);
LABEL_74:
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      148,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::RaiseUpdateDeleteConflictAndSetTransferFilters",
      RootItemIdInternal);
  return (unsigned int)RootItemIdInternal;
}

```

## disassembly

```asm
0x180042df4  mov     [rsp-40h+arg_18], r9
0x180042df9  push    rbp
0x180042dfa  push    rbx
0x180042dfb  push    rsi
0x180042dfc  push    rdi
0x180042dfd  push    r12
0x180042dff  push    r13
0x180042e01  push    r14
0x180042e03  push    r15
0x180042e05  mov     rbp, rsp
0x180042e08  sub     rsp, 78h
0x180042e0c  mov     r13, r9
0x180042e0f  mov     r12, r8
0x180042e12  mov     rsi, rdx
0x180042e15  mov     r15, rcx
0x180042e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e1f  lea     rax, WPP_GLOBAL_Control
0x180042e26  cmp     rcx, rax
0x180042e29  jz      short loc_180042E5A
0x180042e2b  test    byte ptr [rcx+1Ch], 8
0x180042e2f  jz      short loc_180042E5A
0x180042e31  cmp     byte ptr [rcx+19h], 5
0x180042e35  jb      short loc_180042E5A
0x180042e37  mov     rcx, [rcx+10h]
0x180042e3b  lea     r9, aCchangeapplier_1; "CChangeApplier::RaiseUpdateDeleteConfli"...
0x180042e42  mov     edx, 93h
0x180042e47  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180042e4e  call    WPP_SF_s
0x180042e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e5a  xor     edi, edi
0x180042e5c  mov     ebx, 80004003h
0x180042e61  test    r13, r13
0x180042e64  jz      loc_180043322
0x180042e6a  test    r12, r12
0x180042e6d  jz      loc_180043322
0x180042e73  test    rsi, rsi
0x180042e76  jz      loc_180043322
0x180042e7c  mov     rdx, [r15+190h]
0x180042e83  mov     [rbp+var_38], edi
0x180042e86  test    rdx, rdx
0x180042e89  jz      loc_180043322
0x180042e8f  mov     [rbp+var_30], rdi
0x180042e93  mov     rcx, rdx
0x180042e96  mov     rax, [rdx]
0x180042e99  mov     rax, [rax+8]
0x180042e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ea2  lea     r9d, [rdi+1]; int
0x180042ea6  xor     r8d, r8d; struct CSyncChangeWrapper *
0x180042ea9  mov     rdx, r13; struct CSyncChangeWrapper *
0x180042eac  mov     rcx, r12; this
0x180042eaf  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x180042eb4  mov     ebx, eax
0x180042eb6  test    eax, eax
0x180042eb8  js      loc_18004308B
0x180042ebe  mov     rax, [r12]
0x180042ec2  lea     r8, [rbp+var_30]
0x180042ec6  lea     rdx, _GUID_014ebf97_9f20_4f7a_bdd4_25979c77c002
0x180042ecd  mov     rcx, r12
0x180042ed0  mov     rax, [rax]
0x180042ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ed8  mov     ebx, eax
0x180042eda  test    eax, eax
0x180042edc  js      loc_18004307B
0x180042ee2  lea     ecx, [rdi+38h]; unsigned __int64
0x180042ee5  mov     ebx, 8007000Eh
0x180042eea  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180042eef  test    rax, rax
0x180042ef2  jz      loc_18004307B
0x180042ef8  mov     rdx, [rbp+var_30]; struct IChangeConflict *
0x180042efc  mov     r8, r15; struct CChangeApplier *
0x180042eff  mov     rcx, rax; this
0x180042f02  call    ??0CChangeConflict@@QEAA@PEAUIChangeConflict@@PEAVCChangeApplier@@@Z; CChangeConflict::CChangeConflict(IChangeConflict *,CChangeApplier *)
0x180042f07  mov     r14, rax
0x180042f0a  test    rax, rax
0x180042f0d  jz      loc_18004307B
0x180042f13  lea     edx, [rdi+12h]
0x180042f16  mov     rcx, r15
0x180042f19  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180042f1e  mov     ebx, eax
0x180042f20  test    eax, eax
0x180042f22  js      short loc_180042F4C
0x180042f24  lea     eax, [rdi+1]
0x180042f27  mov     rcx, r13; this
0x180042f2a  mov     r8d, eax; int
0x180042f2d  mov     edx, eax; int
0x180042f2f  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x180042f34  mov     ebx, eax
0x180042f36  test    eax, eax
0x180042f38  js      short loc_180042F4C
0x180042f3a  lea     eax, [rdi+1]
0x180042f3d  mov     rcx, r12; this
0x180042f40  mov     r8d, eax; int
0x180042f43  mov     edx, eax; int
0x180042f45  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x180042f4a  mov     ebx, eax
0x180042f4c  mov     [rbp+var_28], rdi
0x180042f50  test    ebx, ebx
0x180042f52  js      loc_180043056
0x180042f58  lea     rdx, [rbp+var_28]; struct CEnumSyncChangeUnitWrappers **
0x180042f5c  mov     rcx, r12; this
0x180042f5f  call    ?GetChangeUnitWrappers@CSyncChangeWrapper@@QEAAJPEAPEAVCEnumSyncChangeUnitWrappers@@@Z; CSyncChangeWrapper::GetChangeUnitWrappers(CEnumSyncChangeUnitWrappers * *)
0x180042f64  mov     ebx, eax
0x180042f66  cmp     eax, 8004100Fh
0x180042f6b  jz      short loc_180042F7A
0x180042f6d  test    eax, eax
0x180042f6f  jns     short loc_180042F7A
0x180042f71  mov     rdi, [rbp+var_28]
0x180042f75  jmp     loc_180043056
0x180042f7a  mov     rdi, [rbp+var_28]
0x180042f7e  test    rdi, rdi
0x180042f81  jz      short loc_180042FE4
0x180042f83  mov     rax, [rdi]
0x180042f86  mov     rcx, rdi
0x180042f89  mov     rax, [rax+28h]
0x180042f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f92  mov     ebx, eax
0x180042f94  test    ebx, ebx
0x180042f96  js      loc_180043056
0x180042f9c  lea     r8, [rbp+var_18]; struct CSyncChangeUnitWrapper **
0x180042fa0  mov     [rbp+var_18], 0
0x180042fa8  mov     rcx, rdi; this
0x180042fab  call    ?Next@CEnumSyncChangeUnitWrappers@@QEAAJKPEAPEAVCSyncChangeUnitWrapper@@PEAK@Z; CEnumSyncChangeUnitWrappers::Next(ulong,CSyncChangeUnitWrapper * *,ulong *)
0x180042fb0  mov     ebx, eax
0x180042fb2  cmp     eax, 1
0x180042fb5  jz      short loc_180042FE0
0x180042fb7  mov     r13, [rbp+var_18]
0x180042fbb  test    eax, eax
0x180042fbd  js      short loc_180042FC9
0x180042fbf  mov     rcx, r13; this
0x180042fc2  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x180042fc7  mov     ebx, eax
0x180042fc9  test    r13, r13
0x180042fcc  jz      short loc_180042F94
0x180042fce  mov     rax, [r13+0]
0x180042fd2  mov     rcx, r13
0x180042fd5  mov     rax, [rax+10h]
0x180042fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fde  jmp     short loc_180042F94
0x180042fe0  mov     r13, [rbp+arg_18]
0x180042fe4  mov     rcx, [r15+190h]
0x180042feb  mov     rdx, r14
0x180042fee  mov     rax, [rcx]
0x180042ff1  mov     rax, [rax+28h]
0x180042ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ffa  mov     ebx, eax
0x180042ffc  cmp     eax, 80041022h
0x180043001  jz      short loc_180043007
0x180043003  test    eax, eax
0x180043005  js      short loc_180043056
0x180043007  mov     edx, 13h
0x18004300c  mov     rcx, r15
0x18004300f  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180043014  mov     ebx, eax
0x180043016  test    eax, eax
0x180043018  js      short loc_180043056
0x18004301a  xor     r8d, r8d; int
0x18004301d  xor     edx, edx; int
0x18004301f  mov     rcx, r13; this
0x180043022  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x180043027  mov     ebx, eax
0x180043029  test    eax, eax
0x18004302b  js      short loc_180043056
0x18004302d  xor     r8d, r8d; int
0x180043030  xor     edx, edx; int
0x180043032  mov     rcx, r12; this
0x180043035  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x18004303a  mov     ebx, eax
0x18004303c  test    eax, eax
0x18004303e  js      short loc_180043056
0x180043040  mov     rcx, [rbp+var_30]
0x180043044  lea     rdx, [rbp+var_38]
0x180043048  mov     rax, [rcx]
0x18004304b  mov     rax, [rax+38h]
0x18004304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043054  mov     ebx, eax
0x180043056  mov     rax, [r14]
0x180043059  mov     rcx, r14
0x18004305c  mov     rax, [rax+10h]
0x180043060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043065  test    rdi, rdi
0x180043068  jz      short loc_180043079
0x18004306a  mov     rax, [rdi]
0x18004306d  mov     rcx, rdi
0x180043070  mov     rax, [rax+10h]
0x180043074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043079  xor     edi, edi
0x18004307b  mov     rcx, [rbp+var_30]
0x18004307f  mov     rax, [rcx]
0x180043082  mov     rax, [rax+10h]
0x180043086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004308b  mov     rcx, [r15+190h]
0x180043092  mov     rax, [rcx]
0x180043095  mov     rax, [rax+10h]
0x180043099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004309e  test    ebx, ebx
0x1800430a0  js      loc_18004331B
0x1800430a6  mov     ecx, [rbp+var_38]
0x1800430a9  lea     eax, [rcx-1]
0x1800430ac  test    eax, 0FFFFFFFDh
0x1800430b1  jz      short loc_18004312C
0x1800430b3  cmp     ecx, 2
0x1800430b6  jnz     short loc_180043104
0x1800430b8  lea     r9d, [rcx-1]; int
0x1800430bc  xor     r8d, r8d; struct CSyncChangeWrapper *
0x1800430bf  mov     rcx, rsi; this
0x1800430c2  mov     rdx, r12; struct CSyncChangeWrapper *
0x1800430c5  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x1800430ca  mov     ebx, eax
0x1800430cc  test    eax, eax
0x1800430ce  js      loc_18004331B
0x1800430d4  mov     rax, [rsi]
0x1800430d7  mov     rcx, rsi
0x1800430da  mov     edx, [rbp+var_38]
0x1800430dd  mov     rax, [rax+40h]
0x1800430e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430e6  mov     ebx, eax
0x1800430e8  test    eax, eax
0x1800430ea  js      loc_18004331B
0x1800430f0  mov     edx, 2
0x1800430f5  mov     rcx, rsi
0x1800430f8  call    ?SetTransferFilters@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::SetTransferFilters(SYNC_TRANSFER_FILTER)
0x1800430fd  mov     ebx, eax
0x1800430ff  jmp     loc_18004331B
0x180043104  cmp     ecx, 4
0x180043107  jnz     short loc_180043125
0x180043109  cmp     [r15+288h], edi
0x180043110  jnz     short loc_18004311E
0x180043112  lea     edx, [rcx+1Ch]
0x180043115  cmp     [r15+28Ch], edi
0x18004311c  jg      short loc_1800430F5
0x18004311e  mov     edx, 10h
0x180043123  jmp     short loc_1800430F5
0x180043125  mov     edx, 20h ; ' '
0x18004312a  jmp     short loc_1800430F5
0x18004312c  xor     r9d, r9d; int
0x18004312f  xor     r8d, r8d; struct CSyncChangeWrapper *
0x180043132  mov     rdx, r12; struct CSyncChangeWrapper *
0x180043135  mov     rcx, rsi; this
0x180043138  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x18004313d  mov     ebx, eax
0x18004313f  test    eax, eax
0x180043141  js      loc_18004331B
0x180043147  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x18004314b  mov     [rbp+arg_18], rdi
0x18004314f  mov     rcx, rsi; this
0x180043152  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x180043157  mov     ebx, eax
0x180043159  test    eax, eax
0x18004315b  js      loc_18004331B
0x180043161  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x180043165  mov     [rbp+var_18], rdi
0x180043169  mov     rcx, r12; this
0x18004316c  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x180043171  mov     r14, [rbp+arg_18]
0x180043175  mov     ebx, eax
0x180043177  test    eax, eax
0x180043179  js      loc_180043313
0x18004317f  mov     rcx, [r15+80h]
0x180043186  lea     rdx, [rbp+var_28]
0x18004318a  mov     [rbp+var_28], rdi
0x18004318e  mov     [rbp+var_30], rdi
0x180043192  mov     [rbp+arg_18], rdi
0x180043196  mov     [rbp+var_20], rdi
0x18004319a  mov     rax, [rcx]
0x18004319d  mov     rax, [rax+38h]
0x1800431a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431a6  mov     ebx, eax
0x1800431a8  test    eax, eax
0x1800431aa  js      loc_1800432B7
0x1800431b0  mov     rcx, [r15+200h]
0x1800431b7  mov     rdx, [rbp+var_28]
0x1800431bb  mov     rax, [rcx]
0x1800431be  mov     rax, [rax+28h]
0x1800431c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431c7  mov     ebx, eax
0x1800431c9  test    eax, eax
0x1800431cb  js      loc_1800432B7
0x1800431d1  lea     rcx, [rsi+8]
0x1800431d5  mov     rax, [rcx]
0x1800431d8  lea     rdx, [rbp+var_30]
0x1800431dc  mov     rax, [rax+50h]
0x1800431e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431e5  mov     ebx, eax
0x1800431e7  test    eax, eax
0x1800431e9  js      loc_1800432B7
0x1800431ef  mov     rcx, [rbp+var_30]
0x1800431f3  lea     rdx, [rbp+arg_18]
0x1800431f7  mov     rax, [rcx]
0x1800431fa  mov     rax, [rax+50h]
0x1800431fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043203  mov     ebx, eax
0x180043205  test    eax, eax
0x180043207  js      loc_1800432B7
0x18004320d  mov     rcx, [r15+200h]
0x180043214  lea     r8, [rbp+var_20]
0x180043218  mov     rdx, r14
0x18004321b  mov     rax, [rcx]
0x18004321e  mov     rax, [rax+70h]
0x180043222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043227  mov     ebx, eax
  ... truncated ...
```
