# InternalSinkMessageDispatcher::OnEmergencyCallbackModeChange(LineNotificationData const &,int)

- ea: `0x18000ef00`
- end: `0x18000f026`
- name: `?OnEmergencyCallbackModeChange@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@H@Z`
- size: `294`
- prototype: `void __fastcall(InternalSinkMessageDispatcher *__hidden this, const struct LineNotificationData *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180043690`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000ef00`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efd9`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnEmergencyCallbackModeChange(
        struct _RTL_CRITICAL_SECTION *this,
        const struct LineNotificationData *a2,
        unsigned int a3)
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
      v13 = (*(__int64 (__fastcall **)(_QWORD, const struct LineNotificationData *, _QWORD))(*(_QWORD *)*i + 24LL))(
              *i,
              a2,
              a3);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 295);
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
0x18000ef00  push    rbx
0x18000ef02  push    rbp
0x18000ef03  push    rsi
0x18000ef04  push    rdi
0x18000ef05  sub     rsp, 58h
0x18000ef09  mov     rax, cs:__security_cookie
0x18000ef10  xor     rax, rsp
0x18000ef13  mov     [rsp+78h+var_30], rax
0x18000ef18  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ef20  lea     rdi, [rcx+0C8h]
0x18000ef27  mov     rbx, rcx
0x18000ef2a  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x18000ef33  mov     rcx, rdi; lpCriticalSection
0x18000ef36  mov     esi, r8d
0x18000ef39  mov     rbp, rdx
0x18000ef3c  movdqu  [rsp+78h+var_48], xmm0
0x18000ef42  call    cs:__imp_EnterCriticalSection
0x18000ef48  cmp     dword ptr [rbx+0C0h], 0
0x18000ef4f  jz      short loc_18000EF6A
0x18000ef51  mov     r8d, 91h
0x18000ef57  call    Log_AssertionEvent_0
0x18000ef5c  cmp     dword ptr [rbx+0C0h], 0
0x18000ef63  jz      short loc_18000EF6A
0x18000ef65  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ef6a  lea     rdx, [rbx+78h]
0x18000ef6e  lea     rcx, [rsp+78h+var_48]
0x18000ef73  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000ef78  test    al, al
0x18000ef7a  jnz     short loc_18000EFB7
0x18000ef7c  xor     edx, edx
0x18000ef7e  mov     ecx, 8007000Eh
0x18000ef83  mov     r9d, 97h
0x18000ef89  call    Log_HREvent_2
0x18000ef8e  mov     rcx, rdi; lpCriticalSection
0x18000ef91  call    cs:__imp_LeaveCriticalSection
0x18000ef97  lea     rcx, [rsp+78h+var_48]
0x18000ef9c  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000efa1  mov     rcx, [rsp+78h+var_30]
0x18000efa6  xor     rcx, rsp; StackCookie
0x18000efa9  call    __security_check_cookie
0x18000efae  add     rsp, 58h
0x18000efb2  pop     rdi
0x18000efb3  pop     rsi
0x18000efb4  pop     rbp
0x18000efb5  pop     rbx
0x18000efb6  retn
0x18000efb7  mov     rcx, rdi; lpCriticalSection
0x18000efba  call    cs:__imp_LeaveCriticalSection
0x18000efc0  call    cs:__imp_GetCurrentThreadId
0x18000efc6  cmp     [rbx+0D8h], eax
0x18000efcc  jnz     short loc_18000EFEC
0x18000efce  mov     r8d, 9Dh
0x18000efd4  call    Log_AssertionEvent_0
0x18000efd9  call    cs:__imp_GetCurrentThreadId
0x18000efdf  cmp     [rbx+0D8h], eax
0x18000efe5  jnz     short loc_18000EFEC
0x18000efe7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000efec  mov     rbx, qword ptr [rsp+78h+var_48]
0x18000eff1  cmp     rbx, qword ptr [rsp+78h+var_48+8]
0x18000eff6  jz      short loc_18000EF97
0x18000eff8  mov     rcx, [rbx]
0x18000effb  mov     r8d, esi
0x18000effe  mov     rdx, rbp
0x18000f001  mov     rax, [rcx]
0x18000f004  mov     rax, [rax+18h]
0x18000f008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f00d  test    eax, eax
0x18000f00f  jns     short loc_18000F020
0x18000f011  xor     edx, edx
0x18000f013  mov     r9d, 127h
0x18000f019  mov     ecx, eax
0x18000f01b  call    Log_HREvent_2
0x18000f020  add     rbx, 8
0x18000f024  jmp     short loc_18000EFF1
```
