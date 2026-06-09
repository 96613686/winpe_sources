# LicenseInstance::Listener::InitFromDocuments(Microsoft::WRL::ComPtr<ILicenseStorageService> const &,Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &,bool)

- ea: `0x1800184d0`
- end: `0x180018d42`
- name: `?InitFromDocuments@Listener@LicenseInstance@@AEAAXAEBV?$ComPtr@UILicenseStorageService@@@WRL@Microsoft@@AEBV?$ComPtr@UIStoredKeyDocument@@@45@AEBV?$ComPtr@UIStoredLeaseDocument@@@45@_N@Z`
- size: `2162`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f20`
- `0x1800196b0`
- `0x180096d90`

## callees

- `0x180004738`
- `0x18000b7fc`
- `0x180013b50`
- `0x1800171b0`
- `0x180017330`
- `0x1800184d0`
- `0x180054a54`
- `0x1800593bc`
- `0x180076e64`
- `0x18008251f`
- `0x18008252b`
- `0x180084614`
- `0x180084f50`
- `0x1800b8010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018c3e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018c3e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800186dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800186dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018930`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 LicenseInstance::Listener::InitFromDocuments(__int64 a1, __int64 *a2, ...)
{
  __int64 **v2; // rax
  _QWORD *v3; // r13
  __int64 *v4; // rsi
  __int64 v5; // r14
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // r8
  void *v10; // r9
  void **v11; // r15
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rax
  char *v15; // rsi
  _BYTE *v16; // r12
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  void *v20; // rsi
  unsigned __int64 v21; // r12
  __int64 v22; // rbx
  void *v23; // r13
  __int64 **v24; // rdi
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 result; // rax
  __int64 v30; // rbx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rsi
  __int64 (__fastcall *v37)(__int64, void **, _QWORD, __int64 *); // r13
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  int v41; // eax
  int v42; // eax
  void *v43; // r12
  int v44; // eax
  int v45; // eax
  int v46; // eax
  const char *v47; // r9
  int Format; // [rsp+20h] [rbp-88h]
  int v49; // [rsp+40h] [rbp-68h] BYREF
  int v50; // [rsp+44h] [rbp-64h] BYREF
  __int64 v51; // [rsp+48h] [rbp-60h] BYREF
  __int64 v52; // [rsp+50h] [rbp-58h] BYREF
  void *Src; // [rsp+58h] [rbp-50h] BYREF
  FILETIME FileTime1; // [rsp+60h] [rbp-48h] BYREF
  int v55[16]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  _QWORD *v59; // [rsp+C0h] [rbp+18h] BYREF
  va_list va; // [rsp+C0h] [rbp+18h]
  __int64 **v61; // [rsp+C8h] [rbp+20h]
  __int64 v62; // [rsp+D0h] [rbp+28h]
  va_list va1; // [rsp+D8h] [rbp+30h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v59 = va_arg(va1, _QWORD *);
  v61 = va_arg(va1, __int64 **);
  v62 = va_arg(va1, _QWORD);
  v2 = v61;
  v3 = v59;
  v4 = a2;
  v5 = a1;
  v49 = 0;
  v55[0] = 1;
  v6 = (__int64 *)*v59;
  if ( *v59 )
  {
    Src = 0;
    v7 = *v6;
    Src = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, void **))(v7 + 104))(v6, &Src);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v8,
        Format);
    v10 = Src;
    v11 = (void **)(v5 + 72);
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)Src + v13) );
    v14 = *(_QWORD *)(v5 + 96);
    if ( v13 > v14 )
    {
      std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Reallocate_for<_lambda_12dc1f05c26b191247dab1bc103bfa94_,unsigned short const *>(
        v5 + 72,
        v13,
        v9,
        Src);
    }
    else
    {
      if ( v14 > 7 )
        v15 = (char *)*v11;
      else
        v15 = (char *)(v5 + 72);
      *(_QWORD *)(v5 + 88) = v13;
      v30 = 2 * v13;
      memmove_0(v15, v10, 2 * v13);
      *(_WORD *)&v15[v30] = 0;
      v4 = a2;
    }
    FileTime1 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, FILETIME *))(*(_QWORD *)*v3 + 32LL))(*v3, &FileTime1);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v31,
        Format);
    *(FILETIME *)(v5 + 144) = FileTime1;
    v32 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 72LL))(*v3, v5 + 160);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v32,
        Format);
    LODWORD(v52) = 0;
    v33 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v3 + 144LL))(*v3, &v52);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v33,
        Format);
    v16 = (_BYTE *)(v5 + 152);
    *(_BYTE *)(v5 + 152) = (_DWORD)v52 != 0;
    LODWORD(v51) = 0;
    v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*v3 + 48LL))(*v3, v5 + 164, &v51);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v34,
        Format);
    if ( *(int *)(v5 + 164) <= 0x10000000 )
    {
      v46 = v51;
      if ( (int)v51 >= 0 )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
          0x19Fu,
          "LicenseInstance::Listener::InitFromDocuments",
          (wchar_t *)L"Assert (%s): %s");
        v46 = v51;
      }
      *(_DWORD *)(v5 + 156) = v46;
    }
    else
    {
      *(_DWORD *)(v5 + 156) = 0;
    }
    v35 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(*(_QWORD *)*v3 + 112LL))(*v3, 2130706432, v55);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v35,
        Format);
    if ( (unsigned __int8)IsCompareContentIdPresent(retaddr) )
    {
      v50 = 0;
      v42 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 88LL))(*v3, &v50);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
          (const char *)(unsigned int)v42,
          Format);
      if ( v50 >= 2 )
        v49 = (v50 >= 3) + 1;
      else
        v49 = 0;
    }
    v36 = *v4;
    v37 = *(__int64 (__fastcall **)(__int64, void **, _QWORD, __int64 *))(*(_QWORD *)v36 + 104LL);
    v38 = *(_QWORD *)(v5 + 136);
    if ( v38 )
    {
      *(_QWORD *)(v5 + 136) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    if ( *(_QWORD *)(v5 + 96) > 7u )
      v11 = (void **)*v11;
    Format = v5 + 136;
    v39 = v37(v36, v11, *v59, *v61);
    if ( v39 != -2143326201 && v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v39,
        Format);
    if ( Src )
      CoTaskMemFree(Src);
    v3 = v59;
    v2 = v61;
  }
  else
  {
    v16 = (_BYTE *)(v5 + 152);
    v12 = -1;
  }
  v17 = *v2;
  if ( *v2 )
  {
    Src = 0;
    v18 = *v17;
    Src = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, void **))(v18 + 104))(v17, &Src);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v19,
        Format);
    v20 = Src;
    do
      ++v12;
    while ( *((_WORD *)Src + v12) );
    v21 = *(_QWORD *)(v5 + 128);
    if ( v12 <= v21 )
    {
      if ( v21 <= 7 )
        v43 = (void *)(v5 + 104);
      else
        v43 = *(void **)(v5 + 104);
      *(_QWORD *)(v5 + 120) = v12;
      memmove_0(v43, v20, 2 * v12);
      *((_WORD *)v43 + v12) = 0;
    }
    else
    {
      if ( v12 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      v22 = std::wstring::_Calculate_growth(v5 + 104, v12);
      v23 = (void *)std::allocator<unsigned short>::allocate(v5 + 104, v22 + 1);
      *(_QWORD *)(v5 + 120) = v12;
      *(_QWORD *)(v5 + 128) = v22;
      memcpy_0(v23, v20, 2 * v12);
      *((_WORD *)v23 + v12) = 0;
      if ( v21 > 7 )
        std::_Deallocate<16>(*(_QWORD *)(v5 + 104), 2 * v21 + 2);
      *(_QWORD *)(v5 + 104) = v23;
    }
    v24 = v61;
    v25 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**v61 + 72))(*v61, v5 + 160);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v25,
        Format);
    v50 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, int *))(**v24 + 120))(*v24, &v50);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v26,
        Format);
    *(_BYTE *)(v5 + 152) = v50 != 0;
    FileTime1 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64 *, FILETIME *))(**v24 + 32))(*v24, &FileTime1);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v27,
        Format);
    if ( CompareFileTime(&FileTime1, (const FILETIME *)(v5 + 144)) < 0 )
      *(FILETIME *)(v5 + 144) = FileTime1;
    v28 = (*(__int64 (__fastcall **)(__int64 *, int *))(**v24 + 136))(*v24, &v49);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
        (const char *)(unsigned int)v28,
        Format);
    if ( v49 > 1 && (v55[0] & 8) != 0 )
    {
      LODWORD(v52) = 1;
      LODWORD(v51) = 0x10000000;
      v44 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64 *))(**v24 + 48))(*v24, &v51, &v52);
      if ( v44 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
          (const char *)(unsigned int)v44,
          Format);
      if ( (int)v52 < 0 && (*(int *)(v5 + 156) >= 0 || (_DWORD)v52 != -2143322111) )
        *(_DWORD *)(v5 + 156) = v52;
    }
    if ( !*v59 )
    {
      LODWORD(v59) = 0;
      v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD **))(**v24 + 128))(*v24, (_QWORD **)va);
      if ( v45 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
          (const char *)(unsigned int)v45,
          Format);
      if ( (_DWORD)v59 )
      {
        v51 = 0;
        if ( (int)Microsoft::WRL::ComPtr<IStoredLeaseDocument>::As<IClipLeaseCatalogInfo>(v24, &v51) >= 0 )
        {
          try
          {
            (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 56LL))(v51, &v52);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 136);
            Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v52);
            *(_QWORD *)(v5 + 136) = v52;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x203,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
              v47);
            v5 = a1;
          }
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v51);
      }
    }
    if ( Src )
      CoTaskMemFree(Src);
  }
  else if ( (_BYTE)v62 )
  {
    if ( *v16 )
    {
      v40 = *v3;
      if ( *v3 )
      {
        LODWORD(v59) = 0;
        v41 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v40 + 88LL))(v40, (_QWORD **)va);
        if ( v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licenseinstance.cpp",
            (const char *)(unsigned int)v41,
            Format);
        if ( (int)v59 >= 3 )
          *v16 = 0;
      }
    }
  }
  result = (unsigned int)v49;
  *(_DWORD *)(v5 + 168) = v49;
  return result;
}

```

## disassembly

```asm
0x1800184d0  mov     r11, rsp
0x1800184d3  mov     [r11+20h], r9
0x1800184d7  mov     [r11+18h], r8
0x1800184db  mov     [r11+10h], rdx
0x1800184df  mov     [r11+8], rcx
0x1800184e3  push    rbx
0x1800184e4  push    rsi
0x1800184e5  push    rdi
0x1800184e6  push    r12
0x1800184e8  push    r13
0x1800184ea  push    r14
0x1800184ec  push    r15
0x1800184ee  sub     rsp, 70h
0x1800184f2  mov     rax, r9
0x1800184f5  mov     r13, r8
0x1800184f8  mov     rsi, rdx
0x1800184fb  mov     r14, rcx
0x1800184fe  xor     ebx, ebx
0x180018500  mov     [rsp+0A8h+var_68], ebx
0x180018504  mov     [rsp+0A8h+var_40], 1
0x18001850c  mov     rcx, [r8]
0x18001850f  test    rcx, rcx
0x180018512  jz      short loc_18001857A
0x180018514  mov     [r11-50h], rbx
0x180018518  mov     rax, [rcx]
0x18001851b  mov     [r11-50h], rbx
0x18001851f  lea     rdx, [r11-50h]
0x180018523  mov     rax, [rax+68h]
0x180018527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001852c  mov     rcx, [rsp+0A8h]; this
0x180018534  test    eax, eax
0x180018536  js      loc_1800189A5
0x18001853c  mov     r9, [rsp+0A8h+Src]
0x180018541  lea     r15, [r14+48h]
0x180018545  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001854c  mov     rdx, rdi
0x18001854f  nop
0x180018550  inc     rdx
0x180018553  cmp     word ptr [r9+rdx*2], 0
0x180018559  jnz     short loc_180018550
0x18001855b  mov     rax, [r15+18h]
0x18001855f  cmp     rdx, rax
0x180018562  ja      loc_180018BA5
0x180018568  cmp     rax, 7
0x18001856c  ja      loc_180018769
0x180018572  mov     rsi, r15
0x180018575  jmp     loc_18001876C
0x18001857a  lea     r12, [r14+98h]
0x180018581  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018588  mov     rcx, [rax]
0x18001858b  test    rcx, rcx
0x18001858e  jz      loc_180018740
0x180018594  mov     [rsp+0A8h+Src], rbx
0x180018599  mov     rax, [rcx]
0x18001859c  mov     [rsp+0A8h+Src], rbx
0x1800185a1  lea     rdx, [rsp+0A8h+Src]
0x1800185a6  mov     rax, [rax+68h]
0x1800185aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185af  mov     rcx, [rsp+0A8h]; this
0x1800185b7  test    eax, eax
0x1800185b9  js      loc_180018A38
0x1800185bf  mov     rsi, [rsp+0A8h+Src]
0x1800185c4  inc     rdi
0x1800185c7  cmp     word ptr [rsi+rdi*2], 0
0x1800185cc  jnz     short loc_1800185C4
0x1800185ce  mov     r12, [r14+80h]
0x1800185d5  cmp     rdi, r12
0x1800185d8  jbe     loc_180018ADF
0x1800185de  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800185e8  cmp     rdi, rax
0x1800185eb  ja      loc_180018C37
0x1800185f1  mov     rdx, rdi
0x1800185f4  lea     rcx, [r14+68h]
0x1800185f8  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBA_K_K@Z; std::wstring::_Calculate_growth(unsigned __int64)
0x1800185fd  mov     rbx, rax
0x180018600  lea     rdx, [rax+1]
0x180018604  lea     rcx, [r14+68h]
0x180018608  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18001860d  mov     r13, rax
0x180018610  mov     [r14+78h], rdi
0x180018614  mov     [r14+80h], rbx
0x18001861b  lea     rbx, [rdi+rdi]
0x18001861f  mov     r8, rbx; Size
0x180018622  mov     rdx, rsi; Src
0x180018625  mov     rcx, rax; void *
0x180018628  call    memcpy_0
0x18001862d  xor     esi, esi
0x18001862f  mov     [rbx+r13], si
0x180018634  cmp     r12, 7
0x180018638  ja      loc_180018C45
0x18001863e  mov     [r14+68h], r13
0x180018642  mov     rdi, [rsp+0A8h+arg_18]
0x18001864a  mov     rcx, [rdi]
0x18001864d  mov     rax, [rcx]
0x180018650  lea     rdx, [r14+0A0h]
0x180018657  mov     rax, [rax+48h]
0x18001865b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018660  mov     rcx, [rsp+0A8h]; this
0x180018668  test    eax, eax
0x18001866a  js      loc_180018A4D
0x180018670  mov     [rsp+0A8h+var_64], esi
0x180018674  mov     rcx, [rdi]
0x180018677  mov     rax, [rcx]
0x18001867a  lea     rdx, [rsp+0A8h+var_64]
0x18001867f  mov     rax, [rax+78h]
0x180018683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018688  mov     rcx, [rsp+0A8h]; this
0x180018690  test    eax, eax
0x180018692  js      loc_180018A62
0x180018698  cmp     [rsp+0A8h+var_64], 0
0x18001869d  setnz   al
0x1800186a0  mov     [r14+98h], al
0x1800186a7  mov     qword ptr [rsp+0A8h+FileTime1.dwLowDateTime], rsi
0x1800186ac  mov     rcx, [rdi]
0x1800186af  mov     rax, [rcx]
0x1800186b2  lea     rdx, [rsp+0A8h+FileTime1]
0x1800186b7  mov     rax, [rax+20h]
0x1800186bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c0  mov     rcx, [rsp+0A8h]; this
0x1800186c8  test    eax, eax
0x1800186ca  js      loc_180018A77
0x1800186d0  lea     rdx, [r14+90h]; lpFileTime2
0x1800186d7  lea     rcx, [rsp+0A8h+FileTime1]; lpFileTime1
0x1800186dc  call    cs:__imp_CompareFileTime
0x1800186e2  test    eax, eax
0x1800186e4  js      loc_180018C5B
0x1800186ea  mov     rcx, [rdi]
0x1800186ed  mov     rax, [rcx]
0x1800186f0  lea     rdx, [rsp+0A8h+var_68]
0x1800186f5  mov     rax, [rax+88h]
0x1800186fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018701  mov     rcx, [rsp+0A8h]; this
0x180018709  test    eax, eax
0x18001870b  js      loc_180018A8C
0x180018711  cmp     [rsp+0A8h+var_68], 1
0x180018716  jg      loc_180018C6C
0x18001871c  mov     rax, [rsp+0A8h+arg_10]
0x180018724  cmp     qword ptr [rax], 0
0x180018728  jz      loc_180018B5F
0x18001872e  mov     rcx, [rsp+0A8h+Src]; pv
0x180018733  test    rcx, rcx
0x180018736  jz      short loc_18001874E
0x180018738  call    cs:__imp_CoTaskMemFree
0x18001873e  jmp     short loc_18001874E
0x180018740  cmp     byte ptr [rsp+0A8h+arg_20], 0
0x180018748  jnz     loc_18001894D
0x18001874e  mov     eax, [rsp+0A8h+var_68]
0x180018752  mov     [r14+0A8h], eax
0x180018759  add     rsp, 70h
0x18001875d  pop     r15
0x18001875f  pop     r14
0x180018761  pop     r13
0x180018763  pop     r12
0x180018765  pop     rdi
0x180018766  pop     rsi
0x180018767  pop     rbx
0x180018768  retn
0x180018769  mov     rsi, [r15]
0x18001876c  mov     [r15+10h], rdx
0x180018770  lea     rbx, [rdx+rdx]
0x180018774  mov     r8, rbx; Size
0x180018777  mov     rdx, r9; Src
0x18001877a  mov     rcx, rsi; void *
0x18001877d  call    memmove_0
0x180018782  xor     eax, eax
0x180018784  mov     [rsi+rbx], ax
0x180018788  mov     rsi, [rsp+0A8h+arg_8]
0x180018790  xor     ebx, ebx
0x180018792  mov     qword ptr [rsp+0A8h+FileTime1.dwLowDateTime], rbx
0x180018797  mov     rcx, [r13+0]
0x18001879b  mov     rax, [rcx]
0x18001879e  lea     rdx, [rsp+0A8h+FileTime1]
0x1800187a3  mov     rax, [rax+20h]
0x1800187a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ac  mov     rcx, [rsp+0A8h]; this
0x1800187b4  test    eax, eax
0x1800187b6  js      loc_1800189BA
0x1800187bc  mov     rax, qword ptr [rsp+0A8h+FileTime1.dwLowDateTime]
0x1800187c1  mov     [r14+90h], rax
0x1800187c8  mov     rcx, [r13+0]
0x1800187cc  mov     rax, [rcx]
0x1800187cf  lea     rdx, [r14+0A0h]
0x1800187d6  mov     rax, [rax+48h]
0x1800187da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187df  mov     rcx, [rsp+0A8h]; this
0x1800187e7  test    eax, eax
0x1800187e9  js      loc_1800189CF
0x1800187ef  mov     dword ptr [rsp+0A8h+var_58], ebx
0x1800187f3  mov     rcx, [r13+0]
0x1800187f7  mov     rax, [rcx]
0x1800187fa  lea     rdx, [rsp+0A8h+var_58]
0x1800187ff  mov     rax, [rax+90h]
0x180018806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001880b  mov     rcx, [rsp+0A8h]; this
0x180018813  test    eax, eax
0x180018815  js      loc_1800189E4
0x18001881b  cmp     dword ptr [rsp+0A8h+var_58], 0
0x180018820  setnz   al
0x180018823  lea     r12, [r14+98h]
0x18001882a  mov     [r12], al
0x18001882e  mov     dword ptr [rsp+0A8h+var_60], ebx
0x180018832  mov     rcx, [r13+0]
0x180018836  mov     rax, [rcx]
0x180018839  lea     r8, [rsp+0A8h+var_60]
0x18001883e  lea     rdx, [r14+0A4h]
0x180018845  mov     rax, [rax+30h]
0x180018849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001884e  mov     rcx, [rsp+0A8h]; this
0x180018856  test    eax, eax
0x180018858  js      loc_1800189F9
0x18001885e  cmp     dword ptr [r14+0A4h], 10000000h
0x180018869  jle     loc_180018BB2
0x18001886f  xor     ebx, ebx
0x180018871  mov     [r14+9Ch], ebx
0x180018878  mov     rcx, [r13+0]
0x18001887c  mov     rax, [rcx]
0x18001887f  lea     r8, [rsp+0A8h+var_40]
0x180018884  mov     edx, 7F000000h
0x180018889  mov     rax, [rax+70h]
0x18001888d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018892  mov     rcx, [rsp+0A8h]; this
0x18001889a  test    eax, eax
0x18001889c  js      loc_180018A0E
0x1800188a2  call    IsCompareContentIdPresent
0x1800188a7  test    al, al
0x1800188a9  jnz     loc_180018AA1
0x1800188af  mov     rsi, [rsi]
0x1800188b2  mov     rax, [rsi]
0x1800188b5  mov     r13, [rax+68h]
0x1800188b9  lea     rbx, [r14+88h]
0x1800188c0  mov     rcx, [rbx]
0x1800188c3  test    rcx, rcx
0x1800188c6  jz      short loc_1800188DC
0x1800188c8  mov     qword ptr [rbx], 0
0x1800188cf  mov     rax, [rcx]
0x1800188d2  mov     rax, [rax+10h]
0x1800188d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188db  nop
0x1800188dc  cmp     qword ptr [r15+18h], 7
0x1800188e1  jbe     short loc_1800188E6
0x1800188e3  mov     r15, [r15]
0x1800188e6  mov     [rsp+0A8h+Format], rbx; int
0x1800188eb  mov     r9, [rsp+0A8h+arg_18]
0x1800188f3  mov     r9, [r9]
0x1800188f6  mov     rax, [rsp+0A8h+arg_10]
0x1800188fe  mov     r8, [rax]
0x180018901  mov     rdx, r15
0x180018904  mov     rcx, rsi
0x180018907  mov     rax, r13
0x18001890a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890f  cmp     eax, 803F7007h
0x180018914  jz      short loc_180018926
0x180018916  mov     rcx, [rsp+0A8h]; this
0x18001891e  test    eax, eax
0x180018920  js      loc_180018A23
0x180018926  mov     rcx, [rsp+0A8h+Src]; pv
0x18001892b  test    rcx, rcx
0x18001892e  jz      short loc_180018936
0x180018930  call    cs:__imp_CoTaskMemFree
0x180018936  mov     r13, [rsp+0A8h+arg_10]
0x18001893e  mov     rax, [rsp+0A8h+arg_18]
0x180018946  xor     ebx, ebx
0x180018948  jmp     loc_180018588
0x18001894d  cmp     byte ptr [r12], 0
0x180018952  jz      loc_18001874E
0x180018958  mov     rcx, [r13+0]
0x18001895c  test    rcx, rcx
0x18001895f  jz      loc_18001874E
0x180018965  mov     dword ptr [rsp+0A8h+arg_10], ebx
0x18001896c  mov     rax, [rcx]
0x18001896f  lea     rdx, [rsp+0A8h+arg_10]
0x180018977  mov     rax, [rax+58h]
0x18001897b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018980  test    eax, eax
0x180018982  jns     loc_180018D2A
0x180018988  mov     rcx, [rsp+0A8h]; this
0x180018990  mov     r9d, eax; char *
0x180018993  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001899a  mov     edx, 20Bh; void *
0x18001899f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189a5  mov     r9d, eax; char *
0x1800189a8  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800189af  mov     edx, 18Dh; void *
0x1800189b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189ba  mov     r9d, eax; char *
0x1800189bd  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800189c4  mov     edx, 192h; void *
0x1800189c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189cf  mov     r9d, eax; char *
0x1800189d2  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800189d9  mov     edx, 195h; void *
0x1800189de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189e4  mov     r9d, eax; char *
0x1800189e7  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800189ee  mov     edx, 198h; void *
0x1800189f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800189f9  mov     r9d, eax; char *
0x1800189fc  lea     r8, aOnecoreuapEndu_27; "onecoreuap\\enduser\\winstore\\licensem"...
0x180018a03  mov     edx, 19Ch; void *
0x180018a08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
