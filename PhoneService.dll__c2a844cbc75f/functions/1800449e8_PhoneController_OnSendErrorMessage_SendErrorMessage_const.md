# PhoneController::_OnSendErrorMessage(SendErrorMessage const *)

- ea: `0x1800449e8`
- end: `0x180044b64`
- name: `?_OnSendErrorMessage@PhoneController@@IEAAJPEBVSendErrorMessage@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct SendErrorMessage *)`
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
- `0x1800449e8`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044a6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044a6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044abd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044af4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044abd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044af4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044afa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044afa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044b13`

## string_xrefs

- `0x180044a23`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnSendErrorMessage(PhoneController *this, const struct SendErrorMessage *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  unsigned int v6; // ebp
  unsigned int v7; // r14d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *i; // rbx
  int v15; // eax
  __int64 v16; // r8
  __m128i si128; // [rsp+40h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-28h]

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2861);
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 11);
  v6 = *((_DWORD *)a2 + 15);
  v7 = *((_DWORD *)a2 + 14);
  v18 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  if ( *(_DWORD *)(v5 + 192) )
  {
    Log_AssertionEvent_0(v9, v8, 145);
    if ( *(_DWORD *)(v5 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v5 + 120) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
    if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v13, v12, 157);
      if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(*(_QWORD *)*i + 48LL))(
              *i,
              (char *)a2 + 32,
              v7,
              v6);
      if ( v15 < 0 )
        Log_HREvent_2((unsigned int)v15, 0, v16, 326);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v10, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x1800449e8  mov     [rsp+arg_8], rbx
0x1800449ed  mov     [rsp+arg_10], rbp
0x1800449f2  push    rsi
0x1800449f3  push    rdi
0x1800449f4  push    r14
0x1800449f6  sub     rsp, 60h
0x1800449fa  mov     rax, cs:__security_cookie
0x180044a01  xor     rax, rsp
0x180044a04  mov     [rsp+78h+var_20], rax
0x180044a09  mov     rsi, rdx
0x180044a0c  mov     rbx, rcx
0x180044a0f  call    cs:__imp_GetCurrentThreadId
0x180044a15  cmp     [rbx+0F0h], eax
0x180044a1b  jnz     short loc_180044A42
0x180044a1d  mov     r8d, 0B2Dh
0x180044a23  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180044a2a  call    Log_AssertionEvent_3
0x180044a2f  call    cs:__imp_GetCurrentThreadId
0x180044a35  cmp     [rbx+0F0h], eax
0x180044a3b  jnz     short loc_180044A42
0x180044a3d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044a42  mov     rbx, [rbx+58h]
0x180044a46  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180044a4e  mov     ebp, [rsi+3Ch]
0x180044a51  mov     r14d, [rsi+38h]
0x180044a55  lea     rdi, [rbx+0C8h]
0x180044a5c  mov     [rsp+78h+var_28], 0FFFFFFFFFFFFFFFFh
0x180044a65  mov     rcx, rdi; lpCriticalSection
0x180044a68  movdqu  [rsp+78h+var_38], xmm0
0x180044a6e  call    cs:__imp_EnterCriticalSection
0x180044a74  cmp     dword ptr [rbx+0C0h], 0
0x180044a7b  jz      short loc_180044A96
0x180044a7d  mov     r8d, 91h
0x180044a83  call    Log_AssertionEvent_0
0x180044a88  cmp     dword ptr [rbx+0C0h], 0
0x180044a8f  jz      short loc_180044A96
0x180044a91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044a96  lea     rdx, [rbx+78h]
0x180044a9a  lea     rcx, [rsp+78h+var_38]
0x180044a9f  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180044aa4  test    al, al
0x180044aa6  jnz     short loc_180044AF1
0x180044aa8  xor     edx, edx
0x180044aaa  mov     ecx, 8007000Eh
0x180044aaf  mov     r9d, 97h
0x180044ab5  call    Log_HREvent_2
0x180044aba  mov     rcx, rdi; lpCriticalSection
0x180044abd  call    cs:__imp_LeaveCriticalSection
0x180044ac3  lea     rcx, [rsp+78h+var_38]
0x180044ac8  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180044acd  xor     eax, eax
0x180044acf  mov     rcx, [rsp+78h+var_20]
0x180044ad4  xor     rcx, rsp; StackCookie
0x180044ad7  call    __security_check_cookie
0x180044adc  lea     r11, [rsp+78h+var_18]
0x180044ae1  mov     rbx, [r11+28h]
0x180044ae5  mov     rbp, [r11+30h]
0x180044ae9  mov     rsp, r11
0x180044aec  pop     r14
0x180044aee  pop     rdi
0x180044aef  pop     rsi
0x180044af0  retn
0x180044af1  mov     rcx, rdi; lpCriticalSection
0x180044af4  call    cs:__imp_LeaveCriticalSection
0x180044afa  call    cs:__imp_GetCurrentThreadId
0x180044b00  cmp     [rbx+0D8h], eax
0x180044b06  jnz     short loc_180044B26
0x180044b08  mov     r8d, 9Dh
0x180044b0e  call    Log_AssertionEvent_0
0x180044b13  call    cs:__imp_GetCurrentThreadId
0x180044b19  cmp     [rbx+0D8h], eax
0x180044b1f  jnz     short loc_180044B26
0x180044b21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044b26  mov     rbx, qword ptr [rsp+78h+var_38]
0x180044b2b  cmp     rbx, qword ptr [rsp+78h+var_38+8]
0x180044b30  jz      short loc_180044AC3
0x180044b32  mov     rcx, [rbx]
0x180044b35  lea     rdx, [rsi+20h]
0x180044b39  mov     r9d, ebp
0x180044b3c  mov     r8d, r14d
0x180044b3f  mov     rax, [rcx]
0x180044b42  mov     rax, [rax+30h]
0x180044b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b4b  test    eax, eax
0x180044b4d  jns     short loc_180044B5E
0x180044b4f  xor     edx, edx
0x180044b51  mov     r9d, 146h
0x180044b57  mov     ecx, eax
0x180044b59  call    Log_HREvent_2
0x180044b5e  add     rbx, 8
0x180044b62  jmp     short loc_180044B2B
```
