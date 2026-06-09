# PhoneController::_HandleAsyncApiCompleted(AsyncApiCompletedMessage *)

- ea: `0x18003cedc`
- end: `0x18003d06a`
- name: `?_HandleAsyncApiCompleted@PhoneController@@IEAAXPEAVAsyncApiCompletedMessage@@@Z`
- size: `398`
- prototype: `void __fastcall(PhoneController *__hidden this, struct AsyncApiCompletedMessage *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x180001348`
- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000fb70`
- `0x18003cedc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cfcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cfcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d020`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d020`

## pseudocode

```c
void __fastcall PhoneController::_HandleAsyncApiCompleted(
        PhoneController *this,
        struct AsyncApiCompletedMessage *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int *v4; // rsi
  unsigned int *v5; // rdi
  __int64 v7; // rbx
  unsigned int v8; // r14d
  unsigned int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *i; // rbx
  int v16; // eax
  __int64 v17; // r8
  const char *v18; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-30h] BYREF
  __m128i si128; // [rsp+58h] [rbp-28h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h]

  v4 = (unsigned int *)((char *)a2 + 32);
  v5 = (unsigned int *)((char *)a2 + 36);
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v19 = *v4;
    v20 = *v5;
    v18 = "PhoneController: Async API context";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (int)&dword_1800A7B4C,
      a3,
      a4,
      (const unsigned __int16 **)&v18,
      (__int64)&v20,
      (__int64)&v19);
  }
  v7 = *((_QWORD *)this + 11);
  v8 = *v5;
  v9 = *v4;
  v22 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  if ( *(_DWORD *)(v7 + 192) )
  {
    Log_AssertionEvent_0(v11, v10, 145);
    if ( *(_DWORD *)(v7 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v7 + 168) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
    if ( *(_DWORD *)(v7 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v14, v13, 157);
      if ( *(_DWORD *)(v7 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*i + 24LL))(*i, v9, v8);
      if ( v16 < 0 )
        Log_HREvent_2((unsigned int)v16, 0, v17, 378);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v12, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
}

```

## disassembly

```asm
0x18003cedc  mov     r11, rsp
0x18003cedf  mov     [r11+10h], rbx
0x18003cee3  mov     [r11+18h], rsi
0x18003cee7  push    rbp
0x18003cee8  push    rdi
0x18003cee9  push    r14
0x18003ceeb  mov     rbp, rsp
0x18003ceee  sub     rsp, 80h
0x18003cef5  mov     rax, cs:__security_cookie
0x18003cefc  xor     rax, rsp
0x18003ceff  mov     [rbp+var_10], rax
0x18003cf03  mov     eax, cs:dword_1800B3200
0x18003cf09  lea     rsi, [rdx+20h]
0x18003cf0d  lea     rdi, [rdx+24h]
0x18003cf11  mov     rbx, rcx
0x18003cf14  cmp     eax, 4
0x18003cf17  jbe     short loc_18003CF52
0x18003cf19  mov     eax, [rsi]
0x18003cf1b  lea     rdx, dword_1800A7B4C
0x18003cf22  mov     [rbp+var_38], eax
0x18003cf25  mov     eax, [rdi]
0x18003cf27  mov     [rbp+var_30], eax
0x18003cf2a  lea     rax, aPhonecontrolle_153; "PhoneController: Async API context"
0x18003cf31  mov     [rbp+var_40], rax
0x18003cf35  lea     rax, [rbp+var_38]
0x18003cf39  mov     [r11-68h], rax
0x18003cf3d  lea     rax, [rbp+var_30]
0x18003cf41  mov     [r11-70h], rax
0x18003cf45  lea     rax, [rbp+var_40]
0x18003cf49  mov     [r11-78h], rax
0x18003cf4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003cf52  mov     rbx, [rbx+58h]
0x18003cf56  mov     r14d, [rdi]
0x18003cf59  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003cf61  mov     esi, [rsi]
0x18003cf63  lea     rdi, [rbx+0C8h]
0x18003cf6a  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18003cf72  mov     rcx, rdi; lpCriticalSection
0x18003cf75  movdqu  [rbp+var_28], xmm0
0x18003cf7a  call    cs:__imp_EnterCriticalSection
0x18003cf80  cmp     dword ptr [rbx+0C0h], 0
0x18003cf87  jz      short loc_18003CFA2
0x18003cf89  mov     r8d, 91h
0x18003cf8f  call    Log_AssertionEvent_0
0x18003cf94  cmp     dword ptr [rbx+0C0h], 0
0x18003cf9b  jz      short loc_18003CFA2
0x18003cf9d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003cfa2  lea     rdx, [rbx+0A8h]
0x18003cfa9  lea     rcx, [rbp+var_28]
0x18003cfad  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18003cfb2  test    al, al
0x18003cfb4  jnz     short loc_18003CFFE
0x18003cfb6  xor     edx, edx
0x18003cfb8  mov     ecx, 8007000Eh
0x18003cfbd  mov     r9d, 97h
0x18003cfc3  call    Log_HREvent_2
0x18003cfc8  mov     rcx, rdi; lpCriticalSection
0x18003cfcb  call    cs:__imp_LeaveCriticalSection
0x18003cfd1  lea     rcx, [rbp+var_28]
0x18003cfd5  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003cfda  mov     rcx, [rbp+var_10]
0x18003cfde  xor     rcx, rsp; StackCookie
0x18003cfe1  call    __security_check_cookie
0x18003cfe6  lea     r11, [rsp+80h+var_s0]
0x18003cfee  mov     rbx, [r11+28h]
0x18003cff2  mov     rsi, [r11+30h]
0x18003cff6  mov     rsp, r11
0x18003cff9  pop     r14
0x18003cffb  pop     rdi
0x18003cffc  pop     rbp
0x18003cffd  retn
0x18003cffe  mov     rcx, rdi; lpCriticalSection
0x18003d001  call    cs:__imp_LeaveCriticalSection
0x18003d007  call    cs:__imp_GetCurrentThreadId
0x18003d00d  cmp     [rbx+0D8h], eax
0x18003d013  jnz     short loc_18003D033
0x18003d015  mov     r8d, 9Dh
0x18003d01b  call    Log_AssertionEvent_0
0x18003d020  call    cs:__imp_GetCurrentThreadId
0x18003d026  cmp     [rbx+0D8h], eax
0x18003d02c  jnz     short loc_18003D033
0x18003d02e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d033  mov     rbx, qword ptr [rbp+var_28]
0x18003d037  cmp     rbx, qword ptr [rbp+var_28+8]
0x18003d03b  jz      short loc_18003CFD1
0x18003d03d  mov     rcx, [rbx]
0x18003d040  mov     r8d, r14d
0x18003d043  mov     edx, esi
0x18003d045  mov     rax, [rcx]
0x18003d048  mov     rax, [rax+18h]
0x18003d04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d051  test    eax, eax
0x18003d053  jns     short loc_18003D064
0x18003d055  xor     edx, edx
0x18003d057  mov     r9d, 17Ah
0x18003d05d  mov     ecx, eax
0x18003d05f  call    Log_HREvent_2
0x18003d064  add     rbx, 8
0x18003d068  jmp     short loc_18003D037
```
