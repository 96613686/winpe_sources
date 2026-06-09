# StandardCollectorService::SessionLifetimeMonitor::AddProcessToMonitor(uint)

- ea: `0x1800352ec`
- end: `0x180035505`
- name: `?AddProcessToMonitor@SessionLifetimeMonitor@StandardCollectorService@@QEAAJI@Z`
- size: `537`
- prototype: `int(StandardCollectorService::SessionLifetimeMonitor *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032470`
- `0x180034340`

## callees

- `0x1800183d0`
- `0x1800352ec`
- `0x18003d864`
- `0x180041834`
- `0x180041938`
- `0x180041a18`
- `0x180041c24`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180035463`
- `KERNEL32!SetEvent` at `0x180035463`
- `KERNEL32!GetCurrentProcessId` at `0x180035327`
- `KERNEL32!GetCurrentProcessId` at `0x180035327`
- `KERNEL32!LeaveCriticalSection` at `0x1800354ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800354cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800354e8`
- `KERNEL32!LeaveCriticalSection` at `0x1800354ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800354cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800354e8`
- `KERNEL32!EnterCriticalSection` at `0x180035310`
- `KERNEL32!EnterCriticalSection` at `0x180035310`
- `KERNEL32!CloseHandle` at `0x18003549d`
- `KERNEL32!CloseHandle` at `0x1800354c3`
- `KERNEL32!CloseHandle` at `0x1800354dc`
- `KERNEL32!CloseHandle` at `0x18003549d`
- `KERNEL32!CloseHandle` at `0x1800354c3`
- `KERNEL32!CloseHandle` at `0x1800354dc`
- `KERNEL32!GetLastError` at `0x18003546d`
- `KERNEL32!GetLastError` at `0x18003546d`

## string_xrefs

- `0x180035402`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180035443`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x18003548b`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x1800353fb`: `Failed to open session lifetime monitor process ID: %d (HRESULT: %#08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StandardCollectorService::SessionLifetimeMonitor::AddProcessToMonitor(
        StandardCollectorService::SessionLifetimeMonitor *this,
        DWORD a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int v5; // r14d
  void **v6; // r8
  const unsigned __int16 *v7; // r8
  const struct _GUID *v8; // rdx
  int v9; // r15d
  const unsigned __int16 *v10; // r8
  const struct _GUID *v11; // rdx
  DiagHubCommon::LogStream *v12; // rcx
  DWORD LastError; // eax
  DWORD v15; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _GUID *v17[2]; // [rsp+48h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-20h]

  v15 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( !a2 )
  {
    v5 = 1;
LABEL_14:
    LeaveCriticalSection(v4);
    return v5;
  }
  if ( a2 == GetCurrentProcessId() )
  {
    *(_OWORD *)hObject = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)hObject,
      -518979514,
      *((_WORD *)this + 77));
    v8 = (const struct _GUID *)L"<unknown error>";
    if ( hObject[0] )
      v8 = (const struct _GUID *)hObject[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_IStandardCollectorService, v8, v7);
    v5 = (unsigned int)hObject[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)hObject);
    goto LABEL_14;
  }
  hObject[0] = 0;
  v9 = Microsoft::DiagnosticsHub::UnifiedPlatform::OpenProcessForQuery(a2, (unsigned int)hObject, v6);
  if ( !hObject[0] )
  {
    *(_OWORD *)v17 = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)v17,
      -518979513,
      *((_WORD *)this + 77));
    v11 = (const struct _GUID *)L"<unknown error>";
    if ( v17[0] )
      v11 = v17[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_IStandardCollectorService, v11, v10);
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"Failed to open session lifetime monitor process ID: %d (HRESULT: %#08x)",
      a2,
      v9);
    v5 = (unsigned int)v17[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v17);
    goto LABEL_14;
  }
  try
  {
    std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::insert<0,0>(
      (char *)this + 40,
      v17,
      &v15);
    v12 = _logger;
  }
  catch ( std::bad_alloc )
  {
    CloseHandle(hObject[0]);
    LeaveCriticalSection(lpCriticalSection);
    return 2147942414LL;
  }
  DiagHubCommon::LogStream::Write(
    v12,
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
    L"Session lifetime will be based on process %d lifetime");
  if ( !*((_BYTE *)this + 152) )
  {
    if ( !SetEvent(*((HANDLE *)this + 13)) )
    {
      LastError = GetLastError();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Failed to signal lifetime monitor start. (ErrorCode: %#08x)",
        LastError);
      CloseHandle(hObject[0]);
      v5 = -2147418113;
      goto LABEL_14;
    }
    *((_BYTE *)this + 152) = 1;
  }
  CloseHandle(hObject[0]);
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x1800352ec  mov     [rsp+arg_10], rbx
0x1800352f1  push    rsi
0x1800352f2  push    r14
0x1800352f4  push    r15
0x1800352f6  sub     rsp, 60h
0x1800352fa  mov     r14d, edx
0x1800352fd  mov     rsi, rcx
0x180035300  mov     [rsp+78h+var_48], edx
0x180035304  lea     rbx, [rcx+38h]
0x180035308  mov     [rsp+78h+lpCriticalSection], rbx
0x18003530d  mov     rcx, rbx; lpCriticalSection
0x180035310  call    cs:__imp_EnterCriticalSection
0x180035316  nop
0x180035317  test    r14d, r14d
0x18003531a  jnz     short loc_180035327
0x18003531c  mov     r14d, 1
0x180035322  jmp     loc_1800354A9
0x180035327  call    cs:__imp_GetCurrentProcessId
0x18003532d  cmp     r14d, eax
0x180035330  jnz     short loc_180035385
0x180035332  xorps   xmm0, xmm0
0x180035335  movups  xmmword ptr [rsp+78h+hObject], xmm0
0x18003533a  movzx   r8d, word ptr [rsi+9Ah]; unsigned __int16
0x180035342  mov     edx, 0E1110046h; int
0x180035347  lea     rcx, [rsp+78h+hObject]; this
0x18003534c  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x180035351  nop
0x180035352  lea     rdx, aUnknownError; "<unknown error>"
0x180035359  mov     rax, [rsp+78h+hObject]
0x18003535e  test    rax, rax
0x180035361  cmovnz  rdx, rax; struct _GUID *
0x180035365  lea     rcx, IID_IStandardCollectorService; this
0x18003536c  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180035371  mov     r14d, dword ptr [rsp+78h+hObject+8]
0x180035376  lea     rcx, [rsp+78h+hObject]; this
0x18003537b  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180035380  jmp     loc_1800354A9
0x180035385  mov     [rsp+78h+hObject], 0
0x18003538e  lea     rdx, [rsp+78h+hObject]; unsigned int
0x180035393  mov     ecx, r14d; dwProcessId
0x180035396  call    ?OpenProcessForQuery@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJKPEAPEAX@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::OpenProcessForQuery(ulong,void * *)
0x18003539b  mov     r15d, eax
0x18003539e  cmp     [rsp+78h+hObject], 0
0x1800353a4  jnz     short loc_180035423
0x1800353a6  xorps   xmm0, xmm0
0x1800353a9  movups  xmmword ptr [rsp+78h+var_30], xmm0
0x1800353ae  movzx   r8d, word ptr [rsi+9Ah]; unsigned __int16
0x1800353b6  mov     edx, 0E1110047h; int
0x1800353bb  lea     rcx, [rsp+78h+var_30]; this
0x1800353c0  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x1800353c5  nop
0x1800353c6  lea     rdx, aUnknownError; "<unknown error>"
0x1800353cd  mov     rax, [rsp+78h+var_30]
0x1800353d2  test    rax, rax
0x1800353d5  cmovnz  rdx, rax; struct _GUID *
0x1800353d9  lea     rcx, IID_IStandardCollectorService; this
0x1800353e0  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x1800353e5  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800353ec  add     rcx, 0A8h; this
0x1800353f3  mov     [rsp+78h+var_58], r15d
0x1800353f8  mov     r9d, r14d
0x1800353fb  lea     r8, aFailedToOpenSe; "Failed to open session lifetime monitor"...
0x180035402  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180035409  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003540e  mov     r14d, dword ptr [rsp+78h+var_30+8]
0x180035413  lea     rcx, [rsp+78h+var_30]; this
0x180035418  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18003541d  nop
0x18003541e  jmp     loc_1800354A9
0x180035423  lea     rcx, [rsi+28h]
0x180035427  lea     r8, [rsp+78h+var_48]
0x18003542c  lea     rdx, [rsp+78h+var_30]
0x180035431  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@AEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::insert<0,0>(uint const &)
0x180035436  nop
0x180035437  mov     r9d, [rsp+78h+var_48]
0x18003543c  lea     r8, aSessionLifetim; "Session lifetime will be based on proce"...
0x180035443  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003544a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x180035451  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180035456  cmp     byte ptr [rsi+98h], 0
0x18003545d  jnz     short loc_1800354BE
0x18003545f  mov     rcx, [rsi+68h]; hEvent
0x180035463  call    cs:__imp_SetEvent
0x180035469  test    eax, eax
0x18003546b  jnz     short loc_1800354B7
0x18003546d  call    cs:__imp_GetLastError
0x180035473  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003547a  add     rcx, 0A8h; this
0x180035481  mov     r9d, eax
0x180035484  lea     r8, aFailedToSignal; "Failed to signal lifetime monitor start"...
0x18003548b  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180035492  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180035497  nop
0x180035498  mov     rcx, [rsp+78h+hObject]; hObject
0x18003549d  call    cs:__imp_CloseHandle
0x1800354a3  mov     r14d, 8000FFFFh
0x1800354a9  mov     rcx, rbx; lpCriticalSection
0x1800354ac  call    cs:__imp_LeaveCriticalSection
0x1800354b2  mov     eax, r14d
0x1800354b5  jmp     short loc_1800354F3
0x1800354b7  mov     byte ptr [rsi+98h], 1
0x1800354be  mov     rcx, [rsp+78h+hObject]; hObject
0x1800354c3  call    cs:__imp_CloseHandle
0x1800354c9  nop
0x1800354ca  mov     rcx, rbx; lpCriticalSection
0x1800354cd  call    cs:__imp_LeaveCriticalSection
0x1800354d3  xor     eax, eax
0x1800354d5  jmp     short loc_1800354F3
0x1800354d7  mov     rcx, [rsp+78h+hObject]; hObject
0x1800354dc  call    cs:__imp_CloseHandle
0x1800354e2  nop
0x1800354e3  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800354e8  call    cs:__imp_LeaveCriticalSection
0x1800354ee  mov     eax, 8007000Eh
0x1800354f3  mov     rbx, [rsp+78h+arg_10]
0x1800354fb  add     rsp, 60h
0x1800354ff  pop     r15
0x180035501  pop     r14
0x180035503  pop     rsi
0x180035504  retn
```
