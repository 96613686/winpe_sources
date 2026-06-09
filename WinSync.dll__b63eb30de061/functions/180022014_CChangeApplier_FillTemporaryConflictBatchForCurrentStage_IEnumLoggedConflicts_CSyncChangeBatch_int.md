# CChangeApplier::FillTemporaryConflictBatchForCurrentStage(IEnumLoggedConflicts *,CSyncChangeBatch *,int *)

- ea: `0x180022014`
- end: `0x18002248a`
- name: `?FillTemporaryConflictBatchForCurrentStage@CChangeApplier@@AEAAJPEAUIEnumLoggedConflicts@@PEAVCSyncChangeBatch@@PEAH@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct IEnumLoggedConflicts *, struct CSyncChangeBatch *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180021cbc`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180022014`
- `0x18002dc04`
- `0x18002dc5c`
- `0x180032678`
- `0x180036264`
- `0x18003baa8`
- `0x18004059c`
- `0x18004cb40`
- `0x18005c7a8`
- `0x18005ca38`
- `0x180094010`

## string_xrefs

- `0x180022064`: `CChangeApplier::FillTemporaryConflictBatchForCurrentStage`
- `0x180022404`: `CChangeApplier::FillTemporaryConflictBatchForCurrentStage`

## pseudocode

```c
__int64 __fastcall CChangeApplier::FillTemporaryConflictBatchForCurrentStage(
        CChangeApplier *this,
        struct IEnumLoggedConflicts *a2,
        struct CSyncChangeBatch *a3,
        int *a4)
{
  CSyncChangeBatch *v5; // rax
  PVOID *v8; // rcx
  int v9; // ebx
  int v10; // eax
  struct ISyncKnowledge *v11; // r14
  int DestinationKnowledgeWithTemporaryConflicts; // eax
  CSyncEnumLoggedConflictsBuilder *v13; // rax
  CSyncEnumLoggedConflictsBuilder *v14; // rax
  CSyncEnumLoggedConflictsBuilder *v15; // rdi
  int v16; // eax
  int v17; // r15d
  IdParameterPair *v18; // rcx
  int Id; // eax
  unsigned __int8 *v20; // r12
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  struct ISyncChange *v25; // r15
  __int64 v26; // rax
  int v28; // [rsp+30h] [rbp-30h]
  int v29; // [rsp+34h] [rbp-2Ch] BYREF
  int v30; // [rsp+38h] [rbp-28h] BYREF
  struct ILoggedConflict *v31; // [rsp+40h] [rbp-20h] BYREF
  struct ISyncChange *v32; // [rsp+48h] [rbp-18h] BYREF
  struct ISyncKnowledge *v33; // [rsp+50h] [rbp-10h] BYREF
  struct ISyncKnowledge *v34; // [rsp+A8h] [rbp+48h] BYREF
  CSyncChangeBatch *v35; // [rsp+B0h] [rbp+50h]
  int *v36; // [rsp+B8h] [rbp+58h]

  v36 = a4;
  v35 = a3;
  v5 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      168,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::FillTemporaryConflictBatchForCurrentStage");
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v35;
  }
  v9 = -2147467261;
  if ( !a2 || !v5 || !a4 )
    goto LABEL_49;
  v10 = *((_DWORD *)this + 162);
  v34 = 0;
  v11 = 0;
  if ( v10 == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 8LL))(*((_QWORD *)this + 64));
    v11 = (struct ISyncKnowledge *)*((_QWORD *)this + 64);
  }
  else if ( v10 == 2 )
  {
    DestinationKnowledgeWithTemporaryConflicts = CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts(
                                                   this,
                                                   a2,
                                                   &v34);
    v11 = v34;
    v9 = DestinationKnowledgeWithTemporaryConflicts;
    if ( DestinationKnowledgeWithTemporaryConflicts < 0 )
      goto LABEL_46;
  }
  v9 = -2147024882;
  v13 = (CSyncEnumLoggedConflictsBuilder *)SeAlloc(0x18u);
  if ( !v13 )
    goto LABEL_46;
  v14 = CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(v13);
  v15 = v14;
  if ( !v14 )
    goto LABEL_46;
  v9 = CSyncEnumLoggedConflictsBuilder::Init(v14);
  if ( v9 < 0 )
    goto LABEL_45;
  v28 = 0;
  v16 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *))(*(_QWORD *)a2 + 40LL))(a2);
  v31 = 0;
  v9 = v16;
  v30 = 0;
  if ( v16 < 0 )
    goto LABEL_45;
  do
  {
    v17 = 1;
    v9 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *, __int64, struct ILoggedConflict **, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           1,
           &v31,
           &v30);
    if ( v9 )
      break;
    v18 = (IdParameterPair *)(*((_QWORD *)this + 22) + 16LL);
    v32 = 0;
    LODWORD(v34) = 0;
    v29 = 1;
    Id = IdParameterPair::AllocateId(v18, (unsigned __int8 **)&v32, (unsigned int *)&v34);
    v20 = (unsigned __int8 *)v32;
    v9 = Id;
    if ( Id == 1 )
    {
      v21 = (*(__int64 (__fastcall **)(struct ILoggedConflict *, struct ISyncChange *, struct ISyncKnowledge **))(*(_QWORD *)v31 + 48LL))(
              v31,
              v32,
              &v34);
      v9 = v21;
      if ( v21 == -2147024662 )
      {
        v22 = IdParameterPair::AllocateId(
                (IdParameterPair *)(*((_QWORD *)this + 22) + 16LL),
                (unsigned __int8 **)&v32,
                (unsigned __int16)v34);
        v20 = (unsigned __int8 *)v32;
        v9 = v22;
      }
      else if ( !v21 )
      {
        v9 = -2147217379;
        goto LABEL_39;
      }
    }
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct ILoggedConflict *, unsigned __int8 *, struct ISyncKnowledge **))(*(_QWORD *)v31 + 48LL))(
             v31,
             v20,
             &v34);
      if ( v9 >= 0 )
      {
        v33 = 0;
        if ( !(*(unsigned int (__fastcall **)(struct ILoggedConflict *))(*(_QWORD *)v31 + 120LL))(v31) )
        {
          switch ( *((_DWORD *)this + 162) )
          {
            case 1:
            case 2:
              v9 = (*(__int64 (__fastcall **)(struct ILoggedConflict *, struct ISyncKnowledge **))(*(_QWORD *)v31 + 104LL))(
                     v31,
                     &v33);
              if ( v9 >= 0 )
              {
                v9 = CChangeApplier::IsChangeFromTheSourcePending(this, v33, v11, 0, v20, 0);
                if ( !v9 )
                {
                  v17 = 0;
                  goto LABEL_32;
                }
                goto LABEL_31;
              }
              break;
            case 3:
              v23 = CChangeApplier::CheckForPermanentLoggedConflictDependency(this, v31, &v29);
              v17 = v29;
              v9 = v23;
LABEL_31:
              if ( v9 >= 0 )
                goto LABEL_32;
              break;
            case 4:
LABEL_32:
              if ( v17 )
              {
                v32 = 0;
                v9 = CSyncChangeBatch::AddLoggedConflict(v35, v31, &v32);
                if ( v9 >= 0 )
                {
                  v24 = HashTable<ISyncChange *,ILoggedConflict *,DefaultHashTableContext>::AddItem(
                          *((_QWORD *)this + 84),
                          &v32,
                          &v31);
                  v25 = v32;
                  v9 = v24;
                  if ( v24 >= 0 )
                  {
                    ((void (__fastcall *)(struct ISyncChange *))v32->lpVtbl->AddRef)(v32);
                    (*(void (__fastcall **)(struct ILoggedConflict *))(*(_QWORD *)v31 + 8LL))(v31);
                    v9 = (*(__int64 (__fastcall **)(CSyncEnumLoggedConflictsBuilder *, struct ILoggedConflict *))(*(_QWORD *)v15 + 24LL))(
                           v15,
                           v31);
                  }
                  ((void (__fastcall *)(struct ISyncChange *))v25->lpVtbl->Release)(v25);
                  ++v28;
                }
              }
              break;
            default:
              v9 = -2147217379;
              break;
          }
          if ( v33 )
            ((void (__fastcall *)(struct ISyncKnowledge *))v33->lpVtbl->Release)(v33);
        }
      }
    }
LABEL_39:
    IdParameters::FreeId(v20);
    (*(void (__fastcall **)(struct ILoggedConflict *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  while ( v9 >= 0 );
  if ( v9 >= 0 )
  {
    if ( v28 <= 0
      || (v26 = *(_QWORD *)v15,
          v34 = 0,
          v9 = (*(__int64 (__fastcall **)(CSyncEnumLoggedConflictsBuilder *, struct ISyncKnowledge **))(v26 + 32))(
                 v15,
                 &v34),
          v9 >= 0)
      && (v9 = (*(__int64 (__fastcall **)(_QWORD, struct ISyncKnowledge *))(**((_QWORD **)this + 79) + 24LL))(
                 *((_QWORD *)this + 79),
                 v34),
          ((void (__fastcall *)(struct ISyncKnowledge *))v34->lpVtbl->Release)(v34),
          v9 >= 0) )
    {
      *v36 = v28;
    }
  }
LABEL_45:
  (*(void (__fastcall **)(CSyncEnumLoggedConflictsBuilder *))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_46:
  if ( v11 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v11->lpVtbl->Release)(v11);
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      169,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::FillTemporaryConflictBatchForCurrentStage",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022014  mov     [rsp-38h+arg_0], rbx
0x180022019  mov     [rsp-38h+arg_18], r9
0x18002201e  mov     [rsp-38h+arg_10], r8
0x180022023  push    rbp
0x180022024  push    rsi
0x180022025  push    rdi
0x180022026  push    r12
0x180022028  push    r13
0x18002202a  push    r14
0x18002202c  push    r15
0x18002202e  mov     rbp, rsp
0x180022031  sub     rsp, 60h
0x180022035  mov     r12, r9
0x180022038  mov     rax, r8
0x18002203b  mov     r13, rdx
0x18002203e  mov     rsi, rcx
0x180022041  mov     rcx, cs:WPP_GLOBAL_Control
0x180022048  lea     rdi, WPP_GLOBAL_Control
0x18002204f  cmp     rcx, rdi
0x180022052  jz      short loc_180022087
0x180022054  test    byte ptr [rcx+1Ch], 8
0x180022058  jz      short loc_180022087
0x18002205a  cmp     byte ptr [rcx+19h], 5
0x18002205e  jb      short loc_180022087
0x180022060  mov     rcx, [rcx+10h]
0x180022064  lea     r9, aCchangeapplier_4; "CChangeApplier::FillTemporaryConflictBa"...
0x18002206b  mov     edx, 0A8h
0x180022070  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180022077  call    WPP_SF_s
0x18002207c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022083  mov     rax, [rbp+arg_10]
0x180022087  mov     ebx, 80004003h
0x18002208c  test    r13, r13
0x18002208f  jz      loc_1800223EF
0x180022095  test    rax, rax
0x180022098  jz      loc_1800223EF
0x18002209e  test    r12, r12
0x1800220a1  jz      loc_1800223EF
0x1800220a7  mov     eax, [rsi+288h]
0x1800220ad  xor     r12d, r12d
0x1800220b0  mov     [rbp+arg_8], r12
0x1800220b4  mov     r14d, r12d
0x1800220b7  cmp     eax, 1
0x1800220ba  jnz     short loc_1800220D8
0x1800220bc  mov     rcx, [rsi+200h]
0x1800220c3  mov     rax, [rcx]
0x1800220c6  mov     rax, [rax+8]
0x1800220ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cf  mov     r14, [rsi+200h]
0x1800220d6  jmp     short loc_1800220FA
0x1800220d8  cmp     eax, 2
0x1800220db  jnz     short loc_1800220FA
0x1800220dd  lea     r8, [rbp+arg_8]; struct ISyncKnowledge **
0x1800220e1  mov     rdx, r13; struct IEnumLoggedConflicts *
0x1800220e4  mov     rcx, rsi; this
0x1800220e7  call    ?GetDestinationKnowledgeWithTemporaryConflicts@CChangeApplier@@AEAAJPEAUIEnumLoggedConflicts@@PEAPEAUISyncKnowledge@@@Z; CChangeApplier::GetDestinationKnowledgeWithTemporaryConflicts(IEnumLoggedConflicts *,ISyncKnowledge * *)
0x1800220ec  mov     r14, [rbp+arg_8]
0x1800220f0  mov     ebx, eax
0x1800220f2  test    eax, eax
0x1800220f4  js      loc_1800223D4
0x1800220fa  mov     ecx, 18h; unsigned __int64
0x1800220ff  mov     ebx, 8007000Eh
0x180022104  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180022109  test    rax, rax
0x18002210c  jz      loc_1800223D4
0x180022112  mov     rcx, rax; this
0x180022115  call    ??0CSyncEnumLoggedConflictsBuilder@@QEAA@XZ; CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(void)
0x18002211a  mov     rdi, rax
0x18002211d  test    rax, rax
0x180022120  jz      loc_1800223CD
0x180022126  mov     rcx, rax; this
0x180022129  call    ?Init@CSyncEnumLoggedConflictsBuilder@@QEAAJXZ; CSyncEnumLoggedConflictsBuilder::Init(void)
0x18002212e  mov     ebx, eax
0x180022130  test    eax, eax
0x180022132  js      loc_1800223BE
0x180022138  mov     rax, [r13+0]
0x18002213c  mov     rcx, r13
0x18002213f  mov     [rbp+var_30], r12d
0x180022143  mov     rax, [rax+28h]
0x180022147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002214c  mov     [rbp+var_20], r12
0x180022150  mov     ebx, eax
0x180022152  mov     [rbp+var_28], r12d
0x180022156  test    eax, eax
0x180022158  js      loc_1800223BE
0x18002215e  mov     rax, [r13+0]
0x180022162  lea     r9, [rbp+var_28]
0x180022166  mov     r15d, 1
0x18002216c  lea     r8, [rbp+var_20]
0x180022170  mov     edx, r15d
0x180022173  mov     rcx, r13
0x180022176  mov     rax, [rax+18h]
0x18002217a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002217f  mov     ebx, eax
0x180022181  test    eax, eax
0x180022183  jnz     loc_180022360
0x180022189  mov     rcx, [rsi+0B0h]
0x180022190  lea     r8, [rbp+arg_8]; unsigned int *
0x180022194  add     rcx, 10h; this
0x180022198  mov     [rbp+var_18], r12
0x18002219c  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x1800221a0  mov     dword ptr [rbp+arg_8], r12d
0x1800221a4  mov     [rbp+var_2C], r15d
0x1800221a8  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEPEAK@Z; IdParameterPair::AllocateId(uchar * *,ulong *)
0x1800221ad  mov     r12, [rbp+var_18]
0x1800221b1  mov     ebx, eax
0x1800221b3  cmp     eax, r15d
0x1800221b6  jnz     short loc_1800221FB
0x1800221b8  mov     rcx, [rbp+var_20]
0x1800221bc  lea     r8, [rbp+arg_8]
0x1800221c0  mov     rdx, r12
0x1800221c3  mov     rax, [rcx]
0x1800221c6  mov     rax, [rax+30h]
0x1800221ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221cf  mov     ebx, eax
0x1800221d1  cmp     eax, 800700EAh
0x1800221d6  jnz     loc_180022270
0x1800221dc  mov     rcx, [rsi+0B0h]
0x1800221e3  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x1800221e7  movzx   r8d, word ptr [rbp+arg_8]; unsigned __int16
0x1800221ec  add     rcx, 10h; this
0x1800221f0  call    ?AllocateId@IdParameterPair@@QEAAJPEAPEAEG@Z; IdParameterPair::AllocateId(uchar * *,ushort)
0x1800221f5  mov     r12, [rbp+var_18]
0x1800221f9  mov     ebx, eax
0x1800221fb  test    ebx, ebx
0x1800221fd  js      loc_18002233D
0x180022203  mov     rcx, [rbp+var_20]
0x180022207  lea     r8, [rbp+arg_8]
0x18002220b  mov     rdx, r12
0x18002220e  mov     rax, [rcx]
0x180022211  mov     rax, [rax+30h]
0x180022215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002221a  mov     ebx, eax
0x18002221c  test    eax, eax
0x18002221e  js      loc_18002233D
0x180022224  mov     rcx, [rbp+var_20]
0x180022228  mov     [rbp+var_10], 0
0x180022230  mov     rax, [rcx]
0x180022233  mov     rax, [rax+78h]
0x180022237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002223c  test    eax, eax
0x18002223e  jnz     loc_18002233D
0x180022244  mov     ecx, [rsi+288h]
0x18002224a  sub     ecx, r15d
0x18002224d  jz      loc_18002243A
0x180022253  sub     ecx, r15d
0x180022256  jz      loc_18002243A
0x18002225c  sub     ecx, r15d
0x18002225f  jz      short loc_18002227E
0x180022261  cmp     ecx, r15d
0x180022264  jz      short loc_18002229C
0x180022266  mov     ebx, 8004101Dh
0x18002226b  jmp     loc_180022328
0x180022270  test    eax, eax
0x180022272  jnz     short loc_1800221FB
0x180022274  mov     ebx, 8004101Dh
0x180022279  jmp     loc_18002233D
0x18002227e  mov     rdx, [rbp+var_20]; struct ILoggedConflict *
0x180022282  lea     r8, [rbp+var_2C]; int *
0x180022286  mov     rcx, rsi; this
0x180022289  call    ?CheckForPermanentLoggedConflictDependency@CChangeApplier@@AEAAJPEAUILoggedConflict@@PEAH@Z; CChangeApplier::CheckForPermanentLoggedConflictDependency(ILoggedConflict *,int *)
0x18002228e  mov     r15d, [rbp+var_2C]
0x180022292  mov     ebx, eax
0x180022294  test    ebx, ebx
0x180022296  js      loc_180022328
0x18002229c  test    r15d, r15d
0x18002229f  jz      loc_180022328
0x1800222a5  mov     rdx, [rbp+var_20]; struct ILoggedConflict *
0x1800222a9  lea     r8, [rbp+var_18]; struct ISyncChange **
0x1800222ad  mov     rcx, [rbp+arg_10]; this
0x1800222b1  mov     [rbp+var_18], 0
0x1800222b9  call    ?AddLoggedConflict@CSyncChangeBatch@@QEAAJPEAUILoggedConflict@@PEAPEAUISyncChange@@@Z; CSyncChangeBatch::AddLoggedConflict(ILoggedConflict *,ISyncChange * *)
0x1800222be  mov     ebx, eax
0x1800222c0  test    eax, eax
0x1800222c2  js      short loc_180022328
0x1800222c4  mov     rcx, [rsi+2A0h]
0x1800222cb  lea     r8, [rbp+var_20]
0x1800222cf  lea     rdx, [rbp+var_18]
0x1800222d3  call    ?AddItem@?$HashTable@PEAUISyncChange@@PEAUILoggedConflict@@VDefaultHashTableContext@@@@QEAAJAEBQEAUISyncChange@@AEBQEAUILoggedConflict@@@Z; HashTable<ISyncChange *,ILoggedConflict *,DefaultHashTableContext>::AddItem(ISyncChange * const &,ILoggedConflict * const &)
0x1800222d8  mov     r15, [rbp+var_18]
0x1800222dc  mov     ebx, eax
0x1800222de  test    eax, eax
0x1800222e0  js      short loc_180022316
0x1800222e2  mov     rax, [r15]
0x1800222e5  mov     rcx, r15
0x1800222e8  mov     rax, [rax+8]
0x1800222ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f1  mov     rcx, [rbp+var_20]
0x1800222f5  mov     rax, [rcx]
0x1800222f8  mov     rax, [rax+8]
0x1800222fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022301  mov     rax, [rdi]
0x180022304  mov     rcx, rdi
0x180022307  mov     rdx, [rbp+var_20]
0x18002230b  mov     rax, [rax+18h]
0x18002230f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022314  mov     ebx, eax
0x180022316  mov     rax, [r15]
0x180022319  mov     rcx, r15
0x18002231c  mov     rax, [rax+10h]
0x180022320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022325  inc     [rbp+var_30]
0x180022328  mov     rcx, [rbp+var_10]
0x18002232c  test    rcx, rcx
0x18002232f  jz      short loc_18002233D
0x180022331  mov     rax, [rcx]
0x180022334  mov     rax, [rax+10h]
0x180022338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002233d  mov     rcx, r12; unsigned __int8 *
0x180022340  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180022345  mov     rcx, [rbp+var_20]
0x180022349  mov     rax, [rcx]
0x18002234c  mov     rax, [rax+10h]
0x180022350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022355  xor     r12d, r12d
0x180022358  test    ebx, ebx
0x18002235a  jns     loc_18002215E
0x180022360  test    ebx, ebx
0x180022362  js      short loc_1800223BE
0x180022364  mov     r15d, [rbp+var_30]
0x180022368  test    r15d, r15d
0x18002236b  jle     short loc_1800223B7
0x18002236d  mov     rax, [rdi]
0x180022370  lea     rdx, [rbp+arg_8]
0x180022374  mov     rcx, rdi
0x180022377  mov     [rbp+arg_8], r12
0x18002237b  mov     rax, [rax+20h]
0x18002237f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022384  mov     ebx, eax
0x180022386  test    eax, eax
0x180022388  js      short loc_1800223BE
0x18002238a  mov     rcx, [rsi+278h]
0x180022391  mov     rdx, [rbp+arg_8]
0x180022395  mov     rax, [rcx]
0x180022398  mov     rax, [rax+18h]
0x18002239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a1  mov     rcx, [rbp+arg_8]
0x1800223a5  mov     ebx, eax
0x1800223a7  mov     rax, [rcx]
0x1800223aa  mov     rax, [rax+10h]
0x1800223ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223b3  test    ebx, ebx
0x1800223b5  js      short loc_1800223BE
0x1800223b7  mov     rax, [rbp+arg_18]
0x1800223bb  mov     [rax], r15d
0x1800223be  mov     rax, [rdi]
0x1800223c1  mov     rcx, rdi
0x1800223c4  mov     rax, [rax+10h]
0x1800223c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223cd  lea     rdi, WPP_GLOBAL_Control
0x1800223d4  test    r14, r14
0x1800223d7  jz      short loc_1800223E8
0x1800223d9  mov     rax, [r14]
0x1800223dc  mov     rcx, r14
0x1800223df  mov     rax, [rax+10h]
0x1800223e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223ef  cmp     rcx, rdi
0x1800223f2  jz      short loc_180022420
0x1800223f4  test    byte ptr [rcx+1Ch], 8
0x1800223f8  jz      short loc_180022420
0x1800223fa  cmp     byte ptr [rcx+19h], 5
0x1800223fe  jb      short loc_180022420
0x180022400  mov     rcx, [rcx+10h]
0x180022404  lea     r9, aCchangeapplier_4; "CChangeApplier::FillTemporaryConflictBa"...
0x18002240b  mov     edx, 0A9h
0x180022410  mov     dword ptr [rsp+60h+var_40], ebx
0x180022414  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18002241b  call    WPP_SF_sD
0x180022420  mov     eax, ebx
0x180022422  mov     rbx, [rsp+60h+arg_0]
0x18002242a  add     rsp, 60h
0x18002242e  pop     r15
0x180022430  pop     r14
0x180022432  pop     r13
0x180022434  pop     r12
0x180022436  pop     rdi
0x180022437  pop     rsi
0x180022438  pop     rbp
0x180022439  retn
0x18002243a  mov     rcx, [rbp+var_20]
0x18002243e  lea     rdx, [rbp+var_10]
0x180022442  mov     rax, [rcx]
0x180022445  mov     rax, [rax+68h]
0x180022449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002244e  mov     ebx, eax
0x180022450  test    eax, eax
0x180022452  js      loc_180022328
0x180022458  mov     rdx, [rbp+var_10]; struct ISyncKnowledge *
0x18002245c  xor     r9d, r9d; unsigned __int8 *
0x18002245f  mov     [rsp+60h+var_38], 0; struct _SYNC_VERSION *
0x180022468  mov     r8, r14; struct ISyncKnowledge *
0x18002246b  mov     rcx, rsi; this
0x18002246e  mov     [rsp+60h+var_40], r12; unsigned __int8 *
0x180022473  call    ?IsChangeFromTheSourcePending@CChangeApplier@@AEAAJPEAUISyncKnowledge@@0PEAE1PEAU_SYNC_VERSION@@@Z; CChangeApplier::IsChangeFromTheSourcePending(ISyncKnowledge *,ISyncKnowledge *,uchar *,uchar *,_SYNC_VERSION *)
0x180022478  mov     ebx, eax
0x18002247a  test    eax, eax
0x18002247c  jnz     loc_180022294
0x180022482  xor     r15d, r15d
0x180022485  jmp     loc_18002229C
  ... truncated ...
```
