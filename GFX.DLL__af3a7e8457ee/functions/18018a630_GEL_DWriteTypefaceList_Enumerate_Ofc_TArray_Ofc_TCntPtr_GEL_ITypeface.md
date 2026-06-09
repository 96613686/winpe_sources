# GEL::DWriteTypefaceList::Enumerate(Ofc::TArray<Ofc::TCntPtr<GEL::ITypeface>> &)

- ea: `0x18018a630`
- end: `0x18018afa4`
- name: `?Enumerate@DWriteTypefaceList@GEL@@EEAAXAEAV?$TArray@V?$TCntPtr@UITypeface@GEL@@@Ofc@@@Ofc@@@Z`
- size: `2420`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180020400`
- `0x1800260d0`
- `0x1800558f0`
- `0x180055ffc`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x180067030`
- `0x18007a98c`
- `0x18007aa30`
- `0x1800bba88`
- `0x1800be640`
- `0x18015b17c`
- `0x18015b1dc`
- `0x18015b5dc`
- `0x18016eca8`
- `0x18016ed44`
- `0x180172180`
- `0x18017ef3c`
- `0x18018a630`
- `0x18018b118`

## import_xrefs

- `Mso98Win32Client!__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ` at `0x18018a6a9`
- `Mso98Win32Client!__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ` at `0x18018a6a9`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018a6af`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018a6af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af35`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af43`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af57`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af65`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af73`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af81`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af8f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af9d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af35`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af43`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af57`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af65`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af73`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af81`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af8f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018af9d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a93c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a94b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018aaf3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018ab02`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018ab13`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a93c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a94b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018aaf3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018ab02`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018ab13`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GEL::DWriteTypefaceList::Enumerate(__int64 a1, Ofc::CArrayImpl *a2)
{
  Mso::CustomFontOAL *v3; // rcx
  Mso::DWriteAssistant *v4; // rcx
  Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  struct Mso::DWriteAssistant::IFontCollection *FontCollection; // rsi
  unsigned int v7; // edi
  unsigned int v8; // r12d
  __m128i si128; // xmm6
  __int64 size_of; // rax
  _QWORD *v11; // rax
  char v12; // bl
  __int64 v13; // rcx
  __int64 v14; // rax
  Mso::Memory *v15; // r14
  Mso::Memory *v16; // r13
  Mso::Memory *v17; // r15
  void *v18; // rdx
  Mso::Memory *v19; // rcx
  int (__fastcall *v20)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, __int64 *); // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  const char *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  const char *v31; // rcx
  _QWORD *v32; // rax
  char v33; // r12
  __int128 *v34; // r8
  __int64 *Internal; // rax
  __int64 v36; // rbx
  __int64 v37; // r9
  __int64 v38; // r8
  char *v39; // r15
  __int64 v40; // rdx
  unsigned int v41; // r10d
  __int64 v42; // rdx
  __int64 v43; // rcx
  char v44; // al
  Ofc::CArrayImpl *v45; // rax
  __int64 v46; // r15
  __int64 v47; // r12
  __int64 v48; // rcx
  int v49; // [rsp+20h] [rbp-E0h]
  char v50; // [rsp+40h] [rbp-C0h]
  char v51; // [rsp+41h] [rbp-BFh]
  unsigned int v52; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  const char *v54; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+58h] [rbp-A8h]
  Mso::Memory *v56; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v57; // [rsp+68h] [rbp-98h]
  unsigned int v58; // [rsp+6Ch] [rbp-94h]
  Mso::Memory *v59; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v60; // [rsp+78h] [rbp-88h]
  unsigned int v61; // [rsp+7Ch] [rbp-84h]
  Mso::Memory *v62; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v63; // [rsp+88h] [rbp-78h]
  unsigned int v64; // [rsp+8Ch] [rbp-74h]
  unsigned int v65; // [rsp+90h] [rbp-70h]
  const char *v66; // [rsp+98h] [rbp-68h] BYREF
  Ofc::CArrayImpl *v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v69[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v70; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v71; // [rsp+D0h] [rbp-30h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  _QWORD v76[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v77[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v78[16]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v79; // [rsp+128h] [rbp+28h] BYREF
  __m128i v80; // [rsp+138h] [rbp+38h]
  _OWORD v81[2]; // [rsp+148h] [rbp+48h] BYREF

  v67 = a2;
  v74 = a1;
  v54 = "Started enumerating Typefaces.";
  Mso::Diagnostics::SendDiagnosticTrace<>(7365471, 173, 50, 2, (__int64)&v54);
  Ofc::CArrayImpl::Reset(a2, Ofc::TDestructRange<Ofc::TCntPtr<Gfx::IFigurePrimitive>,0>::Do);
  Mso::CustomFontOAL::InitializeCustomFontAssetLibrary(v3);
  ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(v4);
  FontCollection = Mso::DWriteAssistant::ResourceManager::GetFontCollection(ResourceManagerInstance);
  v65 = (*(__int64 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *))(*(_QWORD *)FontCollection + 24LL))(FontCollection);
  v7 = 0;
  v8 = 0;
  v55 = 0;
  if ( v65 )
  {
    v76[1] = v69;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v53 = 0;
      v68 = 0;
      v69[0] = 0;
      v69[1] = 0;
      size_of = std::_Get_size_of_n<48>(1);
      v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      *v11 = v11;
      v11[1] = v11;
      v69[0] = v11;
      v70 = 0;
      v71 = 0;
      v72 = 7;
      v73 = 8;
      v68 = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
        &v70,
        16,
        v11);
      v51 = 1;
      v12 = (*(__int64 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD))(*(_QWORD *)FontCollection
                                                                                              + 120LL))(
              FontCollection,
              v8);
      v50 = v12;
      if ( (*(unsigned __int8 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD))(*(_QWORD *)FontCollection + 440LL))(
             FontCollection,
             v8) )
      {
        goto LABEL_4;
      }
      v81[0] = 0;
      v81[1] = si128;
      LOWORD(v81[0]) = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0x80000000;
      v59 = 0;
      v60 = 0;
      v61 = 0x80000000;
      v62 = 0;
      v63 = 0;
      v64 = 0x80000000;
      v52 = 0;
      v14 = *(_QWORD *)FontCollection;
      if ( !v12 )
        break;
      if ( (*(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, _OWORD *))(v14 + 80))(
             FontCollection,
             v8,
             v81) < 0
        || !(*(unsigned __int8 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _OWORD *, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)FontCollection + 280LL))(
              FontCollection,
              v81,
              0,
              0,
              0,
              &v52)
        || !v52 )
      {
        goto LABEL_8;
      }
      Ofc::CArrayImpl::NewAt(
        (Ofc::CArrayImpl *)&v56,
        4u,
        0,
        v52,
        Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
        (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
      Ofc::CArrayImpl::NewAt(
        (Ofc::CArrayImpl *)&v59,
        4u,
        0,
        v52,
        Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
        (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
      Ofc::CArrayImpl::NewAt(
        (Ofc::CArrayImpl *)&v62,
        4u,
        0,
        v52,
        Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
        (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
      v15 = v62;
      v16 = v59;
      v17 = v56;
      if ( (*(unsigned __int8 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _OWORD *, Mso::Memory *, Mso::Memory *, Mso::Memory *, unsigned int *))(*(_QWORD *)FontCollection + 280LL))(
             FontCollection,
             v81,
             v56,
             v59,
             v62,
             &v52) )
      {
        goto LABEL_23;
      }
      if ( v15 )
        Mso::Memory::Free(v15, v18);
      if ( v16 )
        Mso::Memory::Free(v16, v18);
      if ( v17 )
      {
        v19 = v17;
LABEL_37:
        Mso::Memory::Free(v19, v18);
      }
LABEL_38:
      std::wstring::~wstring(v81);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v68);
      v13 = v53;
      if ( v53 )
      {
LABEL_39:
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
LABEL_40:
      v55 = ++v8;
      if ( v8 >= v65 )
        goto LABEL_41;
    }
    v20 = *(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, __int64 *))(v14 + 32);
    v21 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    if ( v20(FontCollection, v8, &v53) < 0 )
    {
LABEL_8:
      std::wstring::~wstring(v81);
LABEL_4:
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v68);
      v13 = v53;
      if ( v53 )
        goto LABEL_39;
      goto LABEL_40;
    }
    if ( !v53 )
      goto LABEL_79;
    v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 32LL))(v53);
    Ofc::CArrayImpl::NewAt(
      (Ofc::CArrayImpl *)&v56,
      4u,
      0,
      v52,
      Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
      (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
    Ofc::CArrayImpl::NewAt(
      (Ofc::CArrayImpl *)&v59,
      4u,
      0,
      v52,
      Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
      (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
    Ofc::CArrayImpl::NewAt(
      (Ofc::CArrayImpl *)&v62,
      4u,
      0,
      v52,
      Ofc::TDefaultConstructRange<enum DWRITE_FONT_STYLE,1,1>::Do,
      (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<enum DWRITE_FONT_STYLE,1>::Do);
    v16 = v59;
    v15 = v62;
    v17 = v56;
    v12 = v50;
LABEL_23:
    if ( !v52 )
    {
LABEL_32:
      v7 = 0;
      if ( v15 )
        Mso::Memory::Free(v15, v18);
      if ( v16 )
        Mso::Memory::Free(v16, v18);
      v19 = v56;
      if ( v56 )
        goto LABEL_37;
      goto LABEL_38;
    }
    while ( 1 )
    {
      v79 = 0;
      v80 = si128;
      LOWORD(v79) = 0;
      v75 = 0;
      if ( v12 )
      {
        if ( v7 >= v63 )
          goto LABEL_74;
        v22 = 4LL * v7;
        if ( v7 >= v60 )
          goto LABEL_73;
        if ( v7 >= v57 )
        {
          CrashWithRecovery(0x1E892498u, 0);
LABEL_73:
          CrashWithRecovery(0x1E892498u, 0);
LABEL_74:
          CrashWithRecovery(0x1E892498u, 0);
LABEL_75:
          CrashWithRecovery(0x1E892496u, 0);
LABEL_76:
          CrashWithRecovery(0x1E892496u, 0);
LABEL_77:
          CrashWithRecovery(0x1E892496u, 0);
LABEL_78:
          CrashWithRecovery(0x1E3C3840u, 0);
LABEL_79:
          CrashWithRecovery(0x1E3C3840u, 0);
          JUMPOUT(0x18018AFA3LL);
        }
        if ( !(*(unsigned __int8 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _OWORD *, __int64, char *, char *, __int128 *))(*(_QWORD *)FontCollection + 344LL))(
                FontCollection,
                v81,
                (__int64)v17 + v22,
                (char *)v16 + v22,
                (char *)v15 + v22,
                &v79) )
          goto LABEL_29;
      }
      else
      {
        v54 = 0;
        if ( !v53 )
          goto LABEL_78;
        if ( (*(int (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v53 + 40LL))(v53, v7, &v54) < 0
          || (*(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, const char *, __int128 *))(*(_QWORD *)FontCollection + 296LL))(
               FontCollection,
               v54,
               &v79) < 0 )
        {
          v24 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v24 + 16LL))(v24);
          }
          std::wstring::~wstring(&v79);
          goto LABEL_31;
        }
        v25 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v54);
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
        if ( v7 >= v57 )
          goto LABEL_77;
        v22 = 4LL * v7;
        *(_DWORD *)((char *)v17 + v22) = v26;
        v27 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v54);
        v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
        if ( v7 >= v60 )
          goto LABEL_76;
        *(_DWORD *)((char *)v16 + v22) = v28;
        v29 = Mso::TCntPtr<IWICImagingFactory>::operator->(&v54);
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 48LL))(v29);
        if ( v7 >= v63 )
          goto LABEL_75;
        *((_DWORD *)v15 + v7) = v30;
        v31 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v31 + 16LL))(v31);
        }
      }
      v32 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                        &v68,
                        v77,
                        &v79);
      if ( *v32 == v69[0] )
      {
        if ( v50 )
        {
          v33 = (*(__int64 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)FontCollection + 176LL))(
                  FontCollection,
                  v8,
                  *(unsigned int *)((char *)v17 + v22),
                  *(unsigned int *)((char *)v16 + v22),
                  *(_DWORD *)((char *)v15 + v22));
          v51 = v33;
        }
        else
        {
          v33 = v51;
        }
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          &v68,
          v78,
          &v79);
        v34 = &v79;
        if ( v80.m128i_i64[1] > 7uLL )
          v34 = (__int128 *)v79;
        LOBYTE(v49) = 1;
        Internal = (__int64 *)GEL::TypefaceList::GetInternal(v74 - 120, v76, v34, 0, v49);
        v36 = *Internal;
        *Internal = 0;
        v75 = v36;
        if ( v76[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[0] + 8LL))(v76[0]);
        GEL::DWriteTypeface::UnloadAllEmbbededFonts((GEL::DWriteTypeface *)v36);
        *(_BYTE *)(v36 + 99) = v33;
        if ( v50 )
        {
          v37 = *((unsigned int *)v15 + v7);
          v54 = (char *)v16 + 4 * v7;
          v38 = *(unsigned int *)v54;
          v39 = (char *)v17 + 4 * v7;
          v66 = v39;
          v40 = *(unsigned int *)v39;
          *(_DWORD *)(v36 + 208) = v55;
          GEL::DWriteTypeface::SetFontMatchParameters(v36, v40, v38, v37);
          *(_BYTE *)(v36 + 100) = 0;
          if ( (*(unsigned __int8 (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _QWORD))(*(_QWORD *)FontCollection + 168LL))(
                 FontCollection,
                 v41) )
          {
            *(_BYTE *)(v36 + 101) = 1;
          }
          (*(void (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _OWORD *, char *, const char *, __int64, __int64))(*(_QWORD *)FontCollection + 272LL))(
            FontCollection,
            v81,
            v39,
            v54,
            (__int64)v15 + 4 * v7,
            v36 + 48);
          (*(void (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, _OWORD *, const char *, const char *, __int64, __int64, int))(*(_QWORD *)FontCollection + 328LL))(
            FontCollection,
            v81,
            v66,
            v54,
            (__int64)v15 + 4 * v7,
            v36 + 88,
            10);
          if ( *(_BYTE *)(v36 + 91) == 9 )
          {
            v44 = 49;
          }
          else
          {
            LOBYTE(v42) = *(_BYTE *)(v36 + 89);
            LOBYTE(v43) = *(_BYTE *)(v36 + 88);
            v44 = sub_18018B118(v43, v42) | 2;
          }
          *(_BYTE *)(v36 + 98) = v44;
        }
        else
        {
          GEL::DWriteTypeface::SetInfo(
            v36,
            v53,
            *((unsigned int *)v17 + v7),
            *((unsigned int *)v16 + v7),
            *((_DWORD *)v15 + v7));
        }
        Ofc::CArrayImpl::EnsureCapacityForOneElem(
          v67,
          8u,
          (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Ofc::TCntPtr<GEL::IEffect const>,1>::Do);
        v45 = v67;
        v46 = *((unsigned int *)v67 + 2);
        v47 = *(_QWORD *)v67;
        *(_QWORD *)(*(_QWORD *)v67 + 8 * v46) = 0;
        ++*((_DWORD *)v45 + 2);
        (**(void (__fastcall ***)(__int64))v36)(v36);
        v48 = *(_QWORD *)(v47 + 8 * v46);
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
        *(_QWORD *)(v47 + 8 * v46) = v36;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
        std::wstring::~wstring(&v79);
        v8 = v55;
        goto LABEL_30;
      }
LABEL_29:
      std::wstring::~wstring(&v79);
LABEL_30:
      v12 = v50;
LABEL_31:
      ++v7;
      v17 = v56;
      if ( v7 >= v52 )
        goto LABEL_32;
    }
  }
LABEL_41:
  v66 = "Finished enumerating Typefaces.";
  return Mso::Diagnostics::SendDiagnosticTrace<>(7365472, 173, 50, 2, (__int64)&v66);
}

```

## disassembly

```asm
0x18018a630  mov     rax, rsp
0x18018a633  mov     [rax+18h], rbx
0x18018a637  push    rbp
0x18018a638  push    rsi
0x18018a639  push    rdi
0x18018a63a  push    r12
0x18018a63c  push    r13
0x18018a63e  push    r14
0x18018a640  push    r15
0x18018a642  lea     rbp, [rsp-80h]
0x18018a647  sub     rsp, 180h
0x18018a64e  movaps  xmmword ptr [rax-48h], xmm6
0x18018a652  mov     rax, cs:__security_cookie
0x18018a659  xor     rax, rsp
0x18018a65c  mov     [rbp+0B0h+var_48], rax
0x18018a660  mov     rbx, rdx
0x18018a663  mov     [rbp+0B0h+var_110], rdx
0x18018a667  mov     [rbp+0B0h+var_C0], rcx
0x18018a66b  lea     rax, aStartedEnumera; "Started enumerating Typefaces."
0x18018a672  mov     [rsp+1B0h+var_160], rax
0x18018a677  mov     r9d, 2
0x18018a67d  lea     rax, [rsp+1B0h+var_160]
0x18018a682  mov     [rsp+1B0h+var_190], rax
0x18018a687  mov     edx, 0ADh
0x18018a68c  mov     ecx, 70635Fh
0x18018a691  lea     r8d, [r9+30h]
0x18018a695  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18018a69a  lea     rdx, ?Do@?$TDestructRange@V?$TCntPtr@UIFigurePrimitive@Gfx@@@Ofc@@$0A@@Ofc@@SAXPEAEK@Z; void (*)(unsigned __int8 *, unsigned int)
0x18018a6a1  mov     rcx, rbx; this
0x18018a6a4  call    ?Reset@CArrayImpl@Ofc@@IEAAXP6AXPEAEK@Z@Z; Ofc::CArrayImpl::Reset(void (*)(uchar *,ulong))
0x18018a6a9  call    cs:__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ; Mso::CustomFontOAL::InitializeCustomFontAssetLibrary(void)
0x18018a6af  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018a6b5  mov     rcx, rax; this
0x18018a6b8  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018a6bd  mov     rsi, rax
0x18018a6c0  mov     rcx, [rax]
0x18018a6c3  mov     rax, [rcx+18h]
0x18018a6c7  mov     rcx, rsi
0x18018a6ca  call    cs:__guard_dispatch_icall_fptr
0x18018a6d0  mov     [rbp+0B0h+var_120], eax
0x18018a6d3  xor     edi, edi
0x18018a6d5  mov     r12d, edi
0x18018a6d8  mov     [rsp+1B0h+var_158], edi
0x18018a6dc  test    eax, eax
0x18018a6de  jz      loc_18018AB6F
0x18018a6e4  lea     rax, [rbp+0B0h+var_F8]
0x18018a6e8  mov     [rbp+0B0h+var_A8], rax
0x18018a6ec  lea     r14, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018a6f3  lea     r15, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018a6fa  lea     r13, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018a701  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18018a709  mov     [rsp+1B0h+var_168], rdi
0x18018a70e  mov     [rbp+0B0h+var_100], 0
0x18018a715  mov     [rbp+0B0h+var_F8], rdi
0x18018a719  mov     [rbp+0B0h+var_F0], rdi
0x18018a71d  mov     ecx, 1
0x18018a722  call    ??$_Get_size_of_n@$0DA@@std@@YA_K_K@Z; std::_Get_size_of_n<48>(unsigned __int64)
0x18018a727  mov     rcx, rax
0x18018a72a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18018a72f  mov     [rax], rax
0x18018a732  mov     [rax+8], rax
0x18018a736  mov     [rbp+0B0h+var_F8], rax
0x18018a73a  mov     [rbp+0B0h+var_E8], rdi
0x18018a73e  xorps   xmm0, xmm0
0x18018a741  movdqa  [rbp+0B0h+var_E0], xmm0
0x18018a746  mov     [rbp+0B0h+var_D0], 7
0x18018a74e  mov     [rbp+0B0h+var_C8], 8
0x18018a756  mov     [rbp+0B0h+var_100], 3F800000h
0x18018a75d  mov     r8, rax
0x18018a760  mov     edx, 10h
0x18018a765  lea     rcx, [rbp+0B0h+var_E8]
0x18018a769  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18018a76e  mov     [rsp+1B0h+var_16F], 1
0x18018a773  mov     rax, [rsi]
0x18018a776  mov     edx, r12d
0x18018a779  mov     rcx, rsi
0x18018a77c  mov     rax, [rax+78h]
0x18018a780  call    cs:__guard_dispatch_icall_fptr
0x18018a786  mov     bl, al
0x18018a788  mov     [rsp+1B0h+var_170], al
0x18018a78c  mov     rcx, [rsi]
0x18018a78f  mov     rax, [rcx+1B8h]
0x18018a796  mov     edx, r12d
0x18018a799  mov     rcx, rsi
0x18018a79c  call    cs:__guard_dispatch_icall_fptr
0x18018a7a2  test    al, al
0x18018a7a4  jz      short loc_18018A7D4
0x18018a7a6  lea     rcx, [rbp+0B0h+var_100]
0x18018a7aa  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18018a7af  mov     rcx, [rsp+1B0h+var_168]
0x18018a7b4  test    rcx, rcx
0x18018a7b7  jz      loc_18018AB5D
0x18018a7bd  mov     [rsp+1B0h+var_168], rdi
0x18018a7c2  mov     rax, [rcx]
0x18018a7c5  mov     rax, [rax+10h]
0x18018a7c9  call    cs:__guard_dispatch_icall_fptr
0x18018a7cf  jmp     loc_18018AB5D
0x18018a7d4  xorps   xmm0, xmm0
0x18018a7d7  movups  [rbp+0B0h+var_68], xmm0
0x18018a7db  movdqu  [rbp+0B0h+var_58], xmm6
0x18018a7e0  mov     word ptr [rbp+0B0h+var_68], di
0x18018a7e4  mov     [rsp+1B0h+var_150], rdi
0x18018a7e9  mov     [rsp+1B0h+var_148], edi
0x18018a7ed  mov     [rsp+1B0h+var_144], 80000000h
0x18018a7f5  mov     [rsp+1B0h+var_140], rdi
0x18018a7fa  mov     [rsp+1B0h+var_138], edi
0x18018a7fe  mov     [rsp+1B0h+var_134], 80000000h
0x18018a806  mov     [rbp+0B0h+var_130], rdi
0x18018a80a  mov     [rbp+0B0h+var_128], edi
0x18018a80d  mov     [rbp+0B0h+var_124], 80000000h
0x18018a814  mov     [rsp+1B0h+var_16C], edi
0x18018a818  mov     rax, [rsi]
0x18018a81b  test    bl, bl
0x18018a81d  jz      loc_18018A963
0x18018a823  lea     r8, [rbp+0B0h+var_68]
0x18018a827  mov     edx, r12d
0x18018a82a  mov     rcx, rsi
0x18018a82d  mov     rax, [rax+50h]
0x18018a831  call    cs:__guard_dispatch_icall_fptr
0x18018a837  test    eax, eax
0x18018a839  jns     short loc_18018A849
0x18018a83b  lea     rcx, [rbp+0B0h+var_68]
0x18018a83f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018a844  jmp     loc_18018A7A6
0x18018a849  mov     rax, [rsi]
0x18018a84c  lea     rcx, [rsp+1B0h+var_16C]
0x18018a851  mov     [rsp+1B0h+var_188], rcx
0x18018a856  mov     [rsp+1B0h+var_190], rdi
0x18018a85b  xor     r9d, r9d
0x18018a85e  xor     r8d, r8d
0x18018a861  lea     rdx, [rbp+0B0h+var_68]
0x18018a865  mov     rcx, rsi
0x18018a868  mov     rax, [rax+118h]
0x18018a86f  call    cs:__guard_dispatch_icall_fptr
0x18018a875  test    al, al
0x18018a877  jz      short loc_18018A83B
0x18018a879  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018a87e  test    r9d, r9d
0x18018a881  jz      short loc_18018A83B
0x18018a883  mov     [rsp+1B0h+var_188], r14; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018a888  mov     [rsp+1B0h+var_190], r15; void (*)(unsigned __int8 *, unsigned int)
0x18018a88d  xor     r8d, r8d; unsigned int
0x18018a890  lea     edx, [r8+4]; unsigned int
0x18018a894  lea     rcx, [rsp+1B0h+var_150]; this
0x18018a899  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018a89e  mov     [rsp+1B0h+var_188], r13; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018a8a3  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018a8aa  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018a8af  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018a8b4  xor     r8d, r8d; unsigned int
0x18018a8b7  lea     edx, [r8+4]; unsigned int
0x18018a8bb  lea     rcx, [rsp+1B0h+var_140]; this
0x18018a8c0  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018a8c5  lea     rax, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018a8cc  mov     [rsp+1B0h+var_188], rax; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018a8d1  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018a8d8  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018a8dd  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018a8e2  xor     r8d, r8d; unsigned int
0x18018a8e5  lea     edx, [r8+4]; unsigned int
0x18018a8e9  lea     rcx, [rbp+0B0h+var_130]; this
0x18018a8ed  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018a8f2  mov     rax, [rsi]
0x18018a8f5  lea     rcx, [rsp+1B0h+var_16C]
0x18018a8fa  mov     [rsp+1B0h+var_188], rcx
0x18018a8ff  mov     r14, [rbp+0B0h+var_130]
0x18018a903  mov     [rsp+1B0h+var_190], r14
0x18018a908  mov     r13, [rsp+1B0h+var_140]
0x18018a90d  mov     r9, r13
0x18018a910  mov     r15, [rsp+1B0h+var_150]
0x18018a915  mov     r8, r15
0x18018a918  lea     rdx, [rbp+0B0h+var_68]
0x18018a91c  mov     rcx, rsi
0x18018a91f  mov     rax, [rax+118h]
0x18018a926  call    cs:__guard_dispatch_icall_fptr
0x18018a92c  test    al, al
0x18018a92e  jnz     loc_18018AA42
0x18018a934  test    r14, r14
0x18018a937  jz      short loc_18018A943
0x18018a939  mov     rcx, r14
0x18018a93c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018a942  nop
0x18018a943  test    r13, r13
0x18018a946  jz      short loc_18018A952
0x18018a948  mov     rcx, r13
0x18018a94b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018a951  nop
0x18018a952  test    r15, r15
0x18018a955  jz      loc_18018AB1A
0x18018a95b  mov     rcx, r15
0x18018a95e  jmp     loc_18018AB13
0x18018a963  mov     rbx, [rax+20h]
0x18018a967  mov     rcx, [rsp+1B0h+var_168]
0x18018a96c  test    rcx, rcx
0x18018a96f  jz      short loc_18018A983
0x18018a971  mov     [rsp+1B0h+var_168], rdi
0x18018a976  mov     rdx, [rcx]
0x18018a979  mov     rax, [rdx+10h]
0x18018a97d  call    cs:__guard_dispatch_icall_fptr
0x18018a983  lea     r8, [rsp+1B0h+var_168]
0x18018a988  mov     edx, r12d
0x18018a98b  mov     rcx, rsi
0x18018a98e  mov     rax, rbx
0x18018a991  call    cs:__guard_dispatch_icall_fptr
0x18018a997  test    eax, eax
0x18018a999  js      loc_18018A83B
0x18018a99f  mov     rcx, [rsp+1B0h+var_168]
0x18018a9a4  test    rcx, rcx
0x18018a9a7  jz      loc_18018AF96
0x18018a9ad  mov     rax, [rcx]
0x18018a9b0  mov     rax, [rax+20h]
0x18018a9b4  call    cs:__guard_dispatch_icall_fptr
0x18018a9ba  mov     [rsp+1B0h+var_16C], eax
0x18018a9be  mov     [rsp+1B0h+var_188], r14; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018a9c3  mov     [rsp+1B0h+var_190], r15; void (*)(unsigned __int8 *, unsigned int)
0x18018a9c8  mov     r9d, eax; unsigned int
0x18018a9cb  xor     r8d, r8d; unsigned int
0x18018a9ce  lea     edx, [r8+4]; unsigned int
0x18018a9d2  lea     rcx, [rsp+1B0h+var_150]; this
0x18018a9d7  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018a9dc  mov     [rsp+1B0h+var_188], r13; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018a9e1  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018a9e8  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018a9ed  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018a9f2  xor     r8d, r8d; unsigned int
0x18018a9f5  lea     edx, [r8+4]; unsigned int
0x18018a9f9  lea     rcx, [rsp+1B0h+var_140]; this
0x18018a9fe  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018aa03  lea     rax, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018aa0a  mov     [rsp+1B0h+var_188], rax; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018aa0f  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018aa16  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018aa1b  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018aa20  xor     r8d, r8d; unsigned int
0x18018aa23  lea     edx, [r8+4]; unsigned int
0x18018aa27  lea     rcx, [rbp+0B0h+var_130]; this
0x18018aa2b  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018aa30  mov     r13, [rsp+1B0h+var_140]
0x18018aa35  mov     r14, [rbp+0B0h+var_130]
0x18018aa39  mov     r15, [rsp+1B0h+var_150]
0x18018aa3e  mov     bl, [rsp+1B0h+var_170]
0x18018aa42  xor     eax, eax
0x18018aa44  cmp     [rsp+1B0h+var_16C], eax
0x18018aa48  jbe     loc_18018AAE9
0x18018aa4e  xorps   xmm0, xmm0
0x18018aa51  movups  [rbp+0B0h+var_88], xmm0
0x18018aa55  movdqu  [rbp+0B0h+var_78], xmm6
0x18018aa5a  mov     word ptr [rbp+0B0h+var_88], ax
0x18018aa5e  mov     [rbp+0B0h+var_B8], rax
0x18018aa62  test    bl, bl
0x18018aa64  jz      loc_18018ABC8
0x18018aa6a  mov     rax, [rsi]
0x18018aa6d  cmp     edi, [rbp+0B0h+var_128]
0x18018aa70  jnb     loc_18018AF50
0x18018aa76  mov     ebx, edi
0x18018aa78  shl     rbx, 2
0x18018aa7c  lea     rcx, [rbx+r14]
0x18018aa80  cmp     edi, [rsp+1B0h+var_138]
0x18018aa84  jnb     loc_18018AF3C
0x18018aa8a  lea     r9, [rbx+r13]
0x18018aa8e  cmp     edi, [rsp+1B0h+var_148]
0x18018aa92  jnb     loc_18018AF2E
0x18018aa98  lea     r8, [rbx+r15]
0x18018aa9c  lea     rdx, [rbp+0B0h+var_88]
0x18018aaa0  mov     [rsp+1B0h+var_188], rdx
0x18018aaa5  mov     [rsp+1B0h+var_190], rcx
0x18018aaaa  lea     rdx, [rbp+0B0h+var_68]
0x18018aaae  mov     rcx, rsi
0x18018aab1  mov     rax, [rax+158h]
0x18018aab8  call    cs:__guard_dispatch_icall_fptr
0x18018aabe  test    al, al
0x18018aac0  jnz     loc_18018ACEE
0x18018aac6  lea     rcx, [rbp+0B0h+var_88]
0x18018aaca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018aacf  mov     bl, [rsp+1B0h+var_170]
0x18018aad3  inc     edi
0x18018aad5  cmp     edi, [rsp+1B0h+var_16C]
0x18018aad9  mov     r15, [rsp+1B0h+var_150]
0x18018aade  mov     eax, 0
0x18018aae3  jb      loc_18018AA4E
0x18018aae9  xor     edi, edi
0x18018aaeb  test    r14, r14
0x18018aaee  jz      short loc_18018AAFA
0x18018aaf0  mov     rcx, r14
0x18018aaf3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018aaf9  nop
0x18018aafa  test    r13, r13
0x18018aafd  jz      short loc_18018AB09
0x18018aaff  mov     rcx, r13
0x18018ab02  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018ab08  nop
0x18018ab09  mov     rcx, [rsp+1B0h+var_150]
0x18018ab0e  test    rcx, rcx
0x18018ab11  jz      short loc_18018AB1A
0x18018ab13  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018ab19  nop
0x18018ab1a  lea     rcx, [rbp+0B0h+var_68]
0x18018ab1e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018ab23  lea     rcx, [rbp+0B0h+var_100]
0x18018ab27  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
  ... truncated ...
```
