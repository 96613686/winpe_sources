# DiagnosticServer::StopService(void)

- ea: `0x180005eac`
- end: `0x180005f74`
- name: `?StopService@DiagnosticServer@@IEAAXXZ`
- size: `200`
- prototype: `void __fastcall(DiagnosticServer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800058ec`

## callees

- `0x180001178`
- `0x180001720`
- `0x180005768`
- `0x180005eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005ec2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005ec2`

## string_xrefs

- `0x180005ee0`: `onecoreuap\base\diagnosis\pdi\diagsvc\dll\diagnosticserver.cpp`
- `0x180005ef9`: `DiagnosticServer::StopService`

## pseudocode

```c
void __fastcall DiagnosticServer::StopService(DiagnosticServer *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v8; // [rsp+50h] [rbp-18h] BYREF
  char *v9; // [rsp+58h] [rbp-10h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF
  const char *v11; // [rsp+90h] [rbp+28h] BYREF
  const char *v12; // [rsp+98h] [rbp+30h] BYREF

  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    SetEvent(v4);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v4, a2, a3) )
  {
    v11 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\dll\\diagnosticserver.cpp";
    v10 = 0;
    v12 = "DiagnosticServer::StopService";
    v8 = "Set shutdown event";
    v9 = (char *)this + 120;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)&unk_18002E930,
      v6,
      v7,
      &v9,
      (__int64)&v10,
      &v8,
      &v12,
      &v11);
  }
  DiagnosticServer::ReportSvcStatus(this, 3, 0, 5000);
}

```

## disassembly

```asm
0x180005eac  push    rbp
0x180005eae  push    rbx
0x180005eaf  mov     rbp, rsp
0x180005eb2  sub     rsp, 68h
0x180005eb6  mov     rbx, rcx
0x180005eb9  mov     rcx, [rcx+38h]; hEvent
0x180005ebd  test    rcx, rcx
0x180005ec0  jz      short loc_180005EC8
0x180005ec2  call    cs:__imp_SetEvent
0x180005ec8  mov     eax, cs:dword_180039000
0x180005ece  cmp     eax, 5
0x180005ed1  jbe     loc_180005F59
0x180005ed7  call    _tlgKeywordOn
0x180005edc  test    al, al
0x180005ede  jz      short loc_180005F59
0x180005ee0  lea     rax, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180005ee7  mov     [rbp+arg_0], 0FBh
0x180005eee  mov     [rbp+arg_10], rax
0x180005ef2  lea     rdx, unk_18002E930
0x180005ef9  lea     rax, aDiagnosticserv; "DiagnosticServer::StopService"
0x180005f00  mov     [rbp+arg_8], 0
0x180005f07  mov     [rbp+arg_18], rax
0x180005f0b  lea     rax, aSetShutdownEve; "Set shutdown event"
0x180005f12  mov     [rbp+var_18], rax
0x180005f16  lea     rax, [rbx+78h]
0x180005f1a  mov     [rbp+var_10], rax
0x180005f1e  lea     rax, [rbp+arg_0]
0x180005f22  mov     [rsp+68h+var_20], rax
0x180005f27  lea     rax, [rbp+arg_10]
0x180005f2b  mov     [rsp+68h+var_28], rax
0x180005f30  lea     rax, [rbp+arg_18]
0x180005f34  mov     [rsp+68h+var_30], rax
0x180005f39  lea     rax, [rbp+var_18]
0x180005f3d  mov     [rsp+68h+var_38], rax
0x180005f42  lea     rax, [rbp+arg_8]
0x180005f46  mov     [rsp+68h+var_40], rax
0x180005f4b  lea     rax, [rbp+var_10]
0x180005f4f  mov     [rsp+68h+var_48], rax
0x180005f54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005f59  xor     r8d, r8d; unsigned int
0x180005f5c  mov     r9d, 1388h; unsigned int
0x180005f62  mov     rcx, rbx; this
0x180005f65  lea     edx, [r8+3]; unsigned int
0x180005f69  add     rsp, 68h
0x180005f6d  pop     rbx
0x180005f6e  pop     rbp
0x180005f6f  jmp     ?ReportSvcStatus@DiagnosticServer@@IEAAXKKK@Z; DiagnosticServer::ReportSvcStatus(ulong,ulong,ulong)
```
