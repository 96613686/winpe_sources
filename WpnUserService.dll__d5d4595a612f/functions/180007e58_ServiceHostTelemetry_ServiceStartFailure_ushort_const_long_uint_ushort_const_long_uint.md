# ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)

- ea: `0x180007e58`
- end: `0x180007ef4`
- name: `??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64 *, int *, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009d40`
- `0x18000a170`
- `0x18000e9e8`
- `0x180010444`

## callees

- `0x180001144`
- `0x180007e58`
- `0x18000a648`

## pseudocode

```c
__int64 __fastcall ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(
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
               (unsigned int)byte_180014B1B,
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
0x180007e58  mov     [rsp+arg_0], rbx
0x180007e5d  mov     [rsp+arg_8], rsi
0x180007e62  push    rdi
0x180007e63  sub     rsp, 50h
0x180007e67  mov     rbx, r8
0x180007e6a  mov     rdi, rdx
0x180007e6d  mov     rsi, rcx
0x180007e70  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x180007e75  mov     r10, rax
0x180007e78  mov     r9d, [rax]
0x180007e7b  cmp     r9d, 5
0x180007e7f  jbe     short loc_180007EE4
0x180007e81  mov     rax, [rax+18h]
0x180007e85  mov     rdx, 400000000000h
0x180007e8f  mov     r9, [r10+10h]
0x180007e93  test    rdx, r9
0x180007e96  jz      short loc_180007EE4
0x180007e98  mov     rcx, rax
0x180007e9b  and     rcx, rdx
0x180007e9e  cmp     rcx, rax
0x180007ea1  jnz     short loc_180007EE4
0x180007ea3  mov     eax, [rbx]
0x180007ea5  lea     rdx, byte_180014B1B
0x180007eac  mov     [rsp+58h+arg_18], eax
0x180007eb0  mov     rcx, r10
0x180007eb3  mov     eax, [rdi]
0x180007eb5  mov     [rsp+58h+var_18], eax
0x180007eb9  mov     rax, [rsi]
0x180007ebc  mov     [rsp+58h+var_10], rax
0x180007ec1  lea     rax, [rsp+58h+arg_18]
0x180007ec6  mov     [rsp+58h+var_28], rax
0x180007ecb  lea     rax, [rsp+58h+var_18]
0x180007ed0  mov     [rsp+58h+var_30], rax
0x180007ed5  lea     rax, [rsp+58h+var_10]
0x180007eda  mov     [rsp+58h+var_38], rax
0x180007edf  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007ee4  mov     rbx, [rsp+58h+arg_0]
0x180007ee9  mov     rsi, [rsp+58h+arg_8]
0x180007eee  add     rsp, 50h
0x180007ef2  pop     rdi
0x180007ef3  retn
```
