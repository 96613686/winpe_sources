# CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)

- ea: `0x180051360`
- end: `0x18005146e`
- name: `?GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU2@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CSyncChangeBatch *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, unsigned int, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18005022c`
- `0x180051360`

## string_xrefs

- `0x18005139a`: `CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`
- `0x180051445`: `CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeBatch *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        unsigned int a4,
        struct ISyncKnowledge **a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  unsigned int BatchLearnedKnowledgeAfterRecoveryComplete; // eax

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      128,
      WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      "CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a5 )
  {
    if ( *((_DWORD *)this + 36) > a4 )
    {
      if ( *((_DWORD *)this + 39) && !*((_QWORD *)this + 7) && *((_DWORD *)this + 41) == 1 && *((_QWORD *)this + 24) )
      {
        BatchLearnedKnowledgeAfterRecoveryComplete = CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(
                                                       (__int64)this - 56,
                                                       1,
                                                       a2,
                                                       (__int64)a3,
                                                       a4,
                                                       a5);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        v10 = BatchLearnedKnowledgeAfterRecoveryComplete;
      }
      else
      {
        v10 = -2147217407;
      }
    }
    else
    {
      v10 = -2147024809;
    }
  }
  else
  {
    v10 = -2147467261;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      129,
      (unsigned int)WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids,
      (unsigned int)"CSyncChangeBatch::GetLearnedFilterForgottenKnowledgeAfterRecoveryComplete",
      v10);
  return v10;
}

```

## disassembly

```asm
0x180051360  push    rbx
0x180051362  push    rbp
0x180051363  push    rsi
0x180051364  push    rdi
0x180051365  push    r14
0x180051367  sub     rsp, 30h
0x18005136b  mov     esi, r9d
0x18005136e  mov     rbp, r8
0x180051371  mov     rdi, rdx
0x180051374  mov     rbx, rcx
0x180051377  mov     rcx, cs:WPP_GLOBAL_Control
0x18005137e  lea     r14, WPP_GLOBAL_Control
0x180051385  cmp     rcx, r14
0x180051388  jz      short loc_1800513B9
0x18005138a  test    byte ptr [rcx+1Ch], 10h
0x18005138e  jz      short loc_1800513B9
0x180051390  cmp     byte ptr [rcx+19h], 5
0x180051394  jb      short loc_1800513B9
0x180051396  mov     rcx, [rcx+10h]
0x18005139a  lea     r9, aCsyncchangebat_55; "CSyncChangeBatch::GetLearnedFilterForgo"...
0x1800513a1  mov     edx, 80h
0x1800513a6  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x1800513ad  call    WPP_SF_s
0x1800513b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800513b9  xor     edx, edx
0x1800513bb  test    rdi, rdi
0x1800513be  jz      short loc_18005142B
0x1800513c0  mov     rax, [rsp+58h+arg_20]
0x1800513c8  test    rax, rax
0x1800513cb  jz      short loc_18005142B
0x1800513cd  cmp     [rbx+90h], esi
0x1800513d3  ja      short loc_1800513DC
0x1800513d5  mov     ebx, 80070057h
0x1800513da  jmp     short loc_180051430
0x1800513dc  cmp     [rbx+9Ch], edx
0x1800513e2  jz      short loc_180051424
0x1800513e4  cmp     [rbx+38h], rdx
0x1800513e8  jnz     short loc_180051424
0x1800513ea  cmp     dword ptr [rbx+0A4h], 1
0x1800513f1  jnz     short loc_180051424
0x1800513f3  cmp     [rbx+0C0h], rdx
0x1800513fa  jz      short loc_180051424
0x1800513fc  mov     [rsp+58h+var_30], rax
0x180051401  lea     rcx, [rbx-38h]
0x180051405  mov     r9, rbp
0x180051408  mov     [rsp+58h+var_38], esi
0x18005140c  mov     r8, rdi
0x18005140f  mov     edx, 1
0x180051414  call    ?GetBatchLearnedKnowledgeAfterRecoveryComplete@CSyncChangeBatch@@AEAAJW4LK_AFTER_RECOVERY_TYPE@@PEAUISyncKnowledge@@PEAUIEnumItemIds@@KPEAPEAU3@@Z; CSyncChangeBatch::GetBatchLearnedKnowledgeAfterRecoveryComplete(LK_AFTER_RECOVERY_TYPE,ISyncKnowledge *,IEnumItemIds *,ulong,ISyncKnowledge * *)
0x180051419  mov     rcx, cs:WPP_GLOBAL_Control
0x180051420  mov     ebx, eax
0x180051422  jmp     short loc_180051430
0x180051424  mov     ebx, 80041001h
0x180051429  jmp     short loc_180051430
0x18005142b  mov     ebx, 80004003h
0x180051430  cmp     rcx, r14
0x180051433  jz      short loc_180051461
0x180051435  test    byte ptr [rcx+1Ch], 10h
0x180051439  jz      short loc_180051461
0x18005143b  cmp     byte ptr [rcx+19h], 5
0x18005143f  jb      short loc_180051461
0x180051441  mov     rcx, [rcx+10h]
0x180051445  lea     r9, aCsyncchangebat_55; "CSyncChangeBatch::GetLearnedFilterForgo"...
0x18005144c  mov     edx, 81h
0x180051451  mov     [rsp+58h+var_38], ebx
0x180051455  lea     r8, WPP_0cbe0c43e8ab3677caf1ece54d956912_Traceguids
0x18005145c  call    WPP_SF_sD
0x180051461  mov     eax, ebx
0x180051463  add     rsp, 30h
0x180051467  pop     r14
0x180051469  pop     rdi
0x18005146a  pop     rsi
0x18005146b  pop     rbp
0x18005146c  pop     rbx
0x18005146d  retn
```
