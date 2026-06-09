# SPTelemetry::ModelUpdate::AsimovAbort<char const * &>(unsigned __int64,char const * &)

- ea: `0x140003d38`
- end: `0x140003dcb`
- name: `??$AsimovAbort@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140004f38`

## callees

- `0x1400012bc`
- `0x140003d38`
- `0x1400077b0`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovAbort<char const * &>(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v7; // r10
  __int64 v8; // r9
  _QWORD v9[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  result = (__int64)SPTraceLoggingClass::Provider();
  v7 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v8 = *(_QWORD *)(a1 + 48);
      v10 = *a3;
      v9[0] = a2;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
               v7,
               (unsigned int)byte_140029C35,
               (int)a1 + 32,
               v8,
               (__int64)v9,
               (__int64)&v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003d38  mov     [rsp+arg_0], rbx
0x140003d3d  mov     [rsp+arg_8], rsi
0x140003d42  push    rdi
0x140003d43  sub     rsp, 40h
0x140003d47  mov     rdi, r8
0x140003d4a  mov     rsi, rdx
0x140003d4d  mov     rbx, rcx
0x140003d50  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140003d55  mov     r10, rax
0x140003d58  mov     r9d, [rax]
0x140003d5b  cmp     r9d, 4
0x140003d5f  jbe     short loc_140003DBB
0x140003d61  mov     rax, [rax+18h]
0x140003d65  mov     rdx, 400000000000h
0x140003d6f  mov     r9, [r10+10h]
0x140003d73  test    rdx, r9
0x140003d76  jz      short loc_140003DBB
0x140003d78  mov     rcx, rax
0x140003d7b  and     rcx, rdx
0x140003d7e  cmp     rcx, rax
0x140003d81  jnz     short loc_140003DBB
0x140003d83  mov     rax, [rdi]
0x140003d86  lea     r8, [rbx+20h]
0x140003d8a  mov     r9, [rbx+30h]
0x140003d8e  lea     rdx, byte_140029C35
0x140003d95  mov     [rsp+48h+arg_18], rax
0x140003d9a  mov     rcx, r10
0x140003d9d  lea     rax, [rsp+48h+arg_18]
0x140003da2  mov     [rsp+48h+var_18], rsi
0x140003da7  mov     [rsp+48h+var_20], rax
0x140003dac  lea     rax, [rsp+48h+var_18]
0x140003db1  mov     [rsp+48h+var_28], rax
0x140003db6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x140003dbb  mov     rbx, [rsp+48h+arg_0]
0x140003dc0  mov     rsi, [rsp+48h+arg_8]
0x140003dc5  add     rsp, 40h
0x140003dc9  pop     rdi
0x140003dca  retn
```
