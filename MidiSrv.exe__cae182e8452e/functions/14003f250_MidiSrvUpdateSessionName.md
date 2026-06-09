# MidiSrvUpdateSessionName

- ea: `0x14003f250`
- end: `0x14003f4bd`
- name: `MidiSrvUpdateSessionName`
- size: `621`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003f250`
- `0x14005a010`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003f2fb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003f30c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003f2fb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003f30c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f332`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f3bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f44f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f332`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f3bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f44f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f2cb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f2cb`

## string_xrefs

- `0x14003f4a8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003f26f`: `MidiSrvUpdateSessionName`
- `0x14003f316`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003f3ab`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall MidiSrvUpdateSessionName(RPC_BINDING_HANDLE Binding, __int64 a2, const char *a3, __int64 a4)
{
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  HRESULT v10; // eax
  volatile signed __int32 *v11; // rdi
  __int64 v13; // rax
  int v14; // eax
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  volatile signed __int32 *v18; // rdi
  int v19; // [rsp+20h] [rbp-60h]
  unsigned int Pid; // [rsp+40h] [rbp-40h] BYREF
  const char *v21; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-30h] BYREF
  int v23[4]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v24; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v22[0] = 0;
    v21 = (const char *)L"Enter";
    *(_QWORD *)v23 = "MidiSrvUpdateSessionName";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&byte_14008B147,
      v8,
      v9,
      v23,
      (__int64)v22,
      &v21);
  }
  v24 = 0;
  v10 = CoInitializeEx(0, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v10,
      v19);
  std::shared_ptr<CMidiSessionTracker>::operator=(&v24, (char *)g_MidiService + 96);
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(Binding, &Pid) )
  {
    a3 = (const char *)(I_RpcBindingInqLocalClientPID(Binding, &Pid) | 0x80010000);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      a3,
      v19);
    CoUninitialize();
    v11 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( !*((_QWORD *)&v24 + 1) )
      return (unsigned int)a3;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return (unsigned int)a3;
    (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) != 1 )
      return (unsigned int)a3;
    goto LABEL_8;
  }
  v13 = *(_QWORD *)v24;
  *(_OWORD *)v23 = *(_OWORD *)a3;
  v14 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, _QWORD))(v13 + 32))(v24, v23, a4, Pid);
  LODWORD(a3) = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v14,
      v19);
    CoUninitialize();
    v11 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( !*((_QWORD *)&v24 + 1) )
      return (unsigned int)a3;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return (unsigned int)a3;
    (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) != 1 )
      return (unsigned int)a3;
LABEL_8:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    return (unsigned int)a3;
  }
  v15 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v15 > 4u )
  {
    v22[0] = 0;
    *(_QWORD *)v23 = L"Exit success";
    v21 = "MidiSrvUpdateSessionName";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v15,
      (__int64)&word_14008B2AE,
      v16,
      v17,
      &v21,
      (__int64)v22,
      v23);
  }
  CoUninitialize();
  v18 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003f250  push    rbp
0x14003f252  push    rbx
0x14003f253  push    rsi
0x14003f254  push    rdi
0x14003f255  push    r15
0x14003f257  mov     rbp, rsp
0x14003f25a  sub     rsp, 80h
0x14003f261  mov     rdi, r9
0x14003f264  mov     rsi, r8
0x14003f267  mov     rbx, rcx
0x14003f26a  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f26f  lea     r15, aMidisrvupdates; "MidiSrvUpdateSessionName"
0x14003f276  mov     rcx, [rax+8]
0x14003f27a  mov     eax, [rcx]
0x14003f27c  cmp     eax, 4
0x14003f27f  jbe     short loc_14003F2BF
0x14003f281  lea     rax, aEnter; "Enter"
0x14003f288  mov     [rbp+var_30], 0
0x14003f290  mov     [rbp+var_38], rax
0x14003f294  lea     rdx, byte_14008B147
0x14003f29b  lea     rax, [rbp+var_38]
0x14003f29f  mov     qword ptr [rbp+var_20], r15
0x14003f2a3  mov     [rsp+80h+var_50], rax
0x14003f2a8  lea     rax, [rbp+var_30]
0x14003f2ac  mov     [rsp+80h+var_58], rax
0x14003f2b1  lea     rax, [rbp+var_20]
0x14003f2b5  mov     qword ptr [rsp+80h+var_60], rax; int
0x14003f2ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003f2bf  xorps   xmm0, xmm0
0x14003f2c2  xor     edx, edx; dwCoInit
0x14003f2c4  xor     ecx, ecx; pvReserved
0x14003f2c6  movdqu  [rbp+var_10], xmm0
0x14003f2cb  call    cs:__imp_CoInitializeEx
0x14003f2d1  test    eax, eax
0x14003f2d3  js      loc_14003F4A4
0x14003f2d9  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003f2e0  lea     rcx, [rbp+var_10]
0x14003f2e4  add     rdx, 60h ; '`'
0x14003f2e8  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003f2ed  lea     rdx, [rbp+Pid]; Pid
0x14003f2f1  mov     [rbp+Pid], 0
0x14003f2f8  mov     rcx, rbx; Binding
0x14003f2fb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003f301  test    eax, eax
0x14003f303  jz      short loc_14003F37E
0x14003f305  lea     rdx, [rbp+Pid]; Pid
0x14003f309  mov     rcx, rbx; Binding
0x14003f30c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003f312  mov     rcx, [rbp+28h]; this
0x14003f316  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003f31d  mov     esi, eax
0x14003f31f  mov     edx, 186h; void *
0x14003f324  or      esi, 80010000h
0x14003f32a  mov     r9d, esi; char *
0x14003f32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f332  call    cs:__imp_CoUninitialize
0x14003f338  mov     rdi, qword ptr [rbp+var_10+8]
0x14003f33c  test    rdi, rdi
0x14003f33f  jz      short loc_14003F377
0x14003f341  or      ebx, 0FFFFFFFFh
0x14003f344  mov     eax, ebx
0x14003f346  lock xadd [rdi+8], eax
0x14003f34b  add     eax, ebx
0x14003f34d  jnz     short loc_14003F377
0x14003f34f  mov     rax, [rdi]
0x14003f352  mov     rcx, rdi
0x14003f355  mov     rax, [rax]
0x14003f358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f35d  mov     edx, ebx
0x14003f35f  lock xadd [rdi+0Ch], edx
0x14003f364  add     edx, ebx
0x14003f366  jnz     short loc_14003F377
0x14003f368  mov     rdx, [rdi]
0x14003f36b  mov     rax, [rdx+8]
0x14003f36f  mov     rcx, rdi
0x14003f372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f377  mov     eax, esi
0x14003f379  jmp     loc_14003F496
0x14003f37e  mov     rcx, qword ptr [rbp+var_10]
0x14003f382  lea     rdx, [rbp+var_20]
0x14003f386  movups  xmm0, xmmword ptr [rsi]
0x14003f389  mov     r9d, [rbp+Pid]
0x14003f38d  mov     r8, rdi
0x14003f390  mov     rax, [rcx]
0x14003f393  movdqu  xmmword ptr [rbp+var_20], xmm0
0x14003f398  mov     rax, [rax+20h]
0x14003f39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f3a1  mov     esi, eax
0x14003f3a3  test    eax, eax
0x14003f3a5  jns     short loc_14003F401
0x14003f3a7  mov     rcx, [rbp+28h]; this
0x14003f3ab  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003f3b2  mov     r9d, eax; char *
0x14003f3b5  mov     edx, 188h; void *
0x14003f3ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003f3bf  call    cs:__imp_CoUninitialize
0x14003f3c5  mov     rdi, qword ptr [rbp+var_10+8]
0x14003f3c9  test    rdi, rdi
0x14003f3cc  jz      short loc_14003F377
0x14003f3ce  or      ebx, 0FFFFFFFFh
0x14003f3d1  mov     eax, ebx
0x14003f3d3  lock xadd [rdi+8], eax
0x14003f3d8  add     eax, ebx
0x14003f3da  jnz     short loc_14003F377
0x14003f3dc  mov     rax, [rdi]
0x14003f3df  mov     rcx, rdi
0x14003f3e2  mov     rax, [rax]
0x14003f3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f3ea  mov     eax, ebx
0x14003f3ec  lock xadd [rdi+0Ch], eax
0x14003f3f1  add     eax, ebx
0x14003f3f3  jnz     short loc_14003F377
0x14003f3f5  mov     rax, [rdi]
0x14003f3f8  mov     rax, [rax+8]
0x14003f3fc  jmp     loc_14003F36F
0x14003f401  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f406  mov     rcx, [rax+8]
0x14003f40a  mov     eax, [rcx]
0x14003f40c  cmp     eax, 4
0x14003f40f  jbe     short loc_14003F44F
0x14003f411  lea     rax, aExitSuccess_0; "Exit success"
0x14003f418  mov     [rbp+var_30], 0
0x14003f420  mov     qword ptr [rbp+var_20], rax
0x14003f424  lea     rdx, word_14008B2AE
0x14003f42b  lea     rax, [rbp+var_20]
0x14003f42f  mov     [rbp+var_38], r15
0x14003f433  mov     [rsp+80h+var_50], rax
0x14003f438  lea     rax, [rbp+var_30]
0x14003f43c  mov     [rsp+80h+var_58], rax
0x14003f441  lea     rax, [rbp+var_38]
0x14003f445  mov     qword ptr [rsp+80h+var_60], rax
0x14003f44a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003f44f  call    cs:__imp_CoUninitialize
0x14003f455  mov     rdi, qword ptr [rbp+var_10+8]
0x14003f459  test    rdi, rdi
0x14003f45c  jz      short loc_14003F494
0x14003f45e  or      ebx, 0FFFFFFFFh
0x14003f461  mov     eax, ebx
0x14003f463  lock xadd [rdi+8], eax
0x14003f468  add     eax, ebx
0x14003f46a  jnz     short loc_14003F494
0x14003f46c  mov     rax, [rdi]
0x14003f46f  mov     rcx, rdi
0x14003f472  mov     rax, [rax]
0x14003f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f47a  mov     eax, ebx
0x14003f47c  lock xadd [rdi+0Ch], eax
0x14003f481  add     eax, ebx
0x14003f483  jnz     short loc_14003F494
0x14003f485  mov     rax, [rdi]
0x14003f488  mov     rcx, rdi
0x14003f48b  mov     rax, [rax+8]
0x14003f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f494  xor     eax, eax
0x14003f496  add     rsp, 80h
0x14003f49d  pop     r15
0x14003f49f  pop     rdi
0x14003f4a0  pop     rsi
0x14003f4a1  pop     rbx
0x14003f4a2  pop     rbp
0x14003f4a3  retn
0x14003f4a4  mov     rcx, [rbp+28h]; this
0x14003f4a8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003f4af  mov     r9d, eax; char *
0x14003f4b2  mov     edx, 14D3h; void *
0x14003f4b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
