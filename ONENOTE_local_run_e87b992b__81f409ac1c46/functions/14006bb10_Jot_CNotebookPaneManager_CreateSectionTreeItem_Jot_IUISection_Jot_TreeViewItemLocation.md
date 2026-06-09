# Jot::CNotebookPaneManager::CreateSectionTreeItem(Jot::IUISection *,Jot::TreeViewItemLocation)

- ea: `0x14006bb10`
- end: `0x14006bec3`
- name: `?CreateSectionTreeItem@CNotebookPaneManager@Jot@@SAPEAVElement@NetUI@@PEAUIUISection@2@W4TreeViewItemLocation@2@@Z`
- size: `947`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: ``

## callers

- `0x140067d9c`
- `0x14009189c`

## callees

- `0x140019348`
- `0x14001c570`
- `0x1400229b4`
- `0x140024000`
- `0x14002a850`
- `0x14002a964`
- `0x140038780`
- `0x1400488d0`
- `0x140048a58`
- `0x1400494a0`
- `0x140049500`
- `0x140049970`
- `0x140049a5c`
- `0x140049aa4`
- `0x140049adc`
- `0x140055c38`
- `0x1400569a0`
- `0x140056ac0`
- `0x140057580`
- `0x14005b190`
- `0x14005b80c`
- `0x14006a030`
- `0x14006ba94`
- `0x14006bb10`
- `0x140078564`
- `0x1400b058c`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14006bce6`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14006bcff`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14006bce6`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14006bcff`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14006bd8b`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14006bd8b`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14006bd96`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14006bd96`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x14006bda7`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x14006bda7`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14006bccc`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14006bccc`
- `mso40uiWin32Client!__imp_?HAlloc@NetUI@@YAPEAX_K@Z` at `0x14006bd28`
- `mso40uiWin32Client!__imp_?HAlloc@NetUI@@YAPEAX_K@Z` at `0x14006bd28`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bbb8`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bbda`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bc49`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bc6b`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bbb8`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bbda`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bc49`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14006bc6b`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x14006bd61`
- `mso40uiWin32Client!__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z` at `0x14006bd61`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14006bbcc`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14006bc5d`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14006bbcc`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14006bc5d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14006be0b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14006be0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
NetUI::Node *__fastcall Jot::CNotebookPaneManager::CreateSectionTreeItem(__int64 a1, int a2)
{
  NetUI::Node *v4; // rsi
  Jot *v5; // rcx
  struct Node *IconContainer; // r15
  NetUI::Node *v7; // rbx
  NetUI::Node *LabelContainer; // r14
  Jot *v9; // rcx
  struct Node *v10; // rbx
  NetUI::Element *v11; // rbx
  struct NetUI::Value *GraphicIcon; // rax
  Jot *v13; // rcx
  Jot *v14; // rcx
  int v15; // r8d
  unsigned __int64 v16; // rdx
  Jot::CTVISectionListener *v17; // rax
  Jot::CTVISectionListener *v18; // rbx
  const wchar_t *v19; // rax
  const struct NetUI::IClassInfo *StaticClassInfo; // rax
  NetUI::TreeViewItem *v21; // rdi
  void *v22; // rdx
  NetUI::Element *v24; // [rsp+30h] [rbp-D0h] BYREF
  NetUI::Element *v25; // [rsp+38h] [rbp-C8h] BYREF
  NetUI::Node *v26; // [rsp+40h] [rbp-C0h] BYREF
  Jot::CTVISectionListener *v27; // [rsp+48h] [rbp-B8h] BYREF
  NetUI::TreeViewItem *v28; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v29[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+5Ch] [rbp-A4h]
  char v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[32]; // [rsp+70h] [rbp-90h] BYREF
  char v34[40]; // [rsp+90h] [rbp-70h] BYREF
  Mso::Memory *v35; // [rsp+B8h] [rbp-48h]
  char v36; // [rsp+D0h] [rbp-30h] BYREF

  v28 = 0;
  v25 = 0;
  v27 = 0;
  Jot::CNotebookPaneManager::CreateBasicTreeViewItem(&v28, &v25, &v27, a1, a2, 0);
  v4 = v28;
  NetUI::Node::SetStyleClass(v28, L"NotebookPanePaddedContainer");
  NetUI::Node::SetStyleClass(v25, L"NotebookPaneSectionItem");
  IconContainer = (struct Node *)Jot::CreateIconContainer(v5);
  NetUI::Node::Add(v25, IconContainer);
  v26 = 0;
  NetUI::Image::Create(&v26);
  NetUI::Node::Add((NetUI::Node *)IconContainer, (struct Node *)v26);
  v7 = (NetUI::Node *)NetUI::nui_control_cast<NetUI::Image>(v26);
  NetUI::Node::SetStyleClass(v7, L"NotebookPaneSectionItemImage");
  NetUI::Element::SetIsAccessible(v7, 0);
  NetUI::Node::SetID(v7, 0xF44u);
  LabelContainer = Jot::CNotebookPaneManager::CreateLabelContainer(v25);
  NetUI::Node::SetStyleClass(LabelContainer, L"NotebookPaneSectionItemLabel");
  NetUI::Element::SetIsAccessible(LabelContainer, 0);
  v10 = (struct Node *)Jot::CreateIconContainer(v9);
  NetUI::Node::Add(v25, v10);
  v24 = 0;
  NetUI::Image::Create(&v24);
  NetUI::Node::Add((NetUI::Node *)v10, (struct Node *)v24);
  NetUI::Node::SetID(v24, L"NotebookPaneSectionItemErrorIcon");
  NetUI::Element::SetIsVisible(v24, 0);
  v11 = (NetUI::Element *)NetUI::nui_control_cast<NetUI::Image>(v24);
  NetUI::Element::SetIsAccessible(v11, 0);
  v29[0] = -254;
  v30 = 2143289344;
  v31 = 1;
  v32 = 0;
  GraphicIcon = (struct NetUI::Value *)NetUI::Value::CreateGraphicIcon(3049, v29);
  NetUI::Image::SetSrc(v11, GraphicIcon);
  if ( a1 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 432LL))(a1) )
    NetUI::Element::SetIsVisible(v24, 1);
  if ( Jot::IsLicensedForFluentUI(v13) )
    NetUI::Node::SetStyleClass(v11, L"ErrorIconImage");
  if ( Jot::IsLicensedForFluentUI(v14) )
  {
    if ( a2 == 2 )
    {
      NetUI::Element::SetWidthPixels((NetUI::Element *)IconContainer, 20, 0);
      NetUI::Element::SetHeightPixels((NetUI::Element *)IconContainer, 20, 0);
    }
    NetUI::Element::SetTextStyle(LabelContainer, 2);
  }
  else
  {
    Jot::NavigationUI::ApplyTextStyle(LabelContainer, (struct NetUI::Element *)0x15D, v15);
  }
  v27 = 0;
  v17 = (Jot::CTVISectionListener *)NetUI::HAlloc((NetUI *)0x88, v16);
  v18 = v17;
  if ( v17 )
    Jot::CTVISectionListener::CTVISectionListener(v17);
  v27 = v18;
  MsoCF::CIPtr<Jot::IFloatieMSAA,Jot::IFloatieMSAA>::Assign((char *)v18 + 64, a1);
  *((_BYTE *)v18 + 77) = 1;
  *((_DWORD *)v18 + 22) = a2;
  NetUI::Node::AddListener(v4, v18, 1);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v33);
  Jot::CWzInBuffer::SetFromResource(
    (Jot::CWzInBuffer *)v33,
    *((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62),
    0x4E388FC0u);
  v19 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v33);
  NetUI::Element::SetAccessibleDescription(v4, v19);
  StaticClassInfo = (const struct NetUI::IClassInfo *)NetUI::TreeViewItem::GetStaticClassInfo();
  if ( v4 && NetUI::Node::IsSubclassOf(v4, StaticClassInfo) )
    v21 = v4;
  else
    v21 = 0;
  if ( v21 )
    _castguard_slow_path_check_user_handled(*(_QWORD *)v21, 51856, 2064);
  NetUI::TreeViewItem::SetHasChildren(v21, 0);
  NetUI::Element::SetAlignChildren(v25, 4);
  if ( v35 != (Mso::Memory *)&v36 )
    Mso::Memory::Free(v35, v22);
  std::wstring::~wstring(v34);
  (*(void (__fastcall **)(Jot::CTVISectionListener *))(*(_QWORD *)v18 + 8LL))(v18);
  return v4;
}

```

## disassembly

```asm
0x14006bb10  mov     [rsp-8+arg_8], rbx
0x14006bb15  mov     [rsp-8+arg_10], rsi
0x14006bb1a  push    rbp
0x14006bb1b  push    rdi
0x14006bb1c  push    r12
0x14006bb1e  push    r14
0x14006bb20  push    r15
0x14006bb22  lea     rbp, [rsp-0F0h]
0x14006bb2a  sub     rsp, 1F0h
0x14006bb31  mov     rax, cs:__security_cookie
0x14006bb38  xor     rax, rsp
0x14006bb3b  mov     [rbp+110h+var_30], rax
0x14006bb42  mov     r12d, edx
0x14006bb45  mov     rdi, rcx
0x14006bb48  mov     [rsp+210h+var_1C0], 0
0x14006bb51  mov     [rsp+210h+var_1D8], 0
0x14006bb5a  mov     [rsp+210h+var_1C8], 0
0x14006bb63  mov     [rsp+210h+var_1E8], 0
0x14006bb68  mov     [rsp+210h+var_1F0], edx
0x14006bb6c  mov     r9, rcx
0x14006bb6f  lea     r8, [rsp+210h+var_1C8]
0x14006bb74  lea     rdx, [rsp+210h+var_1D8]
0x14006bb79  lea     rcx, [rsp+210h+var_1C0]
0x14006bb7e  call    ?CreateBasicTreeViewItem@CNotebookPaneManager@Jot@@CAXPEAPEAVElement@NetUI@@00PEAUIUINotebookEntity@2@W4TreeViewItemLocation@2@_N@Z; Jot::CNotebookPaneManager::CreateBasicTreeViewItem(NetUI::Element * *,NetUI::Element * *,NetUI::Element * *,Jot::IUINotebookEntity *,Jot::TreeViewItemLocation,bool)
0x14006bb83  lea     rdx, aNotebookpanepa; "NotebookPanePaddedContainer"
0x14006bb8a  mov     rsi, [rsp+210h+var_1C0]
0x14006bb8f  mov     rcx, rsi; this
0x14006bb92  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14006bb97  lea     rdx, aNotebookpanese_0; "NotebookPaneSectionItem"
0x14006bb9e  mov     rcx, [rsp+210h+var_1D8]; this
0x14006bba3  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14006bba8  call    ?CreateIconContainer@Jot@@YAPEAVElement@NetUI@@XZ; Jot::CreateIconContainer(void)
0x14006bbad  mov     r15, rax
0x14006bbb0  mov     rdx, rax
0x14006bbb3  mov     rcx, [rsp+210h+var_1D8]
0x14006bbb8  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14006bbbe  mov     [rsp+210h+var_1D0], 0
0x14006bbc7  lea     rcx, [rsp+210h+var_1D0]
0x14006bbcc  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x14006bbd2  mov     rdx, [rsp+210h+var_1D0]
0x14006bbd7  mov     rcx, r15
0x14006bbda  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14006bbe0  mov     rcx, [rsp+210h+var_1D0]; this
0x14006bbe5  call    ??$nui_control_cast@VImage@NetUI@@@NetUI@@YAPEBVImage@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Image>(NetUI::Node const *)
0x14006bbea  mov     rbx, rax
0x14006bbed  lea     rdx, aNotebookpanese; "NotebookPaneSectionItemImage"
0x14006bbf4  mov     rcx, rax; this
0x14006bbf7  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14006bbfc  xor     edx, edx; bool
0x14006bbfe  mov     rcx, rbx; this
0x14006bc01  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x14006bc06  mov     edx, 0F44h; unsigned int
0x14006bc0b  mov     rcx, rbx; this
0x14006bc0e  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x14006bc13  mov     rcx, [rsp+210h+var_1D8]; this
0x14006bc18  call    ?CreateLabelContainer@CNotebookPaneManager@Jot@@CAPEAVLabel@NetUI@@PEAVElement@4@@Z; Jot::CNotebookPaneManager::CreateLabelContainer(NetUI::Element *)
0x14006bc1d  mov     r14, rax
0x14006bc20  lea     rdx, aNotebookpanese_2; "NotebookPaneSectionItemLabel"
0x14006bc27  mov     rcx, rax; this
0x14006bc2a  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14006bc2f  xor     edx, edx; bool
0x14006bc31  mov     rcx, r14; this
0x14006bc34  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x14006bc39  call    ?CreateIconContainer@Jot@@YAPEAVElement@NetUI@@XZ; Jot::CreateIconContainer(void)
0x14006bc3e  mov     rbx, rax
0x14006bc41  mov     rdx, rax
0x14006bc44  mov     rcx, [rsp+210h+var_1D8]
0x14006bc49  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14006bc4f  mov     [rsp+210h+var_1E0], 0
0x14006bc58  lea     rcx, [rsp+210h+var_1E0]
0x14006bc5d  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x14006bc63  mov     rdx, [rsp+210h+var_1E0]
0x14006bc68  mov     rcx, rbx
0x14006bc6b  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14006bc71  lea     rdx, aNotebookpanese_1; "NotebookPaneSectionItemErrorIcon"
0x14006bc78  mov     rcx, [rsp+210h+var_1E0]; this
0x14006bc7d  call    ?SetID@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetID(wchar_t const *)
0x14006bc82  xor     edx, edx; bool
0x14006bc84  mov     rcx, [rsp+210h+var_1E0]; this
0x14006bc89  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x14006bc8e  mov     rcx, [rsp+210h+var_1E0]; this
0x14006bc93  call    ??$nui_control_cast@VImage@NetUI@@@NetUI@@YAPEBVImage@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Image>(NetUI::Node const *)
0x14006bc98  mov     rbx, rax
0x14006bc9b  xor     edx, edx; bool
0x14006bc9d  mov     rcx, rax; this
0x14006bca0  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x14006bca5  mov     [rsp+210h+var_1B8], 0FF02h
0x14006bcac  mov     [rsp+210h+var_1B4], 7FC00000h
0x14006bcb4  mov     [rsp+210h+var_1B0], 1
0x14006bcb9  mov     [rsp+210h+var_1A8], 0
0x14006bcc2  lea     rdx, [rsp+210h+var_1B8]
0x14006bcc7  mov     ecx, 0BE9h
0x14006bccc  call    cs:__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z; NetUI::Value::CreateGraphicIcon(Mso::IconId,NetUI::CreateIconParams const &)
0x14006bcd2  mov     rdx, rax; struct NetUI::Value *
0x14006bcd5  mov     rcx, rbx; this
0x14006bcd8  call    ?SetSrc@Image@NetUI@@QEAAJPEAVValue@2@@Z; NetUI::Image::SetSrc(NetUI::Value *)
0x14006bcdd  test    rdi, rdi
0x14006bce0  jnz     loc_14006BE58
0x14006bce6  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x14006bcec  test    al, al
0x14006bcee  jz      short loc_14006BCFF
0x14006bcf0  lea     rdx, aErroriconimage; "ErrorIconImage"
0x14006bcf7  mov     rcx, rbx; this
0x14006bcfa  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14006bcff  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x14006bd05  test    al, al
0x14006bd07  jnz     loc_14006BE84
0x14006bd0d  mov     edx, 15Dh; struct NetUI::Element *
0x14006bd12  mov     rcx, r14; this
0x14006bd15  call    ?ApplyTextStyle@NavigationUI@Jot@@YAXPEAVElement@NetUI@@H@Z; Jot::NavigationUI::ApplyTextStyle(NetUI::Element *,int)
0x14006bd1a  mov     [rsp+210h+var_1C8], 0
0x14006bd23  mov     ecx, 88h
0x14006bd28  call    cs:__imp_?HAlloc@NetUI@@YAPEAX_K@Z; NetUI::HAlloc(unsigned __int64)
0x14006bd2e  mov     rbx, rax
0x14006bd31  test    rax, rax
0x14006bd34  jz      short loc_14006BD3F
0x14006bd36  mov     rcx, rax; this
0x14006bd39  call    ??0CTVISectionListener@Jot@@QEAA@XZ; Jot::CTVISectionListener::CTVISectionListener(void)
0x14006bd3e  nop
0x14006bd3f  mov     [rsp+210h+var_1C8], rbx
0x14006bd44  lea     rcx, [rbx+40h]
0x14006bd48  mov     rdx, rdi
0x14006bd4b  call    ?Assign@?$CIPtr@UIFloatieMSAA@Jot@@U12@@MsoCF@@QEAAXPEAUIFloatieMSAA@Jot@@@Z; MsoCF::CIPtr<Jot::IFloatieMSAA,Jot::IFloatieMSAA>::Assign(Jot::IFloatieMSAA *)
0x14006bd50  mov     byte ptr [rbx+4Dh], 1
0x14006bd54  mov     [rbx+58h], r12d
0x14006bd58  mov     r8b, 1
0x14006bd5b  mov     rdx, rbx
0x14006bd5e  mov     rcx, rsi
0x14006bd61  call    cs:__imp_?AddListener@Node@NetUI@@QEAAJPEAUIElementListener@2@_N@Z; NetUI::Node::AddListener(NetUI::IElementListener *,bool)
0x14006bd67  lea     rcx, [rsp+210h+var_1A0]
0x14006bd6c  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x14006bd71  nop
0x14006bd72  mov     r8d, 4E388FC0h
0x14006bd78  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14006bd7f  mov     rdx, [rdx+1F0h]
0x14006bd86  lea     rcx, [rsp+210h+var_1A0]
0x14006bd8b  call    cs:__imp_?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x14006bd91  lea     rcx, [rsp+210h+var_1A0]
0x14006bd96  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14006bd9c  mov     rdx, rax; wchar_t *
0x14006bd9f  mov     rcx, rsi; this
0x14006bda2  call    ?SetAccessibleDescription@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetAccessibleDescription(wchar_t const *)
0x14006bda7  call    cs:__imp_?GetStaticClassInfo@TreeViewItem@NetUI@@SAPEAUIClassInfo@2@XZ; NetUI::TreeViewItem::GetStaticClassInfo(void)
0x14006bdad  test    rsi, rsi
0x14006bdb0  jz      loc_14006BEBB
0x14006bdb6  mov     rdx, rax; struct NetUI::IClassInfo *
0x14006bdb9  mov     rcx, rsi; this
0x14006bdbc  call    ?IsSubclassOf@Node@NetUI@@QEBA_NPEBUIClassInfo@2@@Z; NetUI::Node::IsSubclassOf(NetUI::IClassInfo const *)
0x14006bdc1  test    al, al
0x14006bdc3  jz      loc_14006BEBB
0x14006bdc9  mov     rdi, rsi
0x14006bdcc  test    rdi, rdi
0x14006bdcf  jz      short loc_14006BDE4
0x14006bdd1  mov     edx, 0CA90h
0x14006bdd6  mov     r8d, 810h
0x14006bddc  mov     rcx, [rdi]
0x14006bddf  call    __castguard_slow_path_check_user_handled
0x14006bde4  xor     edx, edx; bool
0x14006bde6  mov     rcx, rdi; this
0x14006bde9  call    ?SetHasChildren@TreeViewItem@NetUI@@QEAAJ_N@Z; NetUI::TreeViewItem::SetHasChildren(bool)
0x14006bdee  mov     edx, 4; int
0x14006bdf3  mov     rcx, [rsp+210h+var_1D8]; this
0x14006bdf8  call    ?SetAlignChildren@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetAlignChildren(int)
0x14006bdfd  nop
0x14006bdfe  lea     rax, [rbp+110h+var_140]
0x14006be02  mov     rcx, [rbp+110h+var_158]
0x14006be06  cmp     rcx, rax
0x14006be09  jz      short loc_14006BE11
0x14006be0b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x14006be11  lea     rcx, [rbp+110h+var_180]; void *
0x14006be15  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006be1a  mov     rcx, [rbx]
0x14006be1d  mov     rax, [rcx+8]
0x14006be21  mov     rcx, rbx
0x14006be24  call    cs:__guard_dispatch_icall_fptr
0x14006be2a  mov     rax, rsi
0x14006be2d  mov     rcx, [rbp+110h+var_30]
0x14006be34  xor     rcx, rsp; StackCookie
0x14006be37  call    __security_check_cookie
0x14006be3c  lea     r11, [rsp+210h+var_20]
0x14006be44  mov     rbx, [r11+38h]
0x14006be48  mov     rsi, [r11+40h]
0x14006be4c  mov     rsp, r11
0x14006be4f  pop     r15
0x14006be51  pop     r14
0x14006be53  pop     r12
0x14006be55  pop     rdi
0x14006be56  pop     rbp
0x14006be57  retn
0x14006be58  mov     rax, [rdi]
0x14006be5b  mov     rcx, rdi
0x14006be5e  mov     rax, [rax+1B0h]
0x14006be65  call    cs:__guard_dispatch_icall_fptr
0x14006be6b  test    al, al
0x14006be6d  jz      loc_14006BCE6
0x14006be73  mov     dl, 1; bool
0x14006be75  mov     rcx, [rsp+210h+var_1E0]; this
0x14006be7a  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x14006be7f  jmp     loc_14006BCE6
0x14006be84  cmp     r12d, 2
0x14006be88  jnz     short loc_14006BEA9
0x14006be8a  xor     r8d, r8d; int
0x14006be8d  lea     ebx, [r12+12h]
0x14006be92  mov     edx, ebx; int
0x14006be94  mov     rcx, r15; this
0x14006be97  call    ?SetWidthPixels@Element@NetUI@@QEAAJHH@Z; NetUI::Element::SetWidthPixels(int,int)
0x14006be9c  xor     r8d, r8d; int
0x14006be9f  mov     edx, ebx; int
0x14006bea1  mov     rcx, r15; this
0x14006bea4  call    ?SetHeightPixels@Element@NetUI@@QEAAJHH@Z; NetUI::Element::SetHeightPixels(int,int)
0x14006bea9  mov     edx, 2; int
0x14006beae  mov     rcx, r14; this
0x14006beb1  call    ?SetTextStyle@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetTextStyle(int)
0x14006beb6  jmp     loc_14006BD1A
0x14006bebb  xor     edi, edi
0x14006bebd  jmp     loc_14006BDCC
```
