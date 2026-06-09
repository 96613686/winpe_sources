# PhoneController::_OnWifiCallDropWarningMessage(void)

- ea: `0x180044f68`
- end: `0x1800450be`
- name: `?_OnWifiCallDropWarningMessage@PhoneController@@IEAAJXZ`
- size: `342`
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
- `0x180044f68`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044fdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044fdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004502b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004502b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044fa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004505e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044fa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004505e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045077`

## string_xrefs

- `0x180044f98`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnWifiCallDropWarningMessage(PhoneController *this)
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
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4840);
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
                          v3 + 120) )
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
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 64LL))(*i);
      if ( v11 < 0 )
        Log_HREvent_2((unsigned int)v11, 0, v12, 348);
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
0x180044f68  mov     [rsp+arg_8], rbx
0x180044f6d  push    rdi
0x180044f6e  sub     rsp, 50h
0x180044f72  mov     rax, cs:__security_cookie
0x180044f79  xor     rax, rsp
0x180044f7c  mov     [rsp+58h+var_10], rax
0x180044f81  mov     rbx, rcx
0x180044f84  call    cs:__imp_GetCurrentThreadId
0x180044f8a  cmp     [rbx+0F0h], eax
0x180044f90  jnz     short loc_180044FB7
0x180044f92  mov     r8d, 12E8h
0x180044f98  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180044f9f  call    Log_AssertionEvent_3
0x180044fa4  call    cs:__imp_GetCurrentThreadId
0x180044faa  cmp     [rbx+0F0h], eax
0x180044fb0  jnz     short loc_180044FB7
0x180044fb2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044fb7  mov     rbx, [rbx+58h]
0x180044fbb  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180044fc3  movdqu  [rsp+58h+var_28], xmm0
0x180044fc9  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x180044fd2  lea     rdi, [rbx+0C8h]
0x180044fd9  mov     rcx, rdi; lpCriticalSection
0x180044fdc  call    cs:__imp_EnterCriticalSection
0x180044fe2  cmp     dword ptr [rbx+0C0h], 0
0x180044fe9  jz      short loc_180045004
0x180044feb  mov     r8d, 91h
0x180044ff1  call    Log_AssertionEvent_0
0x180044ff6  cmp     dword ptr [rbx+0C0h], 0
0x180044ffd  jz      short loc_180045004
0x180044fff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180045004  lea     rdx, [rbx+78h]
0x180045008  lea     rcx, [rsp+58h+var_28]
0x18004500d  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180045012  test    al, al
0x180045014  jnz     short loc_180045055
0x180045016  xor     edx, edx
0x180045018  mov     r9d, 97h
0x18004501e  mov     ecx, 8007000Eh
0x180045023  call    Log_HREvent_2
0x180045028  mov     rcx, rdi; lpCriticalSection
0x18004502b  call    cs:__imp_LeaveCriticalSection
0x180045031  lea     rcx, [rsp+58h+var_28]
0x180045036  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004503b  xor     eax, eax
0x18004503d  mov     rcx, [rsp+58h+var_10]
0x180045042  xor     rcx, rsp; StackCookie
0x180045045  call    __security_check_cookie
0x18004504a  mov     rbx, [rsp+58h+arg_8]
0x18004504f  add     rsp, 50h
0x180045053  pop     rdi
0x180045054  retn
0x180045055  mov     rcx, rdi; lpCriticalSection
0x180045058  call    cs:__imp_LeaveCriticalSection
0x18004505e  call    cs:__imp_GetCurrentThreadId
0x180045064  cmp     [rbx+0D8h], eax
0x18004506a  jnz     short loc_18004508A
0x18004506c  mov     r8d, 9Dh
0x180045072  call    Log_AssertionEvent_0
0x180045077  call    cs:__imp_GetCurrentThreadId
0x18004507d  cmp     [rbx+0D8h], eax
0x180045083  jnz     short loc_18004508A
0x180045085  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004508a  mov     rbx, qword ptr [rsp+58h+var_28]
0x18004508f  cmp     rbx, qword ptr [rsp+58h+var_28+8]
0x180045094  jz      short loc_180045031
0x180045096  mov     rcx, [rbx]
0x180045099  mov     rax, [rcx]
0x18004509c  mov     rax, [rax+40h]
0x1800450a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450a5  test    eax, eax
0x1800450a7  jns     short loc_1800450B8
0x1800450a9  xor     edx, edx
0x1800450ab  mov     r9d, 15Ch
0x1800450b1  mov     ecx, eax
0x1800450b3  call    Log_HREvent_2
0x1800450b8  add     rbx, 8
0x1800450bc  jmp     short loc_18004508F
```
