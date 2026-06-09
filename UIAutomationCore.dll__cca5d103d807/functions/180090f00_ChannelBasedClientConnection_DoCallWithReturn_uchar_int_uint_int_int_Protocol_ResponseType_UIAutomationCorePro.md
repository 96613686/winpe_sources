# ChannelBasedClientConnection::DoCallWithReturn(uchar *,int,uint,int,int,Protocol_ResponseType *,UIAutomationCoreProto::UiaCoreResponseMsg * *)

- ea: `0x180090f00`
- end: `0x1800914d6`
- name: `?DoCallWithReturn@ChannelBasedClientConnection@@UEAAJPEAEHIHHPEAW4Protocol_ResponseType@@PEAPEAVUiaCoreResponseMsg@UIAutomationCoreProto@@@Z`
- size: `1494`
- prototype: `__int64 __usercall@<rax>(ChannelBasedClientConnection *__hidden this@<rcx>, unsigned __int8 *@<rdx>, int@<r8d>, unsigned int@<r9d>, int, int, enum Protocol_ResponseType *, struct UIAutomationCoreProto::UiaCoreResponseMsg **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ddcc`
- `0x180032724`
- `0x1800552a8`
- `0x18008fbd8`
- `0x18009054c`
- `0x180090680`
- `0x180090ed4`
- `0x180090f00`
- `0x180092df4`
- `0x180143060`
- `0x180150d18`
- `0x180163e4c`
- `0x1801680a4`
- `0x180168534`
- `0x180171468`
- `0x1802095d0`
- `0x180234b68`
- `0x180235c74`
- `0x180235db8`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800910f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800910f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800910e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800910e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091068`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091068`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800912da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800912da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091052`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18009100e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18009100e`

## string_xrefs

- `0x180090f52`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x180090fe8`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x1800910cd`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x180091110`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x180091262`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x1800913fe`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18009143d`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x180091460`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ChannelBasedClientConnection::DoCallWithReturn(
        RTL_SRWLOCK *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        enum Protocol_ResponseType *a7,
        struct UIAutomationCoreProto::UiaCoreResponseMsg **a8)
{
  __int64 v10; // rax
  __int64 v11; // rdx
  char *v12; // rcx
  _DWORD *v13; // rdi
  unsigned int v14; // r12d
  int Ptr; // edi
  unsigned __int8 v16; // al
  int v17; // ecx
  int v18; // r13d
  int v19; // ecx
  int v20; // edi
  char v21; // al
  int v22; // edx
  const char *v23; // r9
  __int64 result; // rax
  __int64 v25; // rdx
  ClientConnectionTimeoutTrace *v26; // rcx
  int v27; // edi
  __int64 v28; // r8
  PVOID *v29; // rcx
  struct UIAutomationCoreProto::UiaCoreResponseMsg *v30; // rax
  int v31; // [rsp+20h] [rbp-A8h]
  HANDLE hObject; // [rsp+40h] [rbp-88h] BYREF
  int v33; // [rsp+48h] [rbp-80h]
  HWND v34; // [rsp+50h] [rbp-78h]
  __int128 v35; // [rsp+58h] [rbp-70h] BYREF
  char *v36; // [rsp+70h] [rbp-58h] BYREF
  struct UIAutomationCoreProto::UiaCoreResponseMsg *v37; // [rsp+78h] [rbp-50h]
  char v38; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned int v40; // [rsp+D0h] [rbp+8h]

  try
  {
    *(_DWORD *)a7 = 0;
    *a8 = 0;
    if ( !this[64].Ptr )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)0x80040201LL,
        v31);
    v34 = (HWND)(*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 7))(this);
    v40 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 8))(this);
    LODWORD(hObject) = v40;
    if ( g_clientConnectionRecoveryBehavior && !a5 && !CircuitBreaker::IsCallAllowed((CircuitBreaker *)&this[65]) )
    {
      v10 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int128 *))this->Ptr + 13))(this, &v35);
      UiaProvider::ClientConnectionCircuitBreakerOpenState<unsigned long &,std::optional<_GUID>>(&hObject, v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)0x80131505LL,
        v31);
    }
    v35 = 0;
    v12 = (char *)OpenFileMappingW(6u, 0, L"TipTestNumberOfCrossProcCalls");
    hObject = v12;
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      TipTestsSharedMemory::MapFile(&v35, &hObject);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &v35,
        &hObject);
      v12 = (char *)hObject;
    }
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v12);
    if ( !a5 )
    {
      v13 = (_DWORD *)*((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) )
      {
        if ( *v13 == GetCurrentThreadId() )
          ++v13[1];
      }
    }
    LOBYTE(v11) = a6 != 0;
    v14 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64))this->Ptr + 20))(this, v11);
    if ( (*((unsigned __int8 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 12))(this)
      && (*(unsigned int (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[13].Ptr + 24LL))(this[13].Ptr, v14) )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)0x80040201LL,
        v31);
    }
    AcquireSRWLockShared(this + 11);
    Ptr = (int)this[12].Ptr;
    if ( this != (RTL_SRWLOCK *)-88LL )
      ReleaseSRWLockShared(this + 11);
    if ( Ptr == 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)0x80040201LL,
        v31);
    v16 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 12))(this);
    v18 = v16;
    LOBYTE(hObject) = 1;
    BYTE1(hObject) = v16;
    HIDWORD(hObject) = a4;
    v33 = 0;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0ttq_EventWriteTransfer(v17, (unsigned int)ClientConnection_DispatchToProvider_Start, 1, v16, a4);
    LOBYTE(v31) = 0;
    v20 = (*(__int64 (__fastcall **)(PVOID, unsigned __int8 *, _QWORD, _QWORD))(*(_QWORD *)this[64].Ptr + 16LL))(
            this[64].Ptr,
            a2,
            a3,
            v14);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    {
      v21 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 12))(this);
      McTemplateU0qqtqqd_EventWriteTransfer(a3, v22, a4, v40, v21, a3, v14, v20);
    }
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_796aaf4b5428353a6aec4854fe809ea8_Traceguids,
          (unsigned int)v20);
      if ( v20 == -2147024664 )
        ChannelBasedClientConnection::ConnectionState::SetState(&this[11], 2);
      if ( g_clientConnectionRecoveryBehavior && !a5 )
        CircuitBreaker::SetCallResult((CircuitBreaker *)&this[65], v20);
      if ( v20 != -2146233083 )
        v20 = -2147220991;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)v20,
        v31);
    }
    if ( a5 )
    {
      *(_DWORD *)a7 = 4;
      *a8 = 0;
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McTemplateU0ttq_EventWriteTransfer(v19, (unsigned int)ClientConnection_DispatchToProvider_Stop, 1, v18, a4);
      AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>((char *)&v35 + 8);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
      return 0;
    }
    if ( IsDebuggerPresent() )
      v27 = !RequestResponseCoordinator::WaitForResponse((RequestResponseCoordinator *)&this[33], a4, v14)
          ? 0x80131505
          : 0;
    else
      v27 = ChannelBasedClientConnection::WaitForResponse((ChannelBasedClientConnection *)this, a4, v14);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0ttq_EventWriteTransfer(
        (_DWORD)v26,
        (unsigned int)ClientConnection_DispatchToProvider_Stop,
        1,
        v18,
        a4);
    if ( g_clientConnectionRecoveryBehavior )
    {
      if ( v27 == -2146233083 )
        ClientConnectionTimeoutTrace::ReportEtwClientConnectionTimeoutTrace(v26, a2, a3, v40, v34, v14);
      CircuitBreaker::SetCallResult((CircuitBreaker *)&this[65], v27);
    }
    if ( v27 < 0 )
    {
      if ( v27 == -2146233083 )
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_61;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        {
LABEL_58:
          if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 8) != 0 )
            WPP_SF_d(v29[2], 13, &WPP_796aaf4b5428353a6aec4854fe809ea8_Traceguids, (unsigned int)v27);
LABEL_61:
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1BB,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
            (const char *)(unsigned int)v27,
            v31);
        }
        v31 = v40;
        WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v28, v14);
      }
      v29 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_58;
    }
    RequestResponseCoordinator::RemoveResponseInfo(&this[33], &v36, a4);
    if ( !v38 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)0x8000FFFFLL,
        v31);
    if ( (int)v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)v36,
        v31);
    v30 = v37;
    v37 = 0;
    *a8 = v30;
    *(_DWORD *)a7 = HIDWORD(v36);
    std::_Optional_destruct_base<RequestResponseCoordinator::ResponseInfo,0>::~_Optional_destruct_base<RequestResponseCoordinator::ResponseInfo,0>(&v36);
    AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&void TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>((char *)&v35 + 8);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CB,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180090f00  mov     [rsp+arg_10], r8d
0x180090f05  mov     [rsp+arg_8], rdx
0x180090f0a  push    rbx
0x180090f0b  push    rsi
0x180090f0c  push    rdi
0x180090f0d  push    r12
0x180090f0f  push    r13
0x180090f11  push    r14
0x180090f13  push    r15
0x180090f15  sub     rsp, 90h
0x180090f1c  mov     esi, r9d
0x180090f1f  mov     rbx, rcx
0x180090f22  xor     r13d, r13d
0x180090f25  mov     rax, [rsp+0C8h+arg_30]
0x180090f2d  mov     [rax], r13d
0x180090f30  mov     rax, [rsp+0C8h+arg_38]
0x180090f38  mov     [rax], r13
0x180090f3b  mov     rcx, [rsp+0C8h]; this
0x180090f43  cmp     [rbx+200h], r13
0x180090f4a  jnz     short loc_180090F63
0x180090f4c  mov     r9d, 80040201h; char *
0x180090f52  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x180090f59  mov     edx, 124h; void *
0x180090f5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090f63  mov     rax, [rbx]
0x180090f66  mov     rcx, rbx
0x180090f69  mov     rax, [rax+38h]
0x180090f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090f72  mov     [rsp+0C8h+var_78], rax
0x180090f77  mov     rcx, [rbx]
0x180090f7a  mov     rax, [rcx+40h]
0x180090f7e  mov     rcx, rbx
0x180090f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090f86  mov     [rsp+0C8h+arg_0], eax
0x180090f8d  mov     dword ptr [rsp+0C8h+hObject], eax
0x180090f91  mov     cl, cs:?g_clientConnectionRecoveryBehavior@@3U?$atomic@_N@std@@A; std::atomic<bool> g_clientConnectionRecoveryBehavior
0x180090f97  nop
0x180090f98  mov     r15d, [rsp+0C8h+arg_20]
0x180090fa0  test    cl, cl
0x180090fa2  jz      short loc_180090FF9
0x180090fa4  test    r15d, r15d
0x180090fa7  jnz     short loc_180090FF9
0x180090fa9  lea     rcx, [rbx+208h]; this
0x180090fb0  call    ?IsCallAllowed@CircuitBreaker@@QEAA_NXZ; CircuitBreaker::IsCallAllowed(void)
0x180090fb5  test    al, al
0x180090fb7  jnz     short loc_180090FF9
0x180090fb9  mov     rax, [rbx]
0x180090fbc  lea     rdx, [rsp+0C8h+var_70]
0x180090fc1  mov     rcx, rbx
0x180090fc4  mov     rax, [rax+68h]
0x180090fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090fcd  mov     rdx, rax
0x180090fd0  lea     rcx, [rsp+0C8h+hObject]
0x180090fd5  call    ??$ClientConnectionCircuitBreakerOpenState@AEAKV?$optional@U_GUID@@@std@@@UiaProvider@@SAXAEAK$$QEAV?$optional@U_GUID@@@std@@@Z; UiaProvider::ClientConnectionCircuitBreakerOpenState<ulong &,std::optional<_GUID>>(ulong &,std::optional<_GUID> &&)
0x180090fda  mov     rcx, [rsp+0C8h]; this
0x180090fe2  mov     r9d, 80131505h; char *
0x180090fe8  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x180090fef  mov     edx, 12Eh; void *
0x180090ff4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090ff9  xorps   xmm0, xmm0
0x180090ffc  movdqu  [rsp+0C8h+var_70], xmm0
0x180091002  lea     r8, Name; "TipTestNumberOfCrossProcCalls"
0x180091009  xor     edx, edx; bInheritHandle
0x18009100b  lea     ecx, [rdx+6]; dwDesiredAccess
0x18009100e  call    cs:__imp_OpenFileMappingW
0x180091014  mov     rcx, rax
0x180091017  mov     [rsp+0C8h+hObject], rax
0x18009101c  dec     rax
0x18009101f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180091023  ja      short loc_180091048
0x180091025  lea     rdx, [rsp+0C8h+hObject]
0x18009102a  lea     rcx, [rsp+0C8h+var_70]
0x18009102f  call    ?MapFile@TipTestsSharedMemory@@IEAAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; TipTestsSharedMemory::MapFile(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x180091034  lea     rdx, [rsp+0C8h+hObject]
0x180091039  lea     rcx, [rsp+0C8h+var_70]
0x18009103e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180091043  mov     rcx, [rsp+0C8h+hObject]; hObject
0x180091048  lea     rax, [rcx-1]
0x18009104c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180091050  ja      short loc_180091059
0x180091052  call    cs:__imp_CloseHandle
0x180091058  nop
0x180091059  test    r15d, r15d
0x18009105c  jnz     short loc_180091075
0x18009105e  mov     rdi, qword ptr [rsp+0C8h+var_70+8]
0x180091063  test    rdi, rdi
0x180091066  jz      short loc_180091075
0x180091068  call    cs:__imp_GetCurrentThreadId
0x18009106e  cmp     [rdi], eax
0x180091070  jnz     short loc_180091075
0x180091072  inc     dword ptr [rdi+4]
0x180091075  mov     rax, [rbx]
0x180091078  cmp     [rsp+0C8h+arg_28], r13d
0x180091080  setnz   dl
0x180091083  mov     rcx, rbx
0x180091086  mov     rax, [rax+0A0h]
0x18009108d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091092  mov     r12d, eax
0x180091095  mov     rcx, [rbx]
0x180091098  mov     rax, [rcx+60h]
0x18009109c  mov     rcx, rbx
0x18009109f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910a4  test    al, al
0x1800910a6  jz      short loc_1800910DE
0x1800910a8  mov     rcx, [rbx+68h]
0x1800910ac  mov     rax, [rcx]
0x1800910af  mov     edx, r12d
0x1800910b2  mov     rax, [rax+18h]
0x1800910b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800910bb  test    eax, eax
0x1800910bd  jz      short loc_1800910DE
0x1800910bf  mov     rcx, [rsp+0C8h]; this
0x1800910c7  mov     r9d, 80040201h; char *
0x1800910cd  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x1800910d4  mov     edx, 143h; void *
0x1800910d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800910de  lea     r14, [rbx+58h]
0x1800910e2  mov     rcx, r14; SRWLock
0x1800910e5  call    cs:__imp_AcquireSRWLockShared
0x1800910eb  mov     edi, [r14+8]
0x1800910ef  test    r14, r14
0x1800910f2  jz      short loc_1800910FD
0x1800910f4  mov     rcx, r14; SRWLock
0x1800910f7  call    cs:__imp_ReleaseSRWLockShared
0x1800910fd  cmp     edi, 2
0x180091100  jnz     short loc_180091121
0x180091102  mov     rcx, [rsp+0C8h]; this
0x18009110a  mov     r9d, 80040201h; char *
0x180091110  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x180091117  mov     edx, 14Fh; void *
0x18009111c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091121  mov     rax, [rbx]
0x180091124  mov     rcx, rbx
0x180091127  mov     rax, [rax+60h]
0x18009112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091130  movzx   r13d, al
0x180091134  mov     byte ptr [rsp+0C8h+hObject], 1
0x180091139  mov     byte ptr [rsp+0C8h+hObject+1], r13b
0x18009113e  mov     dword ptr [rsp+0C8h+hObject+4], esi
0x180091142  mov     [rsp+0C8h+var_80], 0
0x18009114a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180091151  jz      short loc_18009116D
0x180091153  mov     r9d, r13d
0x180091156  mov     dword ptr [rsp+0C8h+var_A8], esi
0x18009115a  mov     r8d, 1
0x180091160  lea     rdx, ClientConnection_DispatchToProvider_Start
0x180091167  call    McTemplateU0ttq_EventWriteTransfer
0x18009116c  nop
0x18009116d  mov     rcx, [rbx+200h]
0x180091174  mov     rax, [rcx]
0x180091177  mov     byte ptr [rsp+0C8h+var_A8], 0
0x18009117c  mov     r9d, r12d
0x18009117f  mov     r8d, [rsp+0C8h+arg_10]
0x180091187  mov     rdx, [rsp+0C8h+arg_8]
0x18009118f  mov     rax, [rax+10h]
0x180091193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091198  mov     edi, eax
0x18009119a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800911a1  jz      short loc_1800911DD
0x1800911a3  mov     rax, [rbx]
0x1800911a6  mov     rcx, rbx
0x1800911a9  mov     rax, [rax+60h]
0x1800911ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911b2  movzx   eax, al
0x1800911b5  mov     [rsp+0C8h+var_90], edi
0x1800911b9  mov     [rsp+0C8h+var_98], r12d
0x1800911be  mov     ecx, [rsp+0C8h+arg_10]
0x1800911c5  mov     [rsp+0C8h+var_A0], ecx
0x1800911c9  mov     dword ptr [rsp+0C8h+var_A8], eax; int
0x1800911cd  mov     r9d, [rsp+0C8h+arg_0]
0x1800911d5  mov     r8d, esi
0x1800911d8  call    McTemplateU0qqtqqd_EventWriteTransfer
0x1800911dd  test    edi, edi
0x1800911df  jns     loc_180091273
0x1800911e5  lea     rsi, WPP_GLOBAL_Control
0x1800911ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800911f3  cmp     rcx, rsi
0x1800911f6  jz      short loc_180091216
0x1800911f8  test    byte ptr [rcx+1Ch], 8
0x1800911fc  jz      short loc_180091216
0x1800911fe  mov     edx, 0Bh
0x180091203  mov     r9d, edi
0x180091206  lea     r8, WPP_796aaf4b5428353a6aec4854fe809ea8_Traceguids
0x18009120d  mov     rcx, [rcx+10h]
0x180091211  call    WPP_SF_d
0x180091216  cmp     edi, 800700E8h
0x18009121c  jnz     short loc_18009122B
0x18009121e  mov     edx, 2
0x180091223  mov     rcx, r14
0x180091226  call    ?SetState@ConnectionState@ChannelBasedClientConnection@@AEAAXW4ConnectionStateValue@2@@Z; ChannelBasedClientConnection::ConnectionState::SetState(ChannelBasedClientConnection::ConnectionStateValue)
0x18009122b  mov     al, cs:?g_clientConnectionRecoveryBehavior@@3U?$atomic@_N@std@@A; std::atomic<bool> g_clientConnectionRecoveryBehavior
0x180091231  nop
0x180091232  test    al, al
0x180091234  jz      short loc_180091249
0x180091236  test    r15d, r15d
0x180091239  jnz     short loc_180091249
0x18009123b  lea     rcx, [rbx+208h]; this
0x180091242  mov     edx, edi; int
0x180091244  call    ?SetCallResult@CircuitBreaker@@QEAAXJ@Z; CircuitBreaker::SetCallResult(long)
0x180091249  mov     eax, 80040201h
0x18009124e  cmp     edi, 80131505h
0x180091254  cmovnz  edi, eax
0x180091257  mov     rcx, [rsp+0C8h]; this
0x18009125f  mov     r9d, edi; char *
0x180091262  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x180091269  mov     edx, 17Fh; void *
0x18009126e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180091273  test    r15d, r15d
0x180091276  jz      short loc_1800912D3
0x180091278  mov     rax, [rsp+0C8h+arg_30]
0x180091280  mov     dword ptr [rax], 4
0x180091286  mov     rax, [rsp+0C8h+arg_38]
0x18009128e  mov     qword ptr [rax], 0
0x180091295  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18009129c  jz      short loc_1800912B8
0x18009129e  mov     r9d, r13d
0x1800912a1  mov     dword ptr [rsp+0C8h+var_A8], esi
0x1800912a5  mov     r8d, 1
0x1800912ab  lea     rdx, ClientConnection_DispatchToProvider_Stop
0x1800912b2  call    McTemplateU0ttq_EventWriteTransfer
0x1800912b7  nop
0x1800912b8  lea     rcx, [rsp+0C8h+var_70+8]
0x1800912bd  call    ??1?$AutoCleanupFn@PEAURequestHeader@@$1??$TUnmapViewOfFile@PEAURequestHeader@@@@YAXPEAU1@@Z@@QEAA@XZ; AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>::~AutoCleanupFn<RequestHeader *,&TUnmapViewOfFile<RequestHeader *>(RequestHeader *)>(void)
0x1800912c2  lea     rcx, [rsp+0C8h+var_70]
0x1800912c7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800912cc  xor     eax, eax
0x1800912ce  jmp     loc_1800914C2
0x1800912d3  lea     r14, [rbx+108h]
0x1800912da  call    cs:__imp_IsDebuggerPresent
0x1800912e0  mov     r8d, r12d; unsigned int
0x1800912e3  mov     edx, esi; unsigned int
0x1800912e5  test    eax, eax
0x1800912e7  jz      short loc_1800912FF
0x1800912e9  mov     rcx, r14; this
0x1800912ec  call    ?WaitForResponse@RequestResponseCoordinator@@QEAA_NIK@Z; RequestResponseCoordinator::WaitForResponse(uint,ulong)
0x1800912f1  neg     al
0x1800912f3  sbb     edi, edi
0x1800912f5  not     edi
0x1800912f7  and     edi, 80131505h
0x1800912fd  jmp     short loc_180091309
0x1800912ff  mov     rcx, rbx; this
0x180091302  call    ?WaitForResponse@ChannelBasedClientConnection@@AEAAJIK@Z; ChannelBasedClientConnection::WaitForResponse(uint,ulong)
0x180091307  mov     edi, eax
0x180091309  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x180091310  jz      short loc_18009132B
0x180091312  mov     r9d, r13d
0x180091315  mov     dword ptr [rsp+0C8h+var_A8], esi
0x180091319  mov     r8d, 1
0x18009131f  lea     rdx, ClientConnection_DispatchToProvider_Stop
0x180091326  call    McTemplateU0ttq_EventWriteTransfer
0x18009132b  mov     al, cs:?g_clientConnectionRecoveryBehavior@@3U?$atomic@_N@std@@A; std::atomic<bool> g_clientConnectionRecoveryBehavior
0x180091331  nop
0x180091332  mov     r15, [rsp+0C8h+var_78]
0x180091337  test    al, al
0x180091339  jz      short loc_180091378
0x18009133b  cmp     edi, 80131505h
0x180091341  jnz     short loc_18009136A
0x180091343  mov     [rsp+0C8h+var_A0], r12d; unsigned int
0x180091348  mov     [rsp+0C8h+var_A8], r15; int
0x18009134d  mov     r9d, [rsp+0C8h+arg_0]; unsigned int
0x180091355  mov     r8d, [rsp+0C8h+arg_10]; int
0x18009135d  mov     rdx, [rsp+0C8h+arg_8]; unsigned __int8 *
0x180091365  call    ?ReportEtwClientConnectionTimeoutTrace@ClientConnectionTimeoutTrace@@QEAAXPEBEHKPEAUHWND__@@K@Z; ClientConnectionTimeoutTrace::ReportEtwClientConnectionTimeoutTrace(uchar const *,int,ulong,HWND__ *,ulong)
0x18009136a  lea     rcx, [rbx+208h]; this
0x180091371  mov     edx, edi; int
0x180091373  call    ?SetCallResult@CircuitBreaker@@QEAAXJ@Z; CircuitBreaker::SetCallResult(long)
0x180091378  test    edi, edi
0x18009137a  jns     loc_18009140F
0x180091380  cmp     edi, 80131505h
0x180091386  jnz     short loc_1800913C2
0x180091388  lea     rsi, WPP_GLOBAL_Control
0x18009138f  mov     rcx, cs:WPP_GLOBAL_Control
0x180091396  cmp     rcx, rsi
0x180091399  jz      short loc_1800913F3
0x18009139b  test    dword ptr [rcx+1Ch], 200h
0x1800913a2  jz      short loc_1800913D0
0x1800913a4  mov     [rsp+0C8h+var_A0], r15d
0x1800913a9  mov     eax, [rsp+0C8h+arg_0]
0x1800913b0  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800913b4  mov     r9d, r12d
0x1800913b7  mov     rcx, [rcx+10h]
0x1800913bb  call    WPP_SF_ddD
0x1800913c0  jmp     short loc_1800913C9
0x1800913c2  lea     rsi, WPP_GLOBAL_Control
0x1800913c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800913d0  cmp     rcx, rsi
0x1800913d3  jz      short loc_1800913F3
0x1800913d5  test    byte ptr [rcx+1Ch], 8
0x1800913d9  jz      short loc_1800913F3
0x1800913db  mov     edx, 0Dh
0x1800913e0  mov     r9d, edi
0x1800913e3  lea     r8, WPP_796aaf4b5428353a6aec4854fe809ea8_Traceguids
0x1800913ea  mov     rcx, [rcx+10h]
0x1800913ee  call    WPP_SF_d
0x1800913f3  mov     rcx, [rsp+0C8h]; this
0x1800913fb  mov     r9d, edi; char *
0x1800913fe  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x180091405  mov     edx, 1BBh; void *
0x18009140a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009140f  mov     r8d, esi
  ... truncated ...
```
