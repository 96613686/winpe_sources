# CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)

- ea: `0x140017ba0`
- end: `0x140017c26`
- name: `?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z`
- size: `134`
- prototype: `void __fastcall(CEnrollmentLogger *this, unsigned int, const char *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140009bfc`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`

## callees

- `0x140001f1c`
- `0x14000216c`
- `0x140017ba0`

## pseudocode

```c
void __fastcall CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(
        CEnrollmentLogger *this,
        unsigned int a2,
        const char *a3)
{
  __int64 v3; // rcx
  const unsigned __int16 *v4; // r8
  __int64 v5; // r9
  const unsigned __int16 *v6; // r10
  const unsigned __int16 *v7; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-20h] BYREF
  const unsigned __int16 *v9; // [rsp+50h] [rbp-18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF

  if ( (unsigned int)dword_140024000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140024000, 0x400000000000LL, a3, a2) )
    {
      v7 = v6;
      v8 = 0x2000000;
      v9 = v4;
      v10 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v3,
        (__int64)byte_14001FD2B,
        (__int64)v4,
        v5,
        (__int64)&v10,
        &v9,
        (__int64)&v8,
        &v7);
    }
  }
}

```

## disassembly

```asm
0x140017ba0  sub     rsp, 68h
0x140017ba4  mov     eax, cs:dword_140024000
0x140017baa  mov     r9d, edx
0x140017bad  mov     r10, rcx
0x140017bb0  cmp     eax, 5
0x140017bb3  jbe     short loc_140017C21
0x140017bb5  mov     rdx, 400000000000h
0x140017bbf  lea     rcx, dword_140024000
0x140017bc6  call    _tlgKeywordOn
0x140017bcb  test    al, al
0x140017bcd  jz      short loc_140017C21
0x140017bcf  lea     rax, [rsp+68h+var_28]
0x140017bd4  mov     [rsp+68h+var_28], r10
0x140017bd9  mov     [rsp+68h+var_30], rax
0x140017bde  lea     rdx, byte_14001FD2B
0x140017be5  lea     rax, [rsp+68h+var_20]
0x140017bea  mov     [rsp+68h+var_20], 2000000h
0x140017bf3  mov     [rsp+68h+var_38], rax
0x140017bf8  lea     rax, [rsp+68h+var_18]
0x140017bfd  mov     [rsp+68h+var_40], rax
0x140017c02  lea     rax, [rsp+68h+arg_18]
0x140017c0a  mov     [rsp+68h+var_48], rax
0x140017c0f  mov     [rsp+68h+var_18], r8
0x140017c14  mov     [rsp+68h+arg_18], r9d
0x140017c1c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x140017c21  add     rsp, 68h
0x140017c25  retn
```
