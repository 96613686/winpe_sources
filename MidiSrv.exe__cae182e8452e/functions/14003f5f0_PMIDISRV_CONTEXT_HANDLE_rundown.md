# PMIDISRV_CONTEXT_HANDLE_rundown

- ea: `0x14003f5f0`
- end: `0x14003f729`
- name: `PMIDISRV_CONTEXT_HANDLE_rundown`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001ad4`
- `0x14000984c`
- `0x14000c598`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003f5f0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f6bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f6bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f66e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f66e`

## string_xrefs

- `0x14003f714`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003f6ab`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
void __fastcall PMIDISRV_CONTEXT_HANDLE_rundown(__int64 a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  HRESULT v5; // eax
  int v6; // eax
  volatile signed __int32 *v7; // rbx
  int v8; // [rsp+20h] [rbp-30h]
  int v9[4]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  const wchar_t *v11; // [rsp+70h] [rbp+20h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v11 = L"Enter context handle rundown";
    v12 = 0;
    *(_QWORD *)v9 = "PMIDISRV_CONTEXT_HANDLE_rundown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (__int64)v2,
      (__int64)byte_14008B1DD,
      v3,
      v4,
      v9,
      (__int64)&v12,
      &v11);
  }
  *(_OWORD *)v9 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v5,
      v8);
  std::shared_ptr<CMidiSessionTracker>::operator=(v9, (char *)g_MidiService + 96);
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v9 + 56LL))(*(_QWORD *)v9, a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DB,
      (int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v6);
  CoUninitialize();
  v7 = *(volatile signed __int32 **)&v9[2];
  if ( *(_QWORD *)&v9[2]
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v9[2] + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  }
}

```

## disassembly

```asm
0x14003f5f0  mov     [rsp-8+arg_0], rbx
0x14003f5f5  push    rbp
0x14003f5f6  mov     rbp, rsp
0x14003f5f9  sub     rsp, 50h
0x14003f5fd  mov     rbx, rcx
0x14003f600  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f605  mov     rcx, [rax+8]
0x14003f609  mov     eax, [rcx]
0x14003f60b  cmp     eax, 4
0x14003f60e  jbe     short loc_14003F662
0x14003f610  lea     rax, aEnterContextHa; "Enter context handle rundown"
0x14003f617  mov     [rbp+arg_8], rbx
0x14003f61b  mov     [rbp+arg_10], rax
0x14003f61f  lea     rdx, byte_14008B1DD
0x14003f626  lea     rax, aPmidisrvContex; "PMIDISRV_CONTEXT_HANDLE_rundown"
0x14003f62d  mov     [rbp+arg_18], 0
0x14003f635  mov     qword ptr [rbp+var_10], rax
0x14003f639  lea     rax, [rbp+arg_8]
0x14003f63d  mov     [rsp+50h+var_18], rax
0x14003f642  lea     rax, [rbp+arg_10]
0x14003f646  mov     [rsp+50h+var_20], rax
0x14003f64b  lea     rax, [rbp+arg_18]
0x14003f64f  mov     [rsp+50h+var_28], rax
0x14003f654  lea     rax, [rbp+var_10]
0x14003f658  mov     qword ptr [rsp+50h+var_30], rax; int
0x14003f65d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14003f662  xorps   xmm0, xmm0
0x14003f665  xor     edx, edx; dwCoInit
0x14003f667  xor     ecx, ecx; pvReserved
0x14003f669  movdqu  xmmword ptr [rbp+var_10], xmm0
0x14003f66e  call    cs:__imp_CoInitializeEx
0x14003f674  test    eax, eax
0x14003f676  js      loc_14003F710
0x14003f67c  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003f683  lea     rcx, [rbp+var_10]
0x14003f687  add     rdx, 60h ; '`'
0x14003f68b  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003f690  mov     rcx, qword ptr [rbp+var_10]
0x14003f694  mov     rdx, rbx
0x14003f697  mov     rax, [rcx]
0x14003f69a  mov     rax, [rax+38h]
0x14003f69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f6a3  test    eax, eax
0x14003f6a5  jns     short loc_14003F6BF
0x14003f6a7  mov     rcx, [rbp+8]; this
0x14003f6ab  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003f6b2  mov     r9d, eax; char *
0x14003f6b5  mov     edx, 1DBh; void *
0x14003f6ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003f6bf  call    cs:__imp_CoUninitialize
0x14003f6c5  mov     rbx, qword ptr [rbp+var_10+8]
0x14003f6c9  test    rbx, rbx
0x14003f6cc  jz      short loc_14003F705
0x14003f6ce  or      eax, 0FFFFFFFFh
0x14003f6d1  lock xadd [rbx+8], eax
0x14003f6d6  cmp     eax, 1
0x14003f6d9  jnz     short loc_14003F705
0x14003f6db  mov     rax, [rbx]
0x14003f6de  mov     rcx, rbx
0x14003f6e1  mov     rax, [rax]
0x14003f6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f6e9  or      eax, 0FFFFFFFFh
0x14003f6ec  lock xadd [rbx+0Ch], eax
0x14003f6f1  cmp     eax, 1
0x14003f6f4  jnz     short loc_14003F705
0x14003f6f6  mov     rax, [rbx]
0x14003f6f9  mov     rcx, rbx
0x14003f6fc  mov     rax, [rax+8]
0x14003f700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f705  mov     rbx, [rsp+50h+arg_0]
0x14003f70a  add     rsp, 50h
0x14003f70e  pop     rbp
0x14003f70f  retn
0x14003f710  mov     rcx, [rbp+8]; this
0x14003f714  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003f71b  mov     r9d, eax; char *
0x14003f71e  mov     edx, 14D3h; void *
0x14003f723  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
