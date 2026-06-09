# CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(long,char const *)

- ea: `0x18001bde0`
- end: `0x18001be6a`
- name: `?LogEnrollDMPollTaskSchedulerFail@CEnrollmentLogger@@QEAAXJPEBD@Z`
- size: `138`
- prototype: `void __fastcall(CEnrollmentLogger *__hidden this, int, const char *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800085c8`
- `0x18000cfc4`
- `0x18000d590`
- `0x18000db20`
- `0x18000e034`
- `0x18000e40c`
- `0x18000e888`
- `0x18000ef24`

## callees

- `0x180001224`
- `0x18000147c`
- `0x18001bde0`

## pseudocode

```c
void __fastcall CEnrollmentLogger::LogEnrollDMPollTaskSchedulerFail(
        CEnrollmentLogger *this,
        __int64 a2,
        const char *a3)
{
  int v3; // ecx
  int v4; // r8d
  __int64 v5; // r9
  int v6; // r10d
  __int64 v7; // r11
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v10[3]; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+88h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180029000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180029000, 0x400000000000LL, a3, a3) )
    {
      v8 = v7;
      v9 = 0x2000000;
      v10[0] = v5;
      v11 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v3,
        (unsigned int)byte_180023F61,
        v4,
        v5,
        (__int64)&v11,
        (__int64)v10,
        (__int64)&v9,
        (__int64)&v8);
    }
  }
}

```

## disassembly

```asm
0x18001bde0  sub     rsp, 68h
0x18001bde4  mov     eax, cs:dword_180029000
0x18001bdea  mov     r9, r8
0x18001bded  mov     r10d, edx
0x18001bdf0  mov     r11, rcx
0x18001bdf3  cmp     eax, 5
0x18001bdf6  jbe     short loc_18001BE64
0x18001bdf8  mov     rdx, 400000000000h
0x18001be02  lea     rcx, dword_180029000
0x18001be09  call    _tlgKeywordOn
0x18001be0e  test    al, al
0x18001be10  jz      short loc_18001BE64
0x18001be12  lea     rax, [rsp+68h+var_28]
0x18001be17  mov     [rsp+68h+var_28], r11
0x18001be1c  mov     [rsp+68h+var_30], rax
0x18001be21  lea     rdx, byte_180023F61
0x18001be28  lea     rax, [rsp+68h+var_20]
0x18001be2d  mov     [rsp+68h+var_20], 2000000h
0x18001be36  mov     [rsp+68h+var_38], rax
0x18001be3b  lea     rax, [rsp+68h+var_18]
0x18001be40  mov     [rsp+68h+var_40], rax
0x18001be45  lea     rax, [rsp+68h+arg_18]
0x18001be4d  mov     [rsp+68h+var_48], rax
0x18001be52  mov     [rsp+68h+var_18], r9
0x18001be57  mov     [rsp+68h+arg_18], r10d
0x18001be5f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18001be64  add     rsp, 68h
0x18001be68  retn
```
