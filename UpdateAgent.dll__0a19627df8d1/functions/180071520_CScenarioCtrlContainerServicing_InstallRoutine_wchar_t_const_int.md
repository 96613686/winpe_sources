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
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  const struct std::nothrow_t *v12; // rdx
  void *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rbx
  HANDLE v18; // rax
  const struct std::nothrow_t *v19; // rdx
  void *v20; // rcx
  __int64 v21; // rax
  _OWORD *v22; // rsi
  HRESULT Guid; // eax
  __int64 v24; // r8
  unsigned int v25; // edi
  __int64 v26; // rbx
  HANDLE v27; // rax
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rcx
  int ContainerProgressWNFSubscription; // eax
  unsigned int v31; // edi
  __int64 v32; // rbx
  HANDLE v33; // rax
  const struct std::nothrow_t *v34; // rdx
  void *v35; // rcx
  wchar_t *v36; // rax
  wchar_t *v37; // r8
  __int128 *v38; // rdx
  wchar_t *v39; // rcx
  int v40; // eax
  wchar_t *v41; // rax
  const WCHAR *v42; // rcx
  int ContainerBaseImages; // eax
  __int64 v44; // rdx
  unsigned int v45; // edi
  __int64 v46; // rbx
  HANDLE v47; // rax
  const struct std::nothrow_t *v48; // rdx
  void *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  unsigned int v52; // edi
  __int64 v53; // rbx
  HANDLE v54; // rax
  const struct std::nothrow_t *v55; // rdx
  void *v56; // rcx
  __int64 v57; // rbx
  HANDLE v58; // rax
  const struct std::nothrow_t *v59; // rdx
  void *v60; // rcx
  int v61; // [rsp+20h] [rbp-188h]
  __int64 *v62; // [rsp+20h] [rbp-188h]
  int v63; // [rsp+50h] [rbp-158h] BYREF
  __int64 v64; // [rsp+58h] [rbp-150h] BYREF
  __int64 v65[2]; // [rsp+60h] [rbp-148h] BYREF
  __int64 v66[5]; // [rsp+70h] [rbp-138h] BYREF
  char v67; // [rsp+98h] [rbp-110h]
  int v68[2]; // [rsp+A0h] [rbp-108h] BYREF
  void (*v69)(void); // [rsp+A8h] [rbp-100h] BYREF
  void *v70; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-F0h]
  int v72; // [rsp+C0h] [rbp-E8h] BYREF
  __int128 v73; // [rsp+C8h] [rbp-E0h] BYREF
  __m128i v74; // [rsp+D8h] [rbp-D0h]
  __int128 v75; // [rsp+E8h] [rbp-C0h] BYREF
  __m128i v76; // [rsp+F8h] [rbp-B0h]
  wchar_t *v77[2]; // [rsp+108h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+118h] [rbp-90h]
  __int64 v79[2]; // [rsp+128h] [rbp-80h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+138h] [rbp-70h] BYREF
  unsigned __int64 v81; // [rsp+150h] [rbp-58h]
  __int64 v82[2]; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v66[2] = -2;
  v4 = (int)a2;
  *(_OWORD *)v79 = 0;
  LOBYTE(v63) = 0;
  try
  {
    LogAdapter::TraceInfo<>("CScenarioCtrlContainerServicing::InstallRoutine Enter.");
    if ( *((_BYTE *)this + 88) )
    {
      *a3 = 0;
      LogAdapter::TraceInfo<>("Postponing container servicing in offline scenario.");
      return 0;
    }
    v70 = 0;
    v71 = 0;
    *(_OWORD *)v77 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v77[0]) = 0;
    v75 = 0;
    v76 = si128;
    LOWORD(v75) = 0;
    v73 = 0;
    v74 = si128;
    LOWORD(v73) = 0;
    v64 = 0;
    LayerDetails = CScenarioCtrlContainerServicing::GetLayerDetails(
                     (_DWORD)this,
                     v4,
                     0,
                     (unsigned int)&v64,
                     (__int64)&v63,
                     (__int64)this + 128,
                     (__int64)v77,
                     (__int64)&v75,
                     (__int64)&v73,
                     (__int64)&v70);
    v9 = LayerDetails;
    if ( LayerDetails < 0 )
    {
      v72 = LayerDetails;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get layers");
        *(_QWORD *)v68 = &v72;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v68);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)v9,
        v61);
      v10 = v64;
      if ( v64 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v10 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(v77);
      v13 = v70;
      if ( v70 )
      {
        v70 = 0;
        v71 = 0;
        operator delete(v13, v12);
      }
      return v9;
    }
    if ( !(_BYTE)v63 )
      goto LABEL_81;
    if ( *((_DWORD *)this + 30) )
    {
      LogAdapter::TraceInfo<>("Postponing container servicing because LCU staging has been postponed.");
      if ( *((_DWORD *)this + 31) )
      {
        *(_OWORD *)v79 = xmmword_1802C24B0;
        v14 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ((char *)this + 48);
        v15 = CDlpHelpersT<CEmptyType>::GuidToSString(v79, 0, v14);
        v16 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
            (const char *)(unsigned int)v15,
            v61);
          v17 = v64;
          if ( v64 )
          {
            v18 = GetProcessHeap();
            HeapFree(v18, 0, (LPVOID)(v17 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          std::wstring::~wstring(&v73);
          std::wstring::~wstring(&v75);
          std::wstring::~wstring(v77);
          v20 = v70;
          if ( v70 )
          {
            v70 = 0;
            v71 = 0;
            operator delete(v20, v19);
          }
          return v16;
        }
      }
      goto LABEL_81;
    }
    *(_QWORD *)v68 = 0;
    v69 = 0;
    v66[3] = (__int64)&v69;
    v66[4] = (__int64)v68;
    v67 = 1;
    v65[0] = v64;
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(v64 + 2 * v21) );
    v65[1] = v21;
    GetDirectory(lpFileName, v65);
    v22 = (_OWORD *)((char *)this + 104);
    Guid = CoCreateGuid((GUID *)((char *)this + 104));
    v25 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)(unsigned int)Guid,
        v61);
      std::wstring::~wstring(lpFileName);
      if ( v69 && *(_QWORD *)v68 )
        v69();
      v26 = v64;
      if ( v64 )
      {
        v27 = GetProcessHeap();
        HeapFree(v27, 0, (LPVOID)(v26 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(v77);
      v29 = v70;
      if ( v70 )
      {
        v70 = 0;
        v71 = 0;
        operator delete(v29, v28);
      }
      return v25;
    }
    ContainerProgressWNFSubscription = GetContainerProgressWNFSubscription(v68, &v69, v24, this);
    v31 = ContainerProgressWNFSubscription;
    if ( ContainerProgressWNFSubscription < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)(unsigned int)ContainerProgressWNFSubscription,
        v61);
      std::wstring::~wstring(lpFileName);
      if ( v69 && *(_QWORD *)v68 )
        v69();
      v32 = v64;
      if ( v64 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, (LPVOID)(v32 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(v77);
      v35 = v70;
      if ( v70 )
      {
        v70 = 0;
        v71 = 0;
        operator delete(v35, v34);
      }
      return v31;
    }
    if ( !*((_DWORD *)this + 31) )
    {
      v36 = (wchar_t *)v77;
      if ( si128.m128i_i64[1] > 7uLL )
        v36 = v77[0];
      v65[0] = 0;
      v65[1] = 0;
      v37 = (wchar_t *)&v73;
      if ( v74.m128i_i64[1] > 7uLL )
        v37 = (wchar_t *)v73;
      v38 = &v75;
      if ( v76.m128i_i64[1] > 7uLL )
        v38 = (__int128 *)v75;
      v39 = (wchar_t *)lpFileName;
      if ( v81 > 7 )
        v39 = (wchar_t *)lpFileName[0];
      *(_OWORD *)v82 = *v22;
      v40 = ServiceContainerBaseImages(
              v39,
              v38,
              v37,
              (__int64)&v70,
              (wchar_t **)v65,
              v36,
              (struct _GUID *)v82,
              (__int64)v79);
      if ( v40 >= 0 )
      {
LABEL_69:
        v50 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ((char *)this + 48);
        v51 = CDlpHelpersT<CEmptyType>::GuidToSString(v79, 0, v50);
        v52 = v51;
        if ( v51 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
            (const char *)(unsigned int)v51,
            (int)v62);
          std::wstring::~wstring(lpFileName);
          if ( v69 && *(_QWORD *)v68 )
            v69();
          v53 = v64;
          if ( v64 )
          {
            v54 = GetProcessHeap();
            HeapFree(v54, 0, (LPVOID)(v53 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          std::wstring::~wstring(&v73);
          std::wstring::~wstring(&v75);
          std::wstring::~wstring(v77);
          v56 = v70;
          if ( v70 )
          {
            v70 = 0;
            v71 = 0;
            operator delete(v56, v55);
          }
          return v52;
        }
        std::wstring::~wstring(lpFileName);
        if ( v69 && *(_QWORD *)v68 )
          ((void (__fastcall *)(_QWORD))v69)(*(_QWORD *)v68);
LABEL_81:
        *a3 = 0;
        v57 = v64;
        if ( v64 )
        {
          v58 = GetProcessHeap();
          HeapFree(v58, 0, (LPVOID)(v57 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        std::wstring::~wstring(&v73);
        std::wstring::~wstring(&v75);
        std::wstring::~wstring(v77);
        v60 = v70;
        if ( v70 )
        {
          v70 = 0;
          v71 = 0;
          operator delete(v60, v59);
        }
        return 0;
      }
      LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v40, "Failed to service container base images");
    }
    *(_OWORD *)v82 = 0;
    v41 = (wchar_t *)v77;
    if ( si128.m128i_i64[1] > 7uLL )
      v41 = v77[0];
    v66[0] = 0;
    v66[1] = 0;
    v42 = (const WCHAR *)lpFileName;
    if ( v81 > 7 )
      v42 = lpFileName[0];
    *(_OWORD *)v65 = *v22;
    ContainerBaseImages = ReCreateContainerBaseImages(v42, (__int64)v66, v41, (__int64)v65, (__int64)v79, (__int64)v82);
    v45 = ContainerBaseImages;
    if ( ContainerBaseImages < 0 )
    {
      v72 = ContainerBaseImages;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to recreate container base images");
        v65[0] = (__int64)&v72;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v65);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlContainer.h",
        (const char *)v45,
        (int)v62);
      std::wstring::~wstring(lpFileName);
      if ( v69 && *(_QWORD *)v68 )
        v69();
      v46 = v64;
      if ( v64 )
      {
        v47 = GetProcessHeap();
        HeapFree(v47, 0, (LPVOID)(v46 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      std::wstring::~wstring(&v73);
      std::wstring::~wstring(&v75);
      std::wstring::~wstring(v77);
      v49 = v70;
      if ( v70 )
      {
        v70 = 0;
        v71 = 0;
        operator delete(v49, v48);
      }
      return v45;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      v62 = v82;
      LOBYTE(v44) = 1;
      LogAdapter::Logger::LogNumObjects<_GUID>(*(_QWORD *)&LogAdapter::g_Logger, v44, 1, "Recreated layer {}");
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
