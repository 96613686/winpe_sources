# CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(LK_AFTER_RECOVERY_TYPE,ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)

- ea: `0x18005022c`
- end: `0x180050625`
- name: `?GetBatchLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@AEAAJW4LK_AFTER_RECOVERY_TYPE@@PEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU3@@Z`
- size: `1017`
- prototype: `__int64 __fastcall(__int64, int, struct ISyncKnowledge *, __int64, unsigned int, struct ISyncKnowledge **)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180050f60`
- `0x180051360`
- `0x1800517b0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002e58c`
- `0x18002ebe8`
- `0x18004e2e4`
- `0x18005022c`
- `0x180052630`
- `0x180059134`
- `0x180078bb8`
- `0x180078fa8`
- `0x180079388`
- `0x180094010`

## string_xrefs

- `0x180050279`: `CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete`
- `0x1800505ef`: `CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(
        __int64 a1,
        int a2,
        struct ISyncKnowledge *a3,
        __int64 a4,
        unsigned int a5,
        struct ISyncKnowledge **a6)
{
  struct ISyncKnowledge *v6; // r10
  PVOID *v9; // rcx
  int v10; // ebx
  ChangeGroup *v11; // rcx
  int FFKComplementedByDKUnionedWithFK; // eax
  struct IForgottenKnowledge *v13; // r8
  __int64 v14; // rax
  struct IdParameters **v15; // r15
  unsigned __int8 *v16; // rsi
  struct ISyncKnowledge *v17; // r12
  __int64 v18; // r14
  const unsigned __int8 **v19; // rax
  int RootItemIdInternal; // eax
  const unsigned __int8 *v21; // r8
  IdParameterPair *v22; // rcx
  int v23; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  unsigned __int8 *v26; // rcx
  int v27; // eax
  IdParameterPair *v28; // rcx
  int v29; // eax
  const unsigned __int8 *v30; // r14
  unsigned __int8 *v31; // rcx
  int v32; // eax
  struct ISyncKnowledge *v33; // rcx
  struct ISyncFilterInfo *v34; // r8
  IdParameterPair *v35; // rcx
  struct ISyncKnowledge *v37; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int8 *v38; // [rsp+38h] [rbp-28h] BYREF
  struct ISyncKnowledge *v39; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int8 **v40; // [rsp+48h] [rbp-18h]
  struct ISyncKnowledge *v41[2]; // [rsp+50h] [rbp-10h] BYREF

  v6 = a3;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete");
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v6 = a3;
  }
  v39 = 0;
  if ( a6 )
  {
    v11 = **(ChangeGroup ***)(a1 + 104);
    if ( a2 )
    {
      v13 = *(struct IForgottenKnowledge **)(a1 + 136);
      if ( a2 == 1 )
        FFKComplementedByDKUnionedWithFK = ChangeGroup::GetFFKComplementedByDKUnionedWithFK(v11, v6, v13, a5, &v39);
      else
        FFKComplementedByDKUnionedWithFK = ChangeGroup::GetMWKComplementedByDKUnionedWithFK(v11, v6, v13, &v39);
    }
    else
    {
      FFKComplementedByDKUnionedWithFK = ChangeGroup::GetMadeWithKnowledge(v11, &v39);
    }
    v10 = FFKComplementedByDKUnionedWithFK;
    if ( !v39 )
    {
LABEL_48:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_49;
    }
    v14 = *(_QWORD *)(a1 + 88);
    v15 = (struct IdParameters **)(a1 + 72);
    v16 = 0;
    v38 = 0;
    v17 = 0;
    v41[0] = 0;
    v37 = 0;
    v18 = *(_QWORD *)(v14 + 16);
    v19 = (const unsigned __int8 **)(a1 + 248);
    while ( 1 )
    {
      v40 = v19;
      if ( !v18 )
        break;
      RootItemIdInternal = CSyncChange::GetRootItemIdInternal(*(CSyncChange **)v18, &v38);
      v16 = v38;
      v10 = RootItemIdInternal;
      if ( RootItemIdInternal < 0 )
        goto LABEL_44;
      v21 = *(const unsigned __int8 **)(a1 + 248);
      v15 = (struct IdParameters **)(a1 + 72);
      v22 = (IdParameterPair *)(*(_QWORD *)(a1 + 72) + 16LL);
      v40 = (const unsigned __int8 **)(a1 + 248);
      if ( (int)IdParameterPair::CompareId(v22, v38, v21) >= 0 )
        break;
      v38 = 0;
      if ( a2 )
      {
        v24 = (__int64 *)(*(_QWORD *)v18 + 40LL);
        v25 = *v24;
        if ( a2 == 1 )
          v23 = (*(__int64 (__fastcall **)(__int64 *, struct ISyncKnowledge *, __int64, _QWORD, unsigned __int8 **))(v25 + 64))(
                  v24,
                  a3,
                  a4,
                  a5,
                  &v38);
        else
          v23 = (*(__int64 (__fastcall **)(__int64 *, struct ISyncKnowledge *, __int64, unsigned __int8 **))(v25 + 72))(
                  v24,
                  a3,
                  a4,
                  &v38);
      }
      else
      {
        v23 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, unsigned __int8 *, unsigned __int8 **))v39->lpVtbl->ProjectOntoItem)(
                v39,
                v16,
                &v38);
      }
      v10 = v23;
      if ( v23 < 0 )
        goto LABEL_44;
      if ( v37 )
      {
        v27 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, unsigned __int8 *))v37->lpVtbl->Union)(v37, v38);
        v26 = v38;
        v10 = v27;
      }
      else
      {
        (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v38 + 8LL))(v38);
        v26 = v38;
        v37 = (struct ISyncKnowledge *)v38;
      }
      (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v10 < 0 )
        goto LABEL_44;
      v18 = *(_QWORD *)(v18 + 8);
      IdParameterPair::FreeId(v28, v16);
      v19 = v40;
      v16 = 0;
      v38 = 0;
    }
    v29 = CSyncChange::GetRootItemIdInternal(**(CSyncChange ***)(*(_QWORD *)(a1 + 88) + 24LL), (unsigned __int8 **)v41);
    v17 = v41[0];
    v10 = v29;
    if ( v29 >= 0 )
    {
      v30 = *v40;
      if ( (int)IdParameterPair::CompareId(
                  (struct IdParameters *)((char *)*v15 + 16),
                  (const unsigned __int8 *)v41[0],
                  *v40) < 0 )
        goto LABEL_35;
      v41[0] = (struct ISyncKnowledge *)v30;
      v41[1] = v17;
      v38 = 0;
      v10 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, struct ISyncKnowledge **, unsigned __int8 **))v39->lpVtbl->ProjectOntoRange)(
              v39,
              v41,
              &v38);
      if ( v10 >= 0 )
      {
        if ( v37 )
        {
          v32 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, unsigned __int8 *))v37->lpVtbl->Union)(v37, v38);
          v31 = v38;
          v10 = v32;
        }
        else
        {
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v38 + 8LL))(v38);
          v31 = v38;
          v37 = (struct ISyncKnowledge *)v38;
        }
        (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v10 >= 0 )
        {
LABEL_35:
          v33 = v37;
          if ( !v37 )
          {
            v10 = CSyncChangeBatch::CreateEmptyLearnedKnowledge((CSyncChangeBatch *)a1, &v37);
            if ( v10 < 0 )
              goto LABEL_44;
            v33 = v37;
          }
          v34 = *(struct ISyncFilterInfo **)(a1 + 152);
          if ( !v34 )
          {
LABEL_41:
            if ( v33 )
            {
              ((void (__fastcall *)(struct ISyncKnowledge *))v33->lpVtbl->AddRef)(v33);
              v33 = v37;
              *a6 = v37;
            }
            else
            {
              v10 = -2147217379;
            }
LABEL_45:
            if ( v33 )
              ((void (__fastcall *)(struct ISyncKnowledge *))v33->lpVtbl->Release)(v33);
            IdParameterPair::FreeId((IdParameterPair *)v33, v16);
            IdParameterPair::FreeId(v35, (unsigned __int8 *)v17);
            ((void (__fastcall *)(struct ISyncKnowledge *))v39->lpVtbl->Release)(v39);
            goto LABEL_48;
          }
          v41[0] = 0;
          v10 = CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(*v15, v33, v34, v41);
          if ( v10 >= 0 )
          {
            ((void (__fastcall *)(struct ISyncKnowledge *))v37->lpVtbl->Release)(v37);
            v33 = v41[0];
            v37 = v41[0];
            goto LABEL_41;
          }
        }
      }
    }
LABEL_44:
    v33 = v37;
    goto LABEL_45;
  }
  v10 = -2147467261;
LABEL_49:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      79,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005022c  mov     [rsp-38h+arg_0], rbx
0x180050231  mov     [rsp-38h+arg_18], r9
0x180050236  mov     [rsp-38h+arg_10], r8
0x18005023b  push    rbp
0x18005023c  push    rsi
0x18005023d  push    rdi
0x18005023e  push    r12
0x180050240  push    r13
0x180050242  push    r14
0x180050244  push    r15
0x180050246  mov     rbp, rsp
0x180050249  sub     rsp, 60h
0x18005024d  mov     r10, r8
0x180050250  mov     r13d, edx
0x180050253  mov     rdi, rcx
0x180050256  mov     rcx, cs:WPP_GLOBAL_Control
0x18005025d  lea     rax, WPP_GLOBAL_Control
0x180050264  cmp     rcx, rax
0x180050267  jz      short loc_18005029C
0x180050269  test    byte ptr [rcx+1Ch], 10h
0x18005026d  jz      short loc_18005029C
0x18005026f  cmp     byte ptr [rcx+19h], 5
0x180050273  jb      short loc_18005029C
0x180050275  mov     rcx, [rcx+10h]
0x180050279  lea     r9, aCsyncchangebat_16; "CSyncChangeBatch::GetBatchLearnedKnowle"...
0x180050280  mov     edx, 4Eh ; 'N'
0x180050285  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18005028c  call    WPP_SF_s
0x180050291  mov     rcx, cs:WPP_GLOBAL_Control
0x180050298  mov     r10, [rbp+arg_10]
0x18005029c  xor     r14d, r14d
0x18005029f  mov     [rbp+var_20], r14
0x1800502a3  cmp     [rbp+arg_28], r14
0x1800502a7  jnz     short loc_1800502B3
0x1800502a9  mov     ebx, 80004003h
0x1800502ae  jmp     loc_1800505D3
0x1800502b3  mov     rax, [rdi+68h]
0x1800502b7  mov     rcx, [rax]; this
0x1800502ba  test    r13d, r13d
0x1800502bd  jnz     short loc_1800502CA
0x1800502bf  lea     rdx, [rbp+var_20]; struct ISyncKnowledge **
0x1800502c3  call    ?GetMadeWithKnowledge@ChangeGroup@@QEAAJPEAPEAUISyncKnowledge@@@Z; ChangeGroup::GetMadeWithKnowledge(ISyncKnowledge * *)
0x1800502c8  jmp     short loc_1800502F7
0x1800502ca  mov     r8, [rdi+88h]; struct IForgottenKnowledge *
0x1800502d1  mov     rdx, r10; struct ISyncKnowledge *
0x1800502d4  cmp     r13d, 1
0x1800502d8  jnz     short loc_1800502EE
0x1800502da  mov     r9d, [rbp+arg_20]; unsigned int
0x1800502de  lea     rax, [rbp+var_20]
0x1800502e2  mov     [rsp+60h+var_40], rax; struct ISyncKnowledge **
0x1800502e7  call    ?GetFFKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@KPEAPEAU2@@Z; ChangeGroup::GetFFKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ulong,ISyncKnowledge * *)
0x1800502ec  jmp     short loc_1800502F7
0x1800502ee  lea     r9, [rbp+var_20]; struct ISyncKnowledge **
0x1800502f2  call    ?GetMWKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAU2@@Z; ChangeGroup::GetMWKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge * *)
0x1800502f7  mov     ebx, eax
0x1800502f9  cmp     [rbp+var_20], r14
0x1800502fd  jz      loc_1800505CC
0x180050303  mov     rax, [rdi+58h]
0x180050307  lea     r15, [rdi+48h]
0x18005030b  mov     rsi, r14
0x18005030e  mov     [rbp+var_28], r14
0x180050312  mov     r12, r14
0x180050315  mov     [rbp+var_10], r14
0x180050319  mov     [rbp+var_30], r14
0x18005031d  mov     r14, [rax+10h]
0x180050321  lea     rax, [rdi+0F8h]
0x180050328  mov     [rbp+var_18], rax
0x18005032c  test    r14, r14
0x18005032f  jz      loc_18005044D
0x180050335  mov     rcx, [r14]; this
0x180050338  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x18005033c  call    ?GetRootItemIdInternal@CSyncChange@@QEAAJPEAPEAE@Z; CSyncChange::GetRootItemIdInternal(uchar * *)
0x180050341  mov     rsi, [rbp+var_28]
0x180050345  mov     ebx, eax
0x180050347  test    eax, eax
0x180050349  js      loc_180050597
0x18005034f  lea     rax, [rdi+0F8h]
0x180050356  mov     rdx, rsi; unsigned __int8 *
0x180050359  mov     r8, [rax]; unsigned __int8 *
0x18005035c  lea     r15, [rdi+48h]
0x180050360  mov     rcx, [r15]
0x180050363  add     rcx, 10h; this
0x180050367  mov     [rbp+var_18], rax
0x18005036b  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x180050370  test    eax, eax
0x180050372  jns     loc_18005044D
0x180050378  mov     [rbp+var_28], r12
0x18005037c  test    r13d, r13d
0x18005037f  jnz     short loc_18005039A
0x180050381  mov     rcx, [rbp+var_20]
0x180050385  lea     r8, [rbp+var_28]
0x180050389  mov     rdx, rsi
0x18005038c  mov     rax, [rcx]
0x18005038f  mov     rax, [rax+70h]
0x180050393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050398  jmp     short loc_1800503DB
0x18005039a  mov     rcx, [r14]
0x18005039d  mov     r8, [rbp+arg_18]
0x1800503a1  add     rcx, 28h ; '('
0x1800503a5  mov     rax, [rcx]
0x1800503a8  cmp     r13d, 1
0x1800503ac  jnz     short loc_1800503CA
0x1800503ae  mov     r9d, [rbp+arg_20]
0x1800503b2  lea     rdx, [rbp+var_28]
0x1800503b6  mov     rax, [rax+40h]
0x1800503ba  mov     [rsp+60h+var_40], rdx
0x1800503bf  mov     rdx, [rbp+arg_10]
0x1800503c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503c8  jmp     short loc_1800503DB
0x1800503ca  mov     rdx, [rbp+arg_10]
0x1800503ce  lea     r9, [rbp+var_28]
0x1800503d2  mov     rax, [rax+48h]
0x1800503d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503db  mov     ebx, eax
0x1800503dd  test    eax, eax
0x1800503df  js      loc_180050597
0x1800503e5  mov     rcx, [rbp+var_30]
0x1800503e9  test    rcx, rcx
0x1800503ec  jnz     short loc_180050408
0x1800503ee  mov     rcx, [rbp+var_28]
0x1800503f2  mov     rax, [rcx]
0x1800503f5  mov     rax, [rax+8]
0x1800503f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503fe  mov     rcx, [rbp+var_28]
0x180050402  mov     [rbp+var_30], rcx
0x180050406  jmp     short loc_18005041E
0x180050408  mov     rax, [rcx]
0x18005040b  mov     rdx, [rbp+var_28]
0x18005040f  mov     rax, [rax+68h]
0x180050413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050418  mov     rcx, [rbp+var_28]
0x18005041c  mov     ebx, eax
0x18005041e  mov     rax, [rcx]
0x180050421  mov     rax, [rax+10h]
0x180050425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005042a  test    ebx, ebx
0x18005042c  js      loc_180050597
0x180050432  mov     r14, [r14+8]
0x180050436  mov     rdx, rsi; unsigned __int8 *
0x180050439  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x18005043e  mov     rax, [rbp+var_18]
0x180050442  xor     esi, esi
0x180050444  mov     [rbp+var_28], rsi
0x180050448  jmp     loc_180050328
0x18005044d  mov     rax, [rdi+58h]
0x180050451  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x180050455  mov     rcx, [rax+18h]
0x180050459  mov     rcx, [rcx]; this
0x18005045c  call    ?GetRootItemIdInternal@CSyncChange@@QEAAJPEAPEAE@Z; CSyncChange::GetRootItemIdInternal(uchar * *)
0x180050461  mov     r12, [rbp+var_10]
0x180050465  mov     ebx, eax
0x180050467  test    eax, eax
0x180050469  js      loc_180050597
0x18005046f  mov     r14, [rbp+var_18]
0x180050473  mov     rdx, r12; unsigned __int8 *
0x180050476  mov     rcx, [r15]
0x180050479  add     rcx, 10h; this
0x18005047d  mov     r14, [r14]
0x180050480  mov     r8, r14; unsigned __int8 *
0x180050483  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x180050488  test    eax, eax
0x18005048a  js      loc_180050512
0x180050490  mov     rcx, [rbp+var_20]
0x180050494  lea     r8, [rbp+var_28]
0x180050498  mov     [rbp+var_10], r14
0x18005049c  lea     rdx, [rbp+var_10]
0x1800504a0  mov     [rbp+var_8], r12
0x1800504a4  mov     [rbp+var_28], 0
0x1800504ac  mov     rax, [rcx]
0x1800504af  mov     rax, [rax+80h]
0x1800504b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504bb  mov     ebx, eax
0x1800504bd  test    eax, eax
0x1800504bf  js      loc_180050597
0x1800504c5  mov     rcx, [rbp+var_30]
0x1800504c9  test    rcx, rcx
0x1800504cc  jnz     short loc_1800504E8
0x1800504ce  mov     rcx, [rbp+var_28]
0x1800504d2  mov     rax, [rcx]
0x1800504d5  mov     rax, [rax+8]
0x1800504d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504de  mov     rcx, [rbp+var_28]
0x1800504e2  mov     [rbp+var_30], rcx
0x1800504e6  jmp     short loc_1800504FE
0x1800504e8  mov     rax, [rcx]
0x1800504eb  mov     rdx, [rbp+var_28]
0x1800504ef  mov     rax, [rax+68h]
0x1800504f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504f8  mov     rcx, [rbp+var_28]
0x1800504fc  mov     ebx, eax
0x1800504fe  mov     rax, [rcx]
0x180050501  mov     rax, [rax+10h]
0x180050505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005050a  test    ebx, ebx
0x18005050c  js      loc_180050597
0x180050512  mov     rcx, [rbp+var_30]
0x180050516  test    rcx, rcx
0x180050519  jnz     short loc_180050531
0x18005051b  lea     rdx, [rbp+var_30]; struct ISyncKnowledge **
0x18005051f  mov     rcx, rdi; this
0x180050522  call    ?CreateEmptyLearnedKnowledge@CSyncChangeBatch@@AEAAJPEAPEAUISyncKnowledge@@@Z; CSyncChangeBatch::CreateEmptyLearnedKnowledge(ISyncKnowledge * *)
0x180050527  mov     ebx, eax
0x180050529  test    eax, eax
0x18005052b  js      short loc_180050597
0x18005052d  mov     rcx, [rbp+var_30]
0x180050531  mov     r8, [rdi+98h]; struct ISyncFilterInfo *
0x180050538  test    r8, r8
0x18005053b  jz      short loc_180050572
0x18005053d  mov     rdx, rcx; struct ISyncKnowledge *
0x180050540  mov     [rbp+var_10], 0
0x180050548  mov     rcx, [r15]; struct IdParameters *
0x18005054b  lea     r9, [rbp+var_10]; struct ISyncKnowledge **
0x18005054f  call    ?ProjectKnowledgeOntoColumnsIfRequired@CSyncChangeBatch@@SAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUISyncFilterInfo@@PEAPEAU3@@Z; CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(IdParameters *,ISyncKnowledge *,ISyncFilterInfo *,ISyncKnowledge * *)
0x180050554  mov     ebx, eax
0x180050556  test    eax, eax
0x180050558  js      short loc_180050597
0x18005055a  mov     rcx, [rbp+var_30]
0x18005055e  mov     rax, [rcx]
0x180050561  mov     rax, [rax+10h]
0x180050565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005056a  mov     rcx, [rbp+var_10]
0x18005056e  mov     [rbp+var_30], rcx
0x180050572  test    rcx, rcx
0x180050575  jnz     short loc_18005057E
0x180050577  mov     ebx, 8004101Dh
0x18005057c  jmp     short loc_18005059B
0x18005057e  mov     rax, [rcx]
0x180050581  mov     rax, [rax+8]
0x180050585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005058a  mov     rax, [rbp+arg_28]
0x18005058e  mov     rcx, [rbp+var_30]
0x180050592  mov     [rax], rcx
0x180050595  jmp     short loc_18005059B
0x180050597  mov     rcx, [rbp+var_30]
0x18005059b  test    rcx, rcx
0x18005059e  jz      short loc_1800505AC
0x1800505a0  mov     rax, [rcx]
0x1800505a3  mov     rax, [rax+10h]
0x1800505a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505ac  mov     rdx, rsi; unsigned __int8 *
0x1800505af  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x1800505b4  mov     rdx, r12; unsigned __int8 *
0x1800505b7  call    ?FreeId@IdParameterPair@@QEBAXPEAE@Z; IdParameterPair::FreeId(uchar *)
0x1800505bc  mov     rcx, [rbp+var_20]
0x1800505c0  mov     rax, [rcx]
0x1800505c3  mov     rax, [rax+10h]
0x1800505c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505d3  lea     rax, WPP_GLOBAL_Control
0x1800505da  cmp     rcx, rax
0x1800505dd  jz      short loc_18005060B
0x1800505df  test    byte ptr [rcx+1Ch], 10h
0x1800505e3  jz      short loc_18005060B
0x1800505e5  cmp     byte ptr [rcx+19h], 5
0x1800505e9  jb      short loc_18005060B
0x1800505eb  mov     rcx, [rcx+10h]
0x1800505ef  lea     r9, aCsyncchangebat_16; "CSyncChangeBatch::GetBatchLearnedKnowle"...
0x1800505f6  mov     edx, 4Fh ; 'O'
0x1800505fb  mov     dword ptr [rsp+60h+var_40], ebx
0x1800505ff  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x180050606  call    WPP_SF_sD
0x18005060b  mov     eax, ebx
0x18005060d  mov     rbx, [rsp+60h+arg_0]
0x180050615  add     rsp, 60h
0x180050619  pop     r15
0x18005061b  pop     r14
0x18005061d  pop     r13
0x18005061f  pop     r12
0x180050621  pop     rdi
0x180050622  pop     rsi
0x180050623  pop     rbp
0x180050624  retn
```
