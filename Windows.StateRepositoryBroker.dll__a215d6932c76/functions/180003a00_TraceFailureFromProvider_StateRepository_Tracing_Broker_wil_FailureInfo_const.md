# TraceFailureFromProvider<StateRepository::Tracing::Broker>(wil::FailureInfo const &)

- ea: `0x180003a00`
- end: `0x180003a94`
- name: `??$TraceFailureFromProvider@VBroker@Tracing@StateRepository@@@@YAXAEBUFailureInfo@wil@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x18000182c`
- `0x180003a00`
- `0x18000687c`

## pseudocode

```c
__int64 __fastcall TraceFailureFromProvider<StateRepository::Tracing::Broker>(__int64 a1)
{
  unsigned int *v2; // r8
  __int64 result; // rax
  int v4; // r8d
  int v5; // r9d
  _QWORD v6[3]; // [rsp+40h] [rbp-18h] BYREF
  int v7; // [rsp+68h] [rbp+10h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  __int64 v9; // [rsp+78h] [rbp+20h] BYREF

  v2 = *(unsigned int **)(wil::details::static_lazy<StateRepository::Tracing::Broker>::get(
                            a1,
                            _lambda_f1d812b2ab9979f8929c90d47472da81_::_lambda_invoker_cdecl_)
                        + 8);
  result = *v2;
  if ( (unsigned int)result > 2 )
  {
    result = tlgKeywordOn(v2, 0x200000000000LL);
    if ( (_BYTE)result )
    {
      v9 = *(_QWORD *)(a1 + 24);
      v7 = *(_DWORD *)(a1 + 64);
      v6[0] = *(_QWORD *)(a1 + 56);
      v8 = *(_DWORD *)(a1 + 8);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
               v4,
               (unsigned int)&byte_18001000F,
               v4,
               v5,
               (__int64)&v8,
               (__int64)v6,
               (__int64)&v7,
               (__int64)&v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003a00  push    rbx
0x180003a02  sub     rsp, 50h
0x180003a06  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f1d812b2ab9979f8929c90d47472da81_@@CA@XZ; _lambda_f1d812b2ab9979f8929c90d47472da81_::_lambda_invoker_cdecl_(void)
0x180003a0d  mov     rbx, rcx
0x180003a10  call    ?get@?$static_lazy@VBroker@Tracing@StateRepository@@@details@wil@@QEAAPEAVBroker@Tracing@StateRepository@@P6AXXZ@Z; wil::details::static_lazy<StateRepository::Tracing::Broker>::get(void (*)(void))
0x180003a15  mov     r8, [rax+8]
0x180003a19  mov     eax, [r8]
0x180003a1c  cmp     eax, 2
0x180003a1f  jbe     short loc_180003A8E
0x180003a21  mov     rdx, 200000000000h
0x180003a2b  mov     rcx, r8
0x180003a2e  call    _tlgKeywordOn
0x180003a33  test    al, al
0x180003a35  jz      short loc_180003A8E
0x180003a37  mov     rax, [rbx+18h]
0x180003a3b  lea     rdx, byte_18001000F
0x180003a42  mov     [rsp+58h+arg_18], rax
0x180003a47  mov     rcx, r8
0x180003a4a  mov     eax, [rbx+40h]
0x180003a4d  mov     [rsp+58h+arg_8], eax
0x180003a51  mov     rax, [rbx+38h]
0x180003a55  mov     [rsp+58h+var_18], rax
0x180003a5a  mov     eax, [rbx+8]
0x180003a5d  mov     [rsp+58h+arg_10], eax
0x180003a61  lea     rax, [rsp+58h+arg_18]
0x180003a66  mov     [rsp+58h+var_20], rax
0x180003a6b  lea     rax, [rsp+58h+arg_8]
0x180003a70  mov     [rsp+58h+var_28], rax
0x180003a75  lea     rax, [rsp+58h+var_18]
0x180003a7a  mov     [rsp+58h+var_30], rax
0x180003a7f  lea     rax, [rsp+58h+arg_10]
0x180003a84  mov     [rsp+58h+var_38], rax
0x180003a89  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180003a8e  add     rsp, 50h
0x180003a92  pop     rbx
0x180003a93  retn
```
