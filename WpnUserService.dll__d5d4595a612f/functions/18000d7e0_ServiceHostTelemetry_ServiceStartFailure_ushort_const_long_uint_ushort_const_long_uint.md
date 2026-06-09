# ServiceHostTelemetry::ServiceStartFailure<ushort const *,long,uint>(ushort const * &&,long &&,uint &&)

- ea: `0x18000d7e0`
- end: `0x18000d87c`
- name: `??$ServiceStartFailure@PEBGJI@ServiceHostTelemetry@@SAX$$QEAPEBG$$QEAJ$$QEAI@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010444`

## callees

- `0x180001144`
- `0x18000a648`
- `0x18000d7e0`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long,unsigned int>(
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
               (unsigned int)&unk_180015438,
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
0x18000d7e0  mov     [rsp+arg_0], rbx
0x18000d7e5  mov     [rsp+arg_8], rsi
0x18000d7ea  push    rdi
0x18000d7eb  sub     rsp, 50h
0x18000d7ef  mov     rbx, r8
0x18000d7f2  mov     rdi, rdx
0x18000d7f5  mov     rsi, rcx
0x18000d7f8  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000d7fd  mov     r10, rax
0x18000d800  mov     r9d, [rax]
0x18000d803  cmp     r9d, 5
0x18000d807  jbe     short loc_18000D86C
0x18000d809  mov     rax, [rax+18h]
0x18000d80d  mov     rdx, 400000000000h
0x18000d817  mov     r9, [r10+10h]
0x18000d81b  test    rdx, r9
0x18000d81e  jz      short loc_18000D86C
0x18000d820  mov     rcx, rax
0x18000d823  and     rcx, rdx
0x18000d826  cmp     rcx, rax
0x18000d829  jnz     short loc_18000D86C
0x18000d82b  mov     eax, [rbx]
0x18000d82d  lea     rdx, unk_180015438
0x18000d834  mov     [rsp+58h+arg_18], eax
0x18000d838  mov     rcx, r10
0x18000d83b  mov     eax, [rdi]
0x18000d83d  mov     [rsp+58h+var_18], eax
0x18000d841  mov     rax, [rsi]
0x18000d844  mov     [rsp+58h+var_10], rax
0x18000d849  lea     rax, [rsp+58h+arg_18]
0x18000d84e  mov     [rsp+58h+var_28], rax
0x18000d853  lea     rax, [rsp+58h+var_18]
0x18000d858  mov     [rsp+58h+var_30], rax
0x18000d85d  lea     rax, [rsp+58h+var_10]
0x18000d862  mov     [rsp+58h+var_38], rax
0x18000d867  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d86c  mov     rbx, [rsp+58h+arg_0]
0x18000d871  mov     rsi, [rsp+58h+arg_8]
0x18000d876  add     rsp, 50h
0x18000d87a  pop     rdi
0x18000d87b  retn
```
