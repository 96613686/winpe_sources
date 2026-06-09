# ServiceHostTelemetry::ServiceStopFailure<ushort const * &,long &,StopServiceFailureReason &>(ushort const * &,long &,StopServiceFailureReason &)

- ea: `0x18000d884`
- end: `0x18000d920`
- name: `??$ServiceStopFailure@AEAPEBGAEAJAEAW4StopServiceFailureReason@@@ServiceHostTelemetry@@SAXAEAPEBGAEAJAEAW4StopServiceFailureReason@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e554`

## callees

- `0x180001144`
- `0x18000a648`
- `0x18000d884`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceStopFailure<unsigned short const * &,long &,enum StopServiceFailureReason &>(
        __int64 *a1,
        int *a2,
        int *a3)
{
  __int64 result; // rax
  int v7; // r8d
  __int64 v8; // r10
  __int64 v9; // r9
  int v10; // [rsp+40h] [rbp-18h] BYREF
  __int64 v11; // [rsp+48h] [rbp-10h] BYREF
  int v12; // [rsp+78h] [rbp+20h] BYREF

  result = (__int64)ServiceHostLogging::Provider();
  v8 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    v9 = *(_QWORD *)(v8 + 16);
    if ( (v9 & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v12 = *a3;
      v10 = *a2;
      v11 = *a1;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v8,
               (unsigned int)&byte_180015347,
               v7,
               v9,
               (__int64)&v11,
               (__int64)&v10,
               (__int64)&v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d884  mov     [rsp+arg_0], rbx
0x18000d889  mov     [rsp+arg_8], rsi
0x18000d88e  push    rdi
0x18000d88f  sub     rsp, 50h
0x18000d893  mov     rbx, r8
0x18000d896  mov     rdi, rdx
0x18000d899  mov     rsi, rcx
0x18000d89c  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000d8a1  mov     r10, rax
0x18000d8a4  mov     r9d, [rax]
0x18000d8a7  cmp     r9d, 5
0x18000d8ab  jbe     short loc_18000D910
0x18000d8ad  mov     rax, [rax+18h]
0x18000d8b1  mov     rdx, 400000000000h
0x18000d8bb  mov     r9, [r10+10h]
0x18000d8bf  test    rdx, r9
0x18000d8c2  jz      short loc_18000D910
0x18000d8c4  mov     rcx, rax
0x18000d8c7  and     rcx, rdx
0x18000d8ca  cmp     rcx, rax
0x18000d8cd  jnz     short loc_18000D910
0x18000d8cf  mov     eax, [rbx]
0x18000d8d1  lea     rdx, byte_180015347
0x18000d8d8  mov     [rsp+58h+arg_18], eax
0x18000d8dc  mov     rcx, r10
0x18000d8df  mov     eax, [rdi]
0x18000d8e1  mov     [rsp+58h+var_18], eax
0x18000d8e5  mov     rax, [rsi]
0x18000d8e8  mov     [rsp+58h+var_10], rax
0x18000d8ed  lea     rax, [rsp+58h+arg_18]
0x18000d8f2  mov     [rsp+58h+var_28], rax
0x18000d8f7  lea     rax, [rsp+58h+var_18]
0x18000d8fc  mov     [rsp+58h+var_30], rax
0x18000d901  lea     rax, [rsp+58h+var_10]
0x18000d906  mov     [rsp+58h+var_38], rax
0x18000d90b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d910  mov     rbx, [rsp+58h+arg_0]
0x18000d915  mov     rsi, [rsp+58h+arg_8]
0x18000d91a  add     rsp, 50h
0x18000d91e  pop     rdi
0x18000d91f  retn
```
