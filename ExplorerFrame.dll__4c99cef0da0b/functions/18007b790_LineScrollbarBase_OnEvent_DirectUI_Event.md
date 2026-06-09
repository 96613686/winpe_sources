# LineScrollbarBase::OnEvent(DirectUI::Event *)

- ea: `0x18007b790`
- end: `0x18007b95e`
- name: `?OnEvent@LineScrollbarBase@@UEAAXPEAUEvent@DirectUI@@@Z`
- size: `462`
- prototype: `void __fastcall(LineScrollbarBase *__hidden this, struct DirectUI::Event *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18007b790`
- `0x18007b970`
- `0x18007bbf4`
- `0x180210010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b82a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b878`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b947`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b82a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b878`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18007b947`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18007b8d2`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18007b8d2`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b807`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b855`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b8b5`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b807`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b855`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18007b8b5`
- `DUI70!?PositionProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18007b8ab`
- `DUI70!?MaximumProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18007b800`
- `DUI70!?PageProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18007b84b`
- `DUI70!?OnMaximumChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b81b`
- `DUI70!?OnMaximumChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b81b`
- `DUI70!?OnPageChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b869`
- `DUI70!?OnPageChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b869`
- `DUI70!?OnPositionChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b8c9`
- `DUI70!?OnPositionChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z` at `0x18007b8c9`
- `DUI70!?SyncScrollBar@CCBaseScrollBar@DirectUI@@QEAAXXZ` at `0x18007b88b`
- `DUI70!?SyncScrollBar@CCBaseScrollBar@DirectUI@@QEAAXXZ` at `0x18007b88b`
- `DUI70!?OnEvent@HWNDHost@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18007b7b5`
- `DUI70!?OnEvent@HWNDHost@DirectUI@@UEAAXPEAUEvent@2@@Z` at `0x18007b7b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LineScrollbarBase::OnEvent(LineScrollbarBase *this, struct DirectUI::Event *a2)
{
  DirectUI::BaseScrollBar *v4; // rbp
  struct DirectUI::Value *Value; // rsi
  struct DirectUI::Value *v6; // rsi
  struct DirectUI::Value *v7; // rsi
  int Int; // r15d
  struct DirectUI::BaseScrollBar *v9; // r14
  int ScrollBarRange; // ebp
  double v11; // xmm2_8

  if ( !*((_DWORD *)a2 + 5) && *((char **)a2 + 1) == LineScrollbarBase::DeferUpdateScrollbar[0] )
  {
    *((_DWORD *)this + 92) = 0;
    v4 = (LineScrollbarBase *)((char *)this + 352);
    if ( *((_DWORD *)this + 93) )
    {
      *((_DWORD *)this + 93) = 0;
      Value = DirectUI::Element::GetValue(
                this,
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::CCBaseScrollBar::MaximumProp,
                1,
                0);
      DirectUI::BaseScrollBar::OnMaximumChanged(v4, Value);
      if ( Value )
        DirectUI::Value::Release(Value);
    }
    if ( *((_DWORD *)this + 94) )
    {
      *((_DWORD *)this + 94) = 0;
      v6 = DirectUI::Element::GetValue(
             this,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::CCBaseScrollBar::PageProp,
             1,
             0);
      DirectUI::BaseScrollBar::OnPageChanged(v4, v6);
      if ( v6 )
        DirectUI::Value::Release(v6);
    }
    if ( *((_DWORD *)this + 95) )
    {
      *((_DWORD *)this + 95) = 0;
      v7 = DirectUI::Element::GetValue(
             this,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::CCBaseScrollBar::PositionProp,
             1,
             0);
      DirectUI::BaseScrollBar::OnPositionChanged(v4, v7);
      Int = DirectUI::Value::GetInt(v7);
      v9 = (struct DirectUI::BaseScrollBar *)((unsigned __int64)v4 & -(__int64)(this != 0));
      ScrollBarRange = _GetScrollBarRange(v9);
      v11 = ScrollBarRange <= 0
          ? DOUBLE_N1_0
          : (double)(int)(Int - (*(__int64 (__fastcall **)(struct DirectUI::BaseScrollBar *))(*(_QWORD *)v9 + 24LL))(v9))
          * 100.0
          / (double)ScrollBarRange;
      DUI_UiaRaiseScrollbarPosChangeEvent(this, *((double *)this + 48), v11);
      *((_QWORD *)this + 48) = 0;
      if ( v7 )
        DirectUI::Value::Release(v7);
    }
    DirectUI::CCBaseScrollBar::SyncScrollBar(this);
    *((_BYTE *)a2 + 16) = 1;
  }
  if ( !*((_BYTE *)a2 + 16) )
    DirectUI::HWNDHost::OnEvent(this, a2);
}

```

## disassembly

```asm
0x18007b790  push    rbx
0x18007b792  push    rbp
0x18007b793  push    rsi
0x18007b794  push    rdi
0x18007b795  push    r14
0x18007b797  push    r15
0x18007b799  sub     rsp, 28h
0x18007b79d  mov     rdi, rdx
0x18007b7a0  mov     rbx, rcx
0x18007b7a3  cmp     dword ptr [rdx+14h], 0
0x18007b7a7  jz      short loc_18007B7C8
0x18007b7a9  cmp     byte ptr [rdi+10h], 0
0x18007b7ad  jnz     short loc_18007B7BB
0x18007b7af  mov     rdx, rdi
0x18007b7b2  mov     rcx, rbx
0x18007b7b5  call    cs:__imp_?OnEvent@HWNDHost@DirectUI@@UEAAXPEAUEvent@2@@Z; DirectUI::HWNDHost::OnEvent(DirectUI::Event *)
0x18007b7bb  add     rsp, 28h
0x18007b7bf  pop     r15
0x18007b7c1  pop     r14
0x18007b7c3  pop     rdi
0x18007b7c4  pop     rsi
0x18007b7c5  pop     rbp
0x18007b7c6  pop     rbx
0x18007b7c7  retn
0x18007b7c8  mov     rax, cs:?DeferUpdateScrollbar@LineScrollbarBase@@0VUID@@A; UID LineScrollbarBase::DeferUpdateScrollbar
0x18007b7cf  cmp     [rdx+8], rax
0x18007b7d3  jnz     short loc_18007B7A9
0x18007b7d5  mov     dword ptr [rcx+170h], 0
0x18007b7df  lea     rbp, [rcx+160h]
0x18007b7e6  cmp     dword ptr [rcx+174h], 0
0x18007b7ed  jz      short loc_18007B831
0x18007b7ef  mov     dword ptr [rcx+174h], 0
0x18007b7f9  xor     r9d, r9d
0x18007b7fc  lea     r8d, [r9+1]
0x18007b800  mov     rdx, cs:__imp_?MaximumProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::CCBaseScrollBar::MaximumProp(void)
0x18007b807  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007b80d  mov     rsi, rax
0x18007b810  mov     [rsp+58h+arg_8], rax
0x18007b815  mov     rdx, rax
0x18007b818  mov     rcx, rbp
0x18007b81b  call    cs:__imp_?OnMaximumChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z; DirectUI::BaseScrollBar::OnMaximumChanged(DirectUI::Value *)
0x18007b821  nop
0x18007b822  test    rsi, rsi
0x18007b825  jz      short loc_18007B831
0x18007b827  mov     rcx, rsi
0x18007b82a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007b830  nop
0x18007b831  cmp     dword ptr [rbx+178h], 0
0x18007b838  jz      short loc_18007B87F
0x18007b83a  mov     dword ptr [rbx+178h], 0
0x18007b844  xor     r9d, r9d
0x18007b847  lea     r8d, [r9+1]
0x18007b84b  mov     rdx, cs:__imp_?PageProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::CCBaseScrollBar::PageProp(void)
0x18007b852  mov     rcx, rbx
0x18007b855  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007b85b  mov     rsi, rax
0x18007b85e  mov     [rsp+58h+arg_8], rax
0x18007b863  mov     rdx, rax
0x18007b866  mov     rcx, rbp
0x18007b869  call    cs:__imp_?OnPageChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z; DirectUI::BaseScrollBar::OnPageChanged(DirectUI::Value *)
0x18007b86f  nop
0x18007b870  test    rsi, rsi
0x18007b873  jz      short loc_18007B87F
0x18007b875  mov     rcx, rsi
0x18007b878  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007b87e  nop
0x18007b87f  cmp     dword ptr [rbx+17Ch], 0
0x18007b886  jnz     short loc_18007B89A
0x18007b888  mov     rcx, rbx
0x18007b88b  call    cs:__imp_?SyncScrollBar@CCBaseScrollBar@DirectUI@@QEAAXXZ; DirectUI::CCBaseScrollBar::SyncScrollBar(void)
0x18007b891  mov     byte ptr [rdi+10h], 1
0x18007b895  jmp     loc_18007B7A9
0x18007b89a  mov     dword ptr [rbx+17Ch], 0
0x18007b8a4  xor     r9d, r9d
0x18007b8a7  lea     r8d, [r9+1]
0x18007b8ab  mov     rdx, cs:__imp_?PositionProp@CCBaseScrollBar@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::CCBaseScrollBar::PositionProp(void)
0x18007b8b2  mov     rcx, rbx
0x18007b8b5  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18007b8bb  mov     rsi, rax
0x18007b8be  mov     [rsp+58h+arg_8], rax
0x18007b8c3  mov     rdx, rax
0x18007b8c6  mov     rcx, rbp
0x18007b8c9  call    cs:__imp_?OnPositionChanged@BaseScrollBar@DirectUI@@QEAAXPEAVValue@2@@Z; DirectUI::BaseScrollBar::OnPositionChanged(DirectUI::Value *)
0x18007b8cf  mov     rcx, rsi
0x18007b8d2  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18007b8d8  mov     r15d, eax
0x18007b8db  mov     rcx, rbx
0x18007b8de  neg     rcx
0x18007b8e1  sbb     r14, r14
0x18007b8e4  and     r14, rbp
0x18007b8e7  mov     rcx, r14; struct DirectUI::BaseScrollBar *
0x18007b8ea  call    ?_GetScrollBarRange@@YAHPEAVBaseScrollBar@DirectUI@@@Z; _GetScrollBarRange(DirectUI::BaseScrollBar *)
0x18007b8ef  mov     ebp, eax
0x18007b8f1  test    eax, eax
0x18007b8f3  jle     short loc_18007B953
0x18007b8f5  mov     rdx, [r14]
0x18007b8f8  mov     rcx, r14
0x18007b8fb  mov     rax, [rdx+18h]
0x18007b8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b904  sub     r15d, eax
0x18007b907  movd    xmm2, r15d
0x18007b90c  cvtdq2pd xmm2, xmm2
0x18007b910  mulsd   xmm2, cs:__real@4059000000000000
0x18007b918  movd    xmm0, ebp
0x18007b91c  cvtdq2pd xmm0, xmm0
0x18007b920  divsd   xmm2, xmm0; double
0x18007b924  movsd   xmm1, qword ptr [rbx+180h]; double
0x18007b92c  mov     rcx, rbx; struct LineScrollbarBase *
0x18007b92f  call    ?DUI_UiaRaiseScrollbarPosChangeEvent@@YAJPEAVLineScrollbarBase@@NN@Z; DUI_UiaRaiseScrollbarPosChangeEvent(LineScrollbarBase *,double,double)
0x18007b934  mov     qword ptr [rbx+180h], 0
0x18007b93f  test    rsi, rsi
0x18007b942  jz      short loc_18007B94E
0x18007b944  mov     rcx, rsi
0x18007b947  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18007b94d  nop
0x18007b94e  jmp     loc_18007B888
0x18007b953  movsd   xmm2, cs:__real@bff0000000000000
0x18007b95b  jmp     short loc_18007B924
```
