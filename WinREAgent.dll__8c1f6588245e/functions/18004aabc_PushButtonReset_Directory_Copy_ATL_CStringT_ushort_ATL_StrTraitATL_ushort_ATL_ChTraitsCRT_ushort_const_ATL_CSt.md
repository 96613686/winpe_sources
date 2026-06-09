# PushButtonReset::Directory::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)

- ea: `0x18004aabc`
- end: `0x18004b353`
- name: `?Copy@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z`
- size: `2199`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180006de8`
- `0x18004aabc`

## callees

- `0x180003c68`
- `0x1800049a4`
- `0x180004af8`
- `0x1800050bc`
- `0x180005c70`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180037344`
- `0x18004a898`
- `0x18004aabc`
- `0x18004b35c`
- `0x18004b674`
- `0x18004bb04`
- `0x18004c914`
- `0x18004cef4`
- `0x18004d404`
- `0x18004e144`
- `0x18004eb3c`
- `0x18006c633`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004b213`
- `KERNEL32!GetLastError` at `0x18004b257`
- `KERNEL32!GetLastError` at `0x18004b213`
- `KERNEL32!GetLastError` at `0x18004b257`
- `KERNEL32!GetFileAttributesW` at `0x18004b1f1`
- `KERNEL32!GetFileAttributesW` at `0x18004b1f1`
- `KERNEL32!SetFileAttributesW` at `0x18004b205`
- `KERNEL32!SetFileAttributesW` at `0x18004b205`

## string_xrefs

- `0x18004b22f`: `Failed to copy attributes from [%s] to [%s]`
- `0x18004ae52`: `Failed to construct path to [%s] under [%s]`
- `0x18004ae9a`: `Failed to construct path to [%s] under [%s]`
- `0x18004b096`: `Failed to construct path to [%s] under [%s]`
- `0x18004b0e2`: `Failed to construct path to [%s] under [%s]`
- `0x18004ac0b`: `PushButtonReset::Directory::Copy`
- `0x18004ac3e`: `PushButtonReset::Directory::Copy`
- `0x18004aca4`: `PushButtonReset::Directory::Copy`
- `0x18004acd4`: `PushButtonReset::Directory::Copy`
- `0x18004abf0`: `Failed to create target path [%s]`
- `0x18004ad75`: `Failed to copy reparse point [%s] to [%s]`
- `0x18004adae`: `Failed to copy subdir [%s] to [%s]`
- `0x18004afd0`: `Failed to copy file [%s] to [%s]`
- `0x18004b153`: `Failed to get canonical form of source path [%s]`
- `0x18004b1b4`: `Failed to get canonical form of target path [%s]`
- `0x18004b2a6`: `Failed to copy security information`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall PushButtonReset::Directory::Copy(LPCWSTR *a1, LPCWSTR *a2, __int64 a3, char a4)
{
  unsigned __int64 v6; // r13
  __int64 v7; // rsi
  int Size; // ebx
  _QWORD *v9; // rax
  __int64 v10; // r8
  unsigned __int64 i; // rbx
  _QWORD *v12; // rdi
  int v13; // r13d
  __int64 v14; // r9
  int v15; // edi
  __int64 v16; // r8
  _QWORD *v17; // rdi
  int v18; // ecx
  int v19; // ecx
  int v20; // eax
  __int64 v21; // rbx
  LPCWSTR v22; // rdi
  void (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  LPCWSTR v24; // rbx
  ATL::CStringData *v25; // rcx
  __int64 v26; // rbx
  LPCWSTR v27; // rbx
  DWORD FileAttributesW; // eax
  LPCWSTR v29; // rdi
  signed int v30; // eax
  signed int LastError; // eax
  int v32; // esi
  __int64 v34; // [rsp+48h] [rbp-49h] BYREF
  __int64 v35; // [rsp+50h] [rbp-41h] BYREF
  LPCWSTR v36; // [rsp+58h] [rbp-39h] BYREF
  __int64 v37; // [rsp+60h] [rbp-31h] BYREF
  __int64 v38; // [rsp+68h] [rbp-29h] BYREF
  unsigned __int64 v39; // [rsp+70h] [rbp-21h]
  __int64 v40; // [rsp+78h] [rbp-19h]
  int v41; // [rsp+80h] [rbp-11h]
  __int64 v42; // [rsp+88h] [rbp-9h] BYREF
  unsigned __int64 v43; // [rsp+90h] [rbp-1h]
  __int64 v44; // [rsp+98h] [rbp+7h]
  int v45; // [rsp+A0h] [rbp+Fh]
  _QWORD v46[8]; // [rsp+A8h] [rbp+17h] BYREF
  LPCWSTR lpFileName; // [rsp+108h] [rbp+77h] BYREF
  int v49; // [rsp+110h] [rbp+7Fh]

  LOBYTE(v49) = a4;
  v6 = 0;
  v7 = 0;
  v46[1] = 0;
  v46[0] = &RAII::CAutoPbrDelete<PushButtonReset::OverallProgress *>::`vftable';
  if ( a3 )
  {
    v7 = _RTDynamicCast_0(
           a3,
           0,
           &PushButtonReset::ProgressCallback `RTTI Type Descriptor',
           &PushButtonReset::OverallProgress `RTTI Type Descriptor',
           0);
    if ( !v7 )
    {
      lpFileName = 0;
      Size = PushButtonReset::Directory::GetSize(a1, &lpFileName);
      if ( Size < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Size,
          "PushButtonReset::Directory::Copy",
          "base\\reset\\util\\src\\filesystem.cpp",
          2586,
          L"Failed to get size of [%s]",
          *a1);
        goto LABEL_65;
      }
      v9 = PbrHeapAlloc<void>(0x30u);
      v7 = (__int64)v9;
      if ( !v9 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "PushButtonReset::Directory::Copy",
          "base\\reset\\util\\src\\filesystem.cpp",
          2589,
          L"Failed to allocate overallProgress");
        Size = -2147024882;
        goto LABEL_65;
      }
      *v9 = &PushButtonReset::OverallProgress::`vftable';
      v9[1] = a3;
      v9[2] = 0;
      v9[3] = lpFileName;
      v9[4] = 0;
      v9[5] = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(v46[0] + 48LL))(v46, v9);
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&lpFileName,
    (__int64)&pszFormat);
  Size = PushButtonReset::Directory::Create(a2, 0, &lpFileName);
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  if ( Size < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "PushButtonReset::Directory::Copy",
      "base\\reset\\util\\src\\filesystem.cpp",
      2597,
      L"Failed to create target path [%s]",
      *a2);
    goto LABEL_65;
  }
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  Size = PushButtonReset::Directory::EnumSubdirs(a1, &v38);
  if ( Size < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "PushButtonReset::Directory::Copy",
      "base\\reset\\util\\src\\filesystem.cpp",
      2602,
      L"Failed to enumerate subdirs under [%s]",
      *a1);
    goto LABEL_13;
  }
  v49 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v39 )
    {
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      Size = PushButtonReset::Directory::EnumFiles(a1, &v42);
      if ( Size >= 0 )
      {
        while ( v6 < v43 )
        {
          v17 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                            &v42,
                            v6,
                            v16);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v37);
          v18 = PushButtonReset::Path::Combine(a1, v17, &v37);
          LODWORD(lpFileName) = v18;
          if ( v18 < 0 )
          {
            v26 = v37;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v18,
              "PushButtonReset::Directory::Copy",
              "base\\reset\\util\\src\\filesystem.cpp",
              2664,
              L"Failed to construct path to [%s] under [%s]",
              *v17,
              v37);
            v25 = (ATL::CStringData *)(v26 - 24);
            goto LABEL_48;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v36);
          v19 = PushButtonReset::Path::Combine(a2, v17, &v36);
          LODWORD(lpFileName) = v19;
          if ( v19 < 0 )
          {
            v24 = v36;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v19,
              "PushButtonReset::Directory::Copy",
              "base\\reset\\util\\src\\filesystem.cpp",
              2670,
              L"Failed to construct path to [%s] under [%s]",
              *v17,
              v36);
            ATL::CStringData::Release((ATL::CStringData *)(v24 - 12));
            v25 = (ATL::CStringData *)(v37 - 24);
LABEL_48:
            ATL::CStringData::Release(v25);
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v42);
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
            Size = (int)lpFileName;
            goto LABEL_65;
          }
          v20 = PushButtonReset::File::Copy(&v37, &v36, (void (__fastcall ***)(void *, __int64, __int64))v7);
          LODWORD(lpFileName) = v20;
          v21 = v37;
          v22 = v36;
          if ( v20 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v20,
              "PushButtonReset::Directory::Copy",
              "base\\reset\\util\\src\\filesystem.cpp",
              2677,
              L"Failed to copy file [%s] to [%s]",
              v37,
              v36);
            v49 = (int)lpFileName;
          }
          if ( v7 )
          {
            *(_QWORD *)(v7 + 16) += *(_QWORD *)(v7 + 40);
            *(_QWORD *)(v7 + 32) = 0;
            *(_QWORD *)(v7 + 40) = 0;
            v23 = *(void (__fastcall ****)(_QWORD, _QWORD, _QWORD))(v7 + 8);
            if ( v23 )
              (**v23)(v23, *(_QWORD *)(v7 + 16), *(_QWORD *)(v7 + 24));
            if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) )
            {
              ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v42);
              goto LABEL_28;
            }
          }
          ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
          ++v6;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
        Size = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
        if ( Size >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v36);
          Size = PushButtonReset::Path::GetCanonical(a2, &v36);
          if ( Size >= 0 )
          {
            v27 = lpFileName;
            FileAttributesW = GetFileAttributesW(lpFileName);
            v29 = v36;
            if ( FileAttributesW == -1 )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)LastError,
                "PushButtonReset::Directory::Copy",
                "base\\reset\\util\\src\\filesystem.cpp",
                2718,
                L"Failed to get file attributes for [%s]",
                v27);
            }
            else if ( !SetFileAttributesW(v36, FileAttributesW) )
            {
              v30 = GetLastError();
              if ( v30 > 0 )
                v30 = (unsigned __int16)v30 | 0x80070000;
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)v30,
                "PushButtonReset::Directory::Copy",
                "base\\reset\\util\\src\\filesystem.cpp",
                2711,
                L"Failed to copy attributes from [%s] to [%s]",
                v27,
                v29);
            }
            v32 = PushButtonReset::Directory::CopySecurity(a1, a2);
            if ( v32 >= 0 )
            {
              ATL::CStringData::Release((ATL::CStringData *)(v29 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v27 - 12));
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v42);
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
              Size = v49;
            }
            else
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v32,
                "PushButtonReset::Directory::Copy",
                "base\\reset\\util\\src\\filesystem.cpp",
                2725,
                L"Failed to copy security information");
              ATL::CStringData::Release((ATL::CStringData *)(v29 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v27 - 12));
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v42);
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
              Size = v32;
            }
            goto LABEL_65;
          }
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Size,
            "PushButtonReset::Directory::Copy",
            "base\\reset\\util\\src\\filesystem.cpp",
            2701,
            L"Failed to get canonical form of target path [%s]",
            *a2);
          ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Size,
            "PushButtonReset::Directory::Copy",
            "base\\reset\\util\\src\\filesystem.cpp",
            2696,
            L"Failed to get canonical form of source path [%s]",
            *a1);
        }
        ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Size,
          "PushButtonReset::Directory::Copy",
          "base\\reset\\util\\src\\filesystem.cpp",
          2654,
          L"Failed to enumerate files under [%s]",
          *a1);
      }
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v42);
LABEL_13:
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
      goto LABEL_65;
    }
    v12 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                      &v38,
                      i,
                      v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v34);
    v13 = PushButtonReset::Path::Combine(a1, v12, &v34);
    if ( v13 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v13,
        "PushButtonReset::Directory::Copy",
        "base\\reset\\util\\src\\filesystem.cpp",
        2612,
        L"Failed to construct path to [%s] under [%s]",
        *v12,
        v34);
      goto LABEL_31;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v35);
    v13 = PushButtonReset::Path::Combine(a2, v12, &v35);
    if ( v13 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v13,
        "PushButtonReset::Directory::Copy",
        "base\\reset\\util\\src\\filesystem.cpp",
        2618,
        L"Failed to construct path to [%s] under [%s]",
        *v12,
        v35);
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
LABEL_31:
      ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
      Size = v13;
      goto LABEL_65;
    }
    v6 = 0;
    if ( (unsigned __int8)PushButtonReset::Path::IsReparsePoint(&v34) )
    {
      v15 = PushButtonReset::File::Copy(&v34, &v35, 0);
      if ( v15 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v15,
          "PushButtonReset::Directory::Copy",
          "base\\reset\\util\\src\\filesystem.cpp",
          2627,
          L"Failed to copy reparse point [%s] to [%s]",
          v34,
          v35);
LABEL_23:
        v49 = v15;
      }
    }
    else
    {
      LOBYTE(v14) = 1;
      v15 = PushButtonReset::Directory::Copy(&v34, &v35, v7, v14);
      if ( v15 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v15,
          "PushButtonReset::Directory::Copy",
          "base\\reset\\util\\src\\filesystem.cpp",
          2639,
          L"Failed to copy subdir [%s] to [%s]",
          v34,
          v35);
        goto LABEL_23;
      }
    }
    if ( v7 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) )
      break;
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
  }
  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v34 - 24));
LABEL_28:
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v38);
  Size = -2147023673;
LABEL_65:
  v46[0] = &RAII::CAutoPbrDelete<PushButtonReset::OverallProgress *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v46);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18004aabc  mov     rax, rsp
0x18004aabf  mov     [rax+8], rbx
0x18004aac3  mov     [rax+20h], r9b
0x18004aac7  mov     [rax+10h], rdx
0x18004aacb  push    rbp
0x18004aacc  push    rsi
0x18004aacd  push    rdi
0x18004aace  push    r12
0x18004aad0  push    r13
0x18004aad2  push    r14
0x18004aad4  push    r15
0x18004aad6  lea     rbp, [rax-5Fh]
0x18004aada  sub     rsp, 0B0h
0x18004aae1  mov     rdi, r8
0x18004aae4  mov     r12, rcx
0x18004aae7  xor     r13d, r13d
0x18004aaea  mov     esi, r13d
0x18004aaed  mov     [rbp+57h+var_38], r13
0x18004aaf1  lea     rax, ??_7?$CAutoPbrDelete@PEAVOverallProgress@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::OverallProgress *>::`vftable'
0x18004aaf8  mov     [rbp+57h+var_40], rax
0x18004aafc  test    r8, r8
0x18004aaff  jz      loc_18004ABB2
0x18004ab05  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x18004ab0a  lea     r9, ??_R0?AVOverallProgress@PushButtonReset@@@8; PushButtonReset::OverallProgress `RTTI Type Descriptor'
0x18004ab11  lea     r8, ??_R0?AUProgressCallback@PushButtonReset@@@8; PushButtonReset::ProgressCallback `RTTI Type Descriptor'
0x18004ab18  xor     edx, edx
0x18004ab1a  mov     rcx, rdi
0x18004ab1d  call    __RTDynamicCast_0
0x18004ab22  mov     rsi, rax
0x18004ab25  test    rax, rax
0x18004ab28  jnz     loc_18004ABB2
0x18004ab2e  mov     [rbp+57h+lpFileName], r13
0x18004ab32  lea     rdx, [rbp+57h+lpFileName]
0x18004ab36  mov     rcx, r12
0x18004ab39  call    ?GetSize@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::Directory::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18004ab3e  mov     ebx, eax
0x18004ab40  test    eax, eax
0x18004ab42  jns     short loc_18004AB66
0x18004ab44  mov     rcx, [r12]
0x18004ab48  mov     [rsp+0E0h+var_B0], rcx
0x18004ab4d  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x18004ab54  mov     [rsp+0E0h+var_B8], rax
0x18004ab59  mov     dword ptr [rsp+0E0h+var_C0], 0A1Ah
0x18004ab61  jmp     loc_18004AC04
0x18004ab66  mov     ecx, 30h ; '0'
0x18004ab6b  call    ??$PbrHeapAlloc@X@@YAPEAX_K@Z; PbrHeapAlloc<void>(unsigned __int64)
0x18004ab70  mov     rsi, rax
0x18004ab73  test    rax, rax
0x18004ab76  jz      loc_18004AC23
0x18004ab7c  lea     rax, ??_7OverallProgress@PushButtonReset@@6B@; const PushButtonReset::OverallProgress::`vftable'
0x18004ab83  mov     [rsi], rax
0x18004ab86  mov     [rsi+8], rdi
0x18004ab8a  mov     [rsi+10h], r13
0x18004ab8e  mov     rax, [rbp+57h+lpFileName]
0x18004ab92  mov     [rsi+18h], rax
0x18004ab96  mov     [rsi+20h], r13
0x18004ab9a  mov     [rsi+28h], r13
0x18004ab9e  mov     rax, [rbp+57h+var_40]
0x18004aba2  mov     rdx, rsi
0x18004aba5  lea     rcx, [rbp+57h+var_40]
0x18004aba9  mov     rax, [rax+30h]
0x18004abad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abb2  lea     rdx, pszFormat
0x18004abb9  lea     rcx, [rbp+57h+lpFileName]
0x18004abbd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004abc2  nop
0x18004abc3  lea     r8, [rbp+57h+lpFileName]
0x18004abc7  xor     edx, edx
0x18004abc9  mov     rdi, [rbp+57h+arg_8]
0x18004abcd  mov     rcx, rdi
0x18004abd0  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004abd5  mov     ebx, eax
0x18004abd7  mov     rcx, [rbp+57h+lpFileName]
0x18004abdb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004abdf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004abe4  test    ebx, ebx
0x18004abe6  jns     short loc_18004AC5E
0x18004abe8  mov     rcx, [rdi]
0x18004abeb  mov     [rsp+0E0h+var_B0], rcx
0x18004abf0  lea     rax, aFailedToCreate_41; "Failed to create target path [%s]"
0x18004abf7  mov     [rsp+0E0h+var_B8], rax
0x18004abfc  mov     dword ptr [rsp+0E0h+var_C0], 0A25h
0x18004ac04  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ac0b  lea     r8, aPushbuttonrese_126; "PushButtonReset::Directory::Copy"
0x18004ac12  mov     edx, ebx
0x18004ac14  mov     ecx, 2
0x18004ac19  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ac1e  jmp     loc_18004B322
0x18004ac23  lea     rax, aFailedToAlloca_22; "Failed to allocate overallProgress"
0x18004ac2a  mov     [rsp+0E0h+var_B8], rax
0x18004ac2f  mov     dword ptr [rsp+0E0h+var_C0], 0A1Dh
0x18004ac37  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ac3e  lea     r8, aPushbuttonrese_126; "PushButtonReset::Directory::Copy"
0x18004ac45  mov     edx, 8007000Eh
0x18004ac4a  mov     ecx, 2
0x18004ac4f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ac54  mov     ebx, 8007000Eh
0x18004ac59  jmp     loc_18004B322
0x18004ac5e  mov     [rbp+57h+var_80], r13
0x18004ac62  mov     [rbp+57h+var_78], r13
0x18004ac66  mov     [rbp+57h+var_70], r13
0x18004ac6a  mov     [rbp+57h+var_68], r13d
0x18004ac6e  lea     rdx, [rbp+57h+var_80]
0x18004ac72  mov     rcx, r12
0x18004ac75  call    ?EnumSubdirs@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; PushButtonReset::Directory::EnumSubdirs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18004ac7a  mov     ebx, eax
0x18004ac7c  test    eax, eax
0x18004ac7e  jns     short loc_18004ACC6
0x18004ac80  mov     rcx, [r12]
0x18004ac84  mov     [rsp+0E0h+var_B0], rcx
0x18004ac89  lea     rax, aFailedToEnumer_6; "Failed to enumerate subdirs under [%s]"
0x18004ac90  mov     [rsp+0E0h+var_B8], rax
0x18004ac95  mov     dword ptr [rsp+0E0h+var_C0], 0A2Ah
0x18004ac9d  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004aca4  lea     r8, aPushbuttonrese_126; "PushButtonReset::Directory::Copy"
0x18004acab  mov     edx, ebx
0x18004acad  mov     ecx, 2
0x18004acb2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004acb7  nop
0x18004acb8  lea     rcx, [rbp+57h+var_80]
0x18004acbc  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18004acc1  jmp     loc_18004B322
0x18004acc6  mov     [rbp+57h+arg_18], r13d
0x18004acca  mov     rbx, r13
0x18004accd  lea     r14, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004acd4  lea     r15, aPushbuttonrese_126; "PushButtonReset::Directory::Copy"
0x18004acdb  cmp     rbx, [rbp+57h+var_78]
0x18004acdf  jnb     loc_18004AEE1
0x18004ace5  mov     rdx, rbx
0x18004ace8  lea     rcx, [rbp+57h+var_80]
0x18004acec  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18004acf1  mov     rdi, rax
0x18004acf4  lea     rcx, [rbp+57h+var_A0]
0x18004acf8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004acfd  nop
0x18004acfe  lea     r8, [rbp+57h+var_A0]
0x18004ad02  mov     rdx, rdi
0x18004ad05  mov     rcx, r12
0x18004ad08  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004ad0d  mov     r13d, eax
0x18004ad10  test    eax, eax
0x18004ad12  js      loc_18004AE89
0x18004ad18  lea     rcx, [rbp+57h+var_98]
0x18004ad1c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004ad21  nop
0x18004ad22  lea     r8, [rbp+57h+var_98]
0x18004ad26  mov     rdx, rdi
0x18004ad29  mov     rcx, [rbp+57h+arg_8]
0x18004ad2d  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004ad32  mov     r13d, eax
0x18004ad35  test    eax, eax
0x18004ad37  js      loc_18004AE41
0x18004ad3d  lea     rcx, [rbp+57h+var_A0]
0x18004ad41  call    ?IsReparsePoint@Path@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Path::IsReparsePoint(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004ad46  xor     r13d, r13d
0x18004ad49  lea     rdx, [rbp+57h+var_98]
0x18004ad4d  lea     rcx, [rbp+57h+var_A0]
0x18004ad51  test    al, al
0x18004ad53  jz      short loc_18004AD8B
0x18004ad55  xor     r8d, r8d
0x18004ad58  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x18004ad5d  mov     edi, eax
0x18004ad5f  test    eax, eax
0x18004ad61  jns     short loc_18004ADD7
0x18004ad63  mov     rcx, [rbp+57h+var_98]
0x18004ad67  mov     [rsp+38h], rcx
0x18004ad6c  mov     rcx, [rbp+57h+var_A0]
0x18004ad70  mov     [rsp+0E0h+var_B0], rcx
0x18004ad75  lea     rax, aFailedToCopyRe; "Failed to copy reparse point [%s] to [%"...
0x18004ad7c  mov     [rsp+0E0h+var_B8], rax
0x18004ad81  mov     dword ptr [rsp+0E0h+var_C0], 0A43h
0x18004ad89  jmp     short loc_18004ADC2
0x18004ad8b  mov     r9b, 1
0x18004ad8e  mov     r8, rsi
0x18004ad91  call    ?Copy@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::Directory::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x18004ad96  mov     edi, eax
0x18004ad98  test    eax, eax
0x18004ad9a  jns     short loc_18004ADD7
0x18004ad9c  mov     rcx, [rbp+57h+var_98]
0x18004ada0  mov     [rsp+38h], rcx
0x18004ada5  mov     rcx, [rbp+57h+var_A0]
0x18004ada9  mov     [rsp+0E0h+var_B0], rcx
0x18004adae  lea     rax, aFailedToCopySu; "Failed to copy subdir [%s] to [%s]"
0x18004adb5  mov     [rsp+0E0h+var_B8], rax
0x18004adba  mov     dword ptr [rsp+0E0h+var_C0], 0A4Fh
0x18004adc2  mov     r9, r14
0x18004adc5  mov     r8, r15
0x18004adc8  mov     edx, edi
0x18004adca  mov     ecx, 1
0x18004adcf  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004add4  mov     [rbp+57h+arg_18], edi
0x18004add7  test    rsi, rsi
0x18004adda  jz      short loc_18004ADEF
0x18004addc  mov     rax, [rsi]
0x18004addf  mov     rcx, rsi
0x18004ade2  mov     rax, [rax+8]
0x18004ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adeb  test    al, al
0x18004aded  jnz     short loc_18004AE12
0x18004adef  mov     rcx, [rbp+57h+var_98]
0x18004adf3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004adf7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004adfc  nop
0x18004adfd  mov     rcx, [rbp+57h+var_A0]
0x18004ae01  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004ae05  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ae0a  inc     rbx
0x18004ae0d  jmp     loc_18004ACDB
0x18004ae12  mov     rcx, [rbp+57h+var_98]
0x18004ae16  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004ae1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ae1f  nop
0x18004ae20  mov     rcx, [rbp+57h+var_A0]
0x18004ae24  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004ae28  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ae2d  nop
0x18004ae2e  lea     rcx, [rbp+57h+var_80]
0x18004ae32  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18004ae37  mov     ebx, 800704C7h
0x18004ae3c  jmp     loc_18004B322
0x18004ae41  mov     rax, [rbp+57h+var_98]
0x18004ae45  mov     [rsp+38h], rax
0x18004ae4a  mov     rax, [rdi]
0x18004ae4d  mov     [rsp+0E0h+var_B0], rax
0x18004ae52  lea     rax, aFailedToConstr_2; "Failed to construct path to [%s] under "...
0x18004ae59  mov     [rsp+0E0h+var_B8], rax
0x18004ae5e  mov     dword ptr [rsp+0E0h+var_C0], 0A3Ah
0x18004ae66  mov     r9, r14
0x18004ae69  mov     r8, r15
0x18004ae6c  mov     edx, r13d
0x18004ae6f  mov     ecx, 2
0x18004ae74  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ae79  nop
0x18004ae7a  mov     rcx, [rbp+57h+var_98]
0x18004ae7e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004ae82  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ae87  jmp     short loc_18004AEC2
0x18004ae89  mov     rax, [rbp+57h+var_A0]
0x18004ae8d  mov     [rsp+38h], rax
0x18004ae92  mov     rax, [rdi]
0x18004ae95  mov     [rsp+0E0h+var_B0], rax
0x18004ae9a  lea     rax, aFailedToConstr_2; "Failed to construct path to [%s] under "...
0x18004aea1  mov     [rsp+0E0h+var_B8], rax
0x18004aea6  mov     dword ptr [rsp+0E0h+var_C0], 0A34h
0x18004aeae  mov     r9, r14
0x18004aeb1  mov     r8, r15
0x18004aeb4  mov     edx, r13d
0x18004aeb7  mov     ecx, 2
0x18004aebc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004aec1  nop
0x18004aec2  mov     rcx, [rbp+57h+var_A0]
0x18004aec6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004aeca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004aecf  nop
0x18004aed0  lea     rcx, [rbp+57h+var_80]
0x18004aed4  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18004aed9  mov     ebx, r13d
0x18004aedc  jmp     loc_18004B322
0x18004aee1  mov     [rbp+57h+var_60], r13
0x18004aee5  mov     [rbp+57h+var_58], r13
0x18004aee9  mov     [rbp+57h+var_50], r13
0x18004aeed  mov     [rbp+57h+var_48], r13d
0x18004aef1  lea     rdx, [rbp+57h+var_60]
0x18004aef5  mov     rcx, r12
0x18004aef8  call    ?EnumFiles@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; PushButtonReset::Directory::EnumFiles(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18004aefd  mov     ebx, eax
0x18004aeff  test    eax, eax
0x18004af01  jns     short loc_18004AF41
0x18004af03  mov     rcx, [r12]
0x18004af07  mov     [rsp+0E0h+var_B0], rcx
0x18004af0c  lea     rax, aFailedToEnumer_14; "Failed to enumerate files under [%s]"
0x18004af13  mov     [rsp+0E0h+var_B8], rax
0x18004af18  mov     dword ptr [rsp+0E0h+var_C0], 0A5Eh
0x18004af20  mov     r9, r14
0x18004af23  mov     r8, r15
0x18004af26  mov     edx, ebx
0x18004af28  mov     ecx, 2
0x18004af2d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004af32  nop
0x18004af33  lea     rcx, [rbp+57h+var_60]
0x18004af37  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18004af3c  jmp     loc_18004ACB8
0x18004af41  cmp     r13, [rbp+57h+var_58]
0x18004af45  jnb     loc_18004B12E
0x18004af4b  mov     rdx, r13
0x18004af4e  lea     rcx, [rbp+57h+var_60]
0x18004af52  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18004af57  mov     rdi, rax
0x18004af5a  lea     rcx, [rbp+57h+var_88]
0x18004af5e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004af63  nop
0x18004af64  lea     r8, [rbp+57h+var_88]
0x18004af68  mov     rdx, rdi
0x18004af6b  mov     rcx, r12
0x18004af6e  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004af73  mov     ecx, eax
0x18004af75  mov     dword ptr [rbp+57h+lpFileName], eax
0x18004af78  test    eax, eax
0x18004af7a  js      loc_18004B0D1
0x18004af80  lea     rcx, [rbp+57h+var_90]
  ... truncated ...
```
