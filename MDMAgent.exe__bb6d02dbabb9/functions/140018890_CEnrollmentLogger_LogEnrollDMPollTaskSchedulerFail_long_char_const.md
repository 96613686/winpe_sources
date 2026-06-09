# CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)

- ea: `0x140018890`
- end: `0x140018917`
- name: `?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z`
- size: `135`
- prototype: `void __fastcall(CEnrollmentLogger *__hidden this, int, const char *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000a03c`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`

## callees

- `0x140001f30`
- `0x140002188`
- `0x140018890`

## pseudocode

```c
void __fastcall CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(
        CEnrollmentLogger *this,
        __int64 a2,
        const char *a3)
{
  int v3; // ecx
  __int64 v4; // r8
  int v5; // r9d
  __int64 v6; // r10
  __int64 v7; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v9[3]; // [rsp+50h] [rbp-18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF

  if ( (unsigned int)dword_140025000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140025000, 0x400000000000LL) )
    {
      v7 = v6;
      v8 = 0x2000000;
      v9[0] = v4;
      v10 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_140020D2B,
        v4,
        v5,
        (__int64)&v10,
        (__int64)v9,
        (__int64)&v8,
        (__int64)&v7);
    }
  }
}

```

## disassembly

```asm
0x140018890  sub     rsp, 68h
0x140018894  mov     eax, cs:dword_140025000
0x14001889a  mov     r9d, edx
0x14001889d  mov     r10, rcx
0x1400188a0  cmp     eax, 5
0x1400188a3  jbe     short loc_140018911
0x1400188a5  mov     rdx, 400000000000h
0x1400188af  lea     rcx, dword_140025000
0x1400188b6  call    _tlgKeywordOn
0x1400188bb  test    al, al
0x1400188bd  jz      short loc_140018911
0x1400188bf  lea     rax, [rsp+68h+var_28]
0x1400188c4  mov     [rsp+68h+var_28], r10
0x1400188c9  mov     [rsp+68h+var_30], rax
0x1400188ce  lea     rdx, byte_140020D2B
0x1400188d5  lea     rax, [rsp+68h+var_20]
0x1400188da  mov     [rsp+68h+var_20], 2000000h
0x1400188e3  mov     [rsp+68h+var_38], rax
0x1400188e8  lea     rax, [rsp+68h+var_18]
0x1400188ed  mov     [rsp+68h+var_40], rax
0x1400188f2  lea     rax, [rsp+68h+arg_18]
0x1400188fa  mov     [rsp+68h+var_48], rax
0x1400188ff  mov     [rsp+68h+var_18], r8
0x140018904  mov     [rsp+68h+arg_18], r9d
0x14001890c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x140018911  add     rsp, 68h
0x140018915  retn
```
