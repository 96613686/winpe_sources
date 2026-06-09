# Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile(ulong,ulong,Windows::Rtl::SIL_OBJECT_ATTRIBUTES const &,ulong,ulong,ulong,ulong,Windows::Auto<Windows::Rtl::IRtlFile *> *,ulong *)

- ea: `0x180171a60`
- end: `0x1801725f3`
- name: `?CreateNewFile@CDirectory@SystemImplementation@Rtl@Windows@@UEAAJKKAEBUSIL_OBJECT_ATTRIBUTES@34@KKKKPEAV?$Auto@PEAUIRtlFile@Rtl@Windows@@@4@PEAK@Z`
- size: `2963`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, int, int, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x180030b68`
- `0x180035f04`
- `0x180048f3c`
- `0x1800497c0`
- `0x180049c6c`
- `0x180117528`
- `0x1801189d4`
- `0x18011aed0`
- `0x18011c474`
- `0x180138770`
- `0x180171a60`
- `0x1801bd010`

## string_xrefs

- `0x180171be7`: `Valid flags check failed: ShareAccess`
- `0x180171c50`: `CreateOptions`
- `0x180171c1f`: `Valid flags check failed: CreateOptions`
- `0x180171b4a`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171b77`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171bd0`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171c08`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171c39`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171c7d`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171cb2`: `onecore\base\wcp\sil\directory.cpp`
- `0x180171f77`: `onecore\base\wcp\sil\directory.cpp`
- `0x180172018`: `onecore\base\wcp\sil\directory.cpp`
- `0x1801721d3`: `onecore\base\wcp\sil\directory.cpp`
- `0x18017225c`: `onecore\base\wcp\sil\directory.cpp`
- `0x1801721f1`: `ValidateForEnsureSetSecurity(DesiredAccess, CreateOptions, LocalObjectAttributes)`
- `0x18017227a`: `ValidateForEnsureSetAttributes(DesiredAccess, FileAttributes)`
- `0x180171af0`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x180171b3a`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x180171f85`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x180172023`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x1801721de`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x180172267`: `Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile`
- `0x180171f9e`: `!m_FileSystemProvider->IsUnbufferedSil()`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile(
        __int64 a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned int a7,
        int a8,
        void (__fastcall ****a9)(_QWORD),
        _DWORD *a10)
{
  int v11; // r14d
  _QWORD *v13; // rcx
  unsigned int v14; // ebx
  __int128 *v15; // rax
  int v16; // eax
  void (__fastcall ***v17)(_QWORD); // rcx
  void (__fastcall ***v18)(_QWORD); // rcx
  int inited; // eax
  void (__fastcall ***v20)(_QWORD); // rcx
  int v21; // eax
  void (__fastcall ***v22)(_QWORD); // rcx
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  int v26; // ecx
  unsigned int v27; // ebx
  void (__fastcall ***v28)(_QWORD); // rcx
  void (__fastcall ***v29)(_QWORD); // rcx
  int v30; // eax
  void (__fastcall ***v31)(_QWORD); // rcx
  void (__fastcall ***v32)(_QWORD); // rcx
  void (__fastcall ***v33)(_QWORD); // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  void (__fastcall ***v37)(_QWORD); // rcx
  int v38; // eax
  void (__fastcall ***v39)(_QWORD); // rcx
  void (__fastcall ****v41)(_QWORD); // rcx
  void (__fastcall ***v42)(_QWORD); // rbx
  void (__fastcall ***v43)(_QWORD); // rcx
  void (__fastcall ***v44)(_QWORD); // rcx
  unsigned __int64 v45; // [rsp+60h] [rbp-A8h]
  void (__fastcall ***v46)(_QWORD); // [rsp+88h] [rbp-80h] BYREF
  _BYTE v47[24]; // [rsp+90h] [rbp-78h] BYREF
  const char *v48; // [rsp+A8h] [rbp-60h]
  __int128 v49; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-48h]
  __int128 v51; // [rsp+C8h] [rbp-40h]
  __int64 v52; // [rsp+D8h] [rbp-30h]
  void (__fastcall ****v53)(_QWORD); // [rsp+E0h] [rbp-28h]
  _QWORD v54[4]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v55[4]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v56[4]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD v57[4]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v58[4]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD v59[4]; // [rsp+188h] [rbp+80h] BYREF
  _QWORD v60[6]; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v61; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v62; // [rsp+1E8h] [rbp+E0h]
  _OWORD v63[3]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v64; // [rsp+228h] [rbp+120h] BYREF
  __int128 v65; // [rsp+230h] [rbp+128h] BYREF
  __int128 v66; // [rsp+240h] [rbp+138h]
  __int128 v67; // [rsp+250h] [rbp+148h]
  int v68; // [rsp+260h] [rbp+158h] BYREF
  __int128 v69; // [rsp+268h] [rbp+160h] BYREF
  int v70; // [rsp+278h] [rbp+170h] BYREF
  __int128 v71; // [rsp+280h] [rbp+178h] BYREF
  __int128 v72; // [rsp+290h] [rbp+188h] BYREF
  int v73[14]; // [rsp+2A8h] [rbp+1A0h] BYREF
  char v74; // [rsp+2E0h] [rbp+1D8h]

  v60[4] = -2;
  LODWORD(v46) = a3;
  v11 = (int)a2;
  v53 = a9;
  v68 = 0;
  if ( a10 )
    *a10 = 0;
  v73[10] = 0;
  v74 = 0;
  v73[2] = 1;
  if ( (Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, a2) & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(
      (int)v73,
      0,
      (int)&v68,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1,
      (__int64)"Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      0,
      0,
      0,
      0,
      v45);
  if ( (v11 & 0xFFFFC200) != 0 )
  {
    *(_QWORD *)v47 = "onecore\\base\\wcp\\sil\\directory.cpp";
    *(_QWORD *)&v47[8] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    *(_QWORD *)&v47[16] = 696;
    v48 = "Valid flags check failed: Flags";
    v13 = v47;
LABEL_9:
    v68 = -1073741811;
    RtlReportErrorOrigination(v13, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v14 = v68;
LABEL_94:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v73);
    return v14;
  }
  if ( !a9 )
  {
    v54[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v54[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v54[2] = 698;
    v54[3] = "Not-null check failed: File";
    v13 = v54;
    goto LABEL_9;
  }
  if ( (a6 & 0xFFFFFFF8) != 0 )
  {
    v55[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v55[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v55[2] = 699;
    v55[3] = "Valid flags check failed: ShareAccess";
    v13 = v55;
    goto LABEL_9;
  }
  if ( (a8 & 0xFF000000) != 0 )
  {
    v56[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v56[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v56[2] = 700;
    v56[3] = "Valid flags check failed: CreateOptions";
    v13 = v56;
    goto LABEL_9;
  }
  if ( (a8 & 0x40) == 0 )
  {
    v57[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v57[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v57[2] = 701;
    v57[3] = "CreateOptions";
    v13 = v57;
    goto LABEL_9;
  }
  if ( (v11 & 1) != 0 )
  {
    if ( a7 - 2 > 1 && a7 != 5 )
    {
      v58[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
      v58[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v58[2] = 707;
      v58[3] = "CreationDisposition == 0x00000002 || CreationDisposition == 0x00000003 || CreationDisposition == 0x00000005";
      v13 = v58;
      goto LABEL_9;
    }
  }
  else if ( a7 != 2 && a7 != 5 )
  {
    v59[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
    v59[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
    v59[2] = 712;
    v59[3] = "CreationDisposition == 0x00000002 || CreationDisposition == 0x00000005";
    v13 = v59;
    goto LABEL_9;
  }
  v72 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v69 = 0;
  memset(v47, 0, sizeof(v47));
  v71 = 0;
  v64 = 0;
  v61 = 0;
  v62 = 0;
  memset(v63, 0, 40);
  v15 = *(__int128 **)(a4 + 8);
  v49 = *(_OWORD *)(a1 + 48);
  v50 = *(_QWORD *)(a1 + 64);
  v51 = *v15;
  v52 = *((_QWORD *)v15 + 2);
  v16 = RtlCombineNtPathSegments(2, &v49, v47);
  v14 = v16;
  if ( v16 < 0 )
  {
    v68 = v16;
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
    v17 = *(void (__fastcall ****)(_QWORD))&v63[0];
    if ( *(_QWORD *)&v63[0] )
    {
      *(_QWORD *)&v63[0] = 0;
      (**v17)(v17);
    }
LABEL_26:
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v47);
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v69);
    v18 = (void (__fastcall ***)(_QWORD))v69;
    if ( !(_QWORD)v69 )
      goto LABEL_94;
    *(_QWORD *)&v69 = 0;
LABEL_93:
    (**v18)(v18);
    goto LABEL_94;
  }
  inited = RtlInitUnicodeStringFromLUnicodeString(*(_QWORD *)(a4 + 8), &v71);
  v14 = inited;
  if ( inited < 0 )
  {
    v68 = inited;
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
    v20 = *(void (__fastcall ****)(_QWORD))&v63[0];
    if ( *(_QWORD *)&v63[0] )
    {
      *(_QWORD *)&v63[0] = 0;
      (**v20)(v20);
    }
    goto LABEL_26;
  }
  LODWORD(v65) = 48;
  *((_QWORD *)&v65 + 1) = *(_QWORD *)(a1 + 40);
  DWORD2(v66) = *(_DWORD *)(a4 + 16);
  *(_QWORD *)&v66 = &v71;
  v67 = *(_OWORD *)(a4 + 24);
  v70 = 0;
  if ( (v11 & 0x400) == 0 )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 24LL))(*(_QWORD *)(a1 + 24), &v64);
    v14 = v21;
    if ( v21 < 0 )
    {
      v68 = v21;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v22 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v22)(v22);
      }
LABEL_76:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v47);
LABEL_91:
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v69);
      v18 = (void (__fastcall ***)(_QWORD))v69;
      if ( !(_QWORD)v69 )
        goto LABEL_94;
      *(_QWORD *)&v69 = 0;
      goto LABEL_93;
    }
  }
  v23 = v11 & 4 | 8;
  if ( (v11 & 8) == 0 )
    v23 = v11 & 4;
  v24 = v23 | 1;
  if ( (v11 & 2) == 0 )
    v24 = v23;
  v25 = v24 | 0x200;
  if ( (v11 & 0x20) == 0 )
    v25 = v24;
  v26 = v25 | 0x400;
  if ( (v11 & 0x40) == 0 )
    v26 = v25;
  v27 = v26 | 0x800;
  if ( (v11 & 0x80u) == 0 )
    v27 = v26;
  if ( (v11 & 0x800) != 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 72) + 264LL))(*(_QWORD *)(a1 + 72)) )
    {
      v60[0] = "onecore\\base\\wcp\\sil\\directory.cpp";
      v60[1] = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v60[2] = 777;
      v60[3] = "!m_FileSystemProvider->IsUnbufferedSil()";
      v68 = -1073741811;
      RtlReportErrorOrigination(v60, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      v14 = v68;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v28 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v28)(v28);
      }
      goto LABEL_76;
    }
    if ( a7 != 5 )
    {
      *(_QWORD *)&v49 = "onecore\\base\\wcp\\sil\\directory.cpp";
      *((_QWORD *)&v49 + 1) = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v50 = 778;
      *(_QWORD *)&v51 = "CreationDisposition == 0x00000005";
      v68 = -1073741811;
      RtlReportErrorOrigination(&v49, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      v14 = v68;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v29 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v29)(v29);
      }
      goto LABEL_76;
    }
    v27 |= 0x10000u;
  }
  if ( (v11 & 0x1000) != 0 )
  {
    if ( ((unsigned int)v46 & 0x10E0000) != 0x10E0000
      || !(_QWORD)v67
      || (a8 & 0x41) == 0
      || (((a8 & 0x41) - 1LL) & a8 & 0x41) != 0 )
    {
      *(_QWORD *)&v49 = "onecore\\base\\wcp\\sil\\directory.cpp";
      *((_QWORD *)&v49 + 1) = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v50 = 784;
      *(_QWORD *)&v51 = "ValidateForEnsureSetSecurity(DesiredAccess, CreateOptions, LocalObjectAttributes)";
      v68 = -1073741811;
      RtlReportErrorOrigination(&v49, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      v14 = v68;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v32 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v32)(v32);
      }
      goto LABEL_76;
    }
    v27 |= 0x20000u;
  }
  if ( (v11 & 0x2000) != 0 )
  {
    if ( ((unsigned __int16)v46 & 0x100) == 0 || !a5 )
    {
      *(_QWORD *)&v49 = "onecore\\base\\wcp\\sil\\directory.cpp";
      *((_QWORD *)&v49 + 1) = "Windows::Rtl::SystemImplementation::CDirectory::CreateNewFile";
      v50 = 790;
      *(_QWORD *)&v51 = "ValidateForEnsureSetAttributes(DesiredAccess, FileAttributes)";
      v68 = -1073741811;
      RtlReportErrorOrigination(&v49, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      v14 = v68;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v33 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v33)(v33);
      }
      goto LABEL_76;
    }
    v27 |= 0x40000u;
  }
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, _QWORD, __int128 *, __int128 *, _QWORD, int, int, unsigned int, int, _QWORD, _DWORD, __int64, int *))(**(_QWORD **)(a1 + 72) + 112LL))(
          *(_QWORD *)(a1 + 72),
          v27,
          &v69,
          (unsigned int)v46,
          &v65,
          &v72,
          0,
          a5,
          a6,
          a7,
          a8,
          0,
          0,
          v64,
          &v70);
  v14 = v30;
  if ( v30 < 0 )
  {
    v68 = v30;
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
    v31 = *(void (__fastcall ****)(_QWORD))&v63[0];
    if ( *(_QWORD *)&v63[0] )
    {
      *(_QWORD *)&v63[0] = 0;
      (**v31)(v31);
    }
    goto LABEL_76;
  }
  if ( v70 != 1 )
  {
    if ( a10 )
    {
      switch ( v70 )
      {
        case 4:
          *a10 = 4;
          break;
        case 2:
          *a10 = 2;
          break;
        case 5:
          *a10 = 5;
          break;
        case 11:
          *a10 = 6;
          break;
        case 12:
          *a10 = 7;
          break;
        case 13:
          *a10 = 8;
          break;
        default:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x1801725F2LL);
      }
    }
    goto LABEL_107;
  }
  v61 = *(unsigned __int64 *)(a1 + 72);
  *(_QWORD *)&v62 = 0;
  *((_QWORD *)&v62 + 1) = *(_QWORD *)(a1 + 24);
  v34 = *((_QWORD *)&v63[0] + 1);
  *((_QWORD *)&v63[0] + 1) = *((_QWORD *)&v69 + 1);
  *((_QWORD *)&v69 + 1) = v34;
  v35 = v69;
  *(_QWORD *)&v69 = *(_QWORD *)&v63[0];
  *(_QWORD *)&v63[0] = v35;
  *(_QWORD *)&v63[1] = *(_QWORD *)v47;
  *(_OWORD *)((char *)&v63[1] + 8) = *(_OWORD *)&v47[8];
  v46 = 0;
  if ( (v11 & 0x10) != 0 )
  {
    v36 = Windows::Rtl::CRtlRefCountedObjectBase<Windows::Rtl::SystemImplementation::CIniFile,Windows::Rtl::IRtlIniFile,Windows::Rtl::IRtlFile,Windows::Rtl::IRtlSystemObject,Windows::Rtl::IRtlFilesystemObject,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface>::CreateInstance<Windows::Rtl::SystemImplementation::CreateObjectSource,Windows::Rtl::IRtlFile>(
            &v61,
            &v46);
    v14 = v36;
    if ( v36 < 0 )
    {
      v68 = v36;
      if ( v46 )
        (**v46)(v46);
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v37 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v37)(v37);
      }
LABEL_90:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v47);
      goto LABEL_91;
    }
  }
  else
  {
    v38 = Windows::Rtl::CRtlRefCountedObjectBase<Windows::Rtl::SystemImplementation::CFile,Windows::Rtl::IRtlFile,Windows::Rtl::IRtlSystemObject,Windows::Rtl::IRtlFilesystemObject,Windows::Rtl::SystemImplementation::IRtlFilesystemObjectBaseInternal,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface>::CreateInstance<Windows::Rtl::SystemImplementation::CreateObjectSource,Windows::Rtl::IRtlFile>(
            &v61,
            &v46);
    v14 = v38;
    if ( v38 < 0 )
    {
      v68 = v38;
      if ( v46 )
        (**v46)(v46);
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
      v39 = *(void (__fastcall ****)(_QWORD))&v63[0];
      if ( *(_QWORD *)&v63[0] )
      {
        *(_QWORD *)&v63[0] = 0;
        (**v39)(v39);
      }
      goto LABEL_90;
    }
  }
  v41 = v53;
  v42 = *v53;
  *v53 = v46;
  if ( a10 )
  {
    if ( (unsigned __int64)(*((_QWORD *)&v72 + 1) - 2LL) <= 1 )
    {
      if ( *((_QWORD *)&v72 + 1) )
      {
LABEL_104:
        *a10 = 1;
        goto LABEL_105;
      }
    }
    else if ( *((_QWORD *)&v72 + 1) )
    {
      if ( *((_QWORD *)&v72 + 1) == 1 || (MicrosoftTelemetryAssertTriggeredArgs(v41, a7), ((a7 - 1) & 0xFFFFFFFD) == 0) )
      {
        *a10 = 3;
        goto LABEL_105;
      }
      goto LABEL_104;
    }
    if ( a7 )
      MicrosoftTelemetryAssertTriggeredArgs(v41, a7);
    goto LABEL_104;
  }
LABEL_105:
  if ( v42 )
    (**v42)(v42);
LABEL_107:
  v74 = 1;
  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)v63);
  v43 = *(void (__fastcall ****)(_QWORD))&v63[0];
  if ( *(_QWORD *)&v63[0] )
  {
    *(_QWORD *)&v63[0] = 0;
    (**v43)(v43);
  }
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v47);
  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v69);
  v44 = (void (__fastcall ***)(_QWORD))v69;
  if ( (_QWORD)v69 )
  {
    *(_QWORD *)&v69 = 0;
    (**v44)(v44);
  }
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v73);
  return (unsigned int)v68;
}

```

## disassembly

```asm
0x180171a60  mov     rax, rsp
0x180171a63  push    rbp
0x180171a64  push    rsi
0x180171a65  push    rdi
0x180171a66  push    r12
0x180171a68  push    r13
0x180171a6a  push    r14
0x180171a6c  push    r15
0x180171a6e  lea     rbp, [rax-368h]
0x180171a75  sub     rsp, 430h
0x180171a7c  mov     [rbp+360h+var_2A0], 0FFFFFFFFFFFFFFFEh
0x180171a87  mov     [rax+10h], rbx
0x180171a8b  mov     rax, cs:__security_cookie
0x180171a92  xor     rax, rsp
0x180171a95  mov     [rbp+360h+var_40], rax
0x180171a9c  mov     r13, r9
0x180171a9f  mov     dword ptr [rbp+360h+var_3E0], r8d
0x180171aa3  mov     r14d, edx
0x180171aa6  mov     r15, rcx
0x180171aa9  mov     rbx, [rbp+360h+arg_40]
0x180171ab0  mov     [rbp+360h+var_388], rbx
0x180171ab4  mov     rdi, [rbp+360h+arg_48]
0x180171abb  xor     esi, esi
0x180171abd  mov     [rbp+360h+var_208], esi
0x180171ac3  test    rdi, rdi
0x180171ac6  jz      short loc_180171ACA
0x180171ac8  mov     [rdi], esi
0x180171aca  mov     [rbp+360h+var_198], esi
0x180171ad0  mov     [rbp+360h+var_188], sil
0x180171ad7  mov     [rbp+360h+var_1B8], 1
0x180171ae1  lea     r12, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x180171ae8  mov     rcx, r12; this
0x180171aeb  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180171af0  lea     rcx, aWindowsRtlSyst_305; "Windows::Rtl::SystemImplementation::CDi"...
0x180171af7  test    al, 0Eh
0x180171af9  jz      short loc_180171B41
0x180171afb  mov     qword ptr [rsp+460h+var_410], rsi; unsigned int
0x180171b00  mov     [rsp+460h+var_418], rsi; __int64
0x180171b05  mov     [rsp+460h+var_420], rsi; __int64
0x180171b0a  mov     [rsp+460h+var_428], rsi; __int64
0x180171b0f  mov     [rsp+460h+var_430], r12; Windows::WCP::Rtl *
0x180171b14  mov     [rsp+460h+var_438], rcx; __int64
0x180171b19  mov     [rsp+460h+var_440], r15; __int64
0x180171b1e  lea     r9, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x180171b25  lea     r8, [rbp+360h+var_208]; int
0x180171b2c  xor     edx, edx; int
0x180171b2e  lea     rcx, [rbp+360h+var_1C0]; int
0x180171b35  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXKAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(ulong,Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x180171b3a  lea     rcx, aWindowsRtlSyst_305; "Windows::Rtl::SystemImplementation::CDi"...
0x180171b41  test    r14d, 0FFFFC200h
0x180171b48  jz      short loc_180171B72
0x180171b4a  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171b51  mov     qword ptr [rbp+360h+var_3D8], rax
0x180171b55  mov     qword ptr [rbp+360h+var_3D8+8], rcx
0x180171b59  mov     [rbp+360h+var_3C8], 2B8h
0x180171b61  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x180171b68  mov     [rbp+360h+var_3C0], rax
0x180171b6c  lea     rcx, [rbp+360h+var_3D8]
0x180171b70  jmp     short loc_180171B9D
0x180171b72  test    rbx, rbx
0x180171b75  jnz     short loc_180171BC4
0x180171b77  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171b7e  mov     [rbp+360h+var_380], rax
0x180171b82  mov     [rbp+360h+var_378], rcx
0x180171b86  mov     [rbp+360h+var_370], 2BAh
0x180171b8e  lea     rax, aNotNullCheckFa_31; "Not-null check failed: File"
0x180171b95  mov     [rbp+360h+var_368], rax
0x180171b99  lea     rcx, [rbp+360h+var_380]
0x180171b9d  mov     [rbp+360h+var_208], 0C000000Dh
0x180171ba7  mov     r8d, 0C000000Dh
0x180171bad  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180171bb4  call    RtlReportErrorOrigination
0x180171bb9  mov     ebx, [rbp+360h+var_208]
0x180171bbf  jmp     loc_180172464
0x180171bc4  test    [rbp+360h+arg_28], 0FFFFFFF8h
0x180171bce  jz      short loc_180171BF8
0x180171bd0  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171bd7  mov     [rbp+360h+var_360], rax
0x180171bdb  mov     [rbp+360h+var_358], rcx
0x180171bdf  mov     [rbp+360h+var_350], 2BBh
0x180171be7  lea     rax, aValidFlagsChec; "Valid flags check failed: ShareAccess"
0x180171bee  mov     [rbp+360h+var_348], rax
0x180171bf2  lea     rcx, [rbp+360h+var_360]
0x180171bf6  jmp     short loc_180171B9D
0x180171bf8  mov     r12d, [rbp+360h+arg_38]
0x180171bff  test    r12d, 0FF000000h
0x180171c06  jz      short loc_180171C33
0x180171c08  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171c0f  mov     [rbp+360h+var_340], rax
0x180171c13  mov     [rbp+360h+var_338], rcx
0x180171c17  mov     [rbp+360h+var_330], 2BCh
0x180171c1f  lea     rax, aValidFlagsChec_4; "Valid flags check failed: CreateOptions"
0x180171c26  mov     [rbp+360h+var_328], rax
0x180171c2a  lea     rcx, [rbp+360h+var_340]
0x180171c2e  jmp     loc_180171B9D
0x180171c33  test    r12b, 40h
0x180171c37  jnz     short loc_180171C64
0x180171c39  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171c40  mov     [rbp+360h+var_320], rax
0x180171c44  mov     [rbp+360h+var_318], rcx
0x180171c48  mov     [rbp+360h+var_310], 2BDh
0x180171c50  lea     rax, aCreateoptions; "CreateOptions"
0x180171c57  mov     [rbp+360h+var_308], rax
0x180171c5b  lea     rcx, [rbp+360h+var_320]
0x180171c5f  jmp     loc_180171B9D
0x180171c64  mov     esi, [rbp+360h+arg_30]
0x180171c6a  test    r14b, 1
0x180171c6e  jz      short loc_180171CA8
0x180171c70  lea     eax, [rsi-2]
0x180171c73  cmp     eax, 1
0x180171c76  jbe     short loc_180171CEC
0x180171c78  cmp     esi, 5
0x180171c7b  jz      short loc_180171CEC
0x180171c7d  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171c84  mov     [rbp+360h+var_300], rax
0x180171c88  mov     [rbp+360h+var_2F8], rcx
0x180171c8c  mov     [rbp+360h+var_2F0], 2C3h
0x180171c94  lea     rax, aCreationdispos_0; "CreationDisposition == 0x00000002 || Cr"...
0x180171c9b  mov     [rbp+360h+var_2E8], rax
0x180171c9f  lea     rcx, [rbp+360h+var_300]
0x180171ca3  jmp     loc_180171B9D
0x180171ca8  cmp     esi, 2
0x180171cab  jz      short loc_180171CEC
0x180171cad  cmp     esi, 5
0x180171cb0  jz      short loc_180171CEC
0x180171cb2  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171cb9  mov     [rbp+360h+var_2E0], rax
0x180171cc0  mov     [rbp+360h+var_2D8], rcx
0x180171cc7  mov     [rbp+360h+var_2D0], 2C8h
0x180171cd2  lea     rax, aCreationdispos; "CreationDisposition == 0x00000002 || Cr"...
0x180171cd9  mov     [rbp+360h+var_2C8], rax
0x180171ce0  lea     rcx, [rbp+360h+var_2E0]
0x180171ce7  jmp     loc_180171B9D
0x180171cec  xorps   xmm0, xmm0
0x180171cef  movups  [rbp+360h+var_1D8], xmm0
0x180171cf6  xorps   xmm1, xmm1
0x180171cf9  movups  [rbp+360h+var_238], xmm1
0x180171d00  movups  [rbp+360h+var_228], xmm1
0x180171d07  movups  [rbp+360h+var_218], xmm1
0x180171d0e  movdqu  [rbp+360h+var_200], xmm0
0x180171d16  xor     eax, eax
0x180171d18  movups  [rbp+360h+var_3D8], xmm1
0x180171d1c  mov     [rbp+360h+var_3C8], rax
0x180171d20  movups  [rbp+360h+var_1E8], xmm0
0x180171d27  mov     [rbp+360h+var_240], rax
0x180171d2e  movdqa  [rbp+360h+var_290], xmm1
0x180171d36  movdqa  [rbp+360h+var_280], xmm0
0x180171d3e  movdqa  [rbp+360h+var_270], xmm0
0x180171d46  movups  [rbp+360h+var_260], xmm1
0x180171d4d  mov     [rbp+360h+var_250], rax
0x180171d54  mov     rax, [r13+8]
0x180171d58  movups  xmm0, xmmword ptr [r15+30h]
0x180171d5d  movups  [rbp+360h+var_3B8], xmm0
0x180171d61  movsd   xmm1, qword ptr [r15+40h]
0x180171d67  movsd   [rbp+360h+var_3A8], xmm1
0x180171d6c  movups  xmm0, xmmword ptr [rax]
0x180171d6f  movups  [rbp+360h+var_3A0], xmm0
0x180171d73  movsd   xmm1, qword ptr [rax+10h]
0x180171d78  movsd   [rbp+360h+var_390], xmm1
0x180171d7d  lea     r8, [rbp+360h+var_3D8]
0x180171d81  lea     rdx, [rbp+360h+var_3B8]
0x180171d85  mov     ecx, 2
0x180171d8a  call    RtlCombineNtPathSegments
0x180171d8f  mov     ebx, eax
0x180171d91  test    eax, eax
0x180171d93  jns     short loc_180171E00
0x180171d95  mov     [rbp+360h+var_208], eax
0x180171d9b  lea     rcx, [rbp+360h+var_270]; this
0x180171da2  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180171da7  mov     rcx, qword ptr [rbp+360h+var_270]
0x180171dae  test    rcx, rcx
0x180171db1  jz      short loc_180171DCA
0x180171db3  mov     qword ptr [rbp+360h+var_270], 0
0x180171dbe  mov     rdx, [rcx]
0x180171dc1  mov     rax, [rdx]
0x180171dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171dc9  nop
0x180171dca  lea     rcx, [rbp+360h+var_3D8]
0x180171dce  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180171dd3  nop
0x180171dd4  lea     rcx, [rbp+360h+var_200]; this
0x180171ddb  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180171de0  mov     rcx, qword ptr [rbp+360h+var_200]
0x180171de7  test    rcx, rcx
0x180171dea  jz      loc_180172464
0x180171df0  mov     qword ptr [rbp+360h+var_200], 0
0x180171dfb  jmp     loc_180172459
0x180171e00  lea     rdx, [rbp+360h+var_1E8]
0x180171e07  mov     rcx, [r13+8]
0x180171e0b  call    RtlInitUnicodeStringFromLUnicodeString
0x180171e10  mov     ebx, eax
0x180171e12  test    eax, eax
0x180171e14  jns     short loc_180171E5A
0x180171e16  mov     [rbp+360h+var_208], eax
0x180171e1c  lea     rcx, [rbp+360h+var_270]; this
0x180171e23  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180171e28  mov     rcx, qword ptr [rbp+360h+var_270]
0x180171e2f  test    rcx, rcx
0x180171e32  jz      short loc_180171E4B
0x180171e34  mov     qword ptr [rbp+360h+var_270], 0
0x180171e3f  mov     rax, [rcx]
0x180171e42  mov     rax, [rax]
0x180171e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171e4a  nop
0x180171e4b  lea     rcx, [rbp+360h+var_3D8]
0x180171e4f  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180171e54  nop
0x180171e55  jmp     loc_180171DD4
0x180171e5a  mov     dword ptr [rbp+360h+var_238], 30h ; '0'
0x180171e64  mov     rax, [r15+28h]
0x180171e68  mov     qword ptr [rbp+360h+var_238+8], rax
0x180171e6f  mov     eax, [r13+10h]
0x180171e73  mov     dword ptr [rbp+360h+var_228+8], eax
0x180171e79  lea     rax, [rbp+360h+var_1E8]
0x180171e80  mov     qword ptr [rbp+360h+var_228], rax
0x180171e87  mov     rax, [r13+18h]
0x180171e8b  mov     qword ptr [rbp+360h+var_218], rax
0x180171e92  mov     rax, [r13+20h]
0x180171e96  mov     qword ptr [rbp+360h+var_218+8], rax
0x180171e9d  xor     r13d, r13d
0x180171ea0  mov     [rbp+360h+var_1F0], r13d
0x180171ea7  bt      r14d, 0Ah
0x180171eac  jb      short loc_180171F0B
0x180171eae  mov     rcx, [r15+18h]
0x180171eb2  mov     rax, [rcx]
0x180171eb5  lea     rdx, [rbp+360h+var_240]
0x180171ebc  mov     rax, [rax+18h]
0x180171ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171ec5  mov     ebx, eax
0x180171ec7  test    eax, eax
0x180171ec9  jns     short loc_180171F0B
0x180171ecb  mov     [rbp+360h+var_208], eax
0x180171ed1  lea     rcx, [rbp+360h+var_270]; this
0x180171ed8  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180171edd  mov     rcx, qword ptr [rbp+360h+var_270]
0x180171ee4  test    rcx, rcx
0x180171ee7  jz      short loc_180171EFC
0x180171ee9  mov     qword ptr [rbp+360h+var_270], r13
0x180171ef0  mov     rax, [rcx]
0x180171ef3  mov     rax, [rax]
0x180171ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171efb  nop
0x180171efc  lea     rcx, [rbp+360h+var_3D8]
0x180171f00  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180171f05  nop
0x180171f06  jmp     loc_18017243A
0x180171f0b  mov     ecx, r14d
0x180171f0e  and     ecx, 4
0x180171f11  mov     edx, ecx
0x180171f13  or      edx, 8
0x180171f16  test    r14b, 8
0x180171f1a  cmovz   edx, ecx
0x180171f1d  mov     ecx, edx
0x180171f1f  or      ecx, 1
0x180171f22  test    r14b, 2
0x180171f26  cmovz   ecx, edx
0x180171f29  mov     edx, ecx
0x180171f2b  bts     edx, 9
0x180171f2f  test    r14b, 20h
0x180171f33  cmovz   edx, ecx
0x180171f36  mov     ecx, edx
0x180171f38  bts     ecx, 0Ah
0x180171f3c  test    r14b, 40h
0x180171f40  cmovz   ecx, edx
0x180171f43  mov     ebx, ecx
0x180171f45  mov     edx, 800h
0x180171f4a  or      ebx, edx
0x180171f4c  test    r14b, 80h
0x180171f50  cmovz   ebx, ecx
0x180171f53  test    edx, r14d
0x180171f56  jz      loc_1801720A5
0x180171f5c  mov     rcx, [r15+48h]
0x180171f60  mov     rax, [rcx]
0x180171f63  mov     rax, [rax+108h]
0x180171f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171f6f  test    al, al
0x180171f71  jz      loc_18017200F
0x180171f77  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\sil\\directory.cpp"
0x180171f7e  mov     [rbp+360h+var_2C0], rax
0x180171f85  lea     rax, aWindowsRtlSyst_305; "Windows::Rtl::SystemImplementation::CDi"...
0x180171f8c  mov     [rbp+360h+var_2B8], rax
0x180171f93  mov     [rbp+360h+var_2B0], 309h
0x180171f9e  lea     rax, aMFilesystempro_4; "!m_FileSystemProvider->IsUnbufferedSil("...
0x180171fa5  mov     [rbp+360h+var_2A8], rax
0x180171fac  mov     [rbp+360h+var_208], 0C000000Dh
0x180171fb6  mov     r8d, 0C000000Dh
0x180171fbc  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180171fc3  lea     rcx, [rbp+360h+var_2C0]
0x180171fca  call    RtlReportErrorOrigination
0x180171fcf  mov     ebx, [rbp+360h+var_208]
0x180171fd5  lea     rcx, [rbp+360h+var_270]; this
0x180171fdc  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180171fe1  mov     rcx, qword ptr [rbp+360h+var_270]
0x180171fe8  test    rcx, rcx
0x180171feb  jz      short loc_180172000
0x180171fed  mov     qword ptr [rbp+360h+var_270], r13
0x180171ff4  mov     rax, [rcx]
0x180171ff7  mov     rax, [rax]
0x180171ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171fff  nop
  ... truncated ...
```
