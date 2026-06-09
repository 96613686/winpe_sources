# Jot::CNotebookPaneManager::CreateAddSectionTreeItem(Jot::IUIFolder *)

- ea: `0x1400b2108`
- end: `0x1400b2378`
- name: `?CreateAddSectionTreeItem@CNotebookPaneManager@Jot@@SAPEAVElement@NetUI@@PEAUIUIFolder@2@@Z`
- size: `624`
- prototype: `struct NetUI::Element *__fastcall(struct Jot::IUIFolder *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x140067d9c`

## callees

- `0x14001c570`
- `0x140020ab0`
- `0x1400218f4`
- `0x140024000`
- `0x14002a850`
- `0x14002a964`
- `0x140038780`
- `0x1400387d8`
- `0x1400479f8`
- `0x140049440`
- `0x1400494a0`
- `0x140049500`
- `0x140056ac0`
- `0x14005b190`
- `0x1400679fc`
- `0x1400683b4`
- `0x14006a030`
- `0x14006ba94`
- `0x1400b2108`
- `0x1400b2378`
- `0x1400b2484`

## import_xrefs

- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x1400b2292`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x1400b2292`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400b2199`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400b2199`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x1400b225d`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x1400b22c4`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x1400b225d`
- `mso40uiWin32Client!__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z` at `0x1400b22c4`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x1400b2235`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x1400b2235`
- `mso40uiWin32Client!__imp_?Initialize@TreeViewItem@NetUI@@QEAAJXZ` at `0x1400b2140`
- `mso40uiWin32Client!__imp_?Initialize@TreeViewItem@NetUI@@QEAAJXZ` at `0x1400b2140`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b21eb`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b226a`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b2325`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b2332`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b21eb`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b226a`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b2325`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400b2332`
- `mso40uiWin32Client!__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z` at `0x1400b2169`
- `mso40uiWin32Client!__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z` at `0x1400b2169`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400b21b8`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400b21b8`
- `mso40uiWin32Client!__imp_?Destroy@Node@NetUI@@QEAAJ_N@Z` at `0x1400b214f`
- `mso40uiWin32Client!__imp_?Destroy@Node@NetUI@@QEAAJ_N@Z` at `0x1400b214f`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400b220d`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400b220d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct NetUI::Element *__fastcall Jot::CNotebookPaneManager::CreateAddSectionTreeItem(struct Jot::IUIFolder *a1)
{
  NetUI::TreeViewItem *v2; // rax
  NetUI::Node *v3; // rsi
  Jot *v4; // rcx
  NetUI::Element *IconContainer; // rbx
  struct NetUI::Value *GraphicIcon; // rax
  NetUI::Element *LabelContainer; // rbx
  const wchar_t *v8; // rdx
  int v9; // r8d
  int IndentForLevel; // eax
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rdx
  NetUI::Element *v14; // [rsp+30h] [rbp-9h] BYREF
  NetUI::Element *v15; // [rsp+38h] [rbp-1h] BYREF
  NetUI::Image *v16; // [rsp+40h] [rbp+7h] BYREF
  __int16 v17[2]; // [rsp+48h] [rbp+Fh] BYREF
  int v18; // [rsp+4Ch] [rbp+13h]
  char v19; // [rsp+50h] [rbp+17h]
  __int64 v20; // [rsp+58h] [rbp+1Fh]
  wchar_t *v21[3]; // [rsp+60h] [rbp+27h] BYREF
  unsigned __int64 v22; // [rsp+78h] [rbp+3Fh]

  v2 = (NetUI::TreeViewItem *)NetUI::HNewImpl<Jot::CNavBarAddSectionTreeViewItem>();
  v3 = v2;
  if ( v2 && (int)NetUI::TreeViewItem::Initialize(v2) < 0 )
  {
    NetUI::Node::Destroy(v3, 1);
    v3 = 0;
  }
  NetUI::TreeViewItem::SetHasChildren(v3, 1);
  NetUI::TreeViewItem::SetIsCollapsed(v3, 0, 0);
  NetUI::Element::SetExpandToFillHoriz(v3, 1);
  v15 = 0;
  Jot::CTVIAddSectionButton::Create(&v15, v3, a1);
  NetUI::Element::SetLayout(v15, 5);
  NetUI::Element::SetExpandToFillVert(v15, 1);
  v14 = 0;
  NetUI::Element::Create(0, &v14);
  IconContainer = Jot::CreateIconContainer(v4);
  NetUI::Element::SetWidthPixels(IconContainer, 20, 0);
  NetUI::Element::SetHeightPixels(IconContainer, 20, 0);
  NetUI::Node::Add(v14, (struct Node *)IconContainer);
  NetUI::Node::SetStyleClass(v14, L"NotebookPaneAddSectionItem");
  v16 = 0;
  NetUI::Image::Create(&v16);
  v17[0] = -255;
  v18 = 2143289344;
  v19 = 1;
  v20 = 0;
  GraphicIcon = (struct NetUI::Value *)NetUI::Value::CreateGraphicIcon(9079, v17);
  NetUI::Image::SetSrc(v16, GraphicIcon);
  NetUI::Element::SetPadding(v16, 6, 0, 0, 0);
  NetUI::Node::Add(IconContainer, (struct Node *)v16);
  LabelContainer = Jot::CNotebookPaneManager::CreateLabelContainer(v14);
  NetUI::Element::SetTextStyle(LabelContainer, 2);
  Jot::LoadStringFromTheResourceDll(v21, 3396200133LL);
  v8 = (const wchar_t *)v21;
  if ( v22 > 7 )
    v8 = v21[0];
  NetUI::Element::SetContentString(LabelContainer, v8);
  NetUI::Element::SetPadding(LabelContainer, 5, 0, 0, 0);
  IndentForLevel = Jot::GetIndentForLevel(v14, (struct NetUI::Element *)1, v9);
  NetUI::Element::SetIndentBy(v14, IndentForLevel);
  NetUI::Element::SetAlignChildren(v14, 4);
  v11 = (const wchar_t *)v21;
  if ( v22 > 7 )
    v11 = v21[0];
  NetUI::Element::SetAccessibleDescription(v3, v11);
  v12 = (const wchar_t *)v21;
  if ( v22 > 7 )
    v12 = v21[0];
  NetUI::Element::SetScreenTip(v3, v12);
  NetUI::Node::Add(v15, (struct Node *)v14);
  NetUI::Node::Add(v3, (struct Node *)v15);
  if ( v22 > 7 )
    std::_Deallocate<16>(v21[0], 2 * v22 + 2);
  return v3;
}

```

## disassembly

```asm
0x1400b2108  mov     [rsp-8+arg_8], rbx
0x1400b210d  mov     [rsp-8+arg_10], rsi
0x1400b2112  push    rbp
0x1400b2113  lea     rbp, [rsp-57h]
0x1400b2118  sub     rsp, 90h
0x1400b211f  mov     rax, cs:__security_cookie
0x1400b2126  xor     rax, rsp
0x1400b2129  mov     [rbp+57h+var_10], rax
0x1400b212d  mov     rbx, rcx
0x1400b2130  call    ??$HNewImpl@VCNavBarAddSectionTreeViewItem@Jot@@@NetUI@@YAPEAVCNavBarAddSectionTreeViewItem@Jot@@XZ; NetUI::HNewImpl<Jot::CNavBarAddSectionTreeViewItem>(void)
0x1400b2135  mov     rsi, rax
0x1400b2138  test    rax, rax
0x1400b213b  jz      short loc_1400B2157
0x1400b213d  mov     rcx, rax
0x1400b2140  call    cs:__imp_?Initialize@TreeViewItem@NetUI@@QEAAJXZ; NetUI::TreeViewItem::Initialize(void)
0x1400b2146  test    eax, eax
0x1400b2148  jns     short loc_1400B2157
0x1400b214a  mov     dl, 1
0x1400b214c  mov     rcx, rsi
0x1400b214f  call    cs:__imp_?Destroy@Node@NetUI@@QEAAJ_N@Z; NetUI::Node::Destroy(bool)
0x1400b2155  xor     esi, esi
0x1400b2157  mov     dl, 1; bool
0x1400b2159  mov     rcx, rsi; this
0x1400b215c  call    ?SetHasChildren@TreeViewItem@NetUI@@QEAAJ_N@Z; NetUI::TreeViewItem::SetHasChildren(bool)
0x1400b2161  xor     r8d, r8d
0x1400b2164  xor     edx, edx
0x1400b2166  mov     rcx, rsi
0x1400b2169  call    cs:__imp_?SetIsCollapsed@TreeViewItem@NetUI@@QEAAJ_N0@Z; NetUI::TreeViewItem::SetIsCollapsed(bool,bool)
0x1400b216f  mov     dl, 1; bool
0x1400b2171  mov     rcx, rsi; this
0x1400b2174  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x1400b2179  mov     [rbp+57h+var_58], 0
0x1400b2181  mov     r8, rbx; struct Jot::IUIFolder *
0x1400b2184  mov     rdx, rsi; struct Jot::CNavBarAddSectionTreeViewItem *
0x1400b2187  lea     rcx, [rbp+57h+var_58]; struct NetUI::Element **
0x1400b218b  call    ?Create@CTVIAddSectionButton@Jot@@SAJPEAPEAVElement@NetUI@@PEAVCNavBarAddSectionTreeViewItem@2@PEAUIUIFolder@2@@Z; Jot::CTVIAddSectionButton::Create(NetUI::Element * *,Jot::CNavBarAddSectionTreeViewItem *,Jot::IUIFolder *)
0x1400b2190  mov     edx, 5
0x1400b2195  mov     rcx, [rbp+57h+var_58]
0x1400b2199  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x1400b219f  mov     dl, 1; bool
0x1400b21a1  mov     rcx, [rbp+57h+var_58]; this
0x1400b21a5  call    ?SetExpandToFillVert@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillVert(bool)
0x1400b21aa  mov     [rbp+57h+var_60], 0
0x1400b21b2  lea     rdx, [rbp+57h+var_60]
0x1400b21b6  xor     ecx, ecx
0x1400b21b8  call    cs:__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z; NetUI::Element::Create(uint,NetUI::Element * *)
0x1400b21be  call    ?CreateIconContainer@Jot@@YAPEAVElement@NetUI@@XZ; Jot::CreateIconContainer(void)
0x1400b21c3  mov     rbx, rax
0x1400b21c6  xor     r8d, r8d; int
0x1400b21c9  lea     edx, [r8+14h]; int
0x1400b21cd  mov     rcx, rax; this
0x1400b21d0  call    ?SetWidthPixels@Element@NetUI@@QEAAJHH@Z; NetUI::Element::SetWidthPixels(int,int)
0x1400b21d5  xor     r8d, r8d; int
0x1400b21d8  lea     edx, [r8+14h]; int
0x1400b21dc  mov     rcx, rbx; this
0x1400b21df  call    ?SetHeightPixels@Element@NetUI@@QEAAJHH@Z; NetUI::Element::SetHeightPixels(int,int)
0x1400b21e4  mov     rdx, rbx
0x1400b21e7  mov     rcx, [rbp+57h+var_60]
0x1400b21eb  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400b21f1  lea     rdx, aNotebookpanead; "NotebookPaneAddSectionItem"
0x1400b21f8  mov     rcx, [rbp+57h+var_60]; this
0x1400b21fc  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x1400b2201  mov     [rbp+57h+var_50], 0
0x1400b2209  lea     rcx, [rbp+57h+var_50]
0x1400b220d  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x1400b2213  mov     [rbp+57h+var_48], 0FF01h
0x1400b2219  mov     [rbp+57h+var_44], 7FC00000h
0x1400b2220  mov     [rbp+57h+var_40], 1
0x1400b2224  mov     [rbp+57h+var_38], 0
0x1400b222c  lea     rdx, [rbp+57h+var_48]
0x1400b2230  mov     ecx, 2377h
0x1400b2235  call    cs:__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z; NetUI::Value::CreateGraphicIcon(Mso::IconId,NetUI::CreateIconParams const &)
0x1400b223b  mov     rdx, rax; struct NetUI::Value *
0x1400b223e  mov     rcx, [rbp+57h+var_50]; this
0x1400b2242  call    ?SetSrc@Image@NetUI@@QEAAJPEAVValue@2@@Z; NetUI::Image::SetSrc(NetUI::Value *)
0x1400b2247  mov     [rsp+90h+var_70], 0
0x1400b224f  xor     r9d, r9d
0x1400b2252  xor     r8d, r8d
0x1400b2255  lea     edx, [r9+6]
0x1400b2259  mov     rcx, [rbp+57h+var_50]
0x1400b225d  call    cs:__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z; NetUI::Element::SetPadding(int,int,int,int)
0x1400b2263  mov     rdx, [rbp+57h+var_50]
0x1400b2267  mov     rcx, rbx
0x1400b226a  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400b2270  mov     rcx, [rbp+57h+var_60]; this
0x1400b2274  call    ?CreateLabelContainer@CNotebookPaneManager@Jot@@CAPEAVLabel@NetUI@@PEAVElement@4@@Z; Jot::CNotebookPaneManager::CreateLabelContainer(NetUI::Element *)
0x1400b2279  mov     rbx, rax
0x1400b227c  mov     edx, 2; int
0x1400b2281  mov     rcx, rax; this
0x1400b2284  call    ?SetTextStyle@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetTextStyle(int)
0x1400b2289  mov     edx, 0CA6DE6C5h
0x1400b228e  lea     rcx, [rbp+57h+var_30]
0x1400b2292  call    cs:__imp_?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x1400b2298  nop
0x1400b2299  lea     rdx, [rbp+57h+var_30]
0x1400b229d  cmp     [rbp+57h+var_18], 7
0x1400b22a2  cmova   rdx, [rbp+57h+var_30]; wchar_t *
0x1400b22a7  mov     rcx, rbx; this
0x1400b22aa  call    ?SetContentString@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetContentString(wchar_t const *)
0x1400b22af  mov     [rsp+90h+var_70], 0
0x1400b22b7  xor     r9d, r9d
0x1400b22ba  xor     r8d, r8d
0x1400b22bd  lea     edx, [r9+5]
0x1400b22c1  mov     rcx, rbx
0x1400b22c4  call    cs:__imp_?SetPadding@Element@NetUI@@QEAAJHHHH@Z; NetUI::Element::SetPadding(int,int,int,int)
0x1400b22ca  mov     edx, 1; struct NetUI::Element *
0x1400b22cf  mov     rcx, [rbp+57h+var_60]; this
0x1400b22d3  call    ?GetIndentForLevel@Jot@@YAHPEAVElement@NetUI@@H@Z; Jot::GetIndentForLevel(NetUI::Element *,int)
0x1400b22d8  mov     edx, eax; int
0x1400b22da  mov     rcx, [rbp+57h+var_60]; this
0x1400b22de  call    ?SetIndentBy@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetIndentBy(int)
0x1400b22e3  mov     edx, 4; int
0x1400b22e8  mov     rcx, [rbp+57h+var_60]; this
0x1400b22ec  call    ?SetAlignChildren@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetAlignChildren(int)
0x1400b22f1  lea     rdx, [rbp+57h+var_30]
0x1400b22f5  cmp     [rbp+57h+var_18], 7
0x1400b22fa  cmova   rdx, [rbp+57h+var_30]; wchar_t *
0x1400b22ff  mov     rcx, rsi; this
0x1400b2302  call    ?SetAccessibleDescription@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetAccessibleDescription(wchar_t const *)
0x1400b2307  lea     rdx, [rbp+57h+var_30]
0x1400b230b  cmp     [rbp+57h+var_18], 7
0x1400b2310  cmova   rdx, [rbp+57h+var_30]; wchar_t *
0x1400b2315  mov     rcx, rsi; this
0x1400b2318  call    ?SetScreenTip@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetScreenTip(wchar_t const *)
0x1400b231d  mov     rdx, [rbp+57h+var_60]
0x1400b2321  mov     rcx, [rbp+57h+var_58]
0x1400b2325  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400b232b  mov     rdx, [rbp+57h+var_58]
0x1400b232f  mov     rcx, rsi
0x1400b2332  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400b2338  nop
0x1400b2339  mov     rdx, [rbp+57h+var_18]
0x1400b233d  cmp     rdx, 7
0x1400b2341  jbe     short loc_1400B2354
0x1400b2343  lea     rdx, ds:2[rdx*2]
0x1400b234b  mov     rcx, [rbp+57h+var_30]
0x1400b234f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400b2354  mov     rax, rsi
0x1400b2357  mov     rcx, [rbp+57h+var_10]
0x1400b235b  xor     rcx, rsp; StackCookie
0x1400b235e  call    __security_check_cookie
0x1400b2363  lea     r11, [rsp+90h+var_s0]
0x1400b236b  mov     rbx, [r11+18h]
0x1400b236f  mov     rsi, [r11+20h]
0x1400b2373  mov     rsp, r11
0x1400b2376  pop     rbp
0x1400b2377  retn
```
