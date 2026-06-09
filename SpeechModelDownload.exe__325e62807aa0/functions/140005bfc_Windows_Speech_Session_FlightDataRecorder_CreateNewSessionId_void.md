# Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)

- ea: `0x140005bfc`
- end: `0x140005d72`
- name: `?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ`
- size: `374`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140004748`
- `0x1400088c4`
- `0x140015068`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400028b8`
- `0x140005bfc`
- `0x1400078fc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140005c36`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140005c36`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140005c6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140005c6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140005cdd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140005cdd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140005d4a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140005d4a`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  GUID *v1; // rbx
  void (*v3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  __int64 v4; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-58h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-48h] BYREF
  GUID *v8; // [rsp+60h] [rbp-28h]
  __int64 v9; // [rsp+68h] [rbp-20h]

  v1 = (GUID *)((char *)this + 32);
  if ( *((_BYTE *)this + 12) )
  {
LABEL_11:
    CoCreateGuid(v1);
    return;
  }
  EventActivityIdControl(3u, (LPGUID)this + 2);
  if ( !v1->Data1 && !*((_WORD *)this + 18) )
  {
    Context = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`SessionTraceLoggingClass::Instance'::`2'::wrapper, 0, &fPending, &Context)
      && fPending )
    {
      qword_140030680 = 0;
      Context = &qword_140030678;
      qword_140030678 = &FlightDataRecorderActivityClass::`vftable';
      byte_140030688 = 0;
      dword_14003068C = 0;
      qword_140030690 = (struct _tlgProvider_t *)&`SessionTraceLoggingClass::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_cdfb642ce540b95b439d0082c4543265_::_lambda_invoker_cdecl_);
      wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140030678, qword_140030690, v3);
      InitOnceComplete(&`SessionTraceLoggingClass::Instance'::`2'::wrapper, 0, &qword_140030678);
    }
    v4 = *((_QWORD *)Context + 1);
    if ( *(_DWORD *)v4 > 2u
      && (*(_QWORD *)(v4 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v4 + 24) & 0x200000000000LL) == *(_QWORD *)(v4 + 24) )
    {
      v8 = v1;
      v9 = 16;
      tlgWriteTransfer_EventWriteTransfer(v4, &byte_140029BB7, 0, 0, 3, v7);
    }
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x140005bfc  mov     [rsp+arg_8], rbx
0x140005c01  mov     [rsp+arg_10], rsi
0x140005c06  push    rdi
0x140005c07  sub     rsp, 80h
0x140005c0e  mov     rax, cs:__security_cookie
0x140005c15  xor     rax, rsp
0x140005c18  mov     [rsp+88h+var_18], rax
0x140005c1d  xor     esi, esi
0x140005c1f  lea     rbx, [rcx+20h]
0x140005c23  mov     rdi, rcx
0x140005c26  cmp     [rcx+0Ch], sil
0x140005c2a  jnz     loc_140005D47
0x140005c30  mov     rdx, rbx; ActivityId
0x140005c33  lea     ecx, [rsi+3]; ControlCode
0x140005c36  call    cs:__imp_EventActivityIdControl
0x140005c3c  cmp     [rbx], esi
0x140005c3e  jnz     loc_140005D50
0x140005c44  cmp     [rdi+24h], si
0x140005c48  jnz     loc_140005D50
0x140005c4e  lea     r9, [rsp+88h+Context]; lpContext
0x140005c53  mov     [rsp+88h+Context], rsi
0x140005c58  lea     r8, [rsp+88h+fPending]; fPending
0x140005c5d  mov     [rsp+88h+fPending], esi
0x140005c61  xor     edx, edx; dwFlags
0x140005c63  lea     rcx, ?wrapper@?1??Instance@SessionTraceLoggingClass@@KAPEAV2@XZ@4V?$static_lazy@VSessionTraceLoggingClass@@@details@wil@@A; lpInitOnce
0x140005c6a  call    cs:__imp_InitOnceBeginInitialize
0x140005c70  test    eax, eax
0x140005c72  jz      short loc_140005CE3
0x140005c74  cmp     [rsp+88h+fPending], esi
0x140005c78  jz      short loc_140005CE3
0x140005c7a  lea     rdi, qword_140030678
0x140005c81  mov     cs:qword_140030680, rsi
0x140005c88  lea     rax, ??_7FlightDataRecorderActivityClass@@6B@; const FlightDataRecorderActivityClass::`vftable'
0x140005c8f  mov     [rsp+88h+Context], rdi
0x140005c94  mov     cs:qword_140030678, rax
0x140005c9b  mov     cs:byte_140030688, sil
0x140005ca2  mov     cs:dword_14003068C, esi
0x140005ca8  lea     rax, ?__hInner@?1???0StaticHandle@SessionTraceLoggingClass@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SessionTraceLoggingClass::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140005caf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_cdfb642ce540b95b439d0082c4543265_@@CA@XZ; void (__cdecl *)()
0x140005cb6  mov     cs:qword_140030690, rax
0x140005cbd  call    atexit
0x140005cc2  mov     rdx, cs:qword_140030690; struct _tlgProvider_t *
0x140005cc9  mov     rcx, rdi; this
0x140005ccc  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140005cd1  mov     r8, rdi; lpContext
0x140005cd4  lea     rcx, ?wrapper@?1??Instance@SessionTraceLoggingClass@@KAPEAV2@XZ@4V?$static_lazy@VSessionTraceLoggingClass@@@details@wil@@A; lpInitOnce
0x140005cdb  xor     edx, edx; dwFlags
0x140005cdd  call    cs:__imp_InitOnceComplete
0x140005ce3  mov     rax, [rsp+88h+Context]
0x140005ce8  mov     rcx, [rax+8]
0x140005cec  mov     eax, [rcx]
0x140005cee  cmp     eax, 2
0x140005cf1  jbe     short loc_140005D47
0x140005cf3  mov     rdx, [rcx+18h]
0x140005cf7  mov     r8, 200000000000h
0x140005d01  mov     rax, [rcx+10h]
0x140005d05  test    r8, rax
0x140005d08  jz      short loc_140005D47
0x140005d0a  mov     rax, rdx
0x140005d0d  and     rax, r8
0x140005d10  cmp     rax, rdx
0x140005d13  jnz     short loc_140005D47
0x140005d15  lea     rax, [rsp+88h+var_48]
0x140005d1a  mov     [rsp+88h+var_28], rbx
0x140005d1f  mov     [rsp+88h+var_60], rax
0x140005d24  lea     rdx, byte_140029BB7
0x140005d2b  xor     r9d, r9d
0x140005d2e  mov     [rsp+88h+var_68], 3
0x140005d36  xor     r8d, r8d
0x140005d39  mov     [rsp+88h+var_20], 10h
0x140005d42  call    _tlgWriteTransfer_EventWriteTransfer
0x140005d47  mov     rcx, rbx; pguid
0x140005d4a  call    cs:__imp_CoCreateGuid
0x140005d50  mov     rcx, [rsp+88h+var_18]
0x140005d55  xor     rcx, rsp; StackCookie
0x140005d58  call    __security_check_cookie
0x140005d5d  lea     r11, [rsp+88h+var_8]
0x140005d65  mov     rbx, [r11+18h]
0x140005d69  mov     rsi, [r11+20h]
0x140005d6d  mov     rsp, r11
0x140005d70  pop     rdi
0x140005d71  retn
```
