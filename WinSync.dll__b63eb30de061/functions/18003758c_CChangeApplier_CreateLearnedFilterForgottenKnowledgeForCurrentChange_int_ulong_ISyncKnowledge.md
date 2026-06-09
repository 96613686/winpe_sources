# CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange(int,ulong,ISyncKnowledge * *)

- ea: `0x18003758c`
- end: `0x180037760`
- name: `?CreateLearnedFilterForgottenKnowledgeForCurrentChange@CChangeApplier@@AEAAJHKPEAPEAUISyncKnowledge@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CChangeApplier *this, __int64, unsigned int, struct ISyncKnowledge **)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180040cd8`
- `0x180041f28`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18001fc38`
- `0x180021bec`
- `0x18002d338`
- `0x18003202c`
- `0x18003758c`
- `0x180069da8`
- `0x18006a71c`
- `0x180094010`

## string_xrefs

- `0x1800375cb`: `CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange`
- `0x18003772e`: `CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange`

## pseudocode

```c
__int64 __fastcall CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange(
        CChangeApplier *this,
        __int64 a2,
        unsigned int a3,
        struct ISyncKnowledge **a4)
{
  int v7; // eax
  int RootItemIdInternal; // edi
  CSyncChangeWrapper *v9; // rcx
  CSyncChangeWrapper *v10; // rcx
  CSyncChangeWrapper *v11; // rcx
  unsigned __int8 *v12; // rbx
  unsigned __int8 *v14; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int8 *v15; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *v16; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      290,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange");
  }
  if ( *((_DWORD *)this + 107) && *((int *)this + 163) <= 0 )
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)(*((_QWORD *)this + 68) + 48LL)
                                                                                              + 88LL))(
           *((_QWORD *)this + 68) + 48LL,
           *((_QWORD *)this + 65),
           *((_QWORD *)this + 33),
           a3,
           a4);
  else
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct ISyncKnowledge **))(*(_QWORD *)(*((_QWORD *)this + 68) + 48LL)
                                                                                              + 64LL))(
           *((_QWORD *)this + 68) + 48LL,
           *((_QWORD *)this + 65),
           *((_QWORD *)this + 33),
           a3,
           a4);
  RootItemIdInternal = v7;
  if ( !v7 )
  {
    v9 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
    v14 = 0;
    RootItemIdInternal = CSyncChangeWrapper::GetRootItemIdInternal(v9, &v14);
    if ( RootItemIdInternal >= 0 )
    {
      v10 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
      v16 = 0;
      RootItemIdInternal = CSyncChangeWrapper::GetWinnerItemIdInternal(v10, &v16);
      if ( RootItemIdInternal >= 0 )
      {
        v11 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
        v15 = 0;
        RootItemIdInternal = CSyncChangeWrapper::GetOriginalItemIdInternal(v11, &v15);
        if ( RootItemIdInternal >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 291, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
          }
          v12 = v15;
          RootItemIdInternal = CChangeApplier::AddExclusionsToKnowledge(this, *a4, v14, v16, v15);
          IdParameters::FreeId(v12);
        }
        IdParameters::FreeId(v16);
      }
    }
    IdParameters::FreeId(v14);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      292,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::CreateLearnedFilterForgottenKnowledgeForCurrentChange",
      RootItemIdInternal);
  }
  return (unsigned int)RootItemIdInternal;
}

```

## disassembly

```asm
0x18003758c  mov     [rsp+arg_8], rbx
0x180037591  mov     [rsp+arg_10], rsi
0x180037596  push    rdi
0x180037597  push    r13
0x180037599  push    r14
0x18003759b  sub     rsp, 40h
0x18003759f  mov     r14, r9
0x1800375a2  mov     ebx, r8d
0x1800375a5  mov     rsi, rcx
0x1800375a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375af  lea     r13, WPP_GLOBAL_Control
0x1800375b6  cmp     rcx, r13
0x1800375b9  jz      short loc_1800375E3
0x1800375bb  test    byte ptr [rcx+1Ch], 8
0x1800375bf  jz      short loc_1800375E3
0x1800375c1  cmp     byte ptr [rcx+19h], 5
0x1800375c5  jb      short loc_1800375E3
0x1800375c7  mov     rcx, [rcx+10h]
0x1800375cb  lea     r9, aCchangeapplier_101; "CChangeApplier::CreateLearnedFilterForg"...
0x1800375d2  mov     edx, 122h
0x1800375d7  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800375de  call    WPP_SF_s
0x1800375e3  cmp     dword ptr [rsi+1ACh], 0
0x1800375ea  jz      short loc_180037609
0x1800375ec  cmp     dword ptr [rsi+28Ch], 0
0x1800375f3  jg      short loc_180037609
0x1800375f5  mov     rcx, [rsi+220h]
0x1800375fc  add     rcx, 30h ; '0'
0x180037600  mov     rax, [rcx]
0x180037603  mov     rax, [rax+58h]
0x180037607  jmp     short loc_18003761B
0x180037609  mov     rcx, [rsi+220h]
0x180037610  add     rcx, 30h ; '0'
0x180037614  mov     rax, [rcx]
0x180037617  mov     rax, [rax+40h]
0x18003761b  mov     r8, [rsi+108h]
0x180037622  mov     r9d, ebx
0x180037625  mov     rdx, [rsi+208h]
0x18003762c  mov     [rsp+58h+var_38], r14
0x180037631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037636  mov     edi, eax
0x180037638  test    eax, eax
0x18003763a  jnz     loc_180037712
0x180037640  mov     rcx, [rsi+220h]; this
0x180037647  lea     rdx, [rsp+58h+var_28]; unsigned __int8 **
0x18003764c  mov     [rsp+58h+var_28], 0
0x180037655  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x18003765a  mov     edi, eax
0x18003765c  test    eax, eax
0x18003765e  js      loc_180037708
0x180037664  mov     rcx, [rsi+220h]; this
0x18003766b  lea     rdx, [rsp+58h+arg_0]; unsigned __int8 **
0x180037670  mov     [rsp+58h+arg_0], 0
0x180037679  call    ?GetWinnerItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetWinnerItemIdInternal(uchar * *)
0x18003767e  mov     edi, eax
0x180037680  test    eax, eax
0x180037682  js      loc_180037708
0x180037688  mov     rcx, [rsi+220h]; this
0x18003768f  lea     rdx, [rsp+58h+var_20]; unsigned __int8 **
0x180037694  mov     [rsp+58h+var_20], 0
0x18003769d  call    ?GetOriginalItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetOriginalItemIdInternal(uchar * *)
0x1800376a2  mov     edi, eax
0x1800376a4  test    eax, eax
0x1800376a6  js      short loc_1800376FE
0x1800376a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376af  cmp     rcx, r13
0x1800376b2  jz      short loc_1800376D5
0x1800376b4  test    byte ptr [rcx+1Ch], 8
0x1800376b8  jz      short loc_1800376D5
0x1800376ba  cmp     byte ptr [rcx+19h], 5
0x1800376be  jb      short loc_1800376D5
0x1800376c0  mov     rcx, [rcx+10h]
0x1800376c4  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800376cb  mov     edx, 123h
0x1800376d0  call    WPP_SF_
0x1800376d5  mov     rbx, [rsp+58h+var_20]
0x1800376da  mov     rcx, rsi; this
0x1800376dd  mov     r9, [rsp+58h+arg_0]; unsigned __int8 *
0x1800376e2  mov     r8, [rsp+58h+var_28]; unsigned __int8 *
0x1800376e7  mov     rdx, [r14]; struct ISyncKnowledge *
0x1800376ea  mov     [rsp+58h+var_38], rbx; unsigned __int8 *
0x1800376ef  call    ?AddExclusionsToKnowledge@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAE11@Z; CChangeApplier::AddExclusionsToKnowledge(ISyncKnowledge *,uchar *,uchar *,uchar *)
0x1800376f4  mov     rcx, rbx; unsigned __int8 *
0x1800376f7  mov     edi, eax
0x1800376f9  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x1800376fe  mov     rcx, [rsp+58h+arg_0]; unsigned __int8 *
0x180037703  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180037708  mov     rcx, [rsp+58h+var_28]; unsigned __int8 *
0x18003770d  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180037712  mov     rcx, cs:WPP_GLOBAL_Control
0x180037719  cmp     rcx, r13
0x18003771c  jz      short loc_18003774A
0x18003771e  test    byte ptr [rcx+1Ch], 8
0x180037722  jz      short loc_18003774A
0x180037724  cmp     byte ptr [rcx+19h], 5
0x180037728  jb      short loc_18003774A
0x18003772a  mov     rcx, [rcx+10h]
0x18003772e  lea     r9, aCchangeapplier_101; "CChangeApplier::CreateLearnedFilterForg"...
0x180037735  mov     edx, 124h
0x18003773a  mov     dword ptr [rsp+58h+var_38], edi
0x18003773e  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037745  call    WPP_SF_sD
0x18003774a  mov     rbx, [rsp+58h+arg_8]
0x18003774f  mov     eax, edi
0x180037751  mov     rsi, [rsp+58h+arg_10]
0x180037756  add     rsp, 40h
0x18003775a  pop     r14
0x18003775c  pop     r13
0x18003775e  pop     rdi
0x18003775f  retn
```
