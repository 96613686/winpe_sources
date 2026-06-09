# CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)

- ea: `0x180058560`
- end: `0x180058723`
- name: `?GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete@CSyncChange@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU2@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CSyncChange *this, struct ISyncKnowledge *, struct IEnumItemIds *, unsigned int, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002e58c`
- `0x1800509f8`
- `0x180056f84`
- `0x180058560`
- `0x180078bb8`
- `0x180094010`

## string_xrefs

- `0x1800585a5`: `CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`
- `0x1800586ee`: `CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(
        CSyncChange *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5)
{
  PVOID *v9; // rcx
  struct ISyncKnowledge **v10; // rsi
  __int64 v11; // rax
  unsigned int ClosedLowerBoundItemIdInternal; // edi
  CSyncChange *v13; // rbp
  struct IForgottenKnowledge *v14; // r8
  ChangeGroup *v15; // rcx
  struct ISyncKnowledge *v16; // rbx
  struct ISyncKnowledge *v18; // [rsp+68h] [rbp+10h] BYREF

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      110,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && (v10 = a5) != 0 )
  {
    if ( !*((_DWORD *)this + 27) || *((_DWORD *)this + 47) )
    {
      ClosedLowerBoundItemIdInternal = -2147217407;
    }
    else
    {
      v11 = *((_QWORD *)this + 15);
      if ( v11 && a4 >= *(_DWORD *)(v11 + 80) )
      {
        ClosedLowerBoundItemIdInternal = -2147024809;
      }
      else
      {
        v13 = (CSyncChange *)((char *)this - 40);
        v18 = 0;
        ClosedLowerBoundItemIdInternal = CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(
                                           *((CSyncChangeBatch **)this + 26),
                                           (unsigned __int8 **)&v18);
        if ( !ClosedLowerBoundItemIdInternal )
        {
          if ( (int)IdParameterPair::CompareId(
                      (IdParameterPair *)(*((_QWORD *)this + 28) + 16LL),
                      *((const unsigned __int8 **)this + 10),
                      (const unsigned __int8 *)v18) < 0 )
          {
            ClosedLowerBoundItemIdInternal = (*(__int64 (__fastcall **)(CSyncChange *, struct ISyncKnowledge *, struct IEnumItemIds *, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)this + 64LL))(
                                               this,
                                               a2,
                                               a3,
                                               a4,
                                               v10);
          }
          else
          {
            v14 = (struct IForgottenKnowledge *)*((_QWORD *)this + 17);
            v15 = (ChangeGroup *)*((_QWORD *)this + 15);
            v18 = 0;
            ClosedLowerBoundItemIdInternal = ChangeGroup::GetFFKComplementedByDKUnionedWithFK(v15, a2, v14, a4, &v18);
            if ( !ClosedLowerBoundItemIdInternal )
            {
              v16 = v18;
              ClosedLowerBoundItemIdInternal = CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(
                                                 v13,
                                                 v18,
                                                 v10);
              ((void (__fastcall *)(struct ISyncKnowledge *))v16->lpVtbl->Release)(v16);
            }
          }
        }
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    ClosedLowerBoundItemIdInternal = -2147467261;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      111,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete",
      ClosedLowerBoundItemIdInternal);
  return ClosedLowerBoundItemIdInternal;
}

```

## disassembly

```asm
0x180058560  mov     [rsp+arg_0], rbx
0x180058565  mov     [rsp+arg_10], rbp
0x18005856a  push    rsi
0x18005856b  push    rdi
0x18005856c  push    r12
0x18005856e  push    r14
0x180058570  push    r15
0x180058572  sub     rsp, 30h
0x180058576  mov     r15d, r9d
0x180058579  mov     r12, r8
0x18005857c  mov     r14, rdx
0x18005857f  mov     rbx, rcx
0x180058582  mov     rcx, cs:WPP_GLOBAL_Control
0x180058589  lea     rax, WPP_GLOBAL_Control
0x180058590  cmp     rcx, rax
0x180058593  jz      short loc_1800585C4
0x180058595  test    byte ptr [rcx+1Ch], 20h
0x180058599  jz      short loc_1800585C4
0x18005859b  cmp     byte ptr [rcx+19h], 5
0x18005859f  jb      short loc_1800585C4
0x1800585a1  mov     rcx, [rcx+10h]
0x1800585a5  lea     r9, aCsyncchangeGet_9; "CSyncChange::GetLearnedFilterForgottenK"...
0x1800585ac  mov     edx, 6Eh ; 'n'
0x1800585b1  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x1800585b8  call    WPP_SF_s
0x1800585bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800585c4  test    r14, r14
0x1800585c7  jz      loc_1800586CD
0x1800585cd  mov     rsi, [rsp+58h+arg_20]
0x1800585d5  test    rsi, rsi
0x1800585d8  jz      loc_1800586CD
0x1800585de  cmp     dword ptr [rbx+6Ch], 0
0x1800585e2  jz      loc_1800586C6
0x1800585e8  cmp     dword ptr [rbx+0BCh], 0
0x1800585ef  jnz     loc_1800586C6
0x1800585f5  mov     rax, [rbx+78h]
0x1800585f9  test    rax, rax
0x1800585fc  jz      short loc_18005860E
0x1800585fe  cmp     r15d, [rax+50h]
0x180058602  jb      short loc_18005860E
0x180058604  mov     edi, 80070057h
0x180058609  jmp     loc_1800586D2
0x18005860e  lea     rbp, [rbx-28h]
0x180058612  mov     [rsp+58h+arg_8], 0
0x18005861b  mov     rcx, [rbp+0F8h]; this
0x180058622  lea     rdx, [rsp+58h+arg_8]; unsigned __int8 **
0x180058627  call    ?GetClosedLowerBoundItemIdInternal@CSyncChangeBatch@@QEAAJPEAPEAE@Z; CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(uchar * *)
0x18005862c  mov     edi, eax
0x18005862e  test    eax, eax
0x180058630  jnz     short loc_1800586A2
0x180058632  mov     rcx, [rbx+0E0h]
0x180058639  mov     r8, [rsp+58h+arg_8]; unsigned __int8 *
0x18005863e  add     rcx, 10h; this
0x180058642  mov     rdx, [rbx+50h]; unsigned __int8 *
0x180058646  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x18005864b  mov     r9d, r15d; unsigned int
0x18005864e  mov     rdx, r14; struct ISyncKnowledge *
0x180058651  test    eax, eax
0x180058653  js      short loc_1800586AB
0x180058655  mov     r8, [rbx+88h]; struct IForgottenKnowledge *
0x18005865c  lea     rax, [rsp+58h+arg_8]
0x180058661  mov     rcx, [rbx+78h]; this
0x180058665  mov     [rsp+58h+var_38], rax; struct ISyncKnowledge **
0x18005866a  mov     [rsp+58h+arg_8], 0
0x180058673  call    ?GetFFKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@KPEAPEAU2@@Z; ChangeGroup::GetFFKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ulong,ISyncKnowledge * *)
0x180058678  mov     edi, eax
0x18005867a  test    eax, eax
0x18005867c  jnz     short loc_1800586A2
0x18005867e  mov     rbx, [rsp+58h+arg_8]
0x180058683  mov     r8, rsi; struct ISyncKnowledge **
0x180058686  mov     rdx, rbx; struct ISyncKnowledge *
0x180058689  mov     rcx, rbp; this
0x18005868c  call    ?GetChangeLearnedKnowledgeAfterRecoveryComplete@CSyncChange@@AEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge *,ISyncKnowledge * *)
0x180058691  mov     edi, eax
0x180058693  mov     rcx, rbx
0x180058696  mov     rax, [rbx]
0x180058699  mov     rax, [rax+10h]
0x18005869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586a9  jmp     short loc_1800586D2
0x1800586ab  mov     rax, [rbx]
0x1800586ae  mov     r8, r12
0x1800586b1  mov     rcx, rbx
0x1800586b4  mov     [rsp+58h+var_38], rsi
0x1800586b9  mov     rax, [rax+40h]
0x1800586bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586c2  mov     edi, eax
0x1800586c4  jmp     short loc_1800586A2
0x1800586c6  mov     edi, 80041001h
0x1800586cb  jmp     short loc_1800586D2
0x1800586cd  mov     edi, 80004003h
0x1800586d2  lea     rax, WPP_GLOBAL_Control
0x1800586d9  cmp     rcx, rax
0x1800586dc  jz      short loc_18005870A
0x1800586de  test    byte ptr [rcx+1Ch], 20h
0x1800586e2  jz      short loc_18005870A
0x1800586e4  cmp     byte ptr [rcx+19h], 5
0x1800586e8  jb      short loc_18005870A
0x1800586ea  mov     rcx, [rcx+10h]
0x1800586ee  lea     r9, aCsyncchangeGet_9; "CSyncChange::GetLearnedFilterForgottenK"...
0x1800586f5  mov     edx, 6Fh ; 'o'
0x1800586fa  mov     dword ptr [rsp+58h+var_38], edi
0x1800586fe  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180058705  call    WPP_SF_sD
0x18005870a  mov     rbx, [rsp+58h+arg_0]
0x18005870f  mov     eax, edi
0x180058711  mov     rbp, [rsp+58h+arg_10]
0x180058716  add     rsp, 30h
0x18005871a  pop     r15
0x18005871c  pop     r14
0x18005871e  pop     r12
0x180058720  pop     rdi
0x180058721  pop     rsi
0x180058722  retn
```
