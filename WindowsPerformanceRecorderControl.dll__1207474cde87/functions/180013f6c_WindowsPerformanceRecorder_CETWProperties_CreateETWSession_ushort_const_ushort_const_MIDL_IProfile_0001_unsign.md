# WindowsPerformanceRecorder::CETWProperties::CreateETWSession(ushort const *,ushort const *,__MIDL_IProfile_0001,unsigned __int64,WindowsPerformanceRecorder::CETWProperties::CEventSession * *,ushort const *,bool,ushort const *)

- ea: `0x180013f6c`
- end: `0x1800147f6`
- name: `?CreateETWSession@CETWProperties@WindowsPerformanceRecorder@@CAJPEBG0W4__MIDL_IProfile_0001@@_KPEAPEAUCEventSession@12@0_N0@Z`
- size: `2186`
- prototype: `__int64 __fastcall(_WORD *, __int64, int, __int64, __int64, __int64, char, __int64)`
- caller_count: `6`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cc4`
- `0x1800195b0`
- `0x180024074`
- `0x180064880`
- `0x180064944`
- `0x1800649e0`

## callees

- `0x180008330`
- `0x18000a01c`
- `0x18000a0f0`
- `0x18000eeb0`
- `0x180011280`
- `0x1800112f0`
- `0x1800138c0`
- `0x180013f6c`
- `0x180015e2c`
- `0x18001e6e0`
- `0x180020fa0`
- `0x180024598`
- `0x18002a618`
- `0x18002a6b4`
- `0x18002f0e4`
- `0x18003567c`
- `0x180044210`
- `0x180044e24`
- `0x1800493a0`
- `0x18004a758`
- `0x18004ed10`
- `0x18004f8ce`
- `0x18004f964`
- `0x1800519b4`
- `0x180056898`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014453`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014470`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014453`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014470`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x1800141d4`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x1800141d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014327`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014358`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800141eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014327`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014358`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800143b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800143b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014077`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800142ae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800145d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014077`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800142ae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800145d5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014636`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014636`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180014190`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180014190`

## string_xrefs

- `0x1800142fd`: `COMGUARD`
- `0x180014312`: `CreateETWSession`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::CreateETWSession(
        _WORD *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        __int64 a8)
{
  __int64 v9; // rdi
  char *v10; // r15
  _DWORD *v11; // r14
  __int64 v12; // rbx
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  int v16; // ebx
  wchar_t *v18; // r8
  __int64 v19; // rax
  int v20; // edx
  wchar_t *v21; // rdi
  wchar_t *v22; // rax
  wchar_t *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // r12
  int v26; // eax
  __int64 v27; // rcx
  unsigned __int64 v28; // r12
  signed int FileNameWithTag; // esi
  int v30; // eax
  size_t v31; // rdi
  __int64 v32; // rbx
  void *v34; // rax
  GUID v35; // xmm0
  char *v36; // r14
  __int64 v37; // rdx
  __int16 *v38; // r8
  __int64 v39; // rax
  _WORD *v40; // rcx
  __int16 v41; // r9
  __int64 v42; // rdx
  wchar_t *v43; // rdi
  HINSTANCE StringResourceInstance; // rax
  __int64 v45; // rbx
  unsigned __int64 v46; // r13
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // r12
  wchar_t *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rbx
  __int16 *v53; // r8
  int v54; // r10d
  __int64 v55; // rax
  _WORD *v56; // rdx
  __int64 v57; // r9
  __int16 v58; // cx
  __int64 v59; // rcx
  const char *v60; // [rsp+28h] [rbp-80h]
  unsigned int v61; // [rsp+30h] [rbp-78h]
  unsigned int v62; // [rsp+30h] [rbp-78h]
  char *v63; // [rsp+38h] [rbp-70h] BYREF
  wchar_t *Path; // [rsp+40h] [rbp-68h] BYREF
  _DWORD *v65; // [rsp+48h] [rbp-60h] BYREF
  wchar_t *v66; // [rsp+50h] [rbp-58h]
  __int64 v67; // [rsp+58h] [rbp-50h]

  v67 = -2;
  v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v10 = (char *)v9;
  v63 = (char *)v9;
  v11 = (_DWORD *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v65 = v11;
  if ( !a1 )
    goto LABEL_17;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  if ( (_DWORD)v12 )
  {
    v13 = *(unsigned int *)(v9 - 16);
    if ( (int)((*(_DWORD *)(v9 - 12) - v12) | (1 - *(_DWORD *)(v9 - 8))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v63, v12);
      v10 = v63;
    }
    v14 = ((__int64)a1 - v9) >> 1;
    v15 = 2LL * (int)v12;
    if ( v14 > v13 )
    {
      if ( v15 )
      {
        if ( v10 )
        {
          memcpy_0(v10, a1, 2LL * (int)v12);
        }
        else
        {
          *(_DWORD *)_o__errno(v14, a1) = 22;
          invalid_parameter_noinfo();
        }
      }
    }
    else
    {
      memmove_s(v10, 2LL * (int)v12, &v10[2 * v14], 2LL * (int)v12);
    }
    if ( (int)v12 < 0 || (int)v12 > *((_DWORD *)v10 - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *((_DWORD *)v10 - 4) = v12;
    *(_WORD *)&v10[v15] = 0;
  }
  else
  {
LABEL_17:
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v63);
    v10 = v63;
  }
  if ( !WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(a1) )
  {
    v16 = WindowsPerformanceRecorder::AddPrefixToSessionName(&v63);
    if ( v16 < 0 )
    {
LABEL_20:
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v65);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v63);
      return (unsigned int)v16;
    }
    v10 = v63;
  }
  v18 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Path = v18;
  if ( a6 )
  {
    ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(&Path);
    v18 = Path;
  }
  if ( v10 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v10[2 * v19] );
  }
  else
  {
    LODWORD(v19) = 0;
  }
  v20 = *((_DWORD *)v18 - 4) + v19 + 1;
  if ( ((*((_DWORD *)v18 - 3) - v20) | (1 - *((_DWORD *)v18 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&Path, v20);
    v18 = Path;
  }
  PathAppendW(v18, (LPCWSTR)v10);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&Path);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddExtension(&Path);
  v66 = 0;
  v21 = Path;
  if ( *((int *)Path - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&Path, *((unsigned int *)Path - 4));
    v21 = Path;
  }
  v22 = _wfullpath(0, v21, 0);
  v23 = v22;
  v66 = v22;
  if ( !v22 )
  {
    free(0);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v65);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v63);
    return 2147500037LL;
  }
  v24 = -1;
  do
    ++v24;
  while ( v22[v24] );
  if ( (_DWORD)v24 )
  {
    v61 = *(v11 - 4);
    v25 = (char *)v22 - (char *)v11;
    v26 = *(v11 - 3) - v24;
    v27 = v26 | (unsigned int)(1 - *(v11 - 2));
    if ( (v26 | (1 - *(v11 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v65, v24);
      v11 = v65;
    }
    v28 = v25 >> 1;
    if ( v28 > v61 )
    {
      if ( 2LL * (int)v24 )
      {
        if ( v11 )
        {
          memcpy_0(v11, v23, 2LL * (int)v24);
        }
        else
        {
          *(_DWORD *)_o__errno(v27, 0) = 22;
          invalid_parameter_noinfo();
        }
      }
    }
    else
    {
      memmove_s(v11, 2LL * (int)v24, (char *)v11 + 2 * v28, 2LL * (int)v24);
    }
    if ( (int)v24 < 0 || (int)v24 > *(v11 - 3) )
      ATL::AtlThrowImpl(-2147024809);
    *(v11 - 4) = v24;
    *((_WORD *)v11 + (int)v24) = 0;
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v65);
  }
  FileNameWithTag = WindowsPerformanceRecorder::Impl::GetFileNameWithTag(&v65, a8);
  if ( FileNameWithTag < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"CreateETWSession",
      (const char *)0x1B5,
      FileNameWithTag,
      "COMGUARD",
      v60);
    free(v23);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&Path);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v65);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v63);
    return (unsigned int)FileNameWithTag;
  }
  free(v23);
  v30 = _InterlockedDecrement((volatile signed __int32 *)v21 - 2);
  if ( v30 <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v31 = a4 + 4248;
    v66 = (wchar_t *)operator new(0xD8u);
    v32 = WindowsPerformanceRecorder::CETWProperties::CEventSession::CEventSession((WindowsPerformanceRecorder::CETWProperties::CEventSession *)v66);
    *(_QWORD *)a5 = v32;
    v34 = malloc(a4 + 4248);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(2, std::bad_alloc `RTTI Type Descriptor', &loc_1800147A6);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v65);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v63);
      return 2147942414LL;
    }
  }
  *(_QWORD *)(v32 + 8) = v34;
  if ( !v34 )
  {
    v16 = -2147024882;
    goto LABEL_20;
  }
  memset_0(*(void **)(*(_QWORD *)a5 + 8LL), 0, v31);
  **(_DWORD **)(*(_QWORD *)a5 + 8LL) = v31;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 44LL) = 0x20000;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 40LL) = 1;
  if ( a7
    && Performance::COSVersionInfo::IsWindows10AndUp()
    && Performance::COSVersionInfo::GetOSVersionInfo()->dwBuildNumber >= 0x4512 )
  {
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 44LL) |= 0x800000u;
    *(_QWORD *)(*(_QWORD *)a5 + 16LL) = *(_QWORD *)(*(_QWORD *)a5 + 8LL);
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)a5 + 16LL) + 120LL) = 2;
  }
  if ( (unsigned int)_o__wcsicmp(v10, L"Circular Kernel Context Logger") )
  {
    if ( (unsigned int)_o__wcsicmp(v10, L"NT Kernel Logger") )
      goto LABEL_64;
    v35 = SystemTraceControlGuid;
  }
  else
  {
    v35 = (GUID)CKCLGuid;
  }
  *(GUID *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 24LL) = v35;
LABEL_64:
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 116LL) = 144;
  v36 = (char *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + *(unsigned int *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 116LL));
  v37 = 2147483646;
  v38 = (__int16 *)v10;
  v39 = 1024;
  v40 = v36;
  while ( v37 )
  {
    v41 = *v38;
    if ( *v38 )
    {
      ++v38;
      *v40++ = v41;
      --v37;
      if ( --v39 )
        continue;
    }
    if ( !v39 )
    {
      *(v40 - 1) = 0;
LABEL_104:
      v16 = -2147024774;
      goto LABEL_20;
    }
    break;
  }
  *v40 = 0;
  v43 = (wchar_t *)(((__int64 (__fastcall *)(void ***, __int64, __int16 *))ATL::g_strmgr[3])(&ATL::g_strmgr, v37, v38)
                  + 24);
  Path = v43;
  if ( !v36 )
    goto LABEL_89;
  if ( (unsigned __int64)v36 < 0x10000 )
  {
    StringResourceInstance = ATL::AtlFindStringResourceInstance((unsigned __int16)v36, v42);
    if ( !StringResourceInstance )
      goto LABEL_91;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      &Path,
      StringResourceInstance,
      (unsigned __int16)v36);
    goto LABEL_90;
  }
  v45 = -1;
  do
    ++v45;
  while ( *(_WORD *)&v36[2 * v45] );
  if ( !(_DWORD)v45 )
  {
LABEL_89:
    ATL::CSimpleStringT<unsigned short,0>::Empty(&Path);
LABEL_90:
    v43 = Path;
    goto LABEL_91;
  }
  v62 = *((_DWORD *)v43 - 4);
  v46 = (v36 - (char *)v43) >> 1;
  v47 = *((_DWORD *)v43 - 3) - v45;
  v48 = v47 | (unsigned int)(1 - *((_DWORD *)v43 - 2));
  if ( (v47 | (1 - *((_DWORD *)v43 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&Path, v45);
    v43 = Path;
  }
  v49 = (int)v45;
  if ( v46 > v62 )
  {
    if ( v49 * 2 )
    {
      if ( v43 )
      {
        memcpy_0(v43, v36, 2LL * (int)v45);
      }
      else
      {
        *(_DWORD *)_o__errno(v48, v42) = 22;
        invalid_parameter_noinfo();
      }
    }
  }
  else
  {
    memmove_s(v43, 2LL * (int)v45, &v43[v46], 2LL * (int)v45);
  }
  if ( (int)v45 < 0 || (int)v45 > *((_DWORD *)v43 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v43 - 4) = v45;
  v43[v49] = 0;
LABEL_91:
  if ( a1 && *((int *)v43 - 4) >= 0 )
  {
    v50 = wcsstr(v43, a1);
    if ( v50 )
      v51 = v50 - v43;
    else
      LODWORD(v51) = -1;
    if ( (_DWORD)v51 != -1 )
      v36 += 2 * (int)v51;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v43 - 12));
  *(_QWORD *)(*(_QWORD *)a5 + 192LL) = v36;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 112LL) = 2192;
  v52 = (__int64)v65;
  v53 = (__int16 *)v65;
  v54 = 1024;
  v55 = 1024;
  v56 = (_WORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + *(unsigned int *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 112LL));
  v57 = 2147483646;
  while ( v57 )
  {
    v58 = *v53;
    if ( *v53 )
    {
      ++v53;
      *v56++ = v58;
      --v57;
      if ( --v55 )
        continue;
    }
    if ( !v55 )
    {
      *(v56 - 1) = 0;
      goto LABEL_104;
    }
    break;
  }
  *v56 = 0;
  if ( a3 == 2 )
    v54 = 1;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 64LL) = v54;
  if ( Performance::COSVersionInfo::IsWin8AndUp() )
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 64LL) |= 0x800000u;
  if ( Performance::COSVersionInfo::IsWin81AndUp() )
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 64LL) |= 0x8000000u;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 72LL) = 0x80000000;
  v59 = *(_QWORD *)(*(_QWORD *)a5 + 8LL);
  *(_BYTE *)(v59 + 74) = -1;
  *(_WORD *)(v59 + 72) = 4240;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a5 + 8LL) + 4240LL) = 1;
  if ( _InterlockedDecrement((volatile signed __int32 *)(v52 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v52 - 24) + 8LL))(*(_QWORD *)(v52 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)v10 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  return 0;
}

```

## disassembly

```asm
0x180013f6c  mov     rax, rsp
0x180013f6f  mov     [rax+20h], r9
0x180013f73  mov     [rax+18h], r8d
0x180013f77  mov     [rax+10h], rdx
0x180013f7b  mov     [rax+8], rcx
0x180013f7f  push    rbx
0x180013f80  push    rsi
0x180013f81  push    rdi
0x180013f82  push    r12
0x180013f84  push    r13
0x180013f86  push    r14
0x180013f88  push    r15
0x180013f8a  sub     rsp, 70h
0x180013f8e  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x180013f96  mov     rsi, rdx
0x180013f99  mov     r13, rcx
0x180013f9c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013fa3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013faa  mov     rax, [rax+18h]
0x180013fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fb3  lea     rdi, [rax+18h]
0x180013fb7  mov     r15, rdi
0x180013fba  mov     [rsp+0A8h+var_70], rdi
0x180013fbf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013fc6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013fcd  mov     rax, [rax+18h]
0x180013fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd6  lea     r14, [rax+18h]
0x180013fda  mov     [rsp+0A8h+var_60], r14
0x180013fdf  xor     ebx, ebx
0x180013fe1  or      r12, 0FFFFFFFFFFFFFFFFh
0x180013fe5  test    r13, r13
0x180013fe8  jz      loc_1800140B3
0x180013fee  mov     rbx, r12
0x180013ff1  xor     eax, eax
0x180013ff3  inc     rbx
0x180013ff6  cmp     [r13+rbx*2+0], ax
0x180013ffc  jnz     short loc_180013FF3
0x180013ffe  test    ebx, ebx
0x180014000  jz      loc_1800140B1
0x180014006  mov     esi, [rdi-10h]
0x180014009  mov     r13d, 1
0x18001400f  mov     ecx, r13d
0x180014012  sub     ecx, [rdi-8]
0x180014015  mov     eax, [rdi-0Ch]
0x180014018  sub     eax, ebx
0x18001401a  or      ecx, eax
0x18001401c  jge     short loc_18001402F
0x18001401e  mov     edx, ebx
0x180014020  lea     rcx, [rsp+0A8h+var_70]
0x180014025  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001402a  mov     r15, [rsp+0A8h+var_70]
0x18001402f  mov     rdx, [rsp+0A8h+Src]; Src
0x180014037  mov     rcx, rdx
0x18001403a  sub     rcx, rdi
0x18001403d  sar     rcx, 1
0x180014040  movsxd  rax, ebx
0x180014043  lea     rdi, [rax+rax]
0x180014047  cmp     rcx, rsi
0x18001404a  ja      short loc_180014060
0x18001404c  lea     r8, [r15+rcx*2]; Source
0x180014050  mov     r9, rdi; SourceSize
0x180014053  mov     rdx, rdi; DestinationSize
0x180014056  mov     rcx, r15; Destination
0x180014059  call    memmove_s
0x18001405e  jmp     short loc_180014088
0x180014060  test    rdi, rdi
0x180014063  jz      short loc_180014088
0x180014065  test    r15, r15
0x180014068  jz      short loc_180014077
0x18001406a  mov     r8, rdi; Size
0x18001406d  mov     rcx, r15; void *
0x180014070  call    memcpy_0
0x180014075  jmp     short loc_180014088
0x180014077  call    cs:__imp__o__errno
0x18001407d  mov     dword ptr [rax], 16h
0x180014083  call    _invalid_parameter_noinfo
0x180014088  test    ebx, ebx
0x18001408a  js      short loc_1800140A7
0x18001408c  cmp     ebx, [r15-0Ch]
0x180014090  jg      short loc_1800140A7
0x180014092  mov     [r15-10h], ebx
0x180014096  xor     ebx, ebx
0x180014098  mov     [rdi+r15], bx
0x18001409d  mov     rsi, [rsp+0A8h+arg_8]
0x1800140a5  jmp     short loc_1800140C8
0x1800140a7  mov     ecx, 80070057h; int
0x1800140ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800140b1  xor     ebx, ebx
0x1800140b3  lea     rcx, [rsp+0A8h+var_70]
0x1800140b8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800140bd  mov     r13d, 1
0x1800140c3  mov     r15, [rsp+0A8h+var_70]
0x1800140c8  mov     rcx, [rsp+0A8h+Src]; unsigned __int16 *
0x1800140d0  call    ?IsLegacySystemCollectorName@CSystemCollectorElement@WindowsPerformanceRecorder@@SA_NPEBG@Z; WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(ushort const *)
0x1800140d5  test    al, al
0x1800140d7  jnz     short loc_18001410F
0x1800140d9  mov     rdx, rsi
0x1800140dc  lea     rcx, [rsp+0A8h+var_70]; void *
0x1800140e1  call    ?AddPrefixToSessionName@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::AddPrefixToSessionName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x1800140e6  mov     ebx, eax
0x1800140e8  test    eax, eax
0x1800140ea  jns     short loc_180014108
0x1800140ec  lea     rcx, [rsp+0A8h+var_60]; this
0x1800140f1  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800140f6  nop
0x1800140f7  lea     rcx, [rsp+0A8h+var_70]; this
0x1800140fc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180014101  mov     eax, ebx
0x180014103  jmp     loc_1800147E6
0x180014108  mov     r15, [rsp+0A8h+var_70]
0x18001410d  xor     ebx, ebx
0x18001410f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014116  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001411d  mov     rax, [rax+18h]
0x180014121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014126  lea     r8, [rax+18h]
0x18001412a  mov     [rsp+0A8h+Path], r8
0x18001412f  mov     rdx, [rsp+0A8h+arg_28]
0x180014137  test    rdx, rdx
0x18001413a  jz      short loc_18001414B
0x18001413c  lea     rcx, [rsp+0A8h+Path]
0x180014141  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x180014146  mov     r8, [rsp+0A8h+Path]
0x18001414b  mov     ecx, [r8-10h]
0x18001414f  test    r15, r15
0x180014152  jnz     short loc_180014158
0x180014154  mov     eax, ebx
0x180014156  jmp     short loc_180014165
0x180014158  mov     rax, r12
0x18001415b  inc     rax
0x18001415e  cmp     [r15+rax*2], bx
0x180014163  jnz     short loc_18001415B
0x180014165  lea     edx, [rax+1]
0x180014168  add     edx, ecx
0x18001416a  mov     ecx, r13d
0x18001416d  sub     ecx, [r8-8]
0x180014171  mov     eax, [r8-0Ch]
0x180014175  sub     eax, edx
0x180014177  or      ecx, eax
0x180014179  jge     short loc_18001418A
0x18001417b  lea     rcx, [rsp+0A8h+Path]
0x180014180  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180014185  mov     r8, [rsp+0A8h+Path]
0x18001418a  mov     rdx, r15; pszMore
0x18001418d  mov     rcx, r8; pszPath
0x180014190  call    cs:__imp_PathAppendW
0x180014196  lea     rcx, [rsp+0A8h+Path]
0x18001419b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x1800141a0  lea     rcx, [rsp+0A8h+Path]
0x1800141a5  call    ?AddExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddExtension(ushort const *)
0x1800141aa  mov     [rsp+0A8h+var_58], rbx
0x1800141af  mov     rdi, [rsp+0A8h+Path]
0x1800141b4  cmp     [rdi-8], r13d
0x1800141b8  jle     short loc_1800141CC
0x1800141ba  mov     edx, [rdi-10h]
0x1800141bd  lea     rcx, [rsp+0A8h+Path]
0x1800141c2  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x1800141c7  mov     rdi, [rsp+0A8h+Path]
0x1800141cc  xor     r8d, r8d; BufferCount
0x1800141cf  mov     rdx, rdi; Path
0x1800141d2  xor     ecx, ecx; Buffer
0x1800141d4  call    cs:__imp__wfullpath
0x1800141da  mov     rbx, rax
0x1800141dd  mov     [rsp+0A8h+var_58], rax
0x1800141e2  xor     edx, edx
0x1800141e4  test    rax, rax
0x1800141e7  jnz     short loc_18001421C
0x1800141e9  xor     ecx, ecx; Block
0x1800141eb  call    cs:__imp_free
0x1800141f1  nop
0x1800141f2  lea     rcx, [rsp+0A8h+Path]; this
0x1800141f7  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800141fc  nop
0x1800141fd  lea     rcx, [rsp+0A8h+var_60]; this
0x180014202  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180014207  nop
0x180014208  lea     rcx, [rsp+0A8h+var_70]; this
0x18001420d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180014212  mov     eax, 80004005h
0x180014217  jmp     loc_1800147E6
0x18001421c  mov     rsi, r12
0x18001421f  inc     rsi
0x180014222  cmp     [rax+rsi*2], dx
0x180014226  jnz     short loc_18001421F
0x180014228  test    esi, esi
0x18001422a  jnz     short loc_18001423B
0x18001422c  lea     rcx, [rsp+0A8h+var_60]
0x180014231  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180014236  jmp     loc_1800142E5
0x18001423b  mov     eax, [r14-10h]
0x18001423f  mov     [rsp+0A8h+var_78], eax
0x180014243  mov     r12, rbx
0x180014246  sub     r12, r14
0x180014249  mov     ecx, r13d
0x18001424c  sub     ecx, [r14-8]
0x180014250  mov     eax, [r14-0Ch]
0x180014254  sub     eax, esi
0x180014256  or      ecx, eax
0x180014258  jge     short loc_18001426D
0x18001425a  mov     edx, esi
0x18001425c  lea     rcx, [rsp+0A8h+var_60]
0x180014261  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180014266  mov     r14, [rsp+0A8h+var_60]
0x18001426b  xor     edx, edx
0x18001426d  sar     r12, 1
0x180014270  movsxd  rax, esi
0x180014273  lea     r13, [rax+rax]
0x180014277  mov     eax, [rsp+0A8h+var_78]
0x18001427b  cmp     r12, rax
0x18001427e  ja      short loc_180014294
0x180014280  lea     r8, [r14+r12*2]; Source
0x180014284  mov     r9, r13; SourceSize
0x180014287  mov     rdx, r13; DestinationSize
0x18001428a  mov     rcx, r14; Destination
0x18001428d  call    memmove_s
0x180014292  jmp     short loc_1800142BF
0x180014294  test    r13, r13
0x180014297  jz      short loc_1800142C1
0x180014299  test    r14, r14
0x18001429c  jz      short loc_1800142AE
0x18001429e  mov     r8, r13; Size
0x1800142a1  mov     rdx, rbx; Src
0x1800142a4  mov     rcx, r14; void *
0x1800142a7  call    memcpy_0
0x1800142ac  jmp     short loc_1800142BF
0x1800142ae  call    cs:__imp__o__errno
0x1800142b4  mov     dword ptr [rax], 16h
0x1800142ba  call    _invalid_parameter_noinfo
0x1800142bf  xor     edx, edx
0x1800142c1  test    esi, esi
0x1800142c3  js      loc_1800147C2
0x1800142c9  cmp     esi, [r14-0Ch]
0x1800142cd  jg      loc_1800147C2
0x1800142d3  mov     [r14-10h], esi
0x1800142d7  mov     [r14+r13], dx
0x1800142dc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800142e0  lea     r13d, [r12+2]
0x1800142e5  mov     rdx, [rsp+0A8h+arg_38]
0x1800142ed  lea     rcx, [rsp+0A8h+var_60]
0x1800142f2  call    ?GetFileNameWithTag@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::Impl::GetFileNameWithTag(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x1800142f7  mov     esi, eax
0x1800142f9  test    eax, eax
0x1800142fb  jns     short loc_180014355
0x1800142fd  lea     rax, aComguard; "COMGUARD"
0x180014304  mov     [rsp+0A8h+Format], rax; Format
0x180014309  mov     r9d, esi; unsigned int
0x18001430c  mov     r8d, 1B5h; char *
0x180014312  lea     rdx, aCreateetwsessi; "CreateETWSession"
0x180014319  mov     ecx, 2; this
0x18001431e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180014323  nop
0x180014324  mov     rcx, rbx; Block
0x180014327  call    cs:__imp_free
0x18001432d  nop
0x18001432e  lea     rcx, [rsp+0A8h+Path]; this
0x180014333  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180014338  nop
0x180014339  lea     rcx, [rsp+0A8h+var_60]; this
0x18001433e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180014343  nop
0x180014344  lea     rcx, [rsp+0A8h+var_70]; this
0x180014349  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001434e  mov     eax, esi
0x180014350  jmp     loc_1800147E6
0x180014355  mov     rcx, rbx; Block
0x180014358  call    cs:__imp_free
0x18001435e  nop
0x18001435f  lea     rdx, [rdi-18h]
0x180014363  mov     eax, r12d
0x180014366  lock xadd [rdx+10h], eax
0x18001436b  add     eax, r12d
0x18001436e  test    eax, eax
0x180014370  jg      short loc_180014382
0x180014372  mov     rcx, [rdx]
0x180014375  mov     rax, [rcx]
0x180014378  mov     rax, [rax+8]
0x18001437c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014381  nop
0x180014382  mov     rdi, [rsp+0A8h+arg_18]
0x18001438a  add     rdi, 1098h
0x180014391  mov     ecx, 0D8h; Size
0x180014396  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001439b  mov     [rsp+0A8h+var_58], rax
0x1800143a0  mov     rcx, rax; this
0x1800143a3  call    ??0CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::CEventSession(void)
0x1800143a8  mov     rbx, rax
0x1800143ab  mov     rsi, [rsp+0A8h+arg_20]
0x1800143b3  mov     [rsi], rax
0x1800143b6  mov     rcx, rdi; Size
0x1800143b9  call    cs:__imp_malloc
0x1800143bf  mov     [rbx+8], rax
0x1800143c3  xor     ebx, ebx
0x1800143c5  test    rax, rax
0x1800143c8  jnz     short loc_1800143D4
0x1800143ca  mov     ebx, 8007000Eh
0x1800143cf  jmp     loc_1800146CD
0x1800143d4  mov     rcx, [rsi]
0x1800143d7  mov     r8, rdi; Size
0x1800143da  xor     edx, edx; Val
  ... truncated ...
```
