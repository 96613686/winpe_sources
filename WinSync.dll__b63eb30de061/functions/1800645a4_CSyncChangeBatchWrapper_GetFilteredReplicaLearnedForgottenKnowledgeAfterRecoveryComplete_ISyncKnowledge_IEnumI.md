# CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)

- ea: `0x1800645a4`
- end: `0x1800646b7`
- name: `?GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CSyncChangeBatchWrapper *__hidden this, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180037768`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800645a4`
- `0x180094010`

## string_xrefs

- `0x1800645e5`: `CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`
- `0x180064686`: `CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete`

## pseudocode

```c
__int64 __fastcall CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(
        CSyncChangeBatchWrapper *this,
        struct ISyncKnowledge *a2,
        struct IEnumItemIds *a3,
        struct ISyncKnowledge **a4)
{
  PVOID *v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // r9
  unsigned int v10; // ebx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      WPP_238472b3224e399257624831508c69ba_Traceguids,
      "CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v9 )
  {
    v12 = 0;
    v10 = (**v9)(v9, &GUID_de247002_566d_459a_a6ed_a5aab3459fb7, &v12);
    if ( !v10 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge *, struct IEnumItemIds *, struct ISyncKnowledge **))(*(_QWORD *)v12 + 72LL))(
              v12,
              a2,
              a3,
              a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v10 = -2147217379;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      56,
      (unsigned int)WPP_238472b3224e399257624831508c69ba_Traceguids,
      (unsigned int)"CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete",
      v10);
  return v10;
}

```

## disassembly

```asm
0x1800645a4  mov     [rsp+arg_8], rbx
0x1800645a9  mov     [rsp+arg_10], rbp
0x1800645ae  push    rsi
0x1800645af  push    rdi
0x1800645b0  push    r14
0x1800645b2  sub     rsp, 30h
0x1800645b6  mov     rdi, r9
0x1800645b9  mov     rsi, r8
0x1800645bc  mov     rbp, rdx
0x1800645bf  mov     rbx, rcx
0x1800645c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800645c9  lea     r14, WPP_GLOBAL_Control
0x1800645d0  cmp     rcx, r14
0x1800645d3  jz      short loc_180064604
0x1800645d5  test    byte ptr [rcx+1Ch], 8
0x1800645d9  jz      short loc_180064604
0x1800645db  cmp     byte ptr [rcx+19h], 5
0x1800645df  jb      short loc_180064604
0x1800645e1  mov     rcx, [rcx+10h]
0x1800645e5  lea     r9, aCsyncchangebat_36; "CSyncChangeBatchWrapper::GetFilteredRep"...
0x1800645ec  mov     edx, 37h ; '7'
0x1800645f1  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x1800645f8  call    WPP_SF_s
0x1800645fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180064604  mov     r9, [rbx+28h]
0x180064608  test    r9, r9
0x18006460b  jnz     short loc_180064614
0x18006460d  mov     ebx, 8004101Dh
0x180064612  jmp     short loc_180064671
0x180064614  mov     [rsp+48h+arg_0], 0
0x18006461d  lea     r8, [rsp+48h+arg_0]
0x180064622  mov     rax, [r9]
0x180064625  lea     rdx, _GUID_de247002_566d_459a_a6ed_a5aab3459fb7
0x18006462c  mov     rcx, r9
0x18006462f  mov     rax, [rax]
0x180064632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064637  mov     ebx, eax
0x180064639  test    eax, eax
0x18006463b  jnz     short loc_18006466A
0x18006463d  mov     rcx, [rsp+48h+arg_0]
0x180064642  mov     r9, rdi
0x180064645  mov     r8, rsi
0x180064648  mov     rdx, rbp
0x18006464b  mov     rax, [rcx]
0x18006464e  mov     rax, [rax+48h]
0x180064652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064657  mov     rcx, [rsp+48h+arg_0]
0x18006465c  mov     ebx, eax
0x18006465e  mov     rax, [rcx]
0x180064661  mov     rax, [rax+10h]
0x180064665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006466a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064671  cmp     rcx, r14
0x180064674  jz      short loc_1800646A2
0x180064676  test    byte ptr [rcx+1Ch], 8
0x18006467a  jz      short loc_1800646A2
0x18006467c  cmp     byte ptr [rcx+19h], 5
0x180064680  jb      short loc_1800646A2
0x180064682  mov     rcx, [rcx+10h]
0x180064686  lea     r9, aCsyncchangebat_36; "CSyncChangeBatchWrapper::GetFilteredRep"...
0x18006468d  mov     edx, 38h ; '8'
0x180064692  mov     [rsp+48h+var_28], ebx
0x180064696  lea     r8, WPP_238472b3224e399257624831508c69ba_Traceguids
0x18006469d  call    WPP_SF_sD
0x1800646a2  mov     rbp, [rsp+48h+arg_10]
0x1800646a7  mov     eax, ebx
0x1800646a9  mov     rbx, [rsp+48h+arg_8]
0x1800646ae  add     rsp, 30h
0x1800646b2  pop     r14
0x1800646b4  pop     rdi
0x1800646b5  pop     rsi
0x1800646b6  retn
```
