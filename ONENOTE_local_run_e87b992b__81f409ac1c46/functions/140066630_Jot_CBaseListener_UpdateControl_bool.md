# Jot::CBaseListener::UpdateControl(bool)

- ea: `0x140066630`
- end: `0x1400668ac`
- name: `?UpdateControl@CBaseListener@Jot@@UEAAX_N@Z`
- size: `636`
- prototype: `void __fastcall(Jot::CBaseListener *__hidden this, bool)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400664c0`
- `0x1400742f0`
- `0x1400bd630`
- `0x1400ca8d0`

## callees

- `0x140049304`
- `0x140049410`
- `0x140049970`
- `0x140066540`
- `0x140066630`
- `0x1400668ac`
- `0x140066a28`
- `0x14010b054`

## import_xrefs

- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066702`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066786`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066812`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066702`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066786`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x140066812`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066712`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066796`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066822`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066712`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066796`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140066822`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140066757`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400667cc`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140066757`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400667cc`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x1400668a0`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x1400668a0`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14006686f`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14006686f`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14006687b`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14006687b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Jot::CBaseListener::UpdateControl(Jot::CBaseListener *this, bool a2, const char *a3)
{
  Jot *v5; // rcx
  unsigned int PropertyHandle; // r15d
  const char *v7; // r8
  unsigned int v8; // eax
  unsigned int v9; // edx
  const char *v10; // r8
  unsigned int v11; // r14d
  unsigned int v12; // edx
  unsigned int v13; // r14d
  MsoCF::IPropertySet *v14; // rbx
  const struct MsoCF::PropertyInfo *v15; // rax
  NetUI::Element *v16; // rbx
  char v17; // al
  MsoCF::IPropertySet *v18; // rbx
  const struct MsoCF::PropertyInfo *v19; // rax
  NetUI::Element *v20; // rax
  MsoCF::IPropertySet *v21; // rbx
  const struct MsoCF::PropertyInfo *v22; // rax
  NetUI::Element *v23; // rax
  const struct NetUI::PropertyInfo *v24; // rax
  __int64 v25; // [rsp+20h] [rbp-10h] BYREF
  int v26; // [rsp+28h] [rbp-8h]

  *((_BYTE *)this + 32) = 0;
  if ( !*((_QWORD *)this + 3) )
    return;
  v5 = (Jot *)*((_QWORD *)this + 2);
  if ( !v5 )
    return;
  PropertyHandle = Jot::GetPropertyHandle(v5, (struct Node *)&stru_1401F7F18, a3);
  v8 = Jot::GetPropertyHandle(*((Jot **)this + 2), (struct Node *)&stru_1401F7F00, v7);
  v11 = v8;
  if ( PropertyHandle || v8 )
  {
    if ( a2 )
      sub_14010B054(*((Jot **)this + 2), (struct Node *)&stru_140203B70, *((struct MsoCF::IPropertySet **)this + 3));
    if ( PropertyHandle )
    {
      v25 = 0;
      v26 = 0;
      v18 = (MsoCF::IPropertySet *)*((_QWORD *)this + 3);
      v19 = MsoCF::LookupProperty((MsoCF *)PropertyHandle, v9);
      MsoCF::IPropertySet::GetProperty(v18, v19, (struct MsoCF::CPropertyValue *)&v25);
      v20 = (NetUI::Element *)NetUI::nui_control_cast<NetUI::Element>(*((NetUI::Node **)this + 2));
      NetUI::Element::SetIsEnabled(v20, (_DWORD)v25 != 0);
      *((_BYTE *)this + 32) = 1;
    }
    else
    {
      if ( !v11 )
        goto LABEL_5;
      v25 = 0;
      v26 = 0;
      v21 = (MsoCF::IPropertySet *)*((_QWORD *)this + 3);
      v22 = MsoCF::LookupProperty((MsoCF *)v11, v9);
      MsoCF::IPropertySet::GetProperty(v21, v22, (struct MsoCF::CPropertyValue *)&v25);
      v23 = (NetUI::Element *)NetUI::nui_control_cast<NetUI::Element>(*((NetUI::Node **)this + 2));
      NetUI::Element::SetIsEnabled(v23, (_DWORD)v25 == 0);
      *((_BYTE *)this + 32) = 1;
    }
    if ( (v26 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v25);
  }
LABEL_5:
  v13 = Jot::GetPropertyHandle(*((Jot **)this + 2), (struct Node *)&stru_1401F7EE8, v10);
  if ( v13 )
  {
    if ( a2 )
      sub_14010B054(*((Jot **)this + 2), (struct Node *)&stru_140203B90, *((struct MsoCF::IPropertySet **)this + 3));
    v25 = 0;
    v26 = 0;
    v14 = (MsoCF::IPropertySet *)*((_QWORD *)this + 3);
    v15 = MsoCF::LookupProperty((MsoCF *)v13, v12);
    MsoCF::IPropertySet::GetProperty(v14, v15, (struct MsoCF::CPropertyValue *)&v25);
    v16 = (NetUI::Element *)NetUI::nui_control_cast<NetUI::Element>(*((NetUI::Node **)this + 2));
    v17 = *((_BYTE *)v16 + 194) & 1;
    if ( (_DWORD)v25 )
    {
      if ( !v17 )
      {
        NetUI::Element::SetIsVisible(v16, 1);
        v24 = (const struct NetUI::PropertyInfo *)NetUI::Element::LayoutPosPropInfo();
        NetUI::Node::RemoveLocalValue(v16, v24);
      }
    }
    else if ( v17 )
    {
      NetUI::Element::SetIsVisible(v16, 0);
      NetUI::Element::SetLayoutPos(v16, 1);
    }
    if ( (v26 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v25);
  }
  Jot::CBaseListener::UpdateTextProperty(this, *((struct Node **)this + 2), a2);
  Jot::CBaseListener::UpdateAccessibleNameProperty(this, *((struct Node **)this + 2));
}

```

## disassembly

```asm
0x140066630  mov     [rsp-18h+arg_0], rbx
0x140066635  mov     [rsp-18h+arg_8], rsi
0x14006663a  mov     [rsp-18h+arg_10], rdi
0x14006663f  push    rbp
0x140066640  push    r14
0x140066642  push    r15
0x140066644  mov     rbp, rsp
0x140066647  sub     rsp, 30h
0x14006664b  mov     sil, dl
0x14006664e  mov     rdi, rcx
0x140066651  mov     byte ptr [rcx+20h], 0
0x140066655  cmp     qword ptr [rcx+18h], 0
0x14006665a  jz      short loc_1400666CA
0x14006665c  mov     rcx, [rcx+10h]; this
0x140066660  test    rcx, rcx
0x140066663  jz      short loc_1400666CA
0x140066665  lea     rdx, stru_1401F7F18; struct Node *
0x14006666c  call    ?GetPropertyHandle@Jot@@YAIPEAVNode@NetUI@@PEBD@Z; Jot::GetPropertyHandle(NetUI::Node *,char const *)
0x140066671  mov     r15d, eax
0x140066674  lea     rdx, stru_1401F7F00; struct Node *
0x14006667b  mov     rcx, [rdi+10h]; this
0x14006667f  call    ?GetPropertyHandle@Jot@@YAIPEAVNode@NetUI@@PEBD@Z; Jot::GetPropertyHandle(NetUI::Node *,char const *)
0x140066684  mov     r14d, eax
0x140066687  test    r15d, r15d
0x14006668a  jnz     loc_140066762
0x140066690  test    eax, eax
0x140066692  jnz     loc_140066762
0x140066698  lea     rdx, stru_1401F7EE8; struct Node *
0x14006669f  mov     rcx, [rdi+10h]; this
0x1400666a3  call    ?GetPropertyHandle@Jot@@YAIPEAVNode@NetUI@@PEBD@Z; Jot::GetPropertyHandle(NetUI::Node *,char const *)
0x1400666a8  mov     r14d, eax
0x1400666ab  test    eax, eax
0x1400666ad  jnz     short loc_1400666E3
0x1400666af  mov     r8b, sil; bool
0x1400666b2  mov     rdx, [rdi+10h]; struct Node *
0x1400666b6  mov     rcx, rdi; this
0x1400666b9  call    ?UpdateTextProperty@CBaseListener@Jot@@IEAAXPEAVNode@NetUI@@_N@Z; Jot::CBaseListener::UpdateTextProperty(NetUI::Node *,bool)
0x1400666be  mov     rdx, [rdi+10h]; struct Node *
0x1400666c2  mov     rcx, rdi; this
0x1400666c5  call    ?UpdateAccessibleNameProperty@CBaseListener@Jot@@IEAAXPEAVNode@NetUI@@@Z; Jot::CBaseListener::UpdateAccessibleNameProperty(NetUI::Node *)
0x1400666ca  mov     rbx, [rsp+30h+arg_0]
0x1400666cf  mov     rsi, [rsp+30h+arg_8]
0x1400666d4  mov     rdi, [rsp+30h+arg_10]
0x1400666d9  add     rsp, 30h
0x1400666dd  pop     r15
0x1400666df  pop     r14
0x1400666e1  pop     rbp
0x1400666e2  retn
0x1400666e3  test    sil, sil
0x1400666e6  jnz     loc_140066849
0x1400666ec  mov     [rbp+var_10], 0
0x1400666f4  mov     [rbp+var_8], 0
0x1400666fb  mov     rbx, [rdi+18h]
0x1400666ff  mov     ecx, r14d
0x140066702  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x140066708  lea     r8, [rbp+var_10]
0x14006670c  mov     rdx, rax
0x14006670f  mov     rcx, rbx
0x140066712  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x140066718  mov     rcx, [rdi+10h]; this
0x14006671c  call    ??$nui_control_cast@VElement@NetUI@@@NetUI@@YAPEBVElement@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Element>(NetUI::Node const *)
0x140066721  mov     rbx, rax
0x140066724  cmp     dword ptr [rbp+var_10], 0
0x140066728  setnz   cl
0x14006672b  mov     al, [rax+0C2h]
0x140066731  and     al, 1
0x140066733  test    cl, cl
0x140066735  jz      loc_140066886
0x14006673b  test    al, al
0x14006673d  jz      loc_140066865
0x140066743  mov     edx, [rbp+var_8]
0x140066746  mov     eax, edx
0x140066748  shr     eax, 19h
0x14006674b  test    al, 1
0x14006674d  jz      loc_1400666AF
0x140066753  lea     rcx, [rbp+var_10]
0x140066757  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14006675d  jmp     loc_1400666AF
0x140066762  test    sil, sil
0x140066765  jnz     short loc_1400667D7
0x140066767  test    r15d, r15d
0x14006676a  jz      loc_1400667F3
0x140066770  mov     [rbp+var_10], 0
0x140066778  mov     [rbp+var_8], 0
0x14006677f  mov     rbx, [rdi+18h]
0x140066783  mov     ecx, r15d
0x140066786  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x14006678c  lea     r8, [rbp+var_10]
0x140066790  mov     rdx, rax
0x140066793  mov     rcx, rbx
0x140066796  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x14006679c  mov     rcx, [rdi+10h]; this
0x1400667a0  call    ??$nui_control_cast@VElement@NetUI@@@NetUI@@YAPEBVElement@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Element>(NetUI::Node const *)
0x1400667a5  cmp     dword ptr [rbp+var_10], 0
0x1400667a9  setnz   dl; bool
0x1400667ac  mov     rcx, rax; this
0x1400667af  call    ?SetIsEnabled@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsEnabled(bool)
0x1400667b4  mov     byte ptr [rdi+20h], 1
0x1400667b8  mov     edx, [rbp+var_8]
0x1400667bb  mov     eax, edx
0x1400667bd  shr     eax, 19h
0x1400667c0  test    al, 1
0x1400667c2  jz      loc_140066698
0x1400667c8  lea     rcx, [rbp+var_10]
0x1400667cc  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400667d2  jmp     loc_140066698
0x1400667d7  xor     r9d, r9d
0x1400667da  mov     r8, [rdi+18h]; struct MsoCF::IPropertySet *
0x1400667de  lea     rdx, stru_140203B70; struct Node *
0x1400667e5  mov     rcx, [rdi+10h]; this
0x1400667e9  call    sub_14010B054
0x1400667ee  jmp     loc_140066767
0x1400667f3  test    r14d, r14d
0x1400667f6  jz      loc_140066698
0x1400667fc  mov     [rbp+var_10], 0
0x140066804  mov     [rbp+var_8], 0
0x14006680b  mov     rbx, [rdi+18h]
0x14006680f  mov     ecx, r14d
0x140066812  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x140066818  lea     r8, [rbp+var_10]
0x14006681c  mov     rdx, rax
0x14006681f  mov     rcx, rbx
0x140066822  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x140066828  mov     rcx, [rdi+10h]; this
0x14006682c  call    ??$nui_control_cast@VElement@NetUI@@@NetUI@@YAPEBVElement@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Element>(NetUI::Node const *)
0x140066831  cmp     dword ptr [rbp+var_10], 0
0x140066835  setz    dl; bool
0x140066838  mov     rcx, rax; this
0x14006683b  call    ?SetIsEnabled@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsEnabled(bool)
0x140066840  mov     byte ptr [rdi+20h], 1
0x140066844  jmp     loc_1400667B8
0x140066849  xor     r9d, r9d
0x14006684c  mov     r8, [rdi+18h]; struct MsoCF::IPropertySet *
0x140066850  lea     rdx, stru_140203B90; struct Node *
0x140066857  mov     rcx, [rdi+10h]; this
0x14006685b  call    sub_14010B054
0x140066860  jmp     loc_1400666EC
0x140066865  mov     dl, 1; bool
0x140066867  mov     rcx, rbx; this
0x14006686a  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x14006686f  call    cs:__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::LayoutPosPropInfo(void)
0x140066875  mov     rdx, rax
0x140066878  mov     rcx, rbx
0x14006687b  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x140066881  jmp     loc_140066743
0x140066886  test    al, al
0x140066888  jz      loc_140066743
0x14006688e  xor     edx, edx; bool
0x140066890  mov     rcx, rbx; this
0x140066893  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x140066898  mov     edx, 1
0x14006689d  mov     rcx, rbx
0x1400668a0  call    cs:__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetLayoutPos(int)
0x1400668a6  jmp     loc_140066743
```
