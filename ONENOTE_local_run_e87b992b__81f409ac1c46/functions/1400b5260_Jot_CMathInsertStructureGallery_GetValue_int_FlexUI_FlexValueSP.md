# Jot::CMathInsertStructureGallery::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x1400b5260`
- end: `0x1400b5635`
- name: `?GetValue@CMathInsertStructureGallery@Jot@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `981`
- prototype: `bool __fastcall(Jot::CMathInsertStructureGallery *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14003f250`
- `0x140048a58`
- `0x140052c10`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x140083028`
- `0x14008ae50`
- `0x14008ff70`
- `0x1400b5260`

## import_xrefs

- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x1400b53fc`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x1400b53fc`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b5528`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b55b9`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b5528`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1400b55b9`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400b54f6`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400b54f6`
- `onmain!?priTcid@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1400b53a6`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400b52d7`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1400b52d7`
- `Mso98Win32Client!__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z` at `0x1400b52a2`
- `Mso98Win32Client!__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z` at `0x1400b52a2`
- `mso40uiWin32Client!__imp_?IsNull@FlexValue@FlexUI@@SA_NPEBV12@@Z` at `0x1400b535a`
- `mso40uiWin32Client!__imp_?IsNull@FlexValue@FlexUI@@SA_NPEBV12@@Z` at `0x1400b535a`
- `mso40uiWin32Client!__imp_?MsoFGetTbShowKbdShortcuts@@YAHXZ` at `0x1400b52ca`
- `mso40uiWin32Client!__imp_?MsoFGetTbShowKbdShortcuts@@YAHXZ` at `0x1400b52ca`
- `mso40uiWin32Client!__imp_?IsUnset@FlexValue@FlexUI@@SA_NPEBV12@@Z` at `0x1400b5349`
- `mso40uiWin32Client!__imp_?IsUnset@FlexValue@FlexUI@@SA_NPEBV12@@Z` at `0x1400b5349`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b5578`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b560e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b5578`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1400b560e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400b5502`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1400b5502`
- `mso40uiWin32Client!__imp_?GetString@FlexValue@FlexUI@@QEBAPEB_WXZ` at `0x1400b54b9`
- `mso40uiWin32Client!__imp_?GetString@FlexValue@FlexUI@@QEBAPEB_WXZ` at `0x1400b54b9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b54af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b55a4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b54af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400b55a4`

## pseudocode

```c
bool __fastcall Jot::CMathInsertStructureGallery::GetValue(
        Jot::CMathInsertStructureGallery *this,
        int a2,
        struct FlexUI::FlexValueSP *a3)
{
  struct GalleryDSSP *GalleryDataSource; // rbx
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // r9
  __int64 v9; // rcx
  const struct FlexUI::FlexValue *v10; // rax
  NetUI::BaseValue *v11; // rsi
  struct MsoCF::IPropertySet *v12; // rbx
  unsigned int v13; // edx
  const struct MsoCF::PropertyInfo *v14; // rdi
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rdi
  const wchar_t *v18; // rax
  bool v19; // di
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  struct MsoCF::IActionContext *v21; // [rsp+38h] [rbp-C8h] BYREF
  struct MsoCF::IPropertySet *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h]
  const wchar_t *String; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h]
  _BYTE v28[368]; // [rsp+70h] [rbp-90h] BYREF

  if ( a2 != 6 || !MsoFGetTbShowKbdShortcuts() )
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  GalleryDataSource = CMsoGalleryUserDefault::GetGalleryDataSource(this);
  GalleryDSSP::CheckPtrs(GalleryDataSource);
  v8 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)GalleryDataSource + 1);
  v9 = 0;
  v20 = 0;
  if ( !v8 )
  {
LABEL_41:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  }
  (**v8)(v8, &GUID_000c0134_0000_0000_c000_000000000046, &v20);
  if ( !v20 )
    return OfficeSpace::DataSourceBase::GetValue(this, a2, a3);
  v10 = (const struct FlexUI::FlexValue *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 248LL))(v20, 6);
  v11 = v10;
  if ( !v10 || FlexUI::FlexValue::IsUnset(v10) || FlexUI::FlexValue::IsNull(v11) )
  {
LABEL_38:
    if ( v11 )
      NetUI::BaseValue::Release(v11);
    v9 = v20;
    goto LABEL_41;
  }
  v22 = 0;
  v27 = 0;
  v26 = 196734;
  MsoCF::CActionPropertySet::EnsurePropertySet((MsoCF::CActionPropertySet *)&v26, &v22);
  LODWORD(String) = 15365;
  v12 = v22;
  (*(void (__fastcall **)(struct MsoCF::IPropertySet *, _QWORD, const wchar_t **))(*(_QWORD *)v22 + 56LL))(
    v22,
    Jot::PropertySpace_JotMain::priTcid,
    &String);
  v21 = 0;
  (*(void (__fastcall **)(_QWORD, struct MsoCF::IActionContext **))(**(_QWORD **)(*((_QWORD *)this + 34) + 104LL) + 80LL))(
    *(_QWORD *)(*((_QWORD *)this + 34) + 104LL),
    &v21);
  if ( !MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v26, v21) )
  {
LABEL_33:
    if ( v21 )
      (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_38;
  }
  v14 = MsoCF::LookupProperty((MsoCF *)0x1C001004, v13);
  v23 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(struct MsoCF::IPropertySet *, const struct MsoCF::PropertyInfo *, __int64 *))(*(_QWORD *)v12 + 48LL))(
         v12,
         v14,
         &v23) )
  {
    v15 = *((_DWORD *)v14 + 1);
  }
  else
  {
    v15 = 0;
  }
  v24 = v15;
  if ( v15 != 117899322 || !v23 )
  {
    if ( (v15 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v23);
    goto LABEL_33;
  }
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v28);
  if ( v24 != 117899322 || !v23 )
  {
    CrashWithRecovery(0x65756F6Eu, 0);
    __debugbreak();
  }
  v16 = (*(_DWORD *)(v23 + 4) >> 1) & 0x1FFFFFFF;
  v22 = (struct MsoCF::IPropertySet *)(v23 + 8);
  if ( v23 != -8 )
  {
    if ( !(_DWORD)v16 || (v17 = v23 + 8 + 2 * v16, _std_find_trivial_2(v23 + 8, v17, 0) == v17) )
    {
      CrashWithRecovery(0x1F46100Du, 0);
      __debugbreak();
    }
  }
  String = FlexUI::FlexValue::GetString(v11);
  Jot::CWzInBuffer::SetFromPattern<wchar_t const *,MsoCF::String<MsoCF::WzTraits>>(
    (unsigned int)v28,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    2032114967,
    (unsigned int)&String,
    (__int64)&v22);
  v18 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v28);
  v19 = FlexUI::FlexValue::CreateString(v18, a3);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v28);
  if ( (v24 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v23);
  if ( v21 )
    (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v27 = 0;
  (*(void (__fastcall **)(struct MsoCF::IPropertySet *))(*(_QWORD *)v12 + 16LL))(v12);
  NetUI::BaseValue::Release(v11);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return v19;
}

```

## disassembly

```asm
0x1400b5260  push    rbp
0x1400b5262  push    rbx
0x1400b5263  push    rsi
0x1400b5264  push    rdi
0x1400b5265  push    r12
0x1400b5267  push    r14
0x1400b5269  push    r15
0x1400b526b  lea     rbp, [rsp-0F0h]
0x1400b5273  sub     rsp, 1F0h
0x1400b527a  mov     rax, cs:__security_cookie
0x1400b5281  xor     rax, rsp
0x1400b5284  mov     [rbp+120h+var_40], rax
0x1400b528b  mov     r12, r8
0x1400b528e  mov     r15d, edx
0x1400b5291  mov     r14, rcx
0x1400b5294  cmp     edx, 6
0x1400b5297  jz      short loc_1400B52CA
0x1400b5299  mov     r8, r12
0x1400b529c  mov     edx, r15d
0x1400b529f  mov     rcx, r14
0x1400b52a2  call    cs:__imp_?GetValue@DataSourceBase@OfficeSpace@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; OfficeSpace::DataSourceBase::GetValue(int,FlexUI::FlexValueSP &)
0x1400b52a8  nop
0x1400b52a9  mov     rcx, [rbp+120h+var_40]
0x1400b52b0  xor     rcx, rsp; StackCookie
0x1400b52b3  call    __security_check_cookie
0x1400b52b8  add     rsp, 1F0h
0x1400b52bf  pop     r15
0x1400b52c1  pop     r14
0x1400b52c3  pop     r12
0x1400b52c5  pop     rdi
0x1400b52c6  pop     rsi
0x1400b52c7  pop     rbx
0x1400b52c8  pop     rbp
0x1400b52c9  retn
0x1400b52ca  call    cs:__imp_?MsoFGetTbShowKbdShortcuts@@YAHXZ; MsoFGetTbShowKbdShortcuts(void)
0x1400b52d0  test    eax, eax
0x1400b52d2  jz      short loc_1400B5299
0x1400b52d4  mov     rcx, r14
0x1400b52d7  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1400b52dd  mov     rbx, rax
0x1400b52e0  mov     rcx, rax; this
0x1400b52e3  call    ?CheckPtrs@GalleryDSSP@@AEBA_NXZ; GalleryDSSP::CheckPtrs(void)
0x1400b52e8  mov     r9, [rbx+8]
0x1400b52ec  xor     ecx, ecx
0x1400b52ee  mov     [rsp+220h+var_1F0], rcx
0x1400b52f3  test    r9, r9
0x1400b52f6  jz      loc_1400B5619
0x1400b52fc  mov     rax, [r9]
0x1400b52ff  lea     r8, [rsp+220h+var_1F0]
0x1400b5304  lea     rdx, _GUID_000c0134_0000_0000_c000_000000000046
0x1400b530b  mov     rcx, r9
0x1400b530e  mov     rax, [rax]
0x1400b5311  call    cs:__guard_dispatch_icall_fptr
0x1400b5317  mov     rcx, [rsp+220h+var_1F0]
0x1400b531c  test    rcx, rcx
0x1400b531f  jz      loc_1400B5299
0x1400b5325  mov     rax, [rcx]
0x1400b5328  mov     edx, 6
0x1400b532d  mov     rax, [rax+0F8h]
0x1400b5334  call    cs:__guard_dispatch_icall_fptr
0x1400b533a  mov     rsi, rax
0x1400b533d  test    rax, rax
0x1400b5340  jz      loc_1400B5606
0x1400b5346  mov     rcx, rax
0x1400b5349  call    cs:__imp_?IsUnset@FlexValue@FlexUI@@SA_NPEBV12@@Z; FlexUI::FlexValue::IsUnset(FlexUI::FlexValue const *)
0x1400b534f  test    al, al
0x1400b5351  jnz     loc_1400B5606
0x1400b5357  mov     rcx, rsi
0x1400b535a  call    cs:__imp_?IsNull@FlexValue@FlexUI@@SA_NPEBV12@@Z; FlexUI::FlexValue::IsNull(FlexUI::FlexValue const *)
0x1400b5360  test    al, al
0x1400b5362  jnz     loc_1400B5606
0x1400b5368  mov     [rsp+220h+var_1E0], 0
0x1400b5371  mov     [rsp+220h+var_1B8], 0
0x1400b537a  mov     [rsp+220h+var_1C0], 3007Eh
0x1400b5382  lea     rdx, [rsp+220h+var_1E0]; struct MsoCF::IPropertySet **
0x1400b5387  lea     rcx, [rsp+220h+var_1C0]; this
0x1400b538c  call    ?EnsurePropertySet@CActionPropertySet@MsoCF@@QEAAXPEAPEAUIPropertySet@2@@Z; MsoCF::CActionPropertySet::EnsurePropertySet(MsoCF::IPropertySet * *)
0x1400b5391  mov     dword ptr [rsp+220h+var_1C8], 3C05h
0x1400b5399  mov     rbx, [rsp+220h+var_1E0]
0x1400b539e  mov     rax, [rbx]
0x1400b53a1  lea     r8, [rsp+220h+var_1C8]
0x1400b53a6  mov     rdx, cs:__imp_?priTcid@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priTcid
0x1400b53ad  mov     rcx, rbx
0x1400b53b0  mov     rax, [rax+38h]
0x1400b53b4  call    cs:__guard_dispatch_icall_fptr
0x1400b53ba  mov     [rsp+220h+var_1E8], 0
0x1400b53c3  mov     rax, [r14+110h]
0x1400b53ca  mov     rcx, [rax+68h]
0x1400b53ce  mov     rax, [rcx]
0x1400b53d1  lea     rdx, [rsp+220h+var_1E8]
0x1400b53d6  mov     rax, [rax+50h]
0x1400b53da  call    cs:__guard_dispatch_icall_fptr
0x1400b53e0  mov     rdx, [rsp+220h+var_1E8]; struct MsoCF::IActionContext *
0x1400b53e5  lea     rcx, [rsp+220h+var_1C0]; this
0x1400b53ea  call    ?Execute@CActionPropertySet@MsoCF@@QEAA_NPEAUIActionContext@2@@Z; MsoCF::CActionPropertySet::Execute(MsoCF::IActionContext *)
0x1400b53ef  test    al, al
0x1400b53f1  jz      loc_1400B55BF
0x1400b53f7  mov     ecx, 1C001004h
0x1400b53fc  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x1400b5402  mov     rdi, rax
0x1400b5405  mov     [rsp+220h+var_1D8], 0
0x1400b540e  mov     rcx, [rbx]
0x1400b5411  mov     rax, [rcx+30h]
0x1400b5415  lea     r8, [rsp+220h+var_1D8]
0x1400b541a  mov     rdx, rdi
0x1400b541d  mov     rcx, rbx
0x1400b5420  call    cs:__guard_dispatch_icall_fptr
0x1400b5426  test    al, al
0x1400b5428  jz      short loc_1400B542F
0x1400b542a  mov     edx, [rdi+4]
0x1400b542d  jmp     short loc_1400B5431
0x1400b542f  xor     edx, edx
0x1400b5431  mov     [rsp+220h+var_1D0], edx
0x1400b5435  mov     edi, 707003Ah
0x1400b543a  cmp     edx, edi
0x1400b543c  jnz     loc_1400B55AB
0x1400b5442  cmp     [rsp+220h+var_1D8], 0
0x1400b5448  jz      loc_1400B55AB
0x1400b544e  lea     rcx, [rsp+220h+var_1B0]
0x1400b5453  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x1400b5458  cmp     [rsp+220h+var_1D0], edi
0x1400b545c  jnz     loc_1400B559D
0x1400b5462  mov     rcx, [rsp+220h+var_1D8]
0x1400b5467  test    rcx, rcx
0x1400b546a  jz      loc_1400B559D
0x1400b5470  mov     eax, [rcx+4]
0x1400b5473  shr     eax, 1
0x1400b5475  and     eax, 1FFFFFFFh
0x1400b547a  lea     r9, [rcx+8]
0x1400b547e  mov     [rsp+220h+var_1E0], r9
0x1400b5483  test    r9, r9
0x1400b5486  jz      short loc_1400B54B6
0x1400b5488  cmp     eax, 1
0x1400b548b  jb      short loc_1400B54A8
0x1400b548d  add     rcx, 8
0x1400b5491  lea     rdi, [rcx+rax*2]
0x1400b5495  xor     r8d, r8d
0x1400b5498  mov     rdx, rdi
0x1400b549b  mov     rcx, r9
0x1400b549e  call    __std_find_trivial_2
0x1400b54a3  cmp     rax, rdi
0x1400b54a6  jnz     short loc_1400B54B6
0x1400b54a8  xor     edx, edx
0x1400b54aa  mov     ecx, 1F46100Dh
0x1400b54af  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400b54b5  int     3; Trap to Debugger
0x1400b54b6  mov     rcx, rsi
0x1400b54b9  call    cs:__imp_?GetString@FlexValue@FlexUI@@QEBAPEB_WXZ; FlexUI::FlexValue::GetString(void)
0x1400b54bf  mov     [rsp+220h+var_1C8], rax
0x1400b54c4  lea     rax, [rsp+220h+var_1E0]
0x1400b54c9  mov     [rsp+220h+var_200], rax
0x1400b54ce  lea     r9, [rsp+220h+var_1C8]
0x1400b54d3  mov     r8d, 791F9D17h
0x1400b54d9  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400b54e0  mov     rdx, [rdx+1F0h]
0x1400b54e7  lea     rcx, [rsp+220h+var_1B0]
0x1400b54ec  call    ??$SetFromPattern@PEB_WV?$String@UWzTraits@MsoCF@@@MsoCF@@@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@IAEBQEB_WAEBV?$String@UWzTraits@MsoCF@@@MsoCF@@@Z; Jot::CWzInBuffer::SetFromPattern<wchar_t const *,MsoCF::String<MsoCF::WzTraits>>(HINSTANCE__ *,uint,wchar_t const * const &,MsoCF::String<MsoCF::WzTraits> const &)
0x1400b54f1  lea     rcx, [rsp+220h+var_1B0]
0x1400b54f6  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400b54fc  mov     rcx, rax
0x1400b54ff  mov     rdx, r12
0x1400b5502  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1400b5508  mov     dil, al
0x1400b550b  lea     rcx, [rsp+220h+var_1B0]
0x1400b5510  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400b5515  mov     edx, [rsp+220h+var_1D0]
0x1400b5519  mov     ecx, edx
0x1400b551b  shr     ecx, 19h
0x1400b551e  test    cl, 1
0x1400b5521  jz      short loc_1400B552E
0x1400b5523  lea     rcx, [rsp+220h+var_1D8]
0x1400b5528  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400b552e  mov     rcx, [rsp+220h+var_1E8]
0x1400b5533  test    rcx, rcx
0x1400b5536  jz      short loc_1400B5545
0x1400b5538  mov     rax, [rcx]
0x1400b553b  mov     rax, [rax+10h]
0x1400b553f  call    cs:__guard_dispatch_icall_fptr
0x1400b5545  mov     rcx, [rsp+220h+var_1B8]
0x1400b554a  test    rcx, rcx
0x1400b554d  jz      short loc_1400B555C
0x1400b554f  mov     rax, [rcx]
0x1400b5552  mov     rax, [rax+10h]
0x1400b5556  call    cs:__guard_dispatch_icall_fptr
0x1400b555c  mov     [rsp+220h+var_1B8], 0
0x1400b5565  mov     rax, [rbx]
0x1400b5568  mov     rcx, rbx
0x1400b556b  mov     rax, [rax+10h]
0x1400b556f  call    cs:__guard_dispatch_icall_fptr
0x1400b5575  mov     rcx, rsi
0x1400b5578  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1400b557e  mov     rcx, [rsp+220h+var_1F0]
0x1400b5583  test    rcx, rcx
0x1400b5586  jz      short loc_1400B5595
0x1400b5588  mov     rax, [rcx]
0x1400b558b  mov     rax, [rax+10h]
0x1400b558f  call    cs:__guard_dispatch_icall_fptr
0x1400b5595  mov     al, dil
0x1400b5598  jmp     loc_1400B52A9
0x1400b559d  xor     edx, edx
0x1400b559f  mov     ecx, 65756F6Eh
0x1400b55a4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400b55aa  int     3; Trap to Debugger
0x1400b55ab  mov     eax, edx
0x1400b55ad  shr     eax, 19h
0x1400b55b0  test    al, 1
0x1400b55b2  jz      short loc_1400B55BF
0x1400b55b4  lea     rcx, [rsp+220h+var_1D8]
0x1400b55b9  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1400b55bf  mov     rcx, [rsp+220h+var_1E8]
0x1400b55c4  test    rcx, rcx
0x1400b55c7  jz      short loc_1400B55D6
0x1400b55c9  mov     rax, [rcx]
0x1400b55cc  mov     rax, [rax+10h]
0x1400b55d0  call    cs:__guard_dispatch_icall_fptr
0x1400b55d6  mov     rcx, [rsp+220h+var_1B8]
0x1400b55db  test    rcx, rcx
0x1400b55de  jz      short loc_1400B55ED
0x1400b55e0  mov     rax, [rcx]
0x1400b55e3  mov     rax, [rax+10h]
0x1400b55e7  call    cs:__guard_dispatch_icall_fptr
0x1400b55ed  mov     [rsp+220h+var_1B8], 0
0x1400b55f6  mov     rax, [rbx]
0x1400b55f9  mov     rcx, rbx
0x1400b55fc  mov     rax, [rax+10h]
0x1400b5600  call    cs:__guard_dispatch_icall_fptr
0x1400b5606  test    rsi, rsi
0x1400b5609  jz      short loc_1400B5614
0x1400b560b  mov     rcx, rsi
0x1400b560e  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1400b5614  mov     rcx, [rsp+220h+var_1F0]
0x1400b5619  test    rcx, rcx
0x1400b561c  jz      loc_1400B5299
0x1400b5622  mov     rax, [rcx]
0x1400b5625  mov     rax, [rax+10h]
0x1400b5629  call    cs:__guard_dispatch_icall_fptr
0x1400b562f  jmp     loc_1400B5299
```
