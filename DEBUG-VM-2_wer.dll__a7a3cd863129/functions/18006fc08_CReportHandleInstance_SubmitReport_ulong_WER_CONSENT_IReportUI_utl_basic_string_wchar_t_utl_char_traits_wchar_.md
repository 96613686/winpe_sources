# CReportHandleInstance::SubmitReport(ulong,_WER_CONSENT,IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,_WER_SUBMIT_RESULT *,_WERP_SUBMIT_RESULT *)

- ea: `0x18006fc08`
- end: `0x18007008e`
- name: `?SubmitReport@CReportHandleInstance@@QEAAJKW4_WER_CONSENT@@PEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAW4_WER_SUBMIT_RESULT@@PEAW4_WERP_SUBMIT_RESULT@@@Z`
- size: `1158`
- prototype: `__int64 __usercall@<rax>(CReportHandleInstance *this@<rcx>, __int64, enum _WER_SUBMIT_RESULT *, enum _WERP_SUBMIT_RESULT *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180060e50`
- `0x18006ad10`

## callees

- `0x180003a68`
- `0x180004bb4`
- `0x180006c34`
- `0x1800083c8`
- `0x18000d2c0`
- `0x18000dad0`
- `0x180010c3c`
- `0x18001565c`
- `0x18001fe24`
- `0x18002bba0`
- `0x18002c198`
- `0x18002cd50`
- `0x18002ece8`
- `0x18002f34c`
- `0x1800303dc`
- `0x1800318f4`
- `0x18003285c`
- `0x180045bdc`
- `0x1800654c0`
- `0x18006fac4`
- `0x18006fb34`
- `0x18006fc08`
- `0x180072114`
- `0x180073034`
- `0x180073970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fe8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fe8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006fe01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006fe01`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006fe5f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006fe5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fe80`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007006b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fe80`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007006b`

## pseudocode

```c
__int64 CReportHandleInstance::SubmitReport(
        CReportHandleInstance *this,
        enum _WER_FILE_TYPE a2,
        enum _WER_CONSENT a3,
        __int64 a4,
        __int64 a5,
        ...)
{
  enum _WER_SUBMIT_RESULT *v5; // r13
  __int64 v7; // rax
  unsigned int v8; // esi
  enum _WERP_SUBMIT_RESULT *v10; // r12
  int v11; // ebx
  int v12; // r15d
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int IsCurrentProcessInteractive; // eax
  unsigned int v17; // ecx
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  enum _WERP_SUBMIT_RESULT *v22; // rdx
  bool v23; // zf
  __int64 v24; // rdx
  __int64 v25; // r9
  void *v26; // rcx
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  __int64 v30; // [rsp+50h] [rbp-30h]
  __int64 v31[2]; // [rsp+58h] [rbp-28h] BYREF
  _WORD v32[12]; // [rsp+68h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+C0h] [rbp+40h] BYREF
  int v34; // [rsp+C8h] [rbp+48h]
  __int64 v35; // [rsp+D8h] [rbp+58h]
  enum _WER_SUBMIT_RESULT *v36; // [rsp+E8h] [rbp+68h] BYREF
  va_list va; // [rsp+E8h] [rbp+68h]
  enum _WERP_SUBMIT_RESULT *v38; // [rsp+F0h] [rbp+70h] BYREF
  va_list va1; // [rsp+F0h] [rbp+70h]
  va_list va2; // [rsp+F8h] [rbp+78h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v36 = va_arg(va1, enum _WER_SUBMIT_RESULT *);
  va_copy(va2, va1);
  v38 = va_arg(va2, enum _WERP_SUBMIT_RESULT *);
  v35 = a4;
  v5 = v36;
  v7 = *((_QWORD *)this + 1);
  v8 = a2;
  SystemTimeAsFileTime = 0;
  v34 = 0;
  v30 = v7;
  if ( v36 )
    *v36 = WerReportFailed;
  v10 = v38;
  if ( v38 )
    *(_DWORD *)v38 = 2;
  if ( _InterlockedExchange((volatile __int32 *)this + 20, 1) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
    v11 = -2147019873;
    goto LABEL_51;
  }
  v12 = 0;
  if ( (a2 & 0x200000) == 0 && !(unsigned int)CReport::IsReportLocked(*((CReport **)this + 1)) )
  {
    v11 = CReport::TryReportLock(*((CReport **)this + 1));
    if ( v11 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 15;
LABEL_49:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids, (unsigned int)v11);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    v34 = 1;
  }
  if ( a3 == WerConsentApproved )
  {
    if ( (v8 & 0x20000000) != 0 )
      CReport::MarkFilesAsApprovedByType(*((CReport **)this + 1), a2);
    else
      a3 = WerConsentNotAsked;
  }
  v11 = CReport::ValidateSignatureParams(*((CReport **)this + 1));
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_50;
    v15 = 16;
    goto LABEL_25;
  }
  CReport::SetDefaultDynamicParameters(*((CReport **)this + 1));
  v11 = CReport::SetConsentValue(*((CReport **)this + 1), a3);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_50;
    v15 = 17;
LABEL_25:
    WPP_SF_(*((_QWORD *)v13 + 2), v15, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
    goto LABEL_50;
  }
  v11 = CReport::InitializeSettings(*((CReport **)this + 1));
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 18;
      goto LABEL_49;
    }
LABEL_50:
    if ( v12 )
      goto LABEL_62;
    goto LABEL_51;
  }
  *(_DWORD *)(*((_QWORD *)this + 1) + 6616LL) = v8;
  if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    CReport::SetFileTime(*((CReport **)this + 1), &SystemTimeAsFileTime);
    if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) )
      v8 = v8 & 0x7FFFFFFC | 0x80000000;
    IsCurrentProcessInteractive = UtilIsCurrentProcessInteractive();
    v17 = v8 | 0x80000000;
    if ( IsCurrentProcessInteractive )
      v17 = v8;
    *(_DWORD *)(*((_QWORD *)this + 1) + 6616LL) = v17;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    v11 = CReportHandleInstance::InitiateReportManager(this);
    if ( v11 < 0 )
      goto LABEL_51;
  }
  ResetEvent(*((HANDLE *)this + 7));
  if ( UtilWaitForSingleObject(L"CancelEvent", *((void **)this + 8), 0) )
  {
    *((_DWORD *)this + 10) = GetCurrentThreadId();
    CReportHandleInstance::LogReportSubmitAsimovEvent(this);
    v11 = CReportManager::ReportProblem(*((CReportManager **)this + 4));
    CReportHandleInstance::DoFinalCallback(this, v11);
    if ( v11 >= 0 )
      goto LABEL_62;
    v12 = 1;
    if ( v11 != -2145681407 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 19;
        goto LABEL_49;
      }
    }
    goto LABEL_50;
  }
  SetEvent(*((HANDLE *)this + 7));
  v11 = -2145681407;
LABEL_51:
  v18 = *((_QWORD *)this + 1);
  v31[0] = (__int64)v32;
  v31[1] = (__int64)v32;
  v32[0] = 0;
  CReport::GetUniqueIdentifier(v18, v31);
  if ( (unsigned int)dword_1800D8000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 0x400000000000LL) )
  {
    v21 = *((_QWORD *)this + 1);
    v22 = *(enum _WERP_SUBMIT_RESULT **)(v21 + 5912);
    v23 = v22 == *(enum _WERP_SUBMIT_RESULT **)(v21 + 5920);
    LODWORD(v36) = v11;
    if ( v23 )
      v22 = 0;
    v29 = 0x1000000;
    v28 = v31[0];
    v38 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v21,
      (unsigned int)byte_1800C7761,
      v19,
      v20,
      (__int64)&v29,
      (__int64)va,
      (__int64)&v28,
      (__int64)va1);
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v24 = *((_QWORD *)this + 1);
    v25 = *(_QWORD *)(v24 + 5912);
    if ( v25 == *(_QWORD *)(v24 + 5920) )
      v25 = 0;
    WPP_SF_dSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids,
      v11,
      v31[0],
      v25);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v31);
LABEL_62:
  if ( v5 )
    CReportHandleInstance::MapSubmitResult(v5, v11, *(enum _WER_SUBMIT_RESULT *)(v30 + 9128));
  if ( v10 )
    CReportHandleInstance::MapInternalSubmitResult((CReportHandleInstance *)v13, v11, v10);
  if ( (int)(v11 + 0x80000000) < 0 || v11 == -2145681407 )
    v11 = 0;
  if ( v34 )
    CReport::ReleaseReportLock(*((CReport **)this + 1));
  v26 = (void *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)v26 + 1 > 1 )
    SetEvent(v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006fc08  mov     [rsp-38h+arg_10], rbx
0x18006fc0d  mov     [rsp-38h+arg_18], r9
0x18006fc12  push    rbp
0x18006fc13  push    rsi
0x18006fc14  push    rdi
0x18006fc15  push    r12
0x18006fc17  push    r13
0x18006fc19  push    r14
0x18006fc1b  push    r15
0x18006fc1d  mov     rbp, rsp
0x18006fc20  sub     rsp, 80h
0x18006fc27  mov     r13, [rbp+arg_28]
0x18006fc2b  mov     r14d, r8d
0x18006fc2e  mov     rax, [rcx+8]
0x18006fc32  mov     esi, edx
0x18006fc34  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006fc3c  mov     rdi, rcx
0x18006fc3f  mov     [rbp+arg_8], 0
0x18006fc46  mov     [rbp+var_30], rax
0x18006fc4a  test    r13, r13
0x18006fc4d  jz      short loc_18006FC57
0x18006fc4f  mov     dword ptr [r13+0], 4
0x18006fc57  mov     r12, [rbp+arg_30]
0x18006fc5b  test    r12, r12
0x18006fc5e  jz      short loc_18006FC68
0x18006fc60  mov     dword ptr [r12], 2
0x18006fc68  mov     eax, 1
0x18006fc6d  lea     r15, WPP_GLOBAL_Control
0x18006fc74  xchg    eax, [rcx+50h]
0x18006fc77  test    eax, eax
0x18006fc79  jz      short loc_18006FCAC
0x18006fc7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fc82  cmp     rcx, r15
0x18006fc85  jz      short loc_18006FCA2
0x18006fc87  test    byte ptr [rcx+1Ch], 1
0x18006fc8b  jz      short loc_18006FCA2
0x18006fc8d  mov     rcx, [rcx+10h]
0x18006fc91  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006fc98  mov     edx, 0Eh
0x18006fc9d  call    WPP_SF_
0x18006fca2  mov     ebx, 8007139Fh
0x18006fca7  jmp     loc_18006FF11
0x18006fcac  xor     r15d, r15d
0x18006fcaf  bt      esi, 15h
0x18006fcb3  jb      short loc_18006FD02
0x18006fcb5  mov     rcx, [rcx+8]; this
0x18006fcb9  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x18006fcbe  test    eax, eax
0x18006fcc0  jnz     short loc_18006FD02
0x18006fcc2  mov     rcx, [rdi+8]; this
0x18006fcc6  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x18006fccb  mov     ebx, eax
0x18006fccd  test    eax, eax
0x18006fccf  jns     short loc_18006FCFB
0x18006fcd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fcd8  lea     rax, WPP_GLOBAL_Control
0x18006fcdf  cmp     rcx, rax
0x18006fce2  jz      loc_18006FF01
0x18006fce8  test    byte ptr [rcx+1Ch], 1
0x18006fcec  jz      loc_18006FF01
0x18006fcf2  lea     edx, [r15+0Fh]
0x18006fcf6  jmp     loc_18006FEEE
0x18006fcfb  mov     [rbp+arg_8], 1
0x18006fd02  cmp     r14d, 2
0x18006fd06  jnz     short loc_18006FD1F
0x18006fd08  bt      esi, 1Dh
0x18006fd0c  jnb     short loc_18006FD19
0x18006fd0e  mov     rcx, [rdi+8]; this
0x18006fd12  call    ?MarkFilesAsApprovedByType@CReport@@QEAAXW4_WER_FILE_TYPE@@@Z; CReport::MarkFilesAsApprovedByType(_WER_FILE_TYPE)
0x18006fd17  jmp     short loc_18006FD1F
0x18006fd19  mov     r14d, 1
0x18006fd1f  mov     rcx, [rdi+8]; this
0x18006fd23  call    ?ValidateSignatureParams@CReport@@QEAAJXZ; CReport::ValidateSignatureParams(void)
0x18006fd28  mov     ebx, eax
0x18006fd2a  test    eax, eax
0x18006fd2c  jns     short loc_18006FD69
0x18006fd2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd35  lea     rax, WPP_GLOBAL_Control
0x18006fd3c  cmp     rcx, rax
0x18006fd3f  jz      loc_18006FF01
0x18006fd45  test    byte ptr [rcx+1Ch], 1
0x18006fd49  jz      loc_18006FF01
0x18006fd4f  mov     edx, 10h
0x18006fd54  mov     rcx, [rcx+10h]
0x18006fd58  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006fd5f  call    WPP_SF_
0x18006fd64  jmp     loc_18006FF01
0x18006fd69  mov     rcx, [rdi+8]; this
0x18006fd6d  call    ?SetDefaultDynamicParameters@CReport@@QEAAJXZ; CReport::SetDefaultDynamicParameters(void)
0x18006fd72  mov     rcx, [rdi+8]; this
0x18006fd76  mov     edx, r14d; enum _WER_CONSENT
0x18006fd79  call    ?SetConsentValue@CReport@@QEAAJW4_WER_CONSENT@@@Z; CReport::SetConsentValue(_WER_CONSENT)
0x18006fd7e  mov     ebx, eax
0x18006fd80  test    eax, eax
0x18006fd82  jns     short loc_18006FDAC
0x18006fd84  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd8b  lea     rax, WPP_GLOBAL_Control
0x18006fd92  cmp     rcx, rax
0x18006fd95  jz      loc_18006FF01
0x18006fd9b  test    byte ptr [rcx+1Ch], 1
0x18006fd9f  jz      loc_18006FF01
0x18006fda5  mov     edx, 11h
0x18006fdaa  jmp     short loc_18006FD54
0x18006fdac  mov     rcx, [rdi+8]; this
0x18006fdb0  call    ?InitializeSettings@CReport@@QEAAJXZ; CReport::InitializeSettings(void)
0x18006fdb5  mov     ebx, eax
0x18006fdb7  test    eax, eax
0x18006fdb9  jns     short loc_18006FDE6
0x18006fdbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fdc2  lea     rax, WPP_GLOBAL_Control
0x18006fdc9  cmp     rcx, rax
0x18006fdcc  jz      loc_18006FF01
0x18006fdd2  test    byte ptr [rcx+1Ch], 1
0x18006fdd6  jz      loc_18006FF01
0x18006fddc  mov     edx, 12h
0x18006fde1  jmp     loc_18006FEEE
0x18006fde6  mov     rax, [rdi+8]
0x18006fdea  mov     [rax+19D8h], esi
0x18006fdf0  mov     rax, [rdi+8]
0x18006fdf4  cmp     [rax+0B658h], r15d
0x18006fdfb  jnz     short loc_18006FE43
0x18006fdfd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006fe01  call    cs:__imp_GetSystemTimeAsFileTime
0x18006fe07  mov     rcx, [rdi+8]; this
0x18006fe0b  lea     rdx, [rbp+SystemTimeAsFileTime]; struct _FILETIME *
0x18006fe0f  call    ?SetFileTime@CReport@@QEAAXPEAU_FILETIME@@@Z; CReport::SetFileTime(_FILETIME *)
0x18006fe14  mov     rax, [rdi+8]
0x18006fe18  mov     ebx, 80000000h
0x18006fe1d  cmp     [rax+16F0h], r15d
0x18006fe24  jnz     short loc_18006FE2B
0x18006fe26  and     esi, 0FFFFFFFCh
0x18006fe29  or      esi, ebx
0x18006fe2b  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x18006fe30  mov     ecx, esi
0x18006fe32  or      ecx, ebx
0x18006fe34  test    eax, eax
0x18006fe36  mov     rax, [rdi+8]
0x18006fe3a  cmovnz  ecx, esi
0x18006fe3d  mov     [rax+19D8h], ecx
0x18006fe43  cmp     [rdi+20h], r15
0x18006fe47  jnz     short loc_18006FE5B
0x18006fe49  mov     rcx, rdi; this
0x18006fe4c  call    ?InitiateReportManager@CReportHandleInstance@@QEAAJXZ; CReportHandleInstance::InitiateReportManager(void)
0x18006fe51  mov     ebx, eax
0x18006fe53  test    eax, eax
0x18006fe55  js      loc_18006FF0A
0x18006fe5b  mov     rcx, [rdi+38h]; hEvent
0x18006fe5f  call    cs:__imp_ResetEvent
0x18006fe65  mov     rdx, [rdi+40h]; void *
0x18006fe69  lea     rcx, aCancelevent; "CancelEvent"
0x18006fe70  xor     r8d, r8d; unsigned int
0x18006fe73  call    ?UtilWaitForSingleObject@@YAKPEB_WPEAXK@Z; UtilWaitForSingleObject(wchar_t const *,void *,ulong)
0x18006fe78  test    eax, eax
0x18006fe7a  jnz     short loc_18006FE8D
0x18006fe7c  mov     rcx, [rdi+38h]; hEvent
0x18006fe80  call    cs:__imp_SetEvent
0x18006fe86  mov     ebx, 801B8001h
0x18006fe8b  jmp     short loc_18006FF0A
0x18006fe8d  call    cs:__imp_GetCurrentThreadId
0x18006fe93  mov     rcx, rdi; this
0x18006fe96  mov     [rdi+28h], eax
0x18006fe99  call    ?LogReportSubmitAsimovEvent@CReportHandleInstance@@AEAAXXZ; CReportHandleInstance::LogReportSubmitAsimovEvent(void)
0x18006fe9e  mov     r8, [rbp+arg_20]
0x18006fea2  mov     rdx, [rbp+arg_18]
0x18006fea6  mov     rcx, [rdi+20h]; this
0x18006feaa  call    ?ReportProblem@CReportManager@@QEAAJPEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ReportProblem(IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18006feaf  mov     edx, eax; int
0x18006feb1  mov     rcx, rdi; this
0x18006feb4  mov     ebx, eax
0x18006feb6  call    ?DoFinalCallback@CReportHandleInstance@@AEAAJJ@Z; CReportHandleInstance::DoFinalCallback(long)
0x18006febb  test    ebx, ebx
0x18006febd  jns     loc_18007000F
0x18006fec3  mov     r15d, 1
0x18006fec9  cmp     ebx, 801B8001h
0x18006fecf  jz      short loc_18006FF01
0x18006fed1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fed8  lea     rax, WPP_GLOBAL_Control
0x18006fedf  cmp     rcx, rax
0x18006fee2  jz      short loc_18006FF01
0x18006fee4  test    [rcx+1Ch], r15b
0x18006fee8  jz      short loc_18006FF01
0x18006feea  lea     edx, [r15+12h]
0x18006feee  mov     rcx, [rcx+10h]
0x18006fef2  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006fef9  mov     r9d, ebx
0x18006fefc  call    WPP_SF_d
0x18006ff01  test    r15d, r15d
0x18006ff04  jnz     loc_18007000F
0x18006ff0a  lea     r15, WPP_GLOBAL_Control
0x18006ff11  mov     rcx, [rdi+8]
0x18006ff15  lea     rax, [rbp+var_18]
0x18006ff19  mov     [rbp+var_28], rax
0x18006ff1d  lea     rdx, [rbp+var_28]
0x18006ff21  lea     rax, [rbp+var_18]
0x18006ff25  mov     [rbp+var_20], rax
0x18006ff29  xor     eax, eax
0x18006ff2b  mov     [rbp+var_18], ax
0x18006ff2f  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18006ff34  mov     eax, cs:dword_1800D8000
0x18006ff3a  cmp     eax, 5
0x18006ff3d  jbe     short loc_18006FFB8
0x18006ff3f  mov     rdx, 400000000000h
0x18006ff49  lea     rcx, dword_1800D8000
0x18006ff50  call    _tlgKeywordOn
0x18006ff55  test    al, al
0x18006ff57  jz      short loc_18006FFB8
0x18006ff59  mov     rcx, [rdi+8]
0x18006ff5d  xor     eax, eax
0x18006ff5f  mov     rdx, [rcx+1718h]
0x18006ff66  cmp     rdx, [rcx+1720h]
0x18006ff6d  mov     dword ptr [rbp+arg_28], ebx
0x18006ff70  cmovz   rdx, rax
0x18006ff74  mov     [rbp+var_38], 1000000h
0x18006ff7c  mov     rax, [rbp+var_28]
0x18006ff80  mov     [rbp+var_40], rax
0x18006ff84  lea     rax, [rbp+arg_30]
0x18006ff88  mov     [rsp+80h+var_48], rax
0x18006ff8d  lea     rax, [rbp+var_40]
0x18006ff91  mov     [rsp+80h+var_50], rax
0x18006ff96  lea     rax, [rbp+arg_28]
0x18006ff9a  mov     [rsp+80h+var_58], rax
0x18006ff9f  lea     rax, [rbp+var_38]
0x18006ffa3  mov     [rbp+arg_30], rdx
0x18006ffa7  lea     rdx, byte_1800C7761
0x18006ffae  mov     [rsp+80h+var_60], rax
0x18006ffb3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18006ffb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ffbf  cmp     rcx, r15
0x18006ffc2  jz      short loc_180070006
0x18006ffc4  test    byte ptr [rcx+1Ch], 4
0x18006ffc8  jz      short loc_180070006
0x18006ffca  mov     rdx, [rdi+8]
0x18006ffce  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006ffd5  mov     rcx, [rcx+10h]
0x18006ffd9  xor     eax, eax
0x18006ffdb  mov     r9, [rdx+1718h]
0x18006ffe2  cmp     r9, [rdx+1720h]
0x18006ffe9  lea     edx, [rax+14h]
0x18006ffec  cmovz   r9, rax
0x18006fff0  mov     rax, [rbp+var_28]
0x18006fff4  mov     [rsp+80h+var_58], r9
0x18006fff9  mov     r9d, ebx
0x18006fffc  mov     [rsp+80h+var_60], rax
0x180070001  call    WPP_SF_dSS
0x180070006  lea     rcx, [rbp+var_28]; void *
0x18007000a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007000f  test    r13, r13
0x180070012  jz      short loc_180070029
0x180070014  mov     r8, [rbp+var_30]
0x180070018  mov     edx, ebx; int
0x18007001a  mov     rcx, r13; enum _WER_SUBMIT_RESULT *
0x18007001d  mov     r8d, [r8+23A8h]; enum _WER_SUBMIT_RESULT
0x180070024  call    ?MapSubmitResult@CReportHandleInstance@@SAXPEAW4_WER_SUBMIT_RESULT@@JW42@@Z; CReportHandleInstance::MapSubmitResult(_WER_SUBMIT_RESULT *,long,_WER_SUBMIT_RESULT)
0x180070029  test    r12, r12
0x18007002c  jz      short loc_180070038
0x18007002e  mov     r8, r12; enum _WERP_SUBMIT_RESULT *
0x180070031  mov     edx, ebx; int
0x180070033  call    ?MapInternalSubmitResult@CReportHandleInstance@@QEBAJJPEAW4_WERP_SUBMIT_RESULT@@@Z; CReportHandleInstance::MapInternalSubmitResult(long,_WERP_SUBMIT_RESULT *)
0x180070038  mov     ecx, 80000000h
0x18007003d  lea     eax, [rbx+rcx]
0x180070040  test    ecx, eax
0x180070042  jnz     short loc_18007004C
0x180070044  cmp     ebx, 801B8001h
0x18007004a  jnz     short loc_18007004E
0x18007004c  xor     ebx, ebx
0x18007004e  cmp     [rbp+arg_8], 0
0x180070052  jz      short loc_18007005D
0x180070054  mov     rcx, [rdi+8]; this
0x180070058  call    ?ReleaseReportLock@CReport@@QEAAJXZ; CReport::ReleaseReportLock(void)
0x18007005d  mov     rcx, [rdi+38h]; hEvent
0x180070061  lea     rax, [rcx+1]
0x180070065  cmp     rax, 1
0x180070069  jbe     short loc_180070071
0x18007006b  call    cs:__imp_SetEvent
0x180070071  mov     eax, ebx
0x180070073  mov     rbx, [rsp+80h+arg_10]
0x18007007b  add     rsp, 80h
0x180070082  pop     r15
0x180070084  pop     r14
0x180070086  pop     r13
0x180070088  pop     r12
0x18007008a  pop     rdi
0x18007008b  pop     rsi
0x18007008c  pop     rbp
0x18007008d  retn
```
