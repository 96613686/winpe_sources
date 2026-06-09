# PhoneController::_OnRecordingStateChanged(void)

- ea: `0x180044324`
- end: `0x18004447d`
- name: `?_OnRecordingStateChanged@PhoneController@@IEAAJXZ`
- size: `345`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000fb70`
- `0x18002c574`
- `0x180044324`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044398`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044417`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004441d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004441d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044436`

## string_xrefs

- `0x180044354`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnRecordingStateChanged(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *i; // rbx
  int v11; // eax
  __int64 v12; // r8
  __m128i si128; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h]

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2776);
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v3 = *((_QWORD *)this + 11);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v14 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
  if ( *(_DWORD *)(v3 + 192) )
  {
    Log_AssertionEvent_0(v5, v4, 145);
    if ( *(_DWORD *)(v3 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v3 + 144) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
    if ( *(_DWORD *)(v3 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v9, v8, 157);
      if ( *(_DWORD *)(v3 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 32LL))(*i);
      if ( v11 < 0 )
        Log_HREvent_2((unsigned int)v11, 0, v12, 368);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v6, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x180044324  mov     [rsp+arg_8], rbx
0x180044329  push    rdi
0x18004432a  sub     rsp, 50h
0x18004432e  mov     rax, cs:__security_cookie
0x180044335  xor     rax, rsp
0x180044338  mov     [rsp+58h+var_10], rax
0x18004433d  mov     rbx, rcx
0x180044340  call    cs:__imp_GetCurrentThreadId
0x180044346  cmp     [rbx+0F0h], eax
0x18004434c  jnz     short loc_180044373
0x18004434e  mov     r8d, 0AD8h
0x180044354  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004435b  call    Log_AssertionEvent_3
0x180044360  call    cs:__imp_GetCurrentThreadId
0x180044366  cmp     [rbx+0F0h], eax
0x18004436c  jnz     short loc_180044373
0x18004436e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044373  mov     rbx, [rbx+58h]
0x180044377  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004437f  movdqu  [rsp+58h+var_28], xmm0
0x180044385  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x18004438e  lea     rdi, [rbx+0C8h]
0x180044395  mov     rcx, rdi; lpCriticalSection
0x180044398  call    cs:__imp_EnterCriticalSection
0x18004439e  cmp     dword ptr [rbx+0C0h], 0
0x1800443a5  jz      short loc_1800443C0
0x1800443a7  mov     r8d, 91h
0x1800443ad  call    Log_AssertionEvent_0
0x1800443b2  cmp     dword ptr [rbx+0C0h], 0
0x1800443b9  jz      short loc_1800443C0
0x1800443bb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800443c0  lea     rdx, [rbx+90h]
0x1800443c7  lea     rcx, [rsp+58h+var_28]
0x1800443cc  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x1800443d1  test    al, al
0x1800443d3  jnz     short loc_180044414
0x1800443d5  xor     edx, edx
0x1800443d7  mov     r9d, 97h
0x1800443dd  mov     ecx, 8007000Eh
0x1800443e2  call    Log_HREvent_2
0x1800443e7  mov     rcx, rdi; lpCriticalSection
0x1800443ea  call    cs:__imp_LeaveCriticalSection
0x1800443f0  lea     rcx, [rsp+58h+var_28]
0x1800443f5  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800443fa  xor     eax, eax
0x1800443fc  mov     rcx, [rsp+58h+var_10]
0x180044401  xor     rcx, rsp; StackCookie
0x180044404  call    __security_check_cookie
0x180044409  mov     rbx, [rsp+58h+arg_8]
0x18004440e  add     rsp, 50h
0x180044412  pop     rdi
0x180044413  retn
0x180044414  mov     rcx, rdi; lpCriticalSection
0x180044417  call    cs:__imp_LeaveCriticalSection
0x18004441d  call    cs:__imp_GetCurrentThreadId
0x180044423  cmp     [rbx+0D8h], eax
0x180044429  jnz     short loc_180044449
0x18004442b  mov     r8d, 9Dh
0x180044431  call    Log_AssertionEvent_0
0x180044436  call    cs:__imp_GetCurrentThreadId
0x18004443c  cmp     [rbx+0D8h], eax
0x180044442  jnz     short loc_180044449
0x180044444  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044449  mov     rbx, qword ptr [rsp+58h+var_28]
0x18004444e  cmp     rbx, qword ptr [rsp+58h+var_28+8]
0x180044453  jz      short loc_1800443F0
0x180044455  mov     rcx, [rbx]
0x180044458  mov     rax, [rcx]
0x18004445b  mov     rax, [rax+20h]
0x18004445f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044464  test    eax, eax
0x180044466  jns     short loc_180044477
0x180044468  xor     edx, edx
0x18004446a  mov     r9d, 170h
0x180044470  mov     ecx, eax
0x180044472  call    Log_HREvent_2
0x180044477  add     rbx, 8
0x18004447b  jmp     short loc_18004444E
```
