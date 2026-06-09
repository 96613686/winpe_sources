# WindowsPerformanceRecorder::CETWProperties::TranslateToXML(WindowsPerformanceRecorder::CXmlWriter &,bool,bool,WindowsPerformanceRecorder::CProfilesCache &)

- ea: `0x180042638`
- end: `0x1800431fd`
- name: `?TranslateToXML@CETWProperties@WindowsPerformanceRecorder@@QEBAJAEAVCXmlWriter@2@_N1AEAVCProfilesCache@2@@Z`
- size: `3013`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CETWProperties *__hidden this, struct WindowsPerformanceRecorder::CXmlWriter *, bool, bool, struct WindowsPerformanceRecorder::CProfilesCache *)`
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032adc`
- `0x18004ac00`
- `0x18005f068`
- `0x18006eda0`

## callees

- `0x1800024d0`
- `0x180008330`
- `0x180009a84`
- `0x18000eeb0`
- `0x1800102d8`
- `0x1800128f8`
- `0x180013038`
- `0x180013094`
- `0x1800131a0`
- `0x18001b920`
- `0x18001e6b8`
- `0x180021b7c`
- `0x1800234f0`
- `0x180025580`
- `0x180035250`
- `0x18003e33c`
- `0x180042638`
- `0x180043294`
- `0x1800432bc`
- `0x180044210`
- `0x18004b46c`
- `0x18004f970`
- `0x1800656e4`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800431b8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800431b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180043189`
- `OLEAUT32!__imp_SysFreeString` at `0x1800431a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180043189`
- `OLEAUT32!__imp_SysFreeString` at `0x1800431a2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180043140`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180043140`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180043195`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180043195`

## string_xrefs

- `0x1800428d4`: `SystemProviderId`
- `0x180042eb8`: `FileCompression`
- `0x180042e73`: `DeletePreMergedTraceFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::TranslateToXML(
        WindowsPerformanceRecorder::CETWProperties *this,
        struct WindowsPerformanceRecorder::CXmlWriter *a2,
        bool a3,
        bool a4,
        struct WindowsPerformanceRecorder::CProfilesCache *a5)
{
  __int64 result; // rax
  double v10; // xmm6_8
  unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // rbx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v14; // r15
  char *SessionName; // rax
  __int64 v16; // rcx
  char v17; // al
  bool v18; // zf
  const struct WindowsPerformanceRecorder::CEventProvidersCache *v19; // rdx
  const struct WindowsPerformanceRecorder::CEventProvidersCache *v20; // rdx
  int v21; // ebx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v22; // r12
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v23; // r13
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v24; // r15
  char *v25; // rax
  const struct WindowsPerformanceRecorder::CEventProvidersCache *v26; // rdx
  const struct WindowsPerformanceRecorder::CEventProvidersCache *v27; // rdx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **j; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v29; // rbx
  char *v30; // rax
  __int64 v31; // rcx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v32; // r15
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v33; // r12
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v34; // rbx
  char *v35; // rax
  const struct WindowsPerformanceRecorder::CEventProvidersCache *v36; // rdx
  __int64 v37; // r8
  const unsigned __int16 *v38; // rax
  const unsigned __int16 *v39; // rbx
  const unsigned __int16 *v40; // r8
  const unsigned __int16 *v41; // r8
  const unsigned __int16 *v42; // r8
  unsigned __int16 *v43; // rbx
  unsigned __int16 *v44; // rbx
  const char *v45; // rdx
  HRESULT v46; // r14d
  unsigned int v47; // edi
  unsigned __int16 *v48; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int16 *v49; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int16 *v50; // [rsp+40h] [rbp-78h] BYREF
  HRESULT v51; // [rsp+48h] [rbp-70h]
  __int64 v52; // [rsp+50h] [rbp-68h]
  ATL::CAtlException *v53; // [rsp+58h] [rbp-60h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp-58h] BYREF

  v52 = -2;
  result = WindowsPerformanceRecorder::CWPRControl::GetInstance((struct WindowsPerformanceRecorder::CWPRControl **)&v49);
  if ( (int)result >= 0 )
  {
    try
    {
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"WindowsPerformanceRecorder");
      v10 = *((float *)this + 70);
      WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(a2);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L" %ws=\"%.*f\"",
        L"Version",
        1,
        v10);
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"Profiles");
      WindowsPerformanceRecorder::CETWProperties::WriteCollectors(this, a2);
      WindowsPerformanceRecorder::CETWProperties::WriteProviders(this, a2, a3, a4);
      v50 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v50,
        L"%ws:%ws",
        L"RunningProfile",
        *((_QWORD *)this + 40));
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"Profile");
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Id", *((const unsigned __int16 **)this + 39));
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Name", *((const unsigned __int16 **)this + 41));
      v11 = v50;
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Description", v50);
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"LoggingMode", *((const unsigned __int16 **)this + 33));
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"DetailLevel", *((const unsigned __int16 **)this + 34));
      if ( *((_QWORD *)this + 37) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"ProblemCategories");
        v12 = (unsigned __int16 *)**((_QWORD **)this + 36);
        v48 = v12;
        while ( !*((_BYTE *)v12 + 25) )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"ProblemCategory");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", *((const unsigned __int16 **)v12 + 4));
          WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v48);
          v12 = v48;
        }
        WindowsPerformanceRecorder::CXmlWriter::End(a2, L"ProblemCategories");
      }
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"Collectors");
      for ( i = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 1);
            i != *((WindowsPerformanceRecorder::CETWProperties::CEventSession ***)this + 2);
            ++i )
      {
        v14 = *i;
        if ( *(_DWORD *)*i == 1 )
        {
          SessionName = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*i);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v48,
            SessionName);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            58);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            32);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"SystemCollectorId");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
          v16 = *((_QWORD *)v14 + 1);
          if ( *(_DWORD *)(v16 + 72) )
          {
            if ( *(_WORD *)(*(unsigned __int16 *)(v16 + 72) + v16 + 2) )
            {
              ATL::CSimpleStringT<unsigned short,0>::Append(&v48, L"_Provider");
              WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"SystemProviderId");
              WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
              WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
            }
            if ( *((_QWORD *)this + 6) == *((_QWORD *)this + 7)
              || (v17 = 1, *((_QWORD *)this + 9) == *((_QWORD *)this + 10)) )
            {
              v17 = 0;
            }
            if ( *((_QWORD *)this + 12) != *((_QWORD *)this + 13)
              || v17
              || *((_QWORD *)this + 19) != *((_QWORD *)this + 20)
              || *((_QWORD *)this + 25) != *((_QWORD *)this + 26) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v49,
                *((char **)this + 4));
              WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"HardwareCounterId");
              WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v49);
              WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v49);
            }
            if ( *((_QWORD *)v14 + 6) != *((_QWORD *)v14 + 7)
              || (!a4
                ? (v18 = *((_QWORD *)v14 + 19) == *((_QWORD *)v14 + 20))
                : (v18 = *((_QWORD *)v14 + 3) == *((_QWORD *)v14 + 4)),
                  !v18) )
            {
              WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"EventProviders");
              v21 = WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(a2, v19, v14, a3, a4, 0);
              if ( v21 < 0
                || (v21 = WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(a2, v20, v14, a3, a4, 1),
                    v21 < 0) )
              {
LABEL_50:
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v48);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v50);
                result = (unsigned int)v21;
                goto LABEL_93;
              }
              WindowsPerformanceRecorder::CXmlWriter::End(a2, L"EventProviders");
            }
          }
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"SystemCollectorId");
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v48);
          break;
        }
      }
      v22 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 1);
      v23 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 2);
      while ( v22 != v23 )
      {
        v24 = *v22;
        if ( *(_DWORD *)*v22 == 2 )
        {
          v25 = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v22);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v48,
            v25);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            58);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            32);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"EventCollectorId");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"EventProviders");
          v21 = WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(a2, v26, v24, a3, a4, 0);
          if ( v21 < 0 )
            goto LABEL_50;
          v21 = WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(a2, v27, v24, a3, a4, 1);
          if ( v21 < 0 )
            goto LABEL_50;
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"EventProviders");
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"EventCollectorId");
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v48);
        }
        ++v22;
      }
      for ( j = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 1);
            j != *((WindowsPerformanceRecorder::CETWProperties::CEventSession ***)this + 2);
            ++j )
      {
        v29 = *j;
        if ( *(_DWORD *)*j == 3 )
        {
          v30 = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*j);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v48,
            v30);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            58);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            32);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"HeapEventCollectorId");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"HeapEventProviders");
          v31 = *((_QWORD *)v29 + 1);
          if ( *(_DWORD *)(v31 + 72) && *(_WORD *)(*(unsigned __int16 *)(v31 + 72) + v31 + 2) )
          {
            ATL::CSimpleStringT<unsigned short,0>::Append(&v48, L"_Provider");
            WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"HeapEventProviderId");
            WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
            WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
          }
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"HeapEventProviders");
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"HeapEventCollectorId");
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v48);
          break;
        }
      }
      v32 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 1);
      v33 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)this + 2);
      while ( v32 != v33 )
      {
        v34 = *v32;
        if ( *(_DWORD *)*v32 == 5 )
        {
          v35 = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v32);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v48,
            v35);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            58);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &v48,
            32);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"HypervisorEventCollectorId");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v48);
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"EventProviders");
          v21 = WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(a2, v36, v34, a3, a4, 0);
          if ( v21 < 0 )
            goto LABEL_50;
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"EventProviders");
          WindowsPerformanceRecorder::CXmlWriter::End(a2, L"HypervisorEventCollectorId");
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v48);
        }
        ++v32;
      }
      v37 = (unsigned int)(*((_DWORD *)a2 + 5) - 2);
      *((_DWORD *)a2 + 5) = v37;
      if ( *((_BYTE *)a2 + 16) )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L" />\n");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%*ws</%ws>\n",
          v37,
          &LocaleName,
          L"Collectors");
      *((_BYTE *)a2 + 16) = 0;
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"TraceMergeProperties");
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"TraceMergeProperty");
      v38 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 44) + 16LL))((char *)this + 352);
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Id", v38);
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Name", *((const unsigned __int16 **)this + 47));
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"DeletePreMergedTraceFiles");
      v39 = L"true";
      v40 = L"true";
      if ( !*((_BYTE *)this + 384) )
        v40 = L"false";
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v40);
      WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"FileCompression");
      v41 = L"true";
      if ( !*((_BYTE *)this + 408) )
        v41 = L"false";
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v41);
      WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"InjectOnly");
      v42 = L"true";
      if ( !*((_BYTE *)this + 409) )
        v42 = L"false";
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v42);
      WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
      WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"SkipMerge");
      if ( !*((_BYTE *)this + 410) )
        v39 = L"false";
      WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", v39);
      WindowsPerformanceRecorder::CXmlWriter::End(a2, 0);
      v43 = 0;
      if ( *((_QWORD *)this + 50) )
      {
        WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"CustomEvents");
        v44 = (unsigned __int16 *)**((_QWORD **)this + 49);
        v49 = v44;
        while ( !*((_BYTE *)v44 + 25) )
        {
          WindowsPerformanceRecorder::CXmlWriter::Start(a2, L"CustomEvent");
          WindowsPerformanceRecorder::CXmlWriter::Attr(a2, L"Value", **((const unsigned __int16 ***)v44 + 4));
          *((_DWORD *)a2 + 5) -= 2;
          if ( !*((_BYTE *)a2 + 16) )
          {
            std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, v45);
            throw (std::invalid_argument *)pExceptionObject;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a2,
            L" />\n");
          *((_BYTE *)a2 + 16) = 0;
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v49);
          v44 = v49;
        }
        *((_DWORD *)a2 + 5) -= 2;
        v43 = 0;
        if ( *((_BYTE *)a2 + 16) )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a2,
            L" />\n");
        else
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            a2,
            L"%*ws</%ws>\n",
            *((unsigned int *)a2 + 5),
            &LocaleName,
            L"CustomEvents");
        *((_BYTE *)a2 + 16) = 0;
      }
      *((_DWORD *)a2 + 5) -= 2;
      if ( *((_BYTE *)a2 + 16) )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L" />\n");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%*ws</%ws>\n",
          *((unsigned int *)a2 + 5),
          &LocaleName,
          L"TraceMergeProperty");
      *((_BYTE *)a2 + 16) = 0;
      *((_DWORD *)a2 + 5) -= 2;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L"%*ws</%ws>\n",
        *((unsigned int *)a2 + 5),
        &LocaleName,
        L"TraceMergeProperties");
      *((_BYTE *)a2 + 16) = 0;
      *((_DWORD *)a2 + 5) -= 2;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L"%*ws</%ws>\n",
        *((unsigned int *)a2 + 5),
        &LocaleName,
        L"Profile");
      *((_BYTE *)a2 + 16) = 0;
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
      *((_DWORD *)a2 + 5) -= 2;
      if ( *((_BYTE *)a2 + 16) )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L" />\n");
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%*ws</%ws>\n",
          *((unsigned int *)a2 + 5),
          &LocaleName,
          L"Profiles");
      *((_BYTE *)a2 + 16) = 0;
      *((_DWORD *)a2 + 5) -= 2;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        a2,
        L"%*ws</%ws>\n",
        *((unsigned int *)a2 + 5),
        &LocaleName,
        L"WindowsPerformanceRecorder");
      *((_BYTE *)a2 + 16) = 0;
      v50 = (unsigned __int16 *)&WindowsPerformanceRecorder::Impl::CAutoComInit::`vftable';
      v46 = CoInitializeEx(0, 0);
      v51 = v46;
      if ( *(_QWORD *)a2 )
      {
        v43 = SysAllocString(*(const OLECHAR **)a2);
        v49 = v43;
        if ( !v43 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v49 = 0;
      }
      v47 = WindowsPerformanceRecorder::CProfilesCache::ValidateProfileFromFileOrString(a5, v43, 0, 1);
      if ( (int)(v47 + 0x80000000) < 0 || v47 == -2147024846 )
      {
        SysFreeString(v43);
        WindowsPerformanceRecorder::Impl::CAutoComInit::~CAutoComInit((WindowsPerformanceRecorder::Impl::CAutoComInit *)&v50);
        result = 0;
      }
      else
      {
        SysFreeString(v43);
        if ( v46 >= 0 )
          CoUninitialize();
        result = v47;
      }
    }
    catch ( ATL::CAtlException *v53 )
    {
      result = *(unsigned int *)v53;
    }
LABEL_93:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x180042638  mov     rax, rsp
0x18004263b  mov     [rax+20h], r9b
0x18004263f  mov     [rax+18h], r8b
0x180042643  push    rdi
0x180042644  push    r12
0x180042646  push    r13
0x180042648  push    r14
0x18004264a  push    r15
0x18004264c  sub     rsp, 90h
0x180042653  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18004265b  mov     [rax+8], rbx
0x18004265f  mov     [rax+10h], rsi
0x180042663  movaps  xmmword ptr [rax-38h], xmm6
0x180042667  mov     r12b, r9b
0x18004266a  mov     r13b, r8b
0x18004266d  mov     rsi, rdx
0x180042670  mov     r14, rcx
0x180042673  lea     rcx, [rax-80h]; struct WindowsPerformanceRecorder::CWPRControl **
0x180042677  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x18004267c  xor     ebx, ebx
0x18004267e  test    eax, eax
0x180042680  js      loc_1800431DA
0x180042686  lea     rdx, aWindowsperform_2; "WindowsPerformanceRecorder"
0x18004268d  mov     rcx, rsi; this
0x180042690  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042695  movss   xmm6, dword ptr [r14+118h]
0x18004269e  cvtps2pd xmm6, xmm6
0x1800426a1  mov     rcx, rsi; this
0x1800426a4  call    ?_CheckAttr@CXmlWriter@WindowsPerformanceRecorder@@AEAAXXZ; WindowsPerformanceRecorder::CXmlWriter::_CheckAttr(void)
0x1800426a9  movsd   qword ptr [rsp+0B8h+var_98], xmm6
0x1800426af  lea     r9d, [rbx+1]
0x1800426b3  lea     r8, aVersion; "Version"
0x1800426ba  lea     rdx, aWsF; " %ws=\"%.*f\""
0x1800426c1  mov     rcx, rsi
0x1800426c4  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800426c9  lea     rdx, aProfiles; "Profiles"
0x1800426d0  mov     rcx, rsi; this
0x1800426d3  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800426d8  mov     rdx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
0x1800426db  mov     rcx, r14; this
0x1800426de  call    ?WriteCollectors@CETWProperties@WindowsPerformanceRecorder@@AEBAJAEAVCXmlWriter@2@@Z; WindowsPerformanceRecorder::CETWProperties::WriteCollectors(WindowsPerformanceRecorder::CXmlWriter &)
0x1800426e3  mov     r9b, r12b; bool
0x1800426e6  mov     r8b, r13b; bool
0x1800426e9  mov     rdx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
0x1800426ec  mov     rcx, r14; this
0x1800426ef  call    ?WriteProviders@CETWProperties@WindowsPerformanceRecorder@@AEBAJAEAVCXmlWriter@2@_N1@Z; WindowsPerformanceRecorder::CETWProperties::WriteProviders(WindowsPerformanceRecorder::CXmlWriter &,bool,bool)
0x1800426f4  nop
0x1800426f5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800426fc  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180042703  mov     rax, [rax+18h]
0x180042707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004270c  add     rax, 18h
0x180042710  mov     [rsp+0B8h+var_78], rax
0x180042715  mov     r9, [r14+140h]
0x18004271c  lea     r8, aRunningprofile_0; "RunningProfile"
0x180042723  lea     rdx, aWsWs_0; "%ws:%ws"
0x18004272a  lea     rcx, [rsp+0B8h+var_78]
0x18004272f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180042734  lea     rdx, aProfile; "Profile"
0x18004273b  mov     rcx, rsi; this
0x18004273e  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042743  mov     r8, [r14+138h]; unsigned __int16 *
0x18004274a  lea     rdx, aId; "Id"
0x180042751  mov     rcx, rsi; this
0x180042754  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180042759  mov     r8, [r14+148h]; unsigned __int16 *
0x180042760  lea     rdx, aName; "Name"
0x180042767  mov     rcx, rsi; this
0x18004276a  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x18004276f  mov     rdi, [rsp+0B8h+var_78]
0x180042774  mov     r8, rdi; unsigned __int16 *
0x180042777  lea     rdx, aDescription; "Description"
0x18004277e  mov     rcx, rsi; this
0x180042781  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180042786  mov     r8, [r14+108h]; unsigned __int16 *
0x18004278d  lea     rdx, aLoggingmode; "LoggingMode"
0x180042794  mov     rcx, rsi; this
0x180042797  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x18004279c  mov     r8, [r14+110h]; unsigned __int16 *
0x1800427a3  lea     rdx, aDetaillevel; "DetailLevel"
0x1800427aa  mov     rcx, rsi; this
0x1800427ad  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x1800427b2  cmp     [r14+128h], rbx
0x1800427b9  jz      short loc_18004282A
0x1800427bb  lea     rdx, aProblemcategor; "ProblemCategories"
0x1800427c2  mov     rcx, rsi; this
0x1800427c5  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800427ca  mov     rbx, [r14+120h]
0x1800427d1  mov     rbx, [rbx]
0x1800427d4  mov     [rsp+0B8h+var_88], rbx
0x1800427d9  mov     rcx, rsi; this
0x1800427dc  cmp     byte ptr [rbx+19h], 0
0x1800427e0  jnz     short loc_18004281C
0x1800427e2  lea     rdx, aProblemcategor_0; "ProblemCategory"
0x1800427e9  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800427ee  mov     r8, [rbx+20h]; unsigned __int16 *
0x1800427f2  lea     rdx, aValue; "Value"
0x1800427f9  mov     rcx, rsi; this
0x1800427fc  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180042801  xor     edx, edx; unsigned __int16 *
0x180042803  mov     rcx, rsi; this
0x180042806  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x18004280b  lea     rcx, [rsp+0B8h+var_88]
0x180042810  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x180042815  mov     rbx, [rsp+0B8h+var_88]
0x18004281a  jmp     short loc_1800427D9
0x18004281c  lea     rdx, aProblemcategor; "ProblemCategories"
0x180042823  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180042828  xor     ebx, ebx
0x18004282a  lea     rdx, aCollectors; "Collectors"
0x180042831  mov     rcx, rsi; this
0x180042834  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042839  mov     rax, [r14+8]
0x18004283d  cmp     rax, [r14+10h]
0x180042841  jz      loc_180042A68
0x180042847  mov     r15, [rax]
0x18004284a  cmp     dword ptr [r15], 1
0x18004284e  jnz     loc_180042BAA
0x180042854  mov     rcx, r15; this
0x180042857  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18004285c  mov     rdx, rax
0x18004285f  lea     rcx, [rsp+0B8h+var_88]
0x180042864  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180042869  nop
0x18004286a  mov     edx, 3Ah ; ':'
0x18004286f  lea     rcx, [rsp+0B8h+var_88]
0x180042874  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180042879  mov     edx, 20h ; ' '
0x18004287e  lea     rcx, [rsp+0B8h+var_88]
0x180042883  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180042888  lea     rdx, aSystemcollecto_0; "SystemCollectorId"
0x18004288f  mov     rcx, rsi; this
0x180042892  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042897  mov     r8, [rsp+0B8h+var_88]; unsigned __int16 *
0x18004289c  lea     rdx, aValue; "Value"
0x1800428a3  mov     rcx, rsi; this
0x1800428a6  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x1800428ab  mov     rcx, [r15+8]
0x1800428af  cmp     [rcx+48h], ebx
0x1800428b2  jz      loc_180042A4E
0x1800428b8  movzx   eax, word ptr [rcx+48h]
0x1800428bc  cmp     [rax+rcx+2], bx
0x1800428c1  jz      short loc_180042901
0x1800428c3  lea     rdx, aProvider; "_Provider"
0x1800428ca  lea     rcx, [rsp+0B8h+var_88]
0x1800428cf  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800428d4  lea     rdx, aSystemprovider; "SystemProviderId"
0x1800428db  mov     rcx, rsi; this
0x1800428de  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800428e3  mov     r8, [rsp+0B8h+var_88]; unsigned __int16 *
0x1800428e8  lea     rdx, aValue; "Value"
0x1800428ef  mov     rcx, rsi; this
0x1800428f2  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x1800428f7  xor     edx, edx; unsigned __int16 *
0x1800428f9  mov     rcx, rsi; this
0x1800428fc  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180042901  mov     rcx, [r14+68h]
0x180042905  mov     rax, [r14+38h]
0x180042909  cmp     [r14+30h], rax
0x18004290d  jz      short loc_18004291B
0x18004290f  mov     rax, [r14+50h]
0x180042913  cmp     [r14+48h], rax
0x180042917  mov     al, 1
0x180042919  jnz     short loc_18004291D
0x18004291b  mov     al, bl
0x18004291d  cmp     [r14+60h], rcx
0x180042921  jnz     short loc_180042947
0x180042923  test    al, al
0x180042925  jnz     short loc_180042947
0x180042927  mov     rax, [r14+0A0h]
0x18004292e  cmp     [r14+98h], rax
0x180042935  jnz     short loc_180042947
0x180042937  mov     rax, [r14+0D0h]
0x18004293e  cmp     [r14+0C8h], rax
0x180042945  jz      short loc_18004298E
0x180042947  mov     rdx, [r14+20h]
0x18004294b  lea     rcx, [rsp+0B8h+var_80]
0x180042950  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180042955  nop
0x180042956  lea     rdx, aHardwarecounte; "HardwareCounterId"
0x18004295d  mov     rcx, rsi; this
0x180042960  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042965  mov     r8, [rsp+0B8h+var_80]; unsigned __int16 *
0x18004296a  lea     rdx, aValue; "Value"
0x180042971  mov     rcx, rsi; this
0x180042974  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180042979  xor     edx, edx; unsigned __int16 *
0x18004297b  mov     rcx, rsi; this
0x18004297e  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180042983  nop
0x180042984  lea     rcx, [rsp+0B8h+var_80]; this
0x180042989  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004298e  mov     rax, [r15+38h]
0x180042992  cmp     [r15+30h], rax
0x180042996  jnz     short loc_1800429BB
0x180042998  test    r12b, r12b
0x18004299b  jz      short loc_1800429A7
0x18004299d  mov     rax, [r15+20h]
0x1800429a1  cmp     [r15+18h], rax
0x1800429a5  jmp     short loc_1800429B5
0x1800429a7  mov     rax, [r15+0A0h]
0x1800429ae  cmp     [r15+98h], rax
0x1800429b5  jz      loc_180042A4E
0x1800429bb  lea     rdx, aEventproviders; "EventProviders"
0x1800429c2  mov     rcx, rsi; this
0x1800429c5  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x1800429ca  mov     [rsp+0B8h+var_90], bl; bool
0x1800429ce  mov     [rsp+0B8h+var_98], r12b; bool
0x1800429d3  mov     r9b, r13b; bool
0x1800429d6  mov     r8, r15; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x1800429d9  mov     rcx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
0x1800429dc  call    ?WriteEventProviderId@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBVCEventProvidersCache@2@PEBUCEventSession@12@_N33@Z; WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CEventProvidersCache const *,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool,bool,bool)
0x1800429e1  mov     ebx, eax
0x1800429e3  test    eax, eax
0x1800429e5  jns     short loc_180042A03
0x1800429e7  lea     rcx, [rsp+0B8h+var_88]; this
0x1800429ec  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800429f1  nop
0x1800429f2  lea     rcx, [rsp+0B8h+var_78]; this
0x1800429f7  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800429fc  mov     eax, ebx
0x1800429fe  jmp     loc_1800431DA
0x180042a03  mov     [rsp+0B8h+var_90], 1; bool
0x180042a08  mov     [rsp+0B8h+var_98], r12b; bool
0x180042a0d  mov     r9b, r13b; bool
0x180042a10  mov     r8, r15; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180042a13  mov     rcx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
0x180042a16  call    ?WriteEventProviderId@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBVCEventProvidersCache@2@PEBUCEventSession@12@_N33@Z; WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CEventProvidersCache const *,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool,bool,bool)
0x180042a1b  mov     ebx, eax
0x180042a1d  test    eax, eax
0x180042a1f  jns     short loc_180042A3D
0x180042a21  lea     rcx, [rsp+0B8h+var_88]; this
0x180042a26  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180042a2b  nop
0x180042a2c  lea     rcx, [rsp+0B8h+var_78]; this
0x180042a31  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180042a36  mov     eax, ebx
0x180042a38  jmp     loc_1800431DA
0x180042a3d  lea     rdx, aEventproviders; "EventProviders"
0x180042a44  mov     rcx, rsi; this
0x180042a47  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180042a4c  xor     ebx, ebx
0x180042a4e  lea     rdx, aSystemcollecto_0; "SystemCollectorId"
0x180042a55  mov     rcx, rsi; this
0x180042a58  call    ?End@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::End(ushort const *)
0x180042a5d  nop
0x180042a5e  lea     rcx, [rsp+0B8h+var_88]; this
0x180042a63  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180042a68  mov     r12, [r14+8]
0x180042a6c  mov     r13, [r14+10h]
0x180042a70  cmp     r12, r13
0x180042a73  jz      loc_180042BB3
0x180042a79  mov     r15, [r12]
0x180042a7d  cmp     dword ptr [r15], 2
0x180042a81  jnz     loc_180042B9F
0x180042a87  mov     rcx, r15; this
0x180042a8a  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180042a8f  mov     rdx, rax
0x180042a92  lea     rcx, [rsp+0B8h+var_88]
0x180042a97  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180042a9c  nop
0x180042a9d  mov     edx, 3Ah ; ':'
0x180042aa2  lea     rcx, [rsp+0B8h+var_88]
0x180042aa7  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180042aac  mov     edx, 20h ; ' '
0x180042ab1  lea     rcx, [rsp+0B8h+var_88]
0x180042ab6  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x180042abb  lea     rdx, aEventcollector_0; "EventCollectorId"
0x180042ac2  mov     rcx, rsi; this
0x180042ac5  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042aca  mov     r8, [rsp+0B8h+var_88]; unsigned __int16 *
0x180042acf  lea     rdx, aValue; "Value"
0x180042ad6  mov     rcx, rsi; this
0x180042ad9  call    ?Attr@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG0@Z; WindowsPerformanceRecorder::CXmlWriter::Attr(ushort const *,ushort const *)
0x180042ade  lea     rdx, aEventproviders; "EventProviders"
0x180042ae5  mov     rcx, rsi; this
0x180042ae8  call    ?Start@CXmlWriter@WindowsPerformanceRecorder@@QEAAXPEBG@Z; WindowsPerformanceRecorder::CXmlWriter::Start(ushort const *)
0x180042aed  mov     [rsp+0B8h+var_90], bl; bool
0x180042af1  mov     al, [rsp+0B8h+arg_18]
0x180042af8  mov     [rsp+0B8h+var_98], al; bool
0x180042afc  mov     r9b, [rsp+0B8h+arg_10]; bool
0x180042b04  mov     r8, r15; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180042b07  mov     rcx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
0x180042b0a  call    ?WriteEventProviderId@CETWProperties@WindowsPerformanceRecorder@@CAJAEAVCXmlWriter@2@PEBVCEventProvidersCache@2@PEBUCEventSession@12@_N33@Z; WindowsPerformanceRecorder::CETWProperties::WriteEventProviderId(WindowsPerformanceRecorder::CXmlWriter &,WindowsPerformanceRecorder::CEventProvidersCache const *,WindowsPerformanceRecorder::CETWProperties::CEventSession const *,bool,bool,bool)
0x180042b0f  mov     ebx, eax
0x180042b11  test    eax, eax
0x180042b13  jns     short loc_180042B31
0x180042b15  lea     rcx, [rsp+0B8h+var_88]; this
0x180042b1a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180042b1f  nop
0x180042b20  lea     rcx, [rsp+0B8h+var_78]; this
0x180042b25  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180042b2a  mov     eax, ebx
0x180042b2c  jmp     loc_1800431DA
0x180042b31  mov     [rsp+0B8h+var_90], 1; bool
0x180042b36  mov     al, [rsp+0B8h+arg_18]
0x180042b3d  mov     [rsp+0B8h+var_98], al; bool
0x180042b41  mov     r9b, [rsp+0B8h+arg_10]; bool
0x180042b49  mov     r8, r15; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180042b4c  mov     rcx, rsi; struct WindowsPerformanceRecorder::CXmlWriter *
  ... truncated ...
```
