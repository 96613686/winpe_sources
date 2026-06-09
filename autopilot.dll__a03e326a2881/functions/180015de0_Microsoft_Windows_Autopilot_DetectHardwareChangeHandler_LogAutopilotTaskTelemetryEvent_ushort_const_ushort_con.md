# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(ushort const *,ushort const *,long)

- ea: `0x180015de0`
- end: `0x180015eca`
- name: `?LogAutopilotTaskTelemetryEvent@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z`
- size: `234`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014d24`
- `0x180014da4`

## callees

- `0x1800016dc`
- `0x1800045b0`
- `0x180015898`
- `0x180015de0`
- `0x180016344`
- `0x180017488`

## pseudocode

```c
void __fastcall Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::LogAutopilotTaskTelemetryEvent(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // rbx
  __int64 v8; // rax
  _QWORD *AutopilotCorrelationVector; // rax
  int v10; // r8d
  int v11; // r9d
  int v12; // [rsp+50h] [rbp-19h] BYREF
  __int64 v13; // [rsp+58h] [rbp-11h] BYREF
  const unsigned __int16 *v14; // [rsp+60h] [rbp-9h] BYREF
  const unsigned __int16 *v15; // [rsp+68h] [rbp-1h] BYREF
  _QWORD *v16; // [rsp+70h] [rbp+7h] BYREF
  _BYTE v17[32]; // [rsp+78h] [rbp+Fh] BYREF

  v6 = ZeroTouchProvCxhTelemetry::Provider();
  v7 = v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    v8 = *((_QWORD *)v6 + 3);
    if ( (*((_QWORD *)v7 + 2) & 0x800000000000LL) != 0 && (v8 & 0x800000000000LL) == v8 )
    {
      v13 = 0x2000000;
      v12 = a3;
      v14 = a2;
      v15 = a1;
      AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v17);
      if ( AutopilotCorrelationVector[3] > 0xFu )
        AutopilotCorrelationVector = (_QWORD *)*AutopilotCorrelationVector;
      v16 = AutopilotCorrelationVector;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v7,
        (unsigned int)word_18003A92A,
        v10,
        v11,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
      std::string::_Tidy_deallocate(v17);
    }
  }
}

```

## disassembly

```asm
0x180015de0  push    rbp
0x180015de2  push    rbx
0x180015de3  push    rsi
0x180015de4  push    rdi
0x180015de5  push    r14
0x180015de7  lea     rbp, [rsp-37h]
0x180015dec  sub     rsp, 0A0h
0x180015df3  mov     rax, cs:__security_cookie
0x180015dfa  xor     rax, rsp
0x180015dfd  mov     [rbp+57h+var_28], rax
0x180015e01  mov     edi, r8d
0x180015e04  mov     rsi, rdx
0x180015e07  mov     r14, rcx
0x180015e0a  call    ?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ; ZeroTouchProvCxhTelemetry::Provider(void)
0x180015e0f  mov     rbx, rax
0x180015e12  mov     r9d, [rax]
0x180015e15  cmp     r9d, 5
0x180015e19  jbe     loc_180015EB0
0x180015e1f  mov     rax, [rax+18h]
0x180015e23  mov     rdx, 800000000000h
0x180015e2d  mov     r9, [rbx+10h]
0x180015e31  test    rdx, r9
0x180015e34  jz      short loc_180015EB0
0x180015e36  mov     rcx, rax
0x180015e39  and     rcx, rdx
0x180015e3c  cmp     rcx, rax
0x180015e3f  jnz     short loc_180015EB0
0x180015e41  lea     rcx, [rbp+57h+var_48]
0x180015e45  mov     [rbp+57h+var_68], 2000000h
0x180015e4d  mov     [rbp+57h+var_70], edi
0x180015e50  mov     [rbp+57h+var_60], rsi
0x180015e54  mov     [rbp+57h+var_58], r14
0x180015e58  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180015e5d  cmp     qword ptr [rax+18h], 0Fh
0x180015e62  jbe     short loc_180015E67
0x180015e64  mov     rax, [rax]
0x180015e67  mov     [rbp+57h+var_50], rax
0x180015e6b  lea     rdx, word_18003A92A
0x180015e72  lea     rax, [rbp+57h+var_68]
0x180015e76  mov     rcx, rbx
0x180015e79  mov     [rsp+0C0h+var_80], rax
0x180015e7e  lea     rax, [rbp+57h+var_70]
0x180015e82  mov     [rsp+0C0h+var_88], rax
0x180015e87  lea     rax, [rbp+57h+var_60]
0x180015e8b  mov     [rsp+0C0h+var_90], rax
0x180015e90  lea     rax, [rbp+57h+var_58]
0x180015e94  mov     [rsp+0C0h+var_98], rax
0x180015e99  lea     rax, [rbp+57h+var_50]
0x180015e9d  mov     [rsp+0C0h+var_A0], rax
0x180015ea2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180015ea7  lea     rcx, [rbp+57h+var_48]
0x180015eab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015eb0  mov     rcx, [rbp+57h+var_28]
0x180015eb4  xor     rcx, rsp; StackCookie
0x180015eb7  call    __security_check_cookie
0x180015ebc  add     rsp, 0A0h
0x180015ec3  pop     r14
0x180015ec5  pop     rdi
0x180015ec6  pop     rsi
0x180015ec7  pop     rbx
0x180015ec8  pop     rbp
0x180015ec9  retn
```
