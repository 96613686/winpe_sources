# MidiSrvVerifyConnectivity

- ea: `0x14003f4d0`
- end: `0x14003f5db`
- name: `MidiSrvVerifyConnectivity`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x1400144ac`
- `0x1400261b4`
- `0x14003c250`
- `0x14003f4d0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f56d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f56d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f542`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003f542`

## string_xrefs

- `0x14003f5c6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 MidiSrvVerifyConnectivity()
{
  _DWORD *v0; // rcx
  __int64 v1; // r8
  __int64 v2; // r9
  HRESULT v3; // eax
  unsigned int v4; // edi
  volatile signed __int32 *v5; // rbx
  int v7; // [rsp+20h] [rbp-38h]
  CMidiSessionTracker *v8[2]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const wchar_t *v10; // [rsp+68h] [rbp+10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  const char *v12; // [rsp+78h] [rbp+20h] BYREF

  v0 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v0 > 4u )
  {
    v11 = 0;
    v10 = L"Enter";
    v12 = "MidiSrvVerifyConnectivity";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v0,
      (__int64)byte_14008B115,
      v1,
      v2,
      &v12,
      (__int64)&v11,
      &v10);
  }
  *(_OWORD *)v8 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      v7);
  std::shared_ptr<CMidiSessionTracker>::operator=(v8, (char *)g_MidiService + 96);
  v4 = CMidiSessionTracker::VerifyConnectivity(v8[0]);
  CoUninitialize();
  v5 = (volatile signed __int32 *)v8[1];
  if ( v8[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14003f4d0  mov     [rsp+arg_0], rbx
0x14003f4d5  push    rdi
0x14003f4d6  sub     rsp, 50h
0x14003f4da  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f4df  mov     rcx, [rax+8]
0x14003f4e3  mov     eax, [rcx]
0x14003f4e5  cmp     eax, 4
0x14003f4e8  jbe     short loc_14003F535
0x14003f4ea  lea     rax, aEnter; "Enter"
0x14003f4f1  mov     [rsp+58h+arg_10], 0
0x14003f4fa  mov     [rsp+58h+arg_8], rax
0x14003f4ff  lea     rdx, byte_14008B115
0x14003f506  lea     rax, aMidisrvverifyc; "MidiSrvVerifyConnectivity"
0x14003f50d  mov     [rsp+58h+arg_18], rax
0x14003f512  lea     rax, [rsp+58h+arg_8]
0x14003f517  mov     [rsp+58h+var_28], rax
0x14003f51c  lea     rax, [rsp+58h+arg_10]
0x14003f521  mov     [rsp+58h+var_30], rax
0x14003f526  lea     rax, [rsp+58h+arg_18]
0x14003f52b  mov     qword ptr [rsp+58h+var_38], rax; int
0x14003f530  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003f535  xorps   xmm0, xmm0
0x14003f538  xor     edx, edx; dwCoInit
0x14003f53a  xor     ecx, ecx; pvReserved
0x14003f53c  movdqu  xmmword ptr [rsp+58h+var_18], xmm0
0x14003f542  call    cs:__imp_CoInitializeEx
0x14003f548  test    eax, eax
0x14003f54a  js      short loc_14003F5C1
0x14003f54c  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003f553  lea     rcx, [rsp+58h+var_18]
0x14003f558  add     rdx, 60h ; '`'
0x14003f55c  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003f561  mov     rcx, [rsp+58h+var_18]; this
0x14003f566  call    ?VerifyConnectivity@CMidiSessionTracker@@QEAAHXZ; CMidiSessionTracker::VerifyConnectivity(void)
0x14003f56b  mov     edi, eax
0x14003f56d  call    cs:__imp_CoUninitialize
0x14003f573  mov     rbx, [rsp+58h+var_18+8]
0x14003f578  test    rbx, rbx
0x14003f57b  jz      short loc_14003F5B4
0x14003f57d  or      ecx, 0FFFFFFFFh
0x14003f580  lock xadd [rbx+8], ecx
0x14003f585  cmp     ecx, 1
0x14003f588  jnz     short loc_14003F5B4
0x14003f58a  mov     rdx, [rbx]
0x14003f58d  mov     rcx, rbx
0x14003f590  mov     rax, [rdx]
0x14003f593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f598  or      eax, 0FFFFFFFFh
0x14003f59b  lock xadd [rbx+0Ch], eax
0x14003f5a0  cmp     eax, 1
0x14003f5a3  jnz     short loc_14003F5B4
0x14003f5a5  mov     rax, [rbx]
0x14003f5a8  mov     rcx, rbx
0x14003f5ab  mov     rax, [rax+8]
0x14003f5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f5b4  mov     rbx, [rsp+58h+arg_0]
0x14003f5b9  mov     eax, edi
0x14003f5bb  add     rsp, 50h
0x14003f5bf  pop     rdi
0x14003f5c0  retn
0x14003f5c1  mov     rcx, [rsp+58h]; this
0x14003f5c6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003f5cd  mov     r9d, eax; char *
0x14003f5d0  mov     edx, 14D3h; void *
0x14003f5d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
