# Windows::Internal::InputPaneRepositionBehavior::OnPropertyChanged(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)

- ea: `0x18009c7d0`
- end: `0x18009c992`
- name: `?OnPropertyChanged@InputPaneRepositionBehavior@Internal@Windows@@UEAAJPEAVElement@DirectUI@@PEBUPropertyInfo@5@HPEAVValue@5@2@Z`
- size: `450`
- prototype: `int(Windows::Internal::InputPaneRepositionBehavior *__hidden this, struct DirectUI::Element *, const struct DirectUI::PropertyInfo *, int, struct DirectUI::Value *, struct DirectUI::Value *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180037a1c`
- `0x18005a3b8`
- `0x1800610ec`
- `0x18009c7d0`
- `0x1800e5010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18009c829`
- `USER32!IsRectEmpty` at `0x18009c835`
- `USER32!IsRectEmpty` at `0x18009c829`
- `USER32!IsRectEmpty` at `0x18009c835`
- `USER32!EqualRect` at `0x18009c818`
- `USER32!EqualRect` at `0x18009c818`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c847`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c854`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c8b7`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c8c4`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c847`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c854`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c8b7`
- `DUI70!?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ` at `0x18009c8c4`
- `DUI70!?LocationProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18009c7ea`

## pseudocode

```c
__int64 __fastcall Windows::Internal::InputPaneRepositionBehavior::OnPropertyChanged(
        const RECT *this,
        struct DirectUI::Element *a2,
        const struct DirectUI::PropertyInfo *a3,
        int a4,
        struct DirectUI::Value *a5,
        struct DirectUI::Value *a6)
{
  int v8; // esi
  BOOL v9; // ebx
  const struct tagPOINT *v10; // rbx
  int v11; // eax
  int v12; // ebx
  const struct tagPOINT *Point; // r14
  const struct tagPOINT *v14; // r13
  unsigned int v15; // ebx
  unsigned int left; // ebx
  int v18; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-14h]
  _QWORD v20[2]; // [rsp+58h] [rbp-10h] BYREF

  v8 = 0;
  if ( DirectUI::PropNotify::IsEqual(a3, a4, DirectUI::Element::LocationProp) )
  {
    v20[0] = 0;
    if ( EqualRect(this + 3, this + 2)
      || (v9 = IsRectEmpty(this + 2), IsRectEmpty(this + 3) == v9)
      || (v10 = DirectUI::Value::GetPoint(a6), DirectUI::Value::GetPoint(a5)->x != v10->x) )
    {
      left = this[4].left;
      if ( left != -1 )
      {
        if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20) >= 0 )
          (*(void (__fastcall **)(_QWORD, struct DirectUI::Element *, _QWORD))(*(_QWORD *)v20[0] + 272LL))(
            v20[0],
            a2,
            left);
        this[4].left = -1;
      }
    }
    else
    {
      v11 = this[3].bottom - this[3].top;
      v12 = this[2].bottom - this[2].top;
      v18 = 0;
      if ( v12 <= v11 )
        v12 = v11;
      v8 = DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, struct DirectUI::Element *, const RECT *, int *))(*(_QWORD *)v20[0]
                                                                                                + 256LL))(
               v20[0],
               a2,
               this + 4,
               &v18);
        if ( v8 >= 0 )
        {
          Point = DirectUI::Value::GetPoint(a6);
          v14 = DirectUI::Value::GetPoint(a5);
          v19 = this[4].left;
          v8 = DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20);
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct DirectUI::Element *, const struct tagPOINT *, const struct tagPOINT *, const RECT *, _DWORD, int))(*(_QWORD *)v20[0] + 304LL))(
                   v20[0],
                   v19,
                   a2,
                   v14,
                   Point,
                   this + 2,
                   0,
                   v12);
          v15 = this[4].left;
          if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)v20) >= 0 )
            (*(void (__fastcall **)(_QWORD, struct DirectUI::Element *, _QWORD))(*(_QWORD *)v20[0] + 264LL))(
              v20[0],
              a2,
              v15);
        }
      }
    }
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v20);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009c7d0  push    rbp
0x18009c7d2  push    rbx
0x18009c7d3  push    rsi
0x18009c7d4  push    rdi
0x18009c7d5  push    r12
0x18009c7d7  push    r13
0x18009c7d9  push    r14
0x18009c7db  push    r15
0x18009c7dd  mov     rbp, rsp
0x18009c7e0  sub     rsp, 68h
0x18009c7e4  mov     rax, r8
0x18009c7e7  mov     r12, rdx
0x18009c7ea  mov     r8, cs:__imp_?LocationProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18009c7f1  mov     rdi, rcx
0x18009c7f4  mov     rcx, rax; struct DirectUI::PropertyInfo *
0x18009c7f7  mov     edx, r9d; int
0x18009c7fa  xor     esi, esi
0x18009c7fc  call    ?IsEqual@PropNotify@DirectUI@@SA_NPEBUPropertyInfo@2@HP6APEBU32@XZ@Z; DirectUI::PropNotify::IsEqual(DirectUI::PropertyInfo const *,int,DirectUI::PropertyInfo const * (*)(void))
0x18009c801  test    al, al
0x18009c803  jz      loc_18009C97F
0x18009c809  lea     r15, [rdi+20h]
0x18009c80d  mov     [rbp+var_10], rsi
0x18009c811  mov     rdx, r15; lprc2
0x18009c814  lea     rcx, [rdi+30h]; lprc1
0x18009c818  call    cs:__imp_EqualRect
0x18009c81e  test    eax, eax
0x18009c820  jnz     loc_18009C941
0x18009c826  mov     rcx, r15; lprc
0x18009c829  call    cs:__imp_IsRectEmpty
0x18009c82f  lea     rcx, [rdi+30h]; lprc
0x18009c833  mov     ebx, eax
0x18009c835  call    cs:__imp_IsRectEmpty
0x18009c83b  cmp     eax, ebx
0x18009c83d  jz      loc_18009C941
0x18009c843  mov     rcx, [rbp+arg_28]
0x18009c847  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x18009c84d  mov     rcx, [rbp+arg_20]
0x18009c851  mov     rbx, rax
0x18009c854  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x18009c85a  mov     ecx, [rax]
0x18009c85c  cmp     ecx, [rbx]
0x18009c85e  jnz     loc_18009C941
0x18009c864  mov     eax, [rdi+3Ch]
0x18009c867  lea     rcx, [rbp+var_10]; this
0x18009c86b  sub     eax, [rdi+34h]
0x18009c86e  mov     ebx, [rdi+2Ch]
0x18009c871  sub     ebx, [rdi+24h]
0x18009c874  cmp     ebx, eax
0x18009c876  mov     [rbp+var_18], esi
0x18009c879  cmovle  ebx, eax
0x18009c87c  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x18009c881  mov     esi, eax
0x18009c883  test    eax, eax
0x18009c885  js      loc_18009C976
0x18009c88b  mov     rcx, [rbp+var_10]
0x18009c88f  lea     r9, [rbp+var_18]
0x18009c893  lea     r8, [rdi+40h]
0x18009c897  mov     rdx, r12
0x18009c89a  mov     rax, [rcx]
0x18009c89d  mov     rax, [rax+100h]
0x18009c8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8a9  mov     esi, eax
0x18009c8ab  test    eax, eax
0x18009c8ad  js      loc_18009C976
0x18009c8b3  mov     rcx, [rbp+arg_28]
0x18009c8b7  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x18009c8bd  mov     rcx, [rbp+arg_20]
0x18009c8c1  mov     r14, rax
0x18009c8c4  call    cs:__imp_?GetPoint@Value@DirectUI@@QEAAPEBUtagPOINT@@XZ; DirectUI::Value::GetPoint(void)
0x18009c8ca  mov     r13, rax
0x18009c8cd  lea     rcx, [rbp+var_10]; this
0x18009c8d1  mov     eax, [rdi+40h]
0x18009c8d4  mov     [rbp+var_14], eax
0x18009c8d7  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x18009c8dc  mov     esi, eax
0x18009c8de  test    eax, eax
0x18009c8e0  js      short loc_18009C916
0x18009c8e2  mov     rcx, [rbp+var_10]
0x18009c8e6  mov     r9, r13
0x18009c8e9  mov     edx, [rbp+var_14]
0x18009c8ec  mov     [rsp+68h+var_30], ebx
0x18009c8f0  mov     [rsp+68h+var_38], 0
0x18009c8f8  mov     r8, [rcx]
0x18009c8fb  mov     [rsp+68h+var_40], r15
0x18009c900  mov     [rsp+68h+var_48], r14
0x18009c905  mov     rax, [r8+130h]
0x18009c90c  mov     r8, r12
0x18009c90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c914  mov     esi, eax
0x18009c916  mov     ebx, [rdi+40h]
0x18009c919  lea     rcx, [rbp+var_10]; this
0x18009c91d  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x18009c922  test    eax, eax
0x18009c924  js      short loc_18009C976
0x18009c926  mov     rcx, [rbp+var_10]
0x18009c92a  mov     r8d, ebx
0x18009c92d  mov     rdx, r12
0x18009c930  mov     rax, [rcx]
0x18009c933  mov     rax, [rax+108h]
0x18009c93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c93f  jmp     short loc_18009C976
0x18009c941  mov     ebx, [rdi+40h]
0x18009c944  cmp     ebx, 0FFFFFFFFh
0x18009c947  jz      short loc_18009C976
0x18009c949  lea     rcx, [rbp+var_10]; this
0x18009c94d  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x18009c952  test    eax, eax
0x18009c954  js      short loc_18009C96F
0x18009c956  mov     rcx, [rbp+var_10]
0x18009c95a  mov     r8d, ebx
0x18009c95d  mov     rdx, r12
0x18009c960  mov     rax, [rcx]
0x18009c963  mov     rax, [rax+110h]
0x18009c96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c96f  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x18009c976  lea     rcx, [rbp+var_10]; this
0x18009c97a  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x18009c97f  mov     eax, esi
0x18009c981  add     rsp, 68h
0x18009c985  pop     r15
0x18009c987  pop     r14
0x18009c989  pop     r13
0x18009c98b  pop     r12
0x18009c98d  pop     rdi
0x18009c98e  pop     rsi
0x18009c98f  pop     rbx
0x18009c990  pop     rbp
0x18009c991  retn
```
