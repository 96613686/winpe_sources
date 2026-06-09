# MidiSrvGetSessionList

- ea: `0x14003dde0`
- end: `0x14003dfe5`
- name: `MidiSrvGetSessionList`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003cdec`
- `0x14003dde0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003deb0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003df73`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003deb0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003df73`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003de54`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003de54`

## string_xrefs

- `0x14003dfd0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003de9c`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003df11`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall MidiSrvGetSessionList(__int64 a1, unsigned __int16 **a2)
{
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  HRESULT v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  volatile signed __int32 *v9; // rbx
  int v11; // eax
  _DWORD *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  volatile signed __int32 *v15; // rbx
  int v16; // [rsp+20h] [rbp-40h]
  const char *v17; // [rsp+40h] [rbp-20h] BYREF
  int v18[2]; // [rsp+48h] [rbp-18h] BYREF
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int16 *v21; // [rsp+90h] [rbp+30h] BYREF
  const wchar_t *v22; // [rsp+98h] [rbp+38h] BYREF

  v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v3 > 4u )
  {
    v17 = 0;
    v22 = L"Enter";
    *(_QWORD *)v18 = "MidiSrvGetSessionList";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)byte_14008B179,
      v4,
      v5,
      v18,
      (__int64)&v17,
      &v22);
  }
  v19 = 0;
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v6,
      v16);
  std::shared_ptr<CMidiSessionTracker>::operator=(&v19, (char *)g_MidiService + 96);
  v21 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)v19 + 64LL))(v19, &v21);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = CopyStringToOutputParameter(v21, a2);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1FE,
        (int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
        (const char *)(unsigned int)v11);
    v12 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v12 > 4u )
    {
      *(_QWORD *)v18 = 0;
      v22 = L"Exit success";
      v17 = "MidiSrvGetSessionList";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v12,
        (__int64)byte_14008B0E3,
        v13,
        v14,
        &v17,
        (__int64)v18,
        &v22);
    }
    CoUninitialize();
    v15 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)(unsigned int)v7,
      v16);
    CoUninitialize();
    v9 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    return v8;
  }
}

```

## disassembly

```asm
0x14003dde0  mov     [rsp-18h+arg_0], rbx
0x14003dde5  push    rbp
0x14003dde6  push    rsi
0x14003dde7  push    r14
0x14003dde9  mov     rbp, rsp
0x14003ddec  sub     rsp, 60h
0x14003ddf0  mov     rbx, rdx
0x14003ddf3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003ddf8  lea     r14, aMidisrvgetsess; "MidiSrvGetSessionList"
0x14003ddff  mov     rcx, [rax+8]
0x14003de03  mov     eax, [rcx]
0x14003de05  cmp     eax, 4
0x14003de08  jbe     short loc_14003DE48
0x14003de0a  lea     rax, aEnter; "Enter"
0x14003de11  mov     [rbp+var_20], 0
0x14003de19  mov     [rbp+arg_18], rax
0x14003de1d  lea     rdx, byte_14008B179
0x14003de24  lea     rax, [rbp+arg_18]
0x14003de28  mov     qword ptr [rbp+var_18], r14
0x14003de2c  mov     [rsp+60h+var_30], rax
0x14003de31  lea     rax, [rbp+var_20]
0x14003de35  mov     [rsp+60h+var_38], rax
0x14003de3a  lea     rax, [rbp+var_18]
0x14003de3e  mov     qword ptr [rsp+60h+var_40], rax; int
0x14003de43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003de48  xorps   xmm0, xmm0
0x14003de4b  xor     edx, edx; dwCoInit
0x14003de4d  xor     ecx, ecx; pvReserved
0x14003de4f  movdqu  [rbp+var_10], xmm0
0x14003de54  call    cs:__imp_CoInitializeEx
0x14003de5a  test    eax, eax
0x14003de5c  js      loc_14003DFCC
0x14003de62  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003de69  lea     rcx, [rbp+var_10]
0x14003de6d  add     rdx, 60h ; '`'
0x14003de71  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003de76  mov     rcx, qword ptr [rbp+var_10]
0x14003de7a  lea     rdx, [rbp+arg_10]
0x14003de7e  mov     [rbp+arg_10], 0
0x14003de86  mov     rax, [rcx]
0x14003de89  mov     rax, [rax+40h]
0x14003de8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003de92  mov     esi, eax
0x14003de94  test    eax, eax
0x14003de96  jns     short loc_14003DEFD
0x14003de98  mov     rcx, [rbp+18h]; this
0x14003de9c  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003dea3  mov     r9d, eax; char *
0x14003dea6  mov     edx, 1FCh; void *
0x14003deab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003deb0  call    cs:__imp_CoUninitialize
0x14003deb6  mov     rbx, qword ptr [rbp+var_10+8]
0x14003deba  test    rbx, rbx
0x14003debd  jz      short loc_14003DEF6
0x14003debf  or      eax, 0FFFFFFFFh
0x14003dec2  lock xadd [rbx+8], eax
0x14003dec7  cmp     eax, 1
0x14003deca  jnz     short loc_14003DEF6
0x14003decc  mov     rax, [rbx]
0x14003decf  mov     rcx, rbx
0x14003ded2  mov     rax, [rax]
0x14003ded5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003deda  or      eax, 0FFFFFFFFh
0x14003dedd  lock xadd [rbx+0Ch], eax
0x14003dee2  cmp     eax, 1
0x14003dee5  jnz     short loc_14003DEF6
0x14003dee7  mov     rax, [rbx]
0x14003deea  mov     rcx, rbx
0x14003deed  mov     rax, [rax+8]
0x14003def1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003def6  mov     eax, esi
0x14003def8  jmp     loc_14003DFBB
0x14003defd  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x14003df01  mov     rdx, rbx; unsigned __int16 **
0x14003df04  call    ?CopyStringToOutputParameter@@YAJPEBGPEAPEAG@Z; CopyStringToOutputParameter(ushort const *,ushort * *)
0x14003df09  test    eax, eax
0x14003df0b  jns     short loc_14003DF25
0x14003df0d  mov     rcx, [rbp+18h]; this
0x14003df11  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003df18  mov     r9d, eax; char *
0x14003df1b  mov     edx, 1FEh; void *
0x14003df20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003df25  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003df2a  mov     rcx, [rax+8]
0x14003df2e  mov     eax, [rcx]
0x14003df30  cmp     eax, 4
0x14003df33  jbe     short loc_14003DF73
0x14003df35  lea     rax, aExitSuccess_0; "Exit success"
0x14003df3c  mov     qword ptr [rbp+var_18], 0
0x14003df44  mov     [rbp+arg_18], rax
0x14003df48  lea     rdx, byte_14008B0E3
0x14003df4f  lea     rax, [rbp+arg_18]
0x14003df53  mov     [rbp+var_20], r14
0x14003df57  mov     [rsp+60h+var_30], rax
0x14003df5c  lea     rax, [rbp+var_18]
0x14003df60  mov     [rsp+60h+var_38], rax
0x14003df65  lea     rax, [rbp+var_20]
0x14003df69  mov     qword ptr [rsp+60h+var_40], rax
0x14003df6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003df73  call    cs:__imp_CoUninitialize
0x14003df79  mov     rbx, qword ptr [rbp+var_10+8]
0x14003df7d  test    rbx, rbx
0x14003df80  jz      short loc_14003DFB9
0x14003df82  or      eax, 0FFFFFFFFh
0x14003df85  lock xadd [rbx+8], eax
0x14003df8a  cmp     eax, 1
0x14003df8d  jnz     short loc_14003DFB9
0x14003df8f  mov     rax, [rbx]
0x14003df92  mov     rcx, rbx
0x14003df95  mov     rax, [rax]
0x14003df98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df9d  or      eax, 0FFFFFFFFh
0x14003dfa0  lock xadd [rbx+0Ch], eax
0x14003dfa5  cmp     eax, 1
0x14003dfa8  jnz     short loc_14003DFB9
0x14003dfaa  mov     rax, [rbx]
0x14003dfad  mov     rcx, rbx
0x14003dfb0  mov     rax, [rax+8]
0x14003dfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dfb9  xor     eax, eax
0x14003dfbb  mov     rbx, [rsp+60h+arg_0]
0x14003dfc3  add     rsp, 60h
0x14003dfc7  pop     r14
0x14003dfc9  pop     rsi
0x14003dfca  pop     rbp
0x14003dfcb  retn
0x14003dfcc  mov     rcx, [rbp+18h]; this
0x14003dfd0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003dfd7  mov     r9d, eax; char *
0x14003dfda  mov     edx, 14D3h; void *
0x14003dfdf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
