# WindowsPerformanceRecorder::CETWProperties::WriteEventProvider(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool,bool,bool)

- ea: `0x1800113e0`
- end: `0x1800128f2`
- name: `?WriteEventProvider@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBUCEventSession@12@_N22@Z`
- size: `5394`
- prototype: `static int(struct WindowsPerformanceRecorder::CXmlWriter *, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *, bool, bool, bool)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003e33c`

## callees

- `0x1800024d0`
- `0x180009a84`
- `0x1800102d8`
- `0x180011280`
- `0x1800113e0`
- `0x1800128f8`
- `0x180012cb0`
- `0x180013038`
- `0x180013094`
- `0x1800131a0`
- `0x1800138c0`
- `0x180017d70`
- `0x18001c458`
- `0x18001e6b8`
- `0x180027850`
- `0x18002c9e0`
- `0x180035250`
- `0x180043204`
- `0x18004324c`
- `0x180043294`
- `0x180044210`
- `0x180044230`
- `0x180046e98`
- `0x18004f8ce`
- `0x18004f964`
- `0x18004f970`
- `0x180056898`
- `0x18006592c`
- `0x180065974`
- `0x1800659b4`
- `0x180082d30`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800116fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121ea`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800116fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121c4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::WriteEventProvider(
        struct WindowsPerformanceRecorder::CXmlWriter *a1,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2,
        char a3,
        unsigned __int8 a4,
        bool a5)
{
  __int64 v5; // rbx
  char v6; // si
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v7; // r13
  __int64 result; // rax
  char v9; // dl
  bool v10; // di
  __int64 v11; // rax
  struct WindowsPerformanceRecorder::CWPRControl *v12; // r9
  struct WindowsPerformanceRecorder::CWPRControl *v13; // rax
  __int16 *v14; // r10
  char *v15; // r15
  unsigned __int64 v16; // rcx
  char *v17; // rax
  char *v18; // rbx
  char *v19; // rdi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rsi
  char *v23; // r12
  const unsigned __int16 *SessionName; // rdi
  __int64 v25; // rbx
  unsigned __int64 v26; // r14
  unsigned __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // r8d
  __int64 v30; // rbx
  unsigned __int64 v31; // rsi
  int v32; // edi
  unsigned __int64 v33; // rbx
  const wchar_t *v34; // rax
  wchar_t *v35; // rcx
  const unsigned __int16 *v36; // r13
  __int64 v37; // r15
  char *v38; // r14
  __int64 v39; // rbx
  unsigned __int64 v40; // rsi
  int v41; // edi
  unsigned __int64 v42; // rbx
  size_t v43; // r8
  char *v44; // rcx
  char v45; // dl
  char *v46; // rcx
  int v47; // edi
  __int64 v48; // rax
  __int64 v49; // rbx
  char v50; // dl
  char *v51; // rcx
  int v52; // edi
  __int64 v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rbx
  int v56; // eax
  __int64 v57; // rdi
  unsigned __int16 *v58; // r8
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rbx
  int v62; // eax
  __int64 v63; // rdi
  unsigned __int16 *v64; // r8
  int v65; // eax
  __int64 v66; // rcx
  __int16 v67; // bx
  char *v68; // rsi
  const unsigned __int16 *v69; // r8
  unsigned __int64 v70; // rbx
  const unsigned __int16 *v71; // r8
  __int64 v72; // rbx
  const unsigned __int16 *v73; // r8
  unsigned __int64 v74; // rax
  const unsigned __int16 *v75; // r8
  unsigned __int64 v76; // rbx
  const unsigned __int16 *v77; // r8
  const unsigned __int16 *v78; // rdx
  unsigned __int64 v79; // rbx
  unsigned __int64 v80; // rbx
  unsigned __int64 i; // rcx
  __int64 v82; // rdi
  unsigned int v83; // edi
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rcx
  __int64 j; // rax
  unsigned __int64 v88; // rcx
  const unsigned __int16 *v89; // rdx
  unsigned int v90; // ecx
  const unsigned __int16 *v91; // rdx
  unsigned int v92; // ecx
  const unsigned __int16 *v93; // rdx
  unsigned int v94; // ecx
  const unsigned __int16 *v95; // rdx
  unsigned int v96; // ebx
  unsigned __int16 v97; // bx
  const unsigned __int16 *v98; // rdx
  const unsigned __int16 *v99; // r8
  const unsigned __int16 *v100; // rdx
  unsigned int v101[2]; // [rsp+20h] [rbp-118h]
  unsigned int v102; // [rsp+20h] [rbp-118h]
  unsigned int v103; // [rsp+20h] [rbp-118h]
  __int64 v104; // [rsp+28h] [rbp-110h]
  __int64 v105; // [rsp+30h] [rbp-108h]
  __int64 v106; // [rsp+38h] [rbp-100h]
  __int64 v107; // [rsp+40h] [rbp-F8h]
  __int64 v108; // [rsp+48h] [rbp-F0h]
  __int64 v109; // [rsp+50h] [rbp-E8h]
  __int64 v110; // [rsp+58h] [rbp-E0h]
  __int64 v111; // [rsp+60h] [rbp-D8h]
  char v112; // [rsp+70h] [rbp-C8h]
  char *v113; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int64 v114; // [rsp+80h] [rbp-B8h] BYREF
  char pExceptionObject; // [rsp+88h] [rbp-B0h] BYREF
  int v116; // [rsp+8Ch] [rbp-ACh]
  struct WindowsPerformanceRecorder::CWPRControl *v117; // [rsp+90h] [rbp-A8h]
  char *v118; // [rsp+98h] [rbp-A0h]
  int v119; // [rsp+A0h] [rbp-98h]
  void *Src; // [rsp+A8h] [rbp-90h] BYREF
  struct WindowsPerformanceRecorder::CWPRControl *v121[3]; // [rsp+B0h] [rbp-88h] BYREF
  _QWORD v122[3]; // [rsp+C8h] [rbp-70h] BYREF
  _QWORD v123[11]; // [rsp+E0h] [rbp-58h] BYREF

  v121[1] = (struct WindowsPerformanceRecorder::CWPRControl *)-2LL;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  result = WindowsPerformanceRecorder::CWPRControl::GetInstance(v121);
  if ( (int)result >= 0 )
  {
    v119 = *(_DWORD *)(*((_QWORD *)v7 + 1) + 64LL) & 0x1000000;
    v9 = 1;
    v112 = 1;
    v10 = a5;
    if ( a5 )
      v11 = 48;
    else
      v11 = ((v5 ^ 1) << 7) + 24;
    v12 = *(struct WindowsPerformanceRecorder::CWPRControl **)((char *)v7 + v11);
    v13 = *(struct WindowsPerformanceRecorder::CWPRControl **)((char *)v7 + v11 + 8);
    v121[0] = v13;
    while ( 1 )
    {
      v14 = &_ImageBase;
      v117 = v12;
      if ( v12 == v13 )
        return 0;
      v15 = (char *)v12;
      v16 = *((_QWORD *)v12 + 2);
      v114 = v16;
      v17 = (char *)v12;
      v118 = (char *)v12;
      if ( !v10 && !(_BYTE)v5 )
      {
        v18 = (char *)*((_QWORD *)v7 + 3);
        v19 = (char *)*((_QWORD *)v7 + 4);
        if ( v18 != v19 )
        {
          while ( 1 )
          {
            v20 = memcmp_0(v18, v12, 0x10u);
            v12 = v117;
            if ( !v20 )
              break;
            v18 += 264;
            if ( v18 == v19 )
            {
              v17 = v15;
              goto LABEL_12;
            }
          }
          v17 = v18;
          v118 = v18;
LABEL_12:
          v14 = &_ImageBase;
          v9 = v112;
          v16 = v114;
        }
        v10 = a5;
      }
      if ( v6 && *((_BYTE *)v7 + 208) && v16 != -1 && (v16 & 0x1000000000000LL) != 0 )
      {
        v88 = v16 & 0xFFFEFFFFFFFFFFFFuLL;
        v114 = v88;
        if ( v9 )
        {
          v15 = ControlGuid_PerfTrack;
        }
        else if ( !v88 && !*((_QWORD *)v17 + 4) && !*((_QWORD *)v17 + 3) )
        {
          goto LABEL_17;
        }
        v112 = 0;
      }
      if ( *((_BYTE *)v7 + 209) && v17[261] )
        goto LABEL_17;
      if ( *(_DWORD *)v7 == 1 )
      {
        v28 = 0;
        while ( (unsigned int)v28 < 0x11 )
        {
          if ( (unsigned int)InlineIsEqualGUID(
                               (const struct _GUID *)v17,
                               *(const struct _GUID **)&v14[4 * v28 + 299128]) )
            goto LABEL_17;
          v28 = (unsigned int)(v29 + 1);
          v17 = v118;
        }
      }
      v116 = *((_DWORD *)v12 + 58);
      Src = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      LODWORD(v111) = (unsigned __int8)v15[15];
      LODWORD(v110) = (unsigned __int8)v15[14];
      LODWORD(v109) = (unsigned __int8)v15[13];
      LODWORD(v108) = (unsigned __int8)v15[12];
      LODWORD(v107) = (unsigned __int8)v15[11];
      LODWORD(v106) = (unsigned __int8)v15[10];
      LODWORD(v105) = (unsigned __int8)v15[9];
      LODWORD(v104) = (unsigned __int8)v15[8];
      v101[0] = *((unsigned __int16 *)v15 + 3);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &Src,
        L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
        *(unsigned int *)v15,
        *((unsigned __int16 *)v15 + 2),
        *(_QWORD *)v101,
        v104,
        v105,
        v106,
        v107,
        v108,
        v109,
        v110,
        v111);
      v22 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v23 = (char *)v22;
      v113 = (char *)v22;
      SessionName = (const unsigned __int16 *)*((_QWORD *)v7 + 24);
      if ( !SessionName )
      {
        SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v7);
        if ( !SessionName )
          goto LABEL_199;
      }
      v25 = -1;
      do
        ++v25;
      while ( SessionName[v25] );
      if ( (_DWORD)v25 )
      {
        v26 = *(unsigned int *)(v22 - 16);
        if ( (int)((*(_DWORD *)(v22 - 12) - v25) | (1 - *(_DWORD *)(v22 - 8))) < 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v113, v25);
          v23 = v113;
        }
        v27 = ((__int64)SessionName - v22) >> 1;
        if ( v27 <= v26 )
        {
          memmove_s(v23, 2LL * (int)v25, &v23[2 * v27], 2LL * (int)v25);
        }
        else if ( 2LL * (int)v25 )
        {
          if ( v23 )
          {
            memcpy_0(v23, SessionName, 2LL * (int)v25);
          }
          else
          {
            *(_DWORD *)_o__errno(v27, v21) = 22;
            invalid_parameter_noinfo();
          }
        }
        if ( (int)v25 < 0 || (int)v25 > *((_DWORD *)v23 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v23 - 4) = v25;
        *(_WORD *)&v23[2 * (int)v25] = 0;
      }
      else
      {
LABEL_199:
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v113);
        v23 = v113;
      }
      v30 = (char *)L"_" - v23;
      v31 = *((unsigned int *)v23 - 4);
      v32 = v31 + 1;
      if ( (((*((_DWORD *)v23 - 3) - (v31 + 1)) | (1 - *((_DWORD *)v23 - 2))) & 0x80000000) != 0LL )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v113, v32);
        v23 = v113;
      }
      v33 = v30 >> 1;
      if ( v33 <= v31 )
        v34 = (const wchar_t *)&v23[2 * v33];
      else
        v34 = L"_";
      v35 = (wchar_t *)&v23[2 * v31];
      if ( !v35 )
        goto LABEL_214;
      if ( !v34 )
        break;
      *v35 = *v34;
LABEL_45:
      if ( v32 < 0 || v32 > *((_DWORD *)v23 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v23 - 4) = v32;
      *(_WORD *)&v23[2 * v32] = 0;
      v36 = (const unsigned __int16 *)Src;
      v37 = *((int *)Src - 4);
      v38 = (char *)Src;
      v39 = (_BYTE *)Src - v23;
      v40 = *((unsigned int *)v23 - 4);
      v41 = v37 + v40;
      if ( (((*((_DWORD *)v23 - 3) - (v37 + v40)) | (1 - *((_DWORD *)v23 - 2))) & 0x80000000) != 0LL )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v113, v41);
        v23 = v113;
      }
      v42 = v39 >> 1;
      if ( v42 <= v40 )
        v38 = &v23[2 * v42];
      v43 = 2 * v37;
      if ( !(2 * v37) )
        goto LABEL_55;
      v44 = &v23[2 * v40];
      if ( v44 )
      {
        if ( v38 )
        {
          memcpy_0(v44, v38, v43);
          goto LABEL_55;
        }
        memset_0(v44, 0, v43);
      }
      *(_DWORD *)_o__errno(v44, v21) = 22;
      invalid_parameter_noinfo();
LABEL_55:
      if ( v41 < 0 || v41 > *((_DWORD *)v23 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v23 - 4) = v41;
      *(_WORD *)&v23[2 * v41] = 0;
      if ( a5 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(&v113, L"_CaptureState");
        v23 = v113;
      }
      v45 = 0;
      v46 = v23;
      v47 = *((_DWORD *)v23 - 4);
      LODWORD(v48) = 0;
      while ( (int)v48 < v47 )
      {
        v49 = 2LL * (int)v48;
        if ( *(_WORD *)&v46[v49] == 58 )
        {
          if ( !v45 )
          {
            if ( ((*((_DWORD *)v23 - 3) - v47) | (1 - *((_DWORD *)v23 - 2))) < 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v113, v47);
              v23 = v113;
            }
            v45 = 1;
            v46 = v23;
          }
          *(_WORD *)&v46[v49] = 95;
        }
        v48 = (v49 + 2) >> 1;
      }
      if ( v45 )
        ATL::CSimpleStringT<unsigned short,0>::SetLength((__int64 *)&v113, v47);
      v50 = 0;
      v51 = v23;
      v52 = *((_DWORD *)v23 - 4);
      LODWORD(v53) = 0;
      while ( (int)v53 < v52 )
      {
        v54 = 2LL * (int)v53;
        if ( *(_WORD *)&v51[v54] == 32 )
        {
          if ( !v50 )
          {
            if ( ((*((_DWORD *)v23 - 3) - v52) | (1 - *((_DWORD *)v23 - 2))) < 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v113, v52);
              v23 = v113;
            }
            v50 = 1;
            v51 = v23;
          }
          *(_WORD *)&v51[v54] = 95;
        }
        v53 = (v54 + 2) >> 1;
      }
      if ( v50 )
        ATL::CSimpleStringT<unsigned short,0>::SetLength((__int64 *)&v113, v52);
      if ( *((_BYTE *)a1 + 16) )
        ATL::CSimpleStringT<unsigned short,0>::Append(a1, L">\n");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a1,
        L"%*ws<%ws",
        *((unsigned int *)a1 + 5),
        &LocaleName,
        L"EventProvider");
      *((_DWORD *)a1 + 5) += 2;
      *((_BYTE *)a1 + 16) = 1;
      if ( !v23 )
        goto LABEL_220;
      v55 = -1;
      do
        ++v55;
      while ( *(_WORD *)&v23[2 * v55] );
      if ( (_DWORD)v55 )
      {
        v56 = ATL::EscapeXML((const unsigned __int16 *)v23, v55, 0, 0, v101[0]);
        v57 = v56;
        if ( ((*(_DWORD *)(*((_QWORD *)a1 + 1) - 12LL) - v56) | (1 - *(_DWORD *)(*((_QWORD *)a1 + 1) - 8LL))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)a1 + 1, v56);
        if ( (int)v57 < 0 || (v58 = (unsigned __int16 *)*((_QWORD *)a1 + 1), (int)v57 > *((_DWORD *)v58 - 3)) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v58 - 4) = v57;
        *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v57) = 0;
        v59 = ATL::EscapeXML((const unsigned __int16 *)v23, v55, v58, v57 + 1, v102);
        if ( v59 < 0 || (v60 = *((_QWORD *)a1 + 1), v59 > *(_DWORD *)(v60 - 12)) )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(v60 - 16) = v59;
        *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v59) = 0;
        if ( !v59 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
LABEL_220:
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)a1 + 8, &LocaleName);
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a1,
        L" %ws=\"%ws\"",
        L"Id",
        *((_QWORD *)a1 + 1));
      if ( !*((_BYTE *)a1 + 16) )
        throw (WindowsPerformanceRecorder::CXmlWriter::out_of_order *)&pExceptionObject;
      if ( !v36 )
        goto LABEL_225;
      v61 = -1;
      do
        ++v61;
      while ( v36[v61] );
      if ( (_DWORD)v61 )
      {
        v62 = ATL::EscapeXML(v36, v61, 0, 0, v101[0]);
        v63 = v62;
        if ( ((*(_DWORD *)(*((_QWORD *)a1 + 1) - 12LL) - v62) | (1 - *(_DWORD *)(*((_QWORD *)a1 + 1) - 8LL))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)a1 + 1, v62);
        if ( (int)v63 < 0 || (v64 = (unsigned __int16 *)*((_QWORD *)a1 + 1), (int)v63 > *((_DWORD *)v64 - 3)) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v64 - 4) = v63;
        *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v63) = 0;
        v65 = ATL::EscapeXML(v36, v61, v64, v63 + 1, v103);
        if ( v65 < 0 || (v66 = *((_QWORD *)a1 + 1), v65 > *(_DWORD *)(v66 - 12)) )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(v66 - 16) = v65;
        *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v65) = 0;
        if ( !v65 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
LABEL_225:
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)a1 + 8, &LocaleName);
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a1,
        L" %ws=\"%ws\"",
        L"Name",
        *((_QWORD *)a1 + 1));
      if ( !v119 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"NonPagedMemory", 1);
      v67 = v116;
      if ( (v116 & 4) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"Stack", 1);
      if ( (v67 & 1) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"SID", v67 & 1);
      if ( (v67 & 2) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"TSID", 1);
      if ( (v67 & 0x100) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"EventKey", 1);
      if ( (v67 & 0x200) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"ExcludeInPrivate", 1);
      if ( (v67 & 0x400) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"EnableSilos", 1);
      if ( (v67 & 0x800) != 0 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"ContainerId", 1);
      if ( *((_BYTE *)v117 + 248) != 0xFF )
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Level", *((unsigned __int8 *)v117 + 248));
      v10 = a5;
      if ( a5 )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"CaptureStateOnly", a5);
      v68 = v118;
      if ( v118[252] )
        WindowsPerformanceRecorder::CXmlWriter::AttrTrueFalse(a1, L"Strict", (unsigned __int8)v118[252]);
      v69 = (const unsigned __int16 *)*((_QWORD *)v68 + 6);
      if ( v69 )
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"ProcessExeFilter", v69);
      v70 = v114;
      if ( v114 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keywords");
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
        WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v89, v70);
        WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"Keywords");
      }
      if ( v68[249] )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"CaptureStateOnStart");
        v90 = *((_DWORD *)v68 + 59);
        if ( v90 == -1 )
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", L"infinite");
        else
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", v90 / 0x3E8);
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
        WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v91, *((_QWORD *)v68 + 3));
        WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"CaptureStateOnStart");
      }
      if ( v68[250] )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"CaptureStateOnSave");
        v92 = *((_DWORD *)v68 + 60);
        if ( v92 == -1 )
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", L"infinite");
        else
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", v92 / 0x3E8);
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
        WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v93, *((_QWORD *)v68 + 4));
        WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"CaptureStateOnSave");
      }
      if ( v68[251] )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"CaptureStateOnDemand");
        v94 = *((_DWORD *)v68 + 61);
        if ( v94 == -1 )
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", L"infinite");
        else
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Timeout", v94 / 0x3E8);
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
        WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v95, *((_QWORD *)v68 + 5));
        WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"CaptureStateOnDemand");
      }
      if ( *((_QWORD *)v68 + 9) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Stacks");
        v80 = **((_QWORD **)v68 + 8);
        v114 = v80;
        while ( !*(_BYTE *)(v80 + 25) )
        {
          for ( i = 0; i < 0xBC; ++i )
          {
            v82 = 24 * i;
            if ( *(_WORD *)(v80 + 40) == word_18008D968[12 * i] )
            {
              WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Stack");
              WindowsPerformanceRecorder::CXmlWriter::Attr(
                a1,
                L"Value",
                *(const unsigned __int16 **)((char *)&WindowsPerformanceRecorder::CSystemProviderElement::sc_Stacks + v82));
              WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
              goto LABEL_240;
            }
          }
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"CustomStack");
          v96 = *(unsigned __int16 *)(v80 + 40);
          WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(a1);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" %ws=\"0x%04x\"",
            L"Value",
            v96);
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
LABEL_240:
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(&v114);
          v80 = v114;
        }
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"Stacks");
        v10 = a5;
      }
      if ( *((_QWORD *)v68 + 19) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"EventFilters");
        v71 = L"true";
        if ( !v68[258] )
          v71 = L"false";
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"FilterIn", v71);
        v72 = **((_QWORD **)v68 + 18);
        while ( !*(_BYTE *)(v72 + 25) )
        {
          v83 = *(unsigned __int16 *)(v72 + 26);
          if ( *((_BYTE *)a1 + 16) )
            ATL::CSimpleStringT<unsigned short,0>::Append(a1, L">\n");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L"%*ws<%ws",
            *((unsigned int *)a1 + 5),
            &LocaleName,
            L"EventId");
          *((_DWORD *)a1 + 5) += 2;
          *((_BYTE *)a1 + 16) = 1;
          WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(a1);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" %ws=\"%u\"",
            L"Value",
            v83);
          *((_DWORD *)a1 + 5) -= 2;
          if ( !*((_BYTE *)a1 + 16) )
          {
            std::exception::exception((std::exception *)v122, "wszName");
            v122[0] = &std::invalid_argument::`vftable';
            throw (std::invalid_argument *)v122;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" />\n");
          *((_BYTE *)a1 + 16) = 0;
          v86 = *(_QWORD *)(v72 + 16);
          if ( *(_BYTE *)(v86 + 25) )
          {
            for ( j = *(_QWORD *)(v72 + 8); !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
            {
              if ( v72 != *(_QWORD *)(j + 16) )
                break;
              v72 = j;
            }
            v72 = j;
          }
          else
          {
            v72 = std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::IProfileElement *>>::_Min(
                    v86,
                    v84,
                    v85);
          }
        }
        *((_DWORD *)a1 + 5) -= 2;
        if ( *((_BYTE *)a1 + 16) )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" />\n");
        else
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L"%*ws</%ws>\n",
            *((unsigned int *)a1 + 5),
            &LocaleName,
            L"EventFilters");
        *((_BYTE *)a1 + 16) = 0;
        v10 = a5;
      }
      if ( *((_QWORD *)v68 + 11) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"StackFilters");
        v73 = L"true";
        if ( !v68[253] )
          v73 = L"false";
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"FilterIn", v73);
        v74 = **((_QWORD **)v68 + 10);
        v114 = v74;
        while ( !*(_BYTE *)(v74 + 25) )
        {
          v97 = *(_WORD *)(v74 + 26);
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"EventId");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Value", v97);
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v114);
          v74 = v114;
        }
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"StackFilters");
      }
      if ( *((_QWORD *)v68 + 21) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"EventNameFilters");
        v75 = L"true";
        if ( !v68[259] )
          v75 = L"false";
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"FilterIn", v75);
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Level", (unsigned __int8)v68[184]);
        if ( v68[260] )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
          WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v98, *((_QWORD *)v68 + 22));
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        }
        v76 = **((_QWORD **)v68 + 20);
        v114 = v76;
        while ( !*(_BYTE *)(v76 + 25) )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"EventName");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Value", *(const unsigned __int16 **)(v76 + 32));
          *((_DWORD *)a1 + 5) -= 2;
          if ( !*((_BYTE *)a1 + 16) )
          {
            std::exception::exception((std::exception *)v123, "wszName");
            v123[0] = &std::invalid_argument::`vftable';
            throw (std::invalid_argument *)v123;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" />\n");
          *((_BYTE *)a1 + 16) = 0;
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v114);
          v76 = v114;
        }
        *((_DWORD *)a1 + 5) -= 2;
        if ( *((_BYTE *)a1 + 16) )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L" />\n");
        else
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a1,
            L"%*ws</%ws>\n",
            *((unsigned int *)a1 + 5),
            &LocaleName,
            L"EventNameFilters");
        *((_BYTE *)a1 + 16) = 0;
        v68 = v118;
        v10 = a5;
      }
      if ( *((_QWORD *)v68 + 13) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"StackEventNameFilters");
        v77 = L"true";
        if ( !v68[254] )
          v77 = L"false";
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"FilterIn", v77);
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Level", (unsigned __int8)v68[120]);
        if ( v68[255] )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
          WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v78, *((_QWORD *)v68 + 14));
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        }
        v79 = **((_QWORD **)v68 + 12);
        v114 = v79;
        while ( !*(_BYTE *)(v79 + 25) )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"EventName");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Value", *(const unsigned __int16 **)(v79 + 32));
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v114);
          v79 = v114;
        }
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"StackEventNameFilters");
      }
      if ( v68[137] )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"StackKeywordLevelFilter");
        v99 = L"true";
        if ( !v68[256] )
          v99 = L"false";
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"FilterIn", v99);
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Level", (unsigned __int8)v68[136]);
        if ( v68[257] )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"Keyword");
          WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, v100, *((_QWORD *)v68 + 16));
          WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
        }
        WindowsPerformanceRecorder::CXmlWriter::End(a1, L"StackKeywordLevelFilter");
      }
      if ( *((_DWORD *)v68 + 56) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a1, L"CustomFilter");
        WindowsPerformanceRecorder::CXmlWriter::Attr(a1, L"Value", *((const unsigned __int16 **)v68 + 27));
        WindowsPerformanceRecorder::CXmlWriter::AttrHex(a1, L"Type", *((_DWORD *)v68 + 57));
        WindowsPerformanceRecorder::CXmlWriter::End(a1, 0);
      }
      *((_DWORD *)a1 + 5) -= 2;
      if ( *((_BYTE *)a1 + 16) )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a1,
          L" />\n");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a1,
          L"%*ws</%ws>\n",
          *((unsigned int *)a1 + 5),
          &LocaleName,
          L"EventProvider");
      *((_BYTE *)a1 + 16) = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v36 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v36 - 3) + 8LL))(*((_QWORD *)v36 - 3));
      v6 = a3;
      v7 = a2;
      v12 = v117;
LABEL_17:
      v12 = (struct WindowsPerformanceRecorder::CWPRControl *)((char *)v12 + 264);
      LOBYTE(v5) = a4;
      v13 = v121[0];
      v9 = v112;
    }
    *v35 = 0;
LABEL_214:
    *(_DWORD *)_o__errno(v35, v21) = 22;
    invalid_parameter_noinfo();
    goto LABEL_45;
  }
  return result;
}

```

## disassembly

```asm
0x1800113e0  mov     rax, rsp
0x1800113e3  mov     [rax+20h], r9b
0x1800113e7  mov     [rax+18h], r8b
0x1800113eb  mov     [rax+10h], rdx
0x1800113ef  mov     [rax+8], rcx
0x1800113f3  push    rbx
0x1800113f4  push    rsi
0x1800113f5  push    rdi
0x1800113f6  push    r12
0x1800113f8  push    r13
0x1800113fa  push    r14
0x1800113fc  push    r15
0x1800113fe  sub     rsp, 100h
0x180011405  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x18001140d  movzx   ebx, r9b
0x180011411  movzx   esi, r8b
0x180011415  mov     r13, rdx
0x180011418  lea     rcx, [rax-88h]; struct WindowsPerformanceRecorder::CWPRControl **
0x18001141f  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x180011424  test    eax, eax
0x180011426  js      loc_1800120F0
0x18001142c  mov     rax, [r13+8]
0x180011430  mov     eax, [rax+40h]
0x180011433  and     eax, 1000000h
0x180011438  mov     [rsp+138h+var_98], eax
0x18001143f  mov     dl, 1
0x180011441  mov     [rsp+138h+var_C8], dl
0x180011445  movzx   edi, [rsp+138h+arg_20]
0x18001144d  test    dil, dil
0x180011450  jz      loc_18001212B
0x180011456  mov     eax, 30h ; '0'
0x18001145b  mov     r9, [rax+r13]
0x18001145f  mov     rax, [rax+r13+8]
0x180011464  mov     [rsp+138h+var_88], rax
0x18001146c  lea     r10, __ImageBase
0x180011473  mov     r11, 0FFFEFFFFFFFFFFFFh
0x18001147d  mov     r8, 1000000000000h
0x180011487  mov     [rsp+138h+var_A8], r9
0x18001148f  cmp     r9, rax
0x180011492  jz      loc_1800120EE
0x180011498  mov     r15, r9
0x18001149b  mov     rcx, [r9+10h]
0x18001149f  mov     [rsp+138h+var_B8], rcx
0x1800114a7  mov     rax, r9
0x1800114aa  mov     [rsp+138h+var_A0], rax
0x1800114b2  test    dil, dil
0x1800114b5  jnz     short loc_18001152C
0x1800114b7  test    bl, bl
0x1800114b9  jnz     short loc_18001152C
0x1800114bb  mov     rbx, [r13+18h]
0x1800114bf  mov     rdi, [r13+20h]
0x1800114c3  cmp     rbx, rdi
0x1800114c6  jz      short loc_180011524
0x1800114c8  nop     dword ptr [rax+rax+00000000h]
0x1800114d0  mov     r8d, 10h; Size
0x1800114d6  mov     rdx, r9; Buf2
0x1800114d9  mov     rcx, rbx; Buf1
0x1800114dc  call    memcmp_0
0x1800114e1  mov     r9, [rsp+138h+var_A8]
0x1800114e9  test    eax, eax
0x1800114eb  jz      short loc_180011569
0x1800114ed  add     rbx, 108h
0x1800114f4  cmp     rbx, rdi
0x1800114f7  jnz     short loc_1800114D0
0x1800114f9  mov     rax, r15
0x1800114fc  mov     r11, 0FFFEFFFFFFFFFFFFh
0x180011506  mov     r8, 1000000000000h
0x180011510  lea     r10, __ImageBase
0x180011517  movzx   edx, [rsp+138h+var_C8]
0x18001151c  mov     rcx, [rsp+138h+var_B8]
0x180011524  movzx   edi, [rsp+138h+arg_20]
0x18001152c  test    sil, sil
0x18001152f  jnz     loc_18001213F
0x180011535  cmp     byte ptr [r13+0D1h], 0
0x18001153d  jz      short loc_180011576
0x18001153f  cmp     byte ptr [rax+105h], 0
0x180011546  jz      short loc_180011576
0x180011548  add     r9, 108h
0x18001154f  movzx   ebx, [rsp+138h+arg_18]
0x180011557  mov     rax, [rsp+138h+var_88]
0x18001155f  movzx   edx, [rsp+138h+var_C8]
0x180011564  jmp     loc_18001146C
0x180011569  mov     rax, rbx
0x18001156c  mov     [rsp+138h+var_A0], rbx
0x180011574  jmp     short loc_1800114FC
0x180011576  cmp     dword ptr [r13+0], 1
0x18001157b  jz      loc_1800116CB
0x180011581  mov     eax, [r9+0E8h]
0x180011588  mov     [rsp+138h+var_AC], eax
0x18001158f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011596  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001159d  mov     rax, [rax+18h]
0x1800115a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115a6  add     rax, 18h
0x1800115aa  mov     [rsp+138h+Src], rax
0x1800115b2  movzx   eax, byte ptr [r15+0Fh]
0x1800115b7  movzx   ecx, byte ptr [r15+0Eh]
0x1800115bc  movzx   edx, byte ptr [r15+0Dh]
0x1800115c1  movzx   r10d, byte ptr [r15+0Ch]
0x1800115c6  movzx   r11d, byte ptr [r15+0Bh]
0x1800115cb  movzx   ebx, byte ptr [r15+0Ah]
0x1800115d0  movzx   edi, byte ptr [r15+9]
0x1800115d5  movzx   esi, byte ptr [r15+8]
0x1800115da  movzx   r14d, word ptr [r15+6]
0x1800115df  movzx   r9d, word ptr [r15+4]
0x1800115e4  mov     [rsp+138h+var_D8], eax
0x1800115e8  mov     dword ptr [rsp+138h+var_E0], ecx
0x1800115ec  mov     dword ptr [rsp+138h+var_E8], edx
0x1800115f0  mov     dword ptr [rsp+138h+var_F0], r10d
0x1800115f5  mov     dword ptr [rsp+138h+var_F8], r11d
0x1800115fa  mov     dword ptr [rsp+138h+var_100], ebx
0x1800115fe  mov     dword ptr [rsp+138h+var_108], edi
0x180011602  mov     dword ptr [rsp+138h+var_110], esi
0x180011606  mov     [rsp+138h+var_118], r14d
0x18001160b  mov     r8d, [r15]
0x18001160e  lea     rdx, a08x04x04x02x02_0; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180011615  lea     rcx, [rsp+138h+Src]
0x18001161d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180011622  nop
0x180011623  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001162a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180011631  mov     rax, [rax+18h]
0x180011635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001163a  lea     rsi, [rax+18h]
0x18001163e  mov     r12, rsi
0x180011641  mov     [rsp+138h+var_C0], rsi
0x180011646  mov     rdi, [r13+0C0h]
0x18001164d  test    rdi, rdi
0x180011650  jz      loc_180012103
0x180011656  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001165d  nop     dword ptr [rax]
0x180011660  inc     rbx
0x180011663  cmp     word ptr [rdi+rbx*2], 0
0x180011668  jnz     short loc_180011660
0x18001166a  test    ebx, ebx
0x18001166c  jz      loc_180012117
0x180011672  mov     r14d, [rsi-10h]
0x180011676  mov     ecx, 1
0x18001167b  sub     ecx, [rsi-8]
0x18001167e  mov     eax, [rsi-0Ch]
0x180011681  sub     eax, ebx
0x180011683  or      ecx, eax
0x180011685  jge     short loc_180011698
0x180011687  mov     edx, ebx
0x180011689  lea     rcx, [rsp+138h+var_C0]
0x18001168e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180011693  mov     r12, [rsp+138h+var_C0]
0x180011698  mov     rcx, rdi
0x18001169b  sub     rcx, rsi
0x18001169e  sar     rcx, 1
0x1800116a1  movsxd  rax, ebx
0x1800116a4  lea     rsi, [rax+rax]
0x1800116a8  cmp     rcx, r14
0x1800116ab  jbe     loc_180012197
0x1800116b1  test    rsi, rsi
0x1800116b4  jz      short loc_18001170E
0x1800116b6  test    r12, r12
0x1800116b9  jz      short loc_1800116FD
0x1800116bb  mov     r8, rsi; Size
0x1800116be  mov     rdx, rdi; Src
0x1800116c1  mov     rcx, r12; void *
0x1800116c4  call    memcpy_0
0x1800116c9  jmp     short loc_18001170E
0x1800116cb  xor     r8d, r8d
0x1800116ce  cmp     r8d, 11h
0x1800116d2  jnb     loc_180011581
0x1800116d8  mov     rdx, ds:rva off_1800920F0[r10+r8*8]; struct _GUID *
0x1800116e0  mov     rcx, rax; struct _GUID *
0x1800116e3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800116e8  test    eax, eax
0x1800116ea  jnz     loc_180011548
0x1800116f0  inc     r8d
0x1800116f3  mov     rax, [rsp+138h+var_A0]
0x1800116fb  jmp     short loc_1800116CE
0x1800116fd  call    cs:__imp__o__errno
0x180011703  mov     dword ptr [rax], 16h
0x180011709  call    _invalid_parameter_noinfo
0x18001170e  test    ebx, ebx
0x180011710  js      loc_1800121AE
0x180011716  cmp     ebx, [r12-0Ch]
0x18001171b  jg      loc_1800121AE
0x180011721  mov     [r12-10h], ebx
0x180011726  xor     eax, eax
0x180011728  mov     [r12+rsi], ax
0x18001172d  lea     rbx, asc_180094964; "_"
0x180011734  sub     rbx, r12
0x180011737  mov     esi, [r12-10h]
0x18001173c  lea     edi, [rsi+1]
0x18001173f  mov     ecx, 1
0x180011744  sub     ecx, [r12-8]
0x180011749  mov     eax, [r12-0Ch]
0x18001174e  sub     eax, edi
0x180011750  or      ecx, eax
0x180011752  jge     short loc_180011765
0x180011754  mov     edx, edi
0x180011756  lea     rcx, [rsp+138h+var_C0]
0x18001175b  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180011760  mov     r12, [rsp+138h+var_C0]
0x180011765  sar     rbx, 1
0x180011768  cmp     rbx, rsi
0x18001176b  jbe     loc_1800121B8
0x180011771  lea     rax, asc_180094964; "_"
0x180011778  lea     rcx, [r12+rsi*2]
0x18001177c  test    rcx, rcx
0x18001177f  jz      loc_1800121C4
0x180011785  test    rax, rax
0x180011788  jz      loc_1800121C1
0x18001178e  movzx   eax, word ptr [rax]
0x180011791  mov     [rcx], ax
0x180011794  test    edi, edi
0x180011796  js      loc_1800128DB
0x18001179c  cmp     edi, [r12-0Ch]
0x1800117a1  jg      loc_1800128DB
0x1800117a7  mov     [r12-10h], edi
0x1800117ac  movsxd  rcx, edi
0x1800117af  xor     eax, eax
0x1800117b1  mov     [r12+rcx*2], ax
0x1800117b6  mov     r13, [rsp+138h+Src]
0x1800117be  movsxd  r15, dword ptr [r13-10h]
0x1800117c2  mov     r14, r13
0x1800117c5  mov     rbx, r13
0x1800117c8  sub     rbx, r12
0x1800117cb  mov     esi, [r12-10h]
0x1800117d0  lea     edi, [r15+rsi]
0x1800117d4  mov     ecx, 1
0x1800117d9  sub     ecx, [r12-8]
0x1800117de  mov     eax, [r12-0Ch]
0x1800117e3  sub     eax, edi
0x1800117e5  or      ecx, eax
0x1800117e7  jge     short loc_1800117FA
0x1800117e9  mov     edx, edi
0x1800117eb  lea     rcx, [rsp+138h+var_C0]
0x1800117f0  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800117f5  mov     r12, [rsp+138h+var_C0]
0x1800117fa  sar     rbx, 1
0x1800117fd  cmp     rbx, rsi
0x180011800  jbe     loc_1800121DA
0x180011806  mov     r8, r15
0x180011809  add     r8, r8; Size
0x18001180c  jz      short loc_18001182C
0x18001180e  lea     rcx, [r12+rsi*2]; void *
0x180011812  test    rcx, rcx
0x180011815  jz      loc_1800121EA
0x18001181b  test    r14, r14
0x18001181e  jz      loc_1800121E3
0x180011824  mov     rdx, r14; Src
0x180011827  call    memcpy_0
0x18001182c  test    edi, edi
0x18001182e  js      loc_1800128D1
0x180011834  cmp     edi, [r12-0Ch]
0x180011839  jg      loc_1800128D1
0x18001183f  mov     [r12-10h], edi
0x180011844  movsxd  rcx, edi
0x180011847  xor     eax, eax
0x180011849  mov     [r12+rcx*2], ax
0x18001184e  cmp     [rsp+138h+arg_20], al
0x180011855  jnz     loc_180012200
0x18001185b  xor     dl, dl
0x18001185d  mov     rcx, r12
0x180011860  mov     edi, [r12-10h]
0x180011865  xor     eax, eax
0x180011867  cmp     eax, edi
0x180011869  jge     short loc_180011885
0x18001186b  cdqe
0x18001186d  lea     rbx, [rax+rax]
0x180011871  cmp     word ptr [rbx+rcx], 3Ah ; ':'
0x180011876  jz      loc_18001201D
0x18001187c  lea     rax, [rbx+2]
0x180011880  sar     rax, 1
0x180011883  jmp     short loc_180011867
0x180011885  test    dl, dl
0x180011887  jnz     loc_18001221B
0x18001188d  xor     dl, dl
0x18001188f  mov     rcx, r12
0x180011892  mov     edi, [r12-10h]
0x180011897  xor     eax, eax
0x180011899  nop     dword ptr [rax+00000000h]
0x1800118a0  cmp     eax, edi
0x1800118a2  jge     short loc_1800118BE
0x1800118a4  cdqe
0x1800118a6  lea     rbx, [rax+rax]
0x1800118aa  cmp     word ptr [rcx+rbx], 20h ; ' '
0x1800118af  jz      loc_180012057
0x1800118b5  lea     rax, [rbx+2]
0x1800118b9  sar     rax, 1
0x1800118bc  jmp     short loc_1800118A0
0x1800118be  test    dl, dl
0x1800118c0  jnz     loc_18001222C
0x1800118c6  mov     r14, [rsp+138h+arg_0]
0x1800118ce  cmp     byte ptr [r14+10h], 0
0x1800118d3  jnz     loc_18001223D
0x1800118d9  lea     r15, aEventprovider; "EventProvider"
0x1800118e0  mov     qword ptr [rsp+138h+var_118], r15; unsigned int
0x1800118e5  lea     r9, LocaleName
0x1800118ec  mov     r8d, [r14+14h]
0x1800118f0  lea     rdx, aWsWs_2; "%*ws<%ws"
0x1800118f7  mov     rcx, r14
0x1800118fa  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800118ff  add     dword ptr [r14+14h], 2
0x180011904  mov     byte ptr [r14+10h], 1
  ... truncated ...
```
