# ServiceHostTelemetry::ServiceStartFailure<ushort const * &,long &,StartServiceFailureReason &>(ushort const * &,long &,StartServiceFailureReason &)

- ea: `0x18000d73c`
- end: `0x18000d7d8`
- name: `??$ServiceStartFailure@AEAPEBGAEAJAEAW4StartServiceFailureReason@@@ServiceHostTelemetry@@SAXAEAPEBGAEAJAEAW4StartServiceFailureReason@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e51c`

## callees

- `0x180001144`
- `0x18000a648`
- `0x18000d73c`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceStartFailure<unsigned short const * &,long &,enum StartServiceFailureReason &>(
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
               (unsigned int)&word_180015386,
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
0x18000d73c  mov     [rsp+arg_0], rbx
0x18000d741  mov     [rsp+arg_8], rsi
0x18000d746  push    rdi
0x18000d747  sub     rsp, 50h
0x18000d74b  mov     rbx, r8
0x18000d74e  mov     rdi, rdx
0x18000d751  mov     rsi, rcx
0x18000d754  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000d759  mov     r10, rax
0x18000d75c  mov     r9d, [rax]
0x18000d75f  cmp     r9d, 5
0x18000d763  jbe     short loc_18000D7C8
0x18000d765  mov     rax, [rax+18h]
0x18000d769  mov     rdx, 400000000000h
0x18000d773  mov     r9, [r10+10h]
0x18000d777  test    rdx, r9
0x18000d77a  jz      short loc_18000D7C8
0x18000d77c  mov     rcx, rax
0x18000d77f  and     rcx, rdx
0x18000d782  cmp     rcx, rax
0x18000d785  jnz     short loc_18000D7C8
0x18000d787  mov     eax, [rbx]
0x18000d789  lea     rdx, word_180015386
0x18000d790  mov     [rsp+58h+arg_18], eax
0x18000d794  mov     rcx, r10
0x18000d797  mov     eax, [rdi]
0x18000d799  mov     [rsp+58h+var_18], eax
0x18000d79d  mov     rax, [rsi]
0x18000d7a0  mov     [rsp+58h+var_10], rax
0x18000d7a5  lea     rax, [rsp+58h+arg_18]
0x18000d7aa  mov     [rsp+58h+var_28], rax
0x18000d7af  lea     rax, [rsp+58h+var_18]
0x18000d7b4  mov     [rsp+58h+var_30], rax
0x18000d7b9  lea     rax, [rsp+58h+var_10]
0x18000d7be  mov     [rsp+58h+var_38], rax
0x18000d7c3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d7c8  mov     rbx, [rsp+58h+arg_0]
0x18000d7cd  mov     rsi, [rsp+58h+arg_8]
0x18000d7d2  add     rsp, 50h
0x18000d7d6  pop     rdi
0x18000d7d7  retn
```
