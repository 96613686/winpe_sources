# PhoneController::_FindAndSetNewPreferredCallUpgradeLine(void)

- ea: `0x18003a744`
- end: `0x18003a948`
- name: `?_FindAndSetNewPreferredCallUpgradeLine@PhoneController@@IEAAJXZ`
- size: `516`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003baf0`
- `0x180044484`

## callees

- `0x180006e94`
- `0x18000e1a4`
- `0x180010664`
- `0x1800107d8`
- `0x18002c574`
- `0x18002c580`
- `0x18003a744`
- `0x180049284`
- `0x18004b834`
- `0x180051b58`
- `0x180051fd0`
- `0x180075ca0`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a79d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a79d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a7ba`

## string_xrefs

- `0x18003a76b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_FindAndSetNewPreferredCallUpgradeLine(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rsi
  const struct PhoneLine *v5; // rbx
  PhoneLine **v6; // rdi
  PhoneLine **v7; // rsi
  BackTraceCollection *v8; // rcx
  int v9; // edi
  __int64 v10; // r8
  BackTraceCollection *v11; // rcx
  BackTraceCollection *v12; // rcx
  __int64 v13; // r9
  int v15; // eax
  BackTraceCollection *v16; // rcx
  volatile __int32 *v17; // [rsp+30h] [rbp-48h] BYREF
  __m128i si128; // [rsp+38h] [rbp-40h] BYREF
  __int64 v19; // [rsp+48h] [rbp-30h]
  __m128i v20; // [rsp+50h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-18h]

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 814);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v3, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 828);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v4 = *((_QWORD *)this + 19);
  v5 = 0;
  v19 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(&v17, v4 + 48);
  v21 = -1;
  v6 = *(PhoneLine ***)(v4 + 24);
  v7 = *(PhoneLine ***)(v4 + 32);
  v20 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  while ( v6 != v7 )
  {
    if ( (unsigned int)PhoneLine::SupportsCallUpgrade(*v6)
      && !(unsigned __int8)utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>>::push_back(
                             &v20,
                             v6) )
    {
      v9 = -2147024882;
      BackTraceCollection::Capture(v8, -2147024882);
      Log_HREvent_12(2147942414LL, 0, v10, 174);
      goto LABEL_14;
    }
    ++v6;
  }
  utl::vector<ATL::CComPtr<PhoneLine>,utl::allocator<ATL::CComPtr<PhoneLine>>>::operator=(
    (__int64)&si128,
    v20.m128i_i64);
  v9 = 0;
LABEL_14:
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v20);
  utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(&v17);
  if ( v9 >= 0 )
  {
    if ( (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 3 )
    {
      v5 = *(const struct PhoneLine **)si128.m128i_i64[0];
      *(_QWORD *)si128.m128i_i64[0] = 0;
    }
    v9 = 0;
  }
  else
  {
    BackTraceCollection::Capture(v11, v9);
    Log_HREvent_7((unsigned int)v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 840);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  if ( v9 < 0 )
  {
    BackTraceCollection::Capture(v12, v9);
    v13 = 817;
LABEL_21:
    Log_HREvent_7((unsigned int)v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v13);
    if ( v5 )
      (*(void (__fastcall **)(const struct PhoneLine *))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)v9;
  }
  v15 = PhoneController::_SetPreferredCallUpgradeLine(this, v5);
  v9 = v15;
  if ( v15 < 0 )
  {
    BackTraceCollection::Capture(v16, v15);
    v13 = 819;
    goto LABEL_21;
  }
  if ( v5 )
    (*(void (__fastcall **)(const struct PhoneLine *))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18003a744  push    rbp
0x18003a746  push    rbx
0x18003a747  push    rsi
0x18003a748  push    rdi
0x18003a749  push    r14
0x18003a74b  push    r15
0x18003a74d  mov     rbp, rsp
0x18003a750  sub     rsp, 78h
0x18003a754  mov     rax, cs:__security_cookie
0x18003a75b  xor     rax, rsp
0x18003a75e  mov     [rbp+var_10], rax
0x18003a762  mov     r14, rcx
0x18003a765  call    cs:__imp_GetCurrentThreadId
0x18003a76b  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003a772  cmp     [r14+0F0h], eax
0x18003a779  jz      short loc_18003A79D
0x18003a77b  mov     r8d, 32Eh
0x18003a781  mov     rdx, r15
0x18003a784  call    Log_AssertionEvent_3
0x18003a789  call    cs:__imp_GetCurrentThreadId
0x18003a78f  cmp     [r14+0F0h], eax
0x18003a796  jz      short loc_18003A79D
0x18003a798  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a79d  call    cs:__imp_GetCurrentThreadId
0x18003a7a3  cmp     [r14+0F0h], eax
0x18003a7aa  jz      short loc_18003A7CE
0x18003a7ac  mov     r8d, 33Ch
0x18003a7b2  mov     rdx, r15
0x18003a7b5  call    Log_AssertionEvent_3
0x18003a7ba  call    cs:__imp_GetCurrentThreadId
0x18003a7c0  cmp     [r14+0F0h], eax
0x18003a7c7  jz      short loc_18003A7CE
0x18003a7c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a7ce  mov     rsi, [r14+98h]
0x18003a7d5  lea     rcx, [rbp+var_48]
0x18003a7d9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003a7e1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003a7e5  xor     ebx, ebx
0x18003a7e7  mov     [rbp+var_30], rdi
0x18003a7eb  movdqu  [rbp+var_40], xmm0
0x18003a7f0  lea     rdx, [rsi+30h]
0x18003a7f4  call    ??0?$lock_guard@VThreadCheck@@@utl@@QEAA@AEAVThreadCheck@@@Z; utl::lock_guard<ThreadCheck>::lock_guard<ThreadCheck>(ThreadCheck &)
0x18003a7f9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003a801  mov     [rbp+var_18], rdi
0x18003a805  mov     rdi, [rsi+18h]
0x18003a809  mov     rsi, [rsi+20h]
0x18003a80d  movdqu  [rbp+var_28], xmm0
0x18003a812  cmp     rdi, rsi
0x18003a815  jz      short loc_18003A856
0x18003a817  mov     rcx, [rdi]; this
0x18003a81a  call    ?SupportsCallUpgrade@PhoneLine@@QEBAHXZ; PhoneLine::SupportsCallUpgrade(void)
0x18003a81f  test    eax, eax
0x18003a821  jz      short loc_18003A833
0x18003a823  mov     rdx, rdi
0x18003a826  lea     rcx, [rbp+var_28]
0x18003a82a  call    ?push_back@?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@QEAA_NAEBV?$CComPtr@VCallInfo@@@ATL@@@Z; utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>>::push_back(ATL::CComPtr<CallInfo> const &)
0x18003a82f  test    al, al
0x18003a831  jz      short loc_18003A839
0x18003a833  add     rdi, 8
0x18003a837  jmp     short loc_18003A812
0x18003a839  mov     edi, 8007000Eh
0x18003a83e  mov     edx, edi; int
0x18003a840  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003a845  xor     edx, edx
0x18003a847  mov     r9d, 0AEh
0x18003a84d  mov     ecx, edi
0x18003a84f  call    Log_HREvent_12
0x18003a854  jmp     short loc_18003A865
0x18003a856  lea     rdx, [rbp+var_28]
0x18003a85a  lea     rcx, [rbp+var_40]
0x18003a85e  call    ??4?$vector@V?$CComPtr@VPhoneLine@@@ATL@@V?$allocator@V?$CComPtr@VPhoneLine@@@ATL@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::vector<ATL::CComPtr<PhoneLine>,utl::allocator<ATL::CComPtr<PhoneLine>>>::operator=(utl::vector<ATL::CComPtr<PhoneLine>,utl::allocator<ATL::CComPtr<PhoneLine>>> &&)
0x18003a863  xor     edi, edi
0x18003a865  lea     rcx, [rbp+var_28]
0x18003a869  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003a86e  lea     rcx, [rbp+var_48]
0x18003a872  call    ??1?$lock_guard@VThreadCheck@@@utl@@QEAA@XZ; utl::lock_guard<ThreadCheck>::~lock_guard<ThreadCheck>(void)
0x18003a877  mov     esi, 1
0x18003a87c  test    edi, edi
0x18003a87e  jns     short loc_18003A89B
0x18003a880  mov     edx, edi; int
0x18003a882  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003a887  mov     r9d, 348h
0x18003a88d  mov     r8, r15
0x18003a890  mov     edx, esi
0x18003a892  mov     ecx, edi
0x18003a894  call    Log_HREvent_7
0x18003a899  jmp     short loc_18003A8BB
0x18003a89b  mov     rax, qword ptr [rbp+var_40+8]
0x18003a89f  mov     rcx, qword ptr [rbp+var_40]
0x18003a8a3  sub     rax, rcx
0x18003a8a6  sar     rax, 3
0x18003a8aa  test    rax, rax
0x18003a8ad  jz      short loc_18003A8B9
0x18003a8af  mov     rbx, [rcx]
0x18003a8b2  mov     qword ptr [rcx], 0
0x18003a8b9  xor     edi, edi
0x18003a8bb  lea     rcx, [rbp+var_40]
0x18003a8bf  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003a8c4  test    edi, edi
0x18003a8c6  jns     short loc_18003A8F9
0x18003a8c8  mov     edx, edi; int
0x18003a8ca  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003a8cf  mov     r9d, 331h
0x18003a8d5  mov     r8, r15
0x18003a8d8  mov     edx, esi
0x18003a8da  mov     ecx, edi
0x18003a8dc  call    Log_HREvent_7
0x18003a8e1  test    rbx, rbx
0x18003a8e4  jz      short loc_18003A8F5
0x18003a8e6  mov     rcx, [rbx]
0x18003a8e9  mov     rax, [rcx+10h]
0x18003a8ed  mov     rcx, rbx
0x18003a8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8f5  mov     eax, edi
0x18003a8f7  jmp     short loc_18003A92F
0x18003a8f9  mov     rdx, rbx; struct PhoneLine *
0x18003a8fc  mov     rcx, r14; this
0x18003a8ff  call    ?_SetPreferredCallUpgradeLine@PhoneController@@IEAAJPEBVPhoneLine@@@Z; PhoneController::_SetPreferredCallUpgradeLine(PhoneLine const *)
0x18003a904  mov     edi, eax
0x18003a906  test    eax, eax
0x18003a908  jns     short loc_18003A919
0x18003a90a  mov     edx, eax; int
0x18003a90c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003a911  mov     r9d, 333h
0x18003a917  jmp     short loc_18003A8D5
0x18003a919  test    rbx, rbx
0x18003a91c  jz      short loc_18003A92D
0x18003a91e  mov     rax, [rbx]
0x18003a921  mov     rcx, rbx
0x18003a924  mov     rax, [rax+10h]
0x18003a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a92d  xor     eax, eax
0x18003a92f  mov     rcx, [rbp+var_10]
0x18003a933  xor     rcx, rsp; StackCookie
0x18003a936  call    __security_check_cookie
0x18003a93b  add     rsp, 78h
0x18003a93f  pop     r15
0x18003a941  pop     r14
0x18003a943  pop     rdi
0x18003a944  pop     rsi
0x18003a945  pop     rbx
0x18003a946  pop     rbp
0x18003a947  retn
```
