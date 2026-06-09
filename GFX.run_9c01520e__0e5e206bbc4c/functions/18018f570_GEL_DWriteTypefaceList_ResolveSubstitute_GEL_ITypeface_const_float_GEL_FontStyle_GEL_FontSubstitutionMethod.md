# GEL::DWriteTypefaceList::ResolveSubstitute(GEL::ITypeface const &,float,GEL::FontStyle,GEL::FontSubstitutionMethod &)

- ea: `0x18018f570`
- end: `0x18018fb7c`
- name: `?ResolveSubstitute@DWriteTypefaceList@GEL@@UEBA?AV?$TCntPtr@$$CBUITypeface@GEL@@@Ofc@@AEBUITypeface@2@MW4FontStyle@2@AEAW4FontSubstitutionMethod@2@@Z`
- size: `1548`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x180076df0`
- `0x180090370`
- `0x1800fab40`
- `0x1800fbdb4`
- `0x18010fbec`
- `0x180166fb0`
- `0x1801764cc`
- `0x18018f570`
- `0x1801b2a90`
- `0x180205d64`
- `0x180205d98`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18018fb49`
- `MSVCP140!_Mtx_unlock` at `0x18018fb49`
- `MSO!__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ` at `0x18018f664`
- `MSO!__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ` at `0x18018f664`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018f6f2`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018f961`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018f6f2`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018f961`
- `mso40uiWin32Client!__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z` at `0x18018f6e9`
- `mso40uiWin32Client!__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z` at `0x18018f6e9`
- `Mso30Win32Client!__imp_?MsoFsCpgFromCpg@@YAHH@Z` at `0x18018f87f`
- `Mso30Win32Client!__imp_?MsoFsCpgFromCpg@@YAHH@Z` at `0x18018f87f`
- `Mso30Win32Client!__imp_MsoCpgFromChs` at `0x18018f877`
- `Mso30Win32Client!__imp_MsoCpgFromChs` at `0x18018f877`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18018f600`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18018f600`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018fb2c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018fb2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GEL::DWriteTypefaceList::ResolveSubstitute(
        __int64 a1,
        _QWORD *a2,
        GEL::Typeface *a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6)
{
  _QWORD *v7; // r15
  __int64 v8; // r14
  _DWORD *v9; // r13
  struct _Mtx_internal_imp_t *v10; // rbx
  __int64 v11; // rsi
  Mso::FontSubstitution *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rsi
  char *v16; // r12
  void (__fastcall ***PanoseMatch)(_QWORD); // rdx
  unsigned int v18; // r8d
  Mso::DWriteAssistant *v19; // rcx
  const wchar_t *FontSubstitute; // rdi
  Mso::DWriteAssistant *v21; // rcx
  Mso::DWriteAssistant::ResourceManager *v22; // rax
  struct Mso::DWriteAssistant::IFontCollection *v23; // rax
  struct GEL::ITypefaceList *v24; // rax
  __int64 v25; // r9
  GEL::Typeface *v26; // r12
  unsigned __int8 v27; // di
  Mso::DWriteAssistant *v28; // rcx
  __int64 v29; // rbx
  unsigned int i; // r13d
  __int64 v31; // rax
  GEL::Typeface *v32; // r14
  __int64 v33; // rdi
  int v34; // eax
  int v35; // edi
  Ofc::CStr *v36; // rax
  Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  struct Mso::DWriteAssistant::IFontCollection *FontCollection; // rax
  struct GEL::ITypefaceList *DefaultTypefaces; // rax
  __int64 v40; // r9
  __int64 *v41; // rax
  __int64 v42; // rdi
  Ofc::CStr *v43; // rax
  Ofc::CStr *v44; // rax
  Ofc::CStr *v45; // rax
  bool v46; // r8
  Ofc::CStr *v47; // rax
  bool v48; // r8
  __int64 v49; // rax
  int v51; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v52; // [rsp+40h] [rbp-C0h]
  char v53; // [rsp+41h] [rbp-BFh]
  int v54; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B8h] BYREF
  int v56; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v58; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h]
  char *v60; // [rsp+68h] [rbp-98h]
  struct _Mtx_internal_imp_t *v61; // [rsp+78h] [rbp-88h]
  _QWORD *v62; // [rsp+80h] [rbp-80h]
  _BYTE v63[544]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a2;
  v62 = a2;
  v8 = a1;
  v59 = a1;
  v60 = (char *)a2;
  v9 = a6;
  v58 = a6;
  v10 = (struct _Mtx_internal_imp_t *)(a1 + 16);
  v61 = (struct _Mtx_internal_imp_t *)(a1 + 16);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 16));
  v11 = -1;
  *a6 = -1;
  v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 40LL))(v8);
  if ( !v55 )
  {
    MsoShipAssertTagProc(3720792);
    *a6 = 0;
    *v7 = a3;
    if ( a3 )
      (**(void (__fastcall ***)(GEL::Typeface *))a3)(a3);
    goto LABEL_64;
  }
  v57 = (*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)a3 + 16LL))(a3);
  v52 = GEL::Typeface::Chs(a3);
  v53 = (*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)a3 + 104LL))(a3);
  v60 = (char *)a3 + 88;
  if ( Mso::FontSubstitution::IsFontSubstitutionFeatureGateEnabled(v12) )
  {
    GEL::TypefaceList::ResolveSubstitute(v8, &v57, a3, (char *)a3 + 88, a6);
    v15 = 0;
    if ( v57 )
    {
      *v7 = v57;
      v57 = 0;
      goto LABEL_64;
    }
LABEL_17:
    v26 = 0;
    v54 = 0;
    *a6 = 3;
    LOBYTE(v14) = v53;
    v27 = v52;
    LOBYTE(v13) = v52;
    GEL::GetGDICompatibleSubstitute(v63, v13, v14);
    if ( v55 )
    {
      v29 = v59;
      for ( i = 0; i < v55; ++i )
      {
        v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 32LL))(v29, i);
        v32 = (GEL::Typeface *)v31;
        if ( !*(_DWORD *)(v31 + 80) )
        {
          (**(void (__fastcall ***)(__int64))v31)(v31);
          (*(void (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 344LL))(v32);
          (*(void (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 8LL))(v32);
        }
        if ( (*(unsigned __int8 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 40LL))(v32)
          || (*(unsigned __int8 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 48LL))(v32) )
        {
          v33 = (*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 112LL))(v32);
          v34 = MsoCpgFromChs(v52);
          if ( (MsoFsCpgFromCpg(v34) & *(_DWORD *)(v33 + 16)) != 0 )
          {
            if ( GEL::Typeface::Chs(v32) != 2 || v15 )
            {
              if ( GEL::Typeface::Chs(v32) != 2 && !v26 )
                v26 = v32;
            }
            else
            {
              v15 = (__int64)v32;
            }
            v35 = 3;
            if ( v53 != (*(unsigned __int8 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 104LL))(v32) )
              v35 = 1;
            if ( v52 != 2
              || (v36 = (Ofc::CStr *)(*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 16LL))(v32),
                  Ofc::CStr::FEqual(v36, L"Wingdings", 0)) )
            {
              ++v35;
            }
            if ( v54 >= v35 )
            {
              if ( v54 == v35 )
              {
                v43 = (Ofc::CStr *)(*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 16LL))(v32);
                if ( Ofc::CStr::FEqual(v43, L"Arial", 1)
                  || (!v26
                   || (v44 = (Ofc::CStr *)(*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v26 + 16LL))(v26),
                       !Ofc::CStr::FEqual(v44, L"Arial", 1)))
                  && ((v45 = (Ofc::CStr *)(*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 16LL))(v32),
                       Ofc::CStr::FEqual(v45, (const struct Ofc::CStr *)v63, v46))
                   || (v47 = (Ofc::CStr *)(*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v32 + 24LL))(v32),
                       Ofc::CStr::FEqual(v47, (const struct Ofc::CStr *)v63, v48))) )
                {
                  v26 = v32;
                }
              }
            }
            else
            {
              if ( GEL::Typeface::Chs(v32) == 2 )
                v15 = (__int64)v32;
              else
                v26 = v32;
              v54 = v35;
            }
          }
        }
      }
      v10 = v61;
      v7 = v62;
      v9 = v58;
      v8 = v59;
      v27 = v52;
    }
    if ( v27 != 2 )
      v15 = (__int64)v26;
    if ( !v15 )
    {
      ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(v28);
      FontCollection = Mso::DWriteAssistant::ResourceManager::GetFontCollection(ResourceManagerInstance);
      v55 = 0;
      v56 = 0;
      if ( (*(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, const wchar_t *, int *, unsigned int *))(*(_QWORD *)FontCollection + 40LL))(
             FontCollection,
             L"Arial",
             &v56,
             &v55) >= 0
        && v55 )
      {
        *v9 = 4;
        DefaultTypefaces = GEL::ITypefaceList::GetDefaultTypefaces();
        LOBYTE(v51) = v53;
        LOBYTE(v40) = v27;
        v41 = (__int64 *)(*(__int64 (__fastcall **)(struct GEL::ITypefaceList *, _DWORD **, const wchar_t *, __int64, int, char *))(*(_QWORD *)DefaultTypefaces + 16LL))(
                           DefaultTypefaces,
                           &v58,
                           L"Arial",
                           v40,
                           v51,
                           v60);
        v42 = *v41;
        *v41 = 0;
        if ( v58 )
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v58 + 8LL))(v58);
        if ( v42 )
        {
          *v7 = v42;
          goto LABEL_64;
        }
      }
      else
      {
        v49 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, 0);
        v15 = v49;
        if ( !*(_DWORD *)(v49 + 80) )
        {
          *v9 = 5;
          (**(void (__fastcall ***)(__int64))v49)(v49);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 344LL))(v15);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( !v15 )
      {
        CrashWithRecovery(0x65568Au, 0);
        __debugbreak();
      }
    }
    *v7 = v15;
    (**(void (__fastcall ***)(__int64))v15)(v15);
    goto LABEL_64;
  }
  v16 = (char *)a3 + 88;
  PanoseMatch = (void (__fastcall ***)(_QWORD))GEL::TypefaceList::FindPanoseMatch(v8, (char *)a3 + 88, a5);
  if ( PanoseMatch )
  {
    *a6 = 1;
    *v7 = PanoseMatch;
    (**PanoseMatch)(PanoseMatch);
    goto LABEL_64;
  }
  v19 = *(Mso::DWriteAssistant **)v57;
  do
    ++v11;
  while ( *((_WORD *)v19 + v11) );
  FontSubstitute = Mso::DWriteAssistant::GetFontSubstitute(v19, (const wchar_t *)(unsigned int)v11, v18);
  v22 = Mso::DWriteAssistant::GetResourceManagerInstance(v21);
  v23 = Mso::DWriteAssistant::ResourceManager::GetFontCollection(v22);
  v15 = 0;
  v54 = 0;
  v56 = 0;
  if ( !FontSubstitute )
    goto LABEL_17;
  if ( (*(int (__fastcall **)(struct Mso::DWriteAssistant::IFontCollection *, const wchar_t *, int *, int *))(*(_QWORD *)v23 + 40LL))(
         v23,
         FontSubstitute,
         &v56,
         &v54) < 0 )
    goto LABEL_17;
  if ( !v54 )
    goto LABEL_17;
  v24 = GEL::ITypefaceList::GetDefaultTypefaces();
  LOBYTE(v25) = v52;
  (*(void (__fastcall **)(struct GEL::ITypefaceList *, __int64 *, const wchar_t *, __int64, char, char *))(*(_QWORD *)v24 + 16LL))(
    v24,
    &v57,
    FontSubstitute,
    v25,
    v53,
    v16);
  if ( !v57 )
    goto LABEL_17;
  *a6 = 2;
  Ofc::TCntPtr<GEL::IFigure>::TCntPtr<GEL::IFigure>(v7, &v57);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
LABEL_64:
  _Mtx_unlock(v10);
  return v7;
}

```

## disassembly

```asm
0x18018f570  mov     [rsp-8+arg_18], rbx
0x18018f575  push    rbp
0x18018f576  push    rsi
0x18018f577  push    rdi
0x18018f578  push    r12
0x18018f57a  push    r13
0x18018f57c  push    r14
0x18018f57e  push    r15
0x18018f580  lea     rbp, [rsp-1C0h]
0x18018f588  sub     rsp, 2C0h
0x18018f58f  mov     rax, cs:__security_cookie
0x18018f596  xor     rax, rsp
0x18018f599  mov     [rbp+1F0h+var_40], rax
0x18018f5a0  mov     rdi, r8
0x18018f5a3  mov     r15, rdx
0x18018f5a6  mov     [rbp+1F0h+var_270], rdx
0x18018f5aa  mov     r14, rcx
0x18018f5ad  mov     [rsp+2F0h+var_290], rcx
0x18018f5b2  mov     [rsp+2F0h+var_288], rdx
0x18018f5b7  mov     r12d, [rbp+1F0h+arg_20]
0x18018f5be  mov     r13, [rbp+1F0h+arg_28]
0x18018f5c5  mov     [rsp+2F0h+var_298], r13
0x18018f5ca  lea     rbx, [rcx+10h]
0x18018f5ce  mov     [rsp+2F0h+var_278], rbx
0x18018f5d3  mov     rcx, rbx; this
0x18018f5d6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18018f5db  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18018f5df  mov     [r13+0], esi
0x18018f5e3  mov     rax, [r14]
0x18018f5e6  mov     rcx, r14
0x18018f5e9  mov     rax, [rax+28h]
0x18018f5ed  call    cs:__guard_dispatch_icall_fptr
0x18018f5f3  mov     [rsp+2F0h+var_2A8], eax
0x18018f5f7  test    eax, eax
0x18018f5f9  jnz     short loc_18018F626
0x18018f5fb  mov     ecx, 38C658h
0x18018f600  call    cs:__imp_MsoShipAssertTagProc
0x18018f606  xor     eax, eax
0x18018f608  mov     [r13+0], eax
0x18018f60c  mov     [r15], rdi
0x18018f60f  test    rdi, rdi
0x18018f612  jz      loc_18018FB46
0x18018f618  mov     rcx, [rdi]
0x18018f61b  mov     rax, [rcx]
0x18018f61e  mov     rcx, rdi
0x18018f621  jmp     loc_18018FB3F
0x18018f626  mov     rax, [rdi]
0x18018f629  mov     rcx, rdi
0x18018f62c  mov     rax, [rax+10h]
0x18018f630  call    cs:__guard_dispatch_icall_fptr
0x18018f636  mov     [rsp+2F0h+var_2A0], rax
0x18018f63b  mov     rcx, rdi; this
0x18018f63e  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018f643  mov     [rsp+2F0h+var_2B0], al
0x18018f647  mov     rcx, [rdi]
0x18018f64a  mov     rax, [rcx+68h]
0x18018f64e  mov     rcx, rdi
0x18018f651  call    cs:__guard_dispatch_icall_fptr
0x18018f657  mov     [rsp+2F0h+var_2AF], al
0x18018f65b  lea     rax, [rdi+58h]
0x18018f65f  mov     [rsp+2F0h+var_288], rax
0x18018f664  call    cs:__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ; Mso::FontSubstitution::IsFontSubstitutionFeatureGateEnabled(void)
0x18018f66a  mov     rcx, r14
0x18018f66d  test    al, al
0x18018f66f  jz      short loc_18018F6A4
0x18018f671  mov     [rsp+2F0h+var_2D0], r13
0x18018f676  lea     r9, [rdi+58h]
0x18018f67a  mov     r8, rdi
0x18018f67d  lea     rdx, [rsp+2F0h+var_2A0]
0x18018f682  call    ?ResolveSubstitute@TypefaceList@GEL@@QEBA?AV?$TCntPtr@$$CBUITypeface@GEL@@@Ofc@@AEBUITypeface@2@AEBUtagPANOSE@@AEAW4FontSubstitutionMethod@2@@Z; GEL::TypefaceList::ResolveSubstitute(GEL::ITypeface const &,tagPANOSE const &,GEL::FontSubstitutionMethod &)
0x18018f687  mov     rcx, [rsp+2F0h+var_2A0]
0x18018f68c  xor     esi, esi
0x18018f68e  test    rcx, rcx
0x18018f691  jz      loc_18018F7A5
0x18018f697  mov     [r15], rcx
0x18018f69a  mov     [rsp+2F0h+var_2A0], rsi
0x18018f69f  jmp     loc_18018FB46
0x18018f6a4  mov     r8d, r12d
0x18018f6a7  lea     r12, [rdi+58h]
0x18018f6ab  mov     rdx, r12
0x18018f6ae  call    ?FindPanoseMatch@TypefaceList@GEL@@QEBAPEBUITypeface@2@AEBUtagPANOSE@@W4FontStyle@2@@Z; GEL::TypefaceList::FindPanoseMatch(tagPANOSE const &,GEL::FontStyle)
0x18018f6b3  mov     rdx, rax
0x18018f6b6  xor     eax, eax
0x18018f6b8  test    rdx, rdx
0x18018f6bb  jz      short loc_18018F6D6
0x18018f6bd  mov     dword ptr [r13+0], 1
0x18018f6c5  mov     [r15], rdx
0x18018f6c8  mov     rcx, [rdx]
0x18018f6cb  mov     rax, [rcx]
0x18018f6ce  mov     rcx, rdx
0x18018f6d1  jmp     loc_18018FB3F
0x18018f6d6  mov     rcx, [rsp+2F0h+var_2A0]
0x18018f6db  mov     rcx, [rcx]
0x18018f6de  inc     rsi
0x18018f6e1  cmp     [rcx+rsi*2], ax
0x18018f6e5  jnz     short loc_18018F6DE
0x18018f6e7  mov     edx, esi
0x18018f6e9  call    cs:__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z; Mso::DWriteAssistant::GetFontSubstitute(wchar_t const *,uint)
0x18018f6ef  mov     rdi, rax
0x18018f6f2  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018f6f8  mov     rcx, rax; this
0x18018f6fb  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018f700  mov     r10, rax
0x18018f703  xor     esi, esi
0x18018f705  mov     [rsp+2F0h+var_2AC], esi
0x18018f709  mov     [rsp+2F0h+var_2A4], esi
0x18018f70d  test    rdi, rdi
0x18018f710  jz      loc_18018F7A5
0x18018f716  mov     rcx, [rax]
0x18018f719  mov     rax, [rcx+28h]
0x18018f71d  lea     r9, [rsp+2F0h+var_2AC]
0x18018f722  lea     r8, [rsp+2F0h+var_2A4]
0x18018f727  mov     rdx, rdi
0x18018f72a  mov     rcx, r10
0x18018f72d  call    cs:__guard_dispatch_icall_fptr
0x18018f733  test    eax, eax
0x18018f735  js      short loc_18018F7A5
0x18018f737  cmp     [rsp+2F0h+var_2AC], esi
0x18018f73b  jz      short loc_18018F7A5
0x18018f73d  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018f742  mov     r10, rax
0x18018f745  mov     rcx, [rax]
0x18018f748  mov     rax, [rcx+10h]
0x18018f74c  mov     [rsp+2F0h+var_2C8], r12
0x18018f751  mov     cl, [rsp+2F0h+var_2AF]
0x18018f755  mov     byte ptr [rsp+2F0h+var_2D0], cl
0x18018f759  mov     r9b, [rsp+2F0h+var_2B0]
0x18018f75e  mov     r8, rdi
0x18018f761  lea     rdx, [rsp+2F0h+var_2A0]
0x18018f766  mov     rcx, r10
0x18018f769  call    cs:__guard_dispatch_icall_fptr
0x18018f76f  cmp     [rsp+2F0h+var_2A0], rsi
0x18018f774  jz      short loc_18018F7A5
0x18018f776  mov     dword ptr [r13+0], 2
0x18018f77e  lea     rdx, [rsp+2F0h+var_2A0]
0x18018f783  mov     rcx, r15
0x18018f786  call    ??$?0VEllipseFigure@GEL@@X@?$TCntPtr@UIFigure@GEL@@@Ofc@@QEAA@AEBV?$TCntPtr@VEllipseFigure@GEL@@@1@@Z; Ofc::TCntPtr<GEL::IFigure>::TCntPtr<GEL::IFigure>(Ofc::TCntPtr<GEL::EllipseFigure> const &)
0x18018f78b  mov     rcx, [rsp+2F0h+var_2A0]
0x18018f790  test    rcx, rcx
0x18018f793  jz      loc_18018FB46
0x18018f799  mov     rax, [rcx]
0x18018f79c  mov     rax, [rax+8]
0x18018f7a0  jmp     loc_18018FB3F
0x18018f7a5  mov     r12, rsi
0x18018f7a8  xor     eax, eax
0x18018f7aa  mov     [rsp+2F0h+var_2AC], eax
0x18018f7ae  mov     dword ptr [r13+0], 3
0x18018f7b6  mov     r8b, [rsp+2F0h+var_2AF]
0x18018f7bb  mov     dil, [rsp+2F0h+var_2B0]
0x18018f7c0  mov     dl, dil
0x18018f7c3  lea     rcx, [rbp+1F0h+var_260]
0x18018f7c7  call    ?GetGDICompatibleSubstitute@GEL@@YA?AV?$TFixedStr@$0BAA@@Ofc@@EE@Z; GEL::GetGDICompatibleSubstitute(uchar,uchar)
0x18018f7cc  xor     eax, eax
0x18018f7ce  cmp     [rsp+2F0h+var_2A8], eax
0x18018f7d2  jbe     loc_18018F94D
0x18018f7d8  mov     rbx, [rsp+2F0h+var_290]
0x18018f7dd  lea     r15d, [rax+1]
0x18018f7e1  mov     r13d, eax
0x18018f7e4  xor     edi, edi
0x18018f7e6  mov     rax, [rbx]
0x18018f7e9  mov     edx, r13d
0x18018f7ec  mov     rcx, rbx
0x18018f7ef  mov     rax, [rax+20h]
0x18018f7f3  call    cs:__guard_dispatch_icall_fptr
0x18018f7f9  mov     r14, rax
0x18018f7fc  cmp     [rax+50h], edi
0x18018f7ff  jnz     short loc_18018F833
0x18018f801  mov     rcx, [rax]
0x18018f804  mov     rax, [rcx]
0x18018f807  mov     rcx, r14
0x18018f80a  call    cs:__guard_dispatch_icall_fptr
0x18018f810  mov     rcx, [r14]
0x18018f813  mov     rax, [rcx+158h]
0x18018f81a  mov     rcx, r14
0x18018f81d  call    cs:__guard_dispatch_icall_fptr
0x18018f823  mov     rax, [r14]
0x18018f826  mov     rcx, r14
0x18018f829  mov     rax, [rax+8]
0x18018f82d  call    cs:__guard_dispatch_icall_fptr
0x18018f833  mov     rax, [r14]
0x18018f836  mov     rcx, r14
0x18018f839  mov     rax, [rax+28h]
0x18018f83d  call    cs:__guard_dispatch_icall_fptr
0x18018f843  test    al, al
0x18018f845  jnz     short loc_18018F85F
0x18018f847  mov     rax, [r14]
0x18018f84a  mov     rcx, r14
0x18018f84d  mov     rax, [rax+30h]
0x18018f851  call    cs:__guard_dispatch_icall_fptr
0x18018f857  test    al, al
0x18018f859  jz      loc_18018F927
0x18018f85f  mov     rax, [r14]
0x18018f862  mov     rcx, r14
0x18018f865  mov     rax, [rax+70h]
0x18018f869  call    cs:__guard_dispatch_icall_fptr
0x18018f86f  mov     rdi, rax
0x18018f872  movzx   ecx, [rsp+2F0h+var_2B0]
0x18018f877  call    cs:__imp_MsoCpgFromChs
0x18018f87d  mov     ecx, eax
0x18018f87f  call    cs:__imp_?MsoFsCpgFromCpg@@YAHH@Z; MsoFsCpgFromCpg(int)
0x18018f885  test    [rdi+10h], eax
0x18018f888  jz      loc_18018F925
0x18018f88e  mov     rcx, r14; this
0x18018f891  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018f896  cmp     al, 2
0x18018f898  jnz     short loc_18018F8A4
0x18018f89a  test    rsi, rsi
0x18018f89d  jnz     short loc_18018F8A4
0x18018f89f  mov     rsi, r14
0x18018f8a2  jmp     short loc_18018F8B7
0x18018f8a4  mov     rcx, r14; this
0x18018f8a7  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018f8ac  cmp     al, 2
0x18018f8ae  jz      short loc_18018F8B7
0x18018f8b0  test    r12, r12
0x18018f8b3  cmovz   r12, r14
0x18018f8b7  mov     rax, [r14]
0x18018f8ba  mov     rcx, r14
0x18018f8bd  mov     rax, [rax+68h]
0x18018f8c1  call    cs:__guard_dispatch_icall_fptr
0x18018f8c7  mov     edi, 3
0x18018f8cc  cmp     [rsp+2F0h+var_2AF], al
0x18018f8d0  cmovnz  edi, r15d
0x18018f8d4  cmp     [rsp+2F0h+var_2B0], 2
0x18018f8d9  jnz     short loc_18018F901
0x18018f8db  mov     rax, [r14]
0x18018f8de  mov     rcx, r14
0x18018f8e1  mov     rax, [rax+10h]
0x18018f8e5  call    cs:__guard_dispatch_icall_fptr
0x18018f8eb  xor     r8d, r8d; bool
0x18018f8ee  lea     rdx, aWingdings; "Wingdings"
0x18018f8f5  mov     rcx, rax; this
0x18018f8f8  call    ?FEqual@CStr@Ofc@@QEBA_NPEB_W_N@Z; Ofc::CStr::FEqual(wchar_t const *,bool)
0x18018f8fd  test    al, al
0x18018f8ff  jz      short loc_18018F903
0x18018f901  inc     edi
0x18018f903  cmp     [rsp+2F0h+var_2AC], edi
0x18018f907  jge     loc_18018FA1F
0x18018f90d  mov     rcx, r14; this
0x18018f910  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018f915  cmp     al, 2
0x18018f917  jnz     short loc_18018F91E
0x18018f919  mov     rsi, r14
0x18018f91c  jmp     short loc_18018F921
0x18018f91e  mov     r12, r14
0x18018f921  mov     [rsp+2F0h+var_2AC], edi
0x18018f925  xor     edi, edi
0x18018f927  add     r13d, r15d
0x18018f92a  cmp     r13d, [rsp+2F0h+var_2A8]
0x18018f92f  jb      loc_18018F7E6
0x18018f935  mov     rbx, [rsp+2F0h+var_278]
0x18018f93a  mov     r15, [rbp+1F0h+var_270]
0x18018f93e  mov     r13, [rsp+2F0h+var_298]
0x18018f943  mov     r14, [rsp+2F0h+var_290]
0x18018f948  mov     dil, [rsp+2F0h+var_2B0]
0x18018f94d  cmp     dil, 2
0x18018f951  cmovnz  rsi, r12
0x18018f955  xor     r12d, r12d
0x18018f958  test    rsi, rsi
0x18018f95b  jnz     loc_18018FB33
0x18018f961  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018f967  mov     rcx, rax; this
0x18018f96a  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018f96f  mov     r10, rax
0x18018f972  mov     [rsp+2F0h+var_2A8], r12d
0x18018f977  mov     [rsp+2F0h+var_2A4], r12d
0x18018f97c  mov     rcx, [rax]
0x18018f97f  mov     rax, [rcx+28h]
0x18018f983  lea     r9, [rsp+2F0h+var_2A8]
0x18018f988  lea     r8, [rsp+2F0h+var_2A4]
0x18018f98d  lea     rdx, aArial; "Arial"
0x18018f994  mov     rcx, r10
0x18018f997  call    cs:__guard_dispatch_icall_fptr
0x18018f99d  test    eax, eax
0x18018f99f  js      loc_18018FACB
0x18018f9a5  cmp     [rsp+2F0h+var_2A8], r12d
0x18018f9aa  jz      loc_18018FACB
0x18018f9b0  mov     dword ptr [r13+0], 4
0x18018f9b8  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018f9bd  mov     r10, rax
0x18018f9c0  mov     rcx, [rax]
0x18018f9c3  mov     rax, [rcx+10h]
0x18018f9c7  mov     rcx, [rsp+2F0h+var_288]
0x18018f9cc  mov     [rsp+2F0h+var_2C8], rcx
0x18018f9d1  mov     cl, [rsp+2F0h+var_2AF]
0x18018f9d5  mov     byte ptr [rsp+2F0h+var_2D0], cl
0x18018f9d9  mov     r9b, dil
0x18018f9dc  lea     r8, aArial; "Arial"
0x18018f9e3  lea     rdx, [rsp+2F0h+var_298]
0x18018f9e8  mov     rcx, r10
0x18018f9eb  call    cs:__guard_dispatch_icall_fptr
0x18018f9f1  mov     rdi, [rax]
0x18018f9f4  mov     [rax], r12
0x18018f9f7  mov     rcx, [rsp+2F0h+var_298]
0x18018f9fc  test    rcx, rcx
0x18018f9ff  jz      short loc_18018FA0E
0x18018fa01  mov     rax, [rcx]
0x18018fa04  mov     rax, [rax+8]
0x18018fa08  call    cs:__guard_dispatch_icall_fptr
0x18018fa0e  test    rdi, rdi
  ... truncated ...
```
