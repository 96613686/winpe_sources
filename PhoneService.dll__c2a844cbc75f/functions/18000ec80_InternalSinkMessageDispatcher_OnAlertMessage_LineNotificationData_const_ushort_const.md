# InternalSinkMessageDispatcher::OnAlertMessage(LineNotificationData const &,ushort const *)

- ea: `0x18000ec80`
- end: `0x18000eda6`
- name: `?OnAlertMessage@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@PEBG@Z`
- size: `294`
- prototype: `void __fastcall(InternalSinkMessageDispatcher *__hidden this, const struct LineNotificationData *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180040954`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000ec80`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ecc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ed3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed59`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnAlertMessage(
        struct _RTL_CRITICAL_SECTION *this,
        const struct LineNotificationData *a2,
        const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *i; // rbx
  int v13; // eax
  __int64 v14; // r8
  __m128i si128; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]

  v3 = this + 5;
  v16 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection(this + 5);
  if ( LODWORD(this[4].SpinCount) )
  {
    Log_AssertionEvent_0(v8, v7, 145);
    if ( LODWORD(this[4].SpinCount) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          &this[3]) )
  {
    LeaveCriticalSection(v3);
    if ( LODWORD(this[5].OwningThread) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v11, v10, 157);
      if ( LODWORD(this[5].OwningThread) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, const struct LineNotificationData *, const unsigned __int16 *))(*(_QWORD *)*i + 32LL))(
              *i,
              a2,
              a3);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 305);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v9, 151);
    LeaveCriticalSection(v3);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
}

```

## disassembly

```asm
0x18000ec80  push    rbx
0x18000ec82  push    rbp
0x18000ec83  push    rsi
0x18000ec84  push    rdi
0x18000ec85  sub     rsp, 58h
0x18000ec89  mov     rax, cs:__security_cookie
0x18000ec90  xor     rax, rsp
0x18000ec93  mov     [rsp+78h+var_30], rax
0x18000ec98  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000eca0  lea     rdi, [rcx+0C8h]
0x18000eca7  mov     rbx, rcx
0x18000ecaa  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x18000ecb3  mov     rcx, rdi; lpCriticalSection
0x18000ecb6  mov     rsi, r8
0x18000ecb9  mov     rbp, rdx
0x18000ecbc  movdqu  [rsp+78h+var_48], xmm0
0x18000ecc2  call    cs:__imp_EnterCriticalSection
0x18000ecc8  cmp     dword ptr [rbx+0C0h], 0
0x18000eccf  jz      short loc_18000ECEA
0x18000ecd1  mov     r8d, 91h
0x18000ecd7  call    Log_AssertionEvent_0
0x18000ecdc  cmp     dword ptr [rbx+0C0h], 0
0x18000ece3  jz      short loc_18000ECEA
0x18000ece5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ecea  lea     rdx, [rbx+78h]
0x18000ecee  lea     rcx, [rsp+78h+var_48]
0x18000ecf3  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000ecf8  test    al, al
0x18000ecfa  jnz     short loc_18000ED37
0x18000ecfc  xor     edx, edx
0x18000ecfe  mov     ecx, 8007000Eh
0x18000ed03  mov     r9d, 97h
0x18000ed09  call    Log_HREvent_2
0x18000ed0e  mov     rcx, rdi; lpCriticalSection
0x18000ed11  call    cs:__imp_LeaveCriticalSection
0x18000ed17  lea     rcx, [rsp+78h+var_48]
0x18000ed1c  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000ed21  mov     rcx, [rsp+78h+var_30]
0x18000ed26  xor     rcx, rsp; StackCookie
0x18000ed29  call    __security_check_cookie
0x18000ed2e  add     rsp, 58h
0x18000ed32  pop     rdi
0x18000ed33  pop     rsi
0x18000ed34  pop     rbp
0x18000ed35  pop     rbx
0x18000ed36  retn
0x18000ed37  mov     rcx, rdi; lpCriticalSection
0x18000ed3a  call    cs:__imp_LeaveCriticalSection
0x18000ed40  call    cs:__imp_GetCurrentThreadId
0x18000ed46  cmp     [rbx+0D8h], eax
0x18000ed4c  jnz     short loc_18000ED6C
0x18000ed4e  mov     r8d, 9Dh
0x18000ed54  call    Log_AssertionEvent_0
0x18000ed59  call    cs:__imp_GetCurrentThreadId
0x18000ed5f  cmp     [rbx+0D8h], eax
0x18000ed65  jnz     short loc_18000ED6C
0x18000ed67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ed6c  mov     rbx, qword ptr [rsp+78h+var_48]
0x18000ed71  cmp     rbx, qword ptr [rsp+78h+var_48+8]
0x18000ed76  jz      short loc_18000ED17
0x18000ed78  mov     rcx, [rbx]
0x18000ed7b  mov     r8, rsi
0x18000ed7e  mov     rdx, rbp
0x18000ed81  mov     rax, [rcx]
0x18000ed84  mov     rax, [rax+20h]
0x18000ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed8d  test    eax, eax
0x18000ed8f  jns     short loc_18000EDA0
0x18000ed91  xor     edx, edx
0x18000ed93  mov     r9d, 131h
0x18000ed99  mov     ecx, eax
0x18000ed9b  call    Log_HREvent_2
0x18000eda0  add     rbx, 8
0x18000eda4  jmp     short loc_18000ED71
```
