# Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)

- ea: `0x14000aa18`
- end: `0x14000aab1`
- name: `?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ`
- size: `153`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400078b0`
- `0x14000f470`

## callees

- `0x1400010f8`
- `0x140001ffc`
- `0x14000aa18`
- `0x1400110a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000aa3c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000aa3c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000aa9b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000aa9b`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  GUID *v1; // rbx
  __int64 v3; // rcx
  _DWORD *v4; // r8
  int v5; // r8d
  int v6; // r9d
  GUID *v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = (GUID *)((char *)this + 32);
  if ( *((_BYTE *)this + 12) )
  {
LABEL_7:
    CoCreateGuid(v1);
    return;
  }
  EventActivityIdControl(3u, (LPGUID)this + 2);
  if ( !v1->Data1 && !*((_WORD *)this + 18) )
  {
    v4 = *(_DWORD **)(wil::details::static_lazy<SessionTraceLoggingClass>::get(
                        v3,
                        _lambda_cdfb642ce540b95b439d0082c4543265_::_lambda_invoker_cdecl_)
                    + 8);
    if ( *v4 > 2u )
    {
      if ( (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
      {
        v7 = v1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
          v5,
          (unsigned int)&byte_140042D37,
          v5,
          v6,
          (__int64)&v7);
      }
    }
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x14000aa18  mov     [rsp+arg_8], rbx
0x14000aa1d  mov     [rsp+arg_10], rsi
0x14000aa22  push    rdi
0x14000aa23  sub     rsp, 30h
0x14000aa27  xor     esi, esi
0x14000aa29  lea     rbx, [rcx+20h]
0x14000aa2d  mov     rdi, rcx
0x14000aa30  cmp     [rcx+0Ch], sil
0x14000aa34  jnz     short loc_14000AA98
0x14000aa36  mov     rdx, rbx; ActivityId
0x14000aa39  lea     ecx, [rsi+3]; ControlCode
0x14000aa3c  call    cs:__imp_EventActivityIdControl
0x14000aa42  cmp     [rbx], esi
0x14000aa44  jnz     short loc_14000AAA1
0x14000aa46  cmp     [rdi+24h], si
0x14000aa4a  jnz     short loc_14000AAA1
0x14000aa4c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_cdfb642ce540b95b439d0082c4543265_@@CA@XZ; _lambda_cdfb642ce540b95b439d0082c4543265_::_lambda_invoker_cdecl_(void)
0x14000aa53  call    ?get@?$static_lazy@VSessionTraceLoggingClass@@@details@wil@@QEAAPEAVSessionTraceLoggingClass@@P6AXXZ@Z; wil::details::static_lazy<SessionTraceLoggingClass>::get(void (*)(void))
0x14000aa58  mov     r8, [rax+8]
0x14000aa5c  mov     eax, [r8]
0x14000aa5f  cmp     eax, 2
0x14000aa62  jbe     short loc_14000AA98
0x14000aa64  mov     rdx, 200000000000h
0x14000aa6e  mov     rcx, r8
0x14000aa71  call    _tlgKeywordOn
0x14000aa76  test    al, al
0x14000aa78  jz      short loc_14000AA98
0x14000aa7a  lea     rax, [rsp+38h+arg_0]
0x14000aa7f  mov     [rsp+38h+arg_0], rbx
0x14000aa84  lea     rdx, byte_140042D37
0x14000aa8b  mov     [rsp+38h+var_18], rax
0x14000aa90  mov     rcx, r8
0x14000aa93  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x14000aa98  mov     rcx, rbx; pguid
0x14000aa9b  call    cs:__imp_CoCreateGuid
0x14000aaa1  mov     rbx, [rsp+38h+arg_8]
0x14000aaa6  mov     rsi, [rsp+38h+arg_10]
0x14000aaab  add     rsp, 30h
0x14000aaaf  pop     rdi
0x14000aab0  retn
```
