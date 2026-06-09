# CChangeApplier::CreateLearnedKnowledgeForCurrentChange(int,ISyncKnowledge * *)

- ea: `0x180037a58`
- end: `0x180037ca8`
- name: `?CreateLearnedKnowledgeForCurrentChange@CChangeApplier@@AEAAJHPEAPEAUISyncKnowledge@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, int, struct ISyncKnowledge **)`
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
- `0x180037a58`
- `0x180069da8`
- `0x18006a71c`
- `0x180094010`

## string_xrefs

- `0x180037a97`: `CChangeApplier::CreateLearnedKnowledgeForCurrentChange`
- `0x180037c79`: `CChangeApplier::CreateLearnedKnowledgeForCurrentChange`

## pseudocode

```c
__int64 __fastcall CChangeApplier::CreateLearnedKnowledgeForCurrentChange(
        CChangeApplier *this,
        int a2,
        struct ISyncKnowledge **a3)
{
  PVOID *v6; // rcx
  int WinnerItemIdInternal; // ebx
  bool v8; // zf
  _QWORD *v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  unsigned __int8 *v12; // rsi
  int RootItemIdInternal; // eax
  CSyncChangeWrapper *v14; // rcx
  CSyncChangeWrapper *v15; // rcx
  struct ISyncKnowledge *v16; // rdx
  unsigned __int8 *v17; // r14
  unsigned __int8 *v19; // [rsp+30h] [rbp-10h] BYREF
  struct ISyncKnowledge *v20; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int8 *v21; // [rsp+88h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      287,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::CreateLearnedKnowledgeForCurrentChange");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  WinnerItemIdInternal = -2147467261;
  if ( a3 )
  {
    v8 = *((_DWORD *)this + 107) == 0;
    v9 = (_QWORD *)*((_QWORD *)this + 68);
    v20 = 0;
    if ( v8 )
    {
      v11 = *((_QWORD *)this + 65);
      if ( *((_QWORD *)this + 26) )
        v10 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD, struct ISyncKnowledge **))(v9[6] + 56LL))(
                v9 + 6,
                v11,
                *((_QWORD *)this + 33),
                &v20);
      else
        v10 = (*(__int64 (__fastcall **)(_QWORD *, __int64, struct ISyncKnowledge **))(v9[2] + 32LL))(v9 + 2, v11, &v20);
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD *, struct ISyncKnowledge **))(v9[3] + 24LL))(v9 + 3, &v20);
    }
    WinnerItemIdInternal = v10;
    if ( v10 >= 0 )
    {
      v12 = 0;
      v21 = 0;
      if ( !a2
        || (RootItemIdInternal = CSyncChangeWrapper::GetRootItemIdInternal(*((CSyncChangeWrapper **)this + 68), &v21),
            v12 = v21,
            WinnerItemIdInternal = RootItemIdInternal,
            RootItemIdInternal >= 0) )
      {
        v14 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
        v21 = 0;
        WinnerItemIdInternal = CSyncChangeWrapper::GetWinnerItemIdInternal(v14, &v21);
        if ( WinnerItemIdInternal >= 0 )
        {
          v15 = (CSyncChangeWrapper *)*((_QWORD *)this + 68);
          v19 = 0;
          WinnerItemIdInternal = CSyncChangeWrapper::GetOriginalItemIdInternal(v15, &v19);
          if ( WinnerItemIdInternal >= 0 )
          {
            v16 = v20;
            v17 = v19;
            if ( v20 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids);
                v16 = v20;
              }
              WinnerItemIdInternal = CChangeApplier::AddExclusionsToKnowledge(this, v16, v12, v21, v17);
              if ( WinnerItemIdInternal >= 0 )
              {
                ((void (__fastcall *)(struct ISyncKnowledge *))v20->lpVtbl->AddRef)(v20);
                *a3 = v20;
              }
            }
            else
            {
              WinnerItemIdInternal = -2147217379;
            }
            IdParameters::FreeId(v17);
          }
          IdParameters::FreeId(v21);
        }
      }
      IdParameters::FreeId(v12);
    }
    if ( v20 )
      ((void (__fastcall *)(struct ISyncKnowledge *))v20->lpVtbl->Release)(v20);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      289,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::CreateLearnedKnowledgeForCurrentChange",
      WinnerItemIdInternal);
  return (unsigned int)WinnerItemIdInternal;
}

```

## disassembly

```asm
0x180037a58  mov     [rsp-28h+arg_0], rbx
0x180037a5d  push    rbp
0x180037a5e  push    rsi
0x180037a5f  push    rdi
0x180037a60  push    r14
0x180037a62  push    r15
0x180037a64  mov     rbp, rsp
0x180037a67  sub     rsp, 40h
0x180037a6b  mov     r15, r8
0x180037a6e  mov     r14d, edx
0x180037a71  mov     rdi, rcx
0x180037a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a7b  lea     rsi, WPP_GLOBAL_Control
0x180037a82  cmp     rcx, rsi
0x180037a85  jz      short loc_180037AB6
0x180037a87  test    byte ptr [rcx+1Ch], 8
0x180037a8b  jz      short loc_180037AB6
0x180037a8d  cmp     byte ptr [rcx+19h], 5
0x180037a91  jb      short loc_180037AB6
0x180037a93  mov     rcx, [rcx+10h]
0x180037a97  lea     r9, aCchangeapplier_89; "CChangeApplier::CreateLearnedKnowledgeF"...
0x180037a9e  mov     edx, 11Fh
0x180037aa3  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037aaa  call    WPP_SF_s
0x180037aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ab6  mov     ebx, 80004003h
0x180037abb  test    r15, r15
0x180037abe  jz      loc_180037C64
0x180037ac4  cmp     dword ptr [rdi+1ACh], 0
0x180037acb  mov     rcx, [rdi+220h]
0x180037ad2  mov     [rbp+arg_10], 0
0x180037ada  jz      short loc_180037AF2
0x180037adc  add     rcx, 18h
0x180037ae0  lea     rdx, [rbp+arg_10]
0x180037ae4  mov     rax, [rcx]
0x180037ae7  mov     rax, [rax+18h]
0x180037aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037af0  jmp     short loc_180037B34
0x180037af2  cmp     qword ptr [rdi+0D0h], 0
0x180037afa  mov     rdx, [rdi+208h]
0x180037b01  jnz     short loc_180037B19
0x180037b03  add     rcx, 10h
0x180037b07  lea     r8, [rbp+arg_10]
0x180037b0b  mov     rax, [rcx]
0x180037b0e  mov     rax, [rax+20h]
0x180037b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b17  jmp     short loc_180037B34
0x180037b19  mov     r8, [rdi+108h]
0x180037b20  lea     r9, [rbp+arg_10]
0x180037b24  add     rcx, 30h ; '0'
0x180037b28  mov     rax, [rcx]
0x180037b2b  mov     rax, [rax+38h]
0x180037b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b34  mov     ebx, eax
0x180037b36  test    eax, eax
0x180037b38  js      loc_180037C48
0x180037b3e  xor     esi, esi
0x180037b40  mov     [rbp+arg_18], rsi
0x180037b44  test    r14d, r14d
0x180037b47  jz      short loc_180037B67
0x180037b49  mov     rcx, [rdi+220h]; this
0x180037b50  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180037b54  call    ?GetRootItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetRootItemIdInternal(uchar * *)
0x180037b59  mov     rsi, [rbp+arg_18]
0x180037b5d  mov     ebx, eax
0x180037b5f  test    eax, eax
0x180037b61  js      loc_180037C39
0x180037b67  mov     rcx, [rdi+220h]; this
0x180037b6e  lea     rdx, [rbp+arg_18]; unsigned __int8 **
0x180037b72  mov     [rbp+arg_18], 0
0x180037b7a  call    ?GetWinnerItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetWinnerItemIdInternal(uchar * *)
0x180037b7f  mov     ebx, eax
0x180037b81  test    eax, eax
0x180037b83  js      loc_180037C39
0x180037b89  mov     rcx, [rdi+220h]; this
0x180037b90  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x180037b94  mov     [rbp+var_10], 0
0x180037b9c  call    ?GetOriginalItemIdInternal@CSyncChangeWrapper@@QEAAJPEAPEAE@Z; CSyncChangeWrapper::GetOriginalItemIdInternal(uchar * *)
0x180037ba1  mov     ebx, eax
0x180037ba3  test    eax, eax
0x180037ba5  js      loc_180037C30
0x180037bab  mov     rdx, [rbp+arg_10]
0x180037baf  mov     r14, [rbp+var_10]
0x180037bb3  test    rdx, rdx
0x180037bb6  jz      short loc_180037C23
0x180037bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bbf  lea     rax, WPP_GLOBAL_Control
0x180037bc6  cmp     rcx, rax
0x180037bc9  jz      short loc_180037BF0
0x180037bcb  test    byte ptr [rcx+1Ch], 8
0x180037bcf  jz      short loc_180037BF0
0x180037bd1  cmp     byte ptr [rcx+19h], 5
0x180037bd5  jb      short loc_180037BF0
0x180037bd7  mov     rcx, [rcx+10h]
0x180037bdb  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037be2  mov     edx, 120h
0x180037be7  call    WPP_SF_
0x180037bec  mov     rdx, [rbp+arg_10]; struct ISyncKnowledge *
0x180037bf0  mov     r9, [rbp+arg_18]; unsigned __int8 *
0x180037bf4  mov     r8, rsi; unsigned __int8 *
0x180037bf7  mov     rcx, rdi; this
0x180037bfa  mov     [rsp+40h+var_20], r14; unsigned __int8 *
0x180037bff  call    ?AddExclusionsToKnowledge@CChangeApplier@@AEAAJPEAUISyncKnowledge@@PEAE11@Z; CChangeApplier::AddExclusionsToKnowledge(ISyncKnowledge *,uchar *,uchar *,uchar *)
0x180037c04  mov     ebx, eax
0x180037c06  test    eax, eax
0x180037c08  js      short loc_180037C28
0x180037c0a  mov     rcx, [rbp+arg_10]
0x180037c0e  mov     rax, [rcx]
0x180037c11  mov     rax, [rax+8]
0x180037c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c1a  mov     rax, [rbp+arg_10]
0x180037c1e  mov     [r15], rax
0x180037c21  jmp     short loc_180037C28
0x180037c23  mov     ebx, 8004101Dh
0x180037c28  mov     rcx, r14; unsigned __int8 *
0x180037c2b  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180037c30  mov     rcx, [rbp+arg_18]; unsigned __int8 *
0x180037c34  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180037c39  mov     rcx, rsi; unsigned __int8 *
0x180037c3c  call    ?FreeId@IdParameters@@SAXPEAE@Z; IdParameters::FreeId(uchar *)
0x180037c41  lea     rsi, WPP_GLOBAL_Control
0x180037c48  mov     rcx, [rbp+arg_10]
0x180037c4c  test    rcx, rcx
0x180037c4f  jz      short loc_180037C5D
0x180037c51  mov     rax, [rcx]
0x180037c54  mov     rax, [rax+10h]
0x180037c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c64  cmp     rcx, rsi
0x180037c67  jz      short loc_180037C95
0x180037c69  test    byte ptr [rcx+1Ch], 8
0x180037c6d  jz      short loc_180037C95
0x180037c6f  cmp     byte ptr [rcx+19h], 5
0x180037c73  jb      short loc_180037C95
0x180037c75  mov     rcx, [rcx+10h]
0x180037c79  lea     r9, aCchangeapplier_89; "CChangeApplier::CreateLearnedKnowledgeF"...
0x180037c80  mov     edx, 121h
0x180037c85  mov     dword ptr [rsp+40h+var_20], ebx
0x180037c89  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180037c90  call    WPP_SF_sD
0x180037c95  mov     eax, ebx
0x180037c97  mov     rbx, [rsp+40h+arg_0]
0x180037c9c  add     rsp, 40h
0x180037ca0  pop     r15
0x180037ca2  pop     r14
0x180037ca4  pop     rdi
0x180037ca5  pop     rsi
0x180037ca6  pop     rbp
0x180037ca7  retn
```
