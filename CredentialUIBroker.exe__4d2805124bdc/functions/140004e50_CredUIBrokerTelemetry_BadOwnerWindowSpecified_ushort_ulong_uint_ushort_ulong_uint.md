# CredUIBrokerTelemetry::BadOwnerWindowSpecified<ushort *,ulong &,uint>(ushort * &&,ulong &,uint &&)

- ea: `0x140004e50`
- end: `0x140004ee0`
- name: `??$BadOwnerWindowSpecified@PEAGAEAKI@CredUIBrokerTelemetry@@SAX$$QEAPEAGAEAK$$QEAI@Z`
- size: `144`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009cfc`

## callees

- `0x1400013f8`
- `0x140002f8c`
- `0x140004e50`
- `0x140011a40`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CredUIBrokerTelemetry::BadOwnerWindowSpecified<unsigned short *,unsigned long &,unsigned int>(
        __int64 *a1,
        int *a2,
        int *a3)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // r8d
  int v10; // r9d
  int v11; // r10d
  int v12; // ecx
  int v13; // [rsp+40h] [rbp-18h] BYREF
  __int64 v14; // [rsp+48h] [rbp-10h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF

  result = CredUIBrokerLogging::Provider();
  v8 = *(unsigned int *)result;
  if ( (unsigned int)v8 > 5 )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x200000000000LL, v7, v8);
    if ( (_BYTE)result )
    {
      v12 = *a3;
      v13 = *a2;
      v14 = *a1;
      v15 = v12;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                              v11,
                                              (unsigned int)byte_140025ECB,
                                              v9,
                                              v10,
                                              (__int64)&v14,
                                              (__int64)&v13,
                                              (__int64)&v15);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004e50  mov     [rsp+arg_0], rbx
0x140004e55  mov     [rsp+arg_8], rsi
0x140004e5a  push    rdi
0x140004e5b  sub     rsp, 50h
0x140004e5f  mov     rbx, r8
0x140004e62  mov     rdi, rdx
0x140004e65  mov     rsi, rcx
0x140004e68  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140004e6d  mov     r10, rax
0x140004e70  mov     r9d, [rax]
0x140004e73  cmp     r9d, 5
0x140004e77  jbe     short loc_140004ED0
0x140004e79  mov     rdx, 200000000000h
0x140004e83  mov     rcx, rax
0x140004e86  call    _tlgKeywordOn
0x140004e8b  test    al, al
0x140004e8d  jz      short loc_140004ED0
0x140004e8f  mov     eax, [rdi]
0x140004e91  lea     rdx, byte_140025ECB
0x140004e98  mov     ecx, [rbx]
0x140004e9a  mov     [rsp+58h+var_18], eax
0x140004e9e  mov     rax, [rsi]
0x140004ea1  mov     [rsp+58h+var_10], rax
0x140004ea6  lea     rax, [rsp+58h+arg_18]
0x140004eab  mov     [rsp+58h+var_28], rax
0x140004eb0  lea     rax, [rsp+58h+var_18]
0x140004eb5  mov     [rsp+58h+var_30], rax
0x140004eba  lea     rax, [rsp+58h+var_10]
0x140004ebf  mov     [rsp+58h+arg_18], ecx
0x140004ec3  mov     rcx, r10
0x140004ec6  mov     [rsp+58h+var_38], rax
0x140004ecb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004ed0  mov     rbx, [rsp+58h+arg_0]
0x140004ed5  mov     rsi, [rsp+58h+arg_8]
0x140004eda  add     rsp, 50h
0x140004ede  pop     rdi
0x140004edf  retn
```
