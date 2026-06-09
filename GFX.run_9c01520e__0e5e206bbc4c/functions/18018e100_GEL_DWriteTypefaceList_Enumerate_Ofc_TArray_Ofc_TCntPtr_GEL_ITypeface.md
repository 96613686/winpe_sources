# GEL::DWriteTypefaceList::Enumerate(Ofc::TArray<Ofc::TCntPtr<GEL::ITypeface>> &)

- ea: `0x18018e100`
- end: `0x18018ea74`
- name: `?Enumerate@DWriteTypefaceList@GEL@@EEAAXAEAV?$TArray@V?$TCntPtr@UITypeface@GEL@@@Ofc@@@Ofc@@@Z`
- size: `2420`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x1800219e8`
- `0x1800267b0`
- `0x180056390`
- `0x1800569ec`
- `0x1800578b0`
- `0x180057e70`
- `0x180072d00`
- `0x1800776b4`
- `0x180077780`
- `0x1800961a0`
- `0x1800f7108`
- `0x18015ca44`
- `0x18015caa4`
- `0x18015cea4`
- `0x180166fb0`
- `0x180172f10`
- `0x180172fb0`
- `0x180176384`
- `0x1801834bc`
- `0x18018e100`
- `0x18018ebe8`

## import_xrefs

- `Mso98Win32Client!__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ` at `0x18018e179`
- `Mso98Win32Client!__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ` at `0x18018e179`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018e17f`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018e17f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea27`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea35`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea43`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea5f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea6d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea27`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea35`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea43`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea5f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018ea6d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e40c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e41b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5c3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5d2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5e3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e40c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e41b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5c3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5d2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018e5e3`

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
          JUMPOUT(0x18018EA73LL);
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
            v44 = sub_18018EBE8(v43, v42) | 2;
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
0x18018e100  mov     rax, rsp
0x18018e103  mov     [rax+18h], rbx
0x18018e107  push    rbp
0x18018e108  push    rsi
0x18018e109  push    rdi
0x18018e10a  push    r12
0x18018e10c  push    r13
0x18018e10e  push    r14
0x18018e110  push    r15
0x18018e112  lea     rbp, [rsp-80h]
0x18018e117  sub     rsp, 180h
0x18018e11e  movaps  xmmword ptr [rax-48h], xmm6
0x18018e122  mov     rax, cs:__security_cookie
0x18018e129  xor     rax, rsp
0x18018e12c  mov     [rbp+0B0h+var_48], rax
0x18018e130  mov     rbx, rdx
0x18018e133  mov     [rbp+0B0h+var_110], rdx
0x18018e137  mov     [rbp+0B0h+var_C0], rcx
0x18018e13b  lea     rax, aStartedEnumera; "Started enumerating Typefaces."
0x18018e142  mov     [rsp+1B0h+var_160], rax
0x18018e147  mov     r9d, 2
0x18018e14d  lea     rax, [rsp+1B0h+var_160]
0x18018e152  mov     [rsp+1B0h+var_190], rax
0x18018e157  mov     edx, 0ADh
0x18018e15c  mov     ecx, 70635Fh
0x18018e161  lea     r8d, [r9+30h]
0x18018e165  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18018e16a  lea     rdx, ?Do@?$TDestructRange@V?$TCntPtr@UIFigurePrimitive@Gfx@@@Ofc@@$0A@@Ofc@@SAXPEAEK@Z; void (*)(unsigned __int8 *, unsigned int)
0x18018e171  mov     rcx, rbx; this
0x18018e174  call    ?Reset@CArrayImpl@Ofc@@IEAAXP6AXPEAEK@Z@Z; Ofc::CArrayImpl::Reset(void (*)(uchar *,ulong))
0x18018e179  call    cs:__imp_?InitializeCustomFontAssetLibrary@CustomFontOAL@Mso@@YAXXZ; Mso::CustomFontOAL::InitializeCustomFontAssetLibrary(void)
0x18018e17f  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018e185  mov     rcx, rax; this
0x18018e188  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018e18d  mov     rsi, rax
0x18018e190  mov     rcx, [rax]
0x18018e193  mov     rax, [rcx+18h]
0x18018e197  mov     rcx, rsi
0x18018e19a  call    cs:__guard_dispatch_icall_fptr
0x18018e1a0  mov     [rbp+0B0h+var_120], eax
0x18018e1a3  xor     edi, edi
0x18018e1a5  mov     r12d, edi
0x18018e1a8  mov     [rsp+1B0h+var_158], edi
0x18018e1ac  test    eax, eax
0x18018e1ae  jz      loc_18018E63F
0x18018e1b4  lea     rax, [rbp+0B0h+var_F8]
0x18018e1b8  mov     [rbp+0B0h+var_A8], rax
0x18018e1bc  lea     r14, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018e1c3  lea     r15, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018e1ca  lea     r13, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018e1d1  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18018e1d9  mov     [rsp+1B0h+var_168], rdi
0x18018e1de  mov     [rbp+0B0h+var_100], 0
0x18018e1e5  mov     [rbp+0B0h+var_F8], rdi
0x18018e1e9  mov     [rbp+0B0h+var_F0], rdi
0x18018e1ed  mov     ecx, 1
0x18018e1f2  call    ??$_Get_size_of_n@$0DA@@std@@YA_K_K@Z; std::_Get_size_of_n<48>(unsigned __int64)
0x18018e1f7  mov     rcx, rax
0x18018e1fa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18018e1ff  mov     [rax], rax
0x18018e202  mov     [rax+8], rax
0x18018e206  mov     [rbp+0B0h+var_F8], rax
0x18018e20a  mov     [rbp+0B0h+var_E8], rdi
0x18018e20e  xorps   xmm0, xmm0
0x18018e211  movdqa  [rbp+0B0h+var_E0], xmm0
0x18018e216  mov     [rbp+0B0h+var_D0], 7
0x18018e21e  mov     [rbp+0B0h+var_C8], 8
0x18018e226  mov     [rbp+0B0h+var_100], 3F800000h
0x18018e22d  mov     r8, rax
0x18018e230  mov     edx, 10h
0x18018e235  lea     rcx, [rbp+0B0h+var_E8]
0x18018e239  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18018e23e  mov     [rsp+1B0h+var_16F], 1
0x18018e243  mov     rax, [rsi]
0x18018e246  mov     edx, r12d
0x18018e249  mov     rcx, rsi
0x18018e24c  mov     rax, [rax+78h]
0x18018e250  call    cs:__guard_dispatch_icall_fptr
0x18018e256  mov     bl, al
0x18018e258  mov     [rsp+1B0h+var_170], al
0x18018e25c  mov     rcx, [rsi]
0x18018e25f  mov     rax, [rcx+1B8h]
0x18018e266  mov     edx, r12d
0x18018e269  mov     rcx, rsi
0x18018e26c  call    cs:__guard_dispatch_icall_fptr
0x18018e272  test    al, al
0x18018e274  jz      short loc_18018E2A4
0x18018e276  lea     rcx, [rbp+0B0h+var_100]
0x18018e27a  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18018e27f  mov     rcx, [rsp+1B0h+var_168]
0x18018e284  test    rcx, rcx
0x18018e287  jz      loc_18018E62D
0x18018e28d  mov     [rsp+1B0h+var_168], rdi
0x18018e292  mov     rax, [rcx]
0x18018e295  mov     rax, [rax+10h]
0x18018e299  call    cs:__guard_dispatch_icall_fptr
0x18018e29f  jmp     loc_18018E62D
0x18018e2a4  xorps   xmm0, xmm0
0x18018e2a7  movups  [rbp+0B0h+var_68], xmm0
0x18018e2ab  movdqu  [rbp+0B0h+var_58], xmm6
0x18018e2b0  mov     word ptr [rbp+0B0h+var_68], di
0x18018e2b4  mov     [rsp+1B0h+var_150], rdi
0x18018e2b9  mov     [rsp+1B0h+var_148], edi
0x18018e2bd  mov     [rsp+1B0h+var_144], 80000000h
0x18018e2c5  mov     [rsp+1B0h+var_140], rdi
0x18018e2ca  mov     [rsp+1B0h+var_138], edi
0x18018e2ce  mov     [rsp+1B0h+var_134], 80000000h
0x18018e2d6  mov     [rbp+0B0h+var_130], rdi
0x18018e2da  mov     [rbp+0B0h+var_128], edi
0x18018e2dd  mov     [rbp+0B0h+var_124], 80000000h
0x18018e2e4  mov     [rsp+1B0h+var_16C], edi
0x18018e2e8  mov     rax, [rsi]
0x18018e2eb  test    bl, bl
0x18018e2ed  jz      loc_18018E433
0x18018e2f3  lea     r8, [rbp+0B0h+var_68]
0x18018e2f7  mov     edx, r12d
0x18018e2fa  mov     rcx, rsi
0x18018e2fd  mov     rax, [rax+50h]
0x18018e301  call    cs:__guard_dispatch_icall_fptr
0x18018e307  test    eax, eax
0x18018e309  jns     short loc_18018E319
0x18018e30b  lea     rcx, [rbp+0B0h+var_68]
0x18018e30f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018e314  jmp     loc_18018E276
0x18018e319  mov     rax, [rsi]
0x18018e31c  lea     rcx, [rsp+1B0h+var_16C]
0x18018e321  mov     [rsp+1B0h+var_188], rcx
0x18018e326  mov     [rsp+1B0h+var_190], rdi
0x18018e32b  xor     r9d, r9d
0x18018e32e  xor     r8d, r8d
0x18018e331  lea     rdx, [rbp+0B0h+var_68]
0x18018e335  mov     rcx, rsi
0x18018e338  mov     rax, [rax+118h]
0x18018e33f  call    cs:__guard_dispatch_icall_fptr
0x18018e345  test    al, al
0x18018e347  jz      short loc_18018E30B
0x18018e349  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018e34e  test    r9d, r9d
0x18018e351  jz      short loc_18018E30B
0x18018e353  mov     [rsp+1B0h+var_188], r14; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e358  mov     [rsp+1B0h+var_190], r15; void (*)(unsigned __int8 *, unsigned int)
0x18018e35d  xor     r8d, r8d; unsigned int
0x18018e360  lea     edx, [r8+4]; unsigned int
0x18018e364  lea     rcx, [rsp+1B0h+var_150]; this
0x18018e369  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e36e  mov     [rsp+1B0h+var_188], r13; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e373  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018e37a  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018e37f  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018e384  xor     r8d, r8d; unsigned int
0x18018e387  lea     edx, [r8+4]; unsigned int
0x18018e38b  lea     rcx, [rsp+1B0h+var_140]; this
0x18018e390  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e395  lea     rax, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018e39c  mov     [rsp+1B0h+var_188], rax; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e3a1  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018e3a8  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018e3ad  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018e3b2  xor     r8d, r8d; unsigned int
0x18018e3b5  lea     edx, [r8+4]; unsigned int
0x18018e3b9  lea     rcx, [rbp+0B0h+var_130]; this
0x18018e3bd  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e3c2  mov     rax, [rsi]
0x18018e3c5  lea     rcx, [rsp+1B0h+var_16C]
0x18018e3ca  mov     [rsp+1B0h+var_188], rcx
0x18018e3cf  mov     r14, [rbp+0B0h+var_130]
0x18018e3d3  mov     [rsp+1B0h+var_190], r14
0x18018e3d8  mov     r13, [rsp+1B0h+var_140]
0x18018e3dd  mov     r9, r13
0x18018e3e0  mov     r15, [rsp+1B0h+var_150]
0x18018e3e5  mov     r8, r15
0x18018e3e8  lea     rdx, [rbp+0B0h+var_68]
0x18018e3ec  mov     rcx, rsi
0x18018e3ef  mov     rax, [rax+118h]
0x18018e3f6  call    cs:__guard_dispatch_icall_fptr
0x18018e3fc  test    al, al
0x18018e3fe  jnz     loc_18018E512
0x18018e404  test    r14, r14
0x18018e407  jz      short loc_18018E413
0x18018e409  mov     rcx, r14
0x18018e40c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018e412  nop
0x18018e413  test    r13, r13
0x18018e416  jz      short loc_18018E422
0x18018e418  mov     rcx, r13
0x18018e41b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018e421  nop
0x18018e422  test    r15, r15
0x18018e425  jz      loc_18018E5EA
0x18018e42b  mov     rcx, r15
0x18018e42e  jmp     loc_18018E5E3
0x18018e433  mov     rbx, [rax+20h]
0x18018e437  mov     rcx, [rsp+1B0h+var_168]
0x18018e43c  test    rcx, rcx
0x18018e43f  jz      short loc_18018E453
0x18018e441  mov     [rsp+1B0h+var_168], rdi
0x18018e446  mov     rdx, [rcx]
0x18018e449  mov     rax, [rdx+10h]
0x18018e44d  call    cs:__guard_dispatch_icall_fptr
0x18018e453  lea     r8, [rsp+1B0h+var_168]
0x18018e458  mov     edx, r12d
0x18018e45b  mov     rcx, rsi
0x18018e45e  mov     rax, rbx
0x18018e461  call    cs:__guard_dispatch_icall_fptr
0x18018e467  test    eax, eax
0x18018e469  js      loc_18018E30B
0x18018e46f  mov     rcx, [rsp+1B0h+var_168]
0x18018e474  test    rcx, rcx
0x18018e477  jz      loc_18018EA66
0x18018e47d  mov     rax, [rcx]
0x18018e480  mov     rax, [rax+20h]
0x18018e484  call    cs:__guard_dispatch_icall_fptr
0x18018e48a  mov     [rsp+1B0h+var_16C], eax
0x18018e48e  mov     [rsp+1B0h+var_188], r14; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e493  mov     [rsp+1B0h+var_190], r15; void (*)(unsigned __int8 *, unsigned int)
0x18018e498  mov     r9d, eax; unsigned int
0x18018e49b  xor     r8d, r8d; unsigned int
0x18018e49e  lea     edx, [r8+4]; unsigned int
0x18018e4a2  lea     rcx, [rsp+1B0h+var_150]; this
0x18018e4a7  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e4ac  mov     [rsp+1B0h+var_188], r13; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e4b1  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018e4b8  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018e4bd  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018e4c2  xor     r8d, r8d; unsigned int
0x18018e4c5  lea     edx, [r8+4]; unsigned int
0x18018e4c9  lea     rcx, [rsp+1B0h+var_140]; this
0x18018e4ce  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e4d3  lea     rax, ?Do@?$TMoveConstructRange@W4DWRITE_FONT_STYLE@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<DWRITE_FONT_STYLE,1>::Do(uchar *,uchar *,ulong)
0x18018e4da  mov     [rsp+1B0h+var_188], rax; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18018e4df  lea     rax, ?Do@?$TDefaultConstructRange@W4DWRITE_FONT_STYLE@@$00$00@Ofc@@SAXPEAEK@Z; Ofc::TDefaultConstructRange<DWRITE_FONT_STYLE,1,1>::Do(uchar *,ulong)
0x18018e4e6  mov     [rsp+1B0h+var_190], rax; void (*)(unsigned __int8 *, unsigned int)
0x18018e4eb  mov     r9d, [rsp+1B0h+var_16C]; unsigned int
0x18018e4f0  xor     r8d, r8d; unsigned int
0x18018e4f3  lea     edx, [r8+4]; unsigned int
0x18018e4f7  lea     rcx, [rbp+0B0h+var_130]; this
0x18018e4fb  call    ?NewAt@CArrayImpl@Ofc@@IEAAPEAXKKKP6AXPEAEK@ZP6AX00K@Z@Z; Ofc::CArrayImpl::NewAt(ulong,ulong,ulong,void (*)(uchar *,ulong),void (*)(uchar *,uchar *,ulong))
0x18018e500  mov     r13, [rsp+1B0h+var_140]
0x18018e505  mov     r14, [rbp+0B0h+var_130]
0x18018e509  mov     r15, [rsp+1B0h+var_150]
0x18018e50e  mov     bl, [rsp+1B0h+var_170]
0x18018e512  xor     eax, eax
0x18018e514  cmp     [rsp+1B0h+var_16C], eax
0x18018e518  jbe     loc_18018E5B9
0x18018e51e  xorps   xmm0, xmm0
0x18018e521  movups  [rbp+0B0h+var_88], xmm0
0x18018e525  movdqu  [rbp+0B0h+var_78], xmm6
0x18018e52a  mov     word ptr [rbp+0B0h+var_88], ax
0x18018e52e  mov     [rbp+0B0h+var_B8], rax
0x18018e532  test    bl, bl
0x18018e534  jz      loc_18018E698
0x18018e53a  mov     rax, [rsi]
0x18018e53d  cmp     edi, [rbp+0B0h+var_128]
0x18018e540  jnb     loc_18018EA20
0x18018e546  mov     ebx, edi
0x18018e548  shl     rbx, 2
0x18018e54c  lea     rcx, [rbx+r14]
0x18018e550  cmp     edi, [rsp+1B0h+var_138]
0x18018e554  jnb     loc_18018EA0C
0x18018e55a  lea     r9, [rbx+r13]
0x18018e55e  cmp     edi, [rsp+1B0h+var_148]
0x18018e562  jnb     loc_18018E9FE
0x18018e568  lea     r8, [rbx+r15]
0x18018e56c  lea     rdx, [rbp+0B0h+var_88]
0x18018e570  mov     [rsp+1B0h+var_188], rdx
0x18018e575  mov     [rsp+1B0h+var_190], rcx
0x18018e57a  lea     rdx, [rbp+0B0h+var_68]
0x18018e57e  mov     rcx, rsi
0x18018e581  mov     rax, [rax+158h]
0x18018e588  call    cs:__guard_dispatch_icall_fptr
0x18018e58e  test    al, al
0x18018e590  jnz     loc_18018E7BE
0x18018e596  lea     rcx, [rbp+0B0h+var_88]
0x18018e59a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018e59f  mov     bl, [rsp+1B0h+var_170]
0x18018e5a3  inc     edi
0x18018e5a5  cmp     edi, [rsp+1B0h+var_16C]
0x18018e5a9  mov     r15, [rsp+1B0h+var_150]
0x18018e5ae  mov     eax, 0
0x18018e5b3  jb      loc_18018E51E
0x18018e5b9  xor     edi, edi
0x18018e5bb  test    r14, r14
0x18018e5be  jz      short loc_18018E5CA
0x18018e5c0  mov     rcx, r14
0x18018e5c3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018e5c9  nop
0x18018e5ca  test    r13, r13
0x18018e5cd  jz      short loc_18018E5D9
0x18018e5cf  mov     rcx, r13
0x18018e5d2  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018e5d8  nop
0x18018e5d9  mov     rcx, [rsp+1B0h+var_150]
0x18018e5de  test    rcx, rcx
0x18018e5e1  jz      short loc_18018E5EA
0x18018e5e3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18018e5e9  nop
0x18018e5ea  lea     rcx, [rbp+0B0h+var_68]
0x18018e5ee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018e5f3  lea     rcx, [rbp+0B0h+var_100]
0x18018e5f7  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
  ... truncated ...
```
