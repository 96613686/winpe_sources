# CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)

- ea: `0x180057920`
- end: `0x180057ab1`
- name: `?GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete@CSyncChange@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z`
- size: `401`
- prototype: `__int64 __fastcall(CSyncChange *this, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002e58c`
- `0x1800509f8`
- `0x180056f84`
- `0x180057920`
- `0x180078fa8`
- `0x180094010`

## string_xrefs

- `0x180057965`: `CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`
- `0x180057a7c`: `CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(
        CSyncChange *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        struct ISyncKnowledge **a4)
{
  PVOID *v8; // rcx
  CSyncChange *v9; // rbp
  unsigned int ClosedLowerBoundItemIdInternal; // edi
  struct IForgottenKnowledge *v11; // r8
  ChangeGroup *v12; // rcx
  struct ISyncKnowledge *v13; // rbx
  struct ISyncKnowledge *v15; // [rsp+68h] [rbp+10h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      108,
      WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      "CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a4 )
  {
    if ( !*((_DWORD *)this + 27) || *((_DWORD *)this + 47) )
    {
      ClosedLowerBoundItemIdInternal = -2147217407;
    }
    else
    {
      v9 = (CSyncChange *)((char *)this - 40);
      v15 = 0;
      ClosedLowerBoundItemIdInternal = CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(
                                         *((CSyncChangeBatch **)this + 26),
                                         (unsigned __int8 **)&v15);
      if ( !ClosedLowerBoundItemIdInternal )
      {
        if ( (int)IdParameterPair::CompareId(
                    (IdParameterPair *)(*((_QWORD *)this + 28) + 16LL),
                    *((const unsigned __int8 **)this + 10),
                    (const unsigned __int8 *)v15) < 0 )
        {
          ClosedLowerBoundItemIdInternal = (*(__int64 (__fastcall **)(CSyncChange *, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **))(*(_QWORD *)this + 72LL))(
                                             this,
                                             a2,
                                             a3,
                                             a4);
        }
        else
        {
          v11 = (struct IForgottenKnowledge *)*((_QWORD *)this + 17);
          v12 = (ChangeGroup *)*((_QWORD *)this + 15);
          v15 = 0;
          ClosedLowerBoundItemIdInternal = ChangeGroup::GetMWKComplementedByDKUnionedWithFK(v12, a2, v11, &v15);
          if ( !ClosedLowerBoundItemIdInternal )
          {
            v13 = v15;
            ClosedLowerBoundItemIdInternal = CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(v9, v15, a4);
            ((void (__fastcall *)(struct ISyncKnowledge *))v13->lpVtbl->Release)(v13);
          }
        }
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    ClosedLowerBoundItemIdInternal = -2147467261;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      109,
      (unsigned int)WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids,
      (unsigned int)"CSyncChange::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete",
      ClosedLowerBoundItemIdInternal);
  return ClosedLowerBoundItemIdInternal;
}

```

## disassembly

```asm
0x180057920  mov     [rsp+arg_0], rbx
0x180057925  mov     [rsp+arg_10], rbp
0x18005792a  push    rsi
0x18005792b  push    rdi
0x18005792c  push    r13
0x18005792e  push    r14
0x180057930  push    r15
0x180057932  sub     rsp, 30h
0x180057936  mov     r14, r9
0x180057939  mov     r15, r8
0x18005793c  mov     rsi, rdx
0x18005793f  mov     rbx, rcx
0x180057942  mov     rcx, cs:WPP_GLOBAL_Control
0x180057949  lea     r13, WPP_GLOBAL_Control
0x180057950  cmp     rcx, r13
0x180057953  jz      short loc_180057984
0x180057955  test    byte ptr [rcx+1Ch], 20h
0x180057959  jz      short loc_180057984
0x18005795b  cmp     byte ptr [rcx+19h], 5
0x18005795f  jb      short loc_180057984
0x180057961  mov     rcx, [rcx+10h]
0x180057965  lea     r9, aCsyncchangeGet_1; "CSyncChange::GetFilteredReplicaLearnedF"...
0x18005796c  mov     edx, 6Ch ; 'l'
0x180057971  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180057978  call    WPP_SF_s
0x18005797d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057984  test    rsi, rsi
0x180057987  jz      loc_180057A62
0x18005798d  test    r14, r14
0x180057990  jz      loc_180057A62
0x180057996  cmp     dword ptr [rbx+6Ch], 0
0x18005799a  jz      loc_180057A5B
0x1800579a0  cmp     dword ptr [rbx+0BCh], 0
0x1800579a7  jnz     loc_180057A5B
0x1800579ad  lea     rbp, [rbx-28h]
0x1800579b1  mov     [rsp+58h+arg_8], 0
0x1800579ba  mov     rcx, [rbp+0F8h]; this
0x1800579c1  lea     rdx, [rsp+58h+arg_8]; unsigned __int8 **
0x1800579c6  call    ?GetClosedLowerBoundItemIdInternal@CSyncChangeBatch@@QEAAJPEAPEAE@Z; CSyncChangeBatch::GetClosedLowerBoundItemIdInternal(uchar * *)
0x1800579cb  mov     edi, eax
0x1800579cd  test    eax, eax
0x1800579cf  jnz     short loc_180057A39
0x1800579d1  mov     rcx, [rbx+0E0h]
0x1800579d8  mov     r8, [rsp+58h+arg_8]; unsigned __int8 *
0x1800579dd  add     rcx, 10h; this
0x1800579e1  mov     rdx, [rbx+50h]; unsigned __int8 *
0x1800579e5  call    ?CompareId@IdParameterPair@@QEBAHPEBE0@Z; IdParameterPair::CompareId(uchar const *,uchar const *)
0x1800579ea  mov     rdx, rsi; struct ISyncKnowledge *
0x1800579ed  test    eax, eax
0x1800579ef  js      short loc_180057A42
0x1800579f1  mov     r8, [rbx+88h]; struct IForgottenKnowledge *
0x1800579f8  lea     r9, [rsp+58h+arg_8]; struct ISyncKnowledge **
0x1800579fd  mov     rcx, [rbx+78h]; this
0x180057a01  mov     [rsp+58h+arg_8], 0
0x180057a0a  call    ?GetMWKComplementedByDKUnionedWithFK@ChangeGroup@@QEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAU2@@Z; ChangeGroup::GetMWKComplementedByDKUnionedWithFK(ISyncKnowledge *,IForgottenKnowledge *,ISyncKnowledge * *)
0x180057a0f  mov     edi, eax
0x180057a11  test    eax, eax
0x180057a13  jnz     short loc_180057A39
0x180057a15  mov     rbx, [rsp+58h+arg_8]
0x180057a1a  mov     r8, r14; struct ISyncKnowledge **
0x180057a1d  mov     rdx, rbx; struct ISyncKnowledge *
0x180057a20  mov     rcx, rbp; this
0x180057a23  call    ?GetChangeLearnedKnowledgeAfterRecoveryComplete@CSyncChange@@AEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChange::GetChangeLearnedKnowledgeAfterRecoveryComplete(ISyncKnowledge *,ISyncKnowledge * *)
0x180057a28  mov     edi, eax
0x180057a2a  mov     rcx, rbx
0x180057a2d  mov     rax, [rbx]
0x180057a30  mov     rax, [rax+10h]
0x180057a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a40  jmp     short loc_180057A67
0x180057a42  mov     rax, [rbx]
0x180057a45  mov     r9, r14
0x180057a48  mov     r8, r15
0x180057a4b  mov     rcx, rbx
0x180057a4e  mov     rax, [rax+48h]
0x180057a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a57  mov     edi, eax
0x180057a59  jmp     short loc_180057A39
0x180057a5b  mov     edi, 80041001h
0x180057a60  jmp     short loc_180057A67
0x180057a62  mov     edi, 80004003h
0x180057a67  cmp     rcx, r13
0x180057a6a  jz      short loc_180057A98
0x180057a6c  test    byte ptr [rcx+1Ch], 20h
0x180057a70  jz      short loc_180057A98
0x180057a72  cmp     byte ptr [rcx+19h], 5
0x180057a76  jb      short loc_180057A98
0x180057a78  mov     rcx, [rcx+10h]
0x180057a7c  lea     r9, aCsyncchangeGet_1; "CSyncChange::GetFilteredReplicaLearnedF"...
0x180057a83  mov     edx, 6Dh ; 'm'
0x180057a88  mov     [rsp+58h+var_38], edi
0x180057a8c  lea     r8, WPP_898ee27924ee3465bbd2231b74e1faae_Traceguids
0x180057a93  call    WPP_SF_sD
0x180057a98  mov     rbx, [rsp+58h+arg_0]
0x180057a9d  mov     eax, edi
0x180057a9f  mov     rbp, [rsp+58h+arg_10]
0x180057aa4  add     rsp, 30h
0x180057aa8  pop     r15
0x180057aaa  pop     r14
0x180057aac  pop     r13
0x180057aae  pop     rdi
0x180057aaf  pop     rsi
0x180057ab0  retn
```
