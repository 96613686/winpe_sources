# CChangeApplier::GetFilterForgottenKnowledgeComplete(ulong,ISyncKnowledge *)

- ea: `0x18003c580`
- end: `0x18003c747`
- name: `?GetFilterForgottenKnowledgeComplete@CChangeApplier@@UEAAJKPEAUISyncKnowledge@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(CChangeApplier *this, struct ISyncCallback *, struct ISyncKnowledge *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180031f2c`
- `0x180032bf8`
- `0x18003c580`
- `0x180046160`
- `0x1800623f0`
- `0x180094010`

## string_xrefs

- `0x18003c5b8`: `CChangeApplier::GetFilterForgottenKnowledgeComplete`
- `0x18003c71c`: `CChangeApplier::GetFilterForgottenKnowledgeComplete`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetFilterForgottenKnowledgeComplete(
        CChangeApplier *this,
        struct ISyncCallback *a2,
        struct ISyncKnowledge *a3)
{
  __int64 v4; // rbp
  int IsContained; // ebx
  struct ISyncKnowledge *v7; // rdx
  struct _CHANGE_APPLIER_WORK_ITEM *v8; // rax
  struct _CHANGE_APPLIER_WORK_ITEM *v9; // rsi
  int v10; // r8d
  struct ISyncKnowledge *v11; // rcx

  v4 = (unsigned int)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetFilterForgottenKnowledgeComplete");
  }
  if ( (unsigned int)v4 >= *((_DWORD *)this + 46) || *((_DWORD *)this + 47) != (_DWORD)v4 )
  {
    IsContained = -2147024809;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    IsContained = -2147467261;
LABEL_28:
    IsContained = CChangeApplier::SetError((CChangeApplier *)((char *)this - 56), a2, IsContained);
    goto LABEL_29;
  }
  if ( *((_QWORD *)this + 17) )
  {
    if ( !(_DWORD)v4 )
    {
      v11 = (struct ISyncKnowledge *)*((_QWORD *)this + 60);
      if ( v11 )
      {
        IsContained = CSyncChangeContext::KnowledgeIsContained(v11, a3, (unsigned int)a3);
        if ( IsContained == 1 )
        {
          IsContained = -2147217403;
          goto LABEL_28;
        }
LABEL_13:
        if ( IsContained )
          goto LABEL_17;
      }
    }
  }
  else
  {
    v7 = (struct ISyncKnowledge *)*((_QWORD *)this + 60);
    if ( v7 )
    {
      IsContained = CSyncChangeContext::KnowledgeIsContained(a3, v7, (unsigned int)a3);
      if ( IsContained == 1 )
        IsContained = -2147217403;
      goto LABEL_13;
    }
  }
  v8 = (struct _CHANGE_APPLIER_WORK_ITEM *)SeAlloc(0x18u);
  v9 = v8;
  if ( !v8 )
  {
    IsContained = -2147024882;
    goto LABEL_28;
  }
  *((_QWORD *)v8 + 1) = 0;
  *((_DWORD *)v8 + 4) = 0;
  *(_QWORD *)(*((_QWORD *)this + 24) + 8 * v4) = a3;
  ((void (__fastcall *)(struct ISyncKnowledge *))a3->lpVtbl->AddRef)(a3);
  ++*((_DWORD *)this + 47);
  *(_DWORD *)v9 = 1;
  *((_DWORD *)v9 + 4) = v4;
  IsContained = CChangeApplier::AddWorkItemToWorkQueue((CChangeApplier *)((char *)this - 56), v9, v10);
  if ( IsContained < 0 )
    _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(v9, (unsigned int)a2);
LABEL_17:
  if ( IsContained == -2147467260 )
  {
    if ( !*((_DWORD *)this + 156) )
      goto LABEL_28;
    IsContained = 0;
  }
  else if ( IsContained < 0 )
  {
    goto LABEL_28;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetFilterForgottenKnowledgeComplete",
      IsContained);
  }
  return (unsigned int)IsContained;
}

```

## disassembly

```asm
0x18003c580  push    rbx
0x18003c582  push    rbp
0x18003c583  push    rsi
0x18003c584  push    rdi
0x18003c585  push    r13
0x18003c587  push    r14
0x18003c589  sub     rsp, 38h
0x18003c58d  mov     r14, r8
0x18003c590  mov     ebp, edx
0x18003c592  mov     rdi, rcx
0x18003c595  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c59c  lea     r13, WPP_GLOBAL_Control
0x18003c5a3  cmp     rcx, r13
0x18003c5a6  jz      short loc_18003C5D0
0x18003c5a8  test    byte ptr [rcx+1Ch], 8
0x18003c5ac  jz      short loc_18003C5D0
0x18003c5ae  cmp     byte ptr [rcx+19h], 5
0x18003c5b2  jb      short loc_18003C5D0
0x18003c5b4  mov     rcx, [rcx+10h]
0x18003c5b8  lea     r9, aCchangeapplier_87; "CChangeApplier::GetFilterForgottenKnowl"...
0x18003c5bf  mov     edx, 33h ; '3'
0x18003c5c4  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003c5cb  call    WPP_SF_s
0x18003c5d0  cmp     ebp, [rdi+0B8h]
0x18003c5d6  jnb     loc_18003C6ED
0x18003c5dc  cmp     [rdi+0BCh], ebp
0x18003c5e2  jnz     loc_18003C6ED
0x18003c5e8  test    r14, r14
0x18003c5eb  jnz     short loc_18003C5F7
0x18003c5ed  mov     ebx, 80004003h
0x18003c5f2  jmp     loc_18003C6F2
0x18003c5f7  cmp     qword ptr [rdi+88h], 0
0x18003c5ff  jnz     loc_18003C6AE
0x18003c605  mov     rdx, [rdi+1E0h]; struct ISyncKnowledge *
0x18003c60c  test    rdx, rdx
0x18003c60f  jz      short loc_18003C629
0x18003c611  mov     rcx, r14; struct ISyncKnowledge *
0x18003c614  call    ?KnowledgeIsContained@CSyncChangeContext@@SAJPEAUISyncKnowledge@@0K@Z; CSyncChangeContext::KnowledgeIsContained(ISyncKnowledge *,ISyncKnowledge *,ulong)
0x18003c619  mov     ebx, eax
0x18003c61b  cmp     eax, 1
0x18003c61e  jnz     short loc_18003C625
0x18003c620  mov     ebx, 80041005h
0x18003c625  test    ebx, ebx
0x18003c627  jnz     short loc_18003C699
0x18003c629  mov     ecx, 18h; unsigned __int64
0x18003c62e  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18003c633  mov     rsi, rax
0x18003c636  test    rax, rax
0x18003c639  jz      loc_18003C6E6
0x18003c63f  mov     qword ptr [rax+8], 0
0x18003c647  mov     dword ptr [rax+10h], 0
0x18003c64e  mov     rcx, [rdi+0C0h]
0x18003c655  mov     [rcx+rbp*8], r14
0x18003c659  mov     rcx, [r14]
0x18003c65c  mov     rax, [rcx+8]
0x18003c660  mov     rcx, r14
0x18003c663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c668  lea     rcx, [rdi-38h]; this
0x18003c66c  mov     rdx, rsi; struct _CHANGE_APPLIER_WORK_ITEM *
0x18003c66f  mov     eax, [rcx+0F4h]
0x18003c675  inc     eax
0x18003c677  mov     [rdi+0BCh], eax
0x18003c67d  mov     dword ptr [rsi], 1
0x18003c683  mov     [rsi+10h], ebp
0x18003c686  call    ?AddWorkItemToWorkQueue@CChangeApplier@@AEAAJPEAU_CHANGE_APPLIER_WORK_ITEM@@H@Z; CChangeApplier::AddWorkItemToWorkQueue(_CHANGE_APPLIER_WORK_ITEM *,int)
0x18003c68b  mov     ebx, eax
0x18003c68d  test    eax, eax
0x18003c68f  jns     short loc_18003C699
0x18003c691  mov     rcx, rsi; this
0x18003c694  call    ??_G_CHANGE_APPLIER_WORK_ITEM@@QEAAPEAXI@Z; _CHANGE_APPLIER_WORK_ITEM::`scalar deleting destructor'(uint)
0x18003c699  cmp     ebx, 80004004h
0x18003c69f  jnz     short loc_18003C6E0
0x18003c6a1  cmp     dword ptr [rdi+270h], 0
0x18003c6a8  jz      short loc_18003C6F2
0x18003c6aa  xor     ebx, ebx
0x18003c6ac  jmp     short loc_18003C700
0x18003c6ae  test    ebp, ebp
0x18003c6b0  jnz     loc_18003C629
0x18003c6b6  mov     rcx, [rdi+1E0h]; struct ISyncKnowledge *
0x18003c6bd  test    rcx, rcx
0x18003c6c0  jz      loc_18003C629
0x18003c6c6  mov     rdx, r14; struct ISyncKnowledge *
0x18003c6c9  call    ?KnowledgeIsContained@CSyncChangeContext@@SAJPEAUISyncKnowledge@@0K@Z; CSyncChangeContext::KnowledgeIsContained(ISyncKnowledge *,ISyncKnowledge *,ulong)
0x18003c6ce  mov     ebx, eax
0x18003c6d0  cmp     eax, 1
0x18003c6d3  jnz     loc_18003C625
0x18003c6d9  mov     ebx, 80041005h
0x18003c6de  jmp     short loc_18003C6F2
0x18003c6e0  test    ebx, ebx
0x18003c6e2  jns     short loc_18003C700
0x18003c6e4  jmp     short loc_18003C6F2
0x18003c6e6  mov     ebx, 8007000Eh
0x18003c6eb  jmp     short loc_18003C6F2
0x18003c6ed  mov     ebx, 80070057h
0x18003c6f2  lea     rcx, [rdi-38h]; this
0x18003c6f6  mov     r8d, ebx; int
0x18003c6f9  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003c6fe  mov     ebx, eax
0x18003c700  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c707  cmp     rcx, r13
0x18003c70a  jz      short loc_18003C738
0x18003c70c  test    byte ptr [rcx+1Ch], 8
0x18003c710  jz      short loc_18003C738
0x18003c712  cmp     byte ptr [rcx+19h], 5
0x18003c716  jb      short loc_18003C738
0x18003c718  mov     rcx, [rcx+10h]
0x18003c71c  lea     r9, aCchangeapplier_87; "CChangeApplier::GetFilterForgottenKnowl"...
0x18003c723  mov     edx, 34h ; '4'
0x18003c728  mov     [rsp+68h+var_48], ebx
0x18003c72c  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003c733  call    WPP_SF_sD
0x18003c738  mov     eax, ebx
0x18003c73a  add     rsp, 38h
0x18003c73e  pop     r14
0x18003c740  pop     r13
0x18003c742  pop     rdi
0x18003c743  pop     rsi
0x18003c744  pop     rbp
0x18003c745  pop     rbx
0x18003c746  retn
```
