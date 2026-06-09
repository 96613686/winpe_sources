# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction(ushort const *,ushort const *)

- ea: `0x140008bc4`
- end: `0x140008e18`
- name: `?ExecuteAction@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAKPEBG0@Z`
- size: `596`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008e20`

## callees

- `0x1400033b0`
- `0x140003f8c`
- `0x140007d78`
- `0x14000818c`
- `0x140008560`
- `0x14000859c`
- `0x1400088ec`
- `0x140008964`
- `0x140008bc4`
- `0x140008ec8`
- `0x14000a43c`
- `0x14000abc0`
- `0x14000afd4`
- `0x14000b808`
- `0x14000b884`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140008d52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140008d52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008cec`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140008d66`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140008d66`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140008ce2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140008ce2`

## string_xrefs

- `0x140008d32`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140008d77`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdi
  GUID v8; // xmm6
  struct _PROCESS_INFORMATION *v9; // rdx
  __int64 v10; // rdx
  DWORD LastError; // ebx
  void *v12; // rdx
  unsigned int v13; // r8d
  int v14; // eax
  unsigned int hProcess; // ebx
  const char *v16; // r9
  unsigned int v17; // ebx
  struct _PROCESS_INFORMATION *v18; // rdx
  BOOL bInheritHandles; // [rsp+28h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+70h] [rbp-98h]
  GUID v23; // [rsp+78h] [rbp-90h] BYREF
  int v24; // [rsp+88h] [rbp-80h]
  __int128 v25; // [rsp+98h] [rbp-70h] BYREF
  int v26; // [rsp+A8h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v28[48]; // [rsp+128h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F0h] [rbp+1E8h]

  v6 = *((_DWORD *)this + 20);
  v7 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v8 = OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId;
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v28,
    "ExecuteCustomAction");
  v28[0] = &CASTraceProvider::ExecuteCustomAction::`vftable';
  v23 = v8;
  CASTraceProvider::ExecuteCustomAction::StartActivity((CASTraceProvider::ExecuteCustomAction *)v28, &v23, a3, v7, v6);
  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments(
    this,
    a2,
    (struct Common::StringBuffer *)&v25,
    (struct Common::StringBuffer *)&v23);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  *(_OWORD *)&ProcessInformation.hThread = 0;
  v22 = 0;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation.hThread, v9);
  *(_OWORD *)&ProcessInformation.hThread = 0;
  v22 = 0;
  if ( !CreateProcessW(
          0,
          *(LPWSTR *)v23.Data4,
          0,
          0,
          0,
          0x8000000u,
          0,
          a2,
          &StartupInfo,
          (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
  {
    LastError = GetLastError();
    CASTraceProvider::ExecuteCustomAction::CustomErrorLoggingEvent(
      (CASTraceProvider::ExecuteCustomAction *)v28,
      LastError);
    wil::details::in1diag3::Throw_Win32(retaddr, v12, v13, (const char *)LastError, bInheritHandles);
  }
  LOBYTE(v10) = 1;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 232LL))(*((_QWORD *)this + 11), v10);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v14,
      bInheritHandles);
  LODWORD(ProcessInformation.hProcess) = 0;
  hProcess = -1;
  if ( WaitForSingleObject(ProcessInformation.hThread, 0xFFFFFFFF) )
  {
    LODWORD(ProcessInformation.hProcess) = -1;
  }
  else
  {
    if ( !GetExitCodeProcess(ProcessInformation.hThread, (LPDWORD)&ProcessInformation) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        v16);
    hProcess = (unsigned int)ProcessInformation.hProcess;
  }
  *((_DWORD *)this + 19) = (hProcess != 0) + 1;
  if ( *((_DWORD *)this + 20) != 1 )
  {
    OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::PersistStatus(this);
    hProcess = (unsigned int)ProcessInformation.hProcess;
  }
  CASTraceProvider::ExecuteCustomAction::Stop((CASTraceProvider::ExecuteCustomAction *)v28, hProcess);
  v17 = (unsigned int)ProcessInformation.hProcess;
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation.hThread, v18);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v23);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v25);
  CASTraceProvider::ExecuteCustomAction::~ExecuteCustomAction((CASTraceProvider::ExecuteCustomAction *)v28);
  return v17;
}

```

## disassembly

```asm
0x140008bc4  mov     rax, rsp
0x140008bc7  mov     [rax+18h], rbx
0x140008bcb  push    rbp
0x140008bcc  push    rsi
0x140008bcd  push    rdi
0x140008bce  push    r14
0x140008bd0  push    r15
0x140008bd2  lea     rbp, [rax-1E8h]
0x140008bd9  sub     rsp, 2C0h
0x140008be0  movaps  xmmword ptr [rax-38h], xmm6
0x140008be4  mov     rax, cs:__security_cookie
0x140008beb  xor     rax, rsp
0x140008bee  mov     [rbp+1E0h+var_40], rax
0x140008bf5  mov     rsi, r8
0x140008bf8  mov     r14, rdx
0x140008bfb  mov     r15, rcx
0x140008bfe  mov     ebx, [rcx+50h]
0x140008c01  mov     rdi, [rcx+8]
0x140008c05  movups  xmm6, xmmword ptr cs:?s_customInstallExecId@TraceLoggingStatic@Internal@DEH@OSIntegration@@0U_GUID@@A.Data1; _GUID OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId ...
0x140008c0c  lea     rdx, aExecutecustoma; "ExecuteCustomAction"
0x140008c13  lea     rcx, [rbp+1E0h+var_1C0]
0x140008c17  call    ??0?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140008c1c  lea     rax, ??_7ExecuteCustomAction@CASTraceProvider@@6B@; const CASTraceProvider::ExecuteCustomAction::`vftable'
0x140008c23  mov     [rbp+1E0h+var_1C0], rax
0x140008c27  movdqa  xmmword ptr [rsp+2E0h+var_278.Data4], xmm6
0x140008c2d  mov     [rsp+2E0h+bInheritHandles], ebx; unsigned int
0x140008c31  mov     r9, rdi; unsigned __int16 *
0x140008c34  mov     r8, rsi; unsigned __int16 *
0x140008c37  lea     rdx, [rsp+2E0h+var_278.Data4]; struct _GUID *
0x140008c3c  lea     rcx, [rbp+1E0h+var_1C0]; this
0x140008c40  call    ?StartActivity@ExecuteCustomAction@CASTraceProvider@@QEAAXU_GUID@@PEBG1I@Z; CASTraceProvider::ExecuteCustomAction::StartActivity(_GUID,ushort const *,ushort const *,uint)
0x140008c45  nop
0x140008c46  xorps   xmm0, xmm0
0x140008c49  movups  [rbp+1E0h+var_250], xmm0
0x140008c4d  xor     edi, edi
0x140008c4f  mov     [rbp+1E0h+var_240], edi
0x140008c52  movups  xmmword ptr [rsp+2E0h+var_278.Data4], xmm0
0x140008c57  mov     [rbp+1E0h+var_260], edi
0x140008c5a  lea     r9, [rsp+2E0h+var_278.Data4]; struct Common::StringBuffer *
0x140008c5f  lea     r8, [rbp+1E0h+var_250]; struct Common::StringBuffer *
0x140008c63  mov     rdx, r14; unsigned __int16 *
0x140008c66  mov     rcx, r15; this
0x140008c69  call    ?GetApplicationAndArguments@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@IEAAXPEBGAEAVStringBuffer@Common@@1@Z; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments(ushort const *,Common::StringBuffer &,Common::StringBuffer &)
0x140008c6e  xor     edx, edx; Val
0x140008c70  lea     r8d, [rdi+64h]; Size
0x140008c74  lea     rcx, [rbp+1E0h+StartupInfo+4]; void *
0x140008c78  call    memset_0
0x140008c7d  mov     [rbp+1E0h+StartupInfo.cb], 68h ; 'h'
0x140008c84  xorps   xmm0, xmm0
0x140008c87  xor     eax, eax
0x140008c89  movups  xmmword ptr [rsp+2E0h+ProcessInformation.hThread], xmm0
0x140008c8e  mov     qword ptr [rsp+2E0h+var_278.Data1], rax
0x140008c93  lea     rcx, [rsp+2E0h+ProcessInformation.hThread]; this
0x140008c98  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x140008c9d  xorps   xmm0, xmm0
0x140008ca0  xor     eax, eax
0x140008ca2  movups  xmmword ptr [rsp+2E0h+ProcessInformation.hThread], xmm0
0x140008ca7  mov     qword ptr [rsp+2E0h+var_278.Data1], rax
0x140008cac  lea     rax, [rsp+2E0h+ProcessInformation.hThread]
0x140008cb1  mov     [rsp+2E0h+lpProcessInformation], rax; lpProcessInformation
0x140008cb6  lea     rax, [rbp+1E0h+StartupInfo]
0x140008cba  mov     [rsp+2E0h+lpStartupInfo], rax; lpStartupInfo
0x140008cbf  mov     [rsp+2E0h+lpCurrentDirectory], r14; lpCurrentDirectory
0x140008cc4  mov     [rsp+2E0h+lpEnvironment], rdi; lpEnvironment
0x140008cc9  mov     [rsp+2E0h+dwCreationFlags], 8000000h; dwCreationFlags
0x140008cd1  mov     [rsp+2E0h+bInheritHandles], edi; int
0x140008cd5  xor     r9d, r9d; lpThreadAttributes
0x140008cd8  xor     r8d, r8d; lpProcessAttributes
0x140008cdb  mov     rdx, [rsp+2E0h+lpCommandLine]; lpCommandLine
0x140008ce0  xor     ecx, ecx; lpApplicationName
0x140008ce2  call    cs:__imp_CreateProcessW
0x140008ce8  test    eax, eax
0x140008cea  jnz     short loc_140008D0F
0x140008cec  call    cs:__imp_GetLastError
0x140008cf2  mov     ebx, eax
0x140008cf4  mov     edx, eax; unsigned int
0x140008cf6  lea     rcx, [rbp+1E0h+var_1C0]; this
0x140008cfa  call    ?CustomErrorLoggingEvent@ExecuteCustomAction@CASTraceProvider@@QEAAXK@Z; CASTraceProvider::ExecuteCustomAction::CustomErrorLoggingEvent(ulong)
0x140008cff  mov     rcx, [rbp+1E8h]; this
0x140008d06  mov     r9d, ebx; char *
0x140008d09  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140008d0f  mov     rcx, [r15+58h]
0x140008d13  mov     rax, [rcx]
0x140008d16  mov     dl, 1
0x140008d18  mov     rax, [rax+0E8h]
0x140008d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d24  mov     rcx, [rbp+1E8h]; this
0x140008d2b  test    eax, eax
0x140008d2d  jns     short loc_140008D44
0x140008d2f  mov     r9d, eax; char *
0x140008d32  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008d39  mov     edx, 131h; void *
0x140008d3e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008d44  mov     dword ptr [rsp+2E0h+ProcessInformation.hProcess], edi
0x140008d48  or      ebx, 0FFFFFFFFh
0x140008d4b  mov     edx, ebx; dwMilliseconds
0x140008d4d  mov     rcx, [rsp+2E0h+ProcessInformation.hThread]; hHandle
0x140008d52  call    cs:__imp_WaitForSingleObject
0x140008d58  test    eax, eax
0x140008d5a  jnz     short loc_140008D8F
0x140008d5c  lea     rdx, [rsp+2E0h+ProcessInformation]; lpExitCode
0x140008d61  mov     rcx, [rsp+2E0h+ProcessInformation.hThread]; hProcess
0x140008d66  call    cs:__imp_GetExitCodeProcess
0x140008d6c  mov     rcx, [rbp+1E8h]; this
0x140008d73  test    eax, eax
0x140008d75  jnz     short loc_140008D89
0x140008d77  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008d7e  mov     edx, 137h; void *
0x140008d83  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140008d89  mov     ebx, dword ptr [rsp+2E0h+ProcessInformation.hProcess]
0x140008d8d  jmp     short loc_140008D93
0x140008d8f  mov     dword ptr [rsp+2E0h+ProcessInformation.hProcess], ebx
0x140008d93  mov     eax, edi
0x140008d95  test    ebx, ebx
0x140008d97  setnz   al
0x140008d9a  inc     eax
0x140008d9c  mov     [r15+4Ch], eax
0x140008da0  cmp     dword ptr [r15+50h], 1
0x140008da5  jz      short loc_140008DB3
0x140008da7  mov     rcx, r15; this
0x140008daa  call    ?PersistStatus@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAXXZ; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::PersistStatus(void)
0x140008daf  mov     ebx, dword ptr [rsp+2E0h+ProcessInformation.hProcess]
0x140008db3  mov     edx, ebx; unsigned int
0x140008db5  lea     rcx, [rbp+1E0h+var_1C0]; this
0x140008db9  call    ?Stop@ExecuteCustomAction@CASTraceProvider@@QEAAXK@Z; CASTraceProvider::ExecuteCustomAction::Stop(ulong)
0x140008dbe  mov     ebx, dword ptr [rsp+2E0h+ProcessInformation.hProcess]
0x140008dc2  lea     rcx, [rsp+2E0h+ProcessInformation.hThread]; this
0x140008dc7  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x140008dcc  nop
0x140008dcd  lea     rcx, [rsp+2E0h+var_278.Data4]; this
0x140008dd2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x140008dd7  nop
0x140008dd8  lea     rcx, [rbp+1E0h+var_250]; this
0x140008ddc  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x140008de1  nop
0x140008de2  lea     rcx, [rbp+1E0h+var_1C0]; this
0x140008de6  call    ??1ExecuteCustomAction@CASTraceProvider@@QEAA@XZ; CASTraceProvider::ExecuteCustomAction::~ExecuteCustomAction(void)
0x140008deb  mov     eax, ebx
0x140008ded  mov     rcx, [rbp+1E0h+var_40]
0x140008df4  xor     rcx, rsp; StackCookie
0x140008df7  call    __security_check_cookie
0x140008dfc  lea     r11, [rsp+2E0h+var_20]
0x140008e04  mov     rbx, [r11+40h]
0x140008e08  movaps  xmm6, xmmword ptr [r11-10h]
0x140008e0d  mov     rsp, r11
0x140008e10  pop     r15
0x140008e12  pop     r14
0x140008e14  pop     rdi
0x140008e15  pop     rsi
0x140008e16  pop     rbp
0x140008e17  retn
```
