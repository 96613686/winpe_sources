# Jot::CJotFrame::XWorkspaceUser::ShowAltTextDialogAsync(MsoCF::IPropertySet &,std::function<void (MsoCF::IPropertySet &)>)

- ea: `0x140111f90`
- end: `0x1401122d7`
- name: `?ShowAltTextDialogAsync@XWorkspaceUser@CJotFrame@Jot@@UEAAXAEAUIPropertySet@MsoCF@@V?$function@$$A6AXAEAUIPropertySet@MsoCF@@@Z@std@@@Z`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140035474`
- `0x140054290`
- `0x140057580`
- `0x1400a90f0`
- `0x1400e69e4`
- `0x1400e6a90`
- `0x140110040`
- `0x1401100f0`
- `0x140111f90`

## import_xrefs

- `onmain!?priImageAltText@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140112076`
- `onmain!?priImageTitle@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140111fe2`
- `onmain!?priInsertTitleString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140112165`
- `onmain!?priInsertTextString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1401121dc`
- `onmain!?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1401120f7`
- `onmain!?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140112129`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140111fec`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140112080`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140112170`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1401121e7`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140111fec`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140112080`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x140112170`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x1401121e7`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140112286`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011229d`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140112286`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011229d`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140111fb4`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140111fb4`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x14011225d`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x14011225d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140111fc8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140112045`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140112239`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140111fc8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140112045`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140112239`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Jot::CJotFrame::XWorkspaceUser::ShowAltTextDialogAsync(
        __int64 a1,
        MsoCF::IPropertySet *a2,
        __int64 a3)
{
  int *v5; // rbx
  __int64 v6; // rax
  int *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rax
  int *v10; // rdi
  __int64 v11; // rsi
  bool v12; // al
  __int64 v13; // rax
  int *v14; // rdi
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rcx
  struct MsoCF::IPropertySet *v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  int v22; // [rsp+40h] [rbp-20h]
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h]
  struct MsoCF::IPropertySet *v25; // [rsp+A8h] [rbp+48h] BYREF

  MsoCF::CreatePropertySet(&v20, 0);
  if ( !v20 )
  {
    CrashWithRecovery(0x1E48C361u, 0);
    __debugbreak();
  }
  v23 = 0;
  v24 = 0;
  MsoCF::IPropertySet::GetProperty(a2, Jot::PropertySpace_Jot14::priImageTitle, (struct MsoCF::CPropertyValue *)&v23);
  v5 = &`MsoCF::String<MsoCF::WzTraits>::TheEmptyString'::`2'::c_empty;
  if ( v24 == 117899322 && v23 )
  {
    v6 = (*(_DWORD *)(v23 + 4) >> 1) & 0x1FFFFFFF;
    v7 = (int *)(v23 + 8);
    if ( v23 != -8 )
    {
      if ( !(_DWORD)v6 || (v8 = v23 + 8 + 2 * v6, _std_find_trivial_2(v23 + 8, v8, 0) == v8) )
      {
        CrashWithRecovery(0x1F46100Du, 0);
        __debugbreak();
      }
    }
  }
  else
  {
    v7 = &`MsoCF::String<MsoCF::WzTraits>::TheEmptyString'::`2'::c_empty;
  }
  v25 = v20;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotMain::prtidInsertTitleString,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v25,
    v7);
  v21 = 0;
  v22 = 0;
  MsoCF::IPropertySet::GetProperty(a2, Jot::PropertySpace_Jot11::priImageAltText, (struct MsoCF::CPropertyValue *)&v21);
  if ( v22 == 117899322 && v21 )
  {
    v9 = (*(_DWORD *)(v21 + 4) >> 1) & 0x1FFFFFFF;
    v10 = (int *)(v21 + 8);
    if ( v21 != -8 )
    {
      if ( !(_DWORD)v9 )
        goto LABEL_33;
      v11 = v21 + 8 + 2 * v9;
      if ( _std_find_trivial_2(v21 + 8, v11, 0) == v11 )
        goto LABEL_33;
    }
  }
  else
  {
    v10 = &`MsoCF::String<MsoCF::WzTraits>::TheEmptyString'::`2'::c_empty;
  }
  v25 = v20;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotMain::prtidInsertTextString,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v25,
    v10);
  LOBYTE(v25) = 0;
  v12 = (*(unsigned __int8 (__fastcall **)(MsoCF::IPropertySet *, _QWORD, struct MsoCF::IPropertySet **))(*(_QWORD *)a2 + 48LL))(
          a2,
          Jot::PropertySpace_JotMain::priFCtrlEnabled,
          &v25)
     && (_BYTE)v25 == 1;
  LOBYTE(v25) = v12;
  (*(void (__fastcall **)(struct MsoCF::IPropertySet *, _QWORD, struct MsoCF::IPropertySet **))(*(_QWORD *)v20 + 56LL))(
    v20,
    Jot::PropertySpace_JotMain::priFCtrlEnabled,
    &v25);
  Jot::CDialogManager::ShowDialog(*((Jot::CDialogManager **)Jot::CJotApp::s_pSingletonJotApp + 64), 0x610u, 0, v20, 0);
  MsoCF::IPropertySet::GetProperty(
    v20,
    Jot::PropertySpace_JotMain::priInsertTitleString,
    (struct MsoCF::CPropertyValue *)&v23);
  if ( v24 != 117899322 || !v23 )
  {
    v14 = &`MsoCF::String<MsoCF::WzTraits>::TheEmptyString'::`2'::c_empty;
    goto LABEL_28;
  }
  v13 = (*(_DWORD *)(v23 + 4) >> 1) & 0x1FFFFFFF;
  v14 = (int *)(v23 + 8);
  if ( v23 != -8 )
  {
    if ( !(_DWORD)v13 || (v15 = v23 + 8 + 2 * v13, _std_find_trivial_2(v23 + 8, v15, 0) == v15) )
    {
LABEL_33:
      CrashWithRecovery(0x1F46100Du, 0);
      __debugbreak();
    }
  }
LABEL_28:
  v25 = v20;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_Jot14::prtidImageTitle,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v25,
    v14);
  MsoCF::IPropertySet::GetProperty(
    v20,
    Jot::PropertySpace_JotMain::priInsertTextString,
    (struct MsoCF::CPropertyValue *)&v21);
  if ( v22 == 117899322 )
  {
    if ( v21 )
    {
      v16 = (*(_DWORD *)(v21 + 4) >> 1) & 0x1FFFFFFF;
      v5 = (int *)(v21 + 8);
      if ( v21 != -8 )
      {
        if ( !(_DWORD)v16 )
          goto LABEL_33;
        v17 = v21 + 8 + 2 * v16;
        if ( _std_find_trivial_2(v21 + 8, v17, 0) == v17 )
          goto LABEL_33;
      }
    }
  }
  v25 = v20;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_Jot11::prtidImageAltText,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v25,
    v5);
  v18 = *(_QWORD *)(a3 + 56);
  if ( !v18 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, struct MsoCF::IPropertySet *))(*(_QWORD *)v18 + 16LL))(v18, v20);
  if ( (v22 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v21);
  if ( (v24 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v23);
  if ( v20 )
    (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v20 + 16LL))(v20);
  return std::_Func_class<void,std::wstring,std::wstring>::~_Func_class<void,std::wstring,std::wstring>(a3);
}

```

## disassembly

```asm
0x140111f90  mov     [rsp-28h+arg_0], rbx
0x140111f95  mov     [rsp-28h+arg_10], r8
0x140111f9a  push    rbp
0x140111f9b  push    rsi
0x140111f9c  push    rdi
0x140111f9d  push    r14
0x140111f9f  push    r15
0x140111fa1  mov     rbp, rsp
0x140111fa4  sub     rsp, 60h
0x140111fa8  mov     r15, r8
0x140111fab  mov     r14, rdx
0x140111fae  xor     edx, edx
0x140111fb0  lea     rcx, [rbp+var_30]
0x140111fb4  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x140111fba  cmp     [rbp+var_30], 0
0x140111fbf  jnz     short loc_140111FCF
0x140111fc1  xor     edx, edx
0x140111fc3  mov     ecx, 1E48C361h
0x140111fc8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140111fce  int     3; Trap to Debugger
0x140111fcf  mov     [rbp+var_18], 0
0x140111fd7  mov     [rbp+var_10], 0
0x140111fde  lea     r8, [rbp+var_18]
0x140111fe2  mov     rdx, cs:__imp_?priImageTitle@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot14::priImageTitle
0x140111fe9  mov     rcx, r14
0x140111fec  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x140111ff2  lea     rbx, ?c_empty@?1??TheEmptyString@?$String@UWzTraits@MsoCF@@@MsoCF@@SA?AV23@XZ@4QB_WB; wchar_t const near * const `MsoCF::String<MsoCF::WzTraits>::TheEmptyString(void)'::`2'::c_empty
0x140111ff9  cmp     [rbp+var_10], 707003Ah
0x140112000  jnz     short loc_14011204C
0x140112002  mov     rcx, [rbp+var_18]
0x140112006  test    rcx, rcx
0x140112009  jz      short loc_14011204C
0x14011200b  mov     eax, [rcx+4]
0x14011200e  shr     eax, 1
0x140112010  and     eax, 1FFFFFFFh
0x140112015  lea     rdi, [rcx+8]
0x140112019  test    rdi, rdi
0x14011201c  jz      short loc_14011204F
0x14011201e  cmp     eax, 1
0x140112021  jb      short loc_14011203E
0x140112023  add     rcx, 8
0x140112027  lea     rsi, [rcx+rax*2]
0x14011202b  xor     r8d, r8d
0x14011202e  mov     rdx, rsi
0x140112031  mov     rcx, rdi
0x140112034  call    __std_find_trivial_2
0x140112039  cmp     rax, rsi
0x14011203c  jnz     short loc_14011204F
0x14011203e  xor     edx, edx
0x140112040  mov     ecx, 1F46100Dh
0x140112045  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x14011204b  int     3; Trap to Debugger
0x14011204c  mov     rdi, rbx
0x14011204f  mov     rax, [rbp+var_30]
0x140112053  mov     [rbp+arg_18], rax
0x140112057  mov     rdx, rdi
0x14011205a  lea     rcx, [rbp+arg_18]
0x14011205e  call    ??4?$CEntry@VprtidInsertTitleString@PropertySpace_JotMain@Jot@@V?$CIPtr@V?$IStringInAtom@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@V12@@MsoCF@@@IPropertySet@MsoCF@@QEAAAEAV012@V?$String@UWzTraits@MsoCF@@@2@@Z; MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotMain::prtidInsertTitleString,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(MsoCF::String<MsoCF::WzTraits>)
0x140112063  mov     [rbp+var_28], 0
0x14011206b  mov     [rbp+var_20], 0
0x140112072  lea     r8, [rbp+var_28]
0x140112076  mov     rdx, cs:__imp_?priImageAltText@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot11::priImageAltText
0x14011207d  mov     rcx, r14
0x140112080  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x140112086  cmp     [rbp+var_20], 707003Ah
0x14011208d  jnz     short loc_1401120D5
0x14011208f  mov     rcx, [rbp+var_28]
0x140112093  test    rcx, rcx
0x140112096  jz      short loc_1401120D5
0x140112098  mov     eax, [rcx+4]
0x14011209b  shr     eax, 1
0x14011209d  and     eax, 1FFFFFFFh
0x1401120a2  lea     rdi, [rcx+8]
0x1401120a6  test    rdi, rdi
0x1401120a9  jz      short loc_1401120D8
0x1401120ab  cmp     eax, 1
0x1401120ae  jb      loc_140112232
0x1401120b4  add     rcx, 8
0x1401120b8  lea     rsi, [rcx+rax*2]
0x1401120bc  xor     r8d, r8d
0x1401120bf  mov     rdx, rsi
0x1401120c2  mov     rcx, rdi
0x1401120c5  call    __std_find_trivial_2
0x1401120ca  cmp     rax, rsi
0x1401120cd  jz      loc_140112232
0x1401120d3  jmp     short loc_1401120D8
0x1401120d5  mov     rdi, rbx
0x1401120d8  mov     rax, [rbp+var_30]
0x1401120dc  mov     [rbp+arg_18], rax
0x1401120e0  mov     rdx, rdi
0x1401120e3  lea     rcx, [rbp+arg_18]
0x1401120e7  call    ??4?$CEntry@VprtidInsertTextString@PropertySpace_JotMain@Jot@@V?$CIPtr@V?$IStringInAtom@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@V12@@MsoCF@@@IPropertySet@MsoCF@@QEAAAEAV012@V?$String@UWzTraits@MsoCF@@@2@@Z; MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotMain::prtidInsertTextString,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(MsoCF::String<MsoCF::WzTraits>)
0x1401120ec  mov     byte ptr [rbp+arg_18], 0
0x1401120f0  mov     rax, [r14]
0x1401120f3  lea     r8, [rbp+arg_18]
0x1401120f7  mov     rdx, cs:__imp_?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priFCtrlEnabled
0x1401120fe  mov     rcx, r14
0x140112101  mov     rax, [rax+30h]
0x140112105  call    cs:__guard_dispatch_icall_fptr
0x14011210b  test    al, al
0x14011210d  jz      short loc_140112119
0x14011210f  cmp     byte ptr [rbp+arg_18], 1
0x140112113  jnz     short loc_140112119
0x140112115  mov     al, 1
0x140112117  jmp     short loc_14011211B
0x140112119  xor     al, al
0x14011211b  mov     byte ptr [rbp+arg_18], al
0x14011211e  mov     rcx, [rbp+var_30]
0x140112122  mov     rax, [rcx]
0x140112125  lea     r8, [rbp+arg_18]
0x140112129  mov     rdx, cs:__imp_?priFCtrlEnabled@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priFCtrlEnabled
0x140112130  mov     rax, [rax+38h]
0x140112134  call    cs:__guard_dispatch_icall_fptr
0x14011213a  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140112141  mov     [rsp+60h+var_40], 0; int
0x140112149  mov     r9, [rbp+var_30]; struct MsoCF::IPropertySet *
0x14011214d  xor     r8d, r8d; HWND
0x140112150  mov     edx, 610h; unsigned int
0x140112155  mov     rcx, [rax+200h]; this
0x14011215c  call    ?ShowDialog@CDialogManager@Jot@@QEAAXIPEAUHWND__@@PEAUIPropertySet@MsoCF@@H@Z; Jot::CDialogManager::ShowDialog(uint,HWND__ *,MsoCF::IPropertySet *,int)
0x140112161  lea     r8, [rbp+var_18]
0x140112165  mov     rdx, cs:__imp_?priInsertTitleString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priInsertTitleString
0x14011216c  mov     rcx, [rbp+var_30]
0x140112170  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x140112176  cmp     [rbp+var_10], 707003Ah
0x14011217d  jnz     short loc_1401121C1
0x14011217f  mov     rcx, [rbp+var_18]
0x140112183  test    rcx, rcx
0x140112186  jz      short loc_1401121C1
0x140112188  mov     eax, [rcx+4]
0x14011218b  shr     eax, 1
0x14011218d  and     eax, 1FFFFFFFh
0x140112192  lea     rdi, [rcx+8]
0x140112196  test    rdi, rdi
0x140112199  jz      short loc_1401121C4
0x14011219b  cmp     eax, 1
0x14011219e  jb      loc_140112232
0x1401121a4  add     rcx, 8
0x1401121a8  lea     rsi, [rcx+rax*2]
0x1401121ac  xor     r8d, r8d
0x1401121af  mov     rdx, rsi
0x1401121b2  mov     rcx, rdi
0x1401121b5  call    __std_find_trivial_2
0x1401121ba  cmp     rax, rsi
0x1401121bd  jz      short loc_140112232
0x1401121bf  jmp     short loc_1401121C4
0x1401121c1  mov     rdi, rbx
0x1401121c4  mov     rax, [rbp+var_30]
0x1401121c8  mov     [rbp+arg_18], rax
0x1401121cc  mov     rdx, rdi
0x1401121cf  lea     rcx, [rbp+arg_18]
0x1401121d3  call    ??4?$CEntry@VprtidImageTitle@PropertySpace_Jot14@Jot@@V?$CIPtr@V?$IStringInAtom@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@V12@@MsoCF@@@IPropertySet@MsoCF@@QEAAAEAV012@V?$String@UWzTraits@MsoCF@@@2@@Z; MsoCF::IPropertySet::CEntry<Jot::PropertySpace_Jot14::prtidImageTitle,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(MsoCF::String<MsoCF::WzTraits>)
0x1401121d8  lea     r8, [rbp+var_28]
0x1401121dc  mov     rdx, cs:__imp_?priInsertTextString@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priInsertTextString
0x1401121e3  mov     rcx, [rbp+var_30]
0x1401121e7  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x1401121ed  cmp     [rbp+var_20], 707003Ah
0x1401121f4  jnz     short loc_140112240
0x1401121f6  mov     rcx, [rbp+var_28]
0x1401121fa  test    rcx, rcx
0x1401121fd  jz      short loc_140112240
0x1401121ff  mov     eax, [rcx+4]
0x140112202  shr     eax, 1
0x140112204  and     eax, 1FFFFFFFh
0x140112209  lea     rbx, [rcx+8]
0x14011220d  test    rbx, rbx
0x140112210  jz      short loc_140112240
0x140112212  cmp     eax, 1
0x140112215  jb      short loc_140112232
0x140112217  add     rcx, 8
0x14011221b  lea     rdi, [rcx+rax*2]
0x14011221f  xor     r8d, r8d
0x140112222  mov     rdx, rdi
0x140112225  mov     rcx, rbx
0x140112228  call    __std_find_trivial_2
0x14011222d  cmp     rax, rdi
0x140112230  jnz     short loc_140112240
0x140112232  xor     edx, edx
0x140112234  mov     ecx, 1F46100Dh
0x140112239  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x14011223f  int     3; Trap to Debugger
0x140112240  mov     rax, [rbp+var_30]
0x140112244  mov     [rbp+arg_18], rax
0x140112248  mov     rdx, rbx
0x14011224b  lea     rcx, [rbp+arg_18]
0x14011224f  call    ??4?$CEntry@VprtidImageAltText@PropertySpace_Jot11@Jot@@V?$CIPtr@V?$IStringInAtom@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@V12@@MsoCF@@@IPropertySet@MsoCF@@QEAAAEAV012@V?$String@UWzTraits@MsoCF@@@2@@Z; MsoCF::IPropertySet::CEntry<Jot::PropertySpace_Jot11::prtidImageAltText,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(MsoCF::String<MsoCF::WzTraits>)
0x140112254  mov     rcx, [r15+38h]
0x140112258  test    rcx, rcx
0x14011225b  jnz     short loc_140112264
0x14011225d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140112263  int     3; Trap to Debugger
0x140112264  mov     rax, [rcx]
0x140112267  mov     rdx, [rbp+var_30]
0x14011226b  mov     rax, [rax+10h]
0x14011226f  call    cs:__guard_dispatch_icall_fptr
0x140112275  nop
0x140112276  mov     edx, [rbp+var_20]
0x140112279  mov     eax, edx
0x14011227b  shr     eax, 19h
0x14011227e  test    al, 1
0x140112280  jz      short loc_14011228D
0x140112282  lea     rcx, [rbp+var_28]
0x140112286  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14011228c  nop
0x14011228d  mov     edx, [rbp+var_10]
0x140112290  mov     eax, edx
0x140112292  shr     eax, 19h
0x140112295  test    al, 1
0x140112297  jz      short loc_1401122A4
0x140112299  lea     rcx, [rbp+var_18]
0x14011229d  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1401122a3  nop
0x1401122a4  mov     rcx, [rbp+var_30]
0x1401122a8  test    rcx, rcx
0x1401122ab  jz      short loc_1401122BB
0x1401122ad  mov     rax, [rcx]
0x1401122b0  mov     rax, [rax+10h]
0x1401122b4  call    cs:__guard_dispatch_icall_fptr
0x1401122ba  nop
0x1401122bb  mov     rcx, r15
0x1401122be  call    ??1?$_Func_class@XV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@XZ; std::_Func_class<void,std::wstring,std::wstring>::~_Func_class<void,std::wstring,std::wstring>(void)
0x1401122c3  mov     rbx, [rsp+60h+arg_0]
0x1401122cb  add     rsp, 60h
0x1401122cf  pop     r15
0x1401122d1  pop     r14
0x1401122d3  pop     rdi
0x1401122d4  pop     rsi
0x1401122d5  pop     rbp
0x1401122d6  retn
```
