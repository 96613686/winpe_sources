# MidiSrvDestroyClient

- ea: `0x14003dae0`
- end: `0x14003ddcc`
- name: `MidiSrvDestroyClient`
- size: `748`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x1400091a4`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400144ac`
- `0x140016484`
- `0x1400261b4`
- `0x14003cd6c`
- `0x14003dae0`
- `0x140046048`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003dc1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003dc1d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003dc82`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003dd17`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003dc82`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003dd17`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003dc32`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003dc32`

## string_xrefs

- `0x14003ddba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003dc71`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MidiSrvDestroyClient(__int64 a1, unsigned __int64 a2)
{
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  CMidiSrv *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  volatile signed __int32 *v9; // rbx
  __int64 *Local; // rax
  HRESULT v11; // eax
  int v12; // eax
  CMidiSrvTraceLogger *v13; // rcx
  unsigned int v14; // edi
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  int v20; // [rsp+20h] [rbp-39h]
  PSRWLOCK SRWLock[2]; // [rsp+40h] [rbp-19h] BYREF
  __int128 v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 (__fastcall **v23)(); // [rsp+60h] [rbp+7h] BYREF
  _QWORD v24[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+78h] [rbp+1Fh]
  DWORD CurrentThreadId; // [rsp+80h] [rbp+27h]
  __int64 v27; // [rsp+88h] [rbp+2Fh]
  char v28; // [rsp+90h] [rbp+37h]
  __int128 *v29; // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  const wchar_t *v31; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+7Fh] BYREF

  v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v3 > 4u )
  {
    v31 = L"Enter";
    v32 = 0;
    SRWLock[0] = (PSRWLOCK)"MidiSrvDestroyClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)byte_14008B3DB,
      v4,
      v5,
      SRWLock,
      (__int64)&v32,
      &v31);
  }
  *(_OWORD *)SRWLock = 0;
  v22 = 0;
  v6 = g_MidiService;
  v7 = *((_QWORD *)g_MidiService + 15);
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v8 = *((_QWORD *)v6 + 15);
  *(_QWORD *)&v22 = *((_QWORD *)v6 + 14);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  *((_QWORD *)&v22 + 1) = v8;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v23 = off_14005B9F8;
  v24[0] = 0;
  v24[1] = &v23;
  v25 = 0;
  CurrentThreadId = 0;
  v27 = 0;
  v28 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v6) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v8,
                         v6);
    v24[0] = Local;
    if ( Local )
    {
      v25 = *Local;
      *Local = (__int64)v24;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  v29 = &v22;
  v11 = CoInitializeEx(0, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v11,
      v20);
  std::shared_ptr<CMidiSessionTracker>::operator=(SRWLock, (char *)g_MidiService + 48);
  v12 = CMidiClientManager::DestroyMidiClient(SRWLock[0], a2);
  v14 = v12;
  if ( v12 >= 0 )
  {
    CMidiSrvTraceLogger::LogMidi2DestroyClient(v13, 0);
    CoUninitialize();
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v19 = (volatile signed __int32 *)SRWLock[1];
    if ( SRWLock[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&SRWLock[1][1], 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v12,
      v20);
    CoUninitialize();
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
    v15 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = (volatile signed __int32 *)SRWLock[1];
    if ( SRWLock[1] && _InterlockedExchangeAdd((volatile signed __int32 *)&SRWLock[1][1], 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x14003dae0  mov     [rsp-8+arg_0], rbx
0x14003dae5  push    rbp
0x14003dae6  push    rsi
0x14003dae7  push    rdi
0x14003dae8  lea     rbp, [rsp-47h]
0x14003daed  sub     rsp, 0A0h
0x14003daf4  mov     rdi, rdx
0x14003daf7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003dafc  mov     rcx, [rax+8]
0x14003db00  mov     eax, [rcx]
0x14003db02  cmp     eax, 4
0x14003db05  jbe     short loc_14003DB4C
0x14003db07  lea     rax, aEnter; "Enter"
0x14003db0e  mov     [rbp+57h+arg_10], rax
0x14003db12  mov     [rbp+57h+arg_18], 0
0x14003db1a  lea     rax, aMidisrvdestroy; "MidiSrvDestroyClient"
0x14003db21  mov     [rbp+57h+SRWLock], rax
0x14003db25  lea     rax, [rbp+57h+arg_10]
0x14003db29  mov     [rsp+0B0h+var_80], rax
0x14003db2e  lea     rax, [rbp+57h+arg_18]
0x14003db32  mov     [rsp+0B0h+var_88], rax
0x14003db37  lea     rax, [rbp+57h+SRWLock]
0x14003db3b  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x14003db40  lea     rdx, byte_14008B3DB
0x14003db47  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003db4c  xorps   xmm0, xmm0
0x14003db4f  movdqu  xmmword ptr [rbp+57h+SRWLock], xmm0
0x14003db54  xorps   xmm1, xmm1
0x14003db57  movdqu  [rbp+57h+var_60], xmm1
0x14003db5c  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003db63  mov     rax, [rdx+78h]
0x14003db67  test    rax, rax
0x14003db6a  jz      short loc_14003DB70
0x14003db6c  lock inc dword ptr [rax+8]
0x14003db70  mov     rcx, [rdx+78h]
0x14003db74  mov     rax, [rdx+70h]
0x14003db78  mov     qword ptr [rbp+57h+var_60], rax
0x14003db7c  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003db80  mov     qword ptr [rbp+57h+var_60+8], rcx
0x14003db84  or      esi, 0FFFFFFFFh
0x14003db87  test    rbx, rbx
0x14003db8a  jz      short loc_14003DBBF
0x14003db8c  mov     eax, esi
0x14003db8e  lock xadd [rbx+8], eax
0x14003db93  add     eax, esi
0x14003db95  jnz     short loc_14003DBBF
0x14003db97  mov     rax, [rbx]
0x14003db9a  mov     rcx, rbx
0x14003db9d  mov     rax, [rax]
0x14003dba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dba5  mov     eax, esi
0x14003dba7  lock xadd [rbx+0Ch], eax
0x14003dbac  add     eax, esi
0x14003dbae  jnz     short loc_14003DBBF
0x14003dbb0  mov     rax, [rbx]
0x14003dbb3  mov     rcx, rbx
0x14003dbb6  mov     rax, [rax+8]
0x14003dbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dbbf  lea     rax, off_14005B9F8
0x14003dbc6  mov     [rbp+57h+var_50], rax
0x14003dbca  mov     [rbp+57h+var_48], 0
0x14003dbd2  lea     rax, [rbp+57h+var_50]
0x14003dbd6  mov     [rbp+57h+var_40], rax
0x14003dbda  mov     [rbp+57h+var_38], 0
0x14003dbe2  mov     [rbp+57h+var_30], 0
0x14003dbe9  mov     [rbp+57h+var_28], 0
0x14003dbf1  mov     [rbp+57h+var_20], 0
0x14003dbf5  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14003dbfd  jz      short loc_14003DC26
0x14003dbff  mov     dl, 1
0x14003dc01  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x14003dc06  mov     [rbp+57h+var_48], rax
0x14003dc0a  test    rax, rax
0x14003dc0d  jz      short loc_14003DC26
0x14003dc0f  mov     rcx, [rax]
0x14003dc12  mov     [rbp+57h+var_38], rcx
0x14003dc16  lea     rcx, [rbp+57h+var_48]
0x14003dc1a  mov     [rax], rcx
0x14003dc1d  call    cs:__imp_GetCurrentThreadId
0x14003dc23  mov     [rbp+57h+var_30], eax
0x14003dc26  lea     rax, [rbp+57h+var_60]
0x14003dc2a  mov     [rbp+57h+var_18], rax
0x14003dc2e  xor     edx, edx; dwCoInit
0x14003dc30  xor     ecx, ecx; pvReserved
0x14003dc32  call    cs:__imp_CoInitializeEx
0x14003dc38  test    eax, eax
0x14003dc3a  js      loc_14003DDB3
0x14003dc40  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003dc47  add     rdx, 30h ; '0'
0x14003dc4b  lea     rcx, [rbp+57h+SRWLock]
0x14003dc4f  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003dc54  mov     rdx, rdi; unsigned __int64
0x14003dc57  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14003dc5b  call    ?DestroyMidiClient@CMidiClientManager@@QEAAJ_K@Z; CMidiClientManager::DestroyMidiClient(unsigned __int64)
0x14003dc60  mov     edi, eax
0x14003dc62  test    eax, eax
0x14003dc64  jns     loc_14003DD10
0x14003dc6a  mov     rcx, [rbp+5Fh]; this
0x14003dc6e  mov     r9d, eax; char *
0x14003dc71  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003dc78  mov     edx, 0E8h; void *
0x14003dc7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003dc82  call    cs:__imp_CoUninitialize
0x14003dc88  lea     rcx, [rbp+57h+var_48]; this
0x14003dc8c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14003dc91  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003dc95  test    rbx, rbx
0x14003dc98  jz      short loc_14003DCCD
0x14003dc9a  mov     eax, esi
0x14003dc9c  lock xadd [rbx+8], eax
0x14003dca1  add     eax, esi
0x14003dca3  jnz     short loc_14003DCCD
0x14003dca5  mov     rax, [rbx]
0x14003dca8  mov     rcx, rbx
0x14003dcab  mov     rax, [rax]
0x14003dcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dcb3  mov     eax, esi
0x14003dcb5  lock xadd [rbx+0Ch], eax
0x14003dcba  add     eax, esi
0x14003dcbc  jnz     short loc_14003DCCD
0x14003dcbe  mov     rax, [rbx]
0x14003dcc1  mov     rcx, rbx
0x14003dcc4  mov     rax, [rax+8]
0x14003dcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dccd  mov     rbx, [rbp+57h+SRWLock+8]
0x14003dcd1  test    rbx, rbx
0x14003dcd4  jz      short loc_14003DD09
0x14003dcd6  mov     eax, esi
0x14003dcd8  lock xadd [rbx+8], eax
0x14003dcdd  add     eax, esi
0x14003dcdf  jnz     short loc_14003DD09
0x14003dce1  mov     rax, [rbx]
0x14003dce4  mov     rcx, rbx
0x14003dce7  mov     rax, [rax]
0x14003dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dcef  mov     eax, esi
0x14003dcf1  lock xadd [rbx+0Ch], eax
0x14003dcf6  add     eax, esi
0x14003dcf8  jnz     short loc_14003DD09
0x14003dcfa  mov     rax, [rbx]
0x14003dcfd  mov     rcx, rbx
0x14003dd00  mov     rax, [rax+8]
0x14003dd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd09  mov     eax, edi
0x14003dd0b  jmp     loc_14003DDA0
0x14003dd10  xor     edx, edx; int
0x14003dd12  call    ?LogMidi2DestroyClient@CMidiSrvTraceLogger@@QEAAXJ@Z; CMidiSrvTraceLogger::LogMidi2DestroyClient(long)
0x14003dd17  call    cs:__imp_CoUninitialize
0x14003dd1d  lea     rcx, [rbp+57h+var_48]; this
0x14003dd21  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14003dd26  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003dd2a  test    rbx, rbx
0x14003dd2d  jz      short loc_14003DD62
0x14003dd2f  mov     eax, esi
0x14003dd31  lock xadd [rbx+8], eax
0x14003dd36  add     eax, esi
0x14003dd38  jnz     short loc_14003DD62
0x14003dd3a  mov     rax, [rbx]
0x14003dd3d  mov     rcx, rbx
0x14003dd40  mov     rax, [rax]
0x14003dd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd48  mov     eax, esi
0x14003dd4a  lock xadd [rbx+0Ch], eax
0x14003dd4f  add     eax, esi
0x14003dd51  jnz     short loc_14003DD62
0x14003dd53  mov     rax, [rbx]
0x14003dd56  mov     rcx, rbx
0x14003dd59  mov     rax, [rax+8]
0x14003dd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd62  mov     rbx, [rbp+57h+SRWLock+8]
0x14003dd66  test    rbx, rbx
0x14003dd69  jz      short loc_14003DD9E
0x14003dd6b  mov     eax, esi
0x14003dd6d  lock xadd [rbx+8], eax
0x14003dd72  add     eax, esi
0x14003dd74  jnz     short loc_14003DD9E
0x14003dd76  mov     rax, [rbx]
0x14003dd79  mov     rcx, rbx
0x14003dd7c  mov     rax, [rax]
0x14003dd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd84  mov     eax, esi
0x14003dd86  lock xadd [rbx+0Ch], eax
0x14003dd8b  add     eax, esi
0x14003dd8d  jnz     short loc_14003DD9E
0x14003dd8f  mov     rax, [rbx]
0x14003dd92  mov     rcx, rbx
0x14003dd95  mov     rax, [rax+8]
0x14003dd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd9e  xor     eax, eax
0x14003dda0  mov     rbx, [rsp+0B0h+arg_0]
0x14003dda8  add     rsp, 0A0h
0x14003ddaf  pop     rdi
0x14003ddb0  pop     rsi
0x14003ddb1  pop     rbp
0x14003ddb2  retn
0x14003ddb3  mov     rcx, [rbp+5Fh]; this
0x14003ddb7  mov     r9d, eax; char *
0x14003ddba  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003ddc1  mov     edx, 14D3h; void *
0x14003ddc6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
