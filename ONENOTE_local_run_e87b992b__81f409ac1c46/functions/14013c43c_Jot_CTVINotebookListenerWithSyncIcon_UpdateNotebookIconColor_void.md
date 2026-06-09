# Jot::CTVINotebookListenerWithSyncIcon::UpdateNotebookIconColor(void)

- ea: `0x14013c43c`
- end: `0x14013c5d9`
- name: `?UpdateNotebookIconColor@CTVINotebookListenerWithSyncIcon@Jot@@AEAAXXZ`
- size: `413`
- prototype: `void __fastcall(Jot::CTVINotebookListenerWithSyncIcon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140139ca0`

## callees

- `0x140049a5c`
- `0x14004acfc`
- `0x140051700`
- `0x140057580`
- `0x14006ba94`
- `0x14013c43c`

## import_xrefs

- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14013c4d2`
- `onmain!?IsLicensedForFluentUI@Jot@@YA_NXZ` at `0x14013c4d2`
- `mso40uiWin32Client!__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z` at `0x14013c4aa`
- `mso40uiWin32Client!__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z` at `0x14013c4c1`
- `mso40uiWin32Client!__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z` at `0x14013c4aa`
- `mso40uiWin32Client!__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z` at `0x14013c4c1`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c4ea`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c506`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c518`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c4ea`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c506`
- `mso40uiWin32Client!__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c518`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c4f6`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c512`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c524`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c53a`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c4f6`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c512`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c524`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x14013c53a`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x14013c4dc`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x14013c4dc`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c52e`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14013c52e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Jot::CTVINotebookListenerWithSyncIcon::UpdateNotebookIconColor(
        Jot::CTVINotebookListenerWithSyncIcon *this)
{
  void (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // r9
  __int64 v3; // rcx
  NetUI::Node *v4; // rbp
  NetUI::Node *v5; // rsi
  NetUI::Node *v6; // rcx
  NetUI::Node *ChildOfIndex; // rax
  NetUI::Node *v8; // rax
  NetUI::Node *v9; // rbx
  const struct NetUI::PropertyInfo *v10; // rax
  const struct NetUI::PropertyInfo *v11; // rax
  const struct NetUI::PropertyInfo *v12; // rax
  NetUI::Node *v13; // rbx
  const struct NetUI::PropertyInfo *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // edx
  NetUI::Element *v17; // rbx
  unsigned int NotebookPaneSectionAndNotebookIconColor; // eax
  __int64 v19; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 8);
  v3 = 0;
  v19 = 0;
  if ( v2 )
  {
    (**v2)(v2, &GUID_0b4dcfc3_4116_4b8e_89ed_1eadf16a0f50, &v19);
    v3 = v19;
  }
  v4 = 0;
  v5 = 0;
  if ( v3 && *((_QWORD *)this + 5) )
  {
    v6 = (NetUI::Node *)*((_QWORD *)this + 13);
    if ( v6 && *((_QWORD *)this + 14) )
    {
      ChildOfIndex = (NetUI::Node *)NetUI::Node::GetChildOfIndex(v6, 0);
      v4 = (NetUI::Node *)NetUI::nui_control_cast<NetUI::Image>(ChildOfIndex);
      v8 = (NetUI::Node *)NetUI::Node::GetChildOfIndex(*((NetUI::Node **)this + 14), 0);
      v5 = (NetUI::Node *)NetUI::nui_control_cast<NetUI::Image>(v8);
    }
    if ( Jot::IsLicensedForFluentUI(v6) && MsoFCbvHighContrast() )
    {
      v9 = (NetUI::Node *)*((_QWORD *)this + 5);
      v10 = (const struct NetUI::PropertyInfo *)NetUI::Node::StyleClassPropInfo();
      NetUI::Node::RemoveLocalValue(v9, v10);
      if ( v4 && v5 )
      {
        v11 = (const struct NetUI::PropertyInfo *)NetUI::Node::StyleClassPropInfo();
        NetUI::Node::RemoveLocalValue(v4, v11);
        v12 = (const struct NetUI::PropertyInfo *)NetUI::Node::StyleClassPropInfo();
        NetUI::Node::RemoveLocalValue(v5, v12);
      }
      v13 = (NetUI::Node *)*((_QWORD *)this + 5);
      v14 = (const struct NetUI::PropertyInfo *)NetUI::Element::ForegroundPropInfo();
      NetUI::Node::RemoveLocalValue(v13, v14);
    }
    else
    {
      NetUI::Node::SetStyleClass(*((NetUI::Node **)this + 5), L"ThemedIconImage");
      if ( v4 && v5 )
      {
        NetUI::Node::SetStyleClass(v4, L"ThemedIconImage");
        NetUI::Node::SetStyleClass(v5, L"ThemedIconImage");
      }
      v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 712LL))(v19);
      if ( v15 != -16777216 )
      {
        v17 = (NetUI::Element *)*((_QWORD *)this + 5);
        NotebookPaneSectionAndNotebookIconColor = Jot::SectionColor::GetNotebookPaneSectionAndNotebookIconColor(
                                                    (Jot::SectionColor *)v15,
                                                    v16);
        NetUI::Element::SetForegroundColor(v17, NotebookPaneSectionAndNotebookIconColor | 0xFF000000);
      }
    }
    v3 = v19;
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x14013c43c  mov     rax, rsp
0x14013c43f  mov     [rax+10h], rbx
0x14013c443  mov     [rax+18h], rbp
0x14013c447  mov     [rax+20h], rsi
0x14013c44b  push    rdi
0x14013c44c  sub     rsp, 20h
0x14013c450  mov     rdi, rcx
0x14013c453  mov     r9, [rcx+40h]
0x14013c457  xor     ecx, ecx
0x14013c459  mov     [rax+8], rcx
0x14013c45d  test    r9, r9
0x14013c460  jz      short loc_14013C482
0x14013c462  mov     rax, [r9]
0x14013c465  lea     r8, [rsp+28h+arg_0]
0x14013c46a  lea     rdx, _GUID_0b4dcfc3_4116_4b8e_89ed_1eadf16a0f50
0x14013c471  mov     rcx, r9
0x14013c474  mov     rax, [rax]
0x14013c477  call    cs:__guard_dispatch_icall_fptr
0x14013c47d  mov     rcx, [rsp+28h+arg_0]
0x14013c482  xor     ebp, ebp
0x14013c484  xor     esi, esi
0x14013c486  test    rcx, rcx
0x14013c489  jz      loc_14013C5B2
0x14013c48f  cmp     [rdi+28h], rsi
0x14013c493  jz      loc_14013C5B2
0x14013c499  mov     rcx, [rdi+68h]
0x14013c49d  test    rcx, rcx
0x14013c4a0  jz      short loc_14013C4D2
0x14013c4a2  cmp     [rdi+70h], rsi
0x14013c4a6  jz      short loc_14013C4D2
0x14013c4a8  xor     edx, edx
0x14013c4aa  call    cs:__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z; NetUI::Node::GetChildOfIndex(int)
0x14013c4b0  mov     rcx, rax; this
0x14013c4b3  call    ??$nui_control_cast@VImage@NetUI@@@NetUI@@YAPEBVImage@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Image>(NetUI::Node const *)
0x14013c4b8  mov     rbp, rax
0x14013c4bb  xor     edx, edx
0x14013c4bd  mov     rcx, [rdi+70h]
0x14013c4c1  call    cs:__imp_?GetChildOfIndex@Node@NetUI@@QEBAPEAV12@H@Z; NetUI::Node::GetChildOfIndex(int)
0x14013c4c7  mov     rcx, rax; this
0x14013c4ca  call    ??$nui_control_cast@VImage@NetUI@@@NetUI@@YAPEBVImage@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Image>(NetUI::Node const *)
0x14013c4cf  mov     rsi, rax
0x14013c4d2  call    cs:__imp_?IsLicensedForFluentUI@Jot@@YA_NXZ; Jot::IsLicensedForFluentUI(void)
0x14013c4d8  test    al, al
0x14013c4da  jz      short loc_14013C542
0x14013c4dc  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x14013c4e2  test    eax, eax
0x14013c4e4  jz      short loc_14013C542
0x14013c4e6  mov     rbx, [rdi+28h]
0x14013c4ea  call    cs:__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Node::StyleClassPropInfo(void)
0x14013c4f0  mov     rdx, rax
0x14013c4f3  mov     rcx, rbx
0x14013c4f6  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x14013c4fc  test    rbp, rbp
0x14013c4ff  jz      short loc_14013C52A
0x14013c501  test    rsi, rsi
0x14013c504  jz      short loc_14013C52A
0x14013c506  call    cs:__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Node::StyleClassPropInfo(void)
0x14013c50c  mov     rdx, rax
0x14013c50f  mov     rcx, rbp
0x14013c512  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x14013c518  call    cs:__imp_?StyleClassPropInfo@Node@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Node::StyleClassPropInfo(void)
0x14013c51e  mov     rdx, rax
0x14013c521  mov     rcx, rsi
0x14013c524  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x14013c52a  mov     rbx, [rdi+28h]
0x14013c52e  call    cs:__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::ForegroundPropInfo(void)
0x14013c534  mov     rdx, rax
0x14013c537  mov     rcx, rbx
0x14013c53a  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x14013c540  jmp     short loc_14013C5AB
0x14013c542  lea     rbx, aThemediconimag; "ThemedIconImage"
0x14013c549  mov     rdx, rbx; wchar_t *
0x14013c54c  mov     rcx, [rdi+28h]; this
0x14013c550  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14013c555  test    rbp, rbp
0x14013c558  jz      short loc_14013C575
0x14013c55a  test    rsi, rsi
0x14013c55d  jz      short loc_14013C575
0x14013c55f  mov     rdx, rbx; wchar_t *
0x14013c562  mov     rcx, rbp; this
0x14013c565  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14013c56a  mov     rdx, rbx; wchar_t *
0x14013c56d  mov     rcx, rsi; this
0x14013c570  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x14013c575  mov     rcx, [rsp+28h+arg_0]
0x14013c57a  mov     rax, [rcx]
0x14013c57d  mov     rax, [rax+2C8h]
0x14013c584  call    cs:__guard_dispatch_icall_fptr
0x14013c58a  mov     esi, 0FF000000h
0x14013c58f  cmp     eax, esi
0x14013c591  jz      short loc_14013C5AB
0x14013c593  mov     rbx, [rdi+28h]
0x14013c597  mov     ecx, eax; this
0x14013c599  call    ?GetNotebookPaneSectionAndNotebookIconColor@SectionColor@Jot@@YAKK@Z; Jot::SectionColor::GetNotebookPaneSectionAndNotebookIconColor(ulong)
0x14013c59e  or      eax, esi
0x14013c5a0  mov     edx, eax; unsigned int
0x14013c5a2  mov     rcx, rbx; this
0x14013c5a5  call    ?SetForegroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetForegroundColor(ulong)
0x14013c5aa  nop
0x14013c5ab  mov     rcx, [rsp+28h+arg_0]
0x14013c5b0  jmp     short $+2
0x14013c5b2  test    rcx, rcx
0x14013c5b5  jz      short loc_14013C5C4
0x14013c5b7  mov     rax, [rcx]
0x14013c5ba  mov     rax, [rax+10h]
0x14013c5be  call    cs:__guard_dispatch_icall_fptr
0x14013c5c4  mov     rbx, [rsp+28h+arg_8]
0x14013c5c9  mov     rbp, [rsp+28h+arg_10]
0x14013c5ce  mov     rsi, [rsp+28h+arg_18]
0x14013c5d3  add     rsp, 20h
0x14013c5d7  pop     rdi
0x14013c5d8  retn
```
