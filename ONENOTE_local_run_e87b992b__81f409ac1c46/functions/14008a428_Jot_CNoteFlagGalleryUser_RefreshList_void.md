# Jot::CNoteFlagGalleryUser::RefreshList(void)

- ea: `0x14008a428`
- end: `0x14008a8a1`
- name: `?RefreshList@CNoteFlagGalleryUser@Jot@@AEAA_NXZ`
- size: `1145`
- prototype: `bool __fastcall(Jot::CNoteFlagGalleryUser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14008a400`

## callees

- `0x14003f250`
- `0x1400488d0`
- `0x140048a58`
- `0x140056ac0`
- `0x140057580`
- `0x140089de4`
- `0x14008a428`
- `0x14008aafc`
- `0x14008ae2c`

## import_xrefs

- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14008a486`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x14008a486`
- `onmain!?priNoteTagLabelList@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14008a54a`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14008a556`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14008a556`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a657`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a752`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a83f`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a657`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a752`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14008a83f`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14008a49c`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14008a49c`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x14008a4b9`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x14008a56c`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x14008a4b9`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x14008a56c`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008a50c`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008a75f`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008a50c`
- `onmain!?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ` at `0x14008a75f`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x14008a48f`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x14008a48f`
- `Mso98Win32Client!__imp_?SetLoadingImage@GalleryItemSP@@QEAA_NHH_N@Z` at `0x14008a5f5`
- `Mso98Win32Client!__imp_?SetLoadingImage@GalleryItemSP@@QEAA_NHH_N@Z` at `0x14008a5f5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14008a6b7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14008a7e7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14008a6b7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14008a7e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Jot::CNoteFlagGalleryUser::RefreshList(struct OfficeSpace::IOfficeSpace **this)
{
  GalleryDSSP *GalleryDataSource; // rbx
  const wchar_t *v3; // rax
  struct FlexUI::FlexValue *v4; // r9
  MsoCF *v5; // rcx
  __int64 v6; // rbx
  struct MsoCF::IActionManager *v7; // rax
  MsoCF *v8; // rcx
  __int64 v9; // r15
  unsigned int v10; // esi
  __int64 v11; // rdi
  __int64 v12; // rbx
  Jot *v13; // rcx
  bool IsFluentRefresh; // al
  int v15; // r8d
  unsigned __int64 v16; // rdx
  unsigned __int64 v18; // rdx
  __int64 v19; // rbx
  struct MsoCF::IActionManager *v20; // rax
  bool v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  MsoCF::IPropertySet *v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  MsoCF::IPropertySet *v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[40]; // [rsp+A0h] [rbp-60h] BYREF
  Mso::Memory *v33; // [rsp+C8h] [rbp-38h]
  _BYTE v34[272]; // [rsp+E0h] [rbp-20h] BYREF

  v25 = 0;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v31);
  Jot::CWzInBuffer::SetFromResource(
    (Jot::CWzInBuffer *)v31,
    *((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62),
    0x23EC314Du);
  GalleryDataSource = CMsoGalleryUserDefault::GetGalleryDataSource((CMsoGalleryUserDefault *)this);
  v3 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v31);
  GalleryDSSP::AddGalleryCategory(GalleryDataSource, (struct GalleryCategorySP *)&v25, v3, v4);
  MsoCF::CreatePropertySet(&v24, 0);
  v23 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this[31] + 13) + 80LL))(*((_QWORD *)this[31] + 13), &v23);
  v26 = 131605;
  v5 = v24;
  v27 = v24;
  if ( v24 )
    (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 8LL))(v24);
  v6 = v23;
  v7 = MsoCF::TheActionManager(v5);
  if ( !(*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, __int64, _QWORD))(*(_QWORD *)v7 + 176LL))(
          v7,
          &v26,
          v6,
          0)
    || (v19 = v23,
        v20 = MsoCF::TheActionManager(v8),
        (*(unsigned __int8 (__fastcall **)(struct MsoCF::IActionManager *, int *, __int64, _QWORD))(*(_QWORD *)v20
                                                                                                  + 168LL))(
          v20,
          &v26,
          v19,
          0)) )
  {
    v28 = 0;
    v29 = 0;
    MsoCF::IPropertySet::GetProperty(
      v24,
      Jot::PropertySpace_JotMain::priNoteTagLabelList,
      (struct MsoCF::CPropertyValue *)&v28);
    v9 = *(int *)(v28 + 8);
    MsoCF::CreatePropertySet(&v30, 0);
    v10 = 0;
    v11 = 0;
    v12 = 0;
    while ( v11 < v9 )
    {
      if ( v10 >= 0x64 )
      {
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        if ( (v29 & 0x2000000) != 0 )
          MsoCF::CPropertyData::FreeAndZero_ComplexType(&v28);
        if ( v27 )
          (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v24 )
          (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 16LL))(v24);
        Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v31);
        goto LABEL_47;
      }
      if ( *(_DWORD *)(v12 + *(_QWORD *)v28 + 8) == 117899322 && *(_QWORD *)(v12 + *(_QWORD *)v28) )
      {
        v22 = 0;
        if ( !Jot::CNoteFlagGalleryUser::AddDelayLoadedControlGalleryItem(
                (Jot::CNoteFlagGalleryUser *)this,
                (struct GalleryItemSP *)&v22,
                this[30],
                (struct GalleryCategorySP *)&v25,
                *((_DWORD *)qword_140200460 + v11),
                v21) )
        {
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v18 = v29;
          if ( (v29 & 0x2000000) != 0 )
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&v28);
          goto LABEL_38;
        }
        IsFluentRefresh = Jot::IsFluentRefresh(v13);
        v15 = 24;
        if ( !IsFluentRefresh )
          v15 = 16;
        GalleryItemSP::SetLoadingImage((GalleryItemSP *)&v22, *((_DWORD *)this + 64), v15, 0);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v22 = 0;
      }
      ++v10;
      ++v11;
      v12 += 16;
    }
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v16 = v29;
    if ( (v29 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v28);
    if ( v27 )
      (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v33 != (Mso::Memory *)v34 )
      Mso::Memory::Free(v33, (void *)v16);
    std::wstring::~wstring(v32);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return 1;
  }
  else
  {
LABEL_38:
    if ( v27 )
      (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v33 != (Mso::Memory *)v34 )
      Mso::Memory::Free(v33, (void *)v18);
    std::wstring::~wstring(v32);
LABEL_47:
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return 0;
  }
}

```

## disassembly

```asm
0x14008a428  mov     [rsp-8+arg_8], rbx
0x14008a42d  mov     [rsp-8+arg_10], rsi
0x14008a432  push    rbp
0x14008a433  push    rdi
0x14008a434  push    r12
0x14008a436  push    r14
0x14008a438  push    r15
0x14008a43a  lea     rbp, [rsp-100h]
0x14008a442  sub     rsp, 200h
0x14008a449  mov     rax, cs:__security_cookie
0x14008a450  xor     rax, rsp
0x14008a453  mov     [rbp+120h+var_30], rax
0x14008a45a  mov     r14, rcx
0x14008a45d  xor     r12d, r12d
0x14008a460  mov     [rsp+220h+var_1D8], r12
0x14008a465  lea     rcx, [rbp+120h+var_1A0]
0x14008a469  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x14008a46e  mov     r8d, 23EC314Dh
0x14008a474  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14008a47b  mov     rdx, [rdx+1F0h]
0x14008a482  lea     rcx, [rbp+120h+var_1A0]
0x14008a486  call    cs:__imp_?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x14008a48c  mov     rcx, r14
0x14008a48f  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x14008a495  mov     rbx, rax
0x14008a498  lea     rcx, [rbp+120h+var_1A0]
0x14008a49c  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14008a4a2  mov     r8, rax; wchar_t *
0x14008a4a5  lea     rdx, [rsp+220h+var_1D8]; struct GalleryCategorySP *
0x14008a4aa  mov     rcx, rbx; this
0x14008a4ad  call    ?AddGalleryCategory@GalleryDSSP@@QEAA_NPEAVGalleryCategorySP@@PEB_WPEAVFlexValue@FlexUI@@@Z; GalleryDSSP::AddGalleryCategory(GalleryCategorySP *,wchar_t const *,FlexUI::FlexValue *)
0x14008a4b2  xor     edx, edx
0x14008a4b4  lea     rcx, [rsp+220h+var_1E0]
0x14008a4b9  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x14008a4bf  nop
0x14008a4c0  mov     [rsp+220h+var_1E8], r12
0x14008a4c5  mov     rax, [r14+0F8h]
0x14008a4cc  mov     rcx, [rax+68h]
0x14008a4d0  mov     rax, [rcx]
0x14008a4d3  lea     rdx, [rsp+220h+var_1E8]
0x14008a4d8  mov     rax, [rax+50h]
0x14008a4dc  call    cs:__guard_dispatch_icall_fptr
0x14008a4e2  mov     [rsp+220h+var_1D0], 20215h
0x14008a4ea  mov     rcx, [rsp+220h+var_1E0]
0x14008a4ef  mov     [rsp+220h+var_1C8], rcx
0x14008a4f4  test    rcx, rcx
0x14008a4f7  jz      short loc_14008A507
0x14008a4f9  mov     rax, [rcx]
0x14008a4fc  mov     rax, [rax+8]
0x14008a500  call    cs:__guard_dispatch_icall_fptr
0x14008a506  nop
0x14008a507  mov     rbx, [rsp+220h+var_1E8]
0x14008a50c  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x14008a512  mov     r10, rax
0x14008a515  mov     rcx, [rax]
0x14008a518  mov     rax, [rcx+0B0h]
0x14008a51f  xor     r9d, r9d
0x14008a522  mov     r8, rbx
0x14008a525  lea     rdx, [rsp+220h+var_1D0]
0x14008a52a  mov     rcx, r10
0x14008a52d  call    cs:__guard_dispatch_icall_fptr
0x14008a533  test    al, al
0x14008a535  jnz     loc_14008A75A
0x14008a53b  mov     [rsp+220h+var_1C0], r12
0x14008a540  mov     [rsp+220h+var_1B8], r12d
0x14008a545  lea     r8, [rsp+220h+var_1C0]
0x14008a54a  mov     rdx, cs:__imp_?priNoteTagLabelList@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priNoteTagLabelList
0x14008a551  mov     rcx, [rsp+220h+var_1E0]
0x14008a556  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x14008a55c  mov     rax, [rsp+220h+var_1C0]
0x14008a561  movsxd  r15, dword ptr [rax+8]
0x14008a565  xor     edx, edx
0x14008a567  lea     rcx, [rsp+220h+var_1B0]
0x14008a56c  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x14008a572  mov     esi, r12d
0x14008a575  mov     rdi, r12
0x14008a578  mov     rbx, r12
0x14008a57b  cmp     rdi, r15
0x14008a57e  jge     loc_14008A62D
0x14008a584  cmp     esi, 64h ; 'd'
0x14008a587  jnb     loc_14008A815
0x14008a58d  mov     rax, [rsp+220h+var_1C0]
0x14008a592  mov     rcx, [rax]
0x14008a595  cmp     dword ptr [rbx+rcx+8], 707003Ah
0x14008a59d  jnz     short loc_14008A617
0x14008a59f  cmp     [rbx+rcx], r12
0x14008a5a3  jz      short loc_14008A617
0x14008a5a5  mov     [rsp+220h+var_1F0], r12
0x14008a5aa  lea     rax, qword_140200460
0x14008a5b1  mov     eax, [rax+rdi*4]
0x14008a5b4  mov     [rsp+220h+var_200], eax; int
0x14008a5b8  lea     r9, [rsp+220h+var_1D8]; struct GalleryCategorySP *
0x14008a5bd  mov     r8, [r14+0F0h]; struct OfficeSpace::IOfficeSpace *
0x14008a5c4  lea     rdx, [rsp+220h+var_1F0]; struct GalleryItemSP *
0x14008a5c9  mov     rcx, r14; this
0x14008a5cc  call    ?AddDelayLoadedControlGalleryItem@CNoteFlagGalleryUser@Jot@@AEAA_NPEAVGalleryItemSP@@PEAUIOfficeSpace@OfficeSpace@@PEAVGalleryCategorySP@@H_N@Z; Jot::CNoteFlagGalleryUser::AddDelayLoadedControlGalleryItem(GalleryItemSP *,OfficeSpace::IOfficeSpace *,GalleryCategorySP *,int,bool)
0x14008a5d1  test    al, al
0x14008a5d3  jz      loc_14008A70A
0x14008a5d9  call    ?IsFluentRefresh@Jot@@YA_NXZ; Jot::IsFluentRefresh(void)
0x14008a5de  mov     edx, [r14+100h]
0x14008a5e5  xor     r9d, r9d
0x14008a5e8  lea     rcx, [rsp+220h+var_1F0]
0x14008a5ed  test    al, al
0x14008a5ef  lea     r8d, [r9+18h]
0x14008a5f3  jz      short loc_14008A625
0x14008a5f5  call    cs:__imp_?SetLoadingImage@GalleryItemSP@@QEAA_NHH_N@Z; GalleryItemSP::SetLoadingImage(int,int,bool)
0x14008a5fb  mov     rcx, [rsp+220h+var_1F0]
0x14008a600  test    rcx, rcx
0x14008a603  jz      short loc_14008A612
0x14008a605  mov     rax, [rcx]
0x14008a608  mov     rax, [rax+10h]
0x14008a60c  call    cs:__guard_dispatch_icall_fptr
0x14008a612  mov     [rsp+220h+var_1F0], r12
0x14008a617  inc     esi
0x14008a619  inc     rdi
0x14008a61c  add     rbx, 10h
0x14008a620  jmp     loc_14008A57B
0x14008a625  mov     r8d, 10h
0x14008a62b  jmp     short loc_14008A5F5
0x14008a62d  mov     rcx, [rsp+220h+var_1B0]
0x14008a632  test    rcx, rcx
0x14008a635  jz      short loc_14008A645
0x14008a637  mov     rax, [rcx]
0x14008a63a  mov     rax, [rax+10h]
0x14008a63e  call    cs:__guard_dispatch_icall_fptr
0x14008a644  nop
0x14008a645  mov     edx, [rsp+220h+var_1B8]
0x14008a649  mov     eax, edx
0x14008a64b  shr     eax, 19h
0x14008a64e  test    al, 1
0x14008a650  jz      short loc_14008A65E
0x14008a652  lea     rcx, [rsp+220h+var_1C0]
0x14008a657  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14008a65d  nop
0x14008a65e  mov     rcx, [rsp+220h+var_1C8]
0x14008a663  test    rcx, rcx
0x14008a666  jz      short loc_14008A675
0x14008a668  mov     rax, [rcx]
0x14008a66b  mov     rax, [rax+10h]
0x14008a66f  call    cs:__guard_dispatch_icall_fptr
0x14008a675  mov     [rsp+220h+var_1C8], r12
0x14008a67a  mov     rcx, [rsp+220h+var_1E8]
0x14008a67f  test    rcx, rcx
0x14008a682  jz      short loc_14008A692
0x14008a684  mov     rax, [rcx]
0x14008a687  mov     rax, [rax+10h]
0x14008a68b  call    cs:__guard_dispatch_icall_fptr
0x14008a691  nop
0x14008a692  mov     rcx, [rsp+220h+var_1E0]
0x14008a697  test    rcx, rcx
0x14008a69a  jz      short loc_14008A6AA
0x14008a69c  mov     rax, [rcx]
0x14008a69f  mov     rax, [rax+10h]
0x14008a6a3  call    cs:__guard_dispatch_icall_fptr
0x14008a6a9  nop
0x14008a6aa  lea     rax, [rbp+120h+var_140]
0x14008a6ae  mov     rcx, [rbp+120h+var_158]
0x14008a6b2  cmp     rcx, rax
0x14008a6b5  jz      short loc_14008A6BD
0x14008a6b7  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x14008a6bd  lea     rcx, [rbp+120h+var_180]; void *
0x14008a6c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008a6c6  mov     rcx, [rsp+220h+var_1D8]
0x14008a6cb  test    rcx, rcx
0x14008a6ce  jz      short loc_14008A6DD
0x14008a6d0  mov     rdx, [rcx]
0x14008a6d3  mov     rax, [rdx+10h]
0x14008a6d7  call    cs:__guard_dispatch_icall_fptr
0x14008a6dd  mov     al, 1
0x14008a6df  mov     rcx, [rbp+120h+var_30]
0x14008a6e6  xor     rcx, rsp; StackCookie
0x14008a6e9  call    __security_check_cookie
0x14008a6ee  lea     r11, [rsp+220h+var_20]
0x14008a6f6  mov     rbx, [r11+38h]
0x14008a6fa  mov     rsi, [r11+40h]
0x14008a6fe  mov     rsp, r11
0x14008a701  pop     r15
0x14008a703  pop     r14
0x14008a705  pop     r12
0x14008a707  pop     rdi
0x14008a708  pop     rbp
0x14008a709  retn
0x14008a70a  mov     rcx, [rsp+220h+var_1F0]
0x14008a70f  test    rcx, rcx
0x14008a712  jz      short loc_14008A721
0x14008a714  mov     rax, [rcx]
0x14008a717  mov     rax, [rax+10h]
0x14008a71b  call    cs:__guard_dispatch_icall_fptr
0x14008a721  mov     [rsp+220h+var_1F0], r12
0x14008a726  mov     rcx, [rsp+220h+var_1B0]
0x14008a72b  test    rcx, rcx
0x14008a72e  jz      short loc_14008A740
0x14008a730  mov     rax, [rcx]
0x14008a733  mov     rax, [rax+10h]
0x14008a737  call    cs:__guard_dispatch_icall_fptr
0x14008a73d  nop
0x14008a73e  xchg    ax, ax
0x14008a740  mov     edx, [rsp+220h+var_1B8]
0x14008a744  mov     eax, edx
0x14008a746  shr     eax, 19h
0x14008a749  test    al, 1
0x14008a74b  jz      short loc_14008A78E
0x14008a74d  lea     rcx, [rsp+220h+var_1C0]
0x14008a752  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14008a758  jmp     short loc_14008A78E
0x14008a75a  mov     rbx, [rsp+220h+var_1E8]
0x14008a75f  call    cs:__imp_?TheActionManager@MsoCF@@YAPEAUIActionManager@1@XZ; MsoCF::TheActionManager(void)
0x14008a765  mov     r10, rax
0x14008a768  mov     rcx, [rax]
0x14008a76b  mov     rax, [rcx+0A8h]
0x14008a772  xor     r9d, r9d
0x14008a775  mov     r8, rbx
0x14008a778  lea     rdx, [rsp+220h+var_1D0]
0x14008a77d  mov     rcx, r10
0x14008a780  call    cs:__guard_dispatch_icall_fptr
0x14008a786  test    al, al
0x14008a788  jnz     loc_14008A53B
0x14008a78e  mov     rcx, [rsp+220h+var_1C8]
0x14008a793  test    rcx, rcx
0x14008a796  jz      short loc_14008A7A5
0x14008a798  mov     rax, [rcx]
0x14008a79b  mov     rax, [rax+10h]
0x14008a79f  call    cs:__guard_dispatch_icall_fptr
0x14008a7a5  mov     [rsp+220h+var_1C8], r12
0x14008a7aa  mov     rcx, [rsp+220h+var_1E8]
0x14008a7af  test    rcx, rcx
0x14008a7b2  jz      short loc_14008A7C2
0x14008a7b4  mov     rax, [rcx]
0x14008a7b7  mov     rax, [rax+10h]
0x14008a7bb  call    cs:__guard_dispatch_icall_fptr
0x14008a7c1  nop
0x14008a7c2  mov     rcx, [rsp+220h+var_1E0]
0x14008a7c7  test    rcx, rcx
0x14008a7ca  jz      short loc_14008A7DA
0x14008a7cc  mov     rax, [rcx]
0x14008a7cf  mov     rax, [rax+10h]
0x14008a7d3  call    cs:__guard_dispatch_icall_fptr
0x14008a7d9  nop
0x14008a7da  lea     rax, [rbp+120h+var_140]
0x14008a7de  mov     rcx, [rbp+120h+var_158]
0x14008a7e2  cmp     rcx, rax
0x14008a7e5  jz      short loc_14008A7ED
0x14008a7e7  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x14008a7ed  lea     rcx, [rbp+120h+var_180]; void *
0x14008a7f1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008a7f6  nop
0x14008a7f7  mov     rcx, [rsp+220h+var_1D8]
0x14008a7fc  test    rcx, rcx
0x14008a7ff  jz      short loc_14008A80E
0x14008a801  mov     rax, [rcx]
0x14008a804  mov     rax, [rax+10h]
0x14008a808  call    cs:__guard_dispatch_icall_fptr
0x14008a80e  xor     al, al
0x14008a810  jmp     loc_14008A6DF
0x14008a815  mov     rcx, [rsp+220h+var_1B0]
0x14008a81a  test    rcx, rcx
0x14008a81d  jz      short loc_14008A82D
0x14008a81f  mov     rax, [rcx]
0x14008a822  mov     rax, [rax+10h]
0x14008a826  call    cs:__guard_dispatch_icall_fptr
0x14008a82c  nop
0x14008a82d  mov     edx, [rsp+220h+var_1B8]
0x14008a831  mov     eax, edx
0x14008a833  shr     eax, 19h
0x14008a836  test    al, 1
0x14008a838  jz      short loc_14008A846
0x14008a83a  lea     rcx, [rsp+220h+var_1C0]
0x14008a83f  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14008a845  nop
0x14008a846  mov     rcx, [rsp+220h+var_1C8]
0x14008a84b  test    rcx, rcx
0x14008a84e  jz      short loc_14008A85D
0x14008a850  mov     rax, [rcx]
0x14008a853  mov     rax, [rax+10h]
0x14008a857  call    cs:__guard_dispatch_icall_fptr
0x14008a85d  mov     [rsp+220h+var_1C8], r12
0x14008a862  mov     rcx, [rsp+220h+var_1E8]
0x14008a867  test    rcx, rcx
0x14008a86a  jz      short loc_14008A87A
0x14008a86c  mov     rax, [rcx]
0x14008a86f  mov     rax, [rax+10h]
0x14008a873  call    cs:__guard_dispatch_icall_fptr
0x14008a879  nop
0x14008a87a  mov     rcx, [rsp+220h+var_1E0]
0x14008a87f  test    rcx, rcx
0x14008a882  jz      short loc_14008A892
0x14008a884  mov     rax, [rcx]
0x14008a887  mov     rax, [rax+10h]
0x14008a88b  call    cs:__guard_dispatch_icall_fptr
0x14008a891  nop
0x14008a892  lea     rcx, [rbp+120h+var_1A0]
0x14008a896  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x14008a89b  jmp     loc_14008A7F7
```
