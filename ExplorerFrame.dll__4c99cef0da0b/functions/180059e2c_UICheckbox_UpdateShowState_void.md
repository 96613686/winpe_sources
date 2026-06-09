# UICheckbox::_UpdateShowState(void)

- ea: `0x180059e2c`
- end: `0x180059f8e`
- name: `?_UpdateShowState@UICheckbox@@IEAAXXZ`
- size: `354`
- prototype: `void __fastcall(UICheckbox *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180059d60`
- `0x18005a370`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x180059e2c`
- `0x180059f94`
- `0x180210010`

## import_xrefs

- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059e82`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059ecc`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059f51`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059e82`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059ecc`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x180059f51`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059ea3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059eed`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059f76`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059ea3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059eed`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180059f76`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059eac`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059ef6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059f7f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059eac`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059ef6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180059f7f`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180059e3e`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180059e3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UICheckbox::_UpdateShowState(UICheckbox *this)
{
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v3; // rbx
  __int64 v4; // rax
  char ShouldApplyTouchImprovement; // al
  struct DirectUI::Value *v6; // rax
  DirectUI::Value *v7; // rbx
  struct DirectUI::Value *Bool; // rax
  DirectUI::Value *v9; // rsi
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  bool v11; // bl
  struct DirectUI::Value *v12; // rax
  DirectUI::Value *v13; // rbx
  __int64 v14; // [rsp+38h] [rbp+10h] BYREF

  TopLevel = DirectUI::Element::GetTopLevel(this);
  v3 = TopLevel;
  if ( TopLevel )
  {
    v4 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v4 + 80LL))(
           v4,
           UIItemsView::Class) )
    {
      Bool = DirectUI::Value::CreateBool(*((_DWORD *)v3 + 110) != 0);
      v9 = Bool;
      if ( Bool )
      {
        DirectUI::Element::SetValue(this, UICheckbox::ShowCheckboxesProp, 1, Bool);
        DirectUI::Value::Release(v9);
      }
      ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v14);
      v10 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v3 + 37);
      v11 = v10
         && (**v10)(v10, &GUID_b1a43ef3_e085_4107_8332_8f89c1298a8f, &v14) >= 0
         && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14) != 0;
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v14);
      v12 = DirectUI::Value::CreateBool(v11);
      v13 = v12;
      if ( v12 )
      {
        DirectUI::Element::SetValue(this, UICheckbox::SelectionModeProp, 1, v12);
        DirectUI::Value::Release(v13);
      }
    }
  }
  ShouldApplyTouchImprovement = TabletModeHelpers::ShouldApplyTouchImprovement();
  v6 = DirectUI::Value::CreateBool(ShouldApplyTouchImprovement);
  v7 = v6;
  if ( v6 )
  {
    DirectUI::Element::SetValue(this, UICheckbox::TabletModeProp, 1, v6);
    DirectUI::Value::Release(v7);
  }
}

```

## disassembly

```asm
0x180059e2c  mov     [rsp+arg_0], rbx
0x180059e31  mov     [rsp+arg_10], rsi
0x180059e36  push    rdi
0x180059e37  sub     rsp, 20h
0x180059e3b  mov     rdi, rcx
0x180059e3e  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x180059e44  mov     rbx, rax
0x180059e47  test    rax, rax
0x180059e4a  jz      short loc_180059E7B
0x180059e4c  mov     rdx, [rax]
0x180059e4f  mov     rcx, rax
0x180059e52  mov     rax, [rdx+118h]
0x180059e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e5e  mov     r8, rax
0x180059e61  mov     rcx, [rax]
0x180059e64  mov     rax, [rcx+50h]
0x180059e68  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x180059e6f  mov     rcx, r8
0x180059e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e77  test    al, al
0x180059e79  jnz     short loc_180059EC2
0x180059e7b  call    ?ShouldApplyTouchImprovement@TabletModeHelpers@@YA_NW4TouchImprovementSettings@1@@Z; TabletModeHelpers::ShouldApplyTouchImprovement(TabletModeHelpers::TouchImprovementSettings)
0x180059e80  mov     cl, al
0x180059e82  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x180059e88  mov     rbx, rax
0x180059e8b  test    rax, rax
0x180059e8e  jz      short loc_180059EB2
0x180059e90  mov     r9, rax
0x180059e93  mov     r8d, 1
0x180059e99  lea     rdx, ?TabletModeProp@UICheckbox@@SAPEBUPropertyInfo@DirectUI@@XZ; UICheckbox::TabletModeProp(void)
0x180059ea0  mov     rcx, rdi
0x180059ea3  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180059ea9  mov     rcx, rbx
0x180059eac  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180059eb2  mov     rbx, [rsp+28h+arg_0]
0x180059eb7  mov     rsi, [rsp+28h+arg_10]
0x180059ebc  add     rsp, 20h
0x180059ec0  pop     rdi
0x180059ec1  retn
0x180059ec2  cmp     dword ptr [rbx+1B8h], 0
0x180059ec9  setnz   cl
0x180059ecc  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x180059ed2  mov     rsi, rax
0x180059ed5  test    rax, rax
0x180059ed8  jz      short loc_180059EFC
0x180059eda  mov     r9, rax
0x180059edd  mov     r8d, 1
0x180059ee3  lea     rdx, ?ShowCheckboxesProp@UICheckbox@@SAPEBUPropertyInfo@DirectUI@@XZ; UICheckbox::ShowCheckboxesProp(void)
0x180059eea  mov     rcx, rdi
0x180059eed  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180059ef3  mov     rcx, rsi
0x180059ef6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180059efc  lea     rcx, [rsp+28h+arg_8]; void *
0x180059f01  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180059f06  nop
0x180059f07  mov     rcx, [rbx+128h]
0x180059f0e  test    rcx, rcx
0x180059f11  jz      short loc_180059F8A
0x180059f13  mov     rax, [rcx]
0x180059f16  lea     r8, [rsp+28h+arg_8]
0x180059f1b  lea     rdx, _GUID_b1a43ef3_e085_4107_8332_8f89c1298a8f
0x180059f22  mov     rax, [rax]
0x180059f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f2a  test    eax, eax
0x180059f2c  js      short loc_180059F8A
0x180059f2e  mov     rcx, [rsp+28h+arg_8]
0x180059f33  mov     rax, [rcx]
0x180059f36  mov     rax, [rax+28h]
0x180059f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f3f  nop
0x180059f40  test    eax, eax
0x180059f42  setnz   bl
0x180059f45  lea     rcx, [rsp+28h+arg_8]; void *
0x180059f4a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180059f4f  mov     cl, bl
0x180059f51  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x180059f57  mov     rbx, rax
0x180059f5a  test    rax, rax
0x180059f5d  jz      loc_180059E7B
0x180059f63  mov     r9, rax
0x180059f66  mov     r8d, 1
0x180059f6c  lea     rdx, ?SelectionModeProp@UICheckbox@@SAPEBUPropertyInfo@DirectUI@@XZ; UICheckbox::SelectionModeProp(void)
0x180059f73  mov     rcx, rdi
0x180059f76  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180059f7c  mov     rcx, rbx
0x180059f7f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180059f85  jmp     loc_180059E7B
0x180059f8a  xor     bl, bl
0x180059f8c  jmp     short loc_180059F45
```
