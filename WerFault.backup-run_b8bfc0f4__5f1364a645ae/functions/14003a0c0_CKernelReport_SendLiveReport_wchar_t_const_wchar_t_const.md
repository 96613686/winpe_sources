# CKernelReport::SendLiveReport(wchar_t const *,wchar_t const *)

- ea: `0x14003a0c0`
- end: `0x14003a8f5`
- name: `?SendLiveReport@CKernelReport@@AEAAJPEB_W0@Z`
- size: `2101`
- prototype: `__int64 __fastcall(CKernelReport *this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x140039c40`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140005430`
- `0x14000c8a0`
- `0x14000fa08`
- `0x140024414`
- `0x140034d9c`
- `0x140035090`
- `0x14003510c`
- `0x140036754`
- `0x140038790`
- `0x140038fd0`
- `0x14003a0c0`
- `0x14003b3ac`
- `0x14003f55c`
- `0x140042250`
- `0x140043d54`

## import_xrefs

- `wer!WerReportSubmit` at `0x14003a81d`
- `wer!WerReportSubmit` at `0x14003a81d`
- `wer!WerReportCreate` at `0x14003a4c9`
- `wer!WerReportCreate` at `0x14003a4c9`
- `wer!WerpAddFile` at `0x14003a606`
- `wer!WerpAddFile` at `0x14003a6a3`
- `wer!WerpAddFile` at `0x14003a7c1`
- `wer!WerpAddFile` at `0x14003a606`
- `wer!WerpAddFile` at `0x14003a6a3`
- `wer!WerpAddFile` at `0x14003a7c1`
- `wer!WerpSetTelemetryKernelParams` at `0x14003a524`
- `wer!WerpSetTelemetryKernelParams` at `0x14003a524`

## string_xrefs

- `0x14003a83f`: `WerCreateReport failed`
- `0x14003a683`: `sysdata.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::SendLiveReport(CKernelReport *this, const wchar_t *a2, const wchar_t *a3)
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
  unsigned int v41; // edi
  int Settings; // eax
  int SystemData; // eax
  __int64 v44; // rcx
  int v45; // edx
  unsigned int v46; // edi
  unsigned __int16 *v47; // r8
  __int64 v48; // rax
  unsigned __int16 *v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // r9
  int v52; // eax
  void *v53; // rcx
  int v54; // eax
  wil::details *v56; // [rsp+20h] [rbp-E0h]
  wil::details *v57; // [rsp+20h] [rbp-E0h]
  wil::details *v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-D8h]
  char *v60; // [rsp+30h] [rbp-D0h]
  char *v61; // [rsp+30h] [rbp-D0h]
  char v62[8]; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT phReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *v64; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v65; // [rsp+58h] [rbp-A8h]
  _WORD v66[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v67; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v68; // [rsp+78h] [rbp-88h]
  _WORD v69[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+90h] [rbp-70h] BYREF
  void *v71; // [rsp+98h] [rbp-68h]
  _WORD *v72; // [rsp+A0h] [rbp-60h]
  _WORD v73[8]; // [rsp+A8h] [rbp-58h] BYREF
  void *v74; // [rsp+B8h] [rbp-48h]
  _WORD *v75; // [rsp+C0h] [rbp-40h]
  _WORD v76[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h]
  int v78; // [rsp+E0h] [rbp-20h]
  void *v79[2]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD v80[8]; // [rsp+100h] [rbp+0h] BYREF
  int v81; // [rsp+110h] [rbp+10h] BYREF
  int v82; // [rsp+114h] [rbp+14h]
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
  v71 = v73;
  v72 = v73;
  v73[0] = 0;
  v74 = v76;
  v75 = v76;
  v76[0] = 0;
  v70 = 1;
  v77 = 5;
  v78 = 0;
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
  v81 = 1;
  v82 = 1;
  v62[0] = 0;
  phReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x9C4u);
  v67 = v69;
  v68 = v69;
  v69[0] = 0;
  v64 = v66;
  v65 = v66;
  v66[0] = 0;
  pReportInformation.dwSize = 2504;
  v6 = -2147024809;
  if ( !a2 )
  {
    CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)&v81);
LABEL_96:
    if ( v74 != v76 )
      operator delete(v74, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v71;
    v8 = v71 == v73;
    goto LABEL_99;
  }
  if ( UtilFileExists(a2) )
  {
    v9 = 2147483646;
    v10 = 128;
    if ( (int)UtilLoadString(&v64, 6, &_ImageBase) >= 0 )
    {
      v11 = (WCHAR *)v64;
      if ( v64 != v65 )
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
    if ( (int)UtilLoadString(&v64, 3, &_ImageBase) >= 0 )
    {
      v17 = (WCHAR *)v64;
      if ( v64 != v65 )
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
    if ( (int)UtilLoadString(&v64, 12, &_ImageBase) >= 0 )
    {
      v22 = (WCHAR *)v64;
      if ( v64 != v65 )
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      (char *)this + 688,
      L"LiveKernelEvent",
      15);
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
          (void *)0x89B,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendLiveReport",
          (const char *)v56,
          (int)"WerpSetTelemetryKernelParams failed",
          v60);
        LODWORD(v57) = CKernelReport::AddBugCheckSignaturesToReport(
                         phReportHandle,
                         L"LiveKernelEvent",
                         (struct _BUGCHECK_INFORMATION *)v95);
        wil::details::in1diag4::Log_IfFailedMsg(
          retaddr,
          (void *)0x8A1,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendLiveReport",
          (const char *)v57,
          (int)"AddBugCheckSignaturesToReport failed",
          v61);
        v41 = 262146;
        Settings = CLiveDumpSettings::LoadSettings((CLiveDumpSettings *)&v81, 0, 0);
        if ( Settings >= 0 && v82 )
          v41 = 262147;
        if ( Settings < 0 )
        {
          LODWORD(v58) = Settings;
          wil::details::in1diag4::_Log_Hr(
            retaddr,
            (void *)0x8AB,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::SendLiveReport",
            v58,
            v59);
        }
        v6 = WerpAddFile(phReportHandle, a2, 2, v41, 0, 0);
        if ( v6 >= 0 )
        {
          if ( *((_WORD *)this + 64) )
            goto LABEL_65;
          SystemData = CKernelReportDataCollection::GetSystemData(
                         (CKernelReportDataCollection *)v62,
                         (wchar_t *)this + 64,
                         0x104u);
          if ( SystemData < 0 )
          {
            LODWORD(v56) = SystemData;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x8BF,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
              "CKernelReport::SendLiveReport",
              v56,
              (int)"GetSystemData failed",
              v60);
          }
          if ( *((_WORD *)this + 64) )
          {
LABEL_65:
            v45 = WerpAddFile(phReportHandle, (char *)this + 128, 5, 262146, L"sysdata.xml", 0);
            if ( v45 < 0 )
            {
              LODWORD(v56) = v45;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x8D3,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                "CKernelReport::SendLiveReport",
                v56,
                (int)"WerAddFile failed",
                v60);
            }
          }
          if ( (int)CKernelReport::GetMatchingLiveDumpFile(v44, v95, a3, &v67) >= 0 && v67 != v68 )
          {
            v46 = 671088641;
            if ( (int)CCrashControlSettings::LoadSettings((CCrashControlSettings *)&v70) >= 0 && HIDWORD(v77) )
              v46 = 671088640;
            v79[0] = v80;
            v79[1] = v80;
            v80[0] = 0;
            if ( v67 )
            {
              v48 = -1;
              do
                ++v48;
              while ( *((_WORD *)v67 + v48) );
              v49 = (unsigned __int16 *)((char *)v67 + 2 * v48);
              while ( 1 )
              {
                v47 = v49;
                if ( v49 <= v67 )
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
            v52 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v79, L"full-%s", v47);
            v53 = 0;
            if ( v52 >= 0 )
              v53 = v79[0];
            v54 = WerpAddFile(
                    phReportHandle,
                    v67,
                    3,
                    v46,
                    v53,
                    L"full_dump=AskKernel;full_dump=AvailableKernel;full_dump=Any;fulldump=AskKernel;fulldump=AvailableKer"
                     "nel;fulldump=Any");
            if ( v54 < 0 )
            {
              LODWORD(v56) = v54;
              wil::details::in1diag4::Log_HrMsg(
                retaddr,
                (void *)0x8FE,
                (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                "CKernelReport::SendLiveReport",
                v56,
                (int)"WerpAddFile failed",
                v60);
            }
            if ( v79[0] != v80 )
              operator delete(v79[0], (const struct std::nothrow_t *)&std::nothrow);
          }
          v6 = WerReportSubmit(phReportHandle, WerConsentNotAsked, 0x804u, 0);
          if ( v6 >= 0 )
          {
            v6 = 0;
LABEL_91:
            if ( v64 != v66 )
              operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
            if ( v67 != v69 )
              operator delete(v67, (const struct std::nothrow_t *)&std::nothrow);
            CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)&v81);
            goto LABEL_96;
          }
          v39 = "WerSubmitReport failed";
          v40 = 2316;
        }
        else
        {
          v39 = "WerAddFile failed";
          v40 = 2230;
        }
      }
      else
      {
        v39 = "ExtractBugCheckInfo failed";
        v40 = 2197;
      }
    }
    else
    {
      v39 = "WerCreateReport failed";
      v40 = 2189;
    }
    LODWORD(v56) = v6;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v40,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendLiveReport",
      v56,
      (int)v39,
      v60);
    goto LABEL_91;
  }
  LODWORD(v56) = -2147024809;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x85A,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendLiveReport",
    v56,
    (int)"File does not exist: %ws",
    (const char *)a2);
  if ( v64 != v66 )
    operator delete(v64, (const struct std::nothrow_t *)&std::nothrow);
  if ( v67 != v69 )
    operator delete(v67, (const struct std::nothrow_t *)&std::nothrow);
  CLiveDumpSettings::~CLiveDumpSettings((CLiveDumpSettings *)&v81);
  if ( v74 != v76 )
    operator delete(v74, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v71;
  v8 = v71 == v73;
LABEL_99:
  if ( !v8 )
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003a0c0  push    rbp
0x14003a0c2  push    rbx
0x14003a0c3  push    rsi
0x14003a0c4  push    rdi
0x14003a0c5  push    r12
0x14003a0c7  push    r13
0x14003a0c9  push    r15
0x14003a0cb  lea     rbp, [rsp-0AB0h]
0x14003a0d3  sub     rsp, 0BB0h
0x14003a0da  mov     rax, cs:__security_cookie
0x14003a0e1  xor     rax, rsp
0x14003a0e4  mov     [rbp+0AE0h+var_40], rax
0x14003a0eb  mov     r12, r8
0x14003a0ee  mov     r15, rdx
0x14003a0f1  mov     r13, rcx
0x14003a0f4  xorps   xmm0, xmm0
0x14003a0f7  xor     eax, eax
0x14003a0f9  movups  [rbp+0AE0h+var_A40], xmm0
0x14003a100  movups  [rbp+0AE0h+var_A30], xmm0
0x14003a107  mov     [rbp+0AE0h+var_A20], rax
0x14003a10e  lea     rax, [rbp+0AE0h+var_B38]
0x14003a112  mov     [rbp+0AE0h+var_B48], rax
0x14003a116  lea     rax, [rbp+0AE0h+var_B38]
0x14003a11a  mov     [rbp+0AE0h+var_B40], rax
0x14003a11e  xor     esi, esi
0x14003a120  mov     [rbp+0AE0h+var_B38], si
0x14003a124  lea     rax, [rbp+0AE0h+var_B18]
0x14003a128  mov     [rbp+0AE0h+var_B28], rax
0x14003a12c  lea     rax, [rbp+0AE0h+var_B18]
0x14003a130  mov     [rbp+0AE0h+var_B20], rax
0x14003a134  mov     [rbp+0AE0h+var_B18], si
0x14003a138  mov     [rbp+0AE0h+var_B50], 1
0x14003a140  mov     [rbp+0AE0h+var_B08], 5
0x14003a148  mov     [rbp+0AE0h+var_B00], esi
0x14003a14b  lea     rax, [rbp+0AE0h+var_AB8]
0x14003a14f  mov     [rbp+0AE0h+var_AC8], rax
0x14003a153  lea     rax, [rbp+0AE0h+var_AB8]
0x14003a157  mov     [rbp+0AE0h+var_AC0], rax
0x14003a15b  mov     [rbp+0AE0h+var_AB8], si
0x14003a15f  lea     rax, [rbp+0AE0h+var_A98]
0x14003a163  mov     [rbp+0AE0h+var_AA8], rax
0x14003a167  lea     rax, [rbp+0AE0h+var_A98]
0x14003a16b  mov     [rbp+0AE0h+var_AA0], rax
0x14003a16f  mov     [rbp+0AE0h+var_A98], si
0x14003a173  lea     rax, [rbp+0AE0h+var_A78]
0x14003a177  mov     [rbp+0AE0h+var_A88], rax
0x14003a17b  lea     rax, [rbp+0AE0h+var_A78]
0x14003a17f  mov     [rbp+0AE0h+var_A80], rax
0x14003a183  mov     [rbp+0AE0h+var_A78], si
0x14003a187  lea     rax, [rbp+0AE0h+var_A58]
0x14003a18e  mov     [rbp+0AE0h+var_A68], rax
0x14003a192  lea     rax, [rbp+0AE0h+var_A58]
0x14003a199  mov     [rbp+0AE0h+var_A60], rax
0x14003a1a0  mov     [rbp+0AE0h+var_A58], si
0x14003a1a7  mov     [rbp+0AE0h+var_AD0], 1
0x14003a1ae  mov     [rbp+0AE0h+var_ACC], 1
0x14003a1b5  mov     [rsp+0BE0h+var_BA0], sil
0x14003a1ba  mov     [rsp+0BE0h+phReportHandle], rsi
0x14003a1bf  xor     edx, edx; Val
0x14003a1c1  mov     r8d, 9C4h; Size
0x14003a1c7  lea     rcx, [rbp+0AE0h+pReportInformation+4]; void *
0x14003a1ce  call    memset_0
0x14003a1d3  lea     rax, [rbp+0AE0h+var_B60]
0x14003a1d7  mov     [rsp+0BE0h+var_B70], rax
0x14003a1dc  lea     rax, [rbp+0AE0h+var_B60]
0x14003a1e0  mov     [rsp+0BE0h+var_B68], rax
0x14003a1e5  mov     [rbp+0AE0h+var_B60], si
0x14003a1e9  lea     rax, [rsp+0BE0h+var_B80]
0x14003a1ee  mov     [rsp+0BE0h+var_B90], rax
0x14003a1f3  lea     rax, [rsp+0BE0h+var_B80]
0x14003a1f8  mov     [rsp+0BE0h+var_B88], rax
0x14003a1fd  mov     [rsp+0BE0h+var_B80], si
0x14003a202  mov     [rbp+0AE0h+pReportInformation.dwSize], 9C8h
0x14003a20c  mov     edi, 80070057h
0x14003a211  test    r15, r15
0x14003a214  jnz     short loc_14003A22C
0x14003a216  lea     rcx, [rbp+0AE0h+var_AD0]; this
0x14003a21a  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003a21f  nop
0x14003a220  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003a227  jmp     loc_14003A8A8
0x14003a22c  mov     rcx, r15; wchar_t *
0x14003a22f  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x14003a234  test    al, al
0x14003a236  jnz     loc_14003A2D6
0x14003a23c  mov     rcx, [rbp+0AE8h]; this
0x14003a243  mov     [rsp+0BE0h+var_BB0], r15; char *
0x14003a248  lea     rax, aFileDoesNotExi; "File does not exist: %ws"
0x14003a24f  mov     qword ptr [rsp+0BE0h+var_BB8], rax; int
0x14003a254  mov     dword ptr [rsp+0BE0h+var_BC0], edi; wil::details *
0x14003a258  lea     r9, aCkernelreportS_0; "CKernelReport::SendLiveReport"
0x14003a25f  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003a266  mov     edx, 85Ah; void *
0x14003a26b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003a270  nop
0x14003a271  lea     rax, [rsp+0BE0h+var_B80]
0x14003a276  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003a27d  mov     rcx, [rsp+0BE0h+var_B90]; void *
0x14003a282  cmp     rcx, rax
0x14003a285  jz      short loc_14003A290
0x14003a287  mov     rdx, rbx; struct std::nothrow_t *
0x14003a28a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a28f  nop
0x14003a290  lea     rax, [rbp+0AE0h+var_B60]
0x14003a294  mov     rcx, [rsp+0BE0h+var_B70]; void *
0x14003a299  cmp     rcx, rax
0x14003a29c  jz      short loc_14003A2A7
0x14003a29e  mov     rdx, rbx; struct std::nothrow_t *
0x14003a2a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a2a6  nop
0x14003a2a7  lea     rcx, [rbp+0AE0h+var_AD0]; this
0x14003a2ab  call    ??1CLiveDumpSettings@@QEAA@XZ; CLiveDumpSettings::~CLiveDumpSettings(void)
0x14003a2b0  nop
0x14003a2b1  mov     rcx, [rbp+0AE0h+var_B28]; void *
0x14003a2b5  lea     rax, [rbp+0AE0h+var_B18]
0x14003a2b9  cmp     rcx, rax
0x14003a2bc  jz      short loc_14003A2C6
0x14003a2be  mov     rdx, rbx; struct std::nothrow_t *
0x14003a2c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003a2c6  mov     rcx, [rbp+0AE0h+var_B48]
0x14003a2ca  lea     rdx, [rbp+0AE0h+var_B38]
0x14003a2ce  cmp     rcx, rdx
0x14003a2d1  jmp     loc_14003A8C8
0x14003a2d6  lea     r8, __ImageBase
0x14003a2dd  mov     edx, 6
0x14003a2e2  lea     rcx, [rsp+0BE0h+var_B90]
0x14003a2e7  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003a2ec  mov     ebx, 7FFFFFFEh
0x14003a2f1  mov     edi, 80h
0x14003a2f6  test    eax, eax
0x14003a2f8  js      short loc_14003A344
0x14003a2fa  mov     rcx, [rsp+0BE0h+var_B90]
0x14003a2ff  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003a304  jz      short loc_14003A344
0x14003a306  mov     r8d, ebx
0x14003a309  mov     edx, edi
0x14003a30b  lea     rax, [rbp+0AE0h+pReportInformation.wzFriendlyEventName]
0x14003a312  test    r8, r8
0x14003a315  jz      short loc_14003A336
0x14003a317  movzx   r9d, word ptr [rcx]
0x14003a31b  test    r9w, r9w
0x14003a31f  jz      short loc_14003A336
0x14003a321  add     rcx, 2
0x14003a325  mov     [rax], r9w
0x14003a329  add     rax, 2
0x14003a32d  dec     r8
0x14003a330  sub     rdx, 1
0x14003a334  jnz     short loc_14003A312
0x14003a336  lea     rcx, [rax-2]
0x14003a33a  test    rdx, rdx
0x14003a33d  cmovnz  rcx, rax
0x14003a341  mov     [rcx], si
0x14003a344  lea     r8, __ImageBase
0x14003a34b  mov     edx, 3
0x14003a350  lea     rcx, [rsp+0BE0h+var_B90]
0x14003a355  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003a35a  test    eax, eax
0x14003a35c  js      short loc_14003A3A6
0x14003a35e  mov     rcx, [rsp+0BE0h+var_B90]
0x14003a363  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003a368  jz      short loc_14003A3A6
0x14003a36a  mov     rdx, rbx
0x14003a36d  lea     rax, [rbp+0AE0h+pReportInformation.wzApplicationName]
0x14003a374  test    rdx, rdx
0x14003a377  jz      short loc_14003A398
0x14003a379  movzx   r8d, word ptr [rcx]
0x14003a37d  test    r8w, r8w
0x14003a381  jz      short loc_14003A398
0x14003a383  add     rcx, 2
0x14003a387  mov     [rax], r8w
0x14003a38b  add     rax, 2
0x14003a38f  dec     rdx
0x14003a392  sub     rdi, 1
0x14003a396  jnz     short loc_14003A374
0x14003a398  lea     rcx, [rax-2]
0x14003a39c  test    rdi, rdi
0x14003a39f  cmovnz  rcx, rax
0x14003a3a3  mov     [rcx], si
0x14003a3a6  lea     r8, __ImageBase
0x14003a3ad  mov     edx, 0Ch
0x14003a3b2  lea     rcx, [rsp+0BE0h+var_B90]
0x14003a3b7  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003a3bc  test    eax, eax
0x14003a3be  js      short loc_14003A40D
0x14003a3c0  mov     rcx, [rsp+0BE0h+var_B90]
0x14003a3c5  cmp     rcx, [rsp+0BE0h+var_B88]
0x14003a3ca  jz      short loc_14003A40D
0x14003a3cc  mov     r8, rbx
0x14003a3cf  mov     edx, 200h
0x14003a3d4  lea     rax, [rbp+0AE0h+pReportInformation.wzDescription]
0x14003a3db  test    r8, r8
0x14003a3de  jz      short loc_14003A3FF
0x14003a3e0  movzx   r9d, word ptr [rcx]
0x14003a3e4  test    r9w, r9w
0x14003a3e8  jz      short loc_14003A3FF
0x14003a3ea  add     rcx, 2
0x14003a3ee  mov     [rax], r9w
0x14003a3f2  add     rax, 2
0x14003a3f6  dec     r8
0x14003a3f9  sub     rdx, 1
0x14003a3fd  jnz     short loc_14003A3DB
0x14003a3ff  lea     rcx, [rax-2]
0x14003a403  test    rdx, rdx
0x14003a406  cmovnz  rcx, rax
0x14003a40a  mov     [rcx], si
0x14003a40d  mov     rcx, rbx
0x14003a410  lea     r9, aWindows; "windows"
0x14003a417  mov     edx, 40h ; '@'
0x14003a41c  mov     r8d, edx
0x14003a41f  lea     rax, [rbp+0AE0h+var_170]
0x14003a426  test    rcx, rcx
0x14003a429  jz      short loc_14003A44A
0x14003a42b  movzx   r10d, word ptr [r9]
0x14003a42f  test    r10w, r10w
0x14003a433  jz      short loc_14003A44A
0x14003a435  add     r9, 2
0x14003a439  mov     [rax], r10w
0x14003a43d  add     rax, 2
0x14003a441  dec     rcx
0x14003a444  sub     r8, 1
0x14003a448  jnz     short loc_14003A426
0x14003a44a  lea     rcx, [rax-2]
0x14003a44e  test    r8, r8
0x14003a451  cmovnz  rcx, rax
0x14003a455  mov     [rcx], si
0x14003a458  lea     rcx, aWindows8; "windows8"
0x14003a45f  lea     rax, [rbp+0AE0h+var_F0]
0x14003a466  test    rbx, rbx
0x14003a469  jz      short loc_14003A48A
0x14003a46b  movzx   r8d, word ptr [rcx]
0x14003a46f  test    r8w, r8w
0x14003a473  jz      short loc_14003A48A
0x14003a475  add     rcx, 2
0x14003a479  mov     [rax], r8w
0x14003a47d  add     rax, 2
0x14003a481  dec     rbx
0x14003a484  sub     rdx, 1
0x14003a488  jnz     short loc_14003A466
0x14003a48a  lea     rcx, [rax-2]
0x14003a48e  test    rdx, rdx
0x14003a491  cmovnz  rcx, rax
0x14003a495  mov     [rcx], si
0x14003a498  lea     rcx, [r13+2B0h]
0x14003a49f  mov     r8d, 0Fh
0x14003a4a5  lea     rdx, aLivekerneleven; "LiveKernelEvent"
0x14003a4ac  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003a4b1  lea     r9, [rsp+0BE0h+phReportHandle]; phReportHandle
0x14003a4b6  lea     r8, [rbp+0AE0h+pReportInformation]; pReportInformation
0x14003a4bd  mov     edx, 4; repType
0x14003a4c2  lea     rcx, aLivekerneleven; "LiveKernelEvent"
0x14003a4c9  call    cs:__imp_WerReportCreate
0x14003a4cf  mov     edi, eax
0x14003a4d1  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14003a4d8  test    eax, eax
0x14003a4da  js      loc_14003A83F
0x14003a4e0  cmp     [rsp+0BE0h+phReportHandle], rsi
0x14003a4e5  jz      loc_14003A83F
0x14003a4eb  lea     rdx, [rbp+0AE0h+var_A40]; struct _BUGCHECK_INFORMATION *
0x14003a4f2  mov     rcx, r15; lpFileName
0x14003a4f5  call    ?ExtractBugCheckInfo@CKernelReport@@CAJPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::ExtractBugCheckInfo(wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003a4fa  mov     edi, eax
0x14003a4fc  test    eax, eax
0x14003a4fe  jns     short loc_14003A511
0x14003a500  lea     rax, aExtractbugchec; "ExtractBugCheckInfo failed"
0x14003a507  mov     edx, 895h
0x14003a50c  jmp     loc_14003A84B
0x14003a511  mov     r8d, [r13+2DCh]
0x14003a518  mov     edx, [r13+2D8h]
0x14003a51f  mov     rcx, [rsp+0BE0h+phReportHandle]
0x14003a524  call    cs:__imp_WerpSetTelemetryKernelParams
0x14003a52a  mov     rcx, [rbp+0AE8h]; this
0x14003a531  lea     r8, aWerpsettelemet; "WerpSetTelemetryKernelParams failed"
0x14003a538  mov     qword ptr [rsp+0BE0h+var_BB8], r8; int
0x14003a53d  mov     dword ptr [rsp+0BE0h+var_BC0], eax; char *
0x14003a541  lea     rsi, aCkernelreportS_0; "CKernelReport::SendLiveReport"
0x14003a548  mov     r9, rsi; char *
0x14003a54b  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003a552  mov     edx, 89Bh; void *
0x14003a557  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003a55c  lea     r8, [rbp+0AE0h+var_A40]; struct _BUGCHECK_INFORMATION *
0x14003a563  lea     rdx, aLivekerneleven; "LiveKernelEvent"
0x14003a56a  mov     rcx, [rsp+0BE0h+phReportHandle]; void *
0x14003a56f  call    ?AddBugCheckSignaturesToReport@CKernelReport@@CAJPEAXPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::AddBugCheckSignaturesToReport(void *,wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003a574  mov     rcx, [rbp+0AE8h]; this
0x14003a57b  lea     rdx, aAddbugchecksig; "AddBugCheckSignaturesToReport failed"
0x14003a582  mov     qword ptr [rsp+0BE0h+var_BB8], rdx; int
0x14003a587  mov     dword ptr [rsp+0BE0h+var_BC0], eax; char *
0x14003a58b  mov     r9, rsi; char *
0x14003a58e  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003a595  mov     edx, 8A1h; void *
0x14003a59a  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003a59f  mov     edi, 40002h
0x14003a5a4  xor     r8d, r8d; wchar_t *
0x14003a5a7  xor     edx, edx; wchar_t *
0x14003a5a9  lea     rcx, [rbp+0AE0h+var_AD0]; this
0x14003a5ad  call    ?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z; CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)
0x14003a5b2  test    eax, eax
0x14003a5b4  js      short loc_14003A5C0
0x14003a5b6  lea     ecx, [rdi+1]
0x14003a5b9  cmp     [rbp+0AE0h+var_ACC], 0
  ... truncated ...
```
