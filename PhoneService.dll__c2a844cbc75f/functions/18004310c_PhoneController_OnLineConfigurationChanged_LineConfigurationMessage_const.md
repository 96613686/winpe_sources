# PhoneController::_OnLineConfigurationChanged(LineConfigurationMessage const *)

- ea: `0x18004310c`
- end: `0x18004326a`
- name: `?_OnLineConfigurationChanged@PhoneController@@IEAAJPEBVLineConfigurationMessage@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct LineConfigurationMessage *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000fb70`
- `0x18002c574`
- `0x18004310c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043182`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800431d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800431fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800431d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800431fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004312a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004314a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004321b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004312a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004314a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043202`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004321b`

## string_xrefs

- `0x18004313e`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnLineConfigurationChanged(
        PhoneController *this,
        const struct LineConfigurationMessage *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *i; // rbx
  int v13; // eax
  __int64 v14; // r8
  __m128i si128; // [rsp+38h] [rbp-50h] BYREF
  __int64 v16; // [rsp+48h] [rbp-40h]

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2634);
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 11);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v16 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  if ( *(_DWORD *)(v5 + 192) )
  {
    Log_AssertionEvent_0(v7, v6, 145);
    if ( *(_DWORD *)(v5 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v5 + 96) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
    if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v11, v10, 157);
      if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*i + 64LL))(
              *i,
              (char *)a2 + 32,
              (char *)a2 + 56);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 277);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v8, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x18004310c  push    rbx
0x18004310e  push    rbp
0x18004310f  push    rsi
0x180043110  push    rdi
0x180043111  sub     rsp, 68h
0x180043115  mov     rax, cs:__security_cookie
0x18004311c  xor     rax, rsp
0x18004311f  mov     [rsp+88h+var_38], rax
0x180043124  mov     rsi, rdx
0x180043127  mov     rbx, rcx
0x18004312a  call    cs:__imp_GetCurrentThreadId
0x180043130  cmp     [rbx+0F0h], eax
0x180043136  jnz     short loc_18004315D
0x180043138  mov     r8d, 0A4Ah
0x18004313e  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180043145  call    Log_AssertionEvent_3
0x18004314a  call    cs:__imp_GetCurrentThreadId
0x180043150  cmp     [rbx+0F0h], eax
0x180043156  jnz     short loc_18004315D
0x180043158  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004315d  mov     rbx, [rbx+58h]
0x180043161  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180043169  movdqu  [rsp+88h+var_50], xmm0
0x18004316f  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x180043178  lea     rdi, [rbx+0C8h]
0x18004317f  mov     rcx, rdi; lpCriticalSection
0x180043182  call    cs:__imp_EnterCriticalSection
0x180043188  cmp     dword ptr [rbx+0C0h], 0
0x18004318f  jz      short loc_1800431AA
0x180043191  mov     r8d, 91h
0x180043197  call    Log_AssertionEvent_0
0x18004319c  cmp     dword ptr [rbx+0C0h], 0
0x1800431a3  jz      short loc_1800431AA
0x1800431a5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800431aa  lea     rdx, [rbx+60h]
0x1800431ae  lea     rcx, [rsp+88h+var_50]
0x1800431b3  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x1800431b8  test    al, al
0x1800431ba  jnz     short loc_1800431F9
0x1800431bc  xor     edx, edx
0x1800431be  mov     ecx, 8007000Eh
0x1800431c3  mov     r9d, 97h
0x1800431c9  call    Log_HREvent_2
0x1800431ce  mov     rcx, rdi; lpCriticalSection
0x1800431d1  call    cs:__imp_LeaveCriticalSection
0x1800431d7  lea     rcx, [rsp+88h+var_50]
0x1800431dc  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800431e1  xor     eax, eax
0x1800431e3  mov     rcx, [rsp+88h+var_38]
0x1800431e8  xor     rcx, rsp; StackCookie
0x1800431eb  call    __security_check_cookie
0x1800431f0  add     rsp, 68h
0x1800431f4  pop     rdi
0x1800431f5  pop     rsi
0x1800431f6  pop     rbp
0x1800431f7  pop     rbx
0x1800431f8  retn
0x1800431f9  mov     rcx, rdi; lpCriticalSection
0x1800431fc  call    cs:__imp_LeaveCriticalSection
0x180043202  call    cs:__imp_GetCurrentThreadId
0x180043208  cmp     [rbx+0D8h], eax
0x18004320e  jnz     short loc_18004322E
0x180043210  mov     r8d, 9Dh
0x180043216  call    Log_AssertionEvent_0
0x18004321b  call    cs:__imp_GetCurrentThreadId
0x180043221  cmp     [rbx+0D8h], eax
0x180043227  jnz     short loc_18004322E
0x180043229  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004322e  mov     rbx, qword ptr [rsp+88h+var_50]
0x180043233  cmp     rbx, qword ptr [rsp+88h+var_50+8]
0x180043238  jz      short loc_1800431D7
0x18004323a  mov     rcx, [rbx]
0x18004323d  lea     r8, [rsi+38h]
0x180043241  lea     rdx, [rsi+20h]
0x180043245  mov     rax, [rcx]
0x180043248  mov     rax, [rax+40h]
0x18004324c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043251  test    eax, eax
0x180043253  jns     short loc_180043264
0x180043255  xor     edx, edx
0x180043257  mov     r9d, 115h
0x18004325d  mov     ecx, eax
0x18004325f  call    Log_HREvent_2
0x180043264  add     rbx, 8
0x180043268  jmp     short loc_180043233
```
