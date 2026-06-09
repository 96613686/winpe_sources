# SPTelemetry::ModelUpdate::AsimovBeginLocal<char const * &>(unsigned __int64,char const * &)

- ea: `0x14000a688`
- end: `0x14000a712`
- name: `??$AsimovBeginLocal@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000c3d8`

## callees

- `0x1400012bc`
- `0x1400077b0`
- `0x14000a688`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovBeginLocal<char const * &>(__int64 a1, __int64 a2, __int64 *a3)
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
    if ( (*(_QWORD *)(v7 + 16) & 1) != 0 && (result & 1) == result )
    {
      v8 = *(_QWORD *)(a1 + 48);
      v10 = *a3;
      v9[0] = a2;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
               v7,
               (unsigned int)&unk_14002A060,
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
0x14000a688  mov     [rsp+arg_0], rbx
0x14000a68d  mov     [rsp+arg_8], rsi
0x14000a692  push    rdi
0x14000a693  sub     rsp, 40h
0x14000a697  mov     rdi, r8
0x14000a69a  mov     rsi, rdx
0x14000a69d  mov     rbx, rcx
0x14000a6a0  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a6a5  mov     r10, rax
0x14000a6a8  mov     r9d, [rax]
0x14000a6ab  cmp     r9d, 4
0x14000a6af  jbe     short loc_14000A702
0x14000a6b1  mov     rax, [rax+18h]
0x14000a6b5  mov     r9, [r10+10h]
0x14000a6b9  test    r9b, 1
0x14000a6bd  jz      short loc_14000A702
0x14000a6bf  mov     rcx, rax
0x14000a6c2  and     ecx, 1
0x14000a6c5  cmp     rcx, rax
0x14000a6c8  jnz     short loc_14000A702
0x14000a6ca  mov     rax, [rdi]
0x14000a6cd  lea     r8, [rbx+20h]
0x14000a6d1  mov     r9, [rbx+30h]
0x14000a6d5  lea     rdx, unk_14002A060
0x14000a6dc  mov     [rsp+48h+arg_18], rax
0x14000a6e1  mov     rcx, r10
0x14000a6e4  lea     rax, [rsp+48h+arg_18]
0x14000a6e9  mov     [rsp+48h+var_18], rsi
0x14000a6ee  mov     [rsp+48h+var_20], rax
0x14000a6f3  lea     rax, [rsp+48h+var_18]
0x14000a6f8  mov     [rsp+48h+var_28], rax
0x14000a6fd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x14000a702  mov     rbx, [rsp+48h+arg_0]
0x14000a707  mov     rsi, [rsp+48h+arg_8]
0x14000a70c  add     rsp, 40h
0x14000a710  pop     rdi
0x14000a711  retn
```
