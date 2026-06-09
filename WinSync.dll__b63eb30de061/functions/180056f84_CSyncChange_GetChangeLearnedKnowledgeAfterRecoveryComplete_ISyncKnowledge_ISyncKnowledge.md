# CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge *,ISyncKnowledge * *)

- ea: `0x180056f84`
- end: `0x1800571f6`
- name: `?GetChangeLearnedKnowledgeAfterRecoveryComplete@CSyncChange@@AEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z`
- size: `626`
- prototype: `__int64 __fastcall(CSyncChange *__hidden this, struct ISyncKnowledge *, struct ISyncKnowledge **)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180057920`
- `0x180058560`
- `0x180058970`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x18002e58c`
- `0x18002f4fc`
- `0x1800509f8`
- `0x180052630`
- `0x180056f84`
- `0x180057d80`
- `0x180059134`
- `0x180094010`

## string_xrefs

- `0x180056fc3`: `CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete`
- `0x1800571c4`: `CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(
        CSyncChange *this,
        struct ISyncKnowledge *a2,
        struct ISyncKnowledge **a3)
{
  CSyncChangeBatch *v6; // rcx
  int ClosedLowerBoundItemIdInternal; // ebx
  CSyncChange *v8; // rcx
  unsigned __int8 *v9; // rdi
  __int64 v10; // rbx
  int v11; // eax
  CSyncChange *v12; // rcx
  unsigned __int8 *v13; // rdx
  IdParameterPair *v14; // rcx
  int v15; // eax
  struct ISyncKnowledgeVtbl *lpVtbl; // rax
  struct ISyncFilterInfo *v17; // r8
  struct IdParameters *v18; // rcx
  struct ISyncKnowledge *v19; // rcx
  struct ISyncKnowledge *v20; // rcx
  unsigned __int8 *v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v23[2]; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v24; // [rsp+48h] [rbp-8h] BYREF
  struct ISyncKnowledge *v25; // [rsp+80h] [rbp+30h] BYREF
  struct ISyncKnowledge *v26; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete");
  }
  v6 = (CSyncChangeBatch *)*((_QWORD *)this + 31);
  v26 = 0;
  v22 = 0;
  ClosedLowerBoundItemIdInternal = CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(v6, &v22);
  if ( ClosedLowerBoundItemIdInternal < 0 )
    goto LABEL_26;
  if ( (int)IdParameterPair::CompareId(
              (IdParameterPair *)(*((_QWORD *)this + 33) + 16LL),
              *((const unsigned __int8 **)this + 15),
              v22) < 0 )
  {
    ClosedLowerBoundItemIdInternal = ((__int64 (__fastcall *)(struct ISyncKnowledge *, _QWORD, struct ISyncKnowledge **))a2->lpVtbl->ProjectOntoItem)(
                                       a2,
                                       *((_QWORD *)this + 15),
                                       &v26);
    goto LABEL_20;
  }
  v8 = (CSyncChange *)*((_QWORD *)this + 24);
  v24 = 0;
  v9 = 0;
  ClosedLowerBoundItemIdInternal = CSyncChange::GetRootItemIdInternal(v8, &v24);
  v23[0] = 0;
  if ( ClosedLowerBoundItemIdInternal >= 0 )
  {
    v10 = *((_QWORD *)this + 33);
    v11 = IdParameterPair::CompareId((IdParameterPair *)(v10 + 16), v24, v22);
    if ( v11 < 0 )
      goto LABEL_10;
    if ( v11 )
    {
      v13 = v24;
      v14 = (IdParameterPair *)(v10 + 16);
    }
    else
    {
      v12 = (CSyncChange *)*((_QWORD *)this + 24);
      LODWORD(v25) = 0;
      ClosedLowerBoundItemIdInternal = CSyncChange::GetFlagsPrivate(v12, (unsigned int *)&v25);
      if ( ClosedLowerBoundItemIdInternal < 0 )
        goto LABEL_19;
      if ( ((unsigned int)v25 & 0x10000) != 0 )
      {
LABEL_10:
        v9 = v22;
        if ( v22 )
          _InterlockedIncrement((volatile signed __int32 *)v22 - 1);
        goto LABEL_18;
      }
      v13 = v22;
      v14 = (IdParameterPair *)(*((_QWORD *)this + 33) + 16LL);
    }
    v15 = IdParameterPair::IncrementId(v14, v13, v23);
    v9 = v23[0];
    ClosedLowerBoundItemIdInternal = v15;
    if ( v15 >= 0 )
    {
LABEL_18:
      v23[1] = *((unsigned __int8 **)this + 15);
      lpVtbl = a2->lpVtbl;
      v23[0] = v9;
      ClosedLowerBoundItemIdInternal = ((__int64 (__fastcall *)(struct ISyncKnowledge *, unsigned __int8 **, struct ISyncKnowledge **))lpVtbl->ProjectOntoRange)(
                                         a2,
                                         v23,
                                         &v26);
    }
  }
LABEL_19:
  IdParameters::FreeId(v9);
  IdParameters::FreeId(v24);
LABEL_20:
  IdParameters::FreeId(v22);
  if ( ClosedLowerBoundItemIdInternal >= 0 )
  {
    v17 = (struct ISyncFilterInfo *)*((_QWORD *)this + 32);
    if ( !v17 )
    {
      v19 = v26;
      goto LABEL_25;
    }
    v18 = (struct IdParameters *)*((_QWORD *)this + 33);
    v25 = 0;
    ClosedLowerBoundItemIdInternal = CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(v18, v26, v17, &v25);
    if ( ClosedLowerBoundItemIdInternal >= 0 )
    {
      ((void (__fastcall *)(struct ISyncKnowledge *))v26->lpVtbl->Release)(v26);
      v19 = v25;
      v26 = v25;
LABEL_25:
      ((void (__fastcall *)(struct ISyncKnowledge *))v19->lpVtbl->AddRef)(v19);
      v20 = v26;
      *a3 = v26;
      goto LABEL_27;
    }
  }
LABEL_26:
  v20 = v26;
LABEL_27:
  if ( v20 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v20->lpVtbl->Release)(v20);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete",
      ClosedLowerBoundItemIdInternal);
  }
  return (unsigned int)ClosedLowerBoundItemIdInternal;
}

```

## disassembly

```asm
0x180056f84  mov     [rsp-28h+arg_8], rbx
0x180056f89  push    rbp
0x180056f8a  push    rsi
0x180056f8b  push    rdi
0x180056f8c  push    r12
0x180056f8e  push    r13
0x180056f90  mov     rbp, rsp
0x180056f93  sub     rsp, 50h
0x180056f97  mov     r13, r8
0x180056f9a  mov     r12, rdx
0x180056f9d  mov     rsi, rcx
0x180056fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fa7  lea     rdi, WPP_GLOBAL_Control
0x180056fae  cmp     rcx, rdi
0x180056fb1  jz      short loc_180056FDB
0x180056fb3  test    byte ptr [rcx+1Ch], 20h
0x180056fb7  jz      short loc_180056FDB
0x180056fb9  cmp     byte ptr [rcx+19h], 5
0x180056fbd  jb      short loc_180056FDB
0x180056fbf  mov     rcx, [rcx+10h]
0x180056fc3  lea     r9, aCsyncchangeGet_26; "CSyncChange::GetChangeLearnedKnowledgeA"...
0x180056fca  mov     edx, 53h ; 'S'
0x180056fcf  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180056fd6  call    WPP_SF_s
0x180056fdb  mov     rcx, [rsi+0F8h]; this
0x180056fe2  lea     rdx, [rbp+var_20]; unsigned __int8 **
0x180056fe6  mov     [rbp+arg_18], 0
0x180056fee  mov     [rbp+var_20], 0
0x180056ff6  call    ?GetClosedLowerBoundItemIdInternal@CSyncChangeBatch@@QEAAJPEAPEAE@Z; CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(uchar * *)
0x180056ffb  mov     ebx, eax
0x180056ffd  test    eax, eax
0x180056fff  js      loc_180057193
0x180057005  mov     rcx, [rsi+108h]
0x18005700c  mov     r8, [rbp+var_20]; unsigned __int8 *
0x180057010  add     rcx, 10h; this
0x180057014  mov     rdx, [rsi+78h]; unsigned __int8 *
0x180057018  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x18005701d  test    eax, eax
0x18005701f  jns     short loc_180057040
0x180057021  mov     rax, [r12]
0x180057025  lea     r8, [rbp+arg_18]
0x180057029  mov     rdx, [rsi+78h]
0x18005702d  mov     rcx, r12
0x180057030  mov     rax, [rax+70h]
0x180057034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057039  mov     ebx, eax
0x18005703b  jmp     loc_180057124
0x180057040  mov     rcx, [rsi+0C0h]; this
0x180057047  lea     rdx, [rbp+var_8]; unsigned __int8 **
0x18005704b  mov     [rbp+var_8], 0
0x180057053  call    ?GetRootItemIdInternal@CSyncChange@@QEAAJPEAPEAE@Z; CSyncChange::GetRootItemIdInternal(uchar * *)
0x180057058  xor     edi, edi
0x18005705a  mov     ebx, eax
0x18005705c  mov     [rbp+var_18], rdi
0x180057060  test    eax, eax
0x180057062  js      loc_18005710C
0x180057068  mov     rbx, [rsi+108h]
0x18005706f  mov     r8, [rbp+var_20]; unsigned __int8 *
0x180057073  mov     rdx, [rbp+var_8]; unsigned __int8 *
0x180057077  lea     rcx, [rbx+10h]; this
0x18005707b  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x180057080  test    eax, eax
0x180057082  jns     short loc_180057093
0x180057084  mov     rdi, [rbp+var_20]
0x180057088  test    rdi, rdi
0x18005708b  jz      short loc_1800570E3
0x18005708d  lock inc dword ptr [rdi-4]
0x180057091  jmp     short loc_1800570E3
0x180057093  jnz     short loc_1800570C8
0x180057095  mov     rcx, [rsi+0C0h]; this
0x18005709c  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800570a0  mov     dword ptr [rbp+arg_0], edi
0x1800570a3  call    ?GetFlagsPrivate@CSyncChange@@QEAAJPEAK@Z; CSyncChange::GetFlagsPrivate(ulong *)
0x1800570a8  mov     ebx, eax
0x1800570aa  test    eax, eax
0x1800570ac  js      short loc_18005710C
0x1800570ae  test    dword ptr [rbp+arg_0], 10000h
0x1800570b5  jnz     short loc_180057084
0x1800570b7  mov     rcx, [rsi+108h]
0x1800570be  mov     rdx, [rbp+var_20]
0x1800570c2  add     rcx, 10h
0x1800570c6  jmp     short loc_1800570D0
0x1800570c8  mov     rdx, [rbp+var_8]; unsigned __int8 *
0x1800570cc  lea     rcx, [rbx+10h]; this
0x1800570d0  lea     r8, [rbp+var_18]; unsigned __int8 **
0x1800570d4  call    ?IncrementId@IdParameterPair@@QEAAJPEBEPEAPEAE@Z; IdParameterPair::IncrementId(uchar const *,uchar * *)
0x1800570d9  mov     rdi, [rbp+var_18]
0x1800570dd  mov     ebx, eax
0x1800570df  test    eax, eax
0x1800570e1  js      short loc_18005710C
0x1800570e3  mov     rax, [rsi+78h]
0x1800570e7  lea     r8, [rbp+arg_18]
0x1800570eb  mov     [rbp+var_10], rax
0x1800570ef  lea     rdx, [rbp+var_18]
0x1800570f3  mov     rax, [r12]
0x1800570f7  mov     rcx, r12
0x1800570fa  mov     [rbp+var_18], rdi
0x1800570fe  mov     rax, [rax+80h]
0x180057105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005710a  mov     ebx, eax
0x18005710c  mov     rcx, rdi; unsigned __int8 *
0x18005710f  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180057114  mov     rcx, [rbp+var_8]; unsigned __int8 *
0x180057118  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18005711d  lea     rdi, WPP_GLOBAL_Control
0x180057124  mov     rcx, [rbp+var_20]; unsigned __int8 *
0x180057128  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x18005712d  test    ebx, ebx
0x18005712f  js      short loc_180057193
0x180057131  mov     r8, [rsi+100h]; struct ISyncFilterInfo *
0x180057138  test    r8, r8
0x18005713b  jz      short loc_180057179
0x18005713d  mov     rdx, [rbp+arg_18]; struct ISyncKnowledge *
0x180057141  lea     r9, [rbp+arg_0]; struct ISyncKnowledge **
0x180057145  mov     rcx, [rsi+108h]; struct IdParameters *
0x18005714c  mov     [rbp+arg_0], 0
0x180057154  call    ?ProjectKnowledgeOntoColumnsIfRequired@CSyncChangeBatch@@SAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUISyncFilterInfo@@PEAPEAU3@@Z; CSyncChangeBatch::ProjectKnowledgeOntoColumnsIfRequired(IdParameters *,ISyncKnowledge *,ISyncFilterInfo *,ISyncKnowledge * *)
0x180057159  mov     ebx, eax
0x18005715b  test    eax, eax
0x18005715d  js      short loc_180057193
0x18005715f  mov     rcx, [rbp+arg_18]
0x180057163  mov     rax, [rcx]
0x180057166  mov     rax, [rax+10h]
0x18005716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005716f  mov     rcx, [rbp+arg_0]
0x180057173  mov     [rbp+arg_18], rcx
0x180057177  jmp     short loc_18005717D
0x180057179  mov     rcx, [rbp+arg_18]
0x18005717d  mov     rax, [rcx]
0x180057180  mov     rax, [rax+8]
0x180057184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057189  mov     rcx, [rbp+arg_18]
0x18005718d  mov     [r13+0], rcx
0x180057191  jmp     short loc_180057197
0x180057193  mov     rcx, [rbp+arg_18]
0x180057197  test    rcx, rcx
0x18005719a  jz      short loc_1800571A8
0x18005719c  mov     rax, [rcx]
0x18005719f  mov     rax, [rax+10h]
0x1800571a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571af  cmp     rcx, rdi
0x1800571b2  jz      short loc_1800571E0
0x1800571b4  test    byte ptr [rcx+1Ch], 20h
0x1800571b8  jz      short loc_1800571E0
0x1800571ba  cmp     byte ptr [rcx+19h], 5
0x1800571be  jb      short loc_1800571E0
0x1800571c0  mov     rcx, [rcx+10h]
0x1800571c4  lea     r9, aCsyncchangeGet_26; "CSyncChange::GetChangeLearnedKnowledgeA"...
0x1800571cb  mov     edx, 54h ; 'T'
0x1800571d0  mov     [rsp+50h+var_30], ebx
0x1800571d4  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x1800571db  call    WPP_SF_sD
0x1800571e0  mov     eax, ebx
0x1800571e2  mov     rbx, [rsp+50h+arg_8]
0x1800571ea  add     rsp, 50h
0x1800571ee  pop     r13
0x1800571f0  pop     r12
0x1800571f2  pop     rdi
0x1800571f3  pop     rsi
0x1800571f4  pop     rbp
0x1800571f5  retn
```
