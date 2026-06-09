# MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)

- ea: `0x180003020`
- end: `0x1800030ac`
- name: `??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006a78`

## callees

- `0x180001008`
- `0x180003020`
- `0x180005820`

## string_xrefs

- `0x18000306e`: `WLIDCpGetConfigDWORDValue`

## pseudocode

```c
__int64 __fastcall MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  int v4; // r9d
  __int64 v5; // r8
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  const char *v8; // [rsp+68h] [rbp+20h] BYREF

  v6 = a1;
  result = (__int64)MSAClientTraceTelemetry::Provider();
  v5 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      LODWORD(v6) = *a2;
      v7 = 50331648;
      v8 = "WLIDCpGetConfigDWORDValue";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
               v5,
               (unsigned int)word_180011172,
               v5,
               v4,
               (__int64)&v8,
               (__int64)&v6,
               (__int64)&v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003020  mov     [rsp+arg_0], rcx
0x180003025  push    rbx
0x180003026  sub     rsp, 40h
0x18000302a  mov     rbx, rdx
0x18000302d  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180003032  mov     r8, rax
0x180003035  mov     ecx, [rax]
0x180003037  cmp     ecx, 5
0x18000303a  jbe     short loc_1800030A6
0x18000303c  mov     rax, [rax+18h]
0x180003040  mov     rdx, 400000000000h
0x18000304a  mov     rcx, [r8+10h]
0x18000304e  test    rdx, rcx
0x180003051  jz      short loc_1800030A6
0x180003053  mov     rcx, rax
0x180003056  and     rcx, rdx
0x180003059  cmp     rcx, rax
0x18000305c  jnz     short loc_1800030A6
0x18000305e  mov     eax, [rbx]
0x180003060  lea     rdx, word_180011172
0x180003067  mov     dword ptr [rsp+48h+arg_0], eax
0x18000306b  mov     rcx, r8
0x18000306e  lea     rax, aWlidcpgetconfi; "WLIDCpGetConfigDWORDValue"
0x180003075  mov     [rsp+48h+arg_10], 3000000h
0x18000307e  mov     [rsp+48h+arg_18], rax
0x180003083  lea     rax, [rsp+48h+arg_10]
0x180003088  mov     [rsp+48h+var_18], rax
0x18000308d  lea     rax, [rsp+48h+arg_0]
0x180003092  mov     [rsp+48h+var_20], rax
0x180003097  lea     rax, [rsp+48h+arg_18]
0x18000309c  mov     [rsp+48h+var_28], rax
0x1800030a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800030a6  add     rsp, 40h
0x1800030aa  pop     rbx
0x1800030ab  retn
```
