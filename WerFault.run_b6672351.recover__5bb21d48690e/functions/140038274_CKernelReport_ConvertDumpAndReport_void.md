# CKernelReport::ConvertDumpAndReport(void)

- ea: `0x140038274`
- end: `0x140038757`
- name: `?ConvertDumpAndReport@CKernelReport@@QEAAJXZ`
- size: `1251`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x140036e5c`

## callees

- `0x140001150`
- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x1400372dc`
- `0x140038274`
- `0x14003b56c`
- `0x14003b5b4`
- `0x14003b784`
- `0x14003dd3c`
- `0x14003e690`
- `0x1400401fc`
- `0x14005f510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400386e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400386e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400383f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400383f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003850f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003854a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140038413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003850f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003854a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003871d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003871d`

## string_xrefs

- `0x140038522`: `CreateEvent failed`
- `0x140038436`: `CreateEvent succeeded for %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::ConvertDumpAndReport(CKernelReport *this)
{
  HANDLE MutexW; // r14
  char v3; // si
  CKernelReport *v4; // rcx
  signed int v5; // ebx
  const char *v6; // rax
  __int64 v7; // rdx
  signed int LastError; // eax
  wil::details *v10; // [rsp+20h] [rbp-E0h]
  wil::details *v11; // [rsp+20h] [rbp-E0h]
  char *v12; // [rsp+30h] [rbp-D0h]
  char *v13; // [rsp+30h] [rbp-D0h]
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  void *v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v22[24]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v23[40]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-10h]
  _WORD *v25; // [rsp+F8h] [rbp-8h]
  _WORD *v26; // [rsp+100h] [rbp+0h]
  _WORD v27[8]; // [rsp+108h] [rbp+8h] BYREF
  _WORD *v28; // [rsp+118h] [rbp+18h]
  _WORD *v29; // [rsp+120h] [rbp+20h]
  _WORD v30[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v31; // [rsp+138h] [rbp+38h]
  int v32; // [rsp+140h] [rbp+40h]
  __int64 v33; // [rsp+148h] [rbp+48h]
  _WORD *v34; // [rsp+150h] [rbp+50h]
  _WORD *v35; // [rsp+158h] [rbp+58h]
  _WORD v36[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v37[8192]; // [rsp+170h] [rbp+70h] BYREF
  _WORD *v38; // [rsp+2170h] [rbp+2070h]
  _WORD *v39; // [rsp+2178h] [rbp+2078h]
  _WORD v40[8]; // [rsp+2180h] [rbp+2080h] BYREF
  _WORD *v41; // [rsp+2190h] [rbp+2090h]
  _WORD *v42; // [rsp+2198h] [rbp+2098h]
  _WORD v43[8]; // [rsp+21A0h] [rbp+20A0h] BYREF
  _WORD *v44; // [rsp+21B0h] [rbp+20B0h]
  _WORD *v45; // [rsp+21B8h] [rbp+20B8h]
  _WORD v46[8]; // [rsp+21C0h] [rbp+20C0h] BYREF
  __int128 v47; // [rsp+21D0h] [rbp+20D0h]
  __int128 v48; // [rsp+21E0h] [rbp+20E0h]
  int v49; // [rsp+21F0h] [rbp+20F0h]
  __int64 v50; // [rsp+21F4h] [rbp+20F4h]
  __int64 v51; // [rsp+21FCh] [rbp+20FCh]
  __int64 v52; // [rsp+2204h] [rbp+2104h]
  __int64 v53; // [rsp+220Ch] [rbp+210Ch]
  _BYTE v54[32]; // [rsp+2220h] [rbp+2120h] BYREF
  __int64 *v55; // [rsp+2240h] [rbp+2140h]
  __int64 v56; // [rsp+2248h] [rbp+2148h]
  int *v57; // [rsp+2250h] [rbp+2150h]
  __int64 v58; // [rsp+2258h] [rbp+2158h]
  int *v59; // [rsp+2260h] [rbp+2160h]
  __int64 v60; // [rsp+2268h] [rbp+2168h]
  int *v61; // [rsp+2270h] [rbp+2170h]
  __int64 v62; // [rsp+2278h] [rbp+2178h]
  int *v63; // [rsp+2280h] [rbp+2180h]
  __int64 v64; // [rsp+2288h] [rbp+2188h]
  int *v65; // [rsp+2290h] [rbp+2190h]
  __int64 v66; // [rsp+2298h] [rbp+2198h]
  int *v67; // [rsp+22A0h] [rbp+21A0h]
  __int64 v68; // [rsp+22A8h] [rbp+21A8h]
  wil::details::in1diag4 *retaddr; // [rsp+22E8h] [rbp+21E8h]

  v21[0] = v22;
  v21[1] = v22;
  v22[0] = 0;
  v25 = v27;
  v26 = v27;
  v27[0] = 0;
  v28 = v30;
  v29 = v30;
  v30[0] = 0;
  v24 = 1;
  v31 = 5;
  v32 = 0;
  v34 = v36;
  v35 = v36;
  v36[0] = 0;
  v33 = 0;
  memset_0(v37, 0, sizeof(v37));
  v38 = v40;
  v39 = v40;
  v40[0] = 0;
  v41 = v43;
  v42 = v43;
  v43[0] = 0;
  v44 = v46;
  v45 = v46;
  v46[0] = 0;
  v47 = 0;
  v48 = 0;
  v49 = -1;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v23[0] = 0;
  MutexW = CreateMutexW(0, 1, L"Global\\WerKernelVerticalGeneratingDump");
  v20 = (__int64)MutexW;
  if ( (unsigned __int64)MutexW + 1 <= 1 || GetLastError() == 183 )
  {
    v3 = 0;
    LODWORD(v10) = GetLastError();
    wil::details::in1diag4::Log_Win32Msg(
      retaddr,
      (void *)0x427,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ConvertDumpAndReport",
      v10,
      (unsigned int)"CreateEvent failed",
      v12);
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
  }
  else
  {
    LODWORD(v10) = 0x80000000;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ConvertDumpAndReport",
      v10,
      (int)"CreateEvent succeeded for %ws",
      (const char *)L"Global\\WerKernelVerticalGeneratingDump");
    v3 = 1;
    v5 = CDumpProcessor::ProcessDump((CDumpProcessor *)v23, (struct KERNEL_QUEUED_REPORT *)v21);
    if ( v5 < 0 )
    {
      v6 = "ProcessDump failed";
      v7 = 1080;
LABEL_5:
      LODWORD(v11) = v5;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::ConvertDumpAndReport",
        v11,
        (int)v6,
        v13);
      goto LABEL_15;
    }
    *((_DWORD *)this + 182) = v49;
    *(_QWORD *)((char *)this + 732) = v50;
    v5 = CKernelReport::QueueKernelReport(v4, (const struct KERNEL_QUEUED_REPORT *)v21);
    if ( v5 < 0 )
    {
      v6 = "QueueKernelReport failed";
      v7 = 1094;
      goto LABEL_5;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl'::`2'::impl) )
      CKernelReport::ReportAllLiveReports(this);
    v5 = 0;
  }
LABEL_15:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl'::`2'::impl) )
    CKernelReport::ReportAllLiveReports(this);
  if ( (unsigned int)dword_14007E000 > 5
    && (qword_14007E010 & 0x400000000000LL) != 0
    && (qword_14007E018 & 0x400000000000LL) == qword_14007E018 )
  {
    v14 = HIDWORD(v53);
    v15 = v53;
    v16 = HIDWORD(v52);
    v17 = v52;
    v18 = HIDWORD(v51);
    v19 = v51;
    v20 = 0x1000000;
    v67 = &v14;
    v68 = 4;
    v65 = &v15;
    v66 = 4;
    v63 = &v16;
    v64 = 4;
    v61 = &v17;
    v62 = 4;
    v59 = &v18;
    v60 = 4;
    v57 = &v19;
    v58 = 4;
    v55 = &v20;
    v56 = 8;
    LODWORD(v11) = 9;
    tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, byte_14007338B, 0, 0, v11, v54);
  }
  if ( v3 )
    ReleaseMutex(MutexW);
  CDumpProcessor::~CDumpProcessor((CDumpProcessor *)v23);
  if ( v21[0] != v22 )
    operator delete(v21[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)MutexW + 1 > 1 )
    CloseHandle(MutexW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140038274  mov     [rsp-8+arg_8], rbx
0x140038279  mov     [rsp-8+arg_10], rsi
0x14003827e  push    rbp
0x14003827f  push    rdi
0x140038280  push    r12
0x140038282  push    r14
0x140038284  push    r15
0x140038286  lea     rbp, [rsp-21C0h]
0x14003828e  mov     eax, 22C0h
0x140038293  call    _alloca_probe
0x140038298  sub     rsp, rax
0x14003829b  mov     rax, cs:__security_cookie
0x1400382a2  xor     rax, rsp
0x1400382a5  mov     [rbp+21E0h+var_30], rax
0x1400382ac  mov     rdi, rcx
0x1400382af  lea     rax, [rsp+22E0h+var_2270]
0x1400382b4  mov     [rsp+22E0h+var_2280], rax
0x1400382b9  lea     rax, [rsp+22E0h+var_2270]
0x1400382be  mov     [rsp+22E0h+var_2278], rax
0x1400382c3  xor     r12d, r12d
0x1400382c6  mov     [rsp+22E0h+var_2270], r12w
0x1400382cc  lea     rax, [rbp+21E0h+var_21D8]
0x1400382d0  mov     [rbp+21E0h+var_21E8], rax
0x1400382d4  lea     rax, [rbp+21E0h+var_21D8]
0x1400382d8  mov     [rbp+21E0h+var_21E0], rax
0x1400382dc  mov     [rbp+21E0h+var_21D8], r12w
0x1400382e1  lea     rax, [rbp+21E0h+var_21B8]
0x1400382e5  mov     [rbp+21E0h+var_21C8], rax
0x1400382e9  lea     rax, [rbp+21E0h+var_21B8]
0x1400382ed  mov     [rbp+21E0h+var_21C0], rax
0x1400382f1  mov     [rbp+21E0h+var_21B8], r12w
0x1400382f6  mov     [rbp+21E0h+var_21F0], 1
0x1400382fe  mov     [rbp+21E0h+var_21A8], 5
0x140038306  mov     [rbp+21E0h+var_21A0], r12d
0x14003830a  lea     rax, [rbp+21E0h+var_2180]
0x14003830e  mov     [rbp+21E0h+var_2190], rax
0x140038312  lea     rax, [rbp+21E0h+var_2180]
0x140038316  mov     [rbp+21E0h+var_2188], rax
0x14003831a  mov     [rbp+21E0h+var_2180], r12w
0x14003831f  mov     [rbp+21E0h+var_2198], r12
0x140038323  xor     edx, edx; Val
0x140038325  mov     r8d, 2000h; Size
0x14003832b  lea     rcx, [rbp+21E0h+var_2170]; void *
0x14003832f  call    memset_0
0x140038334  lea     rax, [rbp+21E0h+var_160]
0x14003833b  mov     [rbp+21E0h+var_170], rax
0x140038342  lea     rax, [rbp+21E0h+var_160]
0x140038349  mov     [rbp+21E0h+var_168], rax
0x140038350  mov     [rbp+21E0h+var_160], r12w
0x140038358  lea     rax, [rbp+21E0h+var_140]
0x14003835f  mov     [rbp+21E0h+var_150], rax
0x140038366  lea     rax, [rbp+21E0h+var_140]
0x14003836d  mov     [rbp+21E0h+var_148], rax
0x140038374  mov     [rbp+21E0h+var_140], r12w
0x14003837c  lea     rax, [rbp+21E0h+var_120]
0x140038383  mov     [rbp+21E0h+var_130], rax
0x14003838a  lea     rax, [rbp+21E0h+var_120]
0x140038391  mov     [rbp+21E0h+var_128], rax
0x140038398  mov     [rbp+21E0h+var_120], r12w
0x1400383a0  xorps   xmm0, xmm0
0x1400383a3  movdqa  [rbp+21E0h+var_110], xmm0
0x1400383ab  xorps   xmm1, xmm1
0x1400383ae  movups  [rbp+21E0h+var_100], xmm1
0x1400383b5  mov     [rbp+21E0h+var_F0], 0FFFFFFFFh
0x1400383bf  mov     [rbp+21E0h+var_EC], r12
0x1400383c6  mov     [rbp+21E0h+var_E4], r12
0x1400383cd  mov     [rbp+21E0h+var_DC], r12
0x1400383d4  mov     [rbp+21E0h+var_D4], r12
0x1400383db  mov     [rbp+21E0h+var_2240], r12w
0x1400383e0  lea     rbx, aGlobalWerkerne_1; "Global\\WerKernelVerticalGeneratingDump"
0x1400383e7  mov     r8, rbx; lpName
0x1400383ea  lea     edx, [r12+1]; bInitialOwner
0x1400383ef  xor     ecx, ecx; lpMutexAttributes
0x1400383f1  call    cs:__imp_CreateMutexW
0x1400383f8  nop     dword ptr [rax+rax+00h]
0x1400383fd  mov     r14, rax
0x140038400  mov     [rsp+22E0h+var_2288], rax
0x140038405  lea     r15, [rax+1]
0x140038409  cmp     r15, 1
0x14003840d  jbe     loc_14003850C
0x140038413  call    cs:__imp_GetLastError
0x14003841a  nop     dword ptr [rax+rax+00h]
0x14003841f  cmp     eax, 0B7h
0x140038424  jz      loc_14003850C
0x14003842a  mov     rcx, [rbp+21E8h]; this
0x140038431  mov     [rsp+22E0h+var_22B0], rbx; char *
0x140038436  lea     rax, aCreateeventSuc; "CreateEvent succeeded for %ws"
0x14003843d  mov     qword ptr [rsp+22E0h+var_22B8], rax; int
0x140038442  mov     dword ptr [rsp+22E0h+var_22C0], 80000000h; wil::details *
0x14003844a  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140038451  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038458  mov     edx, 42Dh; void *
0x14003845d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038462  mov     sil, 1
0x140038465  lea     rdx, [rsp+22E0h+var_2280]; struct KERNEL_QUEUED_REPORT *
0x14003846a  lea     rcx, [rbp+21E0h+var_2240]; this
0x14003846e  call    ?ProcessDump@CDumpProcessor@@QEAAJPEAUKERNEL_QUEUED_REPORT@@@Z; CDumpProcessor::ProcessDump(KERNEL_QUEUED_REPORT *)
0x140038473  mov     ebx, eax
0x140038475  test    eax, eax
0x140038477  jns     short loc_1400384AD
0x140038479  lea     rax, aProcessdumpFai; "ProcessDump failed"
0x140038480  mov     edx, 438h; void *
0x140038485  mov     qword ptr [rsp+22E0h+var_22B8], rax; int
0x14003848a  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038491  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140038498  mov     dword ptr [rsp+22E0h+var_22C0], ebx; wil::details *
0x14003849c  mov     rcx, [rbp+21E8h]; this
0x1400384a3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400384a8  jmp     loc_14003856F
0x1400384ad  mov     eax, [rbp+21E0h+var_F0]
0x1400384b3  mov     [rdi+2D8h], eax
0x1400384b9  mov     eax, dword ptr [rbp+21E0h+var_EC]
0x1400384bf  mov     [rdi+2DCh], eax
0x1400384c5  mov     eax, dword ptr [rbp+21E0h+var_EC+4]
0x1400384cb  mov     [rdi+2E0h], eax
0x1400384d1  lea     rdx, [rsp+22E0h+var_2280]; struct KERNEL_QUEUED_REPORT *
0x1400384d6  call    ?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z; CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)
0x1400384db  mov     ebx, eax
0x1400384dd  test    eax, eax
0x1400384df  jns     short loc_1400384EF
0x1400384e1  lea     rax, aQueuekernelrep; "QueueKernelReport failed"
0x1400384e8  mov     edx, 446h
0x1400384ed  jmp     short loc_140038485
0x1400384ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl(void)'::`2'::impl
0x1400384f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(void)
0x1400384fb  test    al, al
0x1400384fd  jnz     short loc_140038507
0x1400384ff  mov     rcx, rdi; this
0x140038502  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x140038507  mov     ebx, r12d
0x14003850a  jmp     short loc_14003856F
0x14003850c  mov     sil, r12b
0x14003850f  call    cs:__imp_GetLastError
0x140038516  nop     dword ptr [rax+rax+00h]
0x14003851b  mov     rcx, [rbp+21E8h]; this
0x140038522  lea     rdx, aCreateeventFai; "CreateEvent failed"
0x140038529  mov     qword ptr [rsp+22E0h+var_22B8], rdx; unsigned int
0x14003852e  mov     dword ptr [rsp+22E0h+var_22C0], eax; wil::details *
0x140038532  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140038539  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038540  mov     edx, 427h; void *
0x140038545  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003854a  call    cs:__imp_GetLastError
0x140038551  nop     dword ptr [rax+rax+00h]
0x140038556  mov     ebx, eax
0x140038558  test    eax, eax
0x14003855a  jle     short loc_140038565
0x14003855c  movzx   ebx, ax
0x14003855f  or      ebx, 80070000h
0x140038565  mov     eax, 80004005h
0x14003856a  test    ebx, ebx
0x14003856c  cmovns  ebx, eax
0x14003856f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl(void)'::`2'::impl
0x140038576  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(void)
0x14003857b  test    al, al
0x14003857d  jz      short loc_140038587
0x14003857f  mov     rcx, rdi; this
0x140038582  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x140038587  mov     eax, cs:dword_14007E000
0x14003858d  cmp     eax, 5
0x140038590  jbe     loc_1400386D9
0x140038596  mov     rcx, cs:qword_14007E018
0x14003859d  mov     rax, cs:qword_14007E010
0x1400385a4  mov     rdx, 400000000000h
0x1400385ae  test    rdx, rax
0x1400385b1  jz      loc_1400386D9
0x1400385b7  mov     rax, rcx
0x1400385ba  and     rax, rdx
0x1400385bd  cmp     rax, rcx
0x1400385c0  jnz     loc_1400386D9
0x1400385c6  mov     eax, dword ptr [rbp+21E0h+var_D4+4]
0x1400385cc  mov     [rsp+22E0h+var_22A0], eax
0x1400385d0  mov     eax, dword ptr [rbp+21E0h+var_D4]
0x1400385d6  mov     [rsp+22E0h+var_229C], eax
0x1400385da  mov     eax, dword ptr [rbp+21E0h+var_DC+4]
0x1400385e0  mov     [rsp+22E0h+var_2298], eax
0x1400385e4  mov     eax, dword ptr [rbp+21E0h+var_DC]
0x1400385ea  mov     [rsp+22E0h+var_2294], eax
0x1400385ee  mov     eax, dword ptr [rbp+21E0h+var_E4+4]
0x1400385f4  mov     [rsp+22E0h+var_2290], eax
0x1400385f8  mov     eax, dword ptr [rbp+21E0h+var_E4]
0x1400385fe  mov     [rsp+22E0h+var_228C], eax
0x140038602  mov     [rsp+22E0h+var_2288], 1000000h
0x14003860b  lea     rax, [rsp+22E0h+var_22A0]
0x140038610  mov     [rbp+21E0h+var_40], rax
0x140038617  mov     [rbp+21E0h+var_38], 4
0x140038622  lea     rax, [rsp+22E0h+var_229C]
0x140038627  mov     [rbp+21E0h+var_50], rax
0x14003862e  mov     [rbp+21E0h+var_48], 4
0x140038639  lea     rax, [rsp+22E0h+var_2298]
0x14003863e  mov     [rbp+21E0h+var_60], rax
0x140038645  mov     [rbp+21E0h+var_58], 4
0x140038650  lea     rax, [rsp+22E0h+var_2294]
0x140038655  mov     [rbp+21E0h+var_70], rax
0x14003865c  mov     [rbp+21E0h+var_68], 4
0x140038667  lea     rax, [rsp+22E0h+var_2290]
0x14003866c  mov     [rbp+21E0h+var_80], rax
0x140038673  mov     [rbp+21E0h+var_78], 4
0x14003867e  lea     rax, [rsp+22E0h+var_228C]
0x140038683  mov     [rbp+21E0h+var_90], rax
0x14003868a  mov     [rbp+21E0h+var_88], 4
0x140038695  lea     rax, [rsp+22E0h+var_2288]
0x14003869a  mov     [rbp+21E0h+var_A0], rax
0x1400386a1  mov     [rbp+21E0h+var_98], 8
0x1400386ac  lea     rax, [rbp+21E0h+var_C0]
0x1400386b3  mov     qword ptr [rsp+22E0h+var_22B8], rax
0x1400386b8  mov     dword ptr [rsp+22E0h+var_22C0], 9
0x1400386c0  xor     r9d, r9d
0x1400386c3  xor     r8d, r8d
0x1400386c6  lea     rdx, byte_14007338B
0x1400386cd  lea     rcx, dword_14007E000
0x1400386d4  call    _tlgWriteTransfer_EventWriteTransfer
0x1400386d9  test    sil, sil
0x1400386dc  jz      short loc_1400386EE
0x1400386de  mov     rcx, r14; hMutex
0x1400386e1  call    cs:__imp_ReleaseMutex
0x1400386e8  nop     dword ptr [rax+rax+00h]
0x1400386ed  nop
0x1400386ee  lea     rcx, [rbp+21E0h+var_2240]; this
0x1400386f2  call    ??1CDumpProcessor@@QEAA@XZ; CDumpProcessor::~CDumpProcessor(void)
0x1400386f7  nop
0x1400386f8  mov     rcx, [rsp+22E0h+var_2280]; void *
0x1400386fd  lea     rax, [rsp+22E0h+var_2270]
0x140038702  cmp     rcx, rax
0x140038705  jz      short loc_140038714
0x140038707  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003870e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140038713  nop
0x140038714  cmp     r15, 1
0x140038718  jbe     short loc_140038729
0x14003871a  mov     rcx, r14; hObject
0x14003871d  call    cs:__imp_CloseHandle
0x140038724  nop     dword ptr [rax+rax+00h]
0x140038729  mov     eax, ebx
0x14003872b  mov     rcx, [rbp+21E0h+var_30]
0x140038732  xor     rcx, rsp; StackCookie
0x140038735  call    __security_check_cookie
0x14003873a  lea     r11, [rsp+22E0h+var_20]
0x140038742  mov     rbx, [r11+38h]
0x140038746  mov     rsi, [r11+40h]
0x14003874a  mov     rsp, r11
0x14003874d  pop     r15
0x14003874f  pop     r14
0x140038751  pop     r12
0x140038753  pop     rdi
0x140038754  pop     rbp
0x140038755  retn
```
