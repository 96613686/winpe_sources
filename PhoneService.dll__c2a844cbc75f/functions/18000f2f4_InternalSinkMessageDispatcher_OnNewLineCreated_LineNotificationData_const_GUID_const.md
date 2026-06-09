# InternalSinkMessageDispatcher::OnNewLineCreated(LineNotificationData const &,_GUID const &)

- ea: `0x18000f2f4`
- end: `0x18000f461`
- name: `?OnNewLineCreated@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@AEBU_GUID@@@Z`
- size: `365`
- prototype: `void __fastcall(InternalSinkMessageDispatcher *__hidden this, const struct LineNotificationData *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180043c58`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f2f4`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f35c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f35c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f412`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f412`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnNewLineCreated(
        struct _RTL_CRITICAL_SECTION *this,
        const struct LineNotificationData *a2,
        const struct _GUID *a3)
{
  __int128 v3; // xmm0
  __int64 v6; // rcx
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
  __int128 v17; // [rsp+48h] [rbp-30h] BYREF
  __int64 v18; // [rsp+58h] [rbp-20h]

  v3 = *(_OWORD *)a2;
  v6 = *((_QWORD *)a2 + 2);
  v18 = v6;
  v17 = v3;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
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
                          &this[1].SpinCount) )
  {
    LeaveCriticalSection(this + 5);
    if ( LODWORD(this[5].OwningThread) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v11, v10, 157);
      if ( LODWORD(this[5].OwningThread) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, const struct _GUID *))(*(_QWORD *)*i + 24LL))(*i, &v17, a3);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 188);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v9, 151);
    LeaveCriticalSection(this + 5);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
}

```

## disassembly

```asm
0x18000f2f4  mov     [rsp+arg_8], rbx
0x18000f2f9  mov     [rsp+arg_10], rsi
0x18000f2fe  push    rdi
0x18000f2ff  sub     rsp, 70h
0x18000f303  mov     rax, cs:__security_cookie
0x18000f30a  xor     rax, rsp
0x18000f30d  mov     [rsp+78h+var_18], rax
0x18000f312  movups  xmm0, xmmword ptr [rdx]
0x18000f315  mov     rbx, rcx
0x18000f318  mov     rsi, r8
0x18000f31b  mov     rcx, [rdx+10h]
0x18000f31f  mov     [rsp+78h+var_20], rcx
0x18000f324  movdqu  [rsp+78h+var_30], xmm0
0x18000f32a  test    rcx, rcx
0x18000f32d  jz      short loc_18000F33B
0x18000f32f  mov     rax, [rcx]
0x18000f332  mov     rax, [rax+8]
0x18000f336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f33b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000f343  lea     rdi, [rbx+0C8h]
0x18000f34a  mov     rcx, rdi; lpCriticalSection
0x18000f34d  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x18000f356  movdqu  [rsp+78h+var_48], xmm0
0x18000f35c  call    cs:__imp_EnterCriticalSection
0x18000f362  cmp     dword ptr [rbx+0C0h], 0
0x18000f369  jz      short loc_18000F384
0x18000f36b  mov     r8d, 91h
0x18000f371  call    Log_AssertionEvent_0
0x18000f376  cmp     dword ptr [rbx+0C0h], 0
0x18000f37d  jz      short loc_18000F384
0x18000f37f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f384  lea     rdx, [rbx+48h]
0x18000f388  lea     rcx, [rsp+78h+var_48]
0x18000f38d  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000f392  test    al, al
0x18000f394  jnz     short loc_18000F3F0
0x18000f396  xor     edx, edx
0x18000f398  mov     r9d, 97h
0x18000f39e  mov     ecx, 8007000Eh
0x18000f3a3  call    Log_HREvent_2
0x18000f3a8  mov     rcx, rdi; lpCriticalSection
0x18000f3ab  call    cs:__imp_LeaveCriticalSection
0x18000f3b1  lea     rcx, [rsp+78h+var_48]
0x18000f3b6  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000f3bb  mov     rcx, [rsp+78h+var_20]
0x18000f3c0  test    rcx, rcx
0x18000f3c3  jz      short loc_18000F3D1
0x18000f3c5  mov     rax, [rcx]
0x18000f3c8  mov     rax, [rax+10h]
0x18000f3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d1  mov     rcx, [rsp+78h+var_18]
0x18000f3d6  xor     rcx, rsp; StackCookie
0x18000f3d9  call    __security_check_cookie
0x18000f3de  lea     r11, [rsp+78h+var_8]
0x18000f3e3  mov     rbx, [r11+18h]
0x18000f3e7  mov     rsi, [r11+20h]
0x18000f3eb  mov     rsp, r11
0x18000f3ee  pop     rdi
0x18000f3ef  retn
0x18000f3f0  mov     rcx, rdi; lpCriticalSection
0x18000f3f3  call    cs:__imp_LeaveCriticalSection
0x18000f3f9  call    cs:__imp_GetCurrentThreadId
0x18000f3ff  cmp     [rbx+0D8h], eax
0x18000f405  jnz     short loc_18000F425
0x18000f407  mov     r8d, 9Dh
0x18000f40d  call    Log_AssertionEvent_0
0x18000f412  call    cs:__imp_GetCurrentThreadId
0x18000f418  cmp     [rbx+0D8h], eax
0x18000f41e  jnz     short loc_18000F425
0x18000f420  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f425  mov     rbx, qword ptr [rsp+78h+var_48]
0x18000f42a  cmp     rbx, qword ptr [rsp+78h+var_48+8]
0x18000f42f  jz      short loc_18000F3B1
0x18000f431  mov     rcx, [rbx]
0x18000f434  lea     rdx, [rsp+78h+var_30]
0x18000f439  mov     r8, rsi
0x18000f43c  mov     rax, [rcx]
0x18000f43f  mov     rax, [rax+18h]
0x18000f443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f448  test    eax, eax
0x18000f44a  jns     short loc_18000F45B
0x18000f44c  xor     edx, edx
0x18000f44e  mov     r9d, 0BCh
0x18000f454  mov     ecx, eax
0x18000f456  call    Log_HREvent_2
0x18000f45b  add     rbx, 8
0x18000f45f  jmp     short loc_18000F42A
```
