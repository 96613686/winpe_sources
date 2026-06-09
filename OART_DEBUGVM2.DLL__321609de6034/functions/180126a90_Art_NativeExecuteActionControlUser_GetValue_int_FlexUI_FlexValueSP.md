# Art::NativeExecuteActionControlUser::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x180126a90`
- end: `0x1801270be`
- name: `?GetValue@NativeExecuteActionControlUser@Art@@MEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `1582`
- prototype: `bool __fastcall(Art::NativeExecuteActionControlUser *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000eb20`
- `0x180019e80`
- `0x18002a690`
- `0x180084c30`
- `0x18010db54`
- `0x180126a90`
- `0x1801281f0`
- `0x180128400`
- `0x180128640`
- `0x180178f00`
- `0x180180ab0`
- `0x1801e5ef0`
- `0x180204b70`
- `0x180209bdc`
- `0x180210de4`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x1802ddd84`
- `0x18067bc30`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x180126fbe`
- `KERNEL32!DecodePointer` at `0x180126fd0`
- `KERNEL32!DecodePointer` at `0x180126fbe`
- `KERNEL32!DecodePointer` at `0x180126fd0`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180126b13`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180127085`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180126b13`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180127085`
- `Mso98Win32Client!__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z` at `0x180126b06`
- `Mso98Win32Client!__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z` at `0x180126b06`
- `mso40uiWin32Client!__imp_MsoGetLabelFromTcid` at `0x18012709b`
- `mso40uiWin32Client!__imp_MsoGetLabelFromTcid` at `0x18012709b`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180126c84`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180126d06`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801270a9`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180126c84`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180126d06`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801270a9`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180126c76`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180126cf8`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180126c76`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180126cf8`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180126c60`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180126ce2`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180126c60`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180126ce2`

## string_xrefs

- `0x180126e54`: `http://schemas.openxmlformats.org/drawingml/2006/picture`
- `0x180126ee9`: `http://schemas.microsoft.com/office/word/2010/wordprocessingCanvas`
- `0x180126e78`: `http://schemas.openxmlformats.org/drawingml/2006/table`
- `0x180126eb5`: `http://schemas.microsoft.com/office/word/2010/wordprocessingShape`
- `0x180126e92`: `http://schemas.microsoft.com/office/word/2010/wordprocessingInk`

## pseudocode

```c
bool __fastcall Art::NativeExecuteActionControlUser::GetValue(
        OfficeSpace **this,
        struct OfficeSpace::IControl *a2,
        struct FlexUI::FlexValueSP *a3)
{
  int v4; // edi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  char *v10; // r15
  struct Ofc::CProxyPtrImpl **Checked; // rax
  void *v12; // rax
  void (*v13)(void); // rdx
  Ofc::CProxyPtrImpl *v14; // rcx
  Art::View *v15; // rax
  Art::Selection *v16; // rax
  _DWORD *Selection; // rax
  unsigned int v18; // edi
  Art::View *v19; // rax
  Art::Selection *v20; // rax
  Art *v21; // rax
  Art *v22; // rsi
  __int64 v23; // rbx
  unsigned __int8 (__fastcall *v24)(__int64, struct Art::Selection *); // r14
  Art::View *v25; // rax
  struct Art::Selection *v26; // rax
  int v27; // r8d
  __int64 v28; // rax
  bool v29; // bl
  void *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // ebx
  __int64 HinstIntl; // rax
  char v35; // si
  struct Ofc::CProxyPtrImpl **v36; // rax
  struct Ofc::CProxyPtrImpl *v37; // rax
  void *v38; // rax
  const wchar_t *v39; // rax
  __int64 v40; // rbx
  __int64 (__fastcall *v41)(__int64, struct Art::Selection *); // rdi
  Art::View *v42; // rax
  struct Art::Selection *v43; // rax
  char v44; // al
  bool v45; // r9
  Ofc *v46; // rbx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  bool v51; // r9
  bool v52; // r9
  bool v53; // r9
  Art::View *v54; // rax
  Art *v55; // rax
  const struct Art::Selection *v56; // rdx
  bool v57; // r9
  Art::View *v58; // rax
  Art::Selection *v59; // rax
  int *v60; // rax
  bool v61; // r8
  __int64 v62; // rbx
  unsigned __int64 v63; // rdx
  unsigned int v64; // r8d
  __int64 (__fastcall *v65)(__int64); // rax
  _QWORD *v66; // rax
  unsigned __int8 (__fastcall *v67)(__int64, struct Art::Selection *); // rdi
  Art::View *v68; // rax
  struct Art::Selection *v69; // rax
  unsigned int Tcid; // eax
  int v71; // [rsp+20h] [rbp-278h] BYREF
  Ofc::CProxyPtrImpl *v72; // [rsp+28h] [rbp-270h] BYREF
  Ofc *v73; // [rsp+30h] [rbp-268h] BYREF
  Ofc::CProxyPtrImpl *v74; // [rsp+38h] [rbp-260h] BYREF
  Ofc::CProxyPtrImpl *v75; // [rsp+40h] [rbp-258h] BYREF
  struct Ofc::CProxyPtrImpl *v76; // [rsp+48h] [rbp-250h] BYREF
  wchar_t v77; // [rsp+50h] [rbp-248h] BYREF
  wchar_t v78[263]; // [rsp+52h] [rbp-246h] BYREF

  v4 = (int)a2;
  if ( (unsigned int)((_DWORD)a2 - 1) > 1 || !OfficeSpace::FControlOnContextMenu(this[2], a2) )
    return Art::ControlUserBase::GetValue((Art::ControlUserBase *)this, v4, a3);
  v7 = OfficeSpace::DataSourceBase::GetTcid((OfficeSpace::DataSourceBase *)this) - 253;
  if ( v7 )
  {
    v8 = v7 - 526;
    if ( v8 )
    {
      v9 = v8 - 183;
      if ( !v9 || (v47 = v9 - 478) == 0 )
      {
LABEL_7:
        v71 = -201260631;
        v10 = (char *)(this + 4);
        v75 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[4]);
        Checked = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v75);
        v73 = Ofc::CProxyPtrImpl::WeakAddRef(Checked[11]);
        v74 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v73);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v73);
        if ( *((_QWORD *)v74 + 2) )
        {
          v30 = Ofc::CProxyPtrImpl::GetChecked(v74);
          if ( (*(unsigned __int8 (__fastcall **)(void *, __int64, int *))(*(_QWORD *)v30 + 384LL))(v30, 962, &v71) )
          {
            v33 = v71;
            HinstIntl = MsoGetHinstIntl(v32, v31);
            MsoFLoadWz(HinstIntl, v33, &v77, 260);
            LOBYTE(v33) = FlexUI::FlexValue::CreateString(&v77, a3);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v75);
            return v33;
          }
        }
        v12 = Ofc::CProxyPtrImpl::GetChecked(v75);
        Art::UserInterface::GetCurrentView(v12, &v72, 0);
        v14 = v72;
        if ( !*((_QWORD *)v72 + 2) )
          goto LABEL_29;
        v15 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
        v16 = Art::View::EnsureAggregateSelection(v15);
        Selection = Art::Selection::ValidateAndQuerySelection(
                      v16,
                      (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo);
        if ( !Selection || Selection[6] != 1 )
        {
          v18 = -201260640;
          goto LABEL_11;
        }
        v35 = 0;
        v36 = (struct Ofc::CProxyPtrImpl **)Ofc::TArray<Ofc::CVarStr>::operator[](Selection + 4, 0);
        v37 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v36);
        v76 = v37;
        if ( !*((_QWORD *)v37 + 2) )
        {
          v18 = -201260640;
LABEL_28:
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v76);
          if ( !v35 )
          {
LABEL_29:
            v18 = v71;
            goto LABEL_17;
          }
LABEL_11:
          v19 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
          v20 = Art::View::EnsureAggregateSelection(v19);
          v21 = (Art *)Art::Selection::ValidateAndQuerySelection(
                         v20,
                         (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo);
          v22 = v21;
          if ( !v21 || *((_DWORD *)v21 + 4) != 1 )
            goto LABEL_29;
          v23 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
          if ( (unsigned __int64)Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance <= 1 )
          {
            Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>();
            v23 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
          }
          v24 = *(unsigned __int8 (__fastcall **)(__int64, struct Art::Selection *))(*(_QWORD *)v23 + 72LL);
          v25 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
          v26 = Art::View::EnsureAggregateSelection(v25);
          if ( !v24(v23, v26) )
          {
            if ( Art::FSelectionIsLiveFeed(v22, 0, v27) )
            {
              v18 = -201260220;
            }
            else
            {
              v62 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
              if ( (unsigned __int64)Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance <= 1 )
              {
                while ( (unsigned __int64)Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance <= 1 )
                {
                  if ( _InterlockedCompareExchange64(&Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance, 1, 0) )
                  {
                    v76 = 0;
                    std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v76);
                  }
                  else
                  {
                    LOBYTE(v13) = 1;
                    Ofc::AtExit(Ofc::TSingleton<Art::CPictureE2oHelper>::Shutdown, v13, v61);
                    if ( DecodePointer(Ptr) )
                    {
                      v65 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
                      v66 = (_QWORD *)v65(8);
                    }
                    else
                    {
                      v66 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v63, v64);
                    }
                    *v66 = &Art::CPictureE2oHelper::`vftable';
                    _InterlockedCompareExchange64(
                      &Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance,
                      (signed __int64)v66,
                      1);
                  }
                }
                v62 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
              }
              v67 = *(unsigned __int8 (__fastcall **)(__int64, struct Art::Selection *))(*(_QWORD *)v62 + 48LL);
              v68 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
              v69 = Art::View::EnsureAggregateSelection(v68);
              if ( v67(v62, v69) )
              {
                v18 = 362792868;
              }
              else if ( (unsigned __int8)sub_18067BC30(v10) )
              {
                v18 = -201260638;
              }
              else
              {
                if ( !(unsigned __int8)Art::FIsDrawingSelection(v10) )
                  goto LABEL_29;
                v18 = -201260639;
              }
            }
          }
          v71 = v18;
LABEL_17:
          v28 = MsoGetHinstIntl(v14, v13);
          MsoFLoadWz(v28, v18, &v77, 260);
          v29 = FlexUI::FlexValue::CreateString(&v77, a3);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v72);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v75);
          return v29;
        }
        v38 = Ofc::CProxyPtrImpl::GetChecked(v37);
        v39 = (const wchar_t *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v38 + 8LL))(v38);
        Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v73, v39);
        v40 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
        if ( (unsigned __int64)Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance <= 1 )
        {
          Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>();
          v40 = Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance;
        }
        v41 = *(__int64 (__fastcall **)(__int64, struct Art::Selection *))(*(_QWORD *)v40 + 48LL);
        v42 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
        v43 = Art::View::EnsureAggregateSelection(v42);
        v44 = v41(v40, v43);
        v46 = v73;
        if ( v44 )
        {
          v71 = 362792868;
LABEL_26:
          v18 = -201260640;
LABEL_27:
          Ofc::XString::Release((Ofc *)((char *)v46 - 12));
          goto LABEL_28;
        }
        if ( Ofc::FWzEqual(v73, L"http://schemas.openxmlformats.org/drawingml/2006/picture", 0, v45) )
        {
          v18 = -201260640;
          v71 = -201260640;
          goto LABEL_27;
        }
        if ( !Ofc::FWzEqual(v46, L"http://schemas.openxmlformats.org/drawingml/2006/table", 0, v51) )
        {
          if ( Ofc::FWzEqual(v46, L"http://schemas.microsoft.com/office/word/2010/wordprocessingInk", 0, v52) )
          {
            v71 = -201260638;
            goto LABEL_26;
          }
          if ( !Ofc::FWzEqual(v46, L"http://schemas.microsoft.com/office/word/2010/wordprocessingShape", 0, v53) )
          {
            v54 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
            v55 = Art::View::EnsureAggregateSelection(v54);
            if ( !Art::FInE2oDrillDownMode(v55, v56) )
            {
              if ( Ofc::FWzEqual(v46, L"http://schemas.microsoft.com/office/word/2010/wordprocessingCanvas", 0, v57) )
              {
                v58 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
                v59 = Art::View::EnsureAggregateSelection(v58);
                v60 = (int *)Art::Selection::ValidateAndQuerySelection(
                               v59,
                               (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo);
                if ( v60 && v60[4] > 0 )
                  v35 = 1;
                else
                  v71 = -201260637;
              }
              goto LABEL_26;
            }
          }
        }
        v71 = -201260639;
        goto LABEL_26;
      }
      v48 = v47 - 10441;
      if ( v48 )
      {
        v49 = v48 - 4152;
        if ( v49 )
        {
          v50 = v49 - 1;
          if ( v50 )
          {
            if ( v50 == 11495 )
              goto LABEL_7;
            return Art::ControlUserBase::GetValue((Art::ControlUserBase *)this, v4, a3);
          }
        }
      }
    }
  }
  Tcid = OfficeSpace::DataSourceBase::GetTcid((OfficeSpace::DataSourceBase *)this);
  MsoGetLabelFromTcid(1, Tcid, &v77, 260);
  return FlexUI::FlexValue::CreateString(v78, a3);
}

```

## disassembly

```asm
0x180126a90  mov     [rsp+arg_18], rbx
0x180126a95  push    rsi
0x180126a96  push    rdi
0x180126a97  push    r12
0x180126a99  push    r14
0x180126a9b  push    r15
0x180126a9d  sub     rsp, 270h
0x180126aa4  mov     rax, cs:__security_cookie
0x180126aab  xor     rax, rsp
0x180126aae  mov     [rsp+298h+var_38], rax
0x180126ab6  mov     r12, r8
0x180126ab9  mov     edi, edx
0x180126abb  mov     rbx, rcx
0x180126abe  lea     eax, [rdx-1]
0x180126ac1  mov     r14d, 1
0x180126ac7  cmp     eax, r14d
0x180126aca  jbe     short loc_180126B02
0x180126acc  mov     r8, r12; struct FlexUI::FlexValueSP *
0x180126acf  mov     edx, edi; int
0x180126ad1  mov     rcx, rbx; this
0x180126ad4  call    ?GetValue@ControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; Art::ControlUserBase::GetValue(int,FlexUI::FlexValueSP &)
0x180126ad9  nop
0x180126ada  mov     rcx, [rsp+298h+var_38]
0x180126ae2  xor     rcx, rsp; StackCookie
0x180126ae5  call    __security_check_cookie
0x180126aea  mov     rbx, [rsp+298h+arg_18]
0x180126af2  add     rsp, 270h
0x180126af9  pop     r15
0x180126afb  pop     r14
0x180126afd  pop     r12
0x180126aff  pop     rdi
0x180126b00  pop     rsi
0x180126b01  retn
0x180126b02  mov     rcx, [rcx+10h]
0x180126b06  call    cs:__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z; OfficeSpace::FControlOnContextMenu(OfficeSpace::IControl *)
0x180126b0c  test    al, al
0x180126b0e  jz      short loc_180126ACC
0x180126b10  mov     rcx, rbx
0x180126b13  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x180126b19  sub     eax, 0FDh
0x180126b1e  jz      loc_180127082
0x180126b24  sub     eax, 20Eh
0x180126b29  jz      loc_180127082
0x180126b2f  sub     eax, 0B7h
0x180126b34  jnz     loc_180126E17
0x180126b3a  mov     [rsp+298h+var_278], 0F40101A9h
0x180126b42  lea     r15, [rbx+20h]
0x180126b46  mov     rcx, [r15]; struct Ofc::CProxyPtrImpl *
0x180126b49  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180126b4e  mov     [rsp+298h+var_258], rax
0x180126b53  mov     rcx, rax; this
0x180126b56  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126b5b  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x180126b5f  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180126b64  mov     [rsp+298h+var_268], rax
0x180126b69  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180126b6c  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180126b71  mov     [rsp+298h+var_260], rax
0x180126b76  lea     rcx, [rsp+298h+var_268]; struct Ofc::CProxyPtrImpl **
0x180126b7b  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180126b80  mov     rcx, [rsp+298h+var_260]; this
0x180126b85  cmp     qword ptr [rcx+10h], 0
0x180126b8a  jnz     loc_180126CB1
0x180126b90  mov     rcx, [rsp+298h+var_258]; this
0x180126b95  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126b9a  xor     r8d, r8d
0x180126b9d  lea     rdx, [rsp+298h+var_270]
0x180126ba2  mov     rcx, rax
0x180126ba5  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x180126baa  nop
0x180126bab  mov     rcx, [rsp+298h+var_270]; this
0x180126bb0  cmp     qword ptr [rcx+10h], 0
0x180126bb5  jz      loc_180126DEC
0x180126bbb  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126bc0  mov     rcx, rax; this
0x180126bc3  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126bc8  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VE2oSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x180126bcf  mov     rcx, rax; this
0x180126bd2  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x180126bd7  test    rax, rax
0x180126bda  jnz     loc_180126D29
0x180126be0  mov     edi, 0F40101A0h
0x180126be5  mov     rcx, [rsp+298h+var_270]; this
0x180126bea  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126bef  mov     rcx, rax; this
0x180126bf2  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126bf7  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x180126bfe  mov     rcx, rax; this
0x180126c01  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x180126c06  mov     rsi, rax
0x180126c09  test    rax, rax
0x180126c0c  jz      loc_180126DEC
0x180126c12  cmp     [rax+10h], r14d
0x180126c16  jnz     loc_180126DEC
0x180126c1c  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126c23  cmp     rbx, r14
0x180126c26  jbe     loc_180126DF5
0x180126c2c  mov     rax, [rbx]
0x180126c2f  mov     r14, [rax+48h]
0x180126c33  mov     rcx, [rsp+298h+var_270]; this
0x180126c38  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126c3d  mov     rcx, rax; this
0x180126c40  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126c45  mov     rdx, rax
0x180126c48  mov     rcx, rbx
0x180126c4b  mov     rax, r14
0x180126c4e  call    cs:__guard_dispatch_icall_fptr
0x180126c54  test    al, al
0x180126c56  jz      loc_180126F58
0x180126c5c  mov     [rsp+298h+var_278], edi
0x180126c60  call    cs:__imp_MsoGetHinstIntl
0x180126c66  mov     r9d, 104h
0x180126c6c  lea     r8, [rsp+298h+var_248]
0x180126c71  mov     edx, edi
0x180126c73  mov     rcx, rax
0x180126c76  call    cs:__imp_MsoFLoadWz
0x180126c7c  mov     rdx, r12
0x180126c7f  lea     rcx, [rsp+298h+var_248]
0x180126c84  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x180126c8a  mov     bl, al
0x180126c8c  lea     rcx, [rsp+298h+var_270]; struct Ofc::CProxyPtrImpl **
0x180126c91  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126c96  lea     rcx, [rsp+298h+var_260]; struct Ofc::CProxyPtrImpl **
0x180126c9b  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126ca0  lea     rcx, [rsp+298h+var_258]; struct Ofc::CProxyPtrImpl **
0x180126ca5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126caa  mov     al, bl
0x180126cac  jmp     loc_180126ADA
0x180126cb1  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126cb6  mov     r9, rax
0x180126cb9  mov     rcx, [rax]
0x180126cbc  mov     rax, [rcx+180h]
0x180126cc3  lea     r8, [rsp+298h+var_278]
0x180126cc8  mov     edx, 3C2h
0x180126ccd  mov     rcx, r9
0x180126cd0  call    cs:__guard_dispatch_icall_fptr
0x180126cd6  test    al, al
0x180126cd8  jz      loc_180126B90
0x180126cde  mov     ebx, [rsp+298h+var_278]
0x180126ce2  call    cs:__imp_MsoGetHinstIntl
0x180126ce8  mov     r9d, 104h
0x180126cee  lea     r8, [rsp+298h+var_248]
0x180126cf3  mov     edx, ebx
0x180126cf5  mov     rcx, rax
0x180126cf8  call    cs:__imp_MsoFLoadWz
0x180126cfe  mov     rdx, r12
0x180126d01  lea     rcx, [rsp+298h+var_248]
0x180126d06  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x180126d0c  mov     bl, al
0x180126d0e  lea     rcx, [rsp+298h+var_260]; struct Ofc::CProxyPtrImpl **
0x180126d13  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126d18  lea     rcx, [rsp+298h+var_258]; struct Ofc::CProxyPtrImpl **
0x180126d1d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126d22  mov     al, bl
0x180126d24  jmp     loc_180126ADA
0x180126d29  cmp     [rax+18h], r14d
0x180126d2d  jnz     loc_180126BE0
0x180126d33  xor     sil, sil
0x180126d36  lea     rcx, [rax+10h]
0x180126d3a  xor     edx, edx
0x180126d3c  call    ??A?$TArray@VCVarStr@Ofc@@@Ofc@@QEBAAEBVCVarStr@1@K@Z; Ofc::TArray<Ofc::CVarStr>::operator[](ulong)
0x180126d41  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180126d44  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180126d49  mov     [rsp+298h+var_250], rax
0x180126d4e  cmp     qword ptr [rax+10h], 0
0x180126d53  jz      loc_180126F4E
0x180126d59  mov     rcx, rax; this
0x180126d5c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126d61  mov     rdx, rax
0x180126d64  mov     rcx, [rax]
0x180126d67  mov     rax, [rcx+8]
0x180126d6b  mov     rcx, rdx
0x180126d6e  call    cs:__guard_dispatch_icall_fptr
0x180126d74  mov     rdx, rax; wchar_t *
0x180126d77  lea     rcx, [rsp+298h+var_268]; this
0x180126d7c  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x180126d81  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126d88  cmp     rbx, r14
0x180126d8b  jbe     short loc_180126E06
0x180126d8d  mov     rax, [rbx]
0x180126d90  mov     rdi, [rax+30h]
0x180126d94  mov     rcx, [rsp+298h+var_270]; this
0x180126d99  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126d9e  mov     rcx, rax; this
0x180126da1  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126da6  mov     rdx, rax
0x180126da9  mov     rcx, rbx
0x180126dac  mov     rax, rdi
0x180126daf  call    cs:__guard_dispatch_icall_fptr
0x180126db5  mov     rbx, [rsp+298h+var_268]
0x180126dba  test    al, al
0x180126dbc  jz      loc_180126E51
0x180126dc2  mov     [rsp+298h+var_278], 159FC7A4h
0x180126dca  mov     edi, 0F40101A0h
0x180126dcf  lea     rcx, [rbx-0Ch]; this
0x180126dd3  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x180126dd8  nop
0x180126dd9  lea     rcx, [rsp+298h+var_250]; struct Ofc::CProxyPtrImpl **
0x180126dde  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180126de3  test    sil, sil
0x180126de6  jnz     loc_180126BE5
0x180126dec  mov     edi, [rsp+298h+var_278]
0x180126df0  jmp     loc_180126C60
0x180126df5  call    ??$ThreadSafeInitPointerOnce@PEAVCPictureE2oHelper@Art@@V?$TSingletonFactory@VCPictureE2oHelper@Art@@@Ofc@@@Ofc@@YAXPECREAVCPictureE2oHelper@Art@@@Z; Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>(Art::CPictureE2oHelper * volatile *)
0x180126dfa  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126e01  jmp     loc_180126C2C
0x180126e06  call    ??$ThreadSafeInitPointerOnce@PEAVCPictureE2oHelper@Art@@V?$TSingletonFactory@VCPictureE2oHelper@Art@@@Ofc@@@Ofc@@YAXPECREAVCPictureE2oHelper@Art@@@Z; Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>(Art::CPictureE2oHelper * volatile *)
0x180126e0b  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126e12  jmp     loc_180126D8D
0x180126e17  sub     eax, 1DEh
0x180126e1c  jz      loc_180126B3A
0x180126e22  sub     eax, 28C9h
0x180126e27  jz      loc_180127082
0x180126e2d  sub     eax, 1038h
0x180126e32  jz      loc_180127082
0x180126e38  sub     eax, r14d
0x180126e3b  jz      loc_180127082
0x180126e41  cmp     eax, 2CE7h
0x180126e46  jnz     loc_180126ACC
0x180126e4c  jmp     loc_180126B3A
0x180126e51  xor     r8d, r8d; wchar_t *
0x180126e54  lea     rdx, ?c_wzPictureE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.openxmlformats.org/drawi"...
0x180126e5b  mov     rcx, rbx; this
0x180126e5e  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x180126e63  test    al, al
0x180126e65  jz      short loc_180126E75
0x180126e67  mov     edi, 0F40101A0h
0x180126e6c  mov     [rsp+298h+var_278], edi
0x180126e70  jmp     loc_180126DCF
0x180126e75  xor     r8d, r8d; wchar_t *
0x180126e78  lea     rdx, ?c_wzTableE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.openxmlformats.org/drawi"...
0x180126e7f  mov     rcx, rbx; this
0x180126e82  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x180126e87  test    al, al
0x180126e89  jnz     loc_180126F41
0x180126e8f  xor     r8d, r8d; wchar_t *
0x180126e92  lea     rdx, ?c_wzWordInkE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x180126e99  mov     rcx, rbx; this
0x180126e9c  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x180126ea1  test    al, al
0x180126ea3  jz      short loc_180126EB2
0x180126ea5  mov     [rsp+298h+var_278], 0F40101A2h
0x180126ead  jmp     loc_180126DCA
0x180126eb2  xor     r8d, r8d; wchar_t *
0x180126eb5  lea     rdx, ?c_wzWordShapeE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x180126ebc  mov     rcx, rbx; this
0x180126ebf  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x180126ec4  test    al, al
0x180126ec6  jnz     short loc_180126F41
0x180126ec8  mov     rcx, [rsp+298h+var_270]; this
0x180126ecd  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126ed2  mov     rcx, rax; this
0x180126ed5  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126eda  mov     rcx, rax; this
0x180126edd  call    ?FInE2oDrillDownMode@Art@@YA_NAEBVSelection@1@@Z; Art::FInE2oDrillDownMode(Art::Selection const &)
0x180126ee2  test    al, al
0x180126ee4  jnz     short loc_180126F41
0x180126ee6  xor     r8d, r8d; wchar_t *
0x180126ee9  lea     rdx, ?c_wzCanvasE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x180126ef0  mov     rcx, rbx; this
0x180126ef3  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x180126ef8  test    al, al
0x180126efa  jz      loc_180126DCA
0x180126f00  mov     rcx, [rsp+298h+var_270]; this
0x180126f05  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180126f0a  mov     rcx, rax; this
0x180126f0d  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180126f12  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x180126f19  mov     rcx, rax; this
0x180126f1c  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x180126f21  test    rax, rax
0x180126f24  jz      short loc_180126F34
0x180126f26  cmp     dword ptr [rax+10h], 0
0x180126f2a  jle     short loc_180126F34
0x180126f2c  mov     sil, r14b
0x180126f2f  jmp     loc_180126DCA
0x180126f34  mov     [rsp+298h+var_278], 0F40101A3h
0x180126f3c  jmp     loc_180126DCA
0x180126f41  mov     [rsp+298h+var_278], 0F40101A1h
0x180126f49  jmp     loc_180126DCA
0x180126f4e  mov     edi, 0F40101A0h
0x180126f53  jmp     loc_180126DD9
0x180126f58  xor     edx, edx; struct Dr::DrawingSelectionInfo *
0x180126f5a  mov     rcx, rsi; this
0x180126f5d  call    ?FSelectionIsLiveFeed@Art@@YA_NPEBVDrawingSelectionInfo@Dr@@H@Z; Art::FSelectionIsLiveFeed(Dr::DrawingSelectionInfo const *,int)
0x180126f62  test    al, al
0x180126f64  jz      short loc_180126F70
0x180126f66  mov     edi, 0F4010344h
0x180126f6b  jmp     loc_180126C5C
0x180126f70  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126f77  mov     edi, 1
0x180126f7c  cmp     rbx, rdi
0x180126f7f  ja      loc_18012701C
0x180126f85  lea     ebx, [rdi+7]
0x180126f88  lea     rsi, ??_7CPictureE2oHelper@Art@@6B@; const Art::CPictureE2oHelper::`vftable'
0x180126f8f  mov     rax, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x180126f96  cmp     rax, rdi
0x180126f99  ja      short loc_180127015
0x180126f9b  xor     eax, eax
0x180126f9d  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA, rdi; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
  ... truncated ...
```
