# WindowsPerformanceRecorder::CControlManager::UpdateEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)

- ea: `0x18005ed4c`
- end: `0x18005f062`
- name: `?UpdateEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z`
- size: `790`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, int, char)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a1f0`
- `0x18005d1bc`
- `0x18005deb0`
- `0x18005f068`

## callees

- `0x18000829c`
- `0x18000a154`
- `0x18001a8c8`
- `0x18001d190`
- `0x18001d1bc`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x18002f230`
- `0x1800385d4`
- `0x180045cb4`
- `0x18004a170`
- `0x18004b494`
- `0x18004ece0`
- `0x18005ed4c`
- `0x180082d3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005eded`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005eded`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18005ee80`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18005ee80`

## string_xrefs

- `0x18005ef3b`: `UpdateEventSession`
- `0x18005f02c`: `UpdateEventSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        char a5)
{
  signed int RunningSystemGroupMask; // edi
  bool v10; // bp
  const unsigned __int16 *FileName; // rax
  __int64 v12; // r8
  __int64 v13; // r8
  const WCHAR *v14; // rax
  ULONG v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  const unsigned __int16 *v18; // r9
  const struct _GUID *v19; // r8
  const char *v20; // rax
  WindowsPerformanceRecorder::CControlManager *v21; // rcx
  const unsigned __int16 *SessionName; // rax
  const char *v23; // rax
  __int64 (__fastcall **v25)(void *); // [rsp+40h] [rbp-68h] BYREF
  __int64 v26; // [rsp+48h] [rbp-60h]
  _BYTE v27[8]; // [rsp+50h] [rbp-58h] BYREF
  int v28; // [rsp+58h] [rbp-50h]
  _BYTE v29[16]; // [rsp+68h] [rbp-40h] BYREF

  v26 = -2;
  WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(
    (WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v27,
    0xBu,
    *(_BYTE *)(a3 + 206));
  if ( v28 < 0 )
  {
    RunningSystemGroupMask = -984068079;
LABEL_24:
    SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
    WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
      a1,
      (unsigned int)RunningSystemGroupMask,
      2,
      &IID_IControlManager,
      SessionName);
    v23 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"UpdateEventSession",
      (const char *)0xD13,
      RunningSystemGroupMask,
      "%ws",
      v23);
    goto LABEL_25;
  }
  RunningSystemGroupMask = WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(
                             (WindowsPerformanceRecorder::CControlManager *)a1,
                             (const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
  if ( RunningSystemGroupMask < 0 )
    goto LABEL_24;
  *(_QWORD *)(a3 + 112) = *(_QWORD *)(*(_QWORD *)(a1 + 392) + 8LL);
  if ( a4 == 1 )
  {
    v10 = 0;
  }
  else
  {
    FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
    v10 = (unsigned int)_o__wcsicmp(v12 + *(unsigned int *)(v12 + 112), FileName) != 0;
  }
  memcpy_0(*(void **)(a1 + 392), *(const void **)(a3 + 8), **(unsigned int **)(a3 + 8));
  if ( !v10 || !a5 )
    *(_DWORD *)(*(_QWORD *)(a1 + 392) + 112LL) = 0;
  v25 = &off_18008EB00;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &WindowsPerformanceRecorderControlProvider_Context,
      Perf_ExternalCall_Begin,
      v13,
      1,
      v29);
  v14 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
  v15 = ControlTraceW(*(_QWORD *)(a3 + 112), v14, *(PEVENT_TRACE_PROPERTIES *)(a1 + 392), 2u);
  if ( v15 )
    RunningSystemGroupMask = ATL::AtlHresultFromWin32(v15);
  WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&v25);
  if ( RunningSystemGroupMask < 0 )
    goto LABEL_24;
  v16 = *(_QWORD *)(a3 + 16);
  if ( v16 )
  {
    v17 = *(_QWORD *)(a1 + 400);
    if ( v17 )
    {
      if ( ((*(_BYTE *)(v16 + 136) ^ *(_BYTE *)(v17 + 136)) & 2) != 0 )
      {
        v18 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
        WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
          (WindowsPerformanceRecorder::CControlManager *)a1,
          -984086979,
          v19,
          v18,
          a2,
          0);
        v20 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"UpdateEventSession",
          (const char *)0xCF2,
          0xC558063D,
          "%ws: %ws Running Properties->QpcDelta = %u",
          v20,
          a2,
          (*(_DWORD *)(*(_QWORD *)(a1 + 400) + 136LL) >> 1) & 1,
          v25,
          v26);
        *(_DWORD *)(*(_QWORD *)(a3 + 16) + 136LL) ^= (*(_DWORD *)(*(_QWORD *)(a1 + 400) + 136LL)
                                                    ^ *(_DWORD *)(*(_QWORD *)(a3 + 16) + 136LL))
                                                   & 2;
      }
    }
  }
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 48LL) = *(_DWORD *)(*(_QWORD *)(a1 + 392) + 48LL);
  *(_DWORD *)(*(_QWORD *)(a3 + 8) + 52LL) = *(_DWORD *)(*(_QWORD *)(a1 + 392) + 56LL);
  v21 = *(WindowsPerformanceRecorder::CControlManager **)(a3 + 8);
  *((_DWORD *)v21 + 14) = *(_DWORD *)(*(_QWORD *)(a1 + 392) + 56LL);
  if ( *(_DWORD *)a3 == 1 )
  {
    RunningSystemGroupMask = WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(
                               v21,
                               *(_QWORD *)(a3 + 112),
                               (struct _PERFINFO_GROUPMASK *)(a3 + 120));
    if ( RunningSystemGroupMask < 0 )
      goto LABEL_24;
  }
  if ( a5 )
  {
    if ( (unsigned int)(*(_DWORD *)a3 - 1) <= 1 )
    {
      RunningSystemGroupMask = WindowsPerformanceRecorder::CControlManager::UpdateEventProviders(
                                 (WindowsPerformanceRecorder::CControlManager *)a1,
                                 a2,
                                 (struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
      if ( RunningSystemGroupMask < 0 )
        goto LABEL_24;
    }
  }
LABEL_25:
  WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege((WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v27);
  return (unsigned int)RunningSystemGroupMask;
}

```

## disassembly

```asm
0x18005ed4c  push    rbx
0x18005ed4e  push    rbp
0x18005ed4f  push    rsi
0x18005ed50  push    rdi
0x18005ed51  push    r15
0x18005ed53  sub     rsp, 80h
0x18005ed5a  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFEh
0x18005ed63  mov     rax, cs:__security_cookie
0x18005ed6a  xor     rax, rsp
0x18005ed6d  mov     [rsp+0A8h+var_30], rax
0x18005ed72  mov     ebp, r9d
0x18005ed75  mov     rbx, r8
0x18005ed78  mov     r15, rdx
0x18005ed7b  mov     rsi, rcx
0x18005ed7e  mov     r8b, [r8+0CEh]; unsigned __int8
0x18005ed85  mov     edx, 0Bh; unsigned int
0x18005ed8a  lea     rcx, [rsp+0A8h+var_58]; this
0x18005ed8f  call    ??0CAutoPrivilege@Impl@WindowsPerformanceRecorder@@QEAA@KE@Z; WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(ulong,uchar)
0x18005ed94  nop
0x18005ed95  cmp     [rsp+0A8h+var_50], 0
0x18005ed9a  jge     short loc_18005EDA6
0x18005ed9c  mov     edi, 0C5585011h
0x18005eda1  jmp     loc_18005EFE4
0x18005eda6  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18005eda9  mov     rcx, rsi; this
0x18005edac  call    ?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x18005edb1  mov     edi, eax
0x18005edb3  test    eax, eax
0x18005edb5  js      loc_18005EFE4
0x18005edbb  mov     rcx, [rsi+188h]
0x18005edc2  mov     rdx, [rcx+8]
0x18005edc6  mov     [rbx+70h], rdx
0x18005edca  cmp     ebp, 1
0x18005edcd  jnz     short loc_18005EDD4
0x18005edcf  xor     bpl, bpl
0x18005edd2  jmp     short loc_18005EDFC
0x18005edd4  mov     r8, [rsi+188h]
0x18005eddb  mov     rcx, rbx; this
0x18005edde  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x18005ede3  mov     rdx, rax
0x18005ede6  mov     ecx, [r8+70h]
0x18005edea  add     rcx, r8
0x18005eded  call    cs:__imp__o__wcsicmp
0x18005edf3  neg     eax
0x18005edf5  sbb     bpl, bpl
0x18005edf8  and     bpl, 1
0x18005edfc  mov     rdx, [rbx+8]; Src
0x18005ee00  mov     r8d, [rdx]; Size
0x18005ee03  mov     rcx, [rsi+188h]; void *
0x18005ee0a  call    memcpy_0
0x18005ee0f  test    bpl, bpl
0x18005ee12  jz      short loc_18005EE1E
0x18005ee14  cmp     [rsp+0A8h+arg_20], 0
0x18005ee1c  jnz     short loc_18005EE2C
0x18005ee1e  mov     rax, [rsi+188h]
0x18005ee25  mov     dword ptr [rax+70h], 0
0x18005ee2c  lea     rax, off_18008EB00
0x18005ee33  mov     [rsp+0A8h+var_68], rax
0x18005ee38  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 1
0x18005ee3f  jz      short loc_18005EE64
0x18005ee41  lea     rax, [rsp+0A8h+var_40]
0x18005ee46  mov     [rsp+0A8h+Format], rax
0x18005ee4b  mov     r9d, 1
0x18005ee51  lea     rdx, Perf_ExternalCall_Begin
0x18005ee58  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18005ee5f  call    McGenEventWrite_EventWriteTransfer
0x18005ee64  mov     rcx, rbx; this
0x18005ee67  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005ee6c  mov     r9d, 2; ControlCode
0x18005ee72  mov     r8, [rsi+188h]; Properties
0x18005ee79  mov     rdx, rax; InstanceName
0x18005ee7c  mov     rcx, [rbx+70h]; TraceHandle
0x18005ee80  call    cs:__imp_ControlTraceW
0x18005ee86  test    eax, eax
0x18005ee88  jz      short loc_18005EE93
0x18005ee8a  mov     ecx, eax; unsigned int
0x18005ee8c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18005ee91  mov     edi, eax
0x18005ee93  lea     rcx, [rsp+0A8h+var_68]
0x18005ee98  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x18005ee9d  test    edi, edi
0x18005ee9f  js      loc_18005EFE4
0x18005eea5  mov     rcx, [rbx+10h]
0x18005eea9  test    rcx, rcx
0x18005eeac  jz      loc_18005EF72
0x18005eeb2  mov     rax, [rsi+190h]
0x18005eeb9  test    rax, rax
0x18005eebc  jz      loc_18005EF72
0x18005eec2  mov     eax, [rax+88h]
0x18005eec8  xor     eax, [rcx+88h]
0x18005eece  test    al, 2
0x18005eed0  jz      loc_18005EF72
0x18005eed6  mov     rcx, rbx; this
0x18005eed9  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005eede  mov     r9, rax; unsigned __int16 *
0x18005eee1  mov     [rsp+0A8h+var_80], 0; struct IControlErrorInfo *
0x18005eeea  mov     [rsp+0A8h+Format], r15; unsigned __int16 *
0x18005eeef  mov     ebp, 0C558063Dh
0x18005eef4  mov     edx, ebp; int
0x18005eef6  mov     rcx, rsi; this
0x18005eef9  call    ?AddCollectorControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBG1PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(long,_GUID const &,ushort const *,ushort const *,IControlErrorInfo *)
0x18005eefe  mov     rcx, rbx; this
0x18005ef01  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005ef06  mov     rcx, [rsi+190h]
0x18005ef0d  mov     edx, [rcx+88h]
0x18005ef13  shr     edx, 1
0x18005ef15  and     edx, 1
0x18005ef18  mov     [rsp+0A8h+var_70], edx
0x18005ef1c  mov     [rsp+0A8h+var_78], r15
0x18005ef21  mov     [rsp+0A8h+var_80], rax; char *
0x18005ef26  lea     rax, aWsWsRunningPro; "%ws: %ws Running Properties->QpcDelta ="...
0x18005ef2d  mov     [rsp+0A8h+Format], rax; Format
0x18005ef32  mov     r9d, ebp; unsigned int
0x18005ef35  mov     r8d, 0CF2h; char *
0x18005ef3b  lea     rdx, aUpdateeventses; "UpdateEventSession"
0x18005ef42  mov     ecx, 3; this
0x18005ef47  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005ef4c  mov     r8, [rbx+10h]
0x18005ef50  mov     edx, [r8+88h]
0x18005ef57  mov     rax, [rsi+190h]
0x18005ef5e  mov     ecx, edx
0x18005ef60  xor     ecx, [rax+88h]
0x18005ef66  and     ecx, 2
0x18005ef69  xor     ecx, edx
0x18005ef6b  mov     [r8+88h], ecx
0x18005ef72  mov     rax, [rsi+188h]
0x18005ef79  mov     rcx, [rbx+8]
0x18005ef7d  mov     eax, [rax+30h]
0x18005ef80  mov     [rcx+30h], eax
0x18005ef83  mov     rax, [rsi+188h]
0x18005ef8a  mov     rcx, [rbx+8]
0x18005ef8e  mov     eax, [rax+38h]
0x18005ef91  mov     [rcx+34h], eax
0x18005ef94  mov     rax, [rsi+188h]
0x18005ef9b  mov     rcx, [rbx+8]; this
0x18005ef9f  mov     eax, [rax+38h]
0x18005efa2  mov     [rcx+38h], eax
0x18005efa5  cmp     dword ptr [rbx], 1
0x18005efa8  jnz     short loc_18005EFBD
0x18005efaa  lea     r8, [rbx+78h]; struct _PERFINFO_GROUPMASK *
0x18005efae  mov     rdx, [rbx+70h]; unsigned __int64
0x18005efb2  call    ?GetRunningSystemGroupMask@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEAU_PERFINFO_GROUPMASK@@@Z; WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(unsigned __int64,_PERFINFO_GROUPMASK &)
0x18005efb7  mov     edi, eax
0x18005efb9  test    eax, eax
0x18005efbb  js      short loc_18005EFE4
0x18005efbd  cmp     [rsp+0A8h+arg_20], 0
0x18005efc5  jz      short loc_18005F03B
0x18005efc7  mov     eax, [rbx]
0x18005efc9  dec     eax
0x18005efcb  cmp     eax, 1
0x18005efce  ja      short loc_18005F03B
0x18005efd0  mov     r8, rbx; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18005efd3  mov     rdx, r15; unsigned __int16 *
0x18005efd6  mov     rcx, rsi; this
0x18005efd9  call    ?UpdateEventProviders@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::UpdateEventProviders(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &)
0x18005efde  mov     edi, eax
0x18005efe0  test    eax, eax
0x18005efe2  jns     short loc_18005F03B
0x18005efe4  mov     rcx, rbx; this
0x18005efe7  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005efec  mov     [rsp+0A8h+Format], rax
0x18005eff1  lea     r9, IID_IControlManager
0x18005eff8  mov     ebp, 2
0x18005effd  mov     r8d, ebp
0x18005f000  mov     edx, edi
0x18005f002  mov     rcx, rsi
0x18005f005  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x18005f00a  mov     rcx, rbx; this
0x18005f00d  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18005f012  mov     [rsp+0A8h+var_80], rax; char *
0x18005f017  lea     rax, aWs_0; "%ws"
0x18005f01e  mov     [rsp+0A8h+Format], rax; Format
0x18005f023  mov     r9d, edi; unsigned int
0x18005f026  mov     r8d, 0D13h; char *
0x18005f02c  lea     rdx, aUpdateeventses; "UpdateEventSession"
0x18005f033  mov     ecx, ebp; this
0x18005f035  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005f03a  nop
0x18005f03b  lea     rcx, [rsp+0A8h+var_58]; this
0x18005f040  call    ??1CAutoPrivilege@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege(void)
0x18005f045  mov     eax, edi
0x18005f047  mov     rcx, [rsp+0A8h+var_30]
0x18005f04c  xor     rcx, rsp; StackCookie
0x18005f04f  call    __security_check_cookie
0x18005f054  add     rsp, 80h
0x18005f05b  pop     r15
0x18005f05d  pop     rdi
0x18005f05e  pop     rsi
0x18005f05f  pop     rbp
0x18005f060  pop     rbx
0x18005f061  retn
```
