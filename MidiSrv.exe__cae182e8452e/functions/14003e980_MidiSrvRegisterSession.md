# MidiSrvRegisterSession

- ea: `0x14003e980`
- end: `0x14003ed04`
- name: `MidiSrvRegisterSession`
- size: `900`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, _OWORD *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x14000a694`
- `0x14000a6b4`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003e980`
- `0x14005a010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x14003eb31`
- `RPCRT4!RpcRevertToSelf` at `0x14003eb3b`
- `RPCRT4!RpcRevertToSelf` at `0x14003eb31`
- `RPCRT4!RpcRevertToSelf` at `0x14003eb3b`
- `RPCRT4!RpcImpersonateClient` at `0x14003ead5`
- `RPCRT4!RpcImpersonateClient` at `0x14003eae2`
- `RPCRT4!RpcImpersonateClient` at `0x14003ead5`
- `RPCRT4!RpcImpersonateClient` at `0x14003eae2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003ea3a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003ea4f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003ea3a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003ea4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003eb27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eb14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eb14`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003eafd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003eafd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ea83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eb1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eb7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ea83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eb1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003eb7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec8c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ea89`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003eb85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ec92`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ea89`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003eb85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ec92`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003ea02`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003ea02`

## string_xrefs

- `0x14003ecef`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003ea5e`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003eb5e`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003ec10`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall MidiSrvRegisterSession(RPC_BINDING_HANDLE BindingHandle, _OWORD *a2, __int64 a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  HRESULT v9; // eax
  RPC_STATUS v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // esi
  volatile signed __int32 *v13; // rdi
  HANDLE v15; // rax
  HANDLE v16; // rdi
  void *v17; // rsi
  DWORD LastError; // ebx
  const char *v19; // r9
  __int64 v20; // rax
  int v21; // eax
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  volatile signed __int32 *v25; // rdi
  int v26; // [rsp+20h] [rbp-60h]
  unsigned int Pid; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-38h] BYREF
  const char *v29; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+58h] [rbp-28h] BYREF
  int v31[4]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v32; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    *(_QWORD *)v31 = "MidiSrvRegisterSession";
    v29 = (const char *)L"Enter";
    v30 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)&dword_14008B344,
      v7,
      v8,
      (__int64)v31,
      (__int64)&v30,
      (__int64)&v29);
  }
  v32 = 0;
  v9 = CoInitializeEx(0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v9,
      v26);
  Pid = 0;
  hObject = 0;
  std::shared_ptr<CMidiSessionTracker>::operator=(&v32, (char *)g_MidiService + 96);
  if ( I_RpcBindingInqLocalClientPID(BindingHandle, &Pid) )
  {
    v10 = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
    v11 = 343;
    goto LABEL_6;
  }
  if ( RpcImpersonateClient(BindingHandle) )
  {
    v10 = RpcImpersonateClient(BindingHandle);
    v11 = 344;
    goto LABEL_6;
  }
  v15 = OpenProcess(0x448u, 0, Pid);
  v16 = hObject;
  v17 = v15;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v16);
    SetLastError(LastError);
  }
  hObject = v17;
  if ( RpcRevertToSelf() )
  {
    v10 = RpcRevertToSelf();
    v11 = 346;
LABEL_6:
    v12 = v10 | 0x80010000;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(v10 | 0x80010000),
      v26);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoUninitialize();
    v13 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( !*((_QWORD *)&v32 + 1) )
      return v12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return v12;
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) != 1 )
      return v12;
    goto LABEL_11;
  }
  if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x15C,
            (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
            v19);
    goto LABEL_21;
  }
  v20 = *(_QWORD *)v32;
  *(_OWORD *)v31 = *a2;
  v21 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, _QWORD))(v20 + 16))(v32, v31, a3, Pid);
  v12 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v21,
      (int)&hObject);
LABEL_21:
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CoUninitialize();
    v13 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( !*((_QWORD *)&v32 + 1) )
      return v12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return v12;
    (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
    if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) != 1 )
      return v12;
LABEL_11:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    return v12;
  }
  v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v22 > 4u )
  {
    v30 = 0;
    *(_QWORD *)v31 = L"Exit success";
    v29 = "MidiSrvRegisterSession";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v22,
      (unsigned int)byte_14008B0B1,
      v23,
      v24,
      (__int64)&v29,
      (__int64)&v30,
      (__int64)v31);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  CoUninitialize();
  v25 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003e980  push    rbp
0x14003e982  push    rbx
0x14003e983  push    rsi
0x14003e984  push    rdi
0x14003e985  push    r12
0x14003e987  push    r14
0x14003e989  push    r15
0x14003e98b  mov     rbp, rsp
0x14003e98e  sub     rsp, 80h
0x14003e995  mov     r14, r9
0x14003e998  mov     r15, r8
0x14003e99b  mov     r12, rdx
0x14003e99e  mov     rbx, rcx
0x14003e9a1  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003e9a6  lea     rdx, aMidisrvregiste; "MidiSrvRegisterSession"
0x14003e9ad  mov     rcx, [rax+8]
0x14003e9b1  mov     eax, [rcx]
0x14003e9b3  cmp     eax, 4
0x14003e9b6  jbe     short loc_14003E9F6
0x14003e9b8  lea     rax, aEnter; "Enter"
0x14003e9bf  mov     qword ptr [rbp+var_20], rdx
0x14003e9c3  mov     [rbp+var_30], rax
0x14003e9c7  lea     rdx, dword_14008B344
0x14003e9ce  lea     rax, [rbp+var_30]
0x14003e9d2  mov     [rbp+var_28], 0
0x14003e9da  mov     [rsp+80h+var_50], rax
0x14003e9df  lea     rax, [rbp+var_28]
0x14003e9e3  mov     [rsp+80h+var_58], rax
0x14003e9e8  lea     rax, [rbp+var_20]
0x14003e9ec  mov     qword ptr [rsp+80h+var_60], rax; int
0x14003e9f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003e9f6  xorps   xmm0, xmm0
0x14003e9f9  xor     edx, edx; dwCoInit
0x14003e9fb  xor     ecx, ecx; pvReserved
0x14003e9fd  movdqu  [rbp+var_10], xmm0
0x14003ea02  call    cs:__imp_CoInitializeEx
0x14003ea08  test    eax, eax
0x14003ea0a  js      loc_14003ECEB
0x14003ea10  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003ea17  lea     rcx, [rbp+var_10]
0x14003ea1b  add     rdx, 60h ; '`'
0x14003ea1f  mov     [rbp+Pid], 0
0x14003ea26  mov     [rbp+hObject], 0
0x14003ea2e  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003ea33  lea     rdx, [rbp+Pid]; Pid
0x14003ea37  mov     rcx, rbx; Binding
0x14003ea3a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003ea40  mov     rcx, rbx; BindingHandle
0x14003ea43  test    eax, eax
0x14003ea45  jz      loc_14003EAD5
0x14003ea4b  lea     rdx, [rbp+Pid]; Pid
0x14003ea4f  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003ea55  mov     edx, 157h; void *
0x14003ea5a  mov     rcx, [rbp+38h]; this
0x14003ea5e  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003ea65  mov     esi, eax
0x14003ea67  or      esi, 80010000h
0x14003ea6d  mov     r9d, esi; char *
0x14003ea70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ea75  mov     rcx, [rbp+hObject]; hObject
0x14003ea79  lea     rax, [rcx-1]
0x14003ea7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003ea81  ja      short loc_14003EA89
0x14003ea83  call    cs:__imp_CloseHandle
0x14003ea89  call    cs:__imp_CoUninitialize
0x14003ea8f  mov     rdi, qword ptr [rbp+var_10+8]
0x14003ea93  test    rdi, rdi
0x14003ea96  jz      short loc_14003EACE
0x14003ea98  or      ebx, 0FFFFFFFFh
0x14003ea9b  mov     eax, ebx
0x14003ea9d  lock xadd [rdi+8], eax
0x14003eaa2  add     eax, ebx
0x14003eaa4  jnz     short loc_14003EACE
0x14003eaa6  mov     rax, [rdi]
0x14003eaa9  mov     rcx, rdi
0x14003eaac  mov     rax, [rax]
0x14003eaaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eab4  mov     edx, ebx
0x14003eab6  lock xadd [rdi+0Ch], edx
0x14003eabb  add     edx, ebx
0x14003eabd  jnz     short loc_14003EACE
0x14003eabf  mov     rdx, [rdi]
0x14003eac2  mov     rax, [rdx+8]
0x14003eac6  mov     rcx, rdi
0x14003eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eace  mov     eax, esi
0x14003ead0  jmp     loc_14003ECD9
0x14003ead5  call    cs:__imp_RpcImpersonateClient
0x14003eadb  test    eax, eax
0x14003eadd  jz      short loc_14003EAF2
0x14003eadf  mov     rcx, rbx; BindingHandle
0x14003eae2  call    cs:__imp_RpcImpersonateClient
0x14003eae8  mov     edx, 158h
0x14003eaed  jmp     loc_14003EA5A
0x14003eaf2  mov     r8d, [rbp+Pid]; dwProcessId
0x14003eaf6  xor     edx, edx; bInheritHandle
0x14003eaf8  mov     ecx, 448h; dwDesiredAccess
0x14003eafd  call    cs:__imp_OpenProcess
0x14003eb03  mov     rdi, [rbp+hObject]
0x14003eb07  mov     rsi, rax
0x14003eb0a  lea     rdx, [rdi-1]
0x14003eb0e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14003eb12  ja      short loc_14003EB2D
0x14003eb14  call    cs:__imp_GetLastError
0x14003eb1a  mov     rcx, rdi; hObject
0x14003eb1d  mov     ebx, eax
0x14003eb1f  call    cs:__imp_CloseHandle
0x14003eb25  mov     ecx, ebx; dwErrCode
0x14003eb27  call    cs:__imp_SetLastError
0x14003eb2d  mov     [rbp+hObject], rsi
0x14003eb31  call    cs:__imp_RpcRevertToSelf
0x14003eb37  test    eax, eax
0x14003eb39  jz      short loc_14003EB4B
0x14003eb3b  call    cs:__imp_RpcRevertToSelf
0x14003eb41  mov     edx, 15Ah
0x14003eb46  jmp     loc_14003EA5A
0x14003eb4b  mov     rax, [rbp+hObject]
0x14003eb4f  inc     rax
0x14003eb52  test    rax, 0FFFFFFFFFFFFFFFEh
0x14003eb58  jnz     short loc_14003EBD3
0x14003eb5a  mov     rcx, [rbp+38h]; this
0x14003eb5e  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003eb65  mov     edx, 15Ch; void *
0x14003eb6a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14003eb6f  mov     esi, eax
0x14003eb71  mov     rcx, [rbp+hObject]; hObject
0x14003eb75  lea     rdx, [rcx-1]
0x14003eb79  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14003eb7d  ja      short loc_14003EB85
0x14003eb7f  call    cs:__imp_CloseHandle
0x14003eb85  call    cs:__imp_CoUninitialize
0x14003eb8b  mov     rdi, qword ptr [rbp+var_10+8]
0x14003eb8f  test    rdi, rdi
0x14003eb92  jz      loc_14003EACE
0x14003eb98  or      ebx, 0FFFFFFFFh
0x14003eb9b  mov     eax, ebx
0x14003eb9d  lock xadd [rdi+8], eax
0x14003eba2  add     eax, ebx
0x14003eba4  jnz     loc_14003EACE
0x14003ebaa  mov     rax, [rdi]
0x14003ebad  mov     rcx, rdi
0x14003ebb0  mov     rax, [rax]
0x14003ebb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ebb8  mov     eax, ebx
0x14003ebba  lock xadd [rdi+0Ch], eax
0x14003ebbf  add     eax, ebx
0x14003ebc1  jnz     loc_14003EACE
0x14003ebc7  mov     rax, [rdi]
0x14003ebca  mov     rax, [rax+8]
0x14003ebce  jmp     loc_14003EAC6
0x14003ebd3  mov     rcx, qword ptr [rbp+var_10]
0x14003ebd7  lea     rdx, [rbp+hObject]
0x14003ebdb  movups  xmm0, xmmword ptr [r12]
0x14003ebe0  mov     r9d, [rbp+Pid]
0x14003ebe4  mov     r8, r15
0x14003ebe7  mov     [rsp+80h+var_58], r14
0x14003ebec  mov     rax, [rcx]
0x14003ebef  mov     qword ptr [rsp+80h+var_60], rdx; int
0x14003ebf4  lea     rdx, [rbp+var_20]
0x14003ebf8  movdqu  xmmword ptr [rbp+var_20], xmm0
0x14003ebfd  mov     rax, [rax+10h]
0x14003ec01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ec06  mov     esi, eax
0x14003ec08  test    eax, eax
0x14003ec0a  jns     short loc_14003EC29
0x14003ec0c  mov     rcx, [rbp+38h]; this
0x14003ec10  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003ec17  mov     r9d, eax; char *
0x14003ec1a  mov     edx, 15Eh; void *
0x14003ec1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ec24  jmp     loc_14003EB71
0x14003ec29  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003ec2e  mov     rcx, [rax+8]
0x14003ec32  mov     eax, [rcx]
0x14003ec34  cmp     eax, 4
0x14003ec37  jbe     short loc_14003EC7E
0x14003ec39  lea     rax, aExitSuccess_0; "Exit success"
0x14003ec40  mov     [rbp+var_28], 0
0x14003ec48  mov     qword ptr [rbp+var_20], rax
0x14003ec4c  lea     rdx, byte_14008B0B1
0x14003ec53  lea     rax, aMidisrvregiste; "MidiSrvRegisterSession"
0x14003ec5a  mov     [rbp+var_30], rax
0x14003ec5e  lea     rax, [rbp+var_20]
0x14003ec62  mov     [rsp+80h+var_50], rax
0x14003ec67  lea     rax, [rbp+var_28]
0x14003ec6b  mov     [rsp+80h+var_58], rax
0x14003ec70  lea     rax, [rbp+var_30]
0x14003ec74  mov     qword ptr [rsp+80h+var_60], rax
0x14003ec79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003ec7e  mov     rcx, [rbp+hObject]; hObject
0x14003ec82  lea     rax, [rcx-1]
0x14003ec86  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003ec8a  ja      short loc_14003EC92
0x14003ec8c  call    cs:__imp_CloseHandle
0x14003ec92  call    cs:__imp_CoUninitialize
0x14003ec98  mov     rdi, qword ptr [rbp+var_10+8]
0x14003ec9c  test    rdi, rdi
0x14003ec9f  jz      short loc_14003ECD7
0x14003eca1  or      ebx, 0FFFFFFFFh
0x14003eca4  mov     eax, ebx
0x14003eca6  lock xadd [rdi+8], eax
0x14003ecab  add     eax, ebx
0x14003ecad  jnz     short loc_14003ECD7
0x14003ecaf  mov     rax, [rdi]
0x14003ecb2  mov     rcx, rdi
0x14003ecb5  mov     rax, [rax]
0x14003ecb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ecbd  mov     eax, ebx
0x14003ecbf  lock xadd [rdi+0Ch], eax
0x14003ecc4  add     eax, ebx
0x14003ecc6  jnz     short loc_14003ECD7
0x14003ecc8  mov     rax, [rdi]
0x14003eccb  mov     rcx, rdi
0x14003ecce  mov     rax, [rax+8]
0x14003ecd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ecd7  xor     eax, eax
0x14003ecd9  add     rsp, 80h
0x14003ece0  pop     r15
0x14003ece2  pop     r14
0x14003ece4  pop     r12
0x14003ece6  pop     rdi
0x14003ece7  pop     rsi
0x14003ece8  pop     rbx
0x14003ece9  pop     rbp
0x14003ecea  retn
0x14003eceb  mov     rcx, [rbp+38h]; this
0x14003ecef  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003ecf6  mov     r9d, eax; char *
0x14003ecf9  mov     edx, 14D3h; void *
0x14003ecfe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
