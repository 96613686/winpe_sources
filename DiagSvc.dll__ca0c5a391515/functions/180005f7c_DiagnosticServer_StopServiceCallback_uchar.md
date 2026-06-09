# DiagnosticServer::StopServiceCallback(uchar)

- ea: `0x180005f7c`
- end: `0x180006075`
- name: `?StopServiceCallback@DiagnosticServer@@IEAAXE@Z`
- size: `249`
- prototype: `void __fastcall(DiagnosticServer *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180005e90`

## callees

- `0x180001178`
- `0x180001720`
- `0x1800054cc`
- `0x180005768`
- `0x180005f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006067`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006067`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f94`

## string_xrefs

- `0x180005fda`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005fe5`: `DiagnosticServer::StopServiceCallback`
- `0x180005ff0`: `Clean up on stop service callback`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagnosticServer::StopServiceCallback(struct _RTL_CRITICAL_SECTION *this, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // [rsp+50h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+58h] [rbp-8h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h]
  const char *v14; // [rsp+90h] [rbp+30h] BYREF
  const char *v15; // [rsp+98h] [rbp+38h] BYREF

  LOBYTE(v13) = a2;
  v3 = this + 2;
  EnterCriticalSection(this + 2);
  v12 = v3;
  DiagnosticServer::ReportSvcStatus((DiagnosticServer *)this, 3, 0, 5000);
  DiagnosticServer::Cleanup((DiagnosticServer *)this);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v5, v4, v6) )
  {
    v13 = 356;
    v14 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v15 = "DiagnosticServer::StopServiceCallback";
    v10 = "Clean up on stop service callback";
    LODWORD(v12) = 0;
    v11 = this + 3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_18002E841,
      v8,
      v9,
      &v11,
      (__int64)&v12,
      &v10,
      &v15,
      &v14);
  }
  DiagnosticServer::ReportSvcStatus((DiagnosticServer *)this, 1, 0, 0);
  if ( v3 )
    LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180005f7c  mov     byte ptr [rsp-18h+arg_8], dl
0x180005f80  push    rbp
0x180005f81  push    rbx
0x180005f82  push    rdi
0x180005f83  mov     rbp, rsp
0x180005f86  sub     rsp, 60h
0x180005f8a  mov     rdi, rcx
0x180005f8d  lea     rbx, [rcx+50h]
0x180005f91  mov     rcx, rbx; lpCriticalSection
0x180005f94  call    cs:__imp_EnterCriticalSection
0x180005f9a  mov     [rbp+arg_0], rbx
0x180005f9e  mov     r9d, 1388h; unsigned int
0x180005fa4  xor     r8d, r8d; unsigned int
0x180005fa7  lea     edx, [r8+3]; unsigned int
0x180005fab  mov     rcx, rdi; this
0x180005fae  call    ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
0x180005fb3  mov     rcx, rdi; this
0x180005fb6  call    ?Cleanup@DiagnosticServer@@IEAAXXZ; DiagnosticServer::Cleanup(void)
0x180005fbb  mov     eax, cs:dword_180039000
0x180005fc1  cmp     eax, 5
0x180005fc4  jbe     loc_18000604C
0x180005fca  call    _tlgKeywordOn
0x180005fcf  test    al, al
0x180005fd1  jz      short loc_18000604C
0x180005fd3  mov     [rbp+arg_8], 164h
0x180005fda  lea     rax, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180005fe1  mov     [rbp+arg_10], rax
0x180005fe5  lea     rax, aDiagnosticserv_1; "DiagnosticServer::StopServiceCallback"
0x180005fec  mov     [rbp+arg_18], rax
0x180005ff0  lea     rax, aCleanUpOnStopS; "Clean up on stop service callback"
0x180005ff7  mov     [rbp+var_10], rax
0x180005ffb  mov     dword ptr [rbp+arg_0], 0
0x180006002  lea     rax, [rdi+78h]
0x180006006  mov     [rbp+var_8], rax
0x18000600a  lea     rax, [rbp+arg_8]
0x18000600e  mov     [rsp+60h+var_18], rax
0x180006013  lea     rax, [rbp+arg_10]
0x180006017  mov     [rsp+60h+var_20], rax
0x18000601c  lea     rax, [rbp+arg_18]
0x180006020  mov     [rsp+60h+var_28], rax
0x180006025  lea     rax, [rbp+var_10]
0x180006029  mov     [rsp+60h+var_30], rax
0x18000602e  lea     rax, [rbp+arg_0]
0x180006032  mov     [rsp+60h+var_38], rax
0x180006037  lea     rax, [rbp+var_8]
0x18000603b  mov     [rsp+60h+var_40], rax
0x180006040  lea     rdx, byte_18002E841
0x180006047  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000604c  xor     r9d, r9d; unsigned int
0x18000604f  xor     r8d, r8d; unsigned int
0x180006052  lea     edx, [r9+1]; unsigned int
0x180006056  mov     rcx, rdi; this
0x180006059  call    ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
0x18000605e  nop
0x18000605f  test    rbx, rbx
0x180006062  jz      short loc_18000606D
0x180006064  mov     rcx, rbx; lpCriticalSection
0x180006067  call    cs:__imp_LeaveCriticalSection
0x18000606d  add     rsp, 60h
0x180006071  pop     rdi
0x180006072  pop     rbx
0x180006073  pop     rbp
0x180006074  retn
```
