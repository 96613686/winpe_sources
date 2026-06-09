# CKernelReport::ConvertDumpAndReport(void)

- ea: `0x140035d20`
- end: `0x1400361e1`
- name: `?ConvertDumpAndReport@CKernelReport@@QEAAJXZ`
- size: `1217`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x14003494c`

## callees

- `0x14000113c`
- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x140034d9c`
- `0x140035d20`
- `0x14003902c`
- `0x140039074`
- `0x140039230`
- `0x14003b47c`
- `0x14003bd9c`
- `0x14003d7d4`
- `0x14005b770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140036178`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140036178`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140035ea0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140035ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035fe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400361ae`

## string_xrefs

- `0x140035fbf`: `CreateEvent failed`
- `0x140035ed9`: `CreateEvent succeeded for %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  _WORD v22[32]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v23[40]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+100h] [rbp+0h]
  _WORD *v25; // [rsp+108h] [rbp+8h]
  _WORD *v26; // [rsp+110h] [rbp+10h]
  _WORD v27[8]; // [rsp+118h] [rbp+18h] BYREF
  _WORD *v28; // [rsp+128h] [rbp+28h]
  _WORD *v29; // [rsp+130h] [rbp+30h]
  _WORD v30[8]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v31; // [rsp+148h] [rbp+48h]
  int v32; // [rsp+150h] [rbp+50h]
  __int64 v33; // [rsp+158h] [rbp+58h]
  _WORD *v34; // [rsp+160h] [rbp+60h]
  _WORD *v35; // [rsp+168h] [rbp+68h]
  _WORD v36[8]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v37[8192]; // [rsp+180h] [rbp+80h] BYREF
  _WORD *v38; // [rsp+2180h] [rbp+2080h]
  _WORD *v39; // [rsp+2188h] [rbp+2088h]
  _WORD v40[8]; // [rsp+2190h] [rbp+2090h] BYREF
  _WORD *v41; // [rsp+21A0h] [rbp+20A0h]
  _WORD *v42; // [rsp+21A8h] [rbp+20A8h]
  _WORD v43[8]; // [rsp+21B0h] [rbp+20B0h] BYREF
  _WORD *v44; // [rsp+21C0h] [rbp+20C0h]
  _WORD *v45; // [rsp+21C8h] [rbp+20C8h]
  _WORD v46[8]; // [rsp+21D0h] [rbp+20D0h] BYREF
  __int128 v47; // [rsp+21E0h] [rbp+20E0h]
  __int128 v48; // [rsp+21F0h] [rbp+20F0h]
  int v49; // [rsp+2200h] [rbp+2100h]
  __int64 v50; // [rsp+2204h] [rbp+2104h]
  __int64 v51; // [rsp+220Ch] [rbp+210Ch]
  __int64 v52; // [rsp+2214h] [rbp+2114h]
  __int64 v53; // [rsp+221Ch] [rbp+211Ch]
  _BYTE v54[32]; // [rsp+2230h] [rbp+2130h] BYREF
  __int64 *v55; // [rsp+2250h] [rbp+2150h]
  __int64 v56; // [rsp+2258h] [rbp+2158h]
  int *v57; // [rsp+2260h] [rbp+2160h]
  __int64 v58; // [rsp+2268h] [rbp+2168h]
  int *v59; // [rsp+2270h] [rbp+2170h]
  __int64 v60; // [rsp+2278h] [rbp+2178h]
  int *v61; // [rsp+2280h] [rbp+2180h]
  __int64 v62; // [rsp+2288h] [rbp+2188h]
  int *v63; // [rsp+2290h] [rbp+2190h]
  __int64 v64; // [rsp+2298h] [rbp+2198h]
  int *v65; // [rsp+22A0h] [rbp+21A0h]
  __int64 v66; // [rsp+22A8h] [rbp+21A8h]
  int *v67; // [rsp+22B0h] [rbp+21B0h]
  __int64 v68; // [rsp+22B8h] [rbp+21B8h]
  wil::details::in1diag4 *retaddr; // [rsp+22F8h] [rbp+21F8h]

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
      (void *)0x433,
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
      (void *)0x439,
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
      v7 = 1092;
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
      v7 = 1106;
      goto LABEL_5;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl'::`2'::impl) )
      CKernelReport::ReportAllLiveReports(this);
    v5 = 0;
  }
LABEL_15:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl'::`2'::impl) )
    CKernelReport::ReportAllLiveReports(this);
  if ( (unsigned int)dword_14007A000 > 5
    && (qword_14007A010 & 0x400000000000LL) != 0
    && (qword_14007A018 & 0x400000000000LL) == qword_14007A018 )
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
    tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &unk_14006F3F3, 0, 0, 9, v54);
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
0x140035d20  mov     [rsp-8+arg_8], rbx
0x140035d25  mov     [rsp-8+arg_10], rsi
0x140035d2a  push    rbp
0x140035d2b  push    rdi
0x140035d2c  push    r12
0x140035d2e  push    r14
0x140035d30  push    r15
0x140035d32  lea     rbp, [rsp-21D0h]
0x140035d3a  mov     eax, 22D0h
0x140035d3f  call    _alloca_probe
0x140035d44  sub     rsp, rax
0x140035d47  mov     rax, cs:__security_cookie
0x140035d4e  xor     rax, rsp
0x140035d51  mov     [rbp+21F0h+var_30], rax
0x140035d58  mov     rdi, rcx
0x140035d5b  lea     rax, [rsp+22F0h+var_2280]
0x140035d60  mov     [rsp+22F0h+var_2290], rax
0x140035d65  lea     rax, [rsp+22F0h+var_2280]
0x140035d6a  mov     [rsp+22F0h+var_2288], rax
0x140035d6f  xor     r12d, r12d
0x140035d72  mov     [rsp+22F0h+var_2280], r12w
0x140035d78  lea     rax, [rbp+21F0h+var_21D8]
0x140035d7c  mov     [rbp+21F0h+var_21E8], rax
0x140035d80  lea     rax, [rbp+21F0h+var_21D8]
0x140035d84  mov     [rbp+21F0h+var_21E0], rax
0x140035d88  mov     [rbp+21F0h+var_21D8], r12w
0x140035d8d  lea     rax, [rbp+21F0h+var_21B8]
0x140035d91  mov     [rbp+21F0h+var_21C8], rax
0x140035d95  lea     rax, [rbp+21F0h+var_21B8]
0x140035d99  mov     [rbp+21F0h+var_21C0], rax
0x140035d9d  mov     [rbp+21F0h+var_21B8], r12w
0x140035da2  mov     [rbp+21F0h+var_21F0], 1
0x140035daa  mov     [rbp+21F0h+var_21A8], 5
0x140035db2  mov     [rbp+21F0h+var_21A0], r12d
0x140035db6  lea     rax, [rbp+21F0h+var_2180]
0x140035dba  mov     [rbp+21F0h+var_2190], rax
0x140035dbe  lea     rax, [rbp+21F0h+var_2180]
0x140035dc2  mov     [rbp+21F0h+var_2188], rax
0x140035dc6  mov     [rbp+21F0h+var_2180], r12w
0x140035dcb  mov     [rbp+21F0h+var_2198], r12
0x140035dcf  xor     edx, edx; Val
0x140035dd1  mov     r8d, 2000h; Size
0x140035dd7  lea     rcx, [rbp+21F0h+var_2170]; void *
0x140035dde  call    memset_0
0x140035de3  lea     rax, [rbp+21F0h+var_160]
0x140035dea  mov     [rbp+21F0h+var_170], rax
0x140035df1  lea     rax, [rbp+21F0h+var_160]
0x140035df8  mov     [rbp+21F0h+var_168], rax
0x140035dff  mov     [rbp+21F0h+var_160], r12w
0x140035e07  lea     rax, [rbp+21F0h+var_140]
0x140035e0e  mov     [rbp+21F0h+var_150], rax
0x140035e15  lea     rax, [rbp+21F0h+var_140]
0x140035e1c  mov     [rbp+21F0h+var_148], rax
0x140035e23  mov     [rbp+21F0h+var_140], r12w
0x140035e2b  lea     rax, [rbp+21F0h+var_120]
0x140035e32  mov     [rbp+21F0h+var_130], rax
0x140035e39  lea     rax, [rbp+21F0h+var_120]
0x140035e40  mov     [rbp+21F0h+var_128], rax
0x140035e47  mov     [rbp+21F0h+var_120], r12w
0x140035e4f  xorps   xmm0, xmm0
0x140035e52  movdqa  [rbp+21F0h+var_110], xmm0
0x140035e5a  xorps   xmm1, xmm1
0x140035e5d  movups  [rbp+21F0h+var_100], xmm1
0x140035e64  mov     [rbp+21F0h+var_F0], 0FFFFFFFFh
0x140035e6e  mov     [rbp+21F0h+var_EC], r12
0x140035e75  mov     [rbp+21F0h+var_E4], r12
0x140035e7c  mov     [rbp+21F0h+var_DC], r12
0x140035e83  mov     [rbp+21F0h+var_D4], r12
0x140035e8a  mov     [rbp+21F0h+var_2240], r12w
0x140035e8f  lea     rbx, aGlobalWerkerne_1; "Global\\WerKernelVerticalGeneratingDump"
0x140035e96  mov     r8, rbx; lpName
0x140035e99  lea     edx, [r12+1]; bInitialOwner
0x140035e9e  xor     ecx, ecx; lpMutexAttributes
0x140035ea0  call    cs:__imp_CreateMutexW
0x140035ea6  mov     r14, rax
0x140035ea9  mov     [rsp+22F0h+var_2298], rax
0x140035eae  lea     r15, [rax+1]
0x140035eb2  cmp     r15, 1
0x140035eb6  jbe     loc_140035FAF
0x140035ebc  call    cs:__imp_GetLastError
0x140035ec2  cmp     eax, 0B7h
0x140035ec7  jz      loc_140035FAF
0x140035ecd  mov     rcx, [rbp+21F8h]; this
0x140035ed4  mov     [rsp+22F0h+var_22C0], rbx; char *
0x140035ed9  lea     rax, aCreateeventSuc; "CreateEvent succeeded for %ws"
0x140035ee0  mov     qword ptr [rsp+22F0h+var_22C8], rax; int
0x140035ee5  mov     dword ptr [rsp+22F0h+var_22D0], 80000000h; wil::details *
0x140035eed  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140035ef4  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035efb  mov     edx, 439h; void *
0x140035f00  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140035f05  mov     sil, 1
0x140035f08  lea     rdx, [rsp+22F0h+var_2290]; struct KERNEL_QUEUED_REPORT *
0x140035f0d  lea     rcx, [rbp+21F0h+var_2240]; this
0x140035f11  call    ?ProcessDump@CDumpProcessor@@QEAAJPEAUKERNEL_QUEUED_REPORT@@@Z; CDumpProcessor::ProcessDump(KERNEL_QUEUED_REPORT *)
0x140035f16  mov     ebx, eax
0x140035f18  test    eax, eax
0x140035f1a  jns     short loc_140035F50
0x140035f1c  lea     rax, aProcessdumpFai; "ProcessDump failed"
0x140035f23  mov     edx, 444h; void *
0x140035f28  mov     qword ptr [rsp+22F0h+var_22C8], rax; int
0x140035f2d  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035f34  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140035f3b  mov     dword ptr [rsp+22F0h+var_22D0], ebx; wil::details *
0x140035f3f  mov     rcx, [rbp+21F8h]; this
0x140035f46  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140035f4b  jmp     loc_140036006
0x140035f50  mov     eax, [rbp+21F0h+var_F0]
0x140035f56  mov     [rdi+2D8h], eax
0x140035f5c  mov     eax, dword ptr [rbp+21F0h+var_EC]
0x140035f62  mov     [rdi+2DCh], eax
0x140035f68  mov     eax, dword ptr [rbp+21F0h+var_EC+4]
0x140035f6e  mov     [rdi+2E0h], eax
0x140035f74  lea     rdx, [rsp+22F0h+var_2290]; struct KERNEL_QUEUED_REPORT *
0x140035f79  call    ?QueueKernelReport@CKernelReport@@AEAAJPEBUKERNEL_QUEUED_REPORT@@@Z; CKernelReport::QueueKernelReport(KERNEL_QUEUED_REPORT const *)
0x140035f7e  mov     ebx, eax
0x140035f80  test    eax, eax
0x140035f82  jns     short loc_140035F92
0x140035f84  lea     rax, aQueuekernelrep; "QueueKernelReport failed"
0x140035f8b  mov     edx, 452h
0x140035f90  jmp     short loc_140035F28
0x140035f92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl(void)'::`2'::impl
0x140035f99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(void)
0x140035f9e  test    al, al
0x140035fa0  jnz     short loc_140035FAA
0x140035fa2  mov     rcx, rdi; this
0x140035fa5  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x140035faa  mov     ebx, r12d
0x140035fad  jmp     short loc_140036006
0x140035faf  mov     sil, r12b
0x140035fb2  call    cs:__imp_GetLastError
0x140035fb8  mov     rcx, [rbp+21F8h]; this
0x140035fbf  lea     rdx, aCreateeventFai; "CreateEvent failed"
0x140035fc6  mov     qword ptr [rsp+22F0h+var_22C8], rdx; unsigned int
0x140035fcb  mov     dword ptr [rsp+22F0h+var_22D0], eax; wil::details *
0x140035fcf  lea     r9, aCkernelreportC_0; "CKernelReport::ConvertDumpAndReport"
0x140035fd6  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035fdd  mov     edx, 433h; void *
0x140035fe2  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140035fe7  call    cs:__imp_GetLastError
0x140035fed  mov     ebx, eax
0x140035fef  test    eax, eax
0x140035ff1  jle     short loc_140035FFC
0x140035ff3  movzx   ebx, ax
0x140035ff6  or      ebx, 80070000h
0x140035ffc  mov     eax, 80004005h
0x140036001  test    ebx, ebx
0x140036003  cmovns  ebx, eax
0x140036006  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::GetImpl(void)'::`2'::impl
0x14003600d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WerReportBootLKD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WerReportBootLKD>::__private_IsEnabled(void)
0x140036012  test    al, al
0x140036014  jz      short loc_14003601E
0x140036016  mov     rcx, rdi; this
0x140036019  call    ?ReportAllLiveReports@CKernelReport@@QEAAJXZ; CKernelReport::ReportAllLiveReports(void)
0x14003601e  mov     eax, cs:dword_14007A000
0x140036024  cmp     eax, 5
0x140036027  jbe     loc_140036170
0x14003602d  mov     rcx, cs:qword_14007A018
0x140036034  mov     rax, cs:qword_14007A010
0x14003603b  mov     rdx, 400000000000h
0x140036045  test    rdx, rax
0x140036048  jz      loc_140036170
0x14003604e  mov     rax, rcx
0x140036051  and     rax, rdx
0x140036054  cmp     rax, rcx
0x140036057  jnz     loc_140036170
0x14003605d  mov     eax, dword ptr [rbp+21F0h+var_D4+4]
0x140036063  mov     [rsp+22F0h+var_22B0], eax
0x140036067  mov     eax, dword ptr [rbp+21F0h+var_D4]
0x14003606d  mov     [rsp+22F0h+var_22AC], eax
0x140036071  mov     eax, dword ptr [rbp+21F0h+var_DC+4]
0x140036077  mov     [rsp+22F0h+var_22A8], eax
0x14003607b  mov     eax, dword ptr [rbp+21F0h+var_DC]
0x140036081  mov     [rsp+22F0h+var_22A4], eax
0x140036085  mov     eax, dword ptr [rbp+21F0h+var_E4+4]
0x14003608b  mov     [rsp+22F0h+var_22A0], eax
0x14003608f  mov     eax, dword ptr [rbp+21F0h+var_E4]
0x140036095  mov     [rsp+22F0h+var_229C], eax
0x140036099  mov     [rsp+22F0h+var_2298], 1000000h
0x1400360a2  lea     rax, [rsp+22F0h+var_22B0]
0x1400360a7  mov     [rbp+21F0h+var_40], rax
0x1400360ae  mov     [rbp+21F0h+var_38], 4
0x1400360b9  lea     rax, [rsp+22F0h+var_22AC]
0x1400360be  mov     [rbp+21F0h+var_50], rax
0x1400360c5  mov     [rbp+21F0h+var_48], 4
0x1400360d0  lea     rax, [rsp+22F0h+var_22A8]
0x1400360d5  mov     [rbp+21F0h+var_60], rax
0x1400360dc  mov     [rbp+21F0h+var_58], 4
0x1400360e7  lea     rax, [rsp+22F0h+var_22A4]
0x1400360ec  mov     [rbp+21F0h+var_70], rax
0x1400360f3  mov     [rbp+21F0h+var_68], 4
0x1400360fe  lea     rax, [rsp+22F0h+var_22A0]
0x140036103  mov     [rbp+21F0h+var_80], rax
0x14003610a  mov     [rbp+21F0h+var_78], 4
0x140036115  lea     rax, [rsp+22F0h+var_229C]
0x14003611a  mov     [rbp+21F0h+var_90], rax
0x140036121  mov     [rbp+21F0h+var_88], 4
0x14003612c  lea     rax, [rsp+22F0h+var_2298]
0x140036131  mov     [rbp+21F0h+var_A0], rax
0x140036138  mov     [rbp+21F0h+var_98], 8
0x140036143  lea     rax, [rbp+21F0h+var_C0]
0x14003614a  mov     qword ptr [rsp+22F0h+var_22C8], rax
0x14003614f  mov     dword ptr [rsp+22F0h+var_22D0], 9
0x140036157  xor     r9d, r9d
0x14003615a  xor     r8d, r8d
0x14003615d  lea     rdx, unk_14006F3F3
0x140036164  lea     rcx, dword_14007A000
0x14003616b  call    _tlgWriteTransfer_EventWriteTransfer
0x140036170  test    sil, sil
0x140036173  jz      short loc_14003617F
0x140036175  mov     rcx, r14; hMutex
0x140036178  call    cs:__imp_ReleaseMutex
0x14003617e  nop
0x14003617f  lea     rcx, [rbp+21F0h+var_2240]; this
0x140036183  call    ??1CDumpProcessor@@QEAA@XZ; CDumpProcessor::~CDumpProcessor(void)
0x140036188  nop
0x140036189  mov     rcx, [rsp+22F0h+var_2290]; void *
0x14003618e  lea     rax, [rsp+22F0h+var_2280]
0x140036193  cmp     rcx, rax
0x140036196  jz      short loc_1400361A5
0x140036198  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003619f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400361a4  nop
0x1400361a5  cmp     r15, 1
0x1400361a9  jbe     short loc_1400361B4
0x1400361ab  mov     rcx, r14; hObject
0x1400361ae  call    cs:__imp_CloseHandle
0x1400361b4  mov     eax, ebx
0x1400361b6  mov     rcx, [rbp+21F0h+var_30]
0x1400361bd  xor     rcx, rsp; StackCookie
0x1400361c0  call    __security_check_cookie
0x1400361c5  lea     r11, [rsp+22F0h+var_20]
0x1400361cd  mov     rbx, [r11+38h]
0x1400361d1  mov     rsi, [r11+40h]
0x1400361d5  mov     rsp, r11
0x1400361d8  pop     r15
0x1400361da  pop     r14
0x1400361dc  pop     r12
0x1400361de  pop     rdi
0x1400361df  pop     rbp
0x1400361e0  retn
```
