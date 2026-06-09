# CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)

- ea: `0x180068fb0`
- end: `0x1800690fc`
- name: `?GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete@CSyncChangeWrapper@@UEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z`
- size: `332`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *this, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180068fb0`
- `0x180069364`
- `0x180094010`

## string_xrefs

- `0x180068ff1`: `CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`
- `0x1800690cb`: `CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeWrapper *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        struct ISyncKnowledge **a4)
{
  PVOID *v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      187,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a4 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
    if ( v9 )
    {
      v13 = 0;
      v10 = (**v9)(v9, &GUID_bfe1ef00_e87d_42fd_a4e9_242d70414aef, &v13);
      v11 = v10;
      if ( v10 == -2147467262 )
      {
        v11 = -2147217379;
      }
      else if ( !v10 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **))(*(_QWORD *)v13 + 80LL))(
                v13,
                a2,
                a3,
                a4);
      }
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    else
    {
      v11 = CSyncChangeWrapper::GetKnowledgeProjectedToItemAndRelevantChangeUnits(
              (CSyncChangeWrapper *)((char *)this - 48),
              *((struct ISyncKnowledge **)this + 39),
              a4);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      188,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete",
      v11);
  return v11;
}

```

## disassembly

```asm
0x180068fb0  mov     [rsp+arg_0], rbx
0x180068fb5  mov     [rsp+arg_10], rbp
0x180068fba  push    rsi
0x180068fbb  push    rdi
0x180068fbc  push    r14
0x180068fbe  sub     rsp, 30h
0x180068fc2  mov     rdi, r9
0x180068fc5  mov     rbp, r8
0x180068fc8  mov     rsi, rdx
0x180068fcb  mov     rbx, rcx
0x180068fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180068fd5  lea     r14, WPP_GLOBAL_Control
0x180068fdc  cmp     rcx, r14
0x180068fdf  jz      short loc_180069010
0x180068fe1  test    byte ptr [rcx+1Ch], 8
0x180068fe5  jz      short loc_180069010
0x180068fe7  cmp     byte ptr [rcx+19h], 5
0x180068feb  jb      short loc_180069010
0x180068fed  mov     rcx, [rcx+10h]
0x180068ff1  lea     r9, aCsyncchangewra_22; "CSyncChangeWrapper::GetFilteredReplicaL"...
0x180068ff8  mov     edx, 0BBh
0x180068ffd  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180069004  call    WPP_SF_s
0x180069009  mov     rcx, cs:WPP_GLOBAL_Control
0x180069010  test    rsi, rsi
0x180069013  jz      loc_1800690B1
0x180069019  test    rdi, rdi
0x18006901c  jz      loc_1800690B1
0x180069022  mov     rcx, [rbx+10h]
0x180069026  test    rcx, rcx
0x180069029  jz      short loc_18006909A
0x18006902b  mov     [rsp+48h+arg_8], 0
0x180069034  lea     r8, [rsp+48h+arg_8]
0x180069039  mov     rax, [rcx]
0x18006903c  lea     rdx, _GUID_bfe1ef00_e87d_42fd_a4e9_242d70414aef
0x180069043  mov     rax, [rax]
0x180069046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006904b  mov     ebx, eax
0x18006904d  cmp     eax, 80004002h
0x180069052  jnz     short loc_18006905B
0x180069054  mov     ebx, 8004101Dh
0x180069059  jmp     short loc_18006907B
0x18006905b  test    eax, eax
0x18006905d  jnz     short loc_18006907B
0x18006905f  mov     rcx, [rsp+48h+arg_8]
0x180069064  mov     r9, rdi
0x180069067  mov     r8, rbp
0x18006906a  mov     rdx, rsi
0x18006906d  mov     rax, [rcx]
0x180069070  mov     rax, [rax+50h]
0x180069074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069079  mov     ebx, eax
0x18006907b  mov     rcx, [rsp+48h+arg_8]
0x180069080  test    rcx, rcx
0x180069083  jz      short loc_180069091
0x180069085  mov     rax, [rcx]
0x180069088  mov     rax, [rax+10h]
0x18006908c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069091  mov     rcx, cs:WPP_GLOBAL_Control
0x180069098  jmp     short loc_1800690B6
0x18006909a  mov     rdx, [rbx+138h]; struct ISyncKnowledge *
0x1800690a1  lea     rcx, [rbx-30h]; this
0x1800690a5  mov     r8, rdi; struct ISyncKnowledge **
0x1800690a8  call    ?GetKnowledgeProjectedToItemAndRelevantChangeUnits@CSyncChangeWrapper@@QEAAJPEAUISyncKnowledge@@PEAPEAU2@@Z; CSyncChangeWrapper::GetKnowledgeProjectedToItemAndRelevantChangeUnits(ISyncKnowledge *,ISyncKnowledge * *)
0x1800690ad  mov     ebx, eax
0x1800690af  jmp     short loc_180069091
0x1800690b1  mov     ebx, 80004003h
0x1800690b6  cmp     rcx, r14
0x1800690b9  jz      short loc_1800690E7
0x1800690bb  test    byte ptr [rcx+1Ch], 8
0x1800690bf  jz      short loc_1800690E7
0x1800690c1  cmp     byte ptr [rcx+19h], 5
0x1800690c5  jb      short loc_1800690E7
0x1800690c7  mov     rcx, [rcx+10h]
0x1800690cb  lea     r9, aCsyncchangewra_22; "CSyncChangeWrapper::GetFilteredReplicaL"...
0x1800690d2  mov     edx, 0BCh
0x1800690d7  mov     [rsp+48h+var_28], ebx
0x1800690db  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x1800690e2  call    WPP_SF_sD
0x1800690e7  mov     rbp, [rsp+48h+arg_10]
0x1800690ec  mov     eax, ebx
0x1800690ee  mov     rbx, [rsp+48h+arg_0]
0x1800690f3  add     rsp, 30h
0x1800690f7  pop     r14
0x1800690f9  pop     rdi
0x1800690fa  pop     rsi
0x1800690fb  retn
```
