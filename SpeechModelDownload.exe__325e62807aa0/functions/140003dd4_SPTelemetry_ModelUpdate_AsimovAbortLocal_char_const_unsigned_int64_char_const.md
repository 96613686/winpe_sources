# SPTelemetry::ModelUpdate::AsimovAbortLocal<char const * &>(unsigned __int64,char const * &)

- ea: `0x140003dd4`
- end: `0x140003e5e`
- name: `??$AsimovAbortLocal@AEAPEBD@ModelUpdate@SPTelemetry@@QEAAX_KAEAPEBD@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140004f38`

## callees

- `0x1400012bc`
- `0x140003dd4`
- `0x1400077b0`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovAbortLocal<char const * &>(__int64 a1, __int64 a2, __int64 *a3)
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
               (unsigned int)byte_140029D05,
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
0x140003dd4  mov     [rsp+arg_0], rbx
0x140003dd9  mov     [rsp+arg_8], rsi
0x140003dde  push    rdi
0x140003ddf  sub     rsp, 40h
0x140003de3  mov     rdi, r8
0x140003de6  mov     rsi, rdx
0x140003de9  mov     rbx, rcx
0x140003dec  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140003df1  mov     r10, rax
0x140003df4  mov     r9d, [rax]
0x140003df7  cmp     r9d, 4
0x140003dfb  jbe     short loc_140003E4E
0x140003dfd  mov     rax, [rax+18h]
0x140003e01  mov     r9, [r10+10h]
0x140003e05  test    r9b, 1
0x140003e09  jz      short loc_140003E4E
0x140003e0b  mov     rcx, rax
0x140003e0e  and     ecx, 1
0x140003e11  cmp     rcx, rax
0x140003e14  jnz     short loc_140003E4E
0x140003e16  mov     rax, [rdi]
0x140003e19  lea     r8, [rbx+20h]
0x140003e1d  mov     r9, [rbx+30h]
0x140003e21  lea     rdx, byte_140029D05
0x140003e28  mov     [rsp+48h+arg_18], rax
0x140003e2d  mov     rcx, r10
0x140003e30  lea     rax, [rsp+48h+arg_18]
0x140003e35  mov     [rsp+48h+var_18], rsi
0x140003e3a  mov     [rsp+48h+var_20], rax
0x140003e3f  lea     rax, [rsp+48h+var_18]
0x140003e44  mov     [rsp+48h+var_28], rax
0x140003e49  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x140003e4e  mov     rbx, [rsp+48h+arg_0]
0x140003e53  mov     rsi, [rsp+48h+arg_8]
0x140003e58  add     rsp, 40h
0x140003e5c  pop     rdi
0x140003e5d  retn
```
