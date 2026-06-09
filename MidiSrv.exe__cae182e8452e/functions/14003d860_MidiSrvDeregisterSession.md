# MidiSrvDeregisterSession

- ea: `0x14003d860`
- end: `0x14003dad2`
- name: `MidiSrvDeregisterSession`
- size: `626`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003d860`
- `0x14005a010`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d90c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d91d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d90c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14003d91d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d943`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d9cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003da5d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d943`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d9cd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003da5d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003d8dc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003d8dc`

## string_xrefs

- `0x14003dabd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003d927`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003d9b9`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall MidiSrvDeregisterSession(RPC_BINDING_HANDLE Binding, __int64 a2, _OWORD *a3)
{
  _DWORD *v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  HRESULT v8; // eax
  const char *v9; // rsi
  volatile signed __int32 *v10; // rdi
  __int64 v12; // rax
  int v13; // eax
  _DWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  volatile signed __int32 *v17; // rdi
  int v18; // [rsp+20h] [rbp-50h]
  const char *v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  int v21[4]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v22; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned int Pid; // [rsp+A8h] [rbp+38h] BYREF

  v5 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v20 = 0;
    v19 = (const char *)L"Enter";
    *(_QWORD *)v21 = "MidiSrvDeregisterSession";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_14008B3A9,
      v6,
      v7,
      v21,
      (__int64)&v20,
      &v19);
  }
  v22 = 0;
  v8 = CoInitializeEx(0, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      v18);
  std::shared_ptr<CMidiSessionTracker>::operator=(&v22, (char *)g_MidiService + 96);
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(Binding, &Pid) )
  {
    v9 = (const char *)(I_RpcBindingInqLocalClientPID(Binding, &Pid) | 0x80010000);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      v9,
      v18);
    CoUninitialize();
    v10 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( !*((_QWORD *)&v22 + 1) )
      return (unsigned int)v9;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return (unsigned int)v9;
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) != 1 )
      return (unsigned int)v9;
    goto LABEL_8;
  }
  v12 = *(_QWORD *)v22;
  *(_OWORD *)v21 = *a3;
  v13 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(v12 + 40))(v22, v21, Pid);
  LODWORD(v9) = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v13,
      v18);
    CoUninitialize();
    v10 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( !*((_QWORD *)&v22 + 1) )
      return (unsigned int)v9;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) != 1 )
      return (unsigned int)v9;
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) != 1 )
      return (unsigned int)v9;
LABEL_8:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    return (unsigned int)v9;
  }
  v14 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    v20 = 0;
    *(_QWORD *)v21 = L"Exit success";
    v19 = "MidiSrvDeregisterSession";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v14,
      (__int64)word_14008B24A,
      v15,
      v16,
      &v19,
      (__int64)&v20,
      v21);
  }
  CoUninitialize();
  v17 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  if ( *((_QWORD *)&v22 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003d860  mov     [rsp-18h+arg_0], rbx
0x14003d865  mov     [rsp-18h+arg_8], rsi
0x14003d86a  push    rbp
0x14003d86b  push    rdi
0x14003d86c  push    r15
0x14003d86e  mov     rbp, rsp
0x14003d871  sub     rsp, 70h
0x14003d875  mov     rdi, r8
0x14003d878  mov     rbx, rcx
0x14003d87b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003d880  lea     r15, aMidisrvderegis; "MidiSrvDeregisterSession"
0x14003d887  mov     rcx, [rax+8]
0x14003d88b  mov     eax, [rcx]
0x14003d88d  cmp     eax, 4
0x14003d890  jbe     short loc_14003D8D0
0x14003d892  lea     rax, aEnter; "Enter"
0x14003d899  mov     [rbp+var_28], 0
0x14003d8a1  mov     [rbp+var_30], rax
0x14003d8a5  lea     rdx, byte_14008B3A9
0x14003d8ac  lea     rax, [rbp+var_30]
0x14003d8b0  mov     qword ptr [rbp+var_20], r15
0x14003d8b4  mov     [rsp+70h+var_40], rax
0x14003d8b9  lea     rax, [rbp+var_28]
0x14003d8bd  mov     [rsp+70h+var_48], rax
0x14003d8c2  lea     rax, [rbp+var_20]
0x14003d8c6  mov     qword ptr [rsp+70h+var_50], rax; int
0x14003d8cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003d8d0  xorps   xmm0, xmm0
0x14003d8d3  xor     edx, edx; dwCoInit
0x14003d8d5  xor     ecx, ecx; pvReserved
0x14003d8d7  movdqu  [rbp+var_10], xmm0
0x14003d8dc  call    cs:__imp_CoInitializeEx
0x14003d8e2  test    eax, eax
0x14003d8e4  js      loc_14003DAB9
0x14003d8ea  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003d8f1  lea     rcx, [rbp+var_10]
0x14003d8f5  add     rdx, 60h ; '`'
0x14003d8f9  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003d8fe  lea     rdx, [rbp+Pid]; Pid
0x14003d902  mov     [rbp+Pid], 0
0x14003d909  mov     rcx, rbx; Binding
0x14003d90c  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003d912  test    eax, eax
0x14003d914  jz      short loc_14003D98F
0x14003d916  lea     rdx, [rbp+Pid]; Pid
0x14003d91a  mov     rcx, rbx; Binding
0x14003d91d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14003d923  mov     rcx, [rbp+18h]; this
0x14003d927  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003d92e  mov     esi, eax
0x14003d930  mov     edx, 1AFh; void *
0x14003d935  or      esi, 80010000h
0x14003d93b  mov     r9d, esi; char *
0x14003d93e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d943  call    cs:__imp_CoUninitialize
0x14003d949  mov     rdi, qword ptr [rbp+var_10+8]
0x14003d94d  test    rdi, rdi
0x14003d950  jz      short loc_14003D988
0x14003d952  or      ebx, 0FFFFFFFFh
0x14003d955  mov     eax, ebx
0x14003d957  lock xadd [rdi+8], eax
0x14003d95c  add     eax, ebx
0x14003d95e  jnz     short loc_14003D988
0x14003d960  mov     rax, [rdi]
0x14003d963  mov     rcx, rdi
0x14003d966  mov     rax, [rax]
0x14003d969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d96e  mov     edx, ebx
0x14003d970  lock xadd [rdi+0Ch], edx
0x14003d975  add     edx, ebx
0x14003d977  jnz     short loc_14003D988
0x14003d979  mov     rdx, [rdi]
0x14003d97c  mov     rax, [rdx+8]
0x14003d980  mov     rcx, rdi
0x14003d983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d988  mov     eax, esi
0x14003d98a  jmp     loc_14003DAA4
0x14003d98f  mov     rcx, qword ptr [rbp+var_10]
0x14003d993  lea     rdx, [rbp+var_20]
0x14003d997  movups  xmm0, xmmword ptr [rdi]
0x14003d99a  mov     r8d, [rbp+Pid]
0x14003d99e  mov     rax, [rcx]
0x14003d9a1  movdqu  xmmword ptr [rbp+var_20], xmm0
0x14003d9a6  mov     rax, [rax+28h]
0x14003d9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d9af  mov     esi, eax
0x14003d9b1  test    eax, eax
0x14003d9b3  jns     short loc_14003DA0F
0x14003d9b5  mov     rcx, [rbp+18h]; this
0x14003d9b9  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003d9c0  mov     r9d, eax; char *
0x14003d9c3  mov     edx, 1B1h; void *
0x14003d9c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d9cd  call    cs:__imp_CoUninitialize
0x14003d9d3  mov     rdi, qword ptr [rbp+var_10+8]
0x14003d9d7  test    rdi, rdi
0x14003d9da  jz      short loc_14003D988
0x14003d9dc  or      ebx, 0FFFFFFFFh
0x14003d9df  mov     eax, ebx
0x14003d9e1  lock xadd [rdi+8], eax
0x14003d9e6  add     eax, ebx
0x14003d9e8  jnz     short loc_14003D988
0x14003d9ea  mov     rax, [rdi]
0x14003d9ed  mov     rcx, rdi
0x14003d9f0  mov     rax, [rax]
0x14003d9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d9f8  mov     eax, ebx
0x14003d9fa  lock xadd [rdi+0Ch], eax
0x14003d9ff  add     eax, ebx
0x14003da01  jnz     short loc_14003D988
0x14003da03  mov     rax, [rdi]
0x14003da06  mov     rax, [rax+8]
0x14003da0a  jmp     loc_14003D980
0x14003da0f  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003da14  mov     rcx, [rax+8]
0x14003da18  mov     eax, [rcx]
0x14003da1a  cmp     eax, 4
0x14003da1d  jbe     short loc_14003DA5D
0x14003da1f  lea     rax, aExitSuccess_0; "Exit success"
0x14003da26  mov     [rbp+var_28], 0
0x14003da2e  mov     qword ptr [rbp+var_20], rax
0x14003da32  lea     rdx, word_14008B24A
0x14003da39  lea     rax, [rbp+var_20]
0x14003da3d  mov     [rbp+var_30], r15
0x14003da41  mov     [rsp+70h+var_40], rax
0x14003da46  lea     rax, [rbp+var_28]
0x14003da4a  mov     [rsp+70h+var_48], rax
0x14003da4f  lea     rax, [rbp+var_30]
0x14003da53  mov     qword ptr [rsp+70h+var_50], rax
0x14003da58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003da5d  call    cs:__imp_CoUninitialize
0x14003da63  mov     rdi, qword ptr [rbp+var_10+8]
0x14003da67  test    rdi, rdi
0x14003da6a  jz      short loc_14003DAA2
0x14003da6c  or      ebx, 0FFFFFFFFh
0x14003da6f  mov     eax, ebx
0x14003da71  lock xadd [rdi+8], eax
0x14003da76  add     eax, ebx
0x14003da78  jnz     short loc_14003DAA2
0x14003da7a  mov     rax, [rdi]
0x14003da7d  mov     rcx, rdi
0x14003da80  mov     rax, [rax]
0x14003da83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003da88  mov     eax, ebx
0x14003da8a  lock xadd [rdi+0Ch], eax
0x14003da8f  add     eax, ebx
0x14003da91  jnz     short loc_14003DAA2
0x14003da93  mov     rax, [rdi]
0x14003da96  mov     rcx, rdi
0x14003da99  mov     rax, [rax+8]
0x14003da9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003daa2  xor     eax, eax
0x14003daa4  lea     r11, [rsp+70h+var_s0]
0x14003daa9  mov     rbx, [r11+20h]
0x14003daad  mov     rsi, [r11+28h]
0x14003dab1  mov     rsp, r11
0x14003dab4  pop     r15
0x14003dab6  pop     rdi
0x14003dab7  pop     rbp
0x14003dab8  retn
0x14003dab9  mov     rcx, [rbp+18h]; this
0x14003dabd  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003dac4  mov     r9d, eax; char *
0x14003dac7  mov     edx, 14D3h; void *
0x14003dacc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
