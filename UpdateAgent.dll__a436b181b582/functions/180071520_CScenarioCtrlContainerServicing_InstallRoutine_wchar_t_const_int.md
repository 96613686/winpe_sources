# CScenarioCtrlContainerServicing::InstallRoutine(wchar_t const *,int *)

- ea: `0x180071520`
- end: `0x180071f7b`
- name: `?InstallRoutine@CScenarioCtrlContainerServicing@@UEAAJPEB_WPEAH@Z`
- size: `2651`
- prototype: `__int64 __fastcall(CScenarioCtrlContainerServicing *__hidden this, const wchar_t *, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18000ce14`
- `0x180012460`
- `0x18001270c`
- `0x180023b20`
- `0x180060534`
- `0x180068c88`
- `0x180071520`
- `0x180077664`
- `0x18008b38c`
- `0x18009f0b0`
- `0x1801e0728`
- `0x18027a338`
- `0x18027a59c`
- `0x18027b984`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800716e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800717ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071d07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071edb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800716e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800717ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071d07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071edb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800716fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071957`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071d1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071e39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071ef0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800716fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071957`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071d1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071e39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071ef0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800718d7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800718d7`

## string_xrefs

- `0x1800716cd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800717d0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800718f8`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x1800719eb`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x180071cbd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x180071dda`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\ScenarioCtrlContainer.h`
- `0x180071567`: `CScenarioCtrlContainerServicing::InstallRoutine Enter.`
- `0x180071b77`: `Failed to service container base images`
- `0x180071c6d`: `Failed to recreate container base images`
- `0x180071d95`: `Recreated layer {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CScenarioCtrlContainerServicing::InstallRoutine(
        CScenarioCtrlContainerServicing *this,
        const wchar_t *a2,
        int *a3)
{
  int v4; // edi
  const char *v6; // r9
  __int64 result; // rax
  int LayerDetails; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rbx
  HANDLE ProcessHeap; // rax
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rbx
  HANDLE v19; // rax
  const struct std::nothrow_t *v20; // rdx
  void *v21; // rcx
  __int64 v22; // rax
  _OWORD *v23; // rsi
  HRESULT Guid; // eax
  __int64 v25; // r8
  unsigned int v26; // edi
  __int64 v27; // rbx
  HANDLE v28; // rax
  const struct std::nothrow_t *v29; // rdx
  void *v30; // rcx
  int ContainerProgressWNFSubscription; // eax
  unsigned int v32; // edi
  __int64 v33; // rbx
  HANDLE v34; // rax
  const struct std::nothrow_t *v35; // rdx
  void *v36; // rcx
  wchar_t *v37; // rax
  wchar_t *v38; // r8
  __int128 *v39; // rdx
  wchar_t *v40; // rcx
  int v41; // eax
  wchar_t *v42; // rax
  const WCHAR *v43; // rcx
  int ContainerBaseImages; // eax
  __int64 v45; // rdx
  unsigned int v46; // edi
  __int64 v47; // rdx
  __int64 v48; // rbx
  HANDLE v49; // rax
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  unsigned int v54; // edi
  __int64 v55; // rbx
  HANDLE v56; // rax
  const struct std::nothrow_t *v57; // rdx
  void *v58; // rcx
  __int64 v59; // rbx
  HANDLE v60; // rax
  const struct std::nothrow_t *v61; // rdx
  void *v62; // rcx
  int *v63; // [rsp+20h] [rbp-188h]
  __int64 *v64; // [rsp+20h] [rbp-188h]
  int v65; // [rsp+50h] [rbp-158h] BYREF
  __int64 v66; // [rsp+58h] [rbp-150h] BYREF
  __int64 v67[2]; // [rsp+60h] [rbp-148h] BYREF
  __int64 v68[5]; // [rsp+70h] [rbp-138h] BYREF
  char v69; // [rsp+98h] [rbp-110h]
  int v70[2]; // [rsp+A0h] [rbp-108h] BYREF
  void (*v71)(void); // [rsp+A8h] [rbp-100h] BYREF
  void *v72; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-F0h]
  int v74; // [rsp+C0h] [rbp-E8h] BYREF
  __int128 v75; // [rsp+C8h] [rbp-E0h] BYREF
  __m128i v76; // [rsp+D8h] [rbp-D0h]
  __int128 v77; // [rsp+E8h] [rbp-C0h] BYREF
  __m128i v78; // [rsp+F8h] [rbp-B0h]
  wchar_t *v79[2]; // [rsp+108h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+118h] [rbp-90h]
  __int64 v81[2]; // [rsp+128h] [rbp-80h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+138h] [rbp-70h] BYREF
  unsigned __int64 v83; // [rsp+150h] [rbp-58h]
  __int64 v84[2]; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v68[2] = -2;
  v4 = (int)a2;
  *(_OWORD *)v81 = 0;
  LOBYTE(v65) = 0;
  try
  {
    LogAdapter::TraceInfo<>("CScenarioCtrlContainerServicing::InstallRoutine Enter.");
    if ( *((_BYTE *)this + 88) )
    {
      *a3 = 0;
      LogAdapter::TraceInfo<>("Postponing container servicing in offline scenario.");
      return 0;
    }
    v72 = 0;
    v73 = 0;
    *(_OWORD *)v79 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v79[0]) = 0;
    v77 = 0;
    v78 = si128;
    LOWORD(v77) = 0;
    v75 = 0;
    v76 = si128;
    LOWORD(v75) = 0;
    v66 = 0;
    LayerDetails = CScenarioCtrlContainerServicing::GetLayerDetails(
                     (_DWORD)this,
                     v4,
                     0,
                     (unsigned int)&v66,
                     (__int64)&v65,
                     (__int64)this + 128,
                     (__int64)v79,
                     (__int64)&v77,
                     (__int64)&v75,
                     (__int64)&v72);
    v9 = LayerDetails;
    if ( LayerDetails < 0 )
    {
      v74 = LayerDetails;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get layers");
        *(_QWORD *)v70 = &v74;
        v63 = v70;
        LOBYTE(v10) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v10,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)v9,
        (int)v63);
      v11 = v66;
      if ( v66 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v11 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(&v77);
      std::wstring::~wstring(v79);
      v14 = v72;
      if ( v72 )
      {
        v72 = 0;
        v73 = 0;
        operator delete(v14, v13);
      }
      return v9;
    }
    if ( !(_BYTE)v65 )
      goto LABEL_81;
    if ( *((_DWORD *)this + 30) )
    {
      LogAdapter::TraceInfo<>("Postponing container servicing because LCU staging has been postponed.");
      if ( *((_DWORD *)this + 31) )
      {
        *(_OWORD *)v81 = xmmword_1802C24B0;
        v15 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ((char *)this + 48);
        v16 = CDlpHelpersT<CEmptyType>::GuidToSString(v81, 0, v15);
        v17 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
            (const char *)(unsigned int)v16,
            (int)v63);
          v18 = v66;
          if ( v66 )
          {
            v19 = GetProcessHeap();
            HeapFree(v19, 0, (LPVOID)(v18 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          std::wstring::~wstring(&v75);
          std::wstring::~wstring(&v77);
          std::wstring::~wstring(v79);
          v21 = v72;
          if ( v72 )
          {
            v72 = 0;
            v73 = 0;
            operator delete(v21, v20);
          }
          return v17;
        }
      }
      goto LABEL_81;
    }
    *(_QWORD *)v70 = 0;
    v71 = 0;
    v68[3] = (__int64)&v71;
    v68[4] = (__int64)v70;
    v69 = 1;
    v67[0] = v66;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v66 + 2 * v22) );
    v67[1] = v22;
    GetDirectory(lpFileName, v67);
    v23 = (_OWORD *)((char *)this + 104);
    Guid = CoCreateGuid((GUID *)((char *)this + 104));
    v26 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)(unsigned int)Guid,
        (int)v63);
      std::wstring::~wstring(lpFileName);
      if ( v71 && *(_QWORD *)v70 )
        v71();
      v27 = v66;
      if ( v66 )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, (LPVOID)(v27 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(&v77);
      std::wstring::~wstring(v79);
      v30 = v72;
      if ( v72 )
      {
        v72 = 0;
        v73 = 0;
        operator delete(v30, v29);
      }
      return v26;
    }
    ContainerProgressWNFSubscription = GetContainerProgressWNFSubscription(v70, &v71, v25, this);
    v32 = ContainerProgressWNFSubscription;
    if ( ContainerProgressWNFSubscription < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)(unsigned int)ContainerProgressWNFSubscription,
        (int)v63);
      std::wstring::~wstring(lpFileName);
      if ( v71 && *(_QWORD *)v70 )
        v71();
      v33 = v66;
      if ( v66 )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, (LPVOID)(v33 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(&v77);
      std::wstring::~wstring(v79);
      v36 = v72;
      if ( v72 )
      {
        v72 = 0;
        v73 = 0;
        operator delete(v36, v35);
      }
      return v32;
    }
    if ( !*((_DWORD *)this + 31) )
    {
      v37 = (wchar_t *)v79;
      if ( si128.m128i_i64[1] > 7uLL )
        v37 = v79[0];
      v67[0] = 0;
      v67[1] = 0;
      v38 = (wchar_t *)&v75;
      if ( v76.m128i_i64[1] > 7uLL )
        v38 = (wchar_t *)v75;
      v39 = &v77;
      if ( v78.m128i_i64[1] > 7uLL )
        v39 = (__int128 *)v77;
      v40 = (wchar_t *)lpFileName;
      if ( v83 > 7 )
        v40 = (wchar_t *)lpFileName[0];
      *(_OWORD *)v84 = *v23;
      v41 = ServiceContainerBaseImages(
              v40,
              v39,
              v38,
              (__int64)&v72,
              (wchar_t **)v67,
              v37,
              (struct _GUID *)v84,
              (__int64)v81);
      if ( v41 >= 0 )
      {
LABEL_69:
        v52 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ((char *)this + 48);
        v53 = CDlpHelpersT<CEmptyType>::GuidToSString(v81, 0, v52);
        v54 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
            (const char *)(unsigned int)v53,
            (int)v64);
          std::wstring::~wstring(lpFileName);
          if ( v71 && *(_QWORD *)v70 )
            v71();
          v55 = v66;
          if ( v66 )
          {
            v56 = GetProcessHeap();
            HeapFree(v56, 0, (LPVOID)(v55 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          std::wstring::~wstring(&v75);
          std::wstring::~wstring(&v77);
          std::wstring::~wstring(v79);
          v58 = v72;
          if ( v72 )
          {
            v72 = 0;
            v73 = 0;
            operator delete(v58, v57);
          }
          return v54;
        }
        std::wstring::~wstring(lpFileName);
        if ( v71 && *(_QWORD *)v70 )
          ((void (__fastcall *)(_QWORD))v71)(*(_QWORD *)v70);
LABEL_81:
        *a3 = 0;
        v59 = v66;
        if ( v66 )
        {
          v60 = GetProcessHeap();
          HeapFree(v60, 0, (LPVOID)(v59 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        std::wstring::~wstring(&v75);
        std::wstring::~wstring(&v77);
        std::wstring::~wstring(v79);
        v62 = v72;
        if ( v72 )
        {
          v72 = 0;
          v73 = 0;
          operator delete(v62, v61);
        }
        return 0;
      }
      LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v41, "Failed to service container base images");
    }
    *(_OWORD *)v84 = 0;
    v42 = (wchar_t *)v79;
    if ( si128.m128i_i64[1] > 7uLL )
      v42 = v79[0];
    v68[0] = 0;
    v68[1] = 0;
    v43 = (const WCHAR *)lpFileName;
    if ( v83 > 7 )
      v43 = lpFileName[0];
    *(_OWORD *)v67 = *v23;
    ContainerBaseImages = ReCreateContainerBaseImages(v43, (__int64)v68, v42, (__int64)v67, (__int64)v81, (__int64)v84);
    v46 = ContainerBaseImages;
    if ( ContainerBaseImages < 0 )
    {
      v74 = ContainerBaseImages;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to recreate container base images");
        v67[0] = (__int64)&v74;
        v64 = v67;
        LOBYTE(v47) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v47,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)v46,
        (int)v64);
      std::wstring::~wstring(lpFileName);
      if ( v71 && *(_QWORD *)v70 )
        v71();
      v48 = v66;
      if ( v66 )
      {
        v49 = GetProcessHeap();
        HeapFree(v49, 0, (LPVOID)(v48 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(&v77);
      std::wstring::~wstring(v79);
      v51 = v72;
      if ( v72 )
      {
        v72 = 0;
        v73 = 0;
        operator delete(v51, v50);
      }
      return v46;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v64 = v84;
      LOBYTE(v45) = 1;
      LogAdapter::Logger::LogNumObjects<_GUID>(*(_QWORD *)&LogAdapter::g_Logger, v45, 1, "Recreated layer {}");
    }
    goto LABEL_69;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAD,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180071520  mov     r11, rsp
0x180071523  push    rbx
0x180071524  push    rsi
0x180071525  push    rdi
0x180071526  push    r14
0x180071528  push    r15
0x18007152a  sub     rsp, 180h
0x180071531  mov     qword ptr [r11-128h], 0FFFFFFFFFFFFFFFEh
0x18007153c  mov     rax, cs:__security_cookie
0x180071543  xor     rax, rsp
0x180071546  mov     [rsp+1A8h+var_38], rax
0x18007154e  mov     r14, r8
0x180071551  mov     rdi, rdx
0x180071554  mov     rbx, rcx
0x180071557  xorps   xmm0, xmm0
0x18007155a  movups  xmmword ptr [r11-80h], xmm0
0x18007155f  xor     r15d, r15d
0x180071562  mov     byte ptr [rsp+1A8h+var_158], r15b
0x180071567  lea     rcx, aCscenarioctrlc; "CScenarioCtrlContainerServicing::Instal"...
0x18007156e  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180071573  cmp     [rbx+58h], r15b
0x180071577  jz      short loc_18007158F
0x180071579  mov     [r14], r15d
0x18007157c  lea     rcx, aPostponingCont; "Postponing container servicing in offli"...
0x180071583  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180071588  xor     eax, eax
0x18007158a  jmp     loc_180071F5B
0x18007158f  mov     [rsp+1A8h+var_F8], r15
0x180071597  mov     [rsp+1A8h+var_F0], r15
0x18007159f  xorps   xmm0, xmm0
0x1800715a2  movups  xmmword ptr [rsp+1A8h+var_A0], xmm0
0x1800715aa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800715b2  movdqu  [rsp+1A8h+var_90], xmm1
0x1800715bb  mov     word ptr [rsp+1A8h+var_A0], r15w
0x1800715c4  movups  [rsp+1A8h+var_C0], xmm0
0x1800715cc  movdqu  [rsp+1A8h+var_B0], xmm1
0x1800715d5  mov     word ptr [rsp+1A8h+var_C0], r15w
0x1800715de  movups  [rsp+1A8h+var_E0], xmm0
0x1800715e6  movdqu  [rsp+1A8h+var_D0], xmm1
0x1800715ef  mov     word ptr [rsp+1A8h+var_E0], r15w
0x1800715f8  mov     [rsp+1A8h+var_150], r15
0x1800715fd  lea     rax, [rbx+80h]
0x180071604  lea     rcx, [rsp+1A8h+var_F8]
0x18007160c  mov     [rsp+1A8h+var_160], rcx
0x180071611  lea     rcx, [rsp+1A8h+var_E0]
0x180071619  mov     [rsp+1A8h+var_168], rcx
0x18007161e  lea     rcx, [rsp+1A8h+var_C0]
0x180071626  mov     [rsp+1A8h+var_170], rcx
0x18007162b  lea     rcx, [rsp+1A8h+var_A0]
0x180071633  mov     [rsp+1A8h+var_178], rcx
0x180071638  mov     [rsp+1A8h+var_180], rax
0x18007163d  lea     rax, [rsp+1A8h+var_158]
0x180071642  mov     [rsp+1A8h+var_188], rax; int
0x180071647  lea     r9, [rsp+1A8h+var_150]
0x18007164c  xor     r8d, r8d
0x18007164f  mov     rdx, rdi
0x180071652  mov     rcx, rbx
0x180071655  call    ?GetLayerDetails@CScenarioCtrlContainerServicing@@AEAAJPEB_W_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_NPEAW4ContainerLayerFlags@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@55PEAV?$Auto@U?$Vector@U_GUID@@@Windows@@@Windows@@@Z
0x18007165a  mov     edi, eax
0x18007165c  test    eax, eax
0x18007165e  jns     loc_180071765
0x180071664  mov     [rsp+1A8h+var_E8], eax
0x18007166b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180071672  test    rcx, rcx
0x180071675  jz      short loc_1800716C2
0x180071677  lea     r9, aFailedToGetLay; "Failed to get layers"
0x18007167e  mov     ebx, 3
0x180071683  mov     r8d, ebx
0x180071686  xor     edx, edx
0x180071688  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007168d  lea     rax, [rsp+1A8h+var_E8]
0x180071695  mov     qword ptr [rsp+1A8h+var_108], rax
0x18007169d  lea     rax, [rsp+1A8h+var_108]
0x1800716a5  mov     [rsp+1A8h+var_188], rax; int
0x1800716aa  lea     r9, asc_1802C6678; ": {}"
0x1800716b1  mov     r8d, ebx
0x1800716b4  mov     dl, 1
0x1800716b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800716bd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800716c2  mov     rcx, [rsp+1A8h]; this
0x1800716ca  mov     r9d, edi; char *
0x1800716cd  lea     r8, aOnecoreBaseNts_15; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x1800716d4  mov     edx, 59h ; 'Y'; void *
0x1800716d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800716de  nop
0x1800716df  mov     rbx, [rsp+1A8h+var_150]
0x1800716e4  test    rbx, rbx
0x1800716e7  jz      short loc_180071712
0x1800716e9  call    cs:__imp_GetProcessHeap
0x1800716f0  nop     dword ptr [rax+rax+00h]
0x1800716f5  mov     rcx, rax; hHeap
0x1800716f8  lea     r8, [rbx-4]; lpMem
0x1800716fc  xor     edx, edx; dwFlags
0x1800716fe  call    cs:__imp_HeapFree
0x180071705  nop     dword ptr [rax+rax+00h]
0x18007170a  xor     ecx, ecx
0x18007170c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180071711  nop
0x180071712  lea     rcx, [rsp+1A8h+var_E0]; void *
0x18007171a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007171f  nop
0x180071720  lea     rcx, [rsp+1A8h+var_C0]; void *
0x180071728  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007172d  nop
0x18007172e  lea     rcx, [rsp+1A8h+var_A0]; void *
0x180071736  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007173b  nop
0x18007173c  mov     rcx, [rsp+1A8h+var_F8]; void *
0x180071744  test    rcx, rcx
0x180071747  jz      short loc_18007175E
0x180071749  mov     [rsp+1A8h+var_F8], r15
0x180071751  mov     [rsp+1A8h+var_F0], r15
0x180071759  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007175e  mov     eax, edi
0x180071760  jmp     loc_180071F5B
0x180071765  cmp     byte ptr [rsp+1A8h+var_158], r15b
0x18007176a  jz      loc_180071ECE
0x180071770  cmp     [rbx+78h], r15d
0x180071774  jz      loc_180071868
0x18007177a  lea     rcx, aPostponingCont_0; "Postponing container servicing because "...
0x180071781  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x180071786  cmp     [rbx+7Ch], r15d
0x18007178a  jz      loc_180071ECE
0x180071790  movups  xmm0, cs:xmmword_1802C24B0
0x180071797  movdqu  xmmword ptr [rsp+1A8h+var_80], xmm0
0x1800717a0  lea     rcx, [rbx+30h]
0x1800717a4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x1800717a9  mov     r8, rax
0x1800717ac  xor     edx, edx
0x1800717ae  lea     rcx, [rsp+1A8h+var_80]
0x1800717b6  call    ?GuidToSString@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBU_GUID@@HPEAPEA_W@Z; CDlpHelpersT<CEmptyType>::GuidToSString(_GUID const *,int,wchar_t * *)
0x1800717bb  mov     edi, eax
0x1800717bd  test    eax, eax
0x1800717bf  jns     loc_180071ECE
0x1800717c5  mov     rcx, [rsp+1A8h]; this
0x1800717cd  mov     r9d, eax; char *
0x1800717d0  lea     r8, aOnecoreBaseNts_15; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x1800717d7  mov     edx, 65h ; 'e'; void *
0x1800717dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800717e1  nop
0x1800717e2  mov     rbx, [rsp+1A8h+var_150]
0x1800717e7  test    rbx, rbx
0x1800717ea  jz      short loc_180071815
0x1800717ec  call    cs:__imp_GetProcessHeap
0x1800717f3  nop     dword ptr [rax+rax+00h]
0x1800717f8  mov     rcx, rax; hHeap
0x1800717fb  lea     r8, [rbx-4]; lpMem
0x1800717ff  xor     edx, edx; dwFlags
0x180071801  call    cs:__imp_HeapFree
0x180071808  nop     dword ptr [rax+rax+00h]
0x18007180d  xor     ecx, ecx
0x18007180f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180071814  nop
0x180071815  lea     rcx, [rsp+1A8h+var_E0]; void *
0x18007181d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071822  nop
0x180071823  lea     rcx, [rsp+1A8h+var_C0]; void *
0x18007182b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071830  nop
0x180071831  lea     rcx, [rsp+1A8h+var_A0]; void *
0x180071839  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007183e  nop
0x18007183f  mov     rcx, [rsp+1A8h+var_F8]; void *
0x180071847  test    rcx, rcx
0x18007184a  jz      short loc_180071861
0x18007184c  mov     [rsp+1A8h+var_F8], r15
0x180071854  mov     [rsp+1A8h+var_F0], r15
0x18007185c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071861  mov     eax, edi
0x180071863  jmp     loc_180071F5B
0x180071868  mov     qword ptr [rsp+1A8h+var_108], r15
0x180071870  mov     [rsp+1A8h+var_100], r15
0x180071878  lea     rax, [rsp+1A8h+var_100]
0x180071880  mov     [rsp+1A8h+var_120], rax
0x180071888  lea     rax, [rsp+1A8h+var_108]
0x180071890  mov     [rsp+1A8h+var_118], rax
0x180071898  mov     [rsp+1A8h+var_110], 1
0x1800718a0  mov     rcx, [rsp+1A8h+var_150]
0x1800718a5  mov     [rsp+1A8h+var_148], rcx
0x1800718aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800718ae  inc     rax
0x1800718b1  cmp     [rcx+rax*2], r15w
0x1800718b6  jnz     short loc_1800718AE
0x1800718b8  mov     [rsp+1A8h+var_148+8], rax
0x1800718bd  lea     rdx, [rsp+1A8h+var_148]
0x1800718c2  lea     rcx, [rsp+1A8h+lpFileName]
0x1800718ca  call    ?GetDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetDirectory(wil::basic_zstring_view<wchar_t> const &)
0x1800718cf  nop
0x1800718d0  lea     rsi, [rbx+68h]
0x1800718d4  mov     rcx, rsi; pguid
0x1800718d7  call    cs:__imp_CoCreateGuid
0x1800718de  nop     dword ptr [rax+rax+00h]
0x1800718e3  mov     edi, eax
0x1800718e5  test    eax, eax
0x1800718e7  jns     loc_1800719BE
0x1800718ed  mov     rcx, [rsp+1A8h]; this
0x1800718f5  mov     r9d, eax; char *
0x1800718f8  lea     r8, aOnecoreBaseNts_15; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x1800718ff  mov     edx, 78h ; 'x'; void *
0x180071904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071909  nop
0x18007190a  lea     rcx, [rsp+1A8h+lpFileName]; void *
0x180071912  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071917  nop
0x180071918  mov     rax, [rsp+1A8h+var_100]
0x180071920  test    rax, rax
0x180071923  jz      short loc_180071938
0x180071925  mov     rcx, qword ptr [rsp+1A8h+var_108]
0x18007192d  test    rcx, rcx
0x180071930  jz      short loc_180071938
0x180071932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071937  nop
0x180071938  mov     rbx, [rsp+1A8h+var_150]
0x18007193d  test    rbx, rbx
0x180071940  jz      short loc_18007196B
0x180071942  call    cs:__imp_GetProcessHeap
0x180071949  nop     dword ptr [rax+rax+00h]
0x18007194e  mov     rcx, rax; hHeap
0x180071951  lea     r8, [rbx-4]; lpMem
0x180071955  xor     edx, edx; dwFlags
0x180071957  call    cs:__imp_HeapFree
0x18007195e  nop     dword ptr [rax+rax+00h]
0x180071963  xor     ecx, ecx
0x180071965  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007196a  nop
0x18007196b  lea     rcx, [rsp+1A8h+var_E0]; void *
0x180071973  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071978  nop
0x180071979  lea     rcx, [rsp+1A8h+var_C0]; void *
0x180071981  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071986  nop
0x180071987  lea     rcx, [rsp+1A8h+var_A0]; void *
0x18007198f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071994  nop
0x180071995  mov     rcx, [rsp+1A8h+var_F8]; void *
0x18007199d  test    rcx, rcx
0x1800719a0  jz      short loc_1800719B7
0x1800719a2  mov     [rsp+1A8h+var_F8], r15
0x1800719aa  mov     [rsp+1A8h+var_F0], r15
0x1800719b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800719b7  mov     eax, edi
0x1800719b9  jmp     loc_180071F5B
0x1800719be  mov     r9, rbx
0x1800719c1  lea     rdx, [rsp+1A8h+var_100]
0x1800719c9  lea     rcx, [rsp+1A8h+var_108]
0x1800719d1  call    GetContainerProgressWNFSubscription
0x1800719d6  mov     edi, eax
0x1800719d8  test    eax, eax
0x1800719da  jns     loc_180071AB1
0x1800719e0  mov     rcx, [rsp+1A8h]; this
0x1800719e8  mov     r9d, eax; char *
0x1800719eb  lea     r8, aOnecoreBaseNts_15; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x1800719f2  mov     edx, 7Eh ; '~'; void *
0x1800719f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800719fc  nop
0x1800719fd  lea     rcx, [rsp+1A8h+lpFileName]; void *
0x180071a05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071a0a  nop
0x180071a0b  mov     rax, [rsp+1A8h+var_100]
0x180071a13  test    rax, rax
0x180071a16  jz      short loc_180071A2B
0x180071a18  mov     rcx, qword ptr [rsp+1A8h+var_108]
0x180071a20  test    rcx, rcx
0x180071a23  jz      short loc_180071A2B
0x180071a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a2a  nop
0x180071a2b  mov     rbx, [rsp+1A8h+var_150]
0x180071a30  test    rbx, rbx
0x180071a33  jz      short loc_180071A5E
0x180071a35  call    cs:__imp_GetProcessHeap
0x180071a3c  nop     dword ptr [rax+rax+00h]
0x180071a41  mov     rcx, rax; hHeap
0x180071a44  lea     r8, [rbx-4]; lpMem
0x180071a48  xor     edx, edx; dwFlags
0x180071a4a  call    cs:__imp_HeapFree
0x180071a51  nop     dword ptr [rax+rax+00h]
0x180071a56  xor     ecx, ecx
0x180071a58  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180071a5d  nop
0x180071a5e  lea     rcx, [rsp+1A8h+var_E0]; void *
0x180071a66  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071a6b  nop
0x180071a6c  lea     rcx, [rsp+1A8h+var_C0]; void *
0x180071a74  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071a79  nop
0x180071a7a  lea     rcx, [rsp+1A8h+var_A0]; void *
0x180071a82  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071a87  nop
0x180071a88  mov     rcx, [rsp+1A8h+var_F8]; void *
0x180071a90  test    rcx, rcx
0x180071a93  jz      short loc_180071AAA
0x180071a95  mov     [rsp+1A8h+var_F8], r15
0x180071a9d  mov     [rsp+1A8h+var_F0], r15
0x180071aa5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071aaa  mov     eax, edi
0x180071aac  jmp     loc_180071F5B
0x180071ab1  cmp     [rbx+7Ch], r15d
0x180071ab5  jnz     loc_180071B8A
0x180071abb  lea     rax, [rsp+1A8h+var_A0]
0x180071ac3  cmp     qword ptr [rsp+1A8h+var_90+8], 7
  ... truncated ...
```
