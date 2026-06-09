# Jot::CParagraphSpacingOptionsListener::OnListenedEvent(NetUI::Element *,NetUI::Event *)

- ea: `0x14010f100`
- end: `0x14010f3b1`
- name: `?OnListenedEvent@CParagraphSpacingOptionsListener@Jot@@UEAAXPEAVElement@NetUI@@PEAUEvent@4@@Z`
- size: `689`
- prototype: `void __fastcall(Jot::CParagraphSpacingOptionsListener *__hidden this, struct NetUI::Element *, struct NetUI::Event *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140022bd8`
- `0x140057580`
- `0x140074598`
- `0x1400aa238`
- `0x14010f100`

## import_xrefs

- `onmain!?priParagraphSpaceBefore@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14010f1e0`
- `onmain!?priParagraphSpaceAfter@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14010f279`
- `onmain!?priParagraphLineSpacingExact@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14010f312`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f1a1`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f23a`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f2d3`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f1a1`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f23a`
- `onmain!?GetDecimalChar@System@Jot@@YA_WXZ` at `0x14010f2d3`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f1ea`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f283`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f31c`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f1ea`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f283`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010f31c`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f200`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f299`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f332`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f200`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f299`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010f332`
- `mso40uiWin32Client!__imp_?UIDClick@SimpleButton@NetUI@@SAPEAUUID__@2@XZ` at `0x14010f14f`
- `mso40uiWin32Client!__imp_?UIDClick@SimpleButton@NetUI@@SAPEAUUID__@2@XZ` at `0x14010f14f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f21b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f2b4`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f356`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f21b`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f2b4`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010f356`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x14010f3a4`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x14010f3a4`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f1b1`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f24a`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f2e3`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f1b1`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f24a`
- `Mso20Win32Client!__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z` at `0x14010f2e3`

## pseudocode

```c
void __fastcall Jot::CParagraphSpacingOptionsListener::OnListenedEvent(
        Jot::CParagraphSpacingOptionsListener *this,
        struct NetUI::Element *a2,
        struct NetUI::Event *a3)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  struct MsoCF::IPropertySet *v7; // rax
  Jot::System *v8; // rcx
  const wchar_t *TextString; // r14
  MsoCF::IPropertySet *v10; // rbx
  wchar_t v11; // ax
  NetUI::Element *v12; // r14
  struct NetUI::Value *v13; // rcx
  Jot::System *v14; // rcx
  const wchar_t *v15; // r14
  wchar_t v16; // ax
  NetUI::Element *v17; // r14
  struct NetUI::Value *v18; // rcx
  Jot::System *v19; // rcx
  const wchar_t *v20; // r14
  wchar_t v21; // ax
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  int v23; // [rsp+28h] [rbp-18h]
  struct NetUI::Value *v24; // [rsp+70h] [rbp+30h] BYREF
  double v25; // [rsp+78h] [rbp+38h] BYREF

  if ( !a3 )
    return;
  if ( *((_DWORD *)a3 + 7) != 1 )
    return;
  v5 = *((_QWORD *)a3 + 1);
  if ( !v5 )
    return;
  if ( v5 != *((_QWORD *)this + 8) )
    return;
  v6 = *((_QWORD *)a3 + 2);
  if ( v6 != NetUI::SimpleButton::UIDClick(this, a2) )
    return;
  v7 = Jot::CBaseRootElement::UsePropertySet(*((Jot::CBaseRootElement **)this + 9), 1);
  MsoCF::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>(
    &v25,
    v7);
  v24 = 0;
  TextString = NetUI::Element::GetTextString(*((NetUI::Element **)this + 5), &v24);
  v10 = *(MsoCF::IPropertySet **)&v25;
  if ( TextString )
  {
    v25 = 0.0;
    Jot::System::GetDecimalChar(v8);
    if ( (int)MsoParseDoubleWzEx(TextString, v11, &v25) <= 0 )
      goto LABEL_28;
    v22 = COERCE_UNSIGNED_INT(v25);
    v23 = 8716328;
    MsoCF::IPropertySet::SetProperty(
      v10,
      Jot::PropertySpace_Jot14::priParagraphSpaceBefore,
      (const struct MsoCF::CPropertyValue *)&v22);
    if ( (v23 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v22);
  }
  v12 = (NetUI::Element *)*((_QWORD *)this + 6);
  v13 = v24;
  if ( v24 )
  {
    v24 = 0;
    NetUI::BaseValue::Release(v13);
  }
  v15 = NetUI::Element::GetTextString(v12, &v24);
  if ( v15 )
  {
    v25 = 0.0;
    Jot::System::GetDecimalChar(v14);
    if ( (int)MsoParseDoubleWzEx(v15, v16, &v25) <= 0 )
      goto LABEL_28;
    v22 = COERCE_UNSIGNED_INT(v25);
    v23 = 8716328;
    MsoCF::IPropertySet::SetProperty(
      v10,
      Jot::PropertySpace_Jot14::priParagraphSpaceAfter,
      (const struct MsoCF::CPropertyValue *)&v22);
    if ( (v23 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v22);
  }
  v17 = (NetUI::Element *)*((_QWORD *)this + 7);
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    NetUI::BaseValue::Release(v18);
  }
  v20 = NetUI::Element::GetTextString(v17, &v24);
  if ( !v20 )
    goto LABEL_22;
  v25 = 0.0;
  Jot::System::GetDecimalChar(v19);
  if ( (int)MsoParseDoubleWzEx(v20, v21, &v25) <= 0 )
  {
LABEL_28:
    MsoAlertIds(*((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62), 27947213, 48, 0);
    *((_BYTE *)a3 + 24) = 1;
    goto LABEL_23;
  }
  v22 = COERCE_UNSIGNED_INT(v25);
  v23 = 8716328;
  MsoCF::IPropertySet::SetProperty(
    v10,
    Jot::PropertySpace_Jot14::priParagraphLineSpacingExact,
    (const struct MsoCF::CPropertyValue *)&v22);
  if ( (v23 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v22);
LABEL_22:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  *((_BYTE *)a3 + 24) |= 1u;
LABEL_23:
  if ( v24 )
    NetUI::BaseValue::Release(v24);
  if ( v10 )
    (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v10 + 16LL))(v10);
}

```

## disassembly

```asm
0x14010f100  test    r8, r8
0x14010f103  jz      locret_14010F389
0x14010f109  mov     [rsp-18h+arg_0], rbx
0x14010f10e  mov     [rsp-18h+arg_8], rsi
0x14010f113  push    rbp
0x14010f114  push    rdi
0x14010f115  push    r14
0x14010f117  mov     rbp, rsp
0x14010f11a  sub     rsp, 40h
0x14010f11e  movaps  [rsp+40h+var_10], xmm6
0x14010f123  mov     rdi, r8
0x14010f126  mov     rsi, rcx
0x14010f129  cmp     dword ptr [r8+1Ch], 1
0x14010f12e  jnz     loc_14010F372
0x14010f134  mov     rax, [r8+8]
0x14010f138  test    rax, rax
0x14010f13b  jz      loc_14010F372
0x14010f141  cmp     rax, [rcx+40h]
0x14010f145  jnz     loc_14010F372
0x14010f14b  mov     rbx, [r8+10h]
0x14010f14f  call    cs:__imp_?UIDClick@SimpleButton@NetUI@@SAPEAUUID__@2@XZ; NetUI::SimpleButton::UIDClick(void)
0x14010f155  cmp     rbx, rax
0x14010f158  jnz     loc_14010F372
0x14010f15e  mov     edx, 1; int
0x14010f163  mov     rcx, [rsi+48h]; this
0x14010f167  call    ?UsePropertySet@CBaseRootElement@Jot@@QEAAPEAUIPropertySet@MsoCF@@H@Z; Jot::CBaseRootElement::UsePropertySet(int)
0x14010f16c  mov     rdx, rax
0x14010f16f  lea     rcx, [rbp+arg_18]
0x14010f173  call    ??0?$CIPtr@VCHiddenChunkControlUser@Jot@@V12@@MsoCF@@QEAA@PEAVCHiddenChunkControlUser@Jot@@@Z; MsoCF::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>(Jot::CHiddenChunkControlUser *)
0x14010f178  mov     [rbp+arg_10], 0
0x14010f180  lea     rdx, [rbp+arg_10]; struct NetUI::Value **
0x14010f184  mov     rcx, [rsi+28h]; this
0x14010f188  call    ?GetTextString@Element@NetUI@@QEBAPEB_WPEAPEAVValue@2@@Z; NetUI::Element::GetTextString(NetUI::Value * *)
0x14010f18d  mov     r14, rax
0x14010f190  mov     rbx, [rbp+arg_18]
0x14010f194  xorps   xmm6, xmm6
0x14010f197  test    rax, rax
0x14010f19a  jz      short loc_14010F206
0x14010f19c  movsd   [rbp+arg_18], xmm6
0x14010f1a1  call    cs:__imp_?GetDecimalChar@System@Jot@@YA_WXZ; Jot::System::GetDecimalChar(void)
0x14010f1a7  movzx   edx, ax
0x14010f1aa  lea     r8, [rbp+arg_18]
0x14010f1ae  mov     rcx, r14
0x14010f1b1  call    cs:__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z; MsoParseDoubleWzEx(wchar_t const *,wchar_t,double *)
0x14010f1b7  test    eax, eax
0x14010f1b9  jle     loc_14010F38A
0x14010f1bf  movsd   xmm0, [rbp+arg_18]
0x14010f1c4  cvtpd2ps xmm0, xmm0
0x14010f1c8  mov     [rbp+var_20], 0
0x14010f1d0  movss   dword ptr [rbp+var_20], xmm0
0x14010f1d5  mov     [rbp+var_18], 850028h
0x14010f1dc  lea     r8, [rbp+var_20]
0x14010f1e0  mov     rdx, cs:__imp_?priParagraphSpaceBefore@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot14::priParagraphSpaceBefore
0x14010f1e7  mov     rcx, rbx
0x14010f1ea  call    cs:__imp_?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z; MsoCF::IPropertySet::SetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue const &)
0x14010f1f0  mov     edx, [rbp+var_18]
0x14010f1f3  mov     eax, edx
0x14010f1f5  shr     eax, 19h
0x14010f1f8  test    al, 1
0x14010f1fa  jz      short loc_14010F206
0x14010f1fc  lea     rcx, [rbp+var_20]
0x14010f200  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010f206  mov     r14, [rsi+30h]
0x14010f20a  mov     rcx, [rbp+arg_10]
0x14010f20e  test    rcx, rcx
0x14010f211  jz      short loc_14010F221
0x14010f213  mov     [rbp+arg_10], 0
0x14010f21b  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14010f221  lea     rdx, [rbp+arg_10]; struct NetUI::Value **
0x14010f225  mov     rcx, r14; this
0x14010f228  call    ?GetTextString@Element@NetUI@@QEBAPEB_WPEAPEAVValue@2@@Z; NetUI::Element::GetTextString(NetUI::Value * *)
0x14010f22d  mov     r14, rax
0x14010f230  test    rax, rax
0x14010f233  jz      short loc_14010F29F
0x14010f235  movsd   [rbp+arg_18], xmm6
0x14010f23a  call    cs:__imp_?GetDecimalChar@System@Jot@@YA_WXZ; Jot::System::GetDecimalChar(void)
0x14010f240  movzx   edx, ax
0x14010f243  lea     r8, [rbp+arg_18]
0x14010f247  mov     rcx, r14
0x14010f24a  call    cs:__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z; MsoParseDoubleWzEx(wchar_t const *,wchar_t,double *)
0x14010f250  test    eax, eax
0x14010f252  jle     loc_14010F38A
0x14010f258  movsd   xmm0, [rbp+arg_18]
0x14010f25d  cvtpd2ps xmm0, xmm0
0x14010f261  mov     [rbp+var_20], 0
0x14010f269  movss   dword ptr [rbp+var_20], xmm0
0x14010f26e  mov     [rbp+var_18], 850028h
0x14010f275  lea     r8, [rbp+var_20]
0x14010f279  mov     rdx, cs:__imp_?priParagraphSpaceAfter@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot14::priParagraphSpaceAfter
0x14010f280  mov     rcx, rbx
0x14010f283  call    cs:__imp_?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z; MsoCF::IPropertySet::SetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue const &)
0x14010f289  mov     edx, [rbp+var_18]
0x14010f28c  mov     eax, edx
0x14010f28e  shr     eax, 19h
0x14010f291  test    al, 1
0x14010f293  jz      short loc_14010F29F
0x14010f295  lea     rcx, [rbp+var_20]
0x14010f299  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010f29f  mov     r14, [rsi+38h]
0x14010f2a3  mov     rcx, [rbp+arg_10]
0x14010f2a7  test    rcx, rcx
0x14010f2aa  jz      short loc_14010F2BA
0x14010f2ac  mov     [rbp+arg_10], 0
0x14010f2b4  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14010f2ba  lea     rdx, [rbp+arg_10]; struct NetUI::Value **
0x14010f2be  mov     rcx, r14; this
0x14010f2c1  call    ?GetTextString@Element@NetUI@@QEBAPEB_WPEAPEAVValue@2@@Z; NetUI::Element::GetTextString(NetUI::Value * *)
0x14010f2c6  mov     r14, rax
0x14010f2c9  test    rax, rax
0x14010f2cc  jz      short loc_14010F338
0x14010f2ce  movsd   [rbp+arg_18], xmm6
0x14010f2d3  call    cs:__imp_?GetDecimalChar@System@Jot@@YA_WXZ; Jot::System::GetDecimalChar(void)
0x14010f2d9  movzx   edx, ax
0x14010f2dc  lea     r8, [rbp+arg_18]
0x14010f2e0  mov     rcx, r14
0x14010f2e3  call    cs:__imp_?MsoParseDoubleWzEx@@YAHPEB_W_WPEAN@Z; MsoParseDoubleWzEx(wchar_t const *,wchar_t,double *)
0x14010f2e9  test    eax, eax
0x14010f2eb  jle     loc_14010F38A
0x14010f2f1  movsd   xmm0, [rbp+arg_18]
0x14010f2f6  cvtpd2ps xmm0, xmm0
0x14010f2fa  mov     [rbp+var_20], 0
0x14010f302  movss   dword ptr [rbp+var_20], xmm0
0x14010f307  mov     [rbp+var_18], 850028h
0x14010f30e  lea     r8, [rbp+var_20]
0x14010f312  mov     rdx, cs:__imp_?priParagraphLineSpacingExact@PropertySpace_Jot14@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot14::priParagraphLineSpacingExact
0x14010f319  mov     rcx, rbx
0x14010f31c  call    cs:__imp_?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z; MsoCF::IPropertySet::SetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue const &)
0x14010f322  mov     edx, [rbp+var_18]
0x14010f325  mov     eax, edx
0x14010f327  shr     eax, 19h
0x14010f32a  test    al, 1
0x14010f32c  jz      short loc_14010F338
0x14010f32e  lea     rcx, [rbp+var_20]
0x14010f332  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010f338  mov     rcx, [rsi+48h]
0x14010f33c  mov     rax, [rcx]
0x14010f33f  mov     rax, [rax+8]
0x14010f343  call    cs:__guard_dispatch_icall_fptr
0x14010f349  or      byte ptr [rdi+18h], 1
0x14010f34d  mov     rcx, [rbp+arg_10]
0x14010f351  test    rcx, rcx
0x14010f354  jz      short loc_14010F35C
0x14010f356  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14010f35c  test    rbx, rbx
0x14010f35f  jz      short loc_14010F372
0x14010f361  mov     rax, [rbx]
0x14010f364  mov     rcx, rbx
0x14010f367  mov     rax, [rax+10h]
0x14010f36b  call    cs:__guard_dispatch_icall_fptr
0x14010f371  nop
0x14010f372  mov     rbx, [rsp+40h+arg_0]
0x14010f377  mov     rsi, [rsp+40h+arg_8]
0x14010f37c  movaps  xmm6, [rsp+40h+var_10]
0x14010f381  add     rsp, 40h
0x14010f385  pop     r14
0x14010f387  pop     rdi
0x14010f388  pop     rbp
0x14010f389  retn
0x14010f38a  xor     r9d, r9d
0x14010f38d  mov     edx, 1AA70CDh
0x14010f392  lea     r8d, [r9+30h]
0x14010f396  mov     rcx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14010f39d  mov     rcx, [rcx+1F0h]
0x14010f3a4  call    cs:__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z; MsoAlertIds(HINSTANCE__ *,int,int,HWND__ *)
0x14010f3aa  mov     byte ptr [rdi+18h], 1
0x14010f3ae  jmp     short loc_14010F34D
```
