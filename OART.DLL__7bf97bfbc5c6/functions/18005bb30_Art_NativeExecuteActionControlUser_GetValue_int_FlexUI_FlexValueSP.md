# Art::NativeExecuteActionControlUser::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x18005bb30`
- end: `0x18005c153`
- name: `?GetValue@NativeExecuteActionControlUser@Art@@MEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `1571`
- prototype: `bool __fastcall(Art::NativeExecuteActionControlUser *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003c60`
- `0x18001d1a0`
- `0x1800373d0`
- `0x180038180`
- `0x18003fda0`
- `0x180053654`
- `0x18005bb30`
- `0x18005f7f0`
- `0x1800659a0`
- `0x18006cbe0`
- `0x180070fe0`
- `0x180071720`
- `0x1800a241c`
- `0x18012e100`
- `0x1801aa600`
- `0x180344680`
- `0x18035c3b0`
- `0x1803f0518`
- `0x180653b10`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18005c053`
- `KERNEL32!DecodePointer` at `0x18005c065`
- `KERNEL32!DecodePointer` at `0x18005c053`
- `KERNEL32!DecodePointer` at `0x18005c065`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x18005bbb3`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x18005c11a`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x18005bbb3`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x18005c11a`
- `Mso98Win32Client!__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z` at `0x18005bba6`
- `Mso98Win32Client!__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z` at `0x18005bba6`
- `mso40uiWin32Client!__imp_MsoGetLabelFromTcid` at `0x18005c130`
- `mso40uiWin32Client!__imp_MsoGetLabelFromTcid` at `0x18005c130`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005bd33`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005bdb5`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005c13e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005bd33`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005bdb5`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18005c13e`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x18005bd25`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x18005bda7`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x18005bd25`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x18005bda7`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18005bd0f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18005bd91`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18005bd0f`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18005bd91`

## string_xrefs

- `0x18005bee9`: `http://schemas.openxmlformats.org/drawingml/2006/picture`
- `0x18005bf4a`: `http://schemas.microsoft.com/office/word/2010/wordprocessingShape`
- `0x18005bf27`: `http://schemas.microsoft.com/office/word/2010/wordprocessingInk`
- `0x18005bf7e`: `http://schemas.microsoft.com/office/word/2010/wordprocessingCanvas`
- `0x18005bf0d`: `http://schemas.openxmlformats.org/drawingml/2006/table`

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
  volatile signed __int32 *v11; // rcx
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
  void *Checked; // rax
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
        v11 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v75) + 11);
        if ( *((_DWORD *)v11 + 1) != 0x80000000 )
          _InterlockedAdd(v11 + 1, 1u);
        v73 = (Ofc *)v11;
        v74 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v11);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v73);
        if ( *((_QWORD *)v74 + 2) )
        {
          Checked = Ofc::CProxyPtrImpl::GetChecked(v74);
          if ( (*(unsigned __int8 (__fastcall **)(void *, __int64, int *))(*(_QWORD *)Checked + 384LL))(
                 Checked,
                 962,
                 &v71) )
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
          goto LABEL_31;
        v15 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
        v16 = Art::View::EnsureAggregateSelection(v15);
        Selection = Art::Selection::ValidateAndQuerySelection(
                      v16,
                      (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo);
        if ( !Selection || Selection[6] != 1 )
        {
          v18 = -201260640;
          goto LABEL_13;
        }
        v35 = 0;
        v36 = (struct Ofc::CProxyPtrImpl **)Ofc::TArray<Ofc::CVarStr>::operator[](Selection + 4, 0);
        v37 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v36);
        v76 = v37;
        if ( !*((_QWORD *)v37 + 2) )
        {
          v18 = -201260640;
LABEL_30:
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v76);
          if ( !v35 )
          {
LABEL_31:
            v18 = v71;
            goto LABEL_19;
          }
LABEL_13:
          v19 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v72);
          v20 = Art::View::EnsureAggregateSelection(v19);
          v21 = (Art *)Art::Selection::ValidateAndQuerySelection(
                         v20,
                         (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo);
          v22 = v21;
          if ( !v21 || *((_DWORD *)v21 + 4) != 1 )
            goto LABEL_31;
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
              v18 = -201260221;
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
              else if ( (unsigned __int8)sub_180653B10(v10) )
              {
                v18 = -201260638;
              }
              else
              {
                if ( !(unsigned __int8)Art::FIsDrawingSelection(v10) )
                  goto LABEL_31;
                v18 = -201260639;
              }
            }
          }
          v71 = v18;
LABEL_19:
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
LABEL_28:
          v18 = -201260640;
LABEL_29:
          Ofc::XString::Release((Ofc *)((char *)v46 - 12));
          goto LABEL_30;
        }
        if ( Ofc::FWzEqual(v73, L"http://schemas.openxmlformats.org/drawingml/2006/picture", 0, v45) )
        {
          v18 = -201260640;
          v71 = -201260640;
          goto LABEL_29;
        }
        if ( !Ofc::FWzEqual(v46, L"http://schemas.openxmlformats.org/drawingml/2006/table", 0, v51) )
        {
          if ( Ofc::FWzEqual(v46, L"http://schemas.microsoft.com/office/word/2010/wordprocessingInk", 0, v52) )
          {
            v71 = -201260638;
            goto LABEL_28;
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
              goto LABEL_28;
            }
          }
        }
        v71 = -201260639;
        goto LABEL_28;
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
0x18005bb30  mov     [rsp+arg_18], rbx
0x18005bb35  push    rsi
0x18005bb36  push    rdi
0x18005bb37  push    r12
0x18005bb39  push    r14
0x18005bb3b  push    r15
0x18005bb3d  sub     rsp, 270h
0x18005bb44  mov     rax, cs:__security_cookie
0x18005bb4b  xor     rax, rsp
0x18005bb4e  mov     [rsp+298h+var_38], rax
0x18005bb56  mov     r12, r8
0x18005bb59  mov     edi, edx
0x18005bb5b  mov     rbx, rcx
0x18005bb5e  lea     eax, [rdx-1]
0x18005bb61  mov     r14d, 1
0x18005bb67  cmp     eax, r14d
0x18005bb6a  jbe     short loc_18005BBA2
0x18005bb6c  mov     r8, r12; struct FlexUI::FlexValueSP *
0x18005bb6f  mov     edx, edi; int
0x18005bb71  mov     rcx, rbx; this
0x18005bb74  call    ?GetValue@ControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; Art::ControlUserBase::GetValue(int,FlexUI::FlexValueSP &)
0x18005bb79  nop
0x18005bb7a  mov     rcx, [rsp+298h+var_38]
0x18005bb82  xor     rcx, rsp; StackCookie
0x18005bb85  call    __security_check_cookie
0x18005bb8a  mov     rbx, [rsp+298h+arg_18]
0x18005bb92  add     rsp, 270h
0x18005bb99  pop     r15
0x18005bb9b  pop     r14
0x18005bb9d  pop     r12
0x18005bb9f  pop     rdi
0x18005bba0  pop     rsi
0x18005bba1  retn
0x18005bba2  mov     rcx, [rcx+10h]
0x18005bba6  call    cs:__imp_?FControlOnContextMenu@OfficeSpace@@YA_NPEAUIControl@1@@Z; OfficeSpace::FControlOnContextMenu(OfficeSpace::IControl *)
0x18005bbac  test    al, al
0x18005bbae  jz      short loc_18005BB6C
0x18005bbb0  mov     rcx, rbx
0x18005bbb3  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x18005bbb9  sub     eax, 0FDh
0x18005bbbe  jz      loc_18005C117
0x18005bbc4  sub     eax, 20Eh
0x18005bbc9  jz      loc_18005C117
0x18005bbcf  sub     eax, 0B7h
0x18005bbd4  jnz     loc_18005BEAC
0x18005bbda  mov     [rsp+298h+var_278], 0F40101A9h
0x18005bbe2  lea     r15, [rbx+20h]
0x18005bbe6  mov     rcx, [r15]; struct Ofc::CProxyPtrImpl *
0x18005bbe9  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18005bbee  mov     [rsp+298h+var_258], rax
0x18005bbf3  mov     rcx, rax; this
0x18005bbf6  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bbfb  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x18005bbff  mov     eax, [rcx+4]
0x18005bc02  cmp     eax, 80000000h
0x18005bc07  jz      short loc_18005BC0E
0x18005bc09  lock add [rcx+4], r14d
0x18005bc0e  mov     [rsp+298h+var_268], rcx
0x18005bc13  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18005bc18  mov     [rsp+298h+var_260], rax
0x18005bc1d  lea     rcx, [rsp+298h+var_268]; struct Ofc::CProxyPtrImpl **
0x18005bc22  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18005bc27  mov     rcx, [rsp+298h+var_260]; this
0x18005bc2c  cmp     qword ptr [rcx+10h], 0
0x18005bc31  jnz     loc_18005BD60
0x18005bc37  mov     rcx, [rsp+298h+var_258]; this
0x18005bc3c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bc41  xor     r8d, r8d
0x18005bc44  lea     rdx, [rsp+298h+var_270]
0x18005bc49  mov     rcx, rax
0x18005bc4c  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x18005bc51  nop
0x18005bc52  mov     rcx, [rsp+298h+var_270]; this
0x18005bc57  cmp     qword ptr [rcx+10h], 0
0x18005bc5c  jz      loc_18005BEA3
0x18005bc62  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bc67  mov     rcx, rax; this
0x18005bc6a  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005bc6f  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VE2oSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x18005bc76  mov     rcx, rax; this
0x18005bc79  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x18005bc7e  test    rax, rax
0x18005bc81  jnz     loc_18005BDD8
0x18005bc87  mov     edi, 0F40101A0h
0x18005bc8c  mov     rcx, [rsp+298h+var_270]; this
0x18005bc91  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bc96  mov     rcx, rax; this
0x18005bc99  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005bc9e  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x18005bca5  mov     rcx, rax; this
0x18005bca8  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x18005bcad  mov     rsi, rax
0x18005bcb0  test    rax, rax
0x18005bcb3  jz      loc_18005BEA3
0x18005bcb9  cmp     [rax+10h], r14d
0x18005bcbd  jnz     loc_18005BEA3
0x18005bcc3  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005bcca  cmp     rbx, r14
0x18005bccd  ja      short loc_18005BCDB
0x18005bccf  call    ??$ThreadSafeInitPointerOnce@PEAVCPictureE2oHelper@Art@@V?$TSingletonFactory@VCPictureE2oHelper@Art@@@Ofc@@@Ofc@@YAXPECREAVCPictureE2oHelper@Art@@@Z; Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>(Art::CPictureE2oHelper * volatile *)
0x18005bcd4  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005bcdb  mov     rax, [rbx]
0x18005bcde  mov     r14, [rax+48h]
0x18005bce2  mov     rcx, [rsp+298h+var_270]; this
0x18005bce7  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bcec  mov     rcx, rax; this
0x18005bcef  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005bcf4  mov     rdx, rax
0x18005bcf7  mov     rcx, rbx
0x18005bcfa  mov     rax, r14
0x18005bcfd  call    cs:__guard_dispatch_icall_fptr
0x18005bd03  test    al, al
0x18005bd05  jz      loc_18005BFED
0x18005bd0b  mov     [rsp+298h+var_278], edi
0x18005bd0f  call    cs:__imp_MsoGetHinstIntl
0x18005bd15  mov     r9d, 104h
0x18005bd1b  lea     r8, [rsp+298h+var_248]
0x18005bd20  mov     edx, edi
0x18005bd22  mov     rcx, rax
0x18005bd25  call    cs:__imp_MsoFLoadWz
0x18005bd2b  mov     rdx, r12
0x18005bd2e  lea     rcx, [rsp+298h+var_248]
0x18005bd33  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x18005bd39  mov     bl, al
0x18005bd3b  lea     rcx, [rsp+298h+var_270]; struct Ofc::CProxyPtrImpl **
0x18005bd40  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005bd45  lea     rcx, [rsp+298h+var_260]; struct Ofc::CProxyPtrImpl **
0x18005bd4a  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005bd4f  lea     rcx, [rsp+298h+var_258]; struct Ofc::CProxyPtrImpl **
0x18005bd54  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005bd59  mov     al, bl
0x18005bd5b  jmp     loc_18005BB7A
0x18005bd60  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bd65  mov     r9, rax
0x18005bd68  mov     rcx, [rax]
0x18005bd6b  mov     rax, [rcx+180h]
0x18005bd72  lea     r8, [rsp+298h+var_278]
0x18005bd77  mov     edx, 3C2h
0x18005bd7c  mov     rcx, r9
0x18005bd7f  call    cs:__guard_dispatch_icall_fptr
0x18005bd85  test    al, al
0x18005bd87  jz      loc_18005BC37
0x18005bd8d  mov     ebx, [rsp+298h+var_278]
0x18005bd91  call    cs:__imp_MsoGetHinstIntl
0x18005bd97  mov     r9d, 104h
0x18005bd9d  lea     r8, [rsp+298h+var_248]
0x18005bda2  mov     edx, ebx
0x18005bda4  mov     rcx, rax
0x18005bda7  call    cs:__imp_MsoFLoadWz
0x18005bdad  mov     rdx, r12
0x18005bdb0  lea     rcx, [rsp+298h+var_248]
0x18005bdb5  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x18005bdbb  mov     bl, al
0x18005bdbd  lea     rcx, [rsp+298h+var_260]; struct Ofc::CProxyPtrImpl **
0x18005bdc2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005bdc7  lea     rcx, [rsp+298h+var_258]; struct Ofc::CProxyPtrImpl **
0x18005bdcc  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005bdd1  mov     al, bl
0x18005bdd3  jmp     loc_18005BB7A
0x18005bdd8  cmp     [rax+18h], r14d
0x18005bddc  jnz     loc_18005BC87
0x18005bde2  xor     sil, sil
0x18005bde5  lea     rcx, [rax+10h]
0x18005bde9  xor     edx, edx
0x18005bdeb  call    ??A?$TArray@VCVarStr@Ofc@@@Ofc@@QEBAAEBVCVarStr@1@K@Z; Ofc::TArray<Ofc::CVarStr>::operator[](ulong)
0x18005bdf0  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x18005bdf3  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18005bdf8  mov     [rsp+298h+var_250], rax
0x18005bdfd  cmp     qword ptr [rax+10h], 0
0x18005be02  jz      loc_18005BFE3
0x18005be08  mov     rcx, rax; this
0x18005be0b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005be10  mov     rdx, rax
0x18005be13  mov     rcx, [rax]
0x18005be16  mov     rax, [rcx+8]
0x18005be1a  mov     rcx, rdx
0x18005be1d  call    cs:__guard_dispatch_icall_fptr
0x18005be23  mov     rdx, rax; wchar_t *
0x18005be26  lea     rcx, [rsp+298h+var_268]; this
0x18005be2b  call    ??0CVarStr@Ofc@@QEAA@PEB_W@Z; Ofc::CVarStr::CVarStr(wchar_t const *)
0x18005be30  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005be37  cmp     rbx, r14
0x18005be3a  ja      short loc_18005BE48
0x18005be3c  call    ??$ThreadSafeInitPointerOnce@PEAVCPictureE2oHelper@Art@@V?$TSingletonFactory@VCPictureE2oHelper@Art@@@Ofc@@@Ofc@@YAXPECREAVCPictureE2oHelper@Art@@@Z; Ofc::ThreadSafeInitPointerOnce<Art::CPictureE2oHelper *,Ofc::TSingletonFactory<Art::CPictureE2oHelper>>(Art::CPictureE2oHelper * volatile *)
0x18005be41  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005be48  mov     rax, [rbx]
0x18005be4b  mov     rdi, [rax+30h]
0x18005be4f  mov     rcx, [rsp+298h+var_270]; this
0x18005be54  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005be59  mov     rcx, rax; this
0x18005be5c  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005be61  mov     rdx, rax
0x18005be64  mov     rcx, rbx
0x18005be67  mov     rax, rdi
0x18005be6a  call    cs:__guard_dispatch_icall_fptr
0x18005be70  mov     rbx, [rsp+298h+var_268]
0x18005be75  test    al, al
0x18005be77  jz      short loc_18005BEE6
0x18005be79  mov     [rsp+298h+var_278], 159FC7A4h
0x18005be81  mov     edi, 0F40101A0h
0x18005be86  lea     rcx, [rbx-0Ch]; this
0x18005be8a  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x18005be8f  nop
0x18005be90  lea     rcx, [rsp+298h+var_250]; struct Ofc::CProxyPtrImpl **
0x18005be95  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18005be9a  test    sil, sil
0x18005be9d  jnz     loc_18005BC8C
0x18005bea3  mov     edi, [rsp+298h+var_278]
0x18005bea7  jmp     loc_18005BD0F
0x18005beac  sub     eax, 1DEh
0x18005beb1  jz      loc_18005BBDA
0x18005beb7  sub     eax, 28C9h
0x18005bebc  jz      loc_18005C117
0x18005bec2  sub     eax, 1038h
0x18005bec7  jz      loc_18005C117
0x18005becd  sub     eax, r14d
0x18005bed0  jz      loc_18005C117
0x18005bed6  cmp     eax, 2CE7h
0x18005bedb  jnz     loc_18005BB6C
0x18005bee1  jmp     loc_18005BBDA
0x18005bee6  xor     r8d, r8d; wchar_t *
0x18005bee9  lea     rdx, ?c_wzPictureE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.openxmlformats.org/drawi"...
0x18005bef0  mov     rcx, rbx; this
0x18005bef3  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18005bef8  test    al, al
0x18005befa  jz      short loc_18005BF0A
0x18005befc  mov     edi, 0F40101A0h
0x18005bf01  mov     [rsp+298h+var_278], edi
0x18005bf05  jmp     loc_18005BE86
0x18005bf0a  xor     r8d, r8d; wchar_t *
0x18005bf0d  lea     rdx, ?c_wzTableE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.openxmlformats.org/drawi"...
0x18005bf14  mov     rcx, rbx; this
0x18005bf17  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18005bf1c  test    al, al
0x18005bf1e  jnz     loc_18005BFD6
0x18005bf24  xor     r8d, r8d; wchar_t *
0x18005bf27  lea     rdx, ?c_wzWordInkE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x18005bf2e  mov     rcx, rbx; this
0x18005bf31  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18005bf36  test    al, al
0x18005bf38  jz      short loc_18005BF47
0x18005bf3a  mov     [rsp+298h+var_278], 0F40101A2h
0x18005bf42  jmp     loc_18005BE81
0x18005bf47  xor     r8d, r8d; wchar_t *
0x18005bf4a  lea     rdx, ?c_wzWordShapeE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x18005bf51  mov     rcx, rbx; this
0x18005bf54  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18005bf59  test    al, al
0x18005bf5b  jnz     short loc_18005BFD6
0x18005bf5d  mov     rcx, [rsp+298h+var_270]; this
0x18005bf62  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bf67  mov     rcx, rax; this
0x18005bf6a  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005bf6f  mov     rcx, rax; this
0x18005bf72  call    ?FInE2oDrillDownMode@Art@@YA_NAEBVSelection@1@@Z; Art::FInE2oDrillDownMode(Art::Selection const &)
0x18005bf77  test    al, al
0x18005bf79  jnz     short loc_18005BFD6
0x18005bf7b  xor     r8d, r8d; wchar_t *
0x18005bf7e  lea     rdx, ?c_wzCanvasE2oUri@Namespaces@Xsd@Mso@@3QB_WB; "http://schemas.microsoft.com/office/wor"...
0x18005bf85  mov     rcx, rbx; this
0x18005bf88  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18005bf8d  test    al, al
0x18005bf8f  jz      loc_18005BE81
0x18005bf95  mov     rcx, [rsp+298h+var_270]; this
0x18005bf9a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18005bf9f  mov     rcx, rax; this
0x18005bfa2  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x18005bfa7  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x18005bfae  mov     rcx, rax; this
0x18005bfb1  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x18005bfb6  test    rax, rax
0x18005bfb9  jz      short loc_18005BFC9
0x18005bfbb  cmp     dword ptr [rax+10h], 0
0x18005bfbf  jle     short loc_18005BFC9
0x18005bfc1  mov     sil, r14b
0x18005bfc4  jmp     loc_18005BE81
0x18005bfc9  mov     [rsp+298h+var_278], 0F40101A3h
0x18005bfd1  jmp     loc_18005BE81
0x18005bfd6  mov     [rsp+298h+var_278], 0F40101A1h
0x18005bfde  jmp     loc_18005BE81
0x18005bfe3  mov     edi, 0F40101A0h
0x18005bfe8  jmp     loc_18005BE90
0x18005bfed  xor     edx, edx; struct Dr::DrawingSelectionInfo *
0x18005bfef  mov     rcx, rsi; this
0x18005bff2  call    ?FSelectionIsLiveFeed@Art@@YA_NPEBVDrawingSelectionInfo@Dr@@H@Z; Art::FSelectionIsLiveFeed(Dr::DrawingSelectionInfo const *,int)
0x18005bff7  test    al, al
0x18005bff9  jz      short loc_18005C005
0x18005bffb  mov     edi, 0F4010343h
0x18005c000  jmp     loc_18005BD0B
0x18005c005  mov     rbx, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005c00c  mov     edi, 1
0x18005c011  cmp     rbx, rdi
0x18005c014  ja      loc_18005C0B1
0x18005c01a  lea     ebx, [rdi+7]
0x18005c01d  lea     rsi, ??_7CPictureE2oHelper@Art@@6B@; const Art::CPictureE2oHelper::`vftable'
0x18005c024  mov     rax, cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
0x18005c02b  cmp     rax, rdi
0x18005c02e  ja      short loc_18005C0AA
0x18005c030  xor     eax, eax
0x18005c032  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPictureE2oHelper@Art@@@Ofc@@0PEAVCPictureE2oHelper@Art@@EA, rdi; Art::CPictureE2oHelper * Ofc::TSingleton<Art::CPictureE2oHelper>::s_pInstance
  ... truncated ...
```
