# Jot::CAltTextDialogListener::OnListenerAttach(NetUI::Node *)

- ea: `0x1400e6dc0`
- end: `0x1400e706f`
- name: `?OnListenerAttach@CAltTextDialogListener@Jot@@UEAAXPEAVNode@NetUI@@@Z`
- size: `687`
- prototype: `void __fastcall(Jot::CAltTextDialogListener *__hidden this, struct Node *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001cea8`
- `0x140049410`
- `0x140054290`
- `0x140065cc4`
- `0x1400728d0`
- `0x140074598`
- `0x1400d803c`
- `0x1400e6dc0`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x1400e6df1`
- `KERNEL32!FindAtomW` at `0x1400e6e23`
- `KERNEL32!FindAtomW` at `0x1400e6df1`
- `KERNEL32!FindAtomW` at `0x1400e6e23`
- `onmain!?priInsertTitleString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400e6f0f`
- `onmain!?priInsertTextString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400e6f9b`
- `onmain!?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400e6eb0`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6eba`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6f19`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6fa5`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6eba`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6f19`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1400e6fa5`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e7020`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e7037`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e704e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e7020`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e7037`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400e704e`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6dfd`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e2f`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e57`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e7b`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6dfd`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e2f`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e57`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x1400e6e7b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400e6ffd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400e6ffd`

## pseudocode

```c
void __fastcall Jot::CAltTextDialogListener::OnListenerAttach(Jot::CAltTextDialogListener *this, struct Node *a2)
{
  ATOM AtomW; // ax
  NetUI::Node *NodeSelfOrDescendent; // rax
  __int64 v6; // rax
  NetUI::Node *v7; // rbx
  ATOM v8; // ax
  NetUI::Node *v9; // rax
  __int64 v10; // rax
  NetUI::Node *v11; // rcx
  NetUI::Node *v12; // rax
  __int64 v13; // rax
  NetUI::Node *v14; // rcx
  NetUI::Node *v15; // rax
  __int64 v16; // rax
  MsoCF::IPropertySet *v17; // rax
  MsoCF::IPropertySet *v18; // rax
  NetUI::Element *v19; // r14
  __int64 v20; // rax
  const wchar_t *v21; // rsi
  __int64 v22; // rbx
  MsoCF::IPropertySet *v23; // rax
  int v24; // edx
  NetUI::Element *v25; // rsi
  __int64 v26; // rax
  const wchar_t *v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // [rsp+20h] [rbp-30h] BYREF
  int v30; // [rsp+28h] [rbp-28h]
  __int64 v31; // [rsp+30h] [rbp-20h] BYREF
  int v32; // [rsp+38h] [rbp-18h]
  __int64 v33; // [rsp+40h] [rbp-10h] BYREF
  int v34; // [rsp+48h] [rbp-8h]

  *((_QWORD *)this + 2) = a2;
  if ( a2 )
  {
    AtomW = FindAtomW(L"AltTextTitlebox");
    NodeSelfOrDescendent = (NetUI::Node *)NetUI::Node::FindNodeSelfOrDescendent((NetUI::Node *)a2, AtomW);
    v6 = NetUI::nui_control_cast<NetUI::Textbox>(NodeSelfOrDescendent);
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 4) = v6;
  v7 = (NetUI::Node *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    v8 = FindAtomW(L"AltTextbox");
    v9 = (NetUI::Node *)NetUI::Node::FindNodeSelfOrDescendent(v7, v8);
    v10 = NetUI::nui_control_cast<NetUI::Textbox>(v9);
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)this + 5) = v10;
  v11 = (NetUI::Node *)*((_QWORD *)this + 2);
  if ( v11 )
  {
    v12 = (NetUI::Node *)NetUI::Node::FindNodeSelfOrDescendent(v11, 1u);
    v13 = NetUI::nui_control_cast<NetUI::Button>(v12);
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 6) = v13;
  v14 = (NetUI::Node *)*((_QWORD *)this + 2);
  if ( v14 )
  {
    v15 = (NetUI::Node *)NetUI::Node::FindNodeSelfOrDescendent(v14, 2u);
    v16 = NetUI::nui_control_cast<NetUI::Button>(v15);
  }
  else
  {
    v16 = 0;
  }
  *((_QWORD *)this + 7) = v16;
  v33 = 0;
  v34 = 0;
  v17 = Jot::CBaseRootElement::UsePropertySet(*((Jot::CBaseRootElement **)this + 3), 1);
  MsoCF::IPropertySet::GetProperty(
    v17,
    Jot::PropertySpace_JotMain::priFCtrlEnabled,
    (struct MsoCF::CPropertyValue *)&v33);
  if ( v34 == 2228226 && !(_BYTE)v33 )
  {
    NetUI::Textbox::SetIsEditable(*((NetUI::Textbox **)this + 4), 0);
    NetUI::Textbox::SetIsEditable(*((NetUI::Textbox **)this + 5), 0);
    NetUI::Element::SetIsEnabled(*((NetUI::Element **)this + 6), 0);
  }
  v31 = 0;
  v32 = 0;
  v18 = Jot::CBaseRootElement::UsePropertySet(*((Jot::CBaseRootElement **)this + 3), 1);
  MsoCF::IPropertySet::GetProperty(
    v18,
    Jot::PropertySpace_JotMain::priInsertTitleString,
    (struct MsoCF::CPropertyValue *)&v31);
  if ( v32 == 117899322 && v31 )
  {
    v19 = (NetUI::Element *)*((_QWORD *)this + 4);
    v20 = (*(_DWORD *)(v31 + 4) >> 1) & 0x1FFFFFFF;
    v21 = (const wchar_t *)(v31 + 8);
    if ( v31 != -8 )
    {
      if ( !(_DWORD)v20 || (v22 = v31 + 2 * (v20 + 4), _std_find_trivial_2(v21, v22, 0) == v22) )
      {
LABEL_27:
        CrashWithRecovery(0x1F46100Du, 0);
        __debugbreak();
      }
    }
    NetUI::Element::SetTextString(v19, v21);
  }
  v29 = 0;
  v30 = 0;
  v23 = Jot::CBaseRootElement::UsePropertySet(*((Jot::CBaseRootElement **)this + 3), 1);
  MsoCF::IPropertySet::GetProperty(
    v23,
    Jot::PropertySpace_JotMain::priInsertTextString,
    (struct MsoCF::CPropertyValue *)&v29);
  v24 = v30;
  if ( v30 == 117899322 && v29 )
  {
    v25 = (NetUI::Element *)*((_QWORD *)this + 5);
    v26 = (*(_DWORD *)(v29 + 4) >> 1) & 0x1FFFFFFF;
    v27 = (const wchar_t *)(v29 + 8);
    if ( v29 != -8 )
    {
      if ( !(_DWORD)v26 )
        goto LABEL_27;
      v28 = v29 + 8 + 2 * v26;
      if ( _std_find_trivial_2(v29 + 8, v28, 0) == v28 )
        goto LABEL_27;
    }
    NetUI::Element::SetTextString(v25, v27);
    v24 = v30;
  }
  if ( (v24 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v29);
  if ( (v32 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v31);
  if ( (v34 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v33);
}

```

## disassembly

```asm
0x1400e6dc0  mov     [rsp-18h+arg_0], rbx
0x1400e6dc5  mov     [rsp-18h+arg_8], rsi
0x1400e6dca  mov     [rsp-18h+arg_10], rdi
0x1400e6dcf  push    rbp
0x1400e6dd0  push    r12
0x1400e6dd2  push    r14
0x1400e6dd4  mov     rbp, rsp
0x1400e6dd7  sub     rsp, 50h
0x1400e6ddb  mov     rbx, rdx
0x1400e6dde  mov     rdi, rcx
0x1400e6de1  mov     [rcx+10h], rdx
0x1400e6de5  test    rdx, rdx
0x1400e6de8  jz      short loc_1400E6E0D
0x1400e6dea  lea     rcx, aAlttexttitlebo; "AltTextTitlebox"
0x1400e6df1  call    cs:__imp_FindAtomW
0x1400e6df7  movzx   edx, ax
0x1400e6dfa  mov     rcx, rbx
0x1400e6dfd  call    cs:__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z; NetUI::Node::FindNodeSelfOrDescendent(ushort)
0x1400e6e03  mov     rcx, rax; this
0x1400e6e06  call    ??$nui_control_cast@VTextbox@NetUI@@@NetUI@@YAPEBVTextbox@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Textbox>(NetUI::Node const *)
0x1400e6e0b  jmp     short loc_1400E6E0F
0x1400e6e0d  xor     eax, eax
0x1400e6e0f  mov     [rdi+20h], rax
0x1400e6e13  mov     rbx, [rdi+10h]
0x1400e6e17  test    rbx, rbx
0x1400e6e1a  jz      short loc_1400E6E3F
0x1400e6e1c  lea     rcx, aAlttextbox; "AltTextbox"
0x1400e6e23  call    cs:__imp_FindAtomW
0x1400e6e29  movzx   edx, ax
0x1400e6e2c  mov     rcx, rbx
0x1400e6e2f  call    cs:__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z; NetUI::Node::FindNodeSelfOrDescendent(ushort)
0x1400e6e35  mov     rcx, rax; this
0x1400e6e38  call    ??$nui_control_cast@VTextbox@NetUI@@@NetUI@@YAPEBVTextbox@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Textbox>(NetUI::Node const *)
0x1400e6e3d  jmp     short loc_1400E6E41
0x1400e6e3f  xor     eax, eax
0x1400e6e41  mov     [rdi+28h], rax
0x1400e6e45  mov     rcx, [rdi+10h]
0x1400e6e49  mov     r12d, 1
0x1400e6e4f  test    rcx, rcx
0x1400e6e52  jz      short loc_1400E6E67
0x1400e6e54  mov     edx, r12d
0x1400e6e57  call    cs:__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z; NetUI::Node::FindNodeSelfOrDescendent(ushort)
0x1400e6e5d  mov     rcx, rax; this
0x1400e6e60  call    ??$nui_control_cast@VButton@NetUI@@@NetUI@@YAPEBVButton@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Button>(NetUI::Node const *)
0x1400e6e65  jmp     short loc_1400E6E69
0x1400e6e67  xor     eax, eax
0x1400e6e69  mov     [rdi+30h], rax
0x1400e6e6d  mov     rcx, [rdi+10h]
0x1400e6e71  test    rcx, rcx
0x1400e6e74  jz      short loc_1400E6E8B
0x1400e6e76  mov     edx, 2
0x1400e6e7b  call    cs:__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z; NetUI::Node::FindNodeSelfOrDescendent(ushort)
0x1400e6e81  mov     rcx, rax; this
0x1400e6e84  call    ??$nui_control_cast@VButton@NetUI@@@NetUI@@YAPEBVButton@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Button>(NetUI::Node const *)
0x1400e6e89  jmp     short loc_1400E6E8D
0x1400e6e8b  xor     eax, eax
0x1400e6e8d  mov     [rdi+38h], rax
0x1400e6e91  mov     [rbp+var_10], 0
0x1400e6e99  mov     [rbp+var_8], 0
0x1400e6ea0  mov     edx, r12d; int
0x1400e6ea3  mov     rcx, [rdi+18h]; this
0x1400e6ea7  call    ?UsePropertySet@CBaseRootElement@Jot@@QEAAPEAUIPropertySet@MsoCF@@H@Z; Jot::CBaseRootElement::UsePropertySet(int)
0x1400e6eac  lea     r8, [rbp+var_10]
0x1400e6eb0  mov     rdx, cs:__imp_?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priFCtrlEnabled
0x1400e6eb7  mov     rcx, rax
0x1400e6eba  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400e6ec0  cmp     [rbp+var_8], 220002h
0x1400e6ec7  jnz     short loc_1400E6EF0
0x1400e6ec9  cmp     byte ptr [rbp+var_10], 0
0x1400e6ecd  jnz     short loc_1400E6EF0
0x1400e6ecf  xor     edx, edx; bool
0x1400e6ed1  mov     rcx, [rdi+20h]; this
0x1400e6ed5  call    ?SetIsEditable@Textbox@NetUI@@QEAAJ_N@Z; NetUI::Textbox::SetIsEditable(bool)
0x1400e6eda  xor     edx, edx; bool
0x1400e6edc  mov     rcx, [rdi+28h]; this
0x1400e6ee0  call    ?SetIsEditable@Textbox@NetUI@@QEAAJ_N@Z; NetUI::Textbox::SetIsEditable(bool)
0x1400e6ee5  xor     edx, edx; bool
0x1400e6ee7  mov     rcx, [rdi+30h]; this
0x1400e6eeb  call    ?SetIsEnabled@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsEnabled(bool)
0x1400e6ef0  mov     [rbp+var_20], 0
0x1400e6ef8  mov     [rbp+var_18], 0
0x1400e6eff  mov     edx, r12d; int
0x1400e6f02  mov     rcx, [rdi+18h]; this
0x1400e6f06  call    ?UsePropertySet@CBaseRootElement@Jot@@QEAAPEAUIPropertySet@MsoCF@@H@Z; Jot::CBaseRootElement::UsePropertySet(int)
0x1400e6f0b  lea     r8, [rbp+var_20]
0x1400e6f0f  mov     rdx, cs:__imp_?priInsertTitleString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priInsertTitleString
0x1400e6f16  mov     rcx, rax
0x1400e6f19  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400e6f1f  cmp     [rbp+var_18], 707003Ah
0x1400e6f26  jnz     short loc_1400E6F7C
0x1400e6f28  mov     r8, [rbp+var_20]
0x1400e6f2c  test    r8, r8
0x1400e6f2f  jz      short loc_1400E6F7C
0x1400e6f31  mov     r14, [rdi+20h]
0x1400e6f35  mov     eax, [r8+4]
0x1400e6f39  shr     eax, 1
0x1400e6f3b  and     eax, 1FFFFFFFh
0x1400e6f40  lea     rsi, [r8+8]
0x1400e6f44  test    rsi, rsi
0x1400e6f47  jz      short loc_1400E6F71
0x1400e6f49  cmp     eax, r12d
0x1400e6f4c  jb      loc_1400E6FF6
0x1400e6f52  add     rax, 4
0x1400e6f56  lea     rbx, [r8+rax*2]
0x1400e6f5a  xor     r8d, r8d
0x1400e6f5d  mov     rdx, rbx
0x1400e6f60  mov     rcx, rsi
0x1400e6f63  call    __std_find_trivial_2
0x1400e6f68  cmp     rax, rbx
0x1400e6f6b  jz      loc_1400E6FF6
0x1400e6f71  mov     rdx, rsi; wchar_t *
0x1400e6f74  mov     rcx, r14; this
0x1400e6f77  call    ?SetTextString@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetTextString(wchar_t const *)
0x1400e6f7c  mov     [rbp+var_30], 0
0x1400e6f84  mov     [rbp+var_28], 0
0x1400e6f8b  mov     edx, r12d; int
0x1400e6f8e  mov     rcx, [rdi+18h]; this
0x1400e6f92  call    ?UsePropertySet@CBaseRootElement@Jot@@QEAAPEAUIPropertySet@MsoCF@@H@Z; Jot::CBaseRootElement::UsePropertySet(int)
0x1400e6f97  lea     r8, [rbp+var_30]
0x1400e6f9b  mov     rdx, cs:__imp_?priInsertTextString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priInsertTextString
0x1400e6fa2  mov     rcx, rax
0x1400e6fa5  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1400e6fab  mov     edx, [rbp+var_28]
0x1400e6fae  cmp     edx, 707003Ah
0x1400e6fb4  jnz     short loc_1400E7012
0x1400e6fb6  mov     rcx, [rbp+var_30]
0x1400e6fba  test    rcx, rcx
0x1400e6fbd  jz      short loc_1400E7012
0x1400e6fbf  mov     rsi, [rdi+28h]
0x1400e6fc3  mov     eax, [rcx+4]
0x1400e6fc6  shr     eax, 1
0x1400e6fc8  and     eax, 1FFFFFFFh
0x1400e6fcd  lea     rdi, [rcx+8]
0x1400e6fd1  test    rdi, rdi
0x1400e6fd4  jz      short loc_1400E7004
0x1400e6fd6  cmp     eax, r12d
0x1400e6fd9  jb      short loc_1400E6FF6
0x1400e6fdb  add     rcx, 8
0x1400e6fdf  lea     rbx, [rcx+rax*2]
0x1400e6fe3  xor     r8d, r8d
0x1400e6fe6  mov     rdx, rbx
0x1400e6fe9  mov     rcx, rdi
0x1400e6fec  call    __std_find_trivial_2
0x1400e6ff1  cmp     rax, rbx
0x1400e6ff4  jnz     short loc_1400E7004
0x1400e6ff6  xor     edx, edx
0x1400e6ff8  mov     ecx, 1F46100Dh
0x1400e6ffd  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400e7003  int     3; Trap to Debugger
0x1400e7004  mov     rdx, rdi; wchar_t *
0x1400e7007  mov     rcx, rsi; this
0x1400e700a  call    ?SetTextString@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetTextString(wchar_t const *)
0x1400e700f  mov     edx, [rbp+var_28]
0x1400e7012  mov     eax, edx
0x1400e7014  shr     eax, 19h
0x1400e7017  test    r12b, al
0x1400e701a  jz      short loc_1400E7026
0x1400e701c  lea     rcx, [rbp+var_30]
0x1400e7020  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400e7026  mov     edx, [rbp+var_18]
0x1400e7029  mov     eax, edx
0x1400e702b  shr     eax, 19h
0x1400e702e  test    r12b, al
0x1400e7031  jz      short loc_1400E703D
0x1400e7033  lea     rcx, [rbp+var_20]
0x1400e7037  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400e703d  mov     edx, [rbp+var_8]
0x1400e7040  mov     eax, edx
0x1400e7042  shr     eax, 19h
0x1400e7045  test    r12b, al
0x1400e7048  jz      short loc_1400E7055
0x1400e704a  lea     rcx, [rbp+var_10]
0x1400e704e  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400e7054  nop
0x1400e7055  lea     r11, [rsp+50h+var_s0]
0x1400e705a  mov     rbx, [r11+20h]
0x1400e705e  mov     rsi, [r11+28h]
0x1400e7062  mov     rdi, [r11+30h]
0x1400e7066  mov     rsp, r11
0x1400e7069  pop     r14
0x1400e706b  pop     r12
0x1400e706d  pop     rbp
0x1400e706e  retn
```
