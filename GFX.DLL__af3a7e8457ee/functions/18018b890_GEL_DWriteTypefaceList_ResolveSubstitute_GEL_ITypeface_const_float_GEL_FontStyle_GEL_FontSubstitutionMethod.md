# GEL::DWriteTypefaceList::ResolveSubstitute(GEL::ITypeface const &,float,GEL::FontStyle,GEL::FontSubstitutionMethod &)

- ea: `0x18018b890`
- end: `0x18018be9c`
- name: `?ResolveSubstitute@DWriteTypefaceList@GEL@@UEBA?AV?$TCntPtr@$$CBUITypeface@GEL@@@Ofc@@AEBUITypeface@2@MW4FontStyle@2@AEAW4FontSubstitutionMethod@2@@Z`
- size: `1548`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180055e60`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800795a0`
- `0x18008c8f0`
- `0x18008d720`
- `0x1800be640`
- `0x180111080`
- `0x1801722c4`
- `0x18018b890`
- `0x1801aee70`
- `0x180202a34`
- `0x180202a68`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18018be69`
- `MSVCP140!_Mtx_unlock` at `0x18018be69`
- `MSO!__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ` at `0x18018b984`
- `MSO!__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ` at `0x18018b984`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018ba12`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018bc81`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018ba12`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18018bc81`
- `mso40uiWin32Client!__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z` at `0x18018ba09`
- `mso40uiWin32Client!__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z` at `0x18018ba09`
- `Mso30Win32Client!__imp_?MsoFsCpgFromCpg@@YAHH@Z` at `0x18018bb9f`
- `Mso30Win32Client!__imp_?MsoFsCpgFromCpg@@YAHH@Z` at `0x18018bb9f`
- `Mso30Win32Client!__imp_MsoCpgFromChs` at `0x18018bb97`
- `Mso30Win32Client!__imp_MsoCpgFromChs` at `0x18018bb97`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18018b920`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18018b920`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018be4c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18018be4c`

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
0x18018b890  mov     [rsp-8+arg_18], rbx
0x18018b895  push    rbp
0x18018b896  push    rsi
0x18018b897  push    rdi
0x18018b898  push    r12
0x18018b89a  push    r13
0x18018b89c  push    r14
0x18018b89e  push    r15
0x18018b8a0  lea     rbp, [rsp-1C0h]
0x18018b8a8  sub     rsp, 2C0h
0x18018b8af  mov     rax, cs:__security_cookie
0x18018b8b6  xor     rax, rsp
0x18018b8b9  mov     [rbp+1F0h+var_40], rax
0x18018b8c0  mov     rdi, r8
0x18018b8c3  mov     r15, rdx
0x18018b8c6  mov     [rbp+1F0h+var_270], rdx
0x18018b8ca  mov     r14, rcx
0x18018b8cd  mov     [rsp+2F0h+var_290], rcx
0x18018b8d2  mov     [rsp+2F0h+var_288], rdx
0x18018b8d7  mov     r12d, [rbp+1F0h+arg_20]
0x18018b8de  mov     r13, [rbp+1F0h+arg_28]
0x18018b8e5  mov     [rsp+2F0h+var_298], r13
0x18018b8ea  lea     rbx, [rcx+10h]
0x18018b8ee  mov     [rsp+2F0h+var_278], rbx
0x18018b8f3  mov     rcx, rbx; this
0x18018b8f6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18018b8fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18018b8ff  mov     [r13+0], esi
0x18018b903  mov     rax, [r14]
0x18018b906  mov     rcx, r14
0x18018b909  mov     rax, [rax+28h]
0x18018b90d  call    cs:__guard_dispatch_icall_fptr
0x18018b913  mov     [rsp+2F0h+var_2A8], eax
0x18018b917  test    eax, eax
0x18018b919  jnz     short loc_18018B946
0x18018b91b  mov     ecx, 38C658h
0x18018b920  call    cs:__imp_MsoShipAssertTagProc
0x18018b926  xor     eax, eax
0x18018b928  mov     [r13+0], eax
0x18018b92c  mov     [r15], rdi
0x18018b92f  test    rdi, rdi
0x18018b932  jz      loc_18018BE66
0x18018b938  mov     rcx, [rdi]
0x18018b93b  mov     rax, [rcx]
0x18018b93e  mov     rcx, rdi
0x18018b941  jmp     loc_18018BE5F
0x18018b946  mov     rax, [rdi]
0x18018b949  mov     rcx, rdi
0x18018b94c  mov     rax, [rax+10h]
0x18018b950  call    cs:__guard_dispatch_icall_fptr
0x18018b956  mov     [rsp+2F0h+var_2A0], rax
0x18018b95b  mov     rcx, rdi; this
0x18018b95e  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018b963  mov     [rsp+2F0h+var_2B0], al
0x18018b967  mov     rcx, [rdi]
0x18018b96a  mov     rax, [rcx+68h]
0x18018b96e  mov     rcx, rdi
0x18018b971  call    cs:__guard_dispatch_icall_fptr
0x18018b977  mov     [rsp+2F0h+var_2AF], al
0x18018b97b  lea     rax, [rdi+58h]
0x18018b97f  mov     [rsp+2F0h+var_288], rax
0x18018b984  call    cs:__imp_?IsFontSubstitutionFeatureGateEnabled@FontSubstitution@Mso@@YA_NXZ; Mso::FontSubstitution::IsFontSubstitutionFeatureGateEnabled(void)
0x18018b98a  mov     rcx, r14
0x18018b98d  test    al, al
0x18018b98f  jz      short loc_18018B9C4
0x18018b991  mov     [rsp+2F0h+var_2D0], r13
0x18018b996  lea     r9, [rdi+58h]
0x18018b99a  mov     r8, rdi
0x18018b99d  lea     rdx, [rsp+2F0h+var_2A0]
0x18018b9a2  call    ?ResolveSubstitute@TypefaceList@GEL@@QEBA?AV?$TCntPtr@$$CBUITypeface@GEL@@@Ofc@@AEBUITypeface@2@AEBUtagPANOSE@@AEAW4FontSubstitutionMethod@2@@Z; GEL::TypefaceList::ResolveSubstitute(GEL::ITypeface const &,tagPANOSE const &,GEL::FontSubstitutionMethod &)
0x18018b9a7  mov     rcx, [rsp+2F0h+var_2A0]
0x18018b9ac  xor     esi, esi
0x18018b9ae  test    rcx, rcx
0x18018b9b1  jz      loc_18018BAC5
0x18018b9b7  mov     [r15], rcx
0x18018b9ba  mov     [rsp+2F0h+var_2A0], rsi
0x18018b9bf  jmp     loc_18018BE66
0x18018b9c4  mov     r8d, r12d
0x18018b9c7  lea     r12, [rdi+58h]
0x18018b9cb  mov     rdx, r12
0x18018b9ce  call    ?FindPanoseMatch@TypefaceList@GEL@@QEBAPEBUITypeface@2@AEBUtagPANOSE@@W4FontStyle@2@@Z; GEL::TypefaceList::FindPanoseMatch(tagPANOSE const &,GEL::FontStyle)
0x18018b9d3  mov     rdx, rax
0x18018b9d6  xor     eax, eax
0x18018b9d8  test    rdx, rdx
0x18018b9db  jz      short loc_18018B9F6
0x18018b9dd  mov     dword ptr [r13+0], 1
0x18018b9e5  mov     [r15], rdx
0x18018b9e8  mov     rcx, [rdx]
0x18018b9eb  mov     rax, [rcx]
0x18018b9ee  mov     rcx, rdx
0x18018b9f1  jmp     loc_18018BE5F
0x18018b9f6  mov     rcx, [rsp+2F0h+var_2A0]
0x18018b9fb  mov     rcx, [rcx]
0x18018b9fe  inc     rsi
0x18018ba01  cmp     [rcx+rsi*2], ax
0x18018ba05  jnz     short loc_18018B9FE
0x18018ba07  mov     edx, esi
0x18018ba09  call    cs:__imp_?GetFontSubstitute@DWriteAssistant@Mso@@YAPEB_WPEB_WI@Z; Mso::DWriteAssistant::GetFontSubstitute(wchar_t const *,uint)
0x18018ba0f  mov     rdi, rax
0x18018ba12  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018ba18  mov     rcx, rax; this
0x18018ba1b  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018ba20  mov     r10, rax
0x18018ba23  xor     esi, esi
0x18018ba25  mov     [rsp+2F0h+var_2AC], esi
0x18018ba29  mov     [rsp+2F0h+var_2A4], esi
0x18018ba2d  test    rdi, rdi
0x18018ba30  jz      loc_18018BAC5
0x18018ba36  mov     rcx, [rax]
0x18018ba39  mov     rax, [rcx+28h]
0x18018ba3d  lea     r9, [rsp+2F0h+var_2AC]
0x18018ba42  lea     r8, [rsp+2F0h+var_2A4]
0x18018ba47  mov     rdx, rdi
0x18018ba4a  mov     rcx, r10
0x18018ba4d  call    cs:__guard_dispatch_icall_fptr
0x18018ba53  test    eax, eax
0x18018ba55  js      short loc_18018BAC5
0x18018ba57  cmp     [rsp+2F0h+var_2AC], esi
0x18018ba5b  jz      short loc_18018BAC5
0x18018ba5d  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018ba62  mov     r10, rax
0x18018ba65  mov     rcx, [rax]
0x18018ba68  mov     rax, [rcx+10h]
0x18018ba6c  mov     [rsp+2F0h+var_2C8], r12
0x18018ba71  mov     cl, [rsp+2F0h+var_2AF]
0x18018ba75  mov     byte ptr [rsp+2F0h+var_2D0], cl
0x18018ba79  mov     r9b, [rsp+2F0h+var_2B0]
0x18018ba7e  mov     r8, rdi
0x18018ba81  lea     rdx, [rsp+2F0h+var_2A0]
0x18018ba86  mov     rcx, r10
0x18018ba89  call    cs:__guard_dispatch_icall_fptr
0x18018ba8f  cmp     [rsp+2F0h+var_2A0], rsi
0x18018ba94  jz      short loc_18018BAC5
0x18018ba96  mov     dword ptr [r13+0], 2
0x18018ba9e  lea     rdx, [rsp+2F0h+var_2A0]
0x18018baa3  mov     rcx, r15
0x18018baa6  call    ??$?0VEllipseFigure@GEL@@X@?$TCntPtr@UIFigure@GEL@@@Ofc@@QEAA@AEBV?$TCntPtr@VEllipseFigure@GEL@@@1@@Z; Ofc::TCntPtr<GEL::IFigure>::TCntPtr<GEL::IFigure>(Ofc::TCntPtr<GEL::EllipseFigure> const &)
0x18018baab  mov     rcx, [rsp+2F0h+var_2A0]
0x18018bab0  test    rcx, rcx
0x18018bab3  jz      loc_18018BE66
0x18018bab9  mov     rax, [rcx]
0x18018babc  mov     rax, [rax+8]
0x18018bac0  jmp     loc_18018BE5F
0x18018bac5  mov     r12, rsi
0x18018bac8  xor     eax, eax
0x18018baca  mov     [rsp+2F0h+var_2AC], eax
0x18018bace  mov     dword ptr [r13+0], 3
0x18018bad6  mov     r8b, [rsp+2F0h+var_2AF]
0x18018badb  mov     dil, [rsp+2F0h+var_2B0]
0x18018bae0  mov     dl, dil
0x18018bae3  lea     rcx, [rbp+1F0h+var_260]
0x18018bae7  call    ?GetGDICompatibleSubstitute@GEL@@YA?AV?$TFixedStr@$0BAA@@Ofc@@EE@Z; GEL::GetGDICompatibleSubstitute(uchar,uchar)
0x18018baec  xor     eax, eax
0x18018baee  cmp     [rsp+2F0h+var_2A8], eax
0x18018baf2  jbe     loc_18018BC6D
0x18018baf8  mov     rbx, [rsp+2F0h+var_290]
0x18018bafd  lea     r15d, [rax+1]
0x18018bb01  mov     r13d, eax
0x18018bb04  xor     edi, edi
0x18018bb06  mov     rax, [rbx]
0x18018bb09  mov     edx, r13d
0x18018bb0c  mov     rcx, rbx
0x18018bb0f  mov     rax, [rax+20h]
0x18018bb13  call    cs:__guard_dispatch_icall_fptr
0x18018bb19  mov     r14, rax
0x18018bb1c  cmp     [rax+50h], edi
0x18018bb1f  jnz     short loc_18018BB53
0x18018bb21  mov     rcx, [rax]
0x18018bb24  mov     rax, [rcx]
0x18018bb27  mov     rcx, r14
0x18018bb2a  call    cs:__guard_dispatch_icall_fptr
0x18018bb30  mov     rcx, [r14]
0x18018bb33  mov     rax, [rcx+158h]
0x18018bb3a  mov     rcx, r14
0x18018bb3d  call    cs:__guard_dispatch_icall_fptr
0x18018bb43  mov     rax, [r14]
0x18018bb46  mov     rcx, r14
0x18018bb49  mov     rax, [rax+8]
0x18018bb4d  call    cs:__guard_dispatch_icall_fptr
0x18018bb53  mov     rax, [r14]
0x18018bb56  mov     rcx, r14
0x18018bb59  mov     rax, [rax+28h]
0x18018bb5d  call    cs:__guard_dispatch_icall_fptr
0x18018bb63  test    al, al
0x18018bb65  jnz     short loc_18018BB7F
0x18018bb67  mov     rax, [r14]
0x18018bb6a  mov     rcx, r14
0x18018bb6d  mov     rax, [rax+30h]
0x18018bb71  call    cs:__guard_dispatch_icall_fptr
0x18018bb77  test    al, al
0x18018bb79  jz      loc_18018BC47
0x18018bb7f  mov     rax, [r14]
0x18018bb82  mov     rcx, r14
0x18018bb85  mov     rax, [rax+70h]
0x18018bb89  call    cs:__guard_dispatch_icall_fptr
0x18018bb8f  mov     rdi, rax
0x18018bb92  movzx   ecx, [rsp+2F0h+var_2B0]
0x18018bb97  call    cs:__imp_MsoCpgFromChs
0x18018bb9d  mov     ecx, eax
0x18018bb9f  call    cs:__imp_?MsoFsCpgFromCpg@@YAHH@Z; MsoFsCpgFromCpg(int)
0x18018bba5  test    [rdi+10h], eax
0x18018bba8  jz      loc_18018BC45
0x18018bbae  mov     rcx, r14; this
0x18018bbb1  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018bbb6  cmp     al, 2
0x18018bbb8  jnz     short loc_18018BBC4
0x18018bbba  test    rsi, rsi
0x18018bbbd  jnz     short loc_18018BBC4
0x18018bbbf  mov     rsi, r14
0x18018bbc2  jmp     short loc_18018BBD7
0x18018bbc4  mov     rcx, r14; this
0x18018bbc7  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018bbcc  cmp     al, 2
0x18018bbce  jz      short loc_18018BBD7
0x18018bbd0  test    r12, r12
0x18018bbd3  cmovz   r12, r14
0x18018bbd7  mov     rax, [r14]
0x18018bbda  mov     rcx, r14
0x18018bbdd  mov     rax, [rax+68h]
0x18018bbe1  call    cs:__guard_dispatch_icall_fptr
0x18018bbe7  mov     edi, 3
0x18018bbec  cmp     [rsp+2F0h+var_2AF], al
0x18018bbf0  cmovnz  edi, r15d
0x18018bbf4  cmp     [rsp+2F0h+var_2B0], 2
0x18018bbf9  jnz     short loc_18018BC21
0x18018bbfb  mov     rax, [r14]
0x18018bbfe  mov     rcx, r14
0x18018bc01  mov     rax, [rax+10h]
0x18018bc05  call    cs:__guard_dispatch_icall_fptr
0x18018bc0b  xor     r8d, r8d; bool
0x18018bc0e  lea     rdx, aWingdings; "Wingdings"
0x18018bc15  mov     rcx, rax; this
0x18018bc18  call    ?FEqual@CStr@Ofc@@QEBA_NPEB_W_N@Z; Ofc::CStr::FEqual(wchar_t const *,bool)
0x18018bc1d  test    al, al
0x18018bc1f  jz      short loc_18018BC23
0x18018bc21  inc     edi
0x18018bc23  cmp     [rsp+2F0h+var_2AC], edi
0x18018bc27  jge     loc_18018BD3F
0x18018bc2d  mov     rcx, r14; this
0x18018bc30  call    ?Chs@Typeface@GEL@@QEBAEXZ; GEL::Typeface::Chs(void)
0x18018bc35  cmp     al, 2
0x18018bc37  jnz     short loc_18018BC3E
0x18018bc39  mov     rsi, r14
0x18018bc3c  jmp     short loc_18018BC41
0x18018bc3e  mov     r12, r14
0x18018bc41  mov     [rsp+2F0h+var_2AC], edi
0x18018bc45  xor     edi, edi
0x18018bc47  add     r13d, r15d
0x18018bc4a  cmp     r13d, [rsp+2F0h+var_2A8]
0x18018bc4f  jb      loc_18018BB06
0x18018bc55  mov     rbx, [rsp+2F0h+var_278]
0x18018bc5a  mov     r15, [rbp+1F0h+var_270]
0x18018bc5e  mov     r13, [rsp+2F0h+var_298]
0x18018bc63  mov     r14, [rsp+2F0h+var_290]
0x18018bc68  mov     dil, [rsp+2F0h+var_2B0]
0x18018bc6d  cmp     dil, 2
0x18018bc71  cmovnz  rsi, r12
0x18018bc75  xor     r12d, r12d
0x18018bc78  test    rsi, rsi
0x18018bc7b  jnz     loc_18018BE53
0x18018bc81  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x18018bc87  mov     rcx, rax; this
0x18018bc8a  call    ?GetFontCollection@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIFontCollection@23@XZ; Mso::DWriteAssistant::ResourceManager::GetFontCollection(void)
0x18018bc8f  mov     r10, rax
0x18018bc92  mov     [rsp+2F0h+var_2A8], r12d
0x18018bc97  mov     [rsp+2F0h+var_2A4], r12d
0x18018bc9c  mov     rcx, [rax]
0x18018bc9f  mov     rax, [rcx+28h]
0x18018bca3  lea     r9, [rsp+2F0h+var_2A8]
0x18018bca8  lea     r8, [rsp+2F0h+var_2A4]
0x18018bcad  lea     rdx, aArial; "Arial"
0x18018bcb4  mov     rcx, r10
0x18018bcb7  call    cs:__guard_dispatch_icall_fptr
0x18018bcbd  test    eax, eax
0x18018bcbf  js      loc_18018BDEB
0x18018bcc5  cmp     [rsp+2F0h+var_2A8], r12d
0x18018bcca  jz      loc_18018BDEB
0x18018bcd0  mov     dword ptr [r13+0], 4
0x18018bcd8  call    ?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x18018bcdd  mov     r10, rax
0x18018bce0  mov     rcx, [rax]
0x18018bce3  mov     rax, [rcx+10h]
0x18018bce7  mov     rcx, [rsp+2F0h+var_288]
0x18018bcec  mov     [rsp+2F0h+var_2C8], rcx
0x18018bcf1  mov     cl, [rsp+2F0h+var_2AF]
0x18018bcf5  mov     byte ptr [rsp+2F0h+var_2D0], cl
0x18018bcf9  mov     r9b, dil
0x18018bcfc  lea     r8, aArial; "Arial"
0x18018bd03  lea     rdx, [rsp+2F0h+var_298]
0x18018bd08  mov     rcx, r10
0x18018bd0b  call    cs:__guard_dispatch_icall_fptr
0x18018bd11  mov     rdi, [rax]
0x18018bd14  mov     [rax], r12
0x18018bd17  mov     rcx, [rsp+2F0h+var_298]
0x18018bd1c  test    rcx, rcx
0x18018bd1f  jz      short loc_18018BD2E
0x18018bd21  mov     rax, [rcx]
0x18018bd24  mov     rax, [rax+8]
0x18018bd28  call    cs:__guard_dispatch_icall_fptr
0x18018bd2e  test    rdi, rdi
  ... truncated ...
```
