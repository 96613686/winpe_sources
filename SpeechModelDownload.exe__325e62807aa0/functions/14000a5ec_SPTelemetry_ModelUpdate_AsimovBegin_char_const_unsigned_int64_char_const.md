# SPTelemetry::ModelUpdate::AsimovBegin<char const * &>(unsigned __int64,char const * &)

- ea: `0x14000a5ec`
- end: `0x14000a67f`
- name: `??$AsimovBegin@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000c3d8`

## callees

- `0x1400012bc`
- `0x1400077b0`
- `0x14000a5ec`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovBegin<char const * &>(__int64 a1, __int64 a2, __int64 *a3)
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
               (unsigned int)byte_14002A093,
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
0x14000a5ec  mov     [rsp+arg_0], rbx
0x14000a5f1  mov     [rsp+arg_8], rsi
0x14000a5f6  push    rdi
0x14000a5f7  sub     rsp, 40h
0x14000a5fb  mov     rdi, r8
0x14000a5fe  mov     rsi, rdx
0x14000a601  mov     rbx, rcx
0x14000a604  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a609  mov     r10, rax
0x14000a60c  mov     r9d, [rax]
0x14000a60f  cmp     r9d, 4
0x14000a613  jbe     short loc_14000A66F
0x14000a615  mov     rax, [rax+18h]
0x14000a619  mov     rdx, 400000000000h
0x14000a623  mov     r9, [r10+10h]
0x14000a627  test    rdx, r9
0x14000a62a  jz      short loc_14000A66F
0x14000a62c  mov     rcx, rax
0x14000a62f  and     rcx, rdx
0x14000a632  cmp     rcx, rax
0x14000a635  jnz     short loc_14000A66F
0x14000a637  mov     rax, [rdi]
0x14000a63a  lea     r8, [rbx+20h]
0x14000a63e  mov     r9, [rbx+30h]
0x14000a642  lea     rdx, byte_14002A093
0x14000a649  mov     [rsp+48h+arg_18], rax
0x14000a64e  mov     rcx, r10
0x14000a651  lea     rax, [rsp+48h+arg_18]
0x14000a656  mov     [rsp+48h+var_18], rsi
0x14000a65b  mov     [rsp+48h+var_20], rax
0x14000a660  lea     rax, [rsp+48h+var_18]
0x14000a665  mov     [rsp+48h+var_28], rax
0x14000a66a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x14000a66f  mov     rbx, [rsp+48h+arg_0]
0x14000a674  mov     rsi, [rsp+48h+arg_8]
0x14000a679  add     rsp, 40h
0x14000a67d  pop     rdi
0x14000a67e  retn
```
