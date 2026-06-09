# CKernelReport::SendLiveReport(wchar_t const *,wchar_t const *)

- ea: `0x14003c780`
- end: `0x14003d03f`
- name: `?SendLiveReport@CKernelReport@@AEAAJPEB_W0@Z`
- size: `2239`
- prototype: `int(CKernelReport *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x14003c2bc`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400054e4`
- `0x14000ca20`
- `0x140010034`
- `0x1400149e8`
- `0x140025c44`
- `0x1400372dc`
- `0x140037610`
- `0x14003768c`
- `0x140038d00`
- `0x14003ad40`
- `0x14003b510`
- `0x14003c780`
- `0x14003dc68`
- `0x1400420a4`
- `0x140045078`
- `0x140046d00`

## import_xrefs

- `wer!WerReportSubmit` at `0x14003cf54`
- `wer!WerReportSubmit` at `0x14003cf54`
- `wer!WerReportCreate` at `0x14003cb88`
- `wer!WerReportCreate` at `0x14003cb88`
- `wer!WerpAddFile` at `0x14003cccc`
- `wer!WerpAddFile` at `0x14003cd82`
- `wer!WerpAddFile` at `0x14003cdd6`
- `wer!WerpAddFile` at `0x14003cef6`
- `wer!WerpAddFile` at `0x14003cccc`
- `wer!WerpAddFile` at `0x14003cd82`
- `wer!WerpAddFile` at `0x14003cdd6`
- `wer!WerpAddFile` at `0x14003cef6`
- `wer!WerpSetTelemetryKernelParams` at `0x14003cbe9`
- `wer!WerpSetTelemetryKernelParams` at `0x14003cbe9`

## string_xrefs

- `0x14003cf7f`: `WerCreateReport failed`
- `0x14003cd62`: `sysdata.xml`
- `0x14003cdb6`: `sysdata.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CKernelReport::SendLiveReport(wchar_t *this, const wchar_t *a2, const wchar_t *a3)
{
  HRESULT v6; // edi
  void *v7; // rcx
  bool v8; // zf
  __int64 v9; // rbx
  __int64 v10; // rdi
  WCHAR *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  WCHAR *wzFriendlyEventName; // rax
  WCHAR v15; // r9
  WCHAR *v16; // rcx
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  WCHAR *wzApplicationName; // rax
  WCHAR v20; // r8
  WCHAR *v21; // rcx
  WCHAR *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rdx
  WCHAR *wzDescription; // rax
  WCHAR v26; // r9
  WCHAR *v27; // rcx
  __int64 v28; // rcx
  const wchar_t *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  wchar_t *v32; // rax
  wchar_t v33; // r10
  wchar_t *v34; // rcx
  const wchar_t *v35; // rcx
  wchar_t *v36; // rax
  wchar_t v37; // r8
  wchar_t *v38; // rcx
  const char *v39; // rax
  __int64 v40; // rdx
  int Settings; // eax
  _WORD *v42; // rdi
  int SystemData; // eax
  __int64 v44; // rcx
  int v45; // edx
  int v46; // edx
  unsigned __int16 *v47; // r8
  __int64 v48; // rax
  unsigned __int16 *v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // r9
  int v52; // eax
  int v53; // rcx^4
  int v54; // eax
  wil::details *v56; // [rsp+20h] [rbp-E0h]
  wil::details *v57; // [rsp+20h] [rbp-E0h]
  wil::details *v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-D8h]
  int v60[2]; // [rsp+28h] [rbp-D8h]
  char *v61; // [rsp+30h] [rbp-D0h]
  char *v62; // [rsp+30h] [rbp-D0h]
  char v63[8]; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *v65; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v66; // [rsp+58h] [rbp-A8h]
  _WORD v67[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v68; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v69; // [rsp+78h] [rbp-88h]
  _WORD v70[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  void *v72; // [rsp+98h] [rbp-68h]
  _WORD *v73; // [rsp+A0h] [rbp-60h]
  _WORD v74[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v75; // [rsp+B8h] [rbp-48h]
  _WORD *v76; // [rsp+C0h] [rbp-40h]
  _WORD v77[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h]
  int v79; // [rsp+E0h] [rbp-20h]
  void *v80[2]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD v81[8]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD v82[2]; // [rsp+110h] [rbp+10h] BYREF
  _WORD *v83; // [rsp+118h] [rbp+18h]
  _WORD *v84; // [rsp+120h] [rbp+20h]
  _WORD v85[8]; // [rsp+128h] [rbp+28h] BYREF
  _WORD *v86; // [rsp+138h] [rbp+38h]
  _WORD *v87; // [rsp+140h] [rbp+40h]
  _WORD v88[8]; // [rsp+148h] [rbp+48h] BYREF
  _WORD *v89; // [rsp+158h] [rbp+58h]
  _WORD *v90; // [rsp+160h] [rbp+60h]
  _WORD v91[8]; // [rsp+168h] [rbp+68h] BYREF
  _WORD *v92; // [rsp+178h] [rbp+78h]
  _WORD *v93; // [rsp+180h] [rbp+80h]
  _WORD v94[12]; // [rsp+188h] [rbp+88h] BYREF
  _OWORD v95[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v96; // [rsp+1C0h] [rbp+C0h]
  struct _WER_REPORT_INFORMATION pReportInformation; // [rsp+1D0h] [rbp+D0h] BYREF
  char v98; // [rsp+A70h] [rbp+970h] BYREF
  char v99; // [rsp+AF0h] [rbp+9F0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+BE8h] [rbp+AE8h]

  memset(v95, 0, sizeof(v95));
  v96 = 0;
  v72 = v74;
  v73 = v74;
  v74[0] = 0;
  v75 = v77;
  v76 = v77;
  v77[0] = 0;
  v71 = 1;
  v78 = 5;
  v79 = 0;
  v83 = v85;
  v84 = v85;
  v85[0] = 0;
  v86 = v88;
  v87 = v88;
  v88[0] = 0;
  v89 = v91;
  v90 = v91;
  v91[0] = 0;
  v92 = v94;
  v93 = v94;
  v94[0] = 0;
  v82[0] = 1;
  v82[1] = 1;
  v63[0] = 0;
  phReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x9C4u);
  v68 = v70;
  v69 = v70;
  v70[0] = 0;
  v65 = v67;
  v66 = v67;
  v67[0] = 0;
  pReportInformation.dwSize = 2504;
  v6 = -2147024809;
  if ( !a2 )
  {
    CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)v82);
LABEL_94:
    if ( v75 != v77 )
      operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v72;
    v8 = v72 == v74;
    goto LABEL_97;
  }
  if ( UtilFileExists(a2) )
  {
    v9 = 2147483646;
    v10 = 128;
    if ( (int)UtilLoadString(&v65, 6, &_ImageBase) >= 0 )
    {
      v11 = (WCHAR *)v65;
      if ( v65 != v66 )
      {
        v12 = 2147483646;
        v13 = 128;
        wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
        do
        {
          if ( !v12 )
            break;
          v15 = *v11;
          if ( !*v11 )
            break;
          ++v11;
          *wzFriendlyEventName++ = v15;
          --v12;
          --v13;
        }
        while ( v13 );
        v16 = wzFriendlyEventName - 1;
        if ( v13 )
          v16 = wzFriendlyEventName;
        *v16 = 0;
      }
    }
    if ( (int)UtilLoadString(&v65, 3, &_ImageBase) >= 0 )
    {
      v17 = (WCHAR *)v65;
      if ( v65 != v66 )
      {
        v18 = 2147483646;
        wzApplicationName = pReportInformation.wzApplicationName;
        do
        {
          if ( !v18 )
            break;
          v20 = *v17;
          if ( !*v17 )
            break;
          ++v17;
          *wzApplicationName++ = v20;
          --v18;
          --v10;
        }
        while ( v10 );
        v21 = wzApplicationName - 1;
        if ( v10 )
          v21 = wzApplicationName;
        *v21 = 0;
      }
    }
    if ( (int)UtilLoadString(&v65, 12, &_ImageBase) >= 0 )
    {
      v22 = (WCHAR *)v65;
      if ( v65 != v66 )
      {
        v23 = 2147483646;
        v24 = 512;
        wzDescription = pReportInformation.wzDescription;
        do
        {
          if ( !v23 )
            break;
          v26 = *v22;
          if ( !*v22 )
            break;
          ++v22;
          *wzDescription++ = v26;
          --v23;
          --v24;
        }
        while ( v24 );
        v27 = wzDescription - 1;
        if ( v24 )
          v27 = wzDescription;
        *v27 = 0;
      }
    }
    v28 = 2147483646;
    v29 = L"windows";
    v30 = 64;
    v31 = 64;
    v32 = (wchar_t *)&v98;
    do
    {
      if ( !v28 )
        break;
      v33 = *v29;
      if ( !*v29 )
        break;
      ++v29;
      *v32++ = v33;
      --v28;
      --v31;
    }
    while ( v31 );
    v34 = v32 - 1;
    if ( v31 )
      v34 = v32;
    *v34 = 0;
    v35 = L"windows8";
    v36 = (wchar_t *)&v99;
    do
    {
      if ( !v9 )
        break;
      v37 = *v35;
      if ( !*v35 )
        break;
      ++v35;
      *v36++ = v37;
      --v9;
      --v30;
    }
    while ( v30 );
    v38 = v36 - 1;
    if ( v30 )
      v38 = v36;
    *v38 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(this + 344, L"LiveKernelEvent");
    v6 = WerReportCreate(L"LiveKernelEvent", WerReportKernel, &pReportInformation, &phReportHandle);
    if ( v6 >= 0 && phReportHandle )
    {
      v6 = CKernelReport::ExtractBugCheckInfo(a2, (struct _BUGCHECK_INFORMATION *)v95);
      if ( v6 >= 0 )
      {
        LODWORD(v56) = WerpSetTelemetryKernelParams(
                         phReportHandle,
                         *((unsigned int *)this + 182),
                         *((unsigned int *)this + 183));
        wil::details::in1diag4::Log_IfFailedMsg(
          retaddr,
          (void *)0x8F7,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendLiveReport",
          (const char *)v56,
          (int)"WerpSetTelemetryKernelParams failed",
          v61);
        LODWORD(v57) = CKernelReport::AddBugCheckSignaturesToReport(
                         phReportHandle,
                         L"LiveKernelEvent",
                         (struct _BUGCHECK_INFORMATION *)v95);
        wil::details::in1diag4::Log_IfFailedMsg(
          retaddr,
          (void *)0x8FD,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendLiveReport",
          (const char *)v57,
          (int)"AddBugCheckSignaturesToReport failed",
          v62);
        Settings = CLiveDumpSettings::LoadSettings((CLiveDumpSettings *)v82, 0, 0);
        if ( Settings < 0 )
        {
          LODWORD(v58) = Settings;
          wil::details::in1diag4::_Log_Hr(
            retaddr,
            (void *)0x907,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::SendLiveReport",
            v58,
            v59);
        }
        *(_QWORD *)v60 = 0;
        v56 = 0;
        v6 = WerpAddFile(phReportHandle, a2, 2);
        if ( v6 >= 0 )
        {
          v42 = this + 64;
          if ( !this[64] )
          {
            SystemData = CKernelReportDataCollection::GetSystemData((CKernelReportDataCollection *)v63, this + 64);
            if ( SystemData < 0 )
            {
              LODWORD(v56) = SystemData;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x91B,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                "CKernelReport::SendLiveReport",
                v56,
                (int)"GetSystemData failed",
                v61);
            }
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl) )
          {
            if ( *v42 )
            {
              *(_QWORD *)v60 = 0;
              v56 = (wil::details *)L"sysdata.xml";
              v45 = WerpAddFile(phReportHandle, this + 64, 5);
              if ( v45 < 0 )
              {
                LODWORD(v56) = v45;
                wil::details::in1diag4::Log_HrMsg(
                  retaddr,
                  (void *)0x931,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                  "CKernelReport::SendLiveReport",
                  v56,
                  (int)"WerAddFile failed",
                  v61);
              }
            }
          }
          else if ( *v42 )
          {
            *(_QWORD *)v60 = 0;
            v56 = (wil::details *)L"sysdata.xml";
            v46 = WerpAddFile(phReportHandle, this + 64, 5);
            if ( v46 < 0 )
            {
              LODWORD(v56) = v46;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x948,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                "CKernelReport::SendLiveReport",
                v56,
                (int)"WerAddFile failed",
                v61);
            }
          }
          if ( (int)CKernelReport::GetMatchingLiveDumpFile(v44, v95, a3, &v68, v56, *(_QWORD *)v60) >= 0 && v68 != v69 )
          {
            CCrashControlSettings::LoadSettings((CCrashControlSettings *)&v71);
            v80[0] = v81;
            v80[1] = v81;
            v81[0] = 0;
            if ( v68 )
            {
              v48 = -1;
              do
                ++v48;
              while ( *((_WORD *)v68 + v48) );
              v49 = (unsigned __int16 *)((char *)v68 + 2 * v48);
              while ( 1 )
              {
                v47 = v49;
                if ( v49 <= v68 )
                  break;
                v50 = *--v49;
                LOWORD(v50) = v50 - 47;
                if ( (unsigned __int16)v50 <= 0x2Du )
                {
                  v51 = 0x200000000801LL;
                  if ( _bittest64(&v51, v50) )
                    break;
                }
              }
            }
            else
            {
              v47 = 0;
            }
            v52 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v80, L"full-%s", v47);
            v53 = 0;
            if ( v52 >= 0 )
              v53 = HIDWORD(v80[0]);
            HIDWORD(v56) = v53;
            v54 = WerpAddFile(phReportHandle, v68, 3);
            if ( v54 < 0 )
            {
              LODWORD(v56) = v54;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x974,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                "CKernelReport::SendLiveReport",
                v56,
                (int)"WerpAddFile failed",
                v61);
            }
            if ( v80[0] != v81 )
              operator delete(v80[0], (const struct std::nothrow_t *)&std::nothrow);
          }
          v6 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x804u, 0);
          if ( v6 >= 0 )
          {
            v6 = 0;
LABEL_89:
            if ( v65 != v67 )
              operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
            if ( v68 != v70 )
              operator delete(v68, (const struct std::nothrow_t *)&std::nothrow);
            CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)v82);
            goto LABEL_94;
          }
          v39 = "WerSubmitReport failed";
          v40 = 2434;
        }
        else
        {
          v39 = "WerAddFile failed";
          v40 = 2322;
        }
      }
      else
      {
        v39 = "ExtractBugCheckInfo failed";
        v40 = 2289;
      }
    }
    else
    {
      v39 = "WerCreateReport failed";
      v40 = 2281;
    }
    LODWORD(v56) = v6;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendLiveReport",
      v56,
      (int)v39,
      v61);
    goto LABEL_89;
  }
  LODWORD(v56) = -2147024809;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x8B6,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendLiveReport",
    v56,
    (int)"File does not exist: %ws",
    (const char *)a2);
  if ( v65 != v67 )
    operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
  if ( v68 != v70 )
    operator delete(v68, (const struct std::nothrow_t *)&std::nothrow);
  CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)v82);
  if ( v75 != v77 )
    operator delete(v75, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v72;
  v8 = v72 == v74;
LABEL_97:
  if ( !v8 )
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003c780  mov     [rsp-8+arg_18], rbx
0x14003c785  push    rbp
0x14003c786  push    rsi
0x14003c787  push    rdi
0x14003c788  push    r12
0x14003c78a  push    r13
0x14003c78c  push    r14
0x14003c78e  push    r15
0x14003c790  lea     rbp, [rsp-0AB0h]
0x14003c798  sub     rsp, 0BB0h
0x14003c79f  mov     rax, cs:__security_cookie
0x14003c7a6  xor     rax, rsp
0x14003c7a9  mov     [rbp+0AE0h+var_40], rax
0x14003c7b0  mov     r12, r8
0x14003c7b3  mov     r15, rdx
0x14003c7b6  mov     r13, rcx
0x14003c7b9  xorps   xmm0, xmm0
0x14003c7bc  xor     eax, eax
0x14003c7be  movups  [rbp+0AE0h+var_A40], xmm0
0x14003c7c5  movups  [rbp+0AE0h+var_A30], xmm0
0x14003c7cc  mov     [rbp+0AE0h+var_A20], rax
0x14003c7d3  lea     rax, [rbp+0AE0h+var_B38]
0x14003c7d7  mov     [rbp+0AE0h+var_B48], rax
0x14003c7db  lea     rax, [rbp+0AE0h+var_B38]
0x14003c7df  mov     [rbp+0AE0h+var_B40], rax
0x14003c7e3  xor     esi, esi
0x14003c7e5  mov     [rbp+0AE0h+var_B38], si
0x14003c7e9  lea     rax, [rbp+0AE0h+var_B18]
0x14003c7ed  mov     [rbp+0AE0h+var_B28], rax
0x14003c7f1  lea     rax, [rbp+0AE0h+var_B18]
0x14003c7f5  mov     [rbp+0AE0h+var_B20], rax
0x14003c7f9  mov     [rbp+0AE0h+var_B18], si
0x14003c7fd  mov     [rbp+0AE0h+var_B50], 1
0x14003c805  mov     [rbp+0AE0h+var_B08], 5
0x14003c80d  mov     [rbp+0AE0h+var_B00], esi
0x14003c810  lea     rax, [rbp+0AE0h+var_AB8]
0x14003c814  mov     [rbp+0AE0h+var_AC8], rax
0x14003c818  lea     rax, [rbp+0AE0h+var_AB8]
0x14003c81c  mov     [rbp+0AE0h+var_AC0], rax
0x14003c820  mov     [rbp+0AE0h+var_AB8], si
0x14003c824  lea     rax, [rbp+0AE0h+var_A98]
0x14003c828  mov     [rbp+0AE0h+var_AA8], rax
0x14003c82c  lea     rax, [rbp+0AE0h+var_A98]
0x14003c830  mov     [rbp+0AE0h+var_AA0], rax
0x14003c834  mov     [rbp+0AE0h+var_A98], si
0x14003c838  lea     rax, [rbp+0AE0h+var_A78]
0x14003c83c  mov     [rbp+0AE0h+var_A88], rax
0x14003c840  lea     rax, [rbp+0AE0h+var_A78]
0x14003c844  mov     [rbp+0AE0h+var_A80], rax
0x14003c848  mov     [rbp+0AE0h+var_A78], si
0x14003c84c  lea     rax, [rbp+0AE0h+var_A58]
0x14003c853  mov     [rbp+0AE0h+var_A68], rax
0x14003c857  lea     rax, [rbp+0AE0h+var_A58]
0x14003c85e  mov     [rbp+0AE0h+var_A60], rax
0x14003c865  mov     [rbp+0AE0h+var_A58], si
0x14003c86c  mov     [rbp+0AE0h+var_AD0], 1
0x14003c873  mov     [rbp+0AE0h+var_ACC], 1
0x14003c87a  mov     [rsp+0BE0h+var_BA0], sil
0x14003c87f  mov     [rsp+0BE0h+phReportHandle], rsi
0x14003c884  xor     edx, edx; Val
0x14003c886  mov     r8d, 9C4h; Size
0x14003c88c  lea     rcx, [rbp+0AE0h+pReportInformation+4]; void *
0x14003c893  call    memset_0
0x14003c898  lea     rax, [rbp+0AE0h+var_B60]
0x14003c89c  mov     [rsp+0BE0h+var_B70], rax
0x14003c8a1  lea     rax, [rbp+0AE0h+var_B60]
0x14003c8a5  mov     [rsp+0BE0h+var_B68], rax
0x14003c8aa  mov     [rbp+0AE0h+var_B60], si
0x14003c8ae  lea     rax, [rsp+0BE0h+var_B80]
0x14003c8b3  mov     [rsp+0BE0h+var_B90], rax
0x14003c8b8  lea     rax, [rsp+0BE0h+var_B80]
0x14003c8bd  mov     [rsp+0BE0h+var_B88], rax
0x14003c8c2  mov     [rsp+0BE0h+var_B80], si
0x14003c8c7  mov     [rbp+0AE0h+pReportInformation.dwSize], 9C8h
0x14003c8d1  mov     edi, 80070057h
0x14003c8d6  test    r15, r15
0x14003c8d9  jnz     short loc_14003C8F1
0x14003c8db  lea     rcx, [rbp+0AE0h+var_AD0]; this
0x14003c8df  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003c8e4  nop
0x14003c8e5  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003c8ec  jmp     loc_14003CFE8
0x14003c8f1  mov     rcx, r15; wchar_t *
0x14003c8f4  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x14003c8f9  test    al, al
0x14003c8fb  jnz     loc_14003C99B
0x14003c901  mov     rcx, [rbp+0AE8h]; this
0x14003c908  mov     [rsp+0BE0h+var_BB0], r15; char *
0x14003c90d  lea     rax, aFileDoesNotExi; "File does not exist: %ws"
0x14003c914  mov     qword ptr [rsp+0BE0h+var_BB8], rax; int
0x14003c919  mov     dword ptr [rsp+0BE0h+var_BC0], edi; wil::details *
0x14003c91d  lea     r9, aCkernelreportS_0; "CKernelReport::SendLiveReport"
0x14003c924  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c92b  mov     edx, 8B6h; void *
0x14003c930  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c935  nop
0x14003c936  lea     rax, [rsp+0BE0h+var_B80]
0x14003c93b  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003c942  mov     rcx, [rsp+0BE0h+var_B90]; void *
0x14003c947  cmp     rcx, rax
0x14003c94a  jz      short loc_14003C955
0x14003c94c  mov     rdx, rbx; struct std::nothrow_t *
0x14003c94f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c954  nop
0x14003c955  lea     rax, [rbp+0AE0h+var_B60]
0x14003c959  mov     rcx, [rsp+0BE0h+var_B70]; void *
0x14003c95e  cmp     rcx, rax
0x14003c961  jz      short loc_14003C96C
0x14003c963  mov     rdx, rbx; struct std::nothrow_t *
0x14003c966  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c96b  nop
0x14003c96c  lea     rcx, [rbp+0AE0h+var_AD0]; this
0x14003c970  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003c975  nop
0x14003c976  mov     rcx, [rbp+0AE0h+var_B28]; void *
0x14003c97a  lea     rax, [rbp+0AE0h+var_B18]
0x14003c97e  cmp     rcx, rax
0x14003c981  jz      short loc_14003C98B
0x14003c983  mov     rdx, rbx; struct std::nothrow_t *
0x14003c986  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003c98b  mov     rcx, [rbp+0AE0h+var_B48]
0x14003c98f  lea     rdx, [rbp+0AE0h+var_B38]
0x14003c993  cmp     rcx, rdx
0x14003c996  jmp     loc_14003D008
0x14003c99b  lea     r8, __ImageBase
0x14003c9a2  mov     edx, 6
0x14003c9a7  lea     rcx, [rsp+0BE0h+var_B90]
0x14003c9ac  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003c9b1  mov     ebx, 7FFFFFFEh
0x14003c9b6  mov     edi, 80h
0x14003c9bb  lea     r14d, [rdi-7Eh]
0x14003c9bf  test    eax, eax
0x14003c9c1  js      short loc_14003CA0B
0x14003c9c3  mov     rcx, [rsp+0BE0h+var_B90]
0x14003c9c8  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003c9cd  jz      short loc_14003CA0B
0x14003c9cf  mov     r8d, ebx
0x14003c9d2  mov     edx, edi
0x14003c9d4  lea     rax, [rbp+0AE0h+pReportInformation.wzFriendlyEventName]
0x14003c9db  test    r8, r8
0x14003c9de  jz      short loc_14003C9FD
0x14003c9e0  movzx   r9d, word ptr [rcx]
0x14003c9e4  test    r9w, r9w
0x14003c9e8  jz      short loc_14003C9FD
0x14003c9ea  add     rcx, r14
0x14003c9ed  mov     [rax], r9w
0x14003c9f1  add     rax, r14
0x14003c9f4  dec     r8
0x14003c9f7  sub     rdx, 1
0x14003c9fb  jnz     short loc_14003C9DB
0x14003c9fd  lea     rcx, [rax-2]
0x14003ca01  test    rdx, rdx
0x14003ca04  cmovnz  rcx, rax
0x14003ca08  mov     [rcx], si
0x14003ca0b  lea     r8, __ImageBase
0x14003ca12  mov     edx, 3
0x14003ca17  lea     rcx, [rsp+0BE0h+var_B90]
0x14003ca1c  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003ca21  test    eax, eax
0x14003ca23  js      short loc_14003CA6B
0x14003ca25  mov     rcx, [rsp+0BE0h+var_B90]
0x14003ca2a  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003ca2f  jz      short loc_14003CA6B
0x14003ca31  mov     rdx, rbx
0x14003ca34  lea     rax, [rbp+0AE0h+pReportInformation.wzApplicationName]
0x14003ca3b  test    rdx, rdx
0x14003ca3e  jz      short loc_14003CA5D
0x14003ca40  movzx   r8d, word ptr [rcx]
0x14003ca44  test    r8w, r8w
0x14003ca48  jz      short loc_14003CA5D
0x14003ca4a  add     rcx, r14
0x14003ca4d  mov     [rax], r8w
0x14003ca51  add     rax, r14
0x14003ca54  dec     rdx
0x14003ca57  sub     rdi, 1
0x14003ca5b  jnz     short loc_14003CA3B
0x14003ca5d  lea     rcx, [rax-2]
0x14003ca61  test    rdi, rdi
0x14003ca64  cmovnz  rcx, rax
0x14003ca68  mov     [rcx], si
0x14003ca6b  lea     r8, __ImageBase
0x14003ca72  mov     edx, 0Ch
0x14003ca77  lea     rcx, [rsp+0BE0h+var_B90]
0x14003ca7c  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003ca81  test    eax, eax
0x14003ca83  js      short loc_14003CAD0
0x14003ca85  mov     rcx, [rsp+0BE0h+var_B90]
0x14003ca8a  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003ca8f  jz      short loc_14003CAD0
0x14003ca91  mov     r8, rbx
0x14003ca94  mov     edx, 200h
0x14003ca99  lea     rax, [rbp+0AE0h+pReportInformation.wzDescription]
0x14003caa0  test    r8, r8
0x14003caa3  jz      short loc_14003CAC2
0x14003caa5  movzx   r9d, word ptr [rcx]
0x14003caa9  test    r9w, r9w
0x14003caad  jz      short loc_14003CAC2
0x14003caaf  add     rcx, r14
0x14003cab2  mov     [rax], r9w
0x14003cab6  add     rax, r14
0x14003cab9  dec     r8
0x14003cabc  sub     rdx, 1
0x14003cac0  jnz     short loc_14003CAA0
0x14003cac2  lea     rcx, [rax-2]
0x14003cac6  test    rdx, rdx
0x14003cac9  cmovnz  rcx, rax
0x14003cacd  mov     [rcx], si
0x14003cad0  mov     rcx, rbx
0x14003cad3  lea     r9, aWindows; "windows"
0x14003cada  mov     edx, 40h ; '@'
0x14003cadf  mov     r8d, edx
0x14003cae2  lea     rax, [rbp+0AE0h+var_170]
0x14003cae9  test    rcx, rcx
0x14003caec  jz      short loc_14003CB0B
0x14003caee  movzx   r10d, word ptr [r9]
0x14003caf2  test    r10w, r10w
0x14003caf6  jz      short loc_14003CB0B
0x14003caf8  add     r9, r14
0x14003cafb  mov     [rax], r10w
0x14003caff  add     rax, r14
0x14003cb02  dec     rcx
0x14003cb05  sub     r8, 1
0x14003cb09  jnz     short loc_14003CAE9
0x14003cb0b  lea     rcx, [rax-2]
0x14003cb0f  test    r8, r8
0x14003cb12  cmovnz  rcx, rax
0x14003cb16  mov     [rcx], si
0x14003cb19  lea     rcx, aWindows8; "windows8"
0x14003cb20  lea     rax, [rbp+0AE0h+var_F0]
0x14003cb27  test    rbx, rbx
0x14003cb2a  jz      short loc_14003CB49
0x14003cb2c  movzx   r8d, word ptr [rcx]
0x14003cb30  test    r8w, r8w
0x14003cb34  jz      short loc_14003CB49
0x14003cb36  add     rcx, r14
0x14003cb39  mov     [rax], r8w
0x14003cb3d  add     rax, r14
0x14003cb40  dec     rbx
0x14003cb43  sub     rdx, 1
0x14003cb47  jnz     short loc_14003CB27
0x14003cb49  lea     rcx, [rax-2]
0x14003cb4d  test    rdx, rdx
0x14003cb50  cmovnz  rcx, rax
0x14003cb54  mov     [rcx], si
0x14003cb57  lea     rcx, [r13+2B0h]
0x14003cb5e  mov     r8d, 0Fh
0x14003cb64  lea     rdx, aLivekerneleven; "LiveKernelEvent"
0x14003cb6b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003cb70  lea     r9, [rsp+0BE0h+phReportHandle]; phReportHandle
0x14003cb75  lea     r8, [rbp+0AE0h+pReportInformation]; pReportInformation
0x14003cb7c  mov     edx, 4; repType
0x14003cb81  lea     rcx, aLivekerneleven; "LiveKernelEvent"
0x14003cb88  call    cs:__imp_WerReportCreate
0x14003cb8f  nop     dword ptr [rax+rax+00h]
0x14003cb94  mov     edi, eax
0x14003cb96  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003cb9d  test    eax, eax
0x14003cb9f  js      loc_14003CF7F
0x14003cba5  cmp     [rsp+0BE0h+phReportHandle], rsi
0x14003cbaa  jz      loc_14003CF7F
0x14003cbb0  lea     rdx, [rbp+0AE0h+var_A40]; struct _BUGCHECK_INFORMATION *
0x14003cbb7  mov     rcx, r15; lpFileName
0x14003cbba  call    ?ExtractBugCheckInfo@CKernelReport@@CAJPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::ExtractBugCheckInfo(wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003cbbf  mov     edi, eax
0x14003cbc1  test    eax, eax
0x14003cbc3  jns     short loc_14003CBD6
0x14003cbc5  lea     rax, aExtractbugchec; "ExtractBugCheckInfo failed"
0x14003cbcc  mov     edx, 8F1h
0x14003cbd1  jmp     loc_14003CF8B
0x14003cbd6  mov     r8d, [r13+2DCh]
0x14003cbdd  mov     edx, [r13+2D8h]
0x14003cbe4  mov     rcx, [rsp+0BE0h+phReportHandle]
0x14003cbe9  call    cs:__imp_WerpSetTelemetryKernelParams
0x14003cbf0  nop     dword ptr [rax+rax+00h]
0x14003cbf5  mov     rcx, [rbp+0AE8h]; this
0x14003cbfc  lea     r8, aWerpsettelemet; "WerpSetTelemetryKernelParams failed"
0x14003cc03  mov     qword ptr [rsp+0BE0h+var_BB8], r8; int
0x14003cc08  mov     dword ptr [rsp+0BE0h+var_BC0], eax; char *
0x14003cc0c  lea     rsi, aCkernelreportS_0; "CKernelReport::SendLiveReport"
0x14003cc13  mov     r9, rsi; char *
0x14003cc16  lea     r14, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003cc1d  mov     r8, r14; unsigned int
0x14003cc20  mov     edx, 8F7h; void *
0x14003cc25  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003cc2a  lea     r8, [rbp+0AE0h+var_A40]; struct _BUGCHECK_INFORMATION *
0x14003cc31  lea     rdx, aLivekerneleven; "LiveKernelEvent"
0x14003cc38  mov     rcx, [rsp+0BE0h+phReportHandle]; void *
0x14003cc3d  call    ?AddBugCheckSignaturesToReport@CKernelReport@@CAJPEAXPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::AddBugCheckSignaturesToReport(void *,wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003cc42  mov     rcx, [rbp+0AE8h]; this
0x14003cc49  lea     rdx, aAddbugchecksig; "AddBugCheckSignaturesToReport failed"
0x14003cc50  mov     qword ptr [rsp+0BE0h+var_BB8], rdx; int
0x14003cc55  mov     dword ptr [rsp+0BE0h+var_BC0], eax; char *
0x14003cc59  mov     r9, rsi; char *
0x14003cc5c  mov     r8, r14; unsigned int
0x14003cc5f  mov     edx, 8FDh; void *
0x14003cc64  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003cc69  mov     edi, 40002h
0x14003cc6e  xor     r8d, r8d; wchar_t *
0x14003cc71  xor     edx, edx; wchar_t *
0x14003cc73  lea     rcx, [rbp+0AE0h+var_AD0]; this
  ... truncated ...
```
