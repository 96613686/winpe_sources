# CChangeApplier::GetNewMoveins(ISyncKnowledge *)

- ea: `0x18003d8f0`
- end: `0x18003da02`
- name: `?GetNewMoveins@CChangeApplier@@UEAAJPEAUISyncKnowledge@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CChangeApplier *this, struct ISyncCallback *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18003d8f0`
- `0x180046160`
- `0x180081f68`
- `0x180094010`

## string_xrefs

- `0x18003d92b`: `CChangeApplier::GetNewMoveins`
- `0x18003d9d1`: `CChangeApplier::GetNewMoveins`

## pseudocode

```c
__int64 __fastcall CChangeApplier::GetNewMoveins(CChangeApplier *this, struct ISyncCallback *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  signed int v6; // eax
  const struct _GUID *v7; // r8
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::GetNewMoveins");
  }
  v4 = *((_QWORD *)this + 16);
  if ( !v4 )
  {
    v5 = -2147217379;
LABEL_11:
    v5 = CChangeApplier::SetError((CChangeApplier *)((char *)this - 64), a2, v5);
    goto LABEL_12;
  }
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, struct ISyncCallback *, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, a2, &v9);
  v5 = v6;
  if ( v6 < 0 )
  {
    SetErrorInfoHelper(v6, &IID_IFilteredReplicaNotifyingChangeApplierTarget, v7);
    goto LABEL_11;
  }
  v5 = (*(__int64 (__fastcall **)(char *, struct ISyncCallback *, __int64))(*((_QWORD *)this + 1) + 32LL))(
         (char *)this + 8,
         a2,
         v9);
  if ( v5 < 0 )
    goto LABEL_11;
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      76,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::GetNewMoveins",
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003d8f0  mov     [rsp+arg_8], rbx
0x18003d8f5  mov     [rsp+arg_10], rbp
0x18003d8fa  push    rsi
0x18003d8fb  push    rdi
0x18003d8fc  push    r14
0x18003d8fe  sub     rsp, 30h
0x18003d902  mov     rbp, rdx
0x18003d905  mov     rsi, rcx
0x18003d908  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d90f  lea     r14, WPP_GLOBAL_Control
0x18003d916  cmp     rcx, r14
0x18003d919  jz      short loc_18003D943
0x18003d91b  test    byte ptr [rcx+1Ch], 8
0x18003d91f  jz      short loc_18003D943
0x18003d921  cmp     byte ptr [rcx+19h], 5
0x18003d925  jb      short loc_18003D943
0x18003d927  mov     rcx, [rcx+10h]
0x18003d92b  lea     r9, aCchangeapplier_47; "CChangeApplier::GetNewMoveins"
0x18003d932  mov     edx, 4Bh ; 'K'
0x18003d937  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003d93e  call    WPP_SF_s
0x18003d943  mov     rcx, [rsi+80h]
0x18003d94a  test    rcx, rcx
0x18003d94d  jnz     short loc_18003D956
0x18003d94f  mov     ebx, 8004101Dh
0x18003d954  jmp     short loc_18003D9A7
0x18003d956  mov     [rsp+48h+arg_0], 0
0x18003d95f  lea     r8, [rsp+48h+arg_0]
0x18003d964  mov     rax, [rcx]
0x18003d967  mov     rdx, rbp
0x18003d96a  mov     rax, [rax+30h]
0x18003d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d973  mov     ebx, eax
0x18003d975  test    eax, eax
0x18003d977  js      short loc_18003D999
0x18003d979  mov     r8, [rsp+48h+arg_0]
0x18003d97e  lea     rcx, [rsi+8]
0x18003d982  mov     rax, [rcx]
0x18003d985  mov     rdx, rbp
0x18003d988  mov     rax, [rax+20h]
0x18003d98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d991  mov     ebx, eax
0x18003d993  test    eax, eax
0x18003d995  jns     short loc_18003D9B5
0x18003d997  jmp     short loc_18003D9A7
0x18003d999  lea     rdx, IID_IFilteredReplicaNotifyingChangeApplierTarget; struct _GUID *
0x18003d9a0  mov     ecx, eax; dwMessageId
0x18003d9a2  call    ?SetErrorInfoHelper@@YAXJAEBU_GUID@@0@Z; SetErrorInfoHelper(long,_GUID const &,_GUID const &)
0x18003d9a7  mov     r8d, ebx; int
0x18003d9aa  lea     rcx, [rsi-40h]; this
0x18003d9ae  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x18003d9b3  mov     ebx, eax
0x18003d9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9bc  cmp     rcx, r14
0x18003d9bf  jz      short loc_18003D9ED
0x18003d9c1  test    byte ptr [rcx+1Ch], 8
0x18003d9c5  jz      short loc_18003D9ED
0x18003d9c7  cmp     byte ptr [rcx+19h], 5
0x18003d9cb  jb      short loc_18003D9ED
0x18003d9cd  mov     rcx, [rcx+10h]
0x18003d9d1  lea     r9, aCchangeapplier_47; "CChangeApplier::GetNewMoveins"
0x18003d9d8  mov     edx, 4Ch ; 'L'
0x18003d9dd  mov     [rsp+48h+var_28], ebx
0x18003d9e1  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x18003d9e8  call    WPP_SF_sD
0x18003d9ed  mov     rbp, [rsp+48h+arg_10]
0x18003d9f2  mov     eax, ebx
0x18003d9f4  mov     rbx, [rsp+48h+arg_8]
0x18003d9f9  add     rsp, 30h
0x18003d9fd  pop     r14
0x18003d9ff  pop     rdi
0x18003da00  pop     rsi
0x18003da01  retn
```
