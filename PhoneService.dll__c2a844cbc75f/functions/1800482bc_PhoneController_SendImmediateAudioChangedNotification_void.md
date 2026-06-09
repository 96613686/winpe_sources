# PhoneController::_SendImmediateAudioChangedNotification(void)

- ea: `0x1800482bc`
- end: `0x180048415`
- name: `?_SendImmediateAudioChangedNotification@PhoneController@@IEAAJXZ`
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
- `0x1800482bc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048330`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800482d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800482f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800483b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800483ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800482d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800482f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800483b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800483ce`

## string_xrefs

- `0x1800482ec`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendImmediateAudioChangedNotification(PhoneController *this)
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
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2893);
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
      v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 24LL))(*i);
      if ( v11 < 0 )
        Log_HREvent_2((unsigned int)v11, 0, v12, 358);
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
0x1800482bc  mov     [rsp+arg_8], rbx
0x1800482c1  push    rdi
0x1800482c2  sub     rsp, 50h
0x1800482c6  mov     rax, cs:__security_cookie
0x1800482cd  xor     rax, rsp
0x1800482d0  mov     [rsp+58h+var_10], rax
0x1800482d5  mov     rbx, rcx
0x1800482d8  call    cs:__imp_GetCurrentThreadId
0x1800482de  cmp     [rbx+0F0h], eax
0x1800482e4  jnz     short loc_18004830B
0x1800482e6  mov     r8d, 0B4Dh
0x1800482ec  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800482f3  call    Log_AssertionEvent_3
0x1800482f8  call    cs:__imp_GetCurrentThreadId
0x1800482fe  cmp     [rbx+0F0h], eax
0x180048304  jnz     short loc_18004830B
0x180048306  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004830b  mov     rbx, [rbx+58h]
0x18004830f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180048317  movdqu  [rsp+58h+var_28], xmm0
0x18004831d  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x180048326  lea     rdi, [rbx+0C8h]
0x18004832d  mov     rcx, rdi; lpCriticalSection
0x180048330  call    cs:__imp_EnterCriticalSection
0x180048336  cmp     dword ptr [rbx+0C0h], 0
0x18004833d  jz      short loc_180048358
0x18004833f  mov     r8d, 91h
0x180048345  call    Log_AssertionEvent_0
0x18004834a  cmp     dword ptr [rbx+0C0h], 0
0x180048351  jz      short loc_180048358
0x180048353  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180048358  lea     rdx, [rbx+90h]
0x18004835f  lea     rcx, [rsp+58h+var_28]
0x180048364  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180048369  test    al, al
0x18004836b  jnz     short loc_1800483AC
0x18004836d  xor     edx, edx
0x18004836f  mov     r9d, 97h
0x180048375  mov     ecx, 8007000Eh
0x18004837a  call    Log_HREvent_2
0x18004837f  mov     rcx, rdi; lpCriticalSection
0x180048382  call    cs:__imp_LeaveCriticalSection
0x180048388  lea     rcx, [rsp+58h+var_28]
0x18004838d  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180048392  xor     eax, eax
0x180048394  mov     rcx, [rsp+58h+var_10]
0x180048399  xor     rcx, rsp; StackCookie
0x18004839c  call    __security_check_cookie
0x1800483a1  mov     rbx, [rsp+58h+arg_8]
0x1800483a6  add     rsp, 50h
0x1800483aa  pop     rdi
0x1800483ab  retn
0x1800483ac  mov     rcx, rdi; lpCriticalSection
0x1800483af  call    cs:__imp_LeaveCriticalSection
0x1800483b5  call    cs:__imp_GetCurrentThreadId
0x1800483bb  cmp     [rbx+0D8h], eax
0x1800483c1  jnz     short loc_1800483E1
0x1800483c3  mov     r8d, 9Dh
0x1800483c9  call    Log_AssertionEvent_0
0x1800483ce  call    cs:__imp_GetCurrentThreadId
0x1800483d4  cmp     [rbx+0D8h], eax
0x1800483da  jnz     short loc_1800483E1
0x1800483dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800483e1  mov     rbx, qword ptr [rsp+58h+var_28]
0x1800483e6  cmp     rbx, qword ptr [rsp+58h+var_28+8]
0x1800483eb  jz      short loc_180048388
0x1800483ed  mov     rcx, [rbx]
0x1800483f0  mov     rax, [rcx]
0x1800483f3  mov     rax, [rax+18h]
0x1800483f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483fc  test    eax, eax
0x1800483fe  jns     short loc_18004840F
0x180048400  xor     edx, edx
0x180048402  mov     r9d, 166h
0x180048408  mov     ecx, eax
0x18004840a  call    Log_HREvent_2
0x18004840f  add     rbx, 8
0x180048413  jmp     short loc_1800483E6
```
