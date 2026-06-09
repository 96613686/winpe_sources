# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x1800140dc`
- end: `0x1800147ed`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1809`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013f50`

## callees

- `0x18000139c`
- `0x1800067f0`
- `0x18000c048`
- `0x18000ce70`
- `0x18000d728`
- `0x18000d7e8`
- `0x18000d908`
- `0x180011024`
- `0x180011120`
- `0x180012df4`
- `0x1800130a8`
- `0x180013b7c`
- `0x1800140dc`
- `0x1800157a0`
- `0x1800268f4`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `msvcrt!free` at `0x18001452c`
- `msvcrt!free` at `0x18001467c`
- `msvcrt!free` at `0x18001469e`
- `msvcrt!free` at `0x18001452c`
- `msvcrt!free` at `0x18001467c`
- `msvcrt!free` at `0x18001469e`
- `KERNEL32!GetProcAddress` at `0x180014171`
- `KERNEL32!GetProcAddress` at `0x180014171`
- `KERNEL32!FreeLibrary` at `0x180014209`
- `KERNEL32!FreeLibrary` at `0x1800143f9`
- `KERNEL32!FreeLibrary` at `0x180014209`
- `KERNEL32!FreeLibrary` at `0x1800143f9`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800146bd`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800146bd`
- `KERNEL32!LoadLibraryExW` at `0x180014156`
- `KERNEL32!LoadLibraryExW` at `0x180014156`

## string_xrefs

- `0x1800144c4`: `_NT_SYMBOL_PATH`
- `0x1800144fc`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`
- `0x18001413f`: `mscoree.dll`
- `0x180014167`: `CLRCreateInstance`
- `0x180014483`: `XPERF_NGenPdbsPath`
- `0x18001476a`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  __int64 v2; // rbx
  HMODULE Library; // rsi
  FARPROC ProcAddress; // rax
  int v5; // edi
  unsigned __int16 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned __int16 v9; // di
  __int64 v10; // rax
  _QWORD *v12; // rbx
  int v13; // eax
  unsigned int Error; // ebx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // edi
  _QWORD *v18; // rdx
  int v19; // eax
  _QWORD *v20; // rdx
  unsigned __int64 v21; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  _QWORD *v24; // rdi
  int v25; // edx
  int v26; // ecx
  __int64 v27; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+70h] [rbp-98h] BYREF
  int v35; // [rsp+78h] [rbp-90h] BYREF
  int v36; // [rsp+7Ch] [rbp-8Ch] BYREF
  __int64 v37; // [rsp+80h] [rbp-88h] BYREF
  __int64 v38; // [rsp+88h] [rbp-80h] BYREF
  int v39; // [rsp+98h] [rbp-70h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-68h]
  __int64 v41; // [rsp+A8h] [rbp-60h]
  void *v42; // [rsp+B0h] [rbp-58h]
  void *v43; // [rsp+B8h] [rbp-50h]
  void *v44; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-40h]
  __int64 v46; // [rsp+D0h] [rbp-38h]
  int v47; // [rsp+D8h] [rbp-30h]
  __int64 v48; // [rsp+E0h] [rbp-28h]
  int v49; // [rsp+E8h] [rbp-20h] BYREF
  void *Block; // [rsp+F0h] [rbp-18h]
  __int64 v51; // [rsp+F8h] [rbp-10h]
  __int64 v52; // [rsp+100h] [rbp-8h]
  int v53; // [rsp+108h] [rbp+0h]
  __int64 v54; // [rsp+110h] [rbp+8h]
  int v55; // [rsp+118h] [rbp+10h]
  __int64 v56; // [rsp+120h] [rbp+18h]
  __int64 v57; // [rsp+128h] [rbp+20h]
  __int64 v58; // [rsp+130h] [rbp+28h]
  __int64 v59; // [rsp+138h] [rbp+30h]
  HMODULE v60; // [rsp+140h] [rbp+38h]
  const WCHAR *v61; // [rsp+148h] [rbp+40h]
  __int64 v62; // [rsp+150h] [rbp+48h]
  char v63; // [rsp+158h] [rbp+50h]
  __int16 v64; // [rsp+160h] [rbp+58h] BYREF
  unsigned __int16 v65; // [rsp+162h] [rbp+5Ah]
  __int16 v66; // [rsp+164h] [rbp+5Ch]
  WCHAR Buffer[264]; // [rsp+1A8h] [rbp+A0h] BYREF
  _WORD v68[264]; // [rsp+3B8h] [rbp+2B0h] BYREF

  v56 = -2;
  v2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v33 = v2;
  v61 = L"mscoree.dll";
  v62 = 0;
  Library = LoadLibraryExW(L"mscoree.dll", 0, 0);
  v60 = Library;
  v63 = 1;
  ProcAddress = GetProcAddress(Library, "CLRCreateInstance");
  if ( !ProcAddress )
  {
    v5 = -2147467259;
LABEL_9:
    if ( Library )
      FreeLibrary(Library);
    goto LABEL_42;
  }
  v32 = 0;
  v5 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v32);
  if ( v5 < 0 )
  {
LABEL_7:
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    goto LABEL_9;
  }
  v31 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v31);
  if ( v5 < 0 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    goto LABEL_7;
  }
  v30 = 0;
  LODWORD(v27) = 0;
  v6 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v31 + 24LL))(v31, 1, &v30, &v27) >= 0 )
  {
    do
    {
      if ( (_DWORD)v27 != 1 )
        break;
      v7 = v30;
      v30 = 0;
      v57 = v7;
      v8 = 0;
      v28 = 0;
      if ( v7 )
      {
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v28);
        v8 = v28;
      }
      if ( v8 )
      {
        LODWORD(v29) = 30;
        if ( (*(int (__fastcall **)(__int64, __int16 *, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v64, &v29) >= 0
          && (unsigned int)v29 >= 3
          && ((v64 - 86) & 0xFFDF) == 0 )
        {
          v9 = v65;
          if ( (unsigned __int16)(v65 - 52) <= 5u && v66 == 46 && v65 > v6 )
          {
            v35 = 260;
            if ( (*(int (__fastcall **)(__int64, _WORD *, int *))(*(_QWORD *)v28 + 32LL))(v28, v68, &v35) >= 0 )
            {
              v10 = -1;
              do
                ++v10;
              while ( v68[v10] );
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v68, (unsigned int)v10);
              v6 = v9;
            }
          }
        }
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    while ( (*(int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v31 + 24LL))(v31, 1, &v30, &v27) >= 0 );
    v2 = v33;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( Library )
    FreeLibrary(Library);
  if ( !*(_DWORD *)(v2 - 16) )
  {
    v5 = -2147467259;
LABEL_42:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return (unsigned int)v5;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 40,
    &v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 48,
    &v33);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
  v12 = (_QWORD *)((char *)this + 56);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 56,
                        L"XPERF_NGenPdbsPath")
    || !*(_DWORD *)(*v12 - 16LL) )
  {
    v34 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v34,
                         L"_NT_SYMBOL_PATH") )
    {
      Block = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      v55 = 1;
      v49 = 0;
      v13 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(
              &v49,
              L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})");
      if ( v13 )
      {
        Error = -2147418113;
        if ( v13 == 1 )
          Error = -2147024882;
        if ( Block )
          free(Block);
        goto LABEL_83;
      }
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      v39 = 0;
      v48 = 0;
      if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&v44, 256) )
      {
        ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
        v45 = 256;
      }
      v40 = 0;
      v41 = 0;
      v36 = 0;
      v37 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      while ( 1 )
      {
        v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &v34,
                &v38,
                v15,
                &v36);
        v17 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                       &v37,
                                       v16)
                        - 16LL);
        v18 = (_QWORD *)(v38 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v38 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
        if ( !v17 )
          break;
        if ( v37 )
          v19 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v49, v37, &v39);
        else
          v19 = 0;
        if ( v19 )
        {
          if ( !v39 )
            ATL::AtlThrowImpl(-2147467259);
          v58 = *(_QWORD *)v43;
          v59 = *((_QWORD *)v43 + 1);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 56, v58, (unsigned int)((v59 - v58) >> 1));
          break;
        }
      }
      v20 = (_QWORD *)(v37 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v37 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
      if ( v44 )
        free(v44);
      operator delete(v43);
      operator delete(v42);
      if ( Block )
        free(Block);
    }
    if ( !*(_DWORD *)(*v12 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
LABEL_83:
        v22 = (_QWORD *)(v34 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
        return Error;
      }
      v21 = -1;
      do
        ++v21;
      while ( Buffer[v21] );
      if ( v21 < 2 || Buffer[1] != 58 )
      {
        Error = -2147418113;
        goto LABEL_83;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v23 = (_QWORD *)(v34 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
  }
  v24 = (_QWORD *)((char *)this + 64);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 64,
                        L"XPERF_NGenPdbsCachePath")
    || !*(_DWORD *)(*v24 - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (char *)this + 64,
      (char *)this + 56);
  }
  *((_BYTE *)this + 32) = 1;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    Template_zzzz(v26, v25, *v12, *v24, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
  return 0;
}

```

## disassembly

```asm
0x1800140dc  mov     rax, rsp
0x1800140df  push    rbp
0x1800140e0  push    r12
0x1800140e2  push    r13
0x1800140e4  push    r14
0x1800140e6  push    r15
0x1800140e8  lea     rbp, [rax-4F8h]
0x1800140ef  sub     rsp, 5D0h
0x1800140f6  mov     [rbp+4F0h+var_4D8], 0FFFFFFFFFFFFFFFEh
0x1800140fe  mov     [rax+10h], rbx
0x180014102  mov     [rax+18h], rsi
0x180014106  mov     [rax+20h], rdi
0x18001410a  mov     rax, cs:__security_cookie
0x180014111  xor     rax, rsp
0x180014114  mov     [rbp+4F0h+var_30], rax
0x18001411b  mov     r15, rcx
0x18001411e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014125  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001412c  mov     rax, [rax+18h]
0x180014130  call    cs:__guard_dispatch_icall_fptr
0x180014136  lea     rbx, [rax+18h]
0x18001413a  mov     [rsp+5F0h+var_590], rbx
0x18001413f  lea     rcx, aMscoreeDll; "mscoree.dll"
0x180014146  mov     [rbp+4F0h+var_4B0], rcx
0x18001414a  xor     r12d, r12d
0x18001414d  mov     [rbp+4F0h+var_4A8], r12
0x180014151  xor     r8d, r8d; dwFlags
0x180014154  xor     edx, edx; hFile
0x180014156  call    cs:__imp_LoadLibraryExW
0x18001415c  mov     rsi, rax
0x18001415f  mov     [rbp+4F0h+var_4B8], rax
0x180014163  mov     [rbp+4F0h+var_4A0], 1
0x180014167  lea     rdx, aClrcreateinsta; "CLRCreateInstance"
0x18001416e  mov     rcx, rax; hModule
0x180014171  call    cs:__imp_GetProcAddress
0x180014177  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001417b  test    rax, rax
0x18001417e  jnz     short loc_180014187
0x180014180  mov     edi, 80004005h
0x180014185  jmp     short loc_1800141FD
0x180014187  mov     [rsp+5F0h+var_598], r12
0x18001418c  lea     r8, [rsp+5F0h+var_598]
0x180014191  lea     rdx, IID_ICLRMetaHost
0x180014198  lea     rcx, CLSID_CLRMetaHost
0x18001419f  call    cs:__guard_dispatch_icall_fptr
0x1800141a5  mov     edi, eax
0x1800141a7  test    eax, eax
0x1800141a9  js      short loc_1800141E5
0x1800141ab  mov     [rsp+5F0h+var_5A0], r12
0x1800141b0  mov     rcx, [rsp+5F0h+var_598]
0x1800141b5  mov     rax, [rcx]
0x1800141b8  lea     rdx, [rsp+5F0h+var_5A0]
0x1800141bd  mov     rax, [rax+28h]
0x1800141c1  call    cs:__guard_dispatch_icall_fptr
0x1800141c7  mov     edi, eax
0x1800141c9  test    eax, eax
0x1800141cb  jns     short loc_180014214
0x1800141cd  mov     rcx, [rsp+5F0h+var_5A0]
0x1800141d2  test    rcx, rcx
0x1800141d5  jz      short loc_1800141E5
0x1800141d7  mov     rax, [rcx]
0x1800141da  mov     rax, [rax+10h]
0x1800141de  call    cs:__guard_dispatch_icall_fptr
0x1800141e4  nop
0x1800141e5  mov     rcx, [rsp+5F0h+var_598]
0x1800141ea  test    rcx, rcx
0x1800141ed  jz      short loc_1800141FD
0x1800141ef  mov     rax, [rcx]
0x1800141f2  mov     rax, [rax+10h]
0x1800141f6  call    cs:__guard_dispatch_icall_fptr
0x1800141fc  nop
0x1800141fd  test    rsi, rsi
0x180014200  jz      loc_18001440A
0x180014206  mov     rcx, rsi; hLibModule
0x180014209  call    cs:__imp_FreeLibrary
0x18001420f  jmp     loc_18001440A
0x180014214  mov     [rsp+5F0h+var_5A8], r12
0x180014219  mov     dword ptr [rsp+5F0h+var_5C0], r12d
0x18001421e  movzx   r14d, r12w
0x180014222  mov     rcx, [rsp+5F0h+var_5A0]
0x180014227  mov     rax, [rcx]
0x18001422a  lea     r9, [rsp+5F0h+var_5C0]
0x18001422f  lea     r8, [rsp+5F0h+var_5A8]
0x180014234  mov     edx, 1
0x180014239  mov     rax, [rax+18h]
0x18001423d  call    cs:__guard_dispatch_icall_fptr
0x180014243  test    eax, eax
0x180014245  js      loc_1800143A9
0x18001424b  cmp     dword ptr [rsp+5F0h+var_5C0], 1
0x180014250  jnz     loc_1800143A4
0x180014256  mov     rbx, [rsp+5F0h+var_5A8]
0x18001425b  mov     [rsp+5F0h+var_5A8], r12
0x180014260  mov     [rbp+4F0h+var_4D0], rbx
0x180014264  mov     rcx, r12
0x180014267  mov     [rsp+5F0h+var_5B8], rcx
0x18001426c  test    rbx, rbx
0x18001426f  jz      short loc_180014291
0x180014271  mov     rax, [rbx]
0x180014274  lea     r8, [rsp+5F0h+var_5B8]
0x180014279  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x180014280  mov     rcx, rbx
0x180014283  mov     rax, [rax]
0x180014286  call    cs:__guard_dispatch_icall_fptr
0x18001428c  mov     rcx, [rsp+5F0h+var_5B8]
0x180014291  test    rcx, rcx
0x180014294  jnz     short loc_18001429B
0x180014296  jmp     loc_180014366
0x18001429b  mov     dword ptr [rsp+5F0h+var_5B0], 1Eh
0x1800142a3  mov     rax, [rcx]
0x1800142a6  lea     r8, [rsp+5F0h+var_5B0]
0x1800142ab  lea     rdx, [rbp+4F0h+var_498]
0x1800142af  mov     rax, [rax+18h]
0x1800142b3  call    cs:__guard_dispatch_icall_fptr
0x1800142b9  test    eax, eax
0x1800142bb  js      loc_18001434E
0x1800142c1  cmp     dword ptr [rsp+5F0h+var_5B0], 3
0x1800142c6  jb      loc_18001434E
0x1800142cc  movzx   eax, [rbp+4F0h+var_498]
0x1800142d0  sub     ax, 56h ; 'V'
0x1800142d4  mov     ecx, 0FFDFh
0x1800142d9  test    cx, ax
0x1800142dc  jnz     short loc_18001434E
0x1800142de  movzx   edi, [rbp+4F0h+var_496]
0x1800142e2  lea     eax, [rdi-34h]
0x1800142e5  cmp     ax, 5
0x1800142e9  ja      short loc_18001434E
0x1800142eb  cmp     [rbp+4F0h+var_494], 2Eh ; '.'
0x1800142f0  jnz     short loc_18001434E
0x1800142f2  cmp     di, r14w
0x1800142f6  jbe     short loc_18001434E
0x1800142f8  mov     dword ptr [rsp+5F0h+var_580], 104h
0x180014300  mov     rcx, [rsp+5F0h+var_5B8]
0x180014305  mov     rax, [rcx]
0x180014308  lea     r8, [rsp+5F0h+var_580]
0x18001430d  lea     rdx, [rbp+4F0h+var_240]
0x180014314  mov     rax, [rax+20h]
0x180014318  call    cs:__guard_dispatch_icall_fptr
0x18001431e  test    eax, eax
0x180014320  js      short loc_18001434E
0x180014322  lea     rcx, [rbp+4F0h+var_240]
0x180014329  mov     rax, r13
0x18001432c  inc     rax
0x18001432f  cmp     [rcx+rax*2], r12w
0x180014334  jnz     short loc_18001432C
0x180014336  mov     r8d, eax
0x180014339  lea     rdx, [rbp+4F0h+var_240]
0x180014340  lea     rcx, [rsp+5F0h+var_590]
0x180014345  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001434a  movzx   r14d, di
0x18001434e  mov     rcx, [rsp+5F0h+var_5B8]
0x180014353  test    rcx, rcx
0x180014356  jz      short loc_180014366
0x180014358  mov     rax, [rcx]
0x18001435b  mov     rax, [rax+10h]
0x18001435f  call    cs:__guard_dispatch_icall_fptr
0x180014365  nop
0x180014366  test    rbx, rbx
0x180014369  jz      short loc_18001437B
0x18001436b  mov     rax, [rbx]
0x18001436e  mov     rcx, rbx
0x180014371  mov     rax, [rax+10h]
0x180014375  call    cs:__guard_dispatch_icall_fptr
0x18001437b  mov     rcx, [rsp+5F0h+var_5A0]
0x180014380  mov     rax, [rcx]
0x180014383  lea     r9, [rsp+5F0h+var_5C0]
0x180014388  lea     r8, [rsp+5F0h+var_5A8]
0x18001438d  mov     edx, 1
0x180014392  mov     rax, [rax+18h]
0x180014396  call    cs:__guard_dispatch_icall_fptr
0x18001439c  test    eax, eax
0x18001439e  jns     loc_18001424B
0x1800143a4  mov     rbx, [rsp+5F0h+var_590]
0x1800143a9  mov     rcx, [rsp+5F0h+var_5A8]
0x1800143ae  test    rcx, rcx
0x1800143b1  jz      short loc_1800143C1
0x1800143b3  mov     rax, [rcx]
0x1800143b6  mov     rax, [rax+10h]
0x1800143ba  call    cs:__guard_dispatch_icall_fptr
0x1800143c0  nop
0x1800143c1  mov     rcx, [rsp+5F0h+var_5A0]
0x1800143c6  test    rcx, rcx
0x1800143c9  jz      short loc_1800143D9
0x1800143cb  mov     rax, [rcx]
0x1800143ce  mov     rax, [rax+10h]
0x1800143d2  call    cs:__guard_dispatch_icall_fptr
0x1800143d8  nop
0x1800143d9  mov     rcx, [rsp+5F0h+var_598]
0x1800143de  test    rcx, rcx
0x1800143e1  jz      short loc_1800143F1
0x1800143e3  mov     rax, [rcx]
0x1800143e6  mov     rax, [rax+10h]
0x1800143ea  call    cs:__guard_dispatch_icall_fptr
0x1800143f0  nop
0x1800143f1  test    rsi, rsi
0x1800143f4  jz      short loc_1800143FF
0x1800143f6  mov     rcx, rsi; hLibModule
0x1800143f9  call    cs:__imp_FreeLibrary
0x1800143ff  cmp     [rbx-10h], r12d
0x180014403  jnz     short loc_180014434
0x180014405  mov     edi, 80004005h
0x18001440a  lea     rdx, [rbx-18h]
0x18001440e  mov     ecx, r13d
0x180014411  lock xadd [rdx+10h], ecx
0x180014416  add     ecx, r13d
0x180014419  test    ecx, ecx
0x18001441b  jg      short loc_18001442D
0x18001441d  mov     rcx, [rdx]
0x180014420  mov     r8, [rcx]
0x180014423  mov     rax, [r8+8]
0x180014427  call    cs:__guard_dispatch_icall_fptr
0x18001442d  mov     eax, edi
0x18001442f  jmp     loc_1800147BD
0x180014434  lea     rsi, [r15+28h]
0x180014438  lea     rdx, [rsp+5F0h+var_590]
0x18001443d  mov     rcx, rsi
0x180014440  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014445  mov     rcx, rsi
0x180014448  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18001444d  lea     rdx, [rsp+5F0h+var_590]
0x180014452  lea     rcx, [r15+30h]
0x180014456  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001445b  nop
0x18001445c  lea     rdx, [rbx-18h]
0x180014460  mov     eax, r13d
0x180014463  lock xadd [rdx+10h], eax
0x180014468  add     eax, r13d
0x18001446b  test    eax, eax
0x18001446d  jg      short loc_18001447F
0x18001446f  mov     rcx, [rdx]
0x180014472  mov     rax, [rcx]
0x180014475  mov     rax, [rax+8]
0x180014479  call    cs:__guard_dispatch_icall_fptr
0x18001447f  lea     rbx, [r15+38h]
0x180014483  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x18001448a  mov     rcx, rbx
0x18001448d  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180014492  test    eax, eax
0x180014494  jz      short loc_1800144A3
0x180014496  mov     rax, [rbx]
0x180014499  cmp     [rax-10h], r12d
0x18001449d  jnz     loc_180014766
0x1800144a3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800144aa  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800144b1  mov     rax, [rax+18h]
0x1800144b5  call    cs:__guard_dispatch_icall_fptr
0x1800144bb  add     rax, 18h
0x1800144bf  mov     [rsp+5F0h+var_588], rax
0x1800144c4  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x1800144cb  lea     rcx, [rsp+5F0h+var_588]
0x1800144d0  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800144d5  test    eax, eax
0x1800144d7  jz      loc_1800146A4
0x1800144dd  mov     [rbp+4F0h+Block], r12
0x1800144e1  mov     [rbp+4F0h+var_500], r12
0x1800144e5  mov     [rbp+4F0h+var_4F8], r12
0x1800144e9  mov     [rbp+4F0h+var_4F0], r12d
0x1800144ed  mov     [rbp+4F0h+var_4E8], r12
0x1800144f1  mov     [rbp+4F0h+var_4E0], 1
0x1800144f8  mov     [rbp+4F0h+var_510], r12d
0x1800144fc  lea     rdx, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180014503  lea     rcx, [rbp+4F0h+var_510]
0x180014507  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x18001450c  test    eax, eax
0x18001450e  jz      short loc_180014537
0x180014510  cmp     eax, 1
0x180014513  mov     ebx, 8000FFFFh
0x180014518  jnz     short loc_18001451F
0x18001451a  mov     ebx, 8007000Eh
0x18001451f  mov     rcx, [rbp+4F0h+Block]; Block
0x180014523  test    rcx, rcx
0x180014526  jz      loc_180014712
0x18001452c  call    cs:__imp_free
0x180014532  jmp     loc_180014712
0x180014537  mov     [rbp+4F0h+var_548], r12
0x18001453b  mov     [rbp+4F0h+var_540], r12
0x18001453f  mov     [rbp+4F0h+var_538], r12
0x180014543  mov     [rbp+4F0h+var_530], r12
0x180014547  mov     [rbp+4F0h+var_528], r12
0x18001454b  mov     [rbp+4F0h+var_520], r12d
0x18001454f  mov     [rbp+4F0h+var_560], r12d
0x180014553  mov     [rbp+4F0h+var_518], r12
0x180014557  mov     edi, 100h
0x18001455c  mov     edx, edi
0x18001455e  lea     rcx, [rbp+4F0h+var_538]
0x180014562  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x180014567  test    al, al
0x180014569  jz      short loc_180014574
0x18001456b  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x180014570  mov     [rbp+4F0h+var_530], rdi
0x180014574  mov     [rbp+4F0h+var_558], r12
0x180014578  mov     [rbp+4F0h+var_550], r12
0x18001457c  mov     dword ptr [rsp+5F0h+var_580+4], r12d
0x180014581  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014588  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001458f  mov     rax, [rax+18h]
0x180014593  call    cs:__guard_dispatch_icall_fptr
0x180014599  add     rax, 18h
0x18001459d  mov     [rsp+5F0h+var_578], rax
0x1800145a2  lea     r9, [rsp+5F0h+var_580+4]
0x1800145a7  lea     rdx, [rbp+4F0h+var_570]
  ... truncated ...
```
