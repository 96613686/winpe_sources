# CDeploymentSession::GetOffsetInOuterContainer(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800613b4`
- end: `0x1800621c3`
- name: `?GetOffsetInOuterContainer@CDeploymentSession@@QEAAJPEB_W000PEA_K1@Z`
- size: `3599`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004478c`
- `0x18004f0b0`
- `0x180054e0c`
- `0x180057b60`
- `0x18007c740`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x180006a18`
- `0x180012430`
- `0x180016014`
- `0x18001f35c`
- `0x18001fd10`
- `0x180020360`
- `0x180020d18`
- `0x180023ab0`
- `0x180023b20`
- `0x180025540`
- `0x180027ea4`
- `0x180028054`
- `0x18003c418`
- `0x18005b784`
- `0x1800613b4`
- `0x180077664`
- `0x180078b9c`
- `0x18007a28c`
- `0x18007b914`
- `0x18008b38c`
- `0x18008b3bc`
- `0x18009ad18`
- `0x18009bcc8`
- `0x18009eb7c`
- `0x18009f0b0`
- `0x1800addf4`
- `0x1801def30`
- `0x1801dfc4c`
- `0x1801e3e28`
- `0x1801e3fc0`
- `0x1801e4040`
- `0x1801ea0d4`
- `0x1801ebbb8`
- `0x1801ebd68`
- `0x1801ef498`
- `0x1801efdc0`
- `0x1801f250c`
- `0x18029ea98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800618f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800618f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061581`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006181a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061a27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061b57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800620b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062126`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061581`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006181a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061a27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061b57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800620b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062126`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061596`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006165c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006182f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061b6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061d3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061f1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800620c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006213b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061596`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006165c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006182f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061b6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061d3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061f1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800620c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006213b`

## string_xrefs

- `0x180062190`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x1800621b0`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x180061439`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061565`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18006161d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800619fd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061a7d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061b2d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061cd3`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061e8f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800620fc`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180061923`: `Loaded cix file from cache: {}`
- `0x1800615c1`: `%ls.cix.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CDeploymentSession::GetOffsetInOuterContainer(
        CDeploymentSession *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  __int64 result; // rax
  const unsigned __int8 *v12; // r13
  __int64 v13; // rax
  __int64 v14; // r12
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  __int128 *v19; // rdx
  int v20; // eax
  __int64 v21; // rbx
  HANDLE v22; // rax
  unsigned int v23; // ebx
  const char *v24; // r9
  _QWORD *v25; // rax
  __int64 v26; // rcx
  char v27; // bl
  __int64 v28; // rdx
  __int64 v29; // r8
  CiXParserUtil::AutoCiXDocument *v30; // rax
  __int64 v31; // rbx
  unsigned int v32; // ebx
  const char *v33; // r9
  _QWORD *Path; // rax
  __int64 sstring; // rax
  __int64 v36; // rbx
  HANDLE v37; // rax
  __int64 *v38; // rdi
  void *v39; // rbx
  char *v40; // rdx
  unsigned __int64 v41; // r14
  _QWORD *v42; // rcx
  unsigned __int64 v43; // rsi
  unsigned __int64 v44; // r8
  int v45; // eax
  CiXParserUtil::AutoCiXDocument *v46; // rsi
  void *v47; // rbx
  CiXParserUtil::AutoCiXDocument *v48; // rbx
  __int64 v49; // rdx
  const WCHAR *v50; // r8
  int v51; // eax
  __int64 v52; // rbx
  HANDLE v53; // rax
  int v54; // eax
  __int64 v55; // rbx
  HANDLE v56; // rax
  size_t v57; // rax
  int CiXFileByName; // eax
  __int64 v59; // rbx
  HANDLE v60; // rax
  char v61; // si
  __int64 i; // rdi
  CiXParserUtil::AutoCiXDocument *v63; // rbx
  __int64 v64; // rdx
  __int64 v65; // rbx
  const char *v66; // rax
  int v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rbx
  HANDLE v70; // rax
  __int64 v71; // rdx
  int v72; // eax
  __int64 v73; // r12
  int v74; // ecx
  int v75; // r8d
  __int64 v76; // rbx
  HANDLE v77; // rax
  const char *v78; // r9
  void *v79; // r13
  void *v80; // r12
  CiXParserUtil::AutoCiXDocument *v81; // rbx
  __int64 v82; // rcx
  __int64 v83; // rbx
  HANDLE v84; // rax
  __int64 v85; // rbx
  HANDLE v86; // rax
  int v87; // [rsp+20h] [rbp-218h]
  char v88; // [rsp+40h] [rbp-1F8h]
  __int64 v89; // [rsp+48h] [rbp-1F0h] BYREF
  int v90; // [rsp+50h] [rbp-1E8h] BYREF
  CiXParserUtil::AutoCiXDocument *v91[3]; // [rsp+58h] [rbp-1E0h] BYREF
  wchar_t v92[4]; // [rsp+70h] [rbp-1C8h] BYREF
  __int64 v93; // [rsp+78h] [rbp-1C0h]
  __int64 v94; // [rsp+80h] [rbp-1B8h]
  const unsigned __int8 *v95; // [rsp+88h] [rbp-1B0h]
  __int128 v96; // [rsp+90h] [rbp-1A8h] BYREF
  const unsigned __int8 *v97; // [rsp+A0h] [rbp-198h]
  unsigned __int64 *v98; // [rsp+A8h] [rbp-190h]
  unsigned __int64 *v99; // [rsp+B0h] [rbp-188h]
  CDeploymentSession *v100; // [rsp+B8h] [rbp-180h]
  __int64 v101; // [rsp+C0h] [rbp-178h]
  _OWORD v102[2]; // [rsp+C8h] [rbp-170h] BYREF
  __int128 v103; // [rsp+E8h] [rbp-150h] BYREF
  void *Buf2; // [rsp+F8h] [rbp-140h]
  unsigned __int64 v105; // [rsp+100h] [rbp-138h]
  size_t Size[2]; // [rsp+110h] [rbp-128h] BYREF
  void *Buf1; // [rsp+120h] [rbp-118h]
  const char *v108; // [rsp+130h] [rbp-108h] BYREF
  const char *v109; // [rsp+138h] [rbp-100h]
  __int64 v110; // [rsp+140h] [rbp-F8h]
  const char *v111; // [rsp+148h] [rbp-F0h]
  _QWORD v112[2]; // [rsp+150h] [rbp-E8h] BYREF
  unsigned __int64 v113; // [rsp+160h] [rbp-D8h]
  unsigned __int64 v114; // [rsp+168h] [rbp-D0h]
  unsigned __int8 *v115[2]; // [rsp+170h] [rbp-C8h] BYREF
  __int64 v116; // [rsp+180h] [rbp-B8h]
  unsigned __int64 v117; // [rsp+188h] [rbp-B0h]
  int v118[24]; // [rsp+190h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v101 = -2;
  v100 = this;
  v98 = a6;
  v99 = a7;
  if ( !a6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D2,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)0x80004003LL,
      v87);
    return 2147500035LL;
  }
  if ( a7 )
    *a7 = 0;
  try
  {
    *(_OWORD *)v115 = 0;
    v116 = 0;
    v117 = 15;
    LOBYTE(v115[0]) = 0;
    v12 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    if ( a5 )
    {
      v13 = to_string(&v108);
      std::string::operator=(v115, v13);
      std::string::~string(&v108);
      v12 = (const unsigned __int8 *)v115;
      if ( v117 > 0xF )
        v12 = v115[0];
      v95 = v12;
      v14 = v116;
      *(_QWORD *)&v96 = v116;
      *((_QWORD *)&v96 + 1) = v116 + 1;
      v97 = v12;
    }
    else
    {
      v14 = v96;
    }
    v94 = v14;
    v89 = 0;
    if ( a3 )
    {
      _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v89);
      v15 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), (__int64)a3, 0);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E3,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v15,
          v87);
        v17 = v89;
        if ( v89 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v17 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        goto LABEL_104;
      }
    }
    else
    {
      wil::str_printf<std::wstring>(&v103, L"%ls.cix.xml", a2);
      _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v89);
      v19 = &v103;
      if ( v105 > 7 )
        v19 = (__int128 *)v103;
      v20 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), (__int64)v19, 0);
      v16 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E8,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v20,
          v87);
        std::wstring::~wstring(&v103);
        v21 = v89;
        if ( v89 )
        {
          v22 = GetProcessHeap();
          HeapFree(v22, 0, (LPVOID)(v21 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        goto LABEL_104;
      }
      if ( v89 )
        v23 = *(_DWORD *)(v89 - 4);
      else
        v23 = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( *(_WORD *)(v89 + 2LL * v23) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
          v24);
      *(_QWORD *)v92 = v89;
      v93 = v23;
      v25 = (_QWORD *)to_wstring(&v108, v92);
      v26 = v25[2];
      if ( v25[3] > 7u )
        v25 = (_QWORD *)*v25;
      *(_QWORD *)v92 = v25;
      v93 = v26;
      v27 = FileExists(v92);
      std::wstring::~wstring(&v108);
      if ( !v27 )
      {
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)Buf2) < 4 )
          std::_Xlen_string();
        v87 = 4;
        std::wstring::wstring(&v108, v28, v29, L"cix\\");
        v30 = (CiXParserUtil::AutoCiXDocument *)&v108;
        if ( (unsigned __int64)v111 > 7 )
          v30 = (CiXParserUtil::AutoCiXDocument *)v108;
        v91[0] = v30;
        v91[1] = (CiXParserUtil::AutoCiXDocument *)v110;
        v31 = *((_QWORD *)this + 62);
        if ( v31 )
          v32 = *(_DWORD *)(v31 - 4);
        else
          v32 = 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        Size[0] = *((_QWORD *)this + 62);
        Size[1] = v32;
        if ( *(_WORD *)(Size[0] + 2LL * v32) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xB6,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
            v33);
        Path = CreatePath(v102, (__int64)Size, v91);
        if ( Path[3] > 7u )
          Path = (_QWORD *)*Path;
        sstring = make_sstring(v92, (unsigned __int64)Path);
        __4__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
          &v89,
          sstring);
        v36 = *(_QWORD *)v92;
        if ( *(_QWORD *)v92 )
        {
          v37 = GetProcessHeap();
          HeapFree(v37, 0, (LPVOID)(v36 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        std::wstring::~wstring(v102);
        std::wstring::~wstring(&v108);
      }
      std::wstring::~wstring(&v103);
    }
    to_wstring(v112, v89);
    v38 = (__int64 *)((char *)this + 752);
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      (__int64)this + 752,
      &v103,
      v112);
    v39 = Buf2;
    if ( *((_BYTE *)Buf2 + 25) )
      goto LABEL_55;
    if ( *((_QWORD *)Buf2 + 7) <= 7u )
      v40 = (char *)Buf2 + 32;
    else
      v40 = (char *)*((_QWORD *)Buf2 + 4);
    v41 = *((_QWORD *)Buf2 + 6);
    v42 = v112;
    if ( v114 > 7 )
      v42 = (_QWORD *)v112[0];
    v43 = v113;
    v44 = v113;
    if ( v113 > v41 )
      v44 = *((_QWORD *)Buf2 + 6);
    v45 = _o__wcsnicmp(v42, v40, v44);
    if ( v45 )
    {
      if ( v45 < 0 )
        goto LABEL_55;
    }
    else if ( v43 < v41 )
    {
      goto LABEL_55;
    }
    if ( v39 != (void *)*v38 )
    {
      v46 = (CiXParserUtil::AutoCiXDocument *)*((_QWORD *)v39 + 8);
      LogAdapter::TraceAtLevel<std::wstring>(1, "Loaded cix file from cache: {}", v112);
      goto LABEL_67;
    }
LABEL_55:
    v47 = operator new(0x50u);
    *(_QWORD *)v92 = v47;
    memset_0(v47, 0, 0x50u);
    v91[0] = (CiXParserUtil::AutoCiXDocument *)CiXParserUtil::AutoCiXDocument::AutoCiXDocument((CiXParserUtil::AutoCiXDocument *)v47);
    v46 = *(CiXParserUtil::AutoCiXDocument **)(*(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<CiXParserUtil::AutoCiXDocument>,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::unique_ptr<CiXParserUtil::AutoCiXDocument>>>,0>>::emplace<std::wstring &,std::unique_ptr<CiXParserUtil::AutoCiXDocument>>(
                                                            v38,
                                                            (__int64)&v103,
                                                            v112,
                                                            (__int64 *)v91)
                                             + 64LL);
    v48 = v91[0];
    if ( v91[0] )
    {
      CiXParserUtil::AutoCiXDocument::~AutoCiXDocument(v91[0]);
      operator delete(v48, (const struct std::nothrow_t *)0x50);
    }
    LogAdapter::TraceAtLevel<std::wstring>(1, "Loading and parsing cix file: {}", v112);
    v50 = (const WCHAR *)v112;
    if ( v114 > 7 )
      v50 = (const WCHAR *)v112[0];
    v51 = XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromFile(
            (__int64)v46,
            v49,
            v50,
            0);
    v16 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x402,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v51,
        v87);
      std::wstring::~wstring(v112);
      v52 = v89;
      if ( v89 )
      {
        v53 = GetProcessHeap();
        HeapFree(v53, 0, (LPVOID)(v52 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      goto LABEL_104;
    }
    v54 = CiXParserUtil::AutoCiXDocument::Preload(v46);
    v16 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x403,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v54,
        v87);
      std::wstring::~wstring(v112);
      v55 = v89;
      if ( v89 )
      {
        v56 = GetProcessHeap();
        HeapFree(v56, 0, (LPVOID)(v55 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      goto LABEL_104;
    }
LABEL_67:
    v91[0] = 0;
    v57 = -1;
    do
      ++v57;
    while ( a4[v57] );
    Size[0] = (size_t)a4;
    Size[1] = v57;
    CiXFileByName = CiXParserUtil::AutoCiXDocument::GetCiXFileByName(v46, Size, v91);
    v16 = CiXFileByName;
    if ( CiXFileByName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x407,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)CiXFileByName,
        v87);
      std::wstring::~wstring(v112);
      v59 = v89;
      if ( v89 )
      {
        v60 = GetProcessHeap();
        HeapFree(v60, 0, (LPVOID)(v59 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      goto LABEL_104;
    }
    if ( v91[0] )
    {
      v61 = 0;
      v88 = 0;
      for ( i = *((_QWORD *)v91[0] + 9); i; i = *(_QWORD *)(i + 24) )
      {
        if ( v61 )
          goto LABEL_125;
        v63 = *(CiXParserUtil::AutoCiXDocument **)i;
LABEL_78:
        v91[0] = v63;
        if ( v63 )
        {
          v64 = 0;
          if ( !v61 )
          {
            v65 = *((_QWORD *)v63 + 7);
            while ( 1 )
            {
              if ( !v65 )
              {
                v81 = v91[0];
                v61 = v88;
LABEL_122:
                v63 = (CiXParserUtil::AutoCiXDocument *)*((_QWORD *)v81 + 9);
                v12 = v95;
                v14 = v94;
                goto LABEL_78;
              }
              *(_OWORD *)Size = 0;
              Buf1 = 0;
              if ( v65 == -8 )
                break;
              if ( !(unsigned __int8)RtlIsLUtf8StringValid(v65 + 8, v64) )
              {
                v108 = "onecore\\base\\lstring\\lutf8_string.cpp";
                v109 = "RtlParseHexadecimalLUtf8String";
                v110 = 771;
                v66 = "::RtlIsLUtf8StringValid(InputString)";
LABEL_84:
                v111 = v66;
                RtlReportErrorOrigination(&v108, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
                v67 = -1073741811;
LABEL_88:
                v16 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x41C,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        (const char *)(unsigned int)v67,
                        v87);
                if ( Buf1 )
                {
                  anonymous_namespace_::OurRtlFreeStringRoutine(Buf1);
                  *(_OWORD *)Size = 0;
                  Buf1 = 0;
                }
                std::wstring::~wstring(v112);
                v69 = v89;
                if ( v89 )
                {
                  v70 = GetProcessHeap();
                  HeapFree(v70, 0, (LPVOID)(v69 - 4));
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                }
                goto LABEL_104;
              }
              v67 = RtlParseHexadecimalEncodedLBlob(1, v68, RtlDecodeUtf8, Size);
              if ( v67 < 0 )
                goto LABEL_88;
              v103 = 0u;
              Buf2 = 0;
              if ( !(unsigned __int8)RtlIsLUtf8StringValid(&v96, 0) )
              {
                v108 = "onecore\\base\\lstring\\lblob.cpp";
                v109 = "RtlDecodeBase64LUtf8StringToLBlob";
                v110 = 1540;
                v111 = "::RtlIsLUtf8StringValid(SourceString)";
                RtlReportErrorOrigination(&v108, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
                v72 = -1073741811;
LABEL_98:
                v16 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x426,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        (const char *)(unsigned int)v72,
                        v87);
                if ( Buf2 )
                {
                  anonymous_namespace_::OurRtlFreeStringRoutine(Buf2);
                  v103 = 0;
                  Buf2 = 0;
                }
                if ( Buf1 )
                {
                  anonymous_namespace_::OurRtlFreeStringRoutine(Buf1);
                  *(_OWORD *)Size = 0;
                  Buf1 = 0;
                }
                std::wstring::~wstring(v112);
                v76 = v89;
                if ( v89 )
                {
                  v77 = GetProcessHeap();
                  HeapFree(v77, 0, (LPVOID)(v76 - 4));
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                }
LABEL_104:
                std::string::~string(v115);
                return v16;
              }
              *(_QWORD *)v92 = v71;
              v72 = *(_DWORD *)BUCL::Implementation::Multiply<BUCL::Rtl::CCallDisposition,unsigned __int64>(
                                 &v90,
                                 v14,
                                 6,
                                 v92);
              if ( v72 < 0 )
                goto LABEL_98;
              v73 = *(_QWORD *)v92 >> 3;
              memset_0(v118, 0, 0x58u);
              v72 = RtlInitializeSmartLBlobWritingContext(v74, v73, v75, (unsigned int)&v103, v87, (__int64)v118);
              if ( v72 < 0 )
                goto LABEL_98;
              v72 = RtlpDecodeBase64Chunklets(
                      0,
                      (struct _RTL_UCSCHAR_DECODER_RETURN_VALUE (__high *)(const unsigned __int8 *, const unsigned __int8 *))RtlDecodeUtf8,
                      v12,
                      &v12[v94],
                      (struct _RTL_SMART_LBLOB_WRITING_CONTEXT *)v118);
              if ( v72 < 0 )
                goto LABEL_98;
              v79 = Buf2;
              v80 = Buf1;
              if ( Size[0] == (_QWORD)v103 && !memcmp_0(Buf1, Buf2, Size[0]) )
              {
                v61 = 1;
                v88 = 1;
                v81 = v91[0];
                *v98 = *((_QWORD *)v91[0] + 4);
                if ( v99 )
                  *v99 = *((_QWORD *)v81 + 5);
                if ( v79 )
                {
                  anonymous_namespace_::OurRtlFreeStringRoutine(v79);
                  v103 = 0;
                  Buf2 = 0;
                  v80 = Buf1;
                }
                if ( v80 )
                  anonymous_namespace_::OurRtlFreeStringRoutine(v80);
                goto LABEL_122;
              }
              v82 = *((_QWORD *)v100 + 75);
              if ( v82 )
              {
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v82,
                  2,
                  L"The hash returned by the CIX does not match the Actionlist hash");
                v80 = Buf1;
                v79 = Buf2;
              }
              if ( v79 )
              {
                anonymous_namespace_::OurRtlFreeStringRoutine(v79);
                v103 = 0;
                Buf2 = 0;
                v80 = Buf1;
              }
              if ( v80 )
                anonymous_namespace_::OurRtlFreeStringRoutine(v80);
              v65 = *(_QWORD *)(v65 + 48);
              v12 = v95;
              v14 = v94;
            }
            v108 = "onecore\\base\\lstring\\lutf8_string.cpp";
            v109 = "RtlParseHexadecimalLUtf8String";
            v110 = 770;
            v66 = "Not-null check failed: InputString";
            goto LABEL_84;
          }
        }
      }
      if ( v61 )
      {
LABEL_125:
        std::wstring::~wstring(v112);
        v83 = v89;
        if ( v89 )
        {
          v84 = GetProcessHeap();
          HeapFree(v84, 0, (LPVOID)(v83 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        std::string::~string(v115);
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)0x80070057LL,
      v87);
    std::wstring::~wstring(v112);
    v85 = v89;
    if ( v89 )
    {
      v86 = GetProcessHeap();
      HeapFree(v86, 0, (LPVOID)(v85 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    std::string::~string(v115);
    result = 2147942487LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x440,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v78);
  }
  return result;
}

```

## disassembly

```asm
0x1800613b4  push    rbx
0x1800613b6  push    rsi
0x1800613b7  push    rdi
0x1800613b8  push    r12
0x1800613ba  push    r13
0x1800613bc  push    r14
0x1800613be  push    r15
0x1800613c0  sub     rsp, 200h
0x1800613c7  mov     [rsp+238h+var_178], 0FFFFFFFFFFFFFFFEh
0x1800613d3  mov     rax, cs:__security_cookie
0x1800613da  xor     rax, rsp
0x1800613dd  mov     [rsp+238h+var_48], rax
0x1800613e5  mov     r15, r9
0x1800613e8  mov     rbx, r8
0x1800613eb  mov     rdi, rdx
0x1800613ee  mov     rsi, rcx
0x1800613f1  mov     [rsp+238h+var_180], rcx
0x1800613f9  mov     rdx, [rsp+238h+arg_20]
0x180061401  mov     rcx, [rsp+238h+arg_28]
0x180061409  mov     [rsp+238h+var_190], rcx
0x180061411  mov     rax, [rsp+238h+arg_30]
0x180061419  mov     [rsp+238h+var_188], rax
0x180061421  xor     r14d, r14d
0x180061424  test    rcx, rcx
0x180061427  jnz     short loc_180061451
0x180061429  mov     rcx, [rsp+238h]; this
0x180061431  mov     ebx, 80004003h
0x180061436  mov     r9d, ebx; char *
0x180061439  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180061440  mov     edx, 3D2h; void *
0x180061445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006144a  mov     eax, ebx
0x18006144c  jmp     loc_180062164
0x180061451  test    rax, rax
0x180061454  jz      short loc_180061459
0x180061456  mov     [rax], r14
0x180061459  xorps   xmm0, xmm0
0x18006145c  movups  xmmword ptr [rsp+238h+var_C8], xmm0
0x180061464  mov     [rsp+238h+var_B8], r14
0x18006146c  mov     [rsp+238h+var_B0], 0Fh
0x180061478  mov     byte ptr [rsp+238h+var_C8], r14b
0x180061480  xor     r13d, r13d
0x180061483  mov     [rsp+238h+var_1B0], r13
0x18006148b  movups  [rsp+238h+var_1A8], xmm0
0x180061493  mov     [rsp+238h+var_198], r13
0x18006149b  test    rdx, rdx
0x18006149e  jz      short loc_180061513
0x1800614a0  lea     rcx, [rsp+238h+var_108]
0x1800614a8  call    ?to_string@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEB_W@Z; to_string(wchar_t const * const)
0x1800614ad  mov     rdx, rax
0x1800614b0  lea     rcx, [rsp+238h+var_C8]
0x1800614b8  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800614bd  lea     rcx, [rsp+238h+var_108]; void *
0x1800614c5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800614ca  lea     r13, [rsp+238h+var_C8]
0x1800614d2  cmp     [rsp+238h+var_B0], 0Fh
0x1800614db  cmova   r13, [rsp+238h+var_C8]
0x1800614e4  mov     [rsp+238h+var_1B0], r13
0x1800614ec  mov     r12, [rsp+238h+var_B8]
0x1800614f4  mov     qword ptr [rsp+238h+var_1A8], r12
0x1800614fc  lea     rax, [r12+1]
0x180061501  mov     qword ptr [rsp+238h+var_1A8+8], rax
0x180061509  mov     [rsp+238h+var_198], r13
0x180061511  jmp     short loc_18006151B
0x180061513  mov     r12, qword ptr [rsp+238h+var_1A8]
0x18006151b  mov     [rsp+238h+var_1B8], r12
0x180061523  mov     [rsp+238h+var_1F0], r14
0x180061528  test    rbx, rbx
0x18006152b  jz      loc_1800615BE
0x180061531  lea     rcx, [rsp+238h+var_1F0]
0x180061536  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18006153b  mov     r9, rax
0x18006153e  xor     r8d, r8d
0x180061541  mov     rdx, rbx
0x180061544  mov     rcx, [rsi+1F0h]
0x18006154b  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180061550  mov     edi, eax
0x180061552  test    eax, eax
0x180061554  jns     loc_18006186C
0x18006155a  mov     rcx, [rsp+238h]; this
0x180061562  mov     r9d, eax; char *
0x180061565  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18006156c  mov     edx, 3E3h; void *
0x180061571  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061576  nop
0x180061577  mov     rbx, [rsp+238h+var_1F0]
0x18006157c  test    rbx, rbx
0x18006157f  jz      short loc_1800615AA
0x180061581  call    cs:__imp_GetProcessHeap
0x180061588  nop     dword ptr [rax+rax+00h]
0x18006158d  mov     rcx, rax; hHeap
0x180061590  lea     r8, [rbx-4]; lpMem
0x180061594  xor     edx, edx; dwFlags
0x180061596  call    cs:__imp_HeapFree
0x18006159d  nop     dword ptr [rax+rax+00h]
0x1800615a2  xor     ecx, ecx
0x1800615a4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800615a9  nop
0x1800615aa  lea     rcx, [rsp+238h+var_C8]; void *
0x1800615b2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800615b7  mov     eax, edi
0x1800615b9  jmp     loc_180062164
0x1800615be  mov     r8, rdi
0x1800615c1  lea     rdx, aLsCixXml; "%ls.cix.xml"
0x1800615c8  lea     rcx, [rsp+238h+var_150]
0x1800615d0  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800615d5  nop
0x1800615d6  lea     rcx, [rsp+238h+var_1F0]
0x1800615db  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x1800615e0  lea     rdx, [rsp+238h+var_150]
0x1800615e8  cmp     [rsp+238h+var_138], 7
0x1800615f1  cmova   rdx, qword ptr [rsp+238h+var_150]
0x1800615fa  mov     r9, rax
0x1800615fd  xor     r8d, r8d
0x180061600  mov     rcx, [rsi+1F0h]
0x180061607  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18006160c  mov     edi, eax
0x18006160e  test    eax, eax
0x180061610  jns     short loc_180061684
0x180061612  mov     rcx, [rsp+238h]; this
0x18006161a  mov     r9d, eax; char *
0x18006161d  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x180061624  mov     edx, 3E8h; void *
0x180061629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006162e  nop
0x18006162f  lea     rcx, [rsp+238h+var_150]; void *
0x180061637  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006163c  nop
0x18006163d  mov     rbx, [rsp+238h+var_1F0]
0x180061642  test    rbx, rbx
0x180061645  jz      short loc_180061670
0x180061647  call    cs:__imp_GetProcessHeap
0x18006164e  nop     dword ptr [rax+rax+00h]
0x180061653  mov     rcx, rax; hHeap
0x180061656  lea     r8, [rbx-4]; lpMem
0x18006165a  xor     edx, edx; dwFlags
0x18006165c  call    cs:__imp_HeapFree
0x180061663  nop     dword ptr [rax+rax+00h]
0x180061668  xor     ecx, ecx
0x18006166a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006166f  nop
0x180061670  lea     rcx, [rsp+238h+var_C8]; void *
0x180061678  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006167d  mov     eax, edi
0x18006167f  jmp     loc_180062164
0x180061684  mov     rax, [rsp+238h+var_1F0]
0x180061689  test    rax, rax
0x18006168c  jz      short loc_180061693
0x18006168e  mov     ebx, [rax-4]
0x180061691  jmp     short loc_180061696
0x180061693  mov     ebx, r14d
0x180061696  xor     ecx, ecx
0x180061698  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006169d  mov     rax, [rsp+238h+var_1F0]
0x1800616a2  mov     ecx, ebx
0x1800616a4  cmp     [rax+rcx*2], r14w
0x1800616a9  jnz     loc_180062188
0x1800616af  mov     qword ptr [rsp+238h+var_1C8], rax
0x1800616b4  mov     [rsp+238h+var_1C0], rcx
0x1800616b9  lea     rdx, [rsp+238h+var_1C8]
0x1800616be  lea     rcx, [rsp+238h+var_108]
0x1800616c6  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z; to_wstring(std::wstring_view)
0x1800616cb  nop
0x1800616cc  mov     rcx, [rax+10h]
0x1800616d0  cmp     qword ptr [rax+18h], 7
0x1800616d5  jbe     short loc_1800616DA
0x1800616d7  mov     rax, [rax]
0x1800616da  mov     qword ptr [rsp+238h+var_1C8], rax
0x1800616df  mov     [rsp+238h+var_1C0], rcx
0x1800616e4  lea     rcx, [rsp+238h+var_1C8]
0x1800616e9  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x1800616ee  mov     bl, al
0x1800616f0  lea     rcx, [rsp+238h+var_108]; void *
0x1800616f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800616fd  test    bl, bl
0x1800616ff  jnz     loc_18006185F
0x180061705  mov     rcx, [rsp+238h+Buf2]
0x18006170d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180061717  sub     rax, rcx
0x18006171a  cmp     rax, 4
0x18006171e  jb      loc_1800621A2
0x180061724  lea     rax, [rsp+238h+var_150]
0x18006172c  cmp     [rsp+238h+var_138], 7
0x180061735  cmova   rax, qword ptr [rsp+238h+var_150]
0x18006173e  mov     [rsp+238h+var_208], rcx
0x180061743  mov     [rsp+238h+var_210], rax
0x180061748  mov     [rsp+238h+var_218], 4; int
0x180061751  lea     r9, aCix; "cix\\"
0x180061758  lea     rcx, [rsp+238h+var_108]
0x180061760  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180061765  nop
0x180061766  lea     rax, [rsp+238h+var_108]
0x18006176e  cmp     [rsp+238h+var_F0], 7
0x180061777  cmova   rax, [rsp+238h+var_108]
0x180061780  mov     [rsp+238h+var_1E0], rax
0x180061785  mov     rax, [rsp+238h+var_F8]
0x18006178d  mov     [rsp+238h+var_1D8], rax
0x180061792  mov     rbx, [rsi+1F0h]
0x180061799  test    rbx, rbx
0x18006179c  jnz     short loc_1800617A3
0x18006179e  mov     ebx, r14d
0x1800617a1  jmp     short loc_1800617A6
0x1800617a3  mov     ebx, [rbx-4]
0x1800617a6  xor     ecx, ecx
0x1800617a8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800617ad  mov     rcx, [rsi+1F0h]
0x1800617b4  mov     eax, ebx
0x1800617b6  mov     [rsp+238h+Size], rcx
0x1800617be  mov     [rsp+238h+Size+8], rax
0x1800617c6  cmp     [rcx+rax*2], r14w
0x1800617cb  jnz     loc_1800621A8
0x1800617d1  lea     r8, [rsp+238h+var_1E0]
0x1800617d6  lea     rdx, [rsp+238h+Size]
0x1800617de  lea     rcx, [rsp+238h+var_170]
0x1800617e6  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x1800617eb  nop
0x1800617ec  cmp     qword ptr [rax+18h], 7
0x1800617f1  jbe     short loc_1800617F6
0x1800617f3  mov     rax, [rax]
0x1800617f6  mov     rdx, rax; unsigned __int64
0x1800617f9  lea     rcx, [rsp+238h+var_1C8]; wchar_t *
0x1800617fe  call    ?make_sstring@@YA@QEB_W_K@Z; make_sstring(wchar_t const * const,unsigned __int64)
0x180061803  mov     rdx, rax
0x180061806  lea     rcx, [rsp+238h+var_1F0]
0x18006180b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180061810  mov     rbx, qword ptr [rsp+238h+var_1C8]
0x180061815  test    rbx, rbx
0x180061818  jz      short loc_180061843
0x18006181a  call    cs:__imp_GetProcessHeap
0x180061821  nop     dword ptr [rax+rax+00h]
0x180061826  mov     rcx, rax; hHeap
0x180061829  lea     r8, [rbx-4]; lpMem
0x18006182d  xor     edx, edx; dwFlags
0x18006182f  call    cs:__imp_HeapFree
0x180061836  nop     dword ptr [rax+rax+00h]
0x18006183b  xor     ecx, ecx
0x18006183d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180061842  nop
0x180061843  lea     rcx, [rsp+238h+var_170]; void *
0x18006184b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061850  nop
0x180061851  lea     rcx, [rsp+238h+var_108]; void *
0x180061859  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006185e  nop
0x18006185f  lea     rcx, [rsp+238h+var_150]; void *
0x180061867  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006186c  mov     rdx, [rsp+238h+var_1F0]
0x180061871  lea     rcx, [rsp+238h+var_E8]
0x180061879  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z; to_wstring(wchar_t const * const)
0x18006187e  nop
0x18006187f  lea     rdi, [rsi+2F0h]
0x180061886  lea     r8, [rsp+238h+var_E8]
0x18006188e  lea     rdx, [rsp+238h+var_150]
0x180061896  mov     rcx, rdi
0x180061899  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18006189e  mov     rbx, [rsp+238h+Buf2]
0x1800618a6  cmp     [rbx+19h], r14b
0x1800618aa  jnz     loc_18006193C
0x1800618b0  cmp     qword ptr [rbx+38h], 7
0x1800618b5  jbe     short loc_1800618BD
0x1800618b7  mov     rdx, [rbx+20h]
0x1800618bb  jmp     short loc_1800618C1
0x1800618bd  lea     rdx, [rbx+20h]
0x1800618c1  mov     r14, [rbx+30h]
0x1800618c5  lea     rcx, [rsp+238h+var_E8]
0x1800618cd  cmp     [rsp+238h+var_D0], 7
0x1800618d6  cmova   rcx, [rsp+238h+var_E8]
0x1800618df  mov     rsi, [rsp+238h+var_D8]
0x1800618e7  mov     r8, rsi
0x1800618ea  cmp     rsi, r14
0x1800618ed  cmova   r8, r14
0x1800618f1  call    cs:__imp__o__wcsnicmp
0x1800618f8  nop     dword ptr [rax+rax+00h]
0x1800618fd  test    eax, eax
0x1800618ff  jz      short loc_18006190A
0x180061901  xor     r14d, r14d
0x180061904  test    eax, eax
0x180061906  js      short loc_18006193C
0x180061908  jmp     short loc_180061912
0x18006190a  cmp     rsi, r14
0x18006190d  jb      short loc_180061939
0x18006190f  xor     r14d, r14d
0x180061912  cmp     rbx, [rdi]
0x180061915  jz      short loc_18006193C
0x180061917  mov     rsi, [rbx+40h]
0x18006191b  lea     r8, [rsp+238h+var_E8]
0x180061923  lea     rdx, aLoadedCixFileF; "Loaded cix file from cache: {}"
0x18006192a  mov     ecx, 1
0x18006192f  call    ??$TraceAtLevel@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevel<std::wstring>(LogAdapter::LogLevel,char const * const,std::wstring const &)
0x180061934  jmp     loc_180061AE4
0x180061939  xor     r14d, r14d
0x18006193c  mov     esi, 50h ; 'P'
0x180061941  mov     ecx, esi; Size
0x180061943  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061948  mov     rbx, rax
0x18006194b  mov     qword ptr [rsp+238h+var_1C8], rax
0x180061950  mov     r8d, esi; Size
0x180061953  xor     edx, edx; Val
0x180061955  mov     rcx, rax; void *
0x180061958  call    memset_0
  ... truncated ...
```
