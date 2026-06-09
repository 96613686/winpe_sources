# ItemRowLayout::_RecomputeScrollTickCount(void)

- ea: `0x180082d34`
- end: `0x180082e8e`
- name: `?_RecomputeScrollTickCount@ItemRowLayout@@AEAAXXZ`
- size: `346`
- prototype: `void __fastcall(ItemRowLayout *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800826a0`
- `0x180082c70`

## callees

- `0x180082d34`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082dec`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082e1f`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082e78`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082dec`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082e1f`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180082e78`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082d80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082df5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082e28`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082e81`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082d80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082df5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082e28`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180082e81`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180082d75`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180082d75`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082dc9`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082e01`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082e55`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082dc9`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082e01`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x180082e55`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180082d69`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180082d69`

## pseudocode

```c
void __fastcall ItemRowLayout::_RecomputeScrollTickCount(ItemRowLayout *this)
{
  DirectUI::Value *Value; // rbx
  int Int; // esi
  __int64 v4; // rcx
  struct DirectUI::Value *v5; // rax
  DirectUI::Value *v6; // rsi
  __int64 v7; // rcx
  struct DirectUI::Value *v8; // rax
  DirectUI::Value *v9; // rsi
  struct DirectUI::Value *v10; // rax
  DirectUI::Value *v11; // rsi
  _BYTE v12[24]; // [rsp+30h] [rbp-78h] BYREF
  int v13; // [rsp+48h] [rbp-60h]
  unsigned int v14; // [rsp+74h] [rbp-34h]
  unsigned int v15; // [rsp+7Ch] [rbp-2Ch]

  Value = DirectUI::Element::GetValue(this, ItemLayout::SectionCountProp, 2, 0);
  Int = DirectUI::Value::GetInt(Value);
  DirectUI::Value::Release(Value);
  if ( Int )
  {
    memset_0(v12, 0, 0x58u);
    v4 = *(_QWORD *)this;
    v13 = -1;
    (*(void (__fastcall **)(ItemRowLayout *, _QWORD, _QWORD, _BYTE *))(v4 + 448))(this, (unsigned int)(Int - 1), 0, v12);
    v5 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(v15, 0);
    v6 = v5;
    if ( v5 )
    {
      DirectUI::Element::SetValue(this, ItemLayout::ScrollTickCountProp, 1, v5);
      DirectUI::Value::Release(v6);
    }
    v7 = v14;
  }
  else
  {
    v10 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(0, 0);
    v11 = v10;
    if ( v10 )
    {
      DirectUI::Element::SetValue(this, ItemLayout::ScrollTickCountProp, 1, v10);
      DirectUI::Value::Release(v11);
    }
    v7 = 0;
  }
  v8 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(v7, 0);
  v9 = v8;
  if ( v8 )
  {
    DirectUI::Element::SetValue(this, ItemLayout::RowCountProp, 1, v8);
    DirectUI::Value::Release(v9);
  }
}

```

## disassembly

```asm
0x180082d34  mov     [rsp+arg_8], rbx
0x180082d39  mov     [rsp+arg_10], rsi
0x180082d3e  push    rdi
0x180082d3f  sub     rsp, 0A0h
0x180082d46  mov     rax, cs:__security_cookie
0x180082d4d  xor     rax, rsp
0x180082d50  mov     [rsp+0A8h+var_18], rax
0x180082d58  xor     r9d, r9d
0x180082d5b  lea     rdx, ?SectionCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::SectionCountProp(void)
0x180082d62  mov     rdi, rcx
0x180082d65  lea     r8d, [r9+2]
0x180082d69  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180082d6f  mov     rcx, rax
0x180082d72  mov     rbx, rax
0x180082d75  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180082d7b  mov     rcx, rbx
0x180082d7e  mov     esi, eax
0x180082d80  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082d86  xor     edx, edx; Val
0x180082d88  test    esi, esi
0x180082d8a  jz      loc_180082E53
0x180082d90  lea     r8d, [rdx+58h]; Size
0x180082d94  lea     rcx, [rsp+0A8h+var_78]; void *
0x180082d99  call    memset_0
0x180082d9e  mov     rcx, [rdi]
0x180082da1  lea     edx, [rsi-1]
0x180082da4  lea     r9, [rsp+0A8h+var_78]
0x180082da9  mov     [rsp+0A8h+var_60], 0FFFFFFFFh
0x180082db1  xor     r8d, r8d
0x180082db4  mov     rax, [rcx+1C0h]
0x180082dbb  mov     rcx, rdi
0x180082dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082dc3  mov     ecx, [rsp+0A8h+var_2C]
0x180082dc7  xor     edx, edx
0x180082dc9  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x180082dcf  mov     rsi, rax
0x180082dd2  mov     ebx, 1
0x180082dd7  test    rax, rax
0x180082dda  jz      short loc_180082DFB
0x180082ddc  mov     r9, rax
0x180082ddf  lea     rdx, ?ScrollTickCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ScrollTickCountProp(void)
0x180082de6  mov     r8d, ebx
0x180082de9  mov     rcx, rdi
0x180082dec  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180082df2  mov     rcx, rsi
0x180082df5  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082dfb  mov     ecx, [rsp+0A8h+var_34]
0x180082dff  xor     edx, edx
0x180082e01  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x180082e07  mov     rsi, rax
0x180082e0a  test    rax, rax
0x180082e0d  jz      short loc_180082E2E
0x180082e0f  mov     r9, rax
0x180082e12  lea     rdx, ?RowCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::RowCountProp(void)
0x180082e19  mov     r8d, ebx
0x180082e1c  mov     rcx, rdi
0x180082e1f  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180082e25  mov     rcx, rsi
0x180082e28  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082e2e  mov     rcx, [rsp+0A8h+var_18]
0x180082e36  xor     rcx, rsp; StackCookie
0x180082e39  call    __security_check_cookie
0x180082e3e  lea     r11, [rsp+0A8h+var_8]
0x180082e46  mov     rbx, [r11+18h]
0x180082e4a  mov     rsi, [r11+20h]
0x180082e4e  mov     rsp, r11
0x180082e51  pop     rdi
0x180082e52  retn
0x180082e53  xor     ecx, ecx
0x180082e55  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x180082e5b  mov     rsi, rax
0x180082e5e  mov     ebx, 1
0x180082e63  test    rax, rax
0x180082e66  jz      short loc_180082E87
0x180082e68  mov     r9, rax
0x180082e6b  lea     rdx, ?ScrollTickCountProp@ItemLayout@@SAPEBUPropertyInfo@DirectUI@@XZ; ItemLayout::ScrollTickCountProp(void)
0x180082e72  mov     r8d, ebx
0x180082e75  mov     rcx, rdi
0x180082e78  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180082e7e  mov     rcx, rsi
0x180082e81  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180082e87  xor     ecx, ecx
0x180082e89  jmp     loc_180082DFF
```
