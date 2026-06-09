# CSmsInterceptor::HandleNewMessage(IXMLDOMDocument *,Windows::Sms::Common::SmsMessageType)

- ea: `0x18000fc78`
- end: `0x18000fd8c`
- name: `?HandleNewMessage@CSmsInterceptor@@QEAAJPEAUIXMLDOMDocument@@W4SmsMessageType@Common@Sms@Windows@@@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016750`

## callees

- `0x180003a60`
- `0x18000fc78`
- `0x1800112e8`
- `0x18001bbbc`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000fd20`
- `ntdll!RtlNtStatusToDosError` at `0x18000fd20`
- `ntdll!RtlPublishWnfStateData` at `0x18000fce7`
- `ntdll!RtlPublishWnfStateData` at `0x18000fce7`

## string_xrefs

- `0x18000fd03`: `CSmsInterceptor::HandleNewMessage`
- `0x18000fd47`: `CSmsInterceptor::HandleNewMessage`

## pseudocode

```c
__int64 __fastcall CSmsInterceptor::HandleNewMessage(CSmsInterceptor *a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  unsigned __int64 v6; // rdi
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  signed int v9; // eax
  unsigned int v10; // r8d
  unsigned __int64 v11; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v12[2]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp-28h]

  v11 = 0;
  result = CSmsMessageStore::Add((__int64)a1 + 104, a2, a3, &v11);
  if ( (int)result >= 0 )
  {
    v6 = v11;
    v13 = v11;
    v12[1] = 0;
    v12[0] = a3;
    v7 = RtlPublishWnfStateData(WNF_SMSR_NEW_MESSAGE_RECEIVED, 0, v12, 16, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = RtlNtStatusToDosError(v7);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      LogSmsRouterError(
        "CSmsInterceptor::HandleNewMessage",
        0x264u,
        v10,
        "Error publishing new message notification MsgId: %llu. Type: %d, ntStatus: 0x%08X.",
        v13,
        v12[0],
        v8);
    }
    else
    {
      LogSmsRouterInfo(
        "CSmsInterceptor::HandleNewMessage",
        0x25Au,
        "Published new message notification MsgId: %llu. Type: %d.",
        v13,
        v12[0]);
    }
    return CSmsInterceptor::ScheduleNextRegistration(a1, v6, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000fc78  push    rbx
0x18000fc7a  push    rsi
0x18000fc7b  push    rdi
0x18000fc7c  sub     rsp, 60h
0x18000fc80  mov     rax, cs:__security_cookie
0x18000fc87  xor     rax, rsp
0x18000fc8a  mov     [rsp+78h+var_20], rax
0x18000fc8f  mov     rsi, rcx
0x18000fc92  mov     [rsp+78h+var_38], 0
0x18000fc9b  add     rcx, 68h ; 'h'
0x18000fc9f  lea     r9, [rsp+78h+var_38]
0x18000fca4  mov     ebx, r8d
0x18000fca7  call    ?Add@CSmsMessageStore@@QEAAJPEAUIXMLDOMDocument@@W4SmsMessageType@Common@Sms@Windows@@PEA_K@Z; CSmsMessageStore::Add(IXMLDOMDocument *,Windows::Sms::Common::SmsMessageType,unsigned __int64 *)
0x18000fcac  test    eax, eax
0x18000fcae  js      loc_18000FD77
0x18000fcb4  mov     rdi, [rsp+78h+var_38]
0x18000fcb9  lea     r8, [rsp+78h+var_30]
0x18000fcbe  mov     rcx, cs:WNF_SMSR_NEW_MESSAGE_RECEIVED
0x18000fcc5  mov     r9d, 10h
0x18000fccb  xor     edx, edx
0x18000fccd  mov     [rsp+78h+var_28], rdi
0x18000fcd2  mov     [rsp+78h+var_2C], 0
0x18000fcda  mov     [rsp+78h+var_30], ebx
0x18000fcde  mov     [rsp+78h+var_58], 0
0x18000fce7  call    cs:__imp_RtlPublishWnfStateData
0x18000fced  mov     ebx, eax
0x18000fcef  test    eax, eax
0x18000fcf1  js      short loc_18000FD1E
0x18000fcf3  mov     r9, [rsp+78h+var_28]
0x18000fcf8  lea     r8, aPublishedNewMe; "Published new message notification MsgI"...
0x18000fcff  mov     [rsp+78h+var_50], eax
0x18000fd03  lea     rcx, aCsmsintercepto_0; "CSmsInterceptor::HandleNewMessage"
0x18000fd0a  mov     eax, [rsp+78h+var_30]
0x18000fd0e  mov     edx, 25Ah; unsigned int
0x18000fd13  mov     dword ptr [rsp+78h+var_58], eax
0x18000fd17  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000fd1c  jmp     short loc_18000FD66
0x18000fd1e  mov     ecx, ebx; Status
0x18000fd20  call    cs:__imp_RtlNtStatusToDosError
0x18000fd26  mov     r8d, eax
0x18000fd29  test    eax, eax
0x18000fd2b  jle     short loc_18000FD38
0x18000fd2d  movzx   r8d, ax
0x18000fd31  or      r8d, 80070000h; int
0x18000fd38  mov     eax, [rsp+78h+var_30]
0x18000fd3c  lea     r9, aErrorPublishin; "Error publishing new message notificati"...
0x18000fd43  mov     [rsp+78h+var_48], ebx
0x18000fd47  lea     rcx, aCsmsintercepto_0; "CSmsInterceptor::HandleNewMessage"
0x18000fd4e  mov     [rsp+78h+var_50], eax
0x18000fd52  mov     edx, 264h; unsigned int
0x18000fd57  mov     rax, [rsp+78h+var_28]
0x18000fd5c  mov     [rsp+78h+var_58], rax
0x18000fd61  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000fd66  xor     r9d, r9d; int
0x18000fd69  xor     r8d, r8d; unsigned __int16 *
0x18000fd6c  mov     rdx, rdi; unsigned __int64
0x18000fd6f  mov     rcx, rsi; this
0x18000fd72  call    ?ScheduleNextRegistration@CSmsInterceptor@@AEAAJ_KPEBGH@Z; CSmsInterceptor::ScheduleNextRegistration(unsigned __int64,ushort const *,int)
0x18000fd77  mov     rcx, [rsp+78h+var_20]
0x18000fd7c  xor     rcx, rsp; StackCookie
0x18000fd7f  call    __security_check_cookie
0x18000fd84  add     rsp, 60h
0x18000fd88  pop     rdi
0x18000fd89  pop     rsi
0x18000fd8a  pop     rbx
0x18000fd8b  retn
```
