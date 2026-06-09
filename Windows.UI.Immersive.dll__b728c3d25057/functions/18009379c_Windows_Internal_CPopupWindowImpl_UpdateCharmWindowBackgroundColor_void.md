# Windows::Internal::CPopupWindowImpl::_UpdateCharmWindowBackgroundColor(void)

- ea: `0x18009379c`
- end: `0x180093941`
- name: `?_UpdateCharmWindowBackgroundColor@CPopupWindowImpl@Internal@Windows@@AEAAXXZ`
- size: `421`
- prototype: `void __fastcall(Windows::Internal::CPopupWindowImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180092b30`

## callees

- `0x18001a360`
- `0x180050ba0`
- `0x18008e8e4`
- `0x18009379c`

## import_xrefs

- `USER32!SetWindowCompositionAttribute` at `0x1800938c4`
- `USER32!SetWindowCompositionAttribute` at `0x1800938c4`
- `UxTheme!IsCompositionActive` at `0x180093875`
- `UxTheme!IsCompositionActive` at `0x180093875`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180093925`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180093925`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800938b6`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800938b6`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800937b7`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800937df`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180093807`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18009391a`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800937b7`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800937df`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180093807`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18009391a`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938d8`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938ea`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938fc`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938d8`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938ea`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x1800938fc`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938cc`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938de`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938f0`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938cc`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938de`
- `DUI70!?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800938f0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800937d3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800937fb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180093823`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800937d3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800937fb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180093823`
- `DUI70!StrToID` at `0x1800937c7`
- `DUI70!StrToID` at `0x1800937ef`
- `DUI70!StrToID` at `0x180093817`
- `DUI70!StrToID` at `0x1800937c7`
- `DUI70!StrToID` at `0x1800937ef`
- `DUI70!StrToID` at `0x180093817`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093843`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093853`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093863`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093843`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093853`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180093863`

## pseudocode

```c
void __fastcall Windows::Internal::CPopupWindowImpl::_UpdateCharmWindowBackgroundColor(
        Windows::Internal::CPopupWindowImpl *this)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rsi
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rbp
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rbx
  unsigned int Color; // ebx
  HWND HWND; // rax
  const struct DirectUI::PropertyInfo *v13; // rax
  const struct DirectUI::PropertyInfo *v14; // rax
  const struct DirectUI::PropertyInfo *v15; // rax
  DirectUI::Element *v16; // rax
  _QWORD v17[3]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v18; // [rsp+38h] [rbp-40h] BYREF

  Element = DirectUI::NativeHWNDHost::GetElement(this);
  v3 = StrToID(L"CharmWindowBorder");
  Descendent = DirectUI::Element::FindDescendent(Element, v3);
  v5 = DirectUI::NativeHWNDHost::GetElement(this);
  v6 = StrToID(L"ContentArea");
  v7 = DirectUI::Element::FindDescendent(v5, v6);
  v8 = DirectUI::NativeHWNDHost::GetElement(this);
  v9 = StrToID(L"TitleBarBackground");
  v10 = DirectUI::Element::FindDescendent(v8, v9);
  if ( (unsigned int)IsHighContrast() )
  {
    DirectUI::Element::SetClass(v7, L"HighContrast");
    DirectUI::Element::SetClass(Descendent, L"HighContrast");
    DirectUI::Element::SetClass(v10, L"HighContrast");
LABEL_3:
    Color = CImmersiveColor::GetColor(41);
    goto LABEL_4;
  }
  v13 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(v7, v13);
  v14 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(Descendent, v14);
  v15 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ClassProp();
  DirectUI::Element::RemoveLocalValue(v10, v15);
  if ( (*((_BYTE *)this + 344) & 1) == 0 )
    goto LABEL_3;
  Color = *((_DWORD *)this + 85);
LABEL_4:
  if ( IsCompositionActive() )
  {
    v17[0] = 19;
    v18 = 0;
    LODWORD(v18) = 1;
    DWORD2(v18) = Color;
    v17[1] = &v18;
    v17[2] = 16;
    HWND = DirectUI::NativeHWNDHost::GetHWND(this);
    SetWindowCompositionAttribute(HWND, v17);
  }
  else
  {
    v16 = DirectUI::NativeHWNDHost::GetElement(this);
    DirectUI::Element::SetBackgroundColor(v16, Color);
  }
}

```

## disassembly

```asm
0x18009379c  push    rbx
0x18009379e  push    rbp
0x18009379f  push    rsi
0x1800937a0  push    rdi
0x1800937a1  sub     rsp, 58h
0x1800937a5  mov     rax, cs:__security_cookie
0x1800937ac  xor     rax, rsp
0x1800937af  mov     [rsp+78h+var_30], rax
0x1800937b4  mov     rdi, rcx
0x1800937b7  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800937bd  lea     rcx, aCharmwindowbor; "CharmWindowBorder"
0x1800937c4  mov     rbx, rax
0x1800937c7  call    cs:__imp_StrToID
0x1800937cd  movzx   edx, ax
0x1800937d0  mov     rcx, rbx
0x1800937d3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800937d9  mov     rcx, rdi
0x1800937dc  mov     rsi, rax
0x1800937df  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800937e5  lea     rcx, aContentarea; "ContentArea"
0x1800937ec  mov     rbx, rax
0x1800937ef  call    cs:__imp_StrToID
0x1800937f5  movzx   edx, ax
0x1800937f8  mov     rcx, rbx
0x1800937fb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180093801  mov     rcx, rdi
0x180093804  mov     rbp, rax
0x180093807  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009380d  lea     rcx, aTitlebarbackgr; "TitleBarBackground"
0x180093814  mov     rbx, rax
0x180093817  call    cs:__imp_StrToID
0x18009381d  movzx   edx, ax
0x180093820  mov     rcx, rbx
0x180093823  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180093829  mov     rbx, rax
0x18009382c  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180093831  test    eax, eax
0x180093833  jz      loc_1800938CC
0x180093839  lea     rdx, aHighcontrast; "HighContrast"
0x180093840  mov     rcx, rbp
0x180093843  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180093849  lea     rdx, aHighcontrast; "HighContrast"
0x180093850  mov     rcx, rsi
0x180093853  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180093859  lea     rdx, aHighcontrast; "HighContrast"
0x180093860  mov     rcx, rbx
0x180093863  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180093869  mov     ecx, 29h ; ')'
0x18009386e  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x180093873  mov     ebx, eax
0x180093875  call    cs:__imp_IsCompositionActive
0x18009387b  mov     rcx, rdi
0x18009387e  test    eax, eax
0x180093880  jz      loc_18009391A
0x180093886  xorps   xmm0, xmm0
0x180093889  mov     [rsp+78h+var_58], 13h
0x180093892  movups  [rsp+78h+var_40], xmm0
0x180093897  lea     rax, [rsp+78h+var_40]
0x18009389c  mov     dword ptr [rsp+78h+var_40], 1
0x1800938a4  mov     dword ptr [rsp+78h+var_40+8], ebx
0x1800938a8  mov     [rsp+78h+var_50], rax
0x1800938ad  mov     [rsp+78h+var_48], 10h
0x1800938b6  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800938bc  mov     rcx, rax
0x1800938bf  lea     rdx, [rsp+78h+var_58]
0x1800938c4  call    cs:__imp_SetWindowCompositionAttribute
0x1800938ca  jmp     short loc_18009392B
0x1800938cc  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x1800938d2  mov     rdx, rax
0x1800938d5  mov     rcx, rbp
0x1800938d8  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x1800938de  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x1800938e4  mov     rdx, rax
0x1800938e7  mov     rcx, rsi
0x1800938ea  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x1800938f0  call    cs:__imp_?ClassProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ClassProp(void)
0x1800938f6  mov     rdx, rax
0x1800938f9  mov     rcx, rbx
0x1800938fc  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const *)
0x180093902  test    byte ptr [rdi+158h], 1
0x180093909  jz      loc_180093869
0x18009390f  mov     ebx, [rdi+154h]
0x180093915  jmp     loc_180093875
0x18009391a  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180093920  mov     rcx, rax
0x180093923  mov     edx, ebx
0x180093925  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x18009392b  mov     rcx, [rsp+78h+var_30]
0x180093930  xor     rcx, rsp; StackCookie
0x180093933  call    __security_check_cookie
0x180093938  add     rsp, 58h
0x18009393c  pop     rdi
0x18009393d  pop     rsi
0x18009393e  pop     rbp
0x18009393f  pop     rbx
0x180093940  retn
```
