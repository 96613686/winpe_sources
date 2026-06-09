# WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(ushort const *,ushort const *,ushort const *)

- ea: `0x18001d3d8`
- end: `0x18001d636`
- name: `?AdjustControlProgressHandler@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG00@Z`
- size: `606`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001e2b8`
- `0x1800236b0`
- `0x18005deb0`
- `0x180061780`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x18001d3d8`
- `0x18001e6e0`
- `0x1800234f0`
- `0x180033f30`
- `0x180045cb4`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004f964`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001d5dc`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001d5dc`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001d434`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001d434`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(
        WindowsPerformanceRecorder::CControlManager *this,
        const unsigned __int16 *a2,
        const char *a3,
        WCHAR *a4)
{
  const struct _GUID *v8; // r8
  TRACEHANDLE v9; // r12
  unsigned int Error; // eax
  __int64 v12; // rax
  ULONG v13; // eax
  __int64 v14; // rdi
  struct IControlErrorInfo *v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+30h] [rbp-D0h]
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+60h] [rbp-A0h] BYREF

  v19 = -2;
  memset_0(&Logfile.LoggerName, 0, 0x1B8u);
  Logfile.LogFileName = a4;
  v9 = OpenTraceW(&Logfile);
  if ( v9 == -1 )
  {
    Error = ATL::AtlHresultFromLastError();
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "AdjustControlProgressHandler",
      (const char *)0x9B9,
      Error,
      "%ws",
      a3);
    return ATL::AtlHresultFromLastError();
  }
  else
  {
    if ( Logfile.EventsLost )
    {
      WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
        this,
        -984064000,
        v8,
        (const unsigned __int16 *)a3,
        a2,
        0);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        "AdjustControlProgressHandler",
        (const char *)0x9C0,
        0xC5586000,
        "%ws: %ws",
        a3,
        a2);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v17,
      (char *)a4);
    v12 = std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,>(
            (char *)this + 432,
            v18,
            &v17);
    *(_QWORD *)(*(_QWORD *)v12 + 40LL) = Logfile.LogfileHeader.BuffersWritten;
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    if ( (Logfile.LogfileHeader.LogFileMode & 0x400) == 0
      && (Logfile.LogfileHeader.LogFileMode & 2) != 0
      && Logfile.LogfileHeader.MaximumFileSize )
    {
      v13 = (Logfile.LogfileHeader.MaximumFileSize << 20) / Logfile.LogfileHeader.BufferSize;
      v14 = v13;
      if ( Logfile.LogfileHeader.BuffersWritten > v13 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v17,
          (char *)a4);
        *(_QWORD *)(*(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,>(
                                 (char *)this + 432,
                                 v18,
                                 &v17)
                  + 40LL) = v14;
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v17);
        LODWORD(v16) = Logfile.LogfileHeader.MaximumFileSize;
        LODWORD(v15) = v14;
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)4,
          "AdjustControlProgressHandler",
          (const char *)0x9D2,
          0,
          "Override buffer count to %d per MaximumFileSize %d MB",
          (const char *)v15,
          v16);
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v17,
      (char *)a4);
    *((_QWORD *)this + 53) += *(_QWORD *)(*(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,>(
                                                       (char *)this + 432,
                                                       v18,
                                                       &v17)
                                        + 40LL);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    CloseTrace(v9);
    LODWORD(v15) = Logfile.LogfileHeader.BuffersWritten;
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)4,
      "AdjustControlProgressHandler",
      (const char *)0x9DA,
      0,
      "%d buffers written for %ws",
      (const char *)v15,
      a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18001d3d8  push    rbp
0x18001d3da  push    rbx
0x18001d3db  push    rsi
0x18001d3dc  push    rdi
0x18001d3dd  push    r12
0x18001d3df  push    r14
0x18001d3e1  push    r15
0x18001d3e3  lea     rbp, [rsp-130h]
0x18001d3eb  sub     rsp, 230h
0x18001d3f2  mov     [rsp+260h+var_208], 0FFFFFFFFFFFFFFFEh
0x18001d3fb  mov     rax, cs:__security_cookie
0x18001d402  xor     rax, rsp
0x18001d405  mov     [rbp+160h+var_40], rax
0x18001d40c  mov     rsi, r9
0x18001d40f  mov     rbx, r8
0x18001d412  mov     rdi, rdx
0x18001d415  mov     r14, rcx
0x18001d418  xor     edx, edx; Val
0x18001d41a  mov     r8d, 1B8h; Size
0x18001d420  lea     rcx, [rsp+260h+Logfile.LoggerName]; void *
0x18001d425  call    memset_0
0x18001d42a  mov     [rsp+260h+Logfile.LogFileName], rsi
0x18001d42f  lea     rcx, [rsp+260h+Logfile]; Logfile
0x18001d434  call    cs:__imp_OpenTraceW
0x18001d43a  mov     r12, rax
0x18001d43d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d441  jnz     short loc_18001D47D
0x18001d443  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001d448  mov     r9d, eax; unsigned int
0x18001d44b  mov     [rsp+260h+var_238], rbx; char *
0x18001d450  lea     rax, aWs_0; "%ws"
0x18001d457  mov     [rsp+260h+Format], rax; Format
0x18001d45c  mov     r8d, 9B9h; char *
0x18001d462  lea     rdx, aAdjustcontrolp; "AdjustControlProgressHandler"
0x18001d469  lea     ecx, [r12+3]; this
0x18001d46e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d473  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001d478  jmp     loc_18001D615
0x18001d47d  cmp     [rbp+160h+Logfile.EventsLost], 0
0x18001d484  jz      short loc_18001D4D8
0x18001d486  mov     [rsp+260h+var_238], 0; struct IControlErrorInfo *
0x18001d48f  mov     [rsp+260h+Format], rdi; unsigned __int16 *
0x18001d494  mov     r9, rbx; unsigned __int16 *
0x18001d497  mov     r15d, 0C5586000h
0x18001d49d  mov     edx, r15d; int
0x18001d4a0  mov     rcx, r14; this
0x18001d4a3  call    ?AddCollectorControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBG1PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(long,_GUID const &,ushort const *,ushort const *,IControlErrorInfo *)
0x18001d4a8  mov     [rsp+260h+var_230], rdi
0x18001d4ad  mov     [rsp+260h+var_238], rbx; char *
0x18001d4b2  lea     rax, aWsWs_4; "%ws: %ws"
0x18001d4b9  mov     [rsp+260h+Format], rax; Format
0x18001d4be  mov     r9d, r15d; unsigned int
0x18001d4c1  mov     r8d, 9C0h; char *
0x18001d4c7  lea     rdx, aAdjustcontrolp; "AdjustControlProgressHandler"
0x18001d4ce  mov     ecx, 3; this
0x18001d4d3  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d4d8  mov     rdx, rsi
0x18001d4db  lea     rcx, [rsp+260h+var_220]
0x18001d4e0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d4e5  nop
0x18001d4e6  lea     r15, [r14+1B0h]
0x18001d4ed  lea     r8, [rsp+260h+var_220]
0x18001d4f2  lea     rdx, [rsp+260h+var_218]
0x18001d4f7  mov     rcx, r15
0x18001d4fa  call    ??$_Try_emplace@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$V@?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_KU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@PEAX@std@@_N@1@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18001d4ff  mov     ecx, [rbp+160h+Logfile.LogfileHeader.BuffersWritten]
0x18001d502  mov     rax, [rax]
0x18001d505  mov     [rax+28h], rcx
0x18001d509  mov     rcx, [rsp+260h+var_220]
0x18001d50e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d512  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d517  test    [rbp+160h+Logfile.LogfileHeader.LogFileMode], 400h
0x18001d51e  jnz     short loc_18001D59D
0x18001d520  test    byte ptr [rbp+160h+Logfile.LogfileHeader.LogFileMode], 2
0x18001d524  jz      short loc_18001D59D
0x18001d526  mov     eax, [rbp+160h+Logfile.LogfileHeader.MaximumFileSize]
0x18001d529  test    eax, eax
0x18001d52b  jz      short loc_18001D59D
0x18001d52d  shl     eax, 14h
0x18001d530  xor     edx, edx
0x18001d532  div     [rbp+160h+Logfile.LogfileHeader.BufferSize]
0x18001d535  mov     edi, eax
0x18001d537  cmp     [rbp+160h+Logfile.LogfileHeader.BuffersWritten], eax
0x18001d53a  jbe     short loc_18001D59D
0x18001d53c  mov     rdx, rsi
0x18001d53f  lea     rcx, [rsp+260h+var_220]
0x18001d544  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d549  nop
0x18001d54a  lea     r8, [rsp+260h+var_220]
0x18001d54f  lea     rdx, [rsp+260h+var_218]
0x18001d554  mov     rcx, r15
0x18001d557  call    ??$_Try_emplace@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$V@?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_KU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@PEAX@std@@_N@1@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18001d55c  mov     rax, [rax]
0x18001d55f  mov     [rax+28h], rdi
0x18001d563  lea     rcx, [rsp+260h+var_220]; this
0x18001d568  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001d56d  mov     eax, [rbp+160h+Logfile.LogfileHeader.MaximumFileSize]
0x18001d570  mov     dword ptr [rsp+260h+var_230], eax
0x18001d574  mov     dword ptr [rsp+260h+var_238], edi; char *
0x18001d578  lea     rax, aOverrideBuffer; "Override buffer count to %d per Maximum"...
0x18001d57f  mov     [rsp+260h+Format], rax; Format
0x18001d584  xor     r9d, r9d; unsigned int
0x18001d587  mov     r8d, 9D2h; char *
0x18001d58d  lea     rdx, aAdjustcontrolp; "AdjustControlProgressHandler"
0x18001d594  lea     ecx, [r9+4]; this
0x18001d598  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d59d  mov     rdx, rsi
0x18001d5a0  lea     rcx, [rsp+260h+var_220]
0x18001d5a5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d5aa  nop
0x18001d5ab  lea     r8, [rsp+260h+var_220]
0x18001d5b0  lea     rdx, [rsp+260h+var_218]
0x18001d5b5  mov     rcx, r15
0x18001d5b8  call    ??$_Try_emplace@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$V@?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_KU?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@std@@PEAX@std@@_N@1@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64>::_Try_emplace<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18001d5bd  mov     rax, [rax]
0x18001d5c0  mov     rcx, [rax+28h]
0x18001d5c4  add     [r14+1A8h], rcx
0x18001d5cb  mov     rcx, [rsp+260h+var_220]
0x18001d5d0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d5d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d5d9  mov     rcx, r12; TraceHandle
0x18001d5dc  call    cs:__imp_CloseTrace
0x18001d5e2  mov     [rsp+260h+var_230], rbx
0x18001d5e7  mov     eax, [rbp+160h+Logfile.LogfileHeader.BuffersWritten]
0x18001d5ea  mov     dword ptr [rsp+260h+var_238], eax; char *
0x18001d5ee  lea     rax, aDBuffersWritte; "%d buffers written for %ws"
0x18001d5f5  mov     [rsp+260h+Format], rax; Format
0x18001d5fa  xor     r9d, r9d; unsigned int
0x18001d5fd  mov     r8d, 9DAh; char *
0x18001d603  lea     rdx, aAdjustcontrolp; "AdjustControlProgressHandler"
0x18001d60a  lea     ecx, [r9+4]; this
0x18001d60e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d613  xor     eax, eax
0x18001d615  mov     rcx, [rbp+160h+var_40]
0x18001d61c  xor     rcx, rsp; StackCookie
0x18001d61f  call    __security_check_cookie
0x18001d624  add     rsp, 230h
0x18001d62b  pop     r15
0x18001d62d  pop     r14
0x18001d62f  pop     r12
0x18001d631  pop     rdi
0x18001d632  pop     rsi
0x18001d633  pop     rbx
0x18001d634  pop     rbp
0x18001d635  retn
```
