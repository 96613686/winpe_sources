# WindowsPerformanceRecorder::CControlManager::CancelEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)

- ea: `0x180058e54`
- end: `0x180059053`
- name: `?CancelEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z`
- size: `511`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800236b0`
- `0x180032adc`
- `0x180058800`

## callees

- `0x18000829c`
- `0x18000a154`
- `0x18001a8c8`
- `0x18001d190`
- `0x18001d1bc`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x180037f3c`
- `0x180039214`
- `0x180045cb4`
- `0x18004b39c`
- `0x18004ece0`
- `0x180058e54`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180058f6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180058f6d`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180058ef8`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180058ef8`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::CancelEventSession(
        WindowsPerformanceRecorder::CControlManager *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        char a5)
{
  TRACEHANDLE *v6; // rsi
  __int64 v10; // r8
  int Error; // ebx
  const WCHAR *SessionName; // rax
  ULONG v14; // ebp
  WindowsPerformanceRecorder::Impl *FileName; // rax
  const unsigned __int16 *v16; // rdx
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // rax
  const struct _GUID *v19; // r8
  const char *v20; // rax
  const char *v21; // rax
  __int64 (__fastcall **v22)(void *); // [rsp+40h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+48h] [rbp-50h] BYREF

  v6 = (TRACEHANDLE *)(a3 + 112);
  if ( (int)WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(
              a1,
              (const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3) >= 0 )
    *v6 = *(_QWORD *)(*((_QWORD *)a1 + 49) + 8LL);
  if ( !*v6 )
    return 0;
  Error = 0;
  v22 = &off_18008EB00;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&WindowsPerformanceRecorderControlProvider_Context,
      (const EVENT_DESCRIPTOR *)Perf_ExternalCall_Begin,
      v10,
      1u,
      &v23);
  SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
  v14 = ControlTraceW(*v6, SessionName, *(PEVENT_TRACE_PROPERTIES *)(a3 + 8), 1u);
  WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&v22);
  if ( v14 )
    Error = ATL::AtlHresultFromWin32(v14);
  *v6 = 0;
  *(_OWORD *)(a3 + 120) = 0;
  *(_OWORD *)(a3 + 136) = 0;
  std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::clear(a3 + 152);
  if ( Error < 0
    || a4 == 2
    && (FileName = (WindowsPerformanceRecorder::Impl *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3),
        WindowsPerformanceRecorder::Impl::FileExists(FileName, v16))
    && (v17 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3),
        !DeleteFileW(v17))
    && (Error = ATL::AtlHresultFromLastError(), Error < 0) )
  {
    v18 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
    if ( a5 )
    {
      WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
        a1,
        (unsigned int)Error,
        2,
        &IID_IControlManager,
        v18);
      v20 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "CancelEventSession",
        (const char *)0x10AB,
        Error,
        "%ws",
        v20);
    }
    else
    {
      WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(a1, Error, v19, v18, a2, 0);
      v21 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        "CancelEventSession",
        (const char *)0x10B0,
        Error,
        "%ws: %ws",
        v21,
        a2);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180058e54  push    rbx
0x180058e56  push    rbp
0x180058e57  push    rsi
0x180058e58  push    rdi
0x180058e59  push    r12
0x180058e5b  push    r14
0x180058e5d  push    r15
0x180058e5f  sub     rsp, 60h
0x180058e63  mov     rax, cs:__security_cookie
0x180058e6a  xor     rax, rsp
0x180058e6d  mov     [rsp+98h+var_40], rax
0x180058e72  mov     r12, rdx
0x180058e75  lea     rsi, [r8+70h]
0x180058e79  mov     rdx, r8; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180058e7c  mov     r15d, r9d
0x180058e7f  mov     rdi, r8
0x180058e82  mov     r14, rcx
0x180058e85  call    ?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x180058e8a  test    eax, eax
0x180058e8c  js      short loc_180058E9C
0x180058e8e  mov     rax, [r14+188h]
0x180058e95  mov     rcx, [rax+8]
0x180058e99  mov     [rsi], rcx
0x180058e9c  cmp     qword ptr [rsi], 0
0x180058ea0  jnz     short loc_180058EA9
0x180058ea2  xor     eax, eax
0x180058ea4  jmp     loc_180059037
0x180058ea9  xor     ebx, ebx
0x180058eab  lea     rax, off_18008EB00
0x180058eb2  mov     [rsp+98h+var_58], rax
0x180058eb7  lea     ebp, [rbx+1]
0x180058eba  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, bpl
0x180058ec1  jz      short loc_180058EE3
0x180058ec3  lea     rax, [rsp+98h+var_50]
0x180058ec8  mov     r9d, ebp
0x180058ecb  lea     rdx, Perf_ExternalCall_Begin
0x180058ed2  mov     [rsp+98h+Format], rax
0x180058ed7  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x180058ede  call    McGenEventWrite_EventWriteTransfer
0x180058ee3  mov     rcx, rdi; this
0x180058ee6  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180058eeb  mov     r8, [rdi+8]; Properties
0x180058eef  mov     rdx, rax; InstanceName
0x180058ef2  mov     rcx, [rsi]; TraceHandle
0x180058ef5  mov     r9d, ebp; ControlCode
0x180058ef8  call    cs:__imp_ControlTraceW
0x180058efe  lea     rcx, [rsp+98h+var_58]
0x180058f03  mov     ebp, eax
0x180058f05  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x180058f0a  test    ebp, ebp
0x180058f0c  jz      short loc_180058F17
0x180058f0e  mov     ecx, ebp; unsigned int
0x180058f10  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180058f15  mov     ebx, eax
0x180058f17  xorps   xmm0, xmm0
0x180058f1a  mov     qword ptr [rsi], 0
0x180058f21  movups  xmmword ptr [rdi+78h], xmm0
0x180058f25  lea     rcx, [rdi+98h]
0x180058f2c  movups  xmmword ptr [rdi+88h], xmm0
0x180058f33  call    ?clear@?$vector@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@QEAAXXZ; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::clear(void)
0x180058f38  mov     esi, 2
0x180058f3d  test    ebx, ebx
0x180058f3f  js      short loc_180058F8A
0x180058f41  cmp     r15d, esi
0x180058f44  jnz     loc_180059035
0x180058f4a  mov     rcx, rdi; this
0x180058f4d  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x180058f52  mov     rcx, rax; this
0x180058f55  call    ?FileExists@Impl@WindowsPerformanceRecorder@@YA_NPEBG@Z; WindowsPerformanceRecorder::Impl::FileExists(ushort const *)
0x180058f5a  test    al, al
0x180058f5c  jz      loc_180059035
0x180058f62  mov     rcx, rdi; this
0x180058f65  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x180058f6a  mov     rcx, rax; lpFileName
0x180058f6d  call    cs:__imp_DeleteFileW
0x180058f73  test    eax, eax
0x180058f75  jnz     loc_180059035
0x180058f7b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180058f80  mov     ebx, eax
0x180058f82  test    eax, eax
0x180058f84  jns     loc_180059035
0x180058f8a  mov     rcx, rdi; this
0x180058f8d  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180058f92  cmp     [rsp+98h+arg_20], 0
0x180058f9a  mov     edx, ebx; int
0x180058f9c  mov     rcx, r14; this
0x180058f9f  jz      short loc_180058FE7
0x180058fa1  lea     r9, IID_IControlManager
0x180058fa8  mov     [rsp+98h+Format], rax
0x180058fad  mov     r8d, esi
0x180058fb0  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x180058fb5  mov     rcx, rdi; this
0x180058fb8  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180058fbd  mov     [rsp+98h+var_70], rax; char *
0x180058fc2  lea     rdx, aCanceleventses; "CancelEventSession"
0x180058fc9  lea     rax, aWs_0; "%ws"
0x180058fd0  mov     r9d, ebx; unsigned int
0x180058fd3  mov     r8d, 10ABh; char *
0x180058fd9  mov     [rsp+98h+Format], rax; Format
0x180058fde  mov     ecx, esi; this
0x180058fe0  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180058fe5  jmp     short loc_180059035
0x180058fe7  mov     r9, rax; unsigned __int16 *
0x180058fea  mov     [rsp+98h+var_70], 0; struct IControlErrorInfo *
0x180058ff3  mov     [rsp+98h+Format], r12; unsigned __int16 *
0x180058ff8  call    ?AddCollectorControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBG1PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(long,_GUID const &,ushort const *,ushort const *,IControlErrorInfo *)
0x180058ffd  mov     rcx, rdi; this
0x180059000  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180059005  mov     [rsp+98h+var_68], r12
0x18005900a  lea     rdx, aCanceleventses; "CancelEventSession"
0x180059011  mov     [rsp+98h+var_70], rax; char *
0x180059016  mov     r9d, ebx; unsigned int
0x180059019  lea     rax, aWsWs_4; "%ws: %ws"
0x180059020  mov     r8d, 10B0h; char *
0x180059026  mov     ecx, 3; this
0x18005902b  mov     [rsp+98h+Format], rax; Format
0x180059030  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180059035  mov     eax, ebx
0x180059037  mov     rcx, [rsp+98h+var_40]
0x18005903c  xor     rcx, rsp; StackCookie
0x18005903f  call    __security_check_cookie
0x180059044  add     rsp, 60h
0x180059048  pop     r15
0x18005904a  pop     r14
0x18005904c  pop     r12
0x18005904e  pop     rdi
0x18005904f  pop     rsi
0x180059050  pop     rbp
0x180059051  pop     rbx
0x180059052  retn
```
