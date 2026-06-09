# CChangeApplier::CreateLearnedForgottenKnowledge(int,IForgottenKnowledge * *)

- ea: `0x180037768`
- end: `0x180037a50`
- name: `?CreateLearnedForgottenKnowledge@CChangeApplier@@AEAAJHPEAPEAUIForgottenKnowledge@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, int, struct IForgottenKnowledge **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180039948`
- `0x180040cd8`
- `0x180041f28`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002d338`
- `0x18003202c`
- `0x180037768`
- `0x180064488`
- `0x1800645a4`
- `0x180064c98`
- `0x180094010`

## string_xrefs

- `0x1800377a8`: `CChangeApplier::CreateLearnedForgottenKnowledge`
- `0x180037a1f`: `CChangeApplier::CreateLearnedForgottenKnowledge`

## pseudocode

```c
__int64 __fastcall CChangeApplier::CreateLearnedForgottenKnowledge(
        CChangeApplier *this,
        int a2,
        struct IForgottenKnowledge **a3)
{
  bool v6; // zf
  int LearnedForgottenKnowledge; // eax
  int v8; // ebx
  int v9; // eax
  int FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete; // eax
  struct ISyncKnowledge *v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  struct ISyncKnowledge *v15; // [rsp+60h] [rbp+20h] BYREF
  struct ISyncKnowledge *v16; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      293,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::CreateLearnedForgottenKnowledge");
  }
  v6 = *((_QWORD *)this + 26) == 0;
  v15 = 0;
  if ( v6 )
  {
    if ( a2 )
      LearnedForgottenKnowledge = CSyncChangeBatchWrapper::GetLearnedForgottenKnowledge(
                                    *((CSyncChangeBatchWrapper **)this + 62),
                                    (struct IForgottenKnowledge **)&v15);
    else
      LearnedForgottenKnowledge = (*(__int64 (__fastcall **)(__int64, struct ISyncKnowledge **))(*(_QWORD *)(*((_QWORD *)this + 68) + 24LL)
                                                                                               + 32LL))(
                                    *((_QWORD *)this + 68) + 24LL,
                                    &v15);
    v8 = LearnedForgottenKnowledge;
  }
  else
  {
    v9 = *((_DWORD *)this + 107);
    v16 = 0;
    if ( a2 )
    {
      if ( v9 && *((int *)this + 163) <= 0 )
        FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete = CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(
                                                                          *((CSyncChangeBatchWrapper **)this + 62),
                                                                          *((struct ISyncKnowledge **)this + 65),
                                                                          *((struct IEnumItemIds **)this + 33),
                                                                          &v16);
      else
        FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete = CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledge(
                                                                          *((CSyncChangeBatchWrapper **)this + 62),
                                                                          *((struct ISyncKnowledge **)this + 65),
                                                                          *((struct IEnumItemIds **)this + 33),
                                                                          &v16);
    }
    else if ( v9 && *((int *)this + 163) <= 0 )
    {
      FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)(*((_QWORD *)this + 68) + 48LL) + 80LL))(
                                                                        *((_QWORD *)this + 68) + 48LL,
                                                                        *((_QWORD *)this + 65),
                                                                        *((_QWORD *)this + 33),
                                                                        &v16);
    }
    else
    {
      FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)(*((_QWORD *)this + 68) + 48LL) + 72LL))(
                                                                        *((_QWORD *)this + 68) + 48LL,
                                                                        *((_QWORD *)this + 65),
                                                                        *((_QWORD *)this + 33),
                                                                        &v16);
    }
    v8 = FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete;
    if ( FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete )
    {
      if ( FilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete == 1 )
        v8 = 0;
    }
    else
    {
      v8 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, struct ISyncKnowledge **))v16->lpVtbl->QueryInterface)(
             v16,
             &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
             &v15);
    }
    if ( v16 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v16->lpVtbl->Release)(v16);
  }
  v11 = v15;
  if ( v15 )
  {
    if ( v8 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
        v11 = v15;
      }
      v8 = CChangeApplier::AddExclusionsToKnowledge(this, v11, 0, 0, 0);
      if ( v8 >= 0 )
      {
        v14 = 0;
        v8 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, __int64 *))v15->lpVtbl->QueryInterface)(
               v15,
               &GUID_615bbb53_c945_4203_bf4b_2cb65919a0aa,
               &v14);
        if ( v8 >= 0 )
        {
          v12 = *((_QWORD *)this + 64);
          v16 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, struct ISyncKnowledge **))(*(_QWORD *)v12 + 96LL))(
                 v12,
                 v14,
                 &v16);
          if ( v8 >= 0 )
          {
            v8 = ((__int64 (__fastcall *)(struct ISyncKnowledge *, GUID *, struct IForgottenKnowledge **))v16->lpVtbl->QueryInterface)(
                   v16,
                   &GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2,
                   a3);
            ((void (__fastcall *)(struct ISyncKnowledge *))v16->lpVtbl->Release)(v16);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      v11 = v15;
    }
  }
  else
  {
    *a3 = 0;
  }
  if ( v11 )
    ((void (__fastcall *)(struct ISyncKnowledge *))v11->lpVtbl->Release)(v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      295,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::CreateLearnedForgottenKnowledge",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037768  mov     [rsp-18h+arg_8], rbx
0x18003776d  mov     [rsp-18h+arg_10], rsi
0x180037772  push    rbp
0x180037773  push    rdi
0x180037774  push    r13
0x180037776  mov     rbp, rsp
0x180037779  sub     rsp, 40h
0x18003777d  mov     rsi, r8
0x180037780  mov     ebx, edx
0x180037782  mov     rdi, rcx
0x180037785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003778c  lea     r13, WPP_GLOBAL_Control
0x180037793  cmp     rcx, r13
0x180037796  jz      short loc_1800377C0
0x180037798  test    byte ptr [rcx+1Ch], 8
0x18003779c  jz      short loc_1800377C0
0x18003779e  cmp     byte ptr [rcx+19h], 5
0x1800377a2  jb      short loc_1800377C0
0x1800377a4  mov     rcx, [rcx+10h]
0x1800377a8  lea     r9, aCchangeapplier_83; "CChangeApplier::CreateLearnedForgottenK"...
0x1800377af  mov     edx, 125h
0x1800377b4  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800377bb  call    WPP_SF_s
0x1800377c0  cmp     qword ptr [rdi+0D0h], 0
0x1800377c8  mov     [rbp+arg_0], 0
0x1800377d0  jnz     short loc_180037806
0x1800377d2  lea     rdx, [rbp+arg_0]; struct IForgottenKnowledge **
0x1800377d6  test    ebx, ebx
0x1800377d8  jnz     short loc_1800377F3
0x1800377da  mov     rcx, [rdi+220h]
0x1800377e1  add     rcx, 18h
0x1800377e5  mov     rax, [rcx]
0x1800377e8  mov     rax, [rax+20h]
0x1800377ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377f1  jmp     short loc_1800377FF
0x1800377f3  mov     rcx, [rdi+1F0h]; this
0x1800377fa  call    ?GetLearnedForgottenKnowledge@CSyncChangeBatchWrapper@@QEAAJPEAPEAUIForgottenKnowledge@@@Z; CSyncChangeBatchWrapper::GetLearnedForgottenKnowledge(IForgottenKnowledge * *)
0x1800377ff  mov     ebx, eax
0x180037801  jmp     loc_1800378EF
0x180037806  mov     eax, [rdi+1ACh]
0x18003780c  mov     [rbp+arg_18], 0
0x180037814  test    ebx, ebx
0x180037816  jnz     short loc_180037863
0x180037818  test    eax, eax
0x18003781a  jz      short loc_18003784F
0x18003781c  cmp     [rdi+28Ch], ebx
0x180037822  jg      short loc_18003784F
0x180037824  mov     rcx, [rdi+220h]
0x18003782b  add     rcx, 30h ; '0'
0x18003782f  mov     rax, [rcx]
0x180037832  mov     rax, [rax+50h]
0x180037836  mov     rdx, [rdi+208h]
0x18003783d  lea     r9, [rbp+arg_18]
0x180037841  mov     r8, [rdi+108h]
0x180037848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003784d  jmp     short loc_1800378AE
0x18003784f  mov     rcx, [rdi+220h]
0x180037856  add     rcx, 30h ; '0'
0x18003785a  mov     rax, [rcx]
0x18003785d  mov     rax, [rax+48h]
0x180037861  jmp     short loc_180037836
0x180037863  test    eax, eax
0x180037865  jz      short loc_180037890
0x180037867  cmp     dword ptr [rdi+28Ch], 0
0x18003786e  jg      short loc_180037890
0x180037870  mov     r8, [rdi+108h]; struct IEnumItemIds *
0x180037877  lea     r9, [rbp+arg_18]; struct ISyncKnowledge **
0x18003787b  mov     rdx, [rdi+208h]; struct ISyncKnowledge *
0x180037882  mov     rcx, [rdi+1F0h]; this
0x180037889  call    ?GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z; CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledgeAfterRecoveryComplete(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)
0x18003788e  jmp     short loc_1800378AE
0x180037890  mov     r8, [rdi+108h]; struct IEnumItemIds *
0x180037897  lea     r9, [rbp+arg_18]; struct ISyncKnowledge **
0x18003789b  mov     rdx, [rdi+208h]; struct ISyncKnowledge *
0x1800378a2  mov     rcx, [rdi+1F0h]; this
0x1800378a9  call    ?GetFilteredReplicaLearnedForgottenKnowledge@CSyncChangeBatchWrapper@@QEAAJPEAUISyncKnowledge@@PEAUIEnumItemIds@@PEAPEAU2@@Z; CSyncChangeBatchWrapper::GetFilteredReplicaLearnedForgottenKnowledge(ISyncKnowledge *,IEnumItemIds *,ISyncKnowledge * *)
0x1800378ae  mov     ebx, eax
0x1800378b0  test    eax, eax
0x1800378b2  jnz     short loc_1800378D2
0x1800378b4  mov     rcx, [rbp+arg_18]
0x1800378b8  lea     r8, [rbp+arg_0]
0x1800378bc  lea     rdx, _GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2
0x1800378c3  mov     rax, [rcx]
0x1800378c6  mov     rax, [rax]
0x1800378c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378ce  mov     ebx, eax
0x1800378d0  jmp     short loc_1800378DA
0x1800378d2  xor     eax, eax
0x1800378d4  cmp     ebx, 1
0x1800378d7  cmovz   ebx, eax
0x1800378da  mov     rcx, [rbp+arg_18]
0x1800378de  test    rcx, rcx
0x1800378e1  jz      short loc_1800378EF
0x1800378e3  mov     rax, [rcx]
0x1800378e6  mov     rax, [rax+10h]
0x1800378ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378ef  mov     rcx, [rbp+arg_0]
0x1800378f3  test    rcx, rcx
0x1800378f6  jz      loc_1800379EB
0x1800378fc  test    ebx, ebx
0x1800378fe  js      loc_1800379F2
0x180037904  mov     rax, cs:WPP_GLOBAL_Control
0x18003790b  cmp     rax, r13
0x18003790e  jz      short loc_180037935
0x180037910  test    byte ptr [rax+1Ch], 8
0x180037914  jz      short loc_180037935
0x180037916  cmp     byte ptr [rax+19h], 5
0x18003791a  jb      short loc_180037935
0x18003791c  mov     rcx, [rax+10h]
0x180037920  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037927  mov     edx, 126h
0x18003792c  call    WPP_SF_
0x180037931  mov     rcx, [rbp+arg_0]
0x180037935  mov     rdx, rcx; struct ISyncKnowledge *
0x180037938  mov     [rsp+40h+var_20], 0; unsigned __int8 *
0x180037941  mov     rcx, rdi; this
0x180037944  xor     r9d, r9d; unsigned __int8 *
0x180037947  xor     r8d, r8d; unsigned __int8 *
0x18003794a  call    ?AddExclusionsToKnowledge@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAE11@Z; CChangeApplier::AddExclusionsToKnowledge(ISyncKnowledge *,uchar *,uchar *,uchar *)
0x18003794f  mov     ebx, eax
0x180037951  test    eax, eax
0x180037953  js      loc_1800379E5
0x180037959  mov     rcx, [rbp+arg_0]
0x18003795d  lea     r8, [rbp+var_10]
0x180037961  mov     [rbp+var_10], 0
0x180037969  lea     rdx, _GUID_615bbb53_c945_4203_bf4b_2cb65919a0aa
0x180037970  mov     rax, [rcx]
0x180037973  mov     rax, [rax]
0x180037976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003797b  mov     ebx, eax
0x18003797d  test    eax, eax
0x18003797f  js      short loc_1800379E5
0x180037981  mov     rcx, [rdi+200h]
0x180037988  lea     r8, [rbp+arg_18]
0x18003798c  mov     rdx, [rbp+var_10]
0x180037990  mov     [rbp+arg_18], 0
0x180037998  mov     rax, [rcx]
0x18003799b  mov     rax, [rax+60h]
0x18003799f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379a4  mov     ebx, eax
0x1800379a6  test    eax, eax
0x1800379a8  js      short loc_1800379D5
0x1800379aa  mov     rcx, [rbp+arg_18]
0x1800379ae  lea     rdx, _GUID_456e0f96_6036_452b_9f9d_bcc4b4a85db2
0x1800379b5  mov     r8, rsi
0x1800379b8  mov     rax, [rcx]
0x1800379bb  mov     rax, [rax]
0x1800379be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379c3  mov     rcx, [rbp+arg_18]
0x1800379c7  mov     ebx, eax
0x1800379c9  mov     rax, [rcx]
0x1800379cc  mov     rax, [rax+10h]
0x1800379d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379d5  mov     rcx, [rbp+var_10]
0x1800379d9  mov     rax, [rcx]
0x1800379dc  mov     rax, [rax+10h]
0x1800379e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379e5  mov     rcx, [rbp+arg_0]
0x1800379e9  jmp     short loc_1800379F2
0x1800379eb  mov     qword ptr [rsi], 0
0x1800379f2  test    rcx, rcx
0x1800379f5  jz      short loc_180037A03
0x1800379f7  mov     rax, [rcx]
0x1800379fa  mov     rax, [rax+10h]
0x1800379fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a0a  cmp     rcx, r13
0x180037a0d  jz      short loc_180037A3B
0x180037a0f  test    byte ptr [rcx+1Ch], 8
0x180037a13  jz      short loc_180037A3B
0x180037a15  cmp     byte ptr [rcx+19h], 5
0x180037a19  jb      short loc_180037A3B
0x180037a1b  mov     rcx, [rcx+10h]
0x180037a1f  lea     r9, aCchangeapplier_83; "CChangeApplier::CreateLearnedForgottenK"...
0x180037a26  mov     edx, 127h
0x180037a2b  mov     dword ptr [rsp+40h+var_20], ebx
0x180037a2f  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037a36  call    WPP_SF_sD
0x180037a3b  mov     rsi, [rsp+40h+arg_10]
0x180037a40  mov     eax, ebx
0x180037a42  mov     rbx, [rsp+40h+arg_8]
0x180037a47  add     rsp, 40h
0x180037a4b  pop     r13
0x180037a4d  pop     rdi
0x180037a4e  pop     rbp
0x180037a4f  retn
```
