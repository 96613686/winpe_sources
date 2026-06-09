# CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters(CSyncChangeWrapper *,ILoggedConflict *,CSyncChangeWrapper *)

- ea: `0x180043374`
- end: `0x18004380e`
- name: `?RaiseUpdateUpdateConflictAndSetTransferFilters@CChangeApplier@@AEAAJPEAVCSyncChangeWrapper@@PEAUILoggedConflict@@0@Z`
- size: `1178`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct CSyncChangeWrapper *, struct ILoggedConflict *, struct CSyncChangeWrapper *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x18003f34c`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180035724`
- `0x180041bb4`
- `0x180043374`
- `0x180066018`
- `0x180066680`
- `0x18006acc4`
- `0x18006cc00`
- `0x18006cd94`
- `0x18006e608`
- `0x18006ef64`
- `0x180071bc8`
- `0x180072974`
- `0x180094010`

## string_xrefs

- `0x1800433b7`: `CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters`
- `0x1800437df`: `CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters`

## pseudocode

```c
__int64 __fastcall CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters(
        struct IdParameters **this,
        struct CSyncChangeWrapper *a2,
        struct ILoggedConflict *a3,
        struct CSyncChangeWrapper *a4)
{
  PVOID *v8; // rcx
  int v9; // ebx
  CSyncChangeWrapper *v10; // rax
  CSyncChangeWrapper *v11; // rax
  struct CSyncChangeWrapper *v12; // rdi
  __int64 v13; // rax
  int v14; // ecx
  struct IdParameters *v15; // rcx
  struct CSyncChangeUnitWrapper *v16; // r14
  struct IdParameters *v17; // rdx
  CChangeConflict *v18; // rax
  CChangeConflict *v19; // r14
  int v20; // eax
  __int64 v21; // rdx
  struct IChangeConflict *v23; // [rsp+30h] [rbp-28h] BYREF
  struct ISyncChangeUnit *v24; // [rsp+38h] [rbp-20h] BYREF
  CSyncChangeUnitWrapper *v25[3]; // [rsp+40h] [rbp-18h] BYREF
  int v26; // [rsp+A8h] [rbp+50h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      149,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = -2147467261;
  if ( a2 && a3 && a4 )
  {
    v9 = -2147024882;
    v10 = (CSyncChangeWrapper *)SeAlloc(0x1F0u);
    if ( !v10 )
    {
      v26 = 0;
LABEL_61:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    v11 = CSyncChangeWrapper::CSyncChangeWrapper(v10, this[22]);
    v12 = v11;
    if ( v11 )
    {
      v9 = CSyncChangeWrapper::Init(v11, a3);
      if ( v9 >= 0 )
      {
        v13 = *(_QWORD *)a3;
        v23 = 0;
        if ( (*(unsigned int (__fastcall **)(struct ILoggedConflict *, struct IChangeConflict **))(v13 + 64))(a3, &v23) == -2147217393 )
        {
          v14 = 0;
          v26 = 0;
          goto LABEL_23;
        }
        v9 = ((__int64 (__fastcall *)(struct IChangeConflict *))v23->lpVtbl->GetDestinationProviderConflictingData)(v23);
        if ( v9 >= 0 )
        {
          v24 = 0;
          do
          {
            v9 = ((__int64 (__fastcall *)(struct IChangeConflict *, __int64, struct ISyncChangeUnit **))v23->lpVtbl->GetDestinationProviderConflictingChange)(
                   v23,
                   1,
                   &v24);
            if ( v9 )
              break;
            v15 = this[22];
            v25[0] = 0;
            v9 = CSyncChangeUnitWrapper_CreateInstance(v15, v24, v12, 0, v25);
            if ( v9 >= 0 )
            {
              v16 = v25[0];
              v9 = CSyncChangeUnitWrapper::SetConflict(v25[0]);
              if ( v9 >= 0 )
                v9 = CSyncChangeWrapper::AddChangeUnit(v12, v16);
              (*(void (__fastcall **)(struct CSyncChangeUnitWrapper *))(*(_QWORD *)v16 + 16LL))(v16);
            }
            ((void (__fastcall *)(struct ISyncChangeUnit *))v24->lpVtbl->Release)(v24);
          }
          while ( v9 >= 0 );
        }
        ((void (__fastcall *)(struct IChangeConflict *))v23->lpVtbl->Release)(v23);
      }
    }
    v14 = 0;
    v26 = 0;
    if ( v9 < 0 )
      goto LABEL_58;
LABEL_23:
    v17 = this[50];
    if ( v17 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct IdParameters *))(*(_QWORD *)v17 + 8LL))(v17);
      v9 = CSyncChangeWrapper::SetConflict(v12, a4, 0, 0);
      if ( v9 >= 0 )
      {
        v9 = (**(__int64 (__fastcall ***)(struct CSyncChangeWrapper *, GUID *, struct IChangeConflict **))v12)(
               v12,
               &GUID_014ebf97_9f20_4f7a_bdd4_25979c77c002,
               &v23);
        if ( v9 >= 0 )
        {
          v9 = -2147024882;
          v18 = (CChangeConflict *)SeAlloc(0x38u);
          if ( v18 )
          {
            v19 = CChangeConflict::CChangeConflict(v18, v23, (struct CChangeApplier *)this);
            if ( v19 )
            {
              v9 = CChangeApplier::ChangeState((__int64)this, 18);
              if ( v9 >= 0 )
              {
                v9 = CSyncChangeWrapper::SetConflictFilter(v12, 1, 1);
                if ( v9 >= 0 )
                {
                  v9 = CSyncChangeWrapper::SetConflictFilter(a4, 1, 1);
                  if ( v9 >= 0 )
                  {
                    v20 = (*(__int64 (__fastcall **)(struct IdParameters *, CChangeConflict *))(*(_QWORD *)this[50]
                                                                                              + 40LL))(
                            this[50],
                            v19);
                    v9 = v20;
                    if ( v20 == -2147217374 || v20 >= 0 )
                    {
                      v9 = CChangeApplier::ChangeState((__int64)this, 19);
                      if ( v9 >= 0 )
                      {
                        v9 = CSyncChangeWrapper::SetConflictFilter(v12, 0, 0);
                        if ( v9 >= 0 )
                        {
                          v9 = CSyncChangeWrapper::SetConflictFilter(a4, 0, 0);
                          if ( v9 >= 0 )
                            v9 = ((__int64 (__fastcall *)(struct IChangeConflict *, int *))v23->lpVtbl->GetResolveActionForChange)(
                                   v23,
                                   &v26);
                        }
                      }
                    }
                  }
                }
              }
              (*(void (__fastcall **)(CChangeConflict *))(*(_QWORD *)v19 + 16LL))(v19);
            }
          }
          ((void (__fastcall *)(struct IChangeConflict *))v23->lpVtbl->Release)(v23);
        }
      }
      (*(void (__fastcall **)(struct IdParameters *))(*(_QWORD *)this[50] + 16LL))(this[50]);
      if ( v9 < 0 )
        goto LABEL_58;
      v14 = v26;
    }
    if ( ((v14 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v14 != 2 )
      {
        if ( v14 == 4 )
        {
          if ( *((_DWORD *)this + 162) || (v21 = 32, *((int *)this + 163) <= 0) )
            v21 = 16;
        }
        else
        {
          v21 = 32;
        }
        goto LABEL_57;
      }
    }
    else if ( v14 != 2 )
    {
      a4 = v12;
    }
    v9 = CSyncChangeWrapper::SetConflict(a2, a4, 0, 0);
    if ( v9 < 0
      || (v25[0] = 0,
          v9 = CChangeApplier::MakeChangeIdChangeHelper((CChangeApplier *)this, a2, a3, 1, (unsigned __int64 *)v25),
          v9 < 0)
      || (v9 = (*(__int64 (__fastcall **)(struct IdParameters *, CSyncChangeUnitWrapper *))(*(_QWORD *)this[64] + 40LL))(
                 this[64],
                 v25[0]),
          v9 < 0) )
    {
LABEL_58:
      if ( v12 )
        (*(void (__fastcall **)(struct CSyncChangeWrapper *))(*(_QWORD *)v12 + 16LL))(v12);
      goto LABEL_61;
    }
    if ( v26 == 3 )
    {
      v21 = 4099;
    }
    else
    {
      v21 = 2051;
      if ( v26 != 2 )
        v21 = 8194;
    }
LABEL_57:
    v9 = CSyncChangeWrapper::SetTransferFilters(a2, v21);
    goto LABEL_58;
  }
LABEL_62:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      150,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::RaiseUpdateUpdateConflictAndSetTransferFilters",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180043374  push    rbp
0x180043376  push    rbx
0x180043377  push    rsi
0x180043378  push    rdi
0x180043379  push    r12
0x18004337b  push    r13
0x18004337d  push    r14
0x18004337f  push    r15
0x180043381  mov     rbp, rsp
0x180043384  sub     rsp, 58h
0x180043388  mov     r12, r9
0x18004338b  mov     r13, r8
0x18004338e  mov     r15, rdx
0x180043391  mov     rsi, rcx
0x180043394  mov     rcx, cs:WPP_GLOBAL_Control
0x18004339b  lea     rax, WPP_GLOBAL_Control
0x1800433a2  cmp     rcx, rax
0x1800433a5  jz      short loc_1800433D6
0x1800433a7  test    byte ptr [rcx+1Ch], 8
0x1800433ab  jz      short loc_1800433D6
0x1800433ad  cmp     byte ptr [rcx+19h], 5
0x1800433b1  jb      short loc_1800433D6
0x1800433b3  mov     rcx, [rcx+10h]
0x1800433b7  lea     r9, aCchangeapplier_121; "CChangeApplier::RaiseUpdateUpdateConfli"...
0x1800433be  mov     edx, 95h
0x1800433c3  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800433ca  call    WPP_SF_s
0x1800433cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433d6  mov     ebx, 80004003h
0x1800433db  test    r15, r15
0x1800433de  jz      loc_1800437C3
0x1800433e4  test    r13, r13
0x1800433e7  jz      loc_1800437C3
0x1800433ed  test    r12, r12
0x1800433f0  jz      loc_1800437C3
0x1800433f6  mov     ecx, 1F0h; unsigned __int64
0x1800433fb  mov     ebx, 8007000Eh
0x180043400  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180043405  test    rax, rax
0x180043408  jz      loc_1800437B5
0x18004340e  mov     rdx, [rsi+0B0h]; struct IdParameters *
0x180043415  mov     rcx, rax; this
0x180043418  call    ??0CSyncChangeWrapper@@QEAA@PEAVIdParameters@@@Z; CSyncChangeWrapper::CSyncChangeWrapper(IdParameters *)
0x18004341d  mov     rdi, rax
0x180043420  test    rax, rax
0x180043423  jz      loc_180043531
0x180043429  mov     rdx, r13; struct ILoggedConflict *
0x18004342c  mov     rcx, rax; this
0x18004342f  call    ?Init@CSyncChangeWrapper@@QEAAJPEAUILoggedConflict@@@Z; CSyncChangeWrapper::Init(ILoggedConflict *)
0x180043434  mov     ebx, eax
0x180043436  test    eax, eax
0x180043438  js      loc_180043531
0x18004343e  mov     rax, [r13+0]
0x180043442  lea     rdx, [rbp+var_28]
0x180043446  mov     rcx, r13
0x180043449  mov     [rbp+var_28], 0
0x180043451  mov     rax, [rax+40h]
0x180043455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004345a  cmp     eax, 8004100Fh
0x18004345f  jnz     short loc_18004346B
0x180043461  xor     ecx, ecx
0x180043463  mov     [rbp+arg_8], ecx
0x180043466  jmp     loc_18004353E
0x18004346b  mov     rcx, [rbp+var_28]
0x18004346f  mov     rax, [rcx]
0x180043472  mov     rax, [rax+28h]
0x180043476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004347b  mov     ebx, eax
0x18004347d  test    eax, eax
0x18004347f  js      loc_180043521
0x180043485  mov     [rbp+var_20], 0
0x18004348d  mov     rcx, [rbp+var_28]
0x180043491  lea     r8, [rbp+var_20]
0x180043495  xor     r9d, r9d
0x180043498  mov     rax, [rcx]
0x18004349b  lea     edx, [r9+1]
0x18004349f  mov     rax, [rax+18h]
0x1800434a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434a8  mov     ebx, eax
0x1800434aa  test    eax, eax
0x1800434ac  jnz     short loc_180043521
0x1800434ae  mov     rdx, [rbp+var_20]; struct ISyncChangeUnit *
0x1800434b2  lea     rax, [rbp+var_18]
0x1800434b6  mov     rcx, [rsi+0B0h]; struct IdParameters *
0x1800434bd  xor     r9d, r9d; int
0x1800434c0  mov     r8, rdi; struct CSyncChangeWrapper *
0x1800434c3  mov     [rsp+58h+var_38], rax; struct CSyncChangeUnitWrapper **
0x1800434c8  mov     [rbp+var_18], 0
0x1800434d0  call    ?CSyncChangeUnitWrapper_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncChangeUnit@@PEAVCSyncChangeWrapper@@HPEAPEAVCSyncChangeUnitWrapper@@@Z; CSyncChangeUnitWrapper_CreateInstance(IdParameters *,ISyncChangeUnit *,CSyncChangeWrapper *,int,CSyncChangeUnitWrapper * *)
0x1800434d5  mov     ebx, eax
0x1800434d7  test    eax, eax
0x1800434d9  js      short loc_180043509
0x1800434db  mov     r14, [rbp+var_18]
0x1800434df  mov     rcx, r14; this
0x1800434e2  call    ?SetConflict@CSyncChangeUnitWrapper@@QEAAJXZ; CSyncChangeUnitWrapper::SetConflict(void)
0x1800434e7  mov     ebx, eax
0x1800434e9  test    eax, eax
0x1800434eb  js      short loc_1800434FA
0x1800434ed  mov     rdx, r14; struct CSyncChangeUnitWrapper *
0x1800434f0  mov     rcx, rdi; this
0x1800434f3  call    ?AddChangeUnit@CSyncChangeWrapper@@QEAAJPEAVCSyncChangeUnitWrapper@@@Z; CSyncChangeWrapper::AddChangeUnit(CSyncChangeUnitWrapper *)
0x1800434f8  mov     ebx, eax
0x1800434fa  mov     rax, [r14]
0x1800434fd  mov     rcx, r14
0x180043500  mov     rax, [rax+10h]
0x180043504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043509  mov     rcx, [rbp+var_20]
0x18004350d  mov     rax, [rcx]
0x180043510  mov     rax, [rax+10h]
0x180043514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043519  test    ebx, ebx
0x18004351b  jns     loc_18004348D
0x180043521  mov     rcx, [rbp+var_28]
0x180043525  mov     rax, [rcx]
0x180043528  mov     rax, [rax+10h]
0x18004352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043531  xor     ecx, ecx
0x180043533  mov     [rbp+arg_8], ecx
0x180043536  test    ebx, ebx
0x180043538  js      loc_18004379F
0x18004353e  mov     rdx, [rsi+190h]
0x180043545  test    rdx, rdx
0x180043548  jz      loc_1800436D0
0x18004354e  mov     [rbp+var_28], 0
0x180043556  mov     rcx, rdx
0x180043559  mov     rax, [rdx]
0x18004355c  mov     rax, [rax+8]
0x180043560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043565  xor     r9d, r9d; int
0x180043568  xor     r8d, r8d; struct CSyncChangeWrapper *
0x18004356b  mov     rdx, r12; struct CSyncChangeWrapper *
0x18004356e  mov     rcx, rdi; this
0x180043571  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x180043576  mov     ebx, eax
0x180043578  test    eax, eax
0x18004357a  js      loc_1800436B2
0x180043580  mov     rax, [rdi]
0x180043583  lea     r8, [rbp+var_28]
0x180043587  lea     rdx, _GUID_014ebf97_9f20_4f7a_bdd4_25979c77c002
0x18004358e  mov     rcx, rdi
0x180043591  mov     rax, [rax]
0x180043594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043599  mov     ebx, eax
0x18004359b  test    eax, eax
0x18004359d  js      loc_1800436B2
0x1800435a3  mov     ecx, 38h ; '8'; unsigned __int64
0x1800435a8  mov     ebx, 8007000Eh
0x1800435ad  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800435b2  test    rax, rax
0x1800435b5  jz      loc_1800436A2
0x1800435bb  mov     rdx, [rbp+var_28]; struct IChangeConflict *
0x1800435bf  mov     r8, rsi; struct CChangeApplier *
0x1800435c2  mov     rcx, rax; this
0x1800435c5  call    ??0CChangeConflict@@QEAA@PEAUIChangeConflict@@PEAVCChangeApplier@@@Z; CChangeConflict::CChangeConflict(IChangeConflict *,CChangeApplier *)
0x1800435ca  mov     r14, rax
0x1800435cd  test    rax, rax
0x1800435d0  jz      loc_1800436A2
0x1800435d6  mov     edx, 12h
0x1800435db  mov     rcx, rsi
0x1800435de  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x1800435e3  mov     ebx, eax
0x1800435e5  test    eax, eax
0x1800435e7  js      loc_180043693
0x1800435ed  mov     eax, 1
0x1800435f2  mov     rcx, rdi; this
0x1800435f5  mov     r8d, eax; int
0x1800435f8  mov     edx, eax; int
0x1800435fa  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x1800435ff  mov     ebx, eax
0x180043601  test    eax, eax
0x180043603  js      loc_180043693
0x180043609  mov     eax, 1
0x18004360e  mov     rcx, r12; this
0x180043611  mov     r8d, eax; int
0x180043614  mov     edx, eax; int
0x180043616  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x18004361b  mov     ebx, eax
0x18004361d  test    eax, eax
0x18004361f  js      short loc_180043693
0x180043621  mov     rcx, [rsi+190h]
0x180043628  mov     rdx, r14
0x18004362b  mov     rax, [rcx]
0x18004362e  mov     rax, [rax+28h]
0x180043632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043637  mov     ebx, eax
0x180043639  cmp     eax, 80041022h
0x18004363e  jz      short loc_180043644
0x180043640  test    eax, eax
0x180043642  js      short loc_180043693
0x180043644  mov     edx, 13h
0x180043649  mov     rcx, rsi
0x18004364c  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x180043651  mov     ebx, eax
0x180043653  test    eax, eax
0x180043655  js      short loc_180043693
0x180043657  xor     r8d, r8d; int
0x18004365a  xor     edx, edx; int
0x18004365c  mov     rcx, rdi; this
0x18004365f  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x180043664  mov     ebx, eax
0x180043666  test    eax, eax
0x180043668  js      short loc_180043693
0x18004366a  xor     r8d, r8d; int
0x18004366d  xor     edx, edx; int
0x18004366f  mov     rcx, r12; this
0x180043672  call    ?SetConflictFilter@CSyncChangeWrapper@@QEAAJHH@Z; CSyncChangeWrapper::SetConflictFilter(int,int)
0x180043677  mov     ebx, eax
0x180043679  test    eax, eax
0x18004367b  js      short loc_180043693
0x18004367d  mov     rcx, [rbp+var_28]
0x180043681  lea     rdx, [rbp+arg_8]
0x180043685  mov     rax, [rcx]
0x180043688  mov     rax, [rax+38h]
0x18004368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043691  mov     ebx, eax
0x180043693  mov     rax, [r14]
0x180043696  mov     rcx, r14
0x180043699  mov     rax, [rax+10h]
0x18004369d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436a2  mov     rcx, [rbp+var_28]
0x1800436a6  mov     rax, [rcx]
0x1800436a9  mov     rax, [rax+10h]
0x1800436ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b2  mov     rcx, [rsi+190h]
0x1800436b9  mov     rax, [rcx]
0x1800436bc  mov     rax, [rax+10h]
0x1800436c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436c5  test    ebx, ebx
0x1800436c7  js      loc_18004379F
0x1800436cd  mov     ecx, [rbp+arg_8]
0x1800436d0  lea     eax, [rcx-1]
0x1800436d3  test    eax, 0FFFFFFFDh
0x1800436d8  jz      short loc_180043711
0x1800436da  cmp     ecx, 2
0x1800436dd  jz      short loc_180043719
0x1800436df  cmp     ecx, 4
0x1800436e2  jnz     short loc_180043707
0x1800436e4  cmp     dword ptr [rsi+288h], 0
0x1800436eb  jnz     short loc_1800436FD
0x1800436ed  cmp     dword ptr [rsi+28Ch], 0
0x1800436f4  lea     edx, [rcx+1Ch]
0x1800436f7  jg      loc_180043795
0x1800436fd  mov     edx, 10h
0x180043702  jmp     loc_180043795
0x180043707  mov     edx, 20h ; ' '
0x18004370c  jmp     loc_180043795
0x180043711  cmp     ecx, 2
0x180043714  jz      short loc_180043719
0x180043716  mov     r12, rdi
0x180043719  xor     r9d, r9d; int
0x18004371c  xor     r8d, r8d; struct CSyncChangeWrapper *
0x18004371f  mov     rdx, r12; struct CSyncChangeWrapper *
0x180043722  mov     rcx, r15; this
0x180043725  call    ?SetConflict@CSyncChangeWrapper@@QEAAJPEAV1@0H@Z; CSyncChangeWrapper::SetConflict(CSyncChangeWrapper *,CSyncChangeWrapper *,int)
0x18004372a  mov     ebx, eax
0x18004372c  test    eax, eax
0x18004372e  js      short loc_18004379F
0x180043730  lea     rax, [rbp+var_18]
0x180043734  mov     [rbp+var_18], 0
0x18004373c  mov     r9d, 1; int
0x180043742  mov     [rsp+58h+var_38], rax; unsigned __int64 *
0x180043747  mov     r8, r13; struct ILoggedConflict *
0x18004374a  mov     rdx, r15; struct CSyncChangeWrapper *
0x18004374d  mov     rcx, rsi; this
0x180043750  call    ?MakeChangeIdChangeHelper@CChangeApplier@@AEAAJPEAVCSyncChangeWrapper@@PEAUILoggedConflict@@HPEA_K@Z; CChangeApplier::MakeChangeIdChangeHelper(CSyncChangeWrapper *,ILoggedConflict *,int,unsigned __int64 *)
0x180043755  mov     ebx, eax
0x180043757  test    eax, eax
0x180043759  js      short loc_18004379F
0x18004375b  mov     rcx, [rsi+200h]
0x180043762  mov     rdx, [rbp+var_18]
0x180043766  mov     rax, [rcx]
0x180043769  mov     rax, [rax+28h]
0x18004376d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043772  mov     ebx, eax
0x180043774  test    eax, eax
0x180043776  js      short loc_18004379F
0x180043778  cmp     [rbp+arg_8], 3
0x18004377c  jnz     short loc_180043785
0x18004377e  mov     edx, 1003h
0x180043783  jmp     short loc_180043795
0x180043785  cmp     [rbp+arg_8], 2
0x180043789  mov     edx, 803h
0x18004378e  jz      short loc_180043795
0x180043790  mov     edx, 2002h
0x180043795  mov     rcx, r15
0x180043798  call    ?SetTransferFilters@CSyncChangeWrapper@@QEAAJW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::SetTransferFilters(SYNC_TRANSFER_FILTER)
0x18004379d  mov     ebx, eax
0x18004379f  test    rdi, rdi
0x1800437a2  jz      short loc_1800437BC
0x1800437a4  mov     rax, [rdi]
0x1800437a7  mov     rcx, rdi
0x1800437aa  mov     rax, [rax+10h]
0x1800437ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437b3  jmp     short loc_1800437BC
0x1800437b5  mov     [rbp+arg_8], 0
0x1800437bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437c3  lea     rax, WPP_GLOBAL_Control
0x1800437ca  cmp     rcx, rax
0x1800437cd  jz      short loc_1800437FB
0x1800437cf  test    byte ptr [rcx+1Ch], 8
  ... truncated ...
```
