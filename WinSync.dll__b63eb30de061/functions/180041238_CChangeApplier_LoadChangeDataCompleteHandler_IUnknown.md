# CChangeApplier::LoadChangeDataCompleteHandler(IUnknown *)

- ea: `0x180041238`
- end: `0x180041509`
- name: `?LoadChangeDataCompleteHandler@CChangeApplier@@AEAAJPEAUIUnknown@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(CChangeApplier *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039f60`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800227b0`
- `0x180024894`
- `0x180035724`
- `0x1800374b8`
- `0x180040aa4`
- `0x180041238`
- `0x180041f28`
- `0x180043ac0`
- `0x180045b10`
- `0x180046160`
- `0x1800465e0`
- `0x180094010`

## string_xrefs

- `0x180041276`: `CChangeApplier::LoadChangeDataCompleteHandler`
- `0x1800414d8`: `CChangeApplier::LoadChangeDataCompleteHandler`

## pseudocode

```c
__int64 __fastcall CChangeApplier::LoadChangeDataCompleteHandler(CChangeApplier *this, struct IUnknown *a2)
{
  int TransferFilters; // ebx
  __int64 v5; // rax
  struct ISyncCallback *v6; // rdx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v9; // rdx
  BOOL v10; // esi
  unsigned int v11; // r14d
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v15; // [rsp+60h] [rbp+30h] BYREF
  __int64 v16; // [rsp+68h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      &WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      "CChangeApplier::LoadChangeDataCompleteHandler");
  }
  TransferFilters = CChangeApplier::ChangeState((__int64)this, 8);
  if ( TransferFilters < 0 )
    goto LABEL_32;
  v5 = *((_QWORD *)this + 70);
  if ( v5 )
  {
    v6 = (struct ISyncCallback *)*((_QWORD *)this + 50);
    if ( v6 && *(_DWORD *)(v5 + 76) )
      TransferFilters = CChangeApplier::RecoverableErrorNotificationWrapper(
                          this,
                          v6,
                          *((struct CSyncChangeWrapper **)this + 68),
                          1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 70) + 16LL))(*((_QWORD *)this + 70));
    *((_QWORD *)this + 70) = 0;
    if ( TransferFilters < 0 )
      goto LABEL_32;
  }
  TransferFilters = CChangeApplier::SetProviderWithError(this, 1);
  if ( TransferFilters < 0 )
    goto LABEL_32;
  v7 = *((_QWORD *)this + 73) == 0;
  v16 = 0;
  v15 = 0;
  if ( v7 )
  {
    *((_QWORD *)this + 73) = a2;
    if ( a2 )
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  }
  TransferFilters = CSyncChangeWrapper::GetTransferFilters(
                      *((CSyncChangeWrapper **)this + 68),
                      (enum SYNC_TRANSFER_FILTER *)&v15);
  if ( TransferFilters < 0 )
    goto LABEL_32;
  TransferFilters = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 68) + 8LL) + 80LL))(
                      *((_QWORD *)this + 68) + 8LL,
                      &v16);
  if ( TransferFilters < 0 )
    goto LABEL_32;
  v8 = v16;
  TransferFilters = -2147217379;
  if ( !v16 )
    goto LABEL_36;
  v9 = *((_QWORD *)this + 61);
  v10 = v16 != v9;
  if ( v9 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 16LL))(*((_QWORD *)this + 61));
    v8 = v16;
  }
  *((_QWORD *)this + 61) = v8;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v11 = v15;
  TransferFilters = CChangeApplier::ConvertChangeVersionAndKnowledgeForSave(this, v15);
  if ( TransferFilters >= 0 )
    TransferFilters = CChangeApplier::UpdateRunningKnowledgeStateForTransfer(this, v10);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v16 = 0;
  if ( TransferFilters < 0 )
    goto LABEL_32;
  v12 = *((_QWORD *)this + 68) + 8LL;
  v15 = 0;
  TransferFilters = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 56LL))(v12, &v15);
  if ( TransferFilters < 0 )
    goto LABEL_32;
  if ( (v15 & 5) == 0 && (v11 & 1) != 0 )
  {
    TransferFilters = CChangeApplier::SaveErrorsForCurrentChange(this, 1);
    if ( TransferFilters < 0 )
      goto LABEL_32;
  }
  else if ( (v11 & 0x40000) != 0 )
  {
LABEL_30:
    v13 = CChangeApplier::ItemTransferComplete(this, 0, 0);
    goto LABEL_31;
  }
  if ( TransferFilters == 1 )
    goto LABEL_30;
  v13 = CChangeApplier::ProcessItemData(this);
LABEL_31:
  TransferFilters = v13;
LABEL_32:
  if ( TransferFilters != -2147467260 )
  {
    if ( TransferFilters >= 0 )
      goto LABEL_37;
LABEL_36:
    TransferFilters = CChangeApplier::SetError(this, *((struct ISyncCallback **)this + 50), TransferFilters);
    goto LABEL_37;
  }
  if ( !*((_DWORD *)this + 170) )
    goto LABEL_36;
  TransferFilters = 0;
LABEL_37:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      (unsigned int)&WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids,
      (unsigned int)"CChangeApplier::LoadChangeDataCompleteHandler",
      TransferFilters);
  }
  return (unsigned int)TransferFilters;
}

```

## disassembly

```asm
0x180041238  mov     [rsp-18h+arg_0], rbx
0x18004123d  mov     [rsp-18h+arg_8], rsi
0x180041242  push    rbp
0x180041243  push    rdi
0x180041244  push    r14
0x180041246  mov     rbp, rsp
0x180041249  sub     rsp, 30h
0x18004124d  mov     rsi, rdx
0x180041250  mov     rdi, rcx
0x180041253  mov     rcx, cs:WPP_GLOBAL_Control
0x18004125a  lea     r14, WPP_GLOBAL_Control
0x180041261  cmp     rcx, r14
0x180041264  jz      short loc_18004128E
0x180041266  test    byte ptr [rcx+1Ch], 8
0x18004126a  jz      short loc_18004128E
0x18004126c  cmp     byte ptr [rcx+19h], 5
0x180041270  jb      short loc_18004128E
0x180041272  mov     rcx, [rcx+10h]
0x180041276  lea     r9, aCchangeapplier_48; "CChangeApplier::LoadChangeDataCompleteH"...
0x18004127d  mov     edx, 7Bh ; '{'
0x180041282  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x180041289  call    WPP_SF_s
0x18004128e  mov     edx, 8
0x180041293  mov     rcx, rdi
0x180041296  call    ?ChangeState@CChangeApplier@@AEAAJW4ChangeApplierState@@@Z; CChangeApplier::ChangeState(ChangeApplierState)
0x18004129b  mov     ebx, eax
0x18004129d  test    eax, eax
0x18004129f  js      loc_18004148F
0x1800412a5  mov     rax, [rdi+230h]
0x1800412ac  test    rax, rax
0x1800412af  jz      short loc_180041300
0x1800412b1  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x1800412b8  test    rdx, rdx
0x1800412bb  jz      short loc_1800412DA
0x1800412bd  cmp     dword ptr [rax+4Ch], 0
0x1800412c1  jz      short loc_1800412DA
0x1800412c3  mov     r8, [rdi+220h]; struct CSyncChangeWrapper *
0x1800412ca  mov     r9d, 1; int
0x1800412d0  mov     rcx, rdi; this
0x1800412d3  call    ?RecoverableErrorNotificationWrapper@CChangeApplier@@AEAAJPEAUISyncCallback@@PEAVCSyncChangeWrapper@@H@Z; CChangeApplier::RecoverableErrorNotificationWrapper(ISyncCallback *,CSyncChangeWrapper *,int)
0x1800412d8  mov     ebx, eax
0x1800412da  mov     rcx, [rdi+230h]
0x1800412e1  mov     rax, [rcx]
0x1800412e4  mov     rax, [rax+10h]
0x1800412e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412ed  mov     qword ptr [rdi+230h], 0
0x1800412f8  test    ebx, ebx
0x1800412fa  js      loc_18004148F
0x180041300  mov     edx, 1; int
0x180041305  mov     rcx, rdi; this
0x180041308  call    ?SetProviderWithError@CChangeApplier@@AEAAJH@Z; CChangeApplier::SetProviderWithError(int)
0x18004130d  mov     ebx, eax
0x18004130f  test    eax, eax
0x180041311  js      loc_18004148F
0x180041317  cmp     qword ptr [rdi+248h], 0
0x18004131f  mov     [rbp+arg_18], 0
0x180041327  mov     [rbp+arg_10], 0
0x18004132e  jnz     short loc_18004134B
0x180041330  mov     [rdi+248h], rsi
0x180041337  test    rsi, rsi
0x18004133a  jz      short loc_18004134B
0x18004133c  mov     rax, [rsi]
0x18004133f  mov     rcx, rsi
0x180041342  mov     rax, [rax+8]
0x180041346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004134b  mov     rcx, [rdi+220h]; this
0x180041352  lea     rdx, [rbp+arg_10]; enum SYNC_TRANSFER_FILTER *
0x180041356  call    ?GetTransferFilters@CSyncChangeWrapper@@QEAAJPEAW4SYNC_TRANSFER_FILTER@@@Z; CSyncChangeWrapper::GetTransferFilters(SYNC_TRANSFER_FILTER *)
0x18004135b  mov     ebx, eax
0x18004135d  test    eax, eax
0x18004135f  js      loc_18004148F
0x180041365  mov     rcx, [rdi+220h]
0x18004136c  lea     rdx, [rbp+arg_18]
0x180041370  add     rcx, 8
0x180041374  mov     rax, [rcx]
0x180041377  mov     rax, [rax+50h]
0x18004137b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041380  mov     ebx, eax
0x180041382  test    eax, eax
0x180041384  js      loc_18004148F
0x18004138a  mov     rcx, [rbp+arg_18]
0x18004138e  mov     ebx, 8004101Dh
0x180041393  test    rcx, rcx
0x180041396  jz      loc_1800414A8
0x18004139c  mov     rdx, [rdi+1E8h]
0x1800413a3  xor     esi, esi
0x1800413a5  cmp     rcx, rdx
0x1800413a8  setnz   sil
0x1800413ac  test    rdx, rdx
0x1800413af  jz      short loc_1800413C4
0x1800413b1  mov     rax, [rdx]
0x1800413b4  mov     rcx, rdx
0x1800413b7  mov     rax, [rax+10h]
0x1800413bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413c0  mov     rcx, [rbp+arg_18]
0x1800413c4  mov     [rdi+1E8h], rcx
0x1800413cb  mov     rax, [rcx]
0x1800413ce  mov     rax, [rax+8]
0x1800413d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413d7  mov     r14d, [rbp+arg_10]
0x1800413db  mov     rcx, rdi
0x1800413de  mov     edx, r14d
0x1800413e1  call    ?ConvertChangeVersionAndKnowledgeForSave@CChangeApplier@@AEAAJW4SYNC_TRANSFER_FILTER@@@Z; CChangeApplier::ConvertChangeVersionAndKnowledgeForSave(SYNC_TRANSFER_FILTER)
0x1800413e6  mov     ebx, eax
0x1800413e8  test    eax, eax
0x1800413ea  js      short loc_1800413F8
0x1800413ec  mov     edx, esi; int
0x1800413ee  mov     rcx, rdi; this
0x1800413f1  call    ?UpdateRunningKnowledgeStateForTransfer@CChangeApplier@@AEAAJH@Z; CChangeApplier::UpdateRunningKnowledgeStateForTransfer(int)
0x1800413f6  mov     ebx, eax
0x1800413f8  mov     rcx, [rbp+arg_18]
0x1800413fc  mov     rax, [rcx]
0x1800413ff  mov     rax, [rax+10h]
0x180041403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041408  mov     [rbp+arg_18], 0
0x180041410  test    ebx, ebx
0x180041412  js      short loc_180041488
0x180041414  mov     rcx, [rdi+220h]
0x18004141b  lea     rdx, [rbp+arg_10]
0x18004141f  add     rcx, 8
0x180041423  mov     [rbp+arg_10], 0
0x18004142a  mov     rax, [rcx]
0x18004142d  mov     rax, [rax+38h]
0x180041431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041436  mov     ebx, eax
0x180041438  test    eax, eax
0x18004143a  js      short loc_180041488
0x18004143c  test    byte ptr [rbp+arg_10], 5
0x180041440  setz    cl
0x180041443  test    r14b, 1
0x180041447  setnz   al
0x18004144a  test    al, cl
0x18004144c  jz      short loc_180041463
0x18004144e  mov     edx, 1; int
0x180041453  mov     rcx, rdi; this
0x180041456  call    ?SaveErrorsForCurrentChange@CChangeApplier@@AEAAJH@Z; CChangeApplier::SaveErrorsForCurrentChange(int)
0x18004145b  mov     ebx, eax
0x18004145d  test    eax, eax
0x18004145f  js      short loc_180041488
0x180041461  jmp     short loc_18004146A
0x180041463  bt      r14d, 12h
0x180041468  jb      short loc_180041479
0x18004146a  cmp     ebx, 1
0x18004146d  jz      short loc_180041479
0x18004146f  mov     rcx, rdi; this
0x180041472  call    ?ProcessItemData@CChangeApplier@@AEAAJXZ; CChangeApplier::ProcessItemData(void)
0x180041477  jmp     short loc_180041486
0x180041479  xor     r8d, r8d; int
0x18004147c  xor     edx, edx; int
0x18004147e  mov     rcx, rdi; this
0x180041481  call    ?ItemTransferComplete@CChangeApplier@@AEAAJHH@Z; CChangeApplier::ItemTransferComplete(int,int)
0x180041486  mov     ebx, eax
0x180041488  lea     r14, WPP_GLOBAL_Control
0x18004148f  cmp     ebx, 80004004h
0x180041495  jnz     short loc_1800414A4
0x180041497  cmp     dword ptr [rdi+2A8h], 0
0x18004149e  jz      short loc_1800414A8
0x1800414a0  xor     ebx, ebx
0x1800414a2  jmp     short loc_1800414BC
0x1800414a4  test    ebx, ebx
0x1800414a6  jns     short loc_1800414BC
0x1800414a8  mov     rdx, [rdi+190h]; struct ISyncCallback *
0x1800414af  mov     r8d, ebx; int
0x1800414b2  mov     rcx, rdi; this
0x1800414b5  call    ?SetError@CChangeApplier@@AEAAJPEAUISyncCallback@@J@Z; CChangeApplier::SetError(ISyncCallback *,long)
0x1800414ba  mov     ebx, eax
0x1800414bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800414c3  cmp     rcx, r14
0x1800414c6  jz      short loc_1800414F4
0x1800414c8  test    byte ptr [rcx+1Ch], 8
0x1800414cc  jz      short loc_1800414F4
0x1800414ce  cmp     byte ptr [rcx+19h], 5
0x1800414d2  jb      short loc_1800414F4
0x1800414d4  mov     rcx, [rcx+10h]
0x1800414d8  lea     r9, aCchangeapplier_48; "CChangeApplier::LoadChangeDataCompleteH"...
0x1800414df  mov     edx, 7Ch ; '|'
0x1800414e4  mov     [rsp+30h+var_10], ebx
0x1800414e8  lea     r8, WPP_4afb552cd4e9336475e7a5400d2892b5_Traceguids
0x1800414ef  call    WPP_SF_sD
0x1800414f4  mov     rsi, [rsp+30h+arg_8]
0x1800414f9  mov     eax, ebx
0x1800414fb  mov     rbx, [rsp+30h+arg_0]
0x180041500  add     rsp, 30h
0x180041504  pop     r14
0x180041506  pop     rdi
0x180041507  pop     rbp
0x180041508  retn
```
