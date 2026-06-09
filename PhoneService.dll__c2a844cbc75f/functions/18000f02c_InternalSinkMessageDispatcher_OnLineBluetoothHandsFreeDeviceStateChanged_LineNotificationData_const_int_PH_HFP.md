# InternalSinkMessageDispatcher::OnLineBluetoothHandsFreeDeviceStateChanged(LineNotificationData const &,int,PH_HFPAUDIOSTATUS,int)

- ea: `0x18000f02c`
- end: `0x18000f178`
- name: `?OnLineBluetoothHandsFreeDeviceStateChanged@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@HW4PH_HFPAUDIOSTATUS@@H@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180042de8`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f02c`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f07a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f07a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f11d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f11d`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnLineBluetoothHandsFreeDeviceStateChanged(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *i; // rbx
  int v16; // eax
  __int64 v17; // r8
  __m128i si128; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h]

  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 200);
  v19 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  if ( *(_DWORD *)(a1 + 192) )
  {
    Log_AssertionEvent_0(v11, v10, 145);
    if ( *(_DWORD *)(a1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          a1 + 96) )
  {
    LeaveCriticalSection(v5);
    if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v14, v13, 157);
      if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(*(_QWORD *)*i + 72LL))(*i, a2, a3, a4, a5);
      if ( v16 < 0 )
        Log_HREvent_2((unsigned int)v16, 0, v17, 285);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v12, 151);
    LeaveCriticalSection(v5);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
}

```

## disassembly

```asm
0x18000f02c  mov     [rsp+arg_8], rbx
0x18000f031  mov     [rsp+arg_10], rbp
0x18000f036  push    rsi
0x18000f037  push    rdi
0x18000f038  push    r14
0x18000f03a  sub     rsp, 50h
0x18000f03e  mov     rax, cs:__security_cookie
0x18000f045  xor     rax, rsp
0x18000f048  mov     [rsp+68h+var_20], rax
0x18000f04d  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000f055  lea     rdi, [rcx+0C8h]
0x18000f05c  mov     rbx, rcx
0x18000f05f  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x18000f068  mov     rcx, rdi; lpCriticalSection
0x18000f06b  mov     esi, r9d
0x18000f06e  mov     ebp, r8d
0x18000f071  mov     r14, rdx
0x18000f074  movdqu  [rsp+68h+var_38], xmm0
0x18000f07a  call    cs:__imp_EnterCriticalSection
0x18000f080  cmp     dword ptr [rbx+0C0h], 0
0x18000f087  jz      short loc_18000F0A2
0x18000f089  mov     r8d, 91h
0x18000f08f  call    Log_AssertionEvent_0
0x18000f094  cmp     dword ptr [rbx+0C0h], 0
0x18000f09b  jz      short loc_18000F0A2
0x18000f09d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f0a2  lea     rdx, [rbx+60h]
0x18000f0a6  lea     rcx, [rsp+68h+var_38]
0x18000f0ab  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000f0b0  test    al, al
0x18000f0b2  jnz     short loc_18000F0FB
0x18000f0b4  xor     edx, edx
0x18000f0b6  mov     ecx, 8007000Eh
0x18000f0bb  mov     r9d, 97h
0x18000f0c1  call    Log_HREvent_2
0x18000f0c6  mov     rcx, rdi; lpCriticalSection
0x18000f0c9  call    cs:__imp_LeaveCriticalSection
0x18000f0cf  lea     rcx, [rsp+68h+var_38]
0x18000f0d4  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000f0d9  mov     rcx, [rsp+68h+var_20]
0x18000f0de  xor     rcx, rsp; StackCookie
0x18000f0e1  call    __security_check_cookie
0x18000f0e6  lea     r11, [rsp+68h+var_18]
0x18000f0eb  mov     rbx, [r11+28h]
0x18000f0ef  mov     rbp, [r11+30h]
0x18000f0f3  mov     rsp, r11
0x18000f0f6  pop     r14
0x18000f0f8  pop     rdi
0x18000f0f9  pop     rsi
0x18000f0fa  retn
0x18000f0fb  mov     rcx, rdi; lpCriticalSection
0x18000f0fe  call    cs:__imp_LeaveCriticalSection
0x18000f104  call    cs:__imp_GetCurrentThreadId
0x18000f10a  cmp     [rbx+0D8h], eax
0x18000f110  jnz     short loc_18000F130
0x18000f112  mov     r8d, 9Dh
0x18000f118  call    Log_AssertionEvent_0
0x18000f11d  call    cs:__imp_GetCurrentThreadId
0x18000f123  cmp     [rbx+0D8h], eax
0x18000f129  jnz     short loc_18000F130
0x18000f12b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f130  mov     rbx, qword ptr [rsp+68h+var_38]
0x18000f135  mov     edi, [rsp+68h+arg_20]
0x18000f13c  cmp     rbx, qword ptr [rsp+68h+var_38+8]
0x18000f141  jz      short loc_18000F0CF
0x18000f143  mov     rcx, [rbx]
0x18000f146  mov     r9d, esi
0x18000f149  mov     r8d, ebp
0x18000f14c  mov     [rsp+68h+var_48], edi
0x18000f150  mov     rdx, r14
0x18000f153  mov     rax, [rcx]
0x18000f156  mov     rax, [rax+48h]
0x18000f15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f15f  test    eax, eax
0x18000f161  jns     short loc_18000F172
0x18000f163  xor     edx, edx
0x18000f165  mov     r9d, 11Dh
0x18000f16b  mov     ecx, eax
0x18000f16d  call    Log_HREvent_2
0x18000f172  add     rbx, 8
0x18000f176  jmp     short loc_18000F13C
```
