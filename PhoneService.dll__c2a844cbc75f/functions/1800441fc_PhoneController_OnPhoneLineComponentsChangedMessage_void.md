# PhoneController::_OnPhoneLineComponentsChangedMessage(void)

- ea: `0x1800441fc`
- end: `0x18004431c`
- name: `?_OnPhoneLineComponentsChangedMessage@PhoneController@@IEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000fb70`
- `0x1800441fc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004423a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004423a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800442b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044289`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800442b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442d5`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnPhoneLineComponentsChangedMessage(PhoneController *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *i; // rbx
  int v9; // eax
  __int64 v10; // r8
  __m128i si128; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]

  v1 = *((_QWORD *)this + 11);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v12 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 200));
  if ( *(_DWORD *)(v1 + 192) )
  {
    Log_AssertionEvent_0(v3, v2, 145);
    if ( *(_DWORD *)(v1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v1 + 96) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 200));
    if ( *(_DWORD *)(v1 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v7, v6, 157);
      if ( *(_DWORD *)(v1 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 24LL))(*i);
      if ( v9 < 0 )
        Log_HREvent_2((unsigned int)v9, 0, v10, 209);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v4, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x1800441fc  mov     [rsp+arg_8], rbx
0x180044201  push    rdi
0x180044202  sub     rsp, 50h
0x180044206  mov     rax, cs:__security_cookie
0x18004420d  xor     rax, rsp
0x180044210  mov     [rsp+58h+var_10], rax
0x180044215  mov     rbx, [rcx+58h]
0x180044219  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180044221  movdqu  [rsp+58h+var_28], xmm0
0x180044227  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x180044230  lea     rdi, [rbx+0C8h]
0x180044237  mov     rcx, rdi; lpCriticalSection
0x18004423a  call    cs:__imp_EnterCriticalSection
0x180044240  cmp     dword ptr [rbx+0C0h], 0
0x180044247  jz      short loc_180044262
0x180044249  mov     r8d, 91h
0x18004424f  call    Log_AssertionEvent_0
0x180044254  cmp     dword ptr [rbx+0C0h], 0
0x18004425b  jz      short loc_180044262
0x18004425d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044262  lea     rdx, [rbx+60h]
0x180044266  lea     rcx, [rsp+58h+var_28]
0x18004426b  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180044270  test    al, al
0x180044272  jnz     short loc_1800442B3
0x180044274  xor     edx, edx
0x180044276  mov     r9d, 97h
0x18004427c  mov     ecx, 8007000Eh
0x180044281  call    Log_HREvent_2
0x180044286  mov     rcx, rdi; lpCriticalSection
0x180044289  call    cs:__imp_LeaveCriticalSection
0x18004428f  lea     rcx, [rsp+58h+var_28]
0x180044294  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180044299  xor     eax, eax
0x18004429b  mov     rcx, [rsp+58h+var_10]
0x1800442a0  xor     rcx, rsp; StackCookie
0x1800442a3  call    __security_check_cookie
0x1800442a8  mov     rbx, [rsp+58h+arg_8]
0x1800442ad  add     rsp, 50h
0x1800442b1  pop     rdi
0x1800442b2  retn
0x1800442b3  mov     rcx, rdi; lpCriticalSection
0x1800442b6  call    cs:__imp_LeaveCriticalSection
0x1800442bc  call    cs:__imp_GetCurrentThreadId
0x1800442c2  cmp     [rbx+0D8h], eax
0x1800442c8  jnz     short loc_1800442E8
0x1800442ca  mov     r8d, 9Dh
0x1800442d0  call    Log_AssertionEvent_0
0x1800442d5  call    cs:__imp_GetCurrentThreadId
0x1800442db  cmp     [rbx+0D8h], eax
0x1800442e1  jnz     short loc_1800442E8
0x1800442e3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800442e8  mov     rbx, qword ptr [rsp+58h+var_28]
0x1800442ed  cmp     rbx, qword ptr [rsp+58h+var_28+8]
0x1800442f2  jz      short loc_18004428F
0x1800442f4  mov     rcx, [rbx]
0x1800442f7  mov     rax, [rcx]
0x1800442fa  mov     rax, [rax+18h]
0x1800442fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044303  test    eax, eax
0x180044305  jns     short loc_180044316
0x180044307  xor     edx, edx
0x180044309  mov     r9d, 0D1h
0x18004430f  mov     ecx, eax
0x180044311  call    Log_HREvent_2
0x180044316  add     rbx, 8
0x18004431a  jmp     short loc_1800442ED
```
