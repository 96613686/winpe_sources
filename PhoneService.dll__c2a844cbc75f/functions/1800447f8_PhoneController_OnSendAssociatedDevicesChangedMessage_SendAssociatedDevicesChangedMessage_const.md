# PhoneController::_OnSendAssociatedDevicesChangedMessage(SendAssociatedDevicesChangedMessage const &)

- ea: `0x1800447f8`
- end: `0x1800449e2`
- name: `?_OnSendAssociatedDevicesChangedMessage@PhoneController@@IEAAJAEBVSendAssociatedDevicesChangedMessage@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct SendAssociatedDevicesChangedMessage *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f9f4`
- `0x18002c574`
- `0x1800447f8`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004486f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004486f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800449b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800449b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004481e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004483f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004493e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004481e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004483f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004493e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044958`

## string_xrefs

- `0x180044833`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnSendAssociatedDevicesChangedMessage(
        PhoneController *this,
        const struct SendAssociatedDevicesChangedMessage *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 *v10; // r15
  __int64 v11; // r13
  __int64 v12; // rbp
  unsigned __int64 v13; // rbp
  __int64 v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rbp
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // r8
  __int64 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+38h] [rbp-60h]
  __int64 v24; // [rsp+40h] [rbp-58h]

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2848);
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)this + 11);
  v6 = -1;
  v22 = -1;
  v24 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  if ( *(_DWORD *)(v5 + 192) )
  {
    Log_AssertionEvent_0(v8, v7, 145);
    if ( *(_DWORD *)(v5 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v10 = *(__int64 **)(v5 + 48);
  v11 = -1;
  v12 = *(_QWORD *)(v5 + 56) - (_QWORD)v10;
  v23 = -1;
  v13 = v12 >> 3;
  if ( v13 )
  {
    if ( v13 >= 0x1000000000000000LL
      || !(unsigned __int8)utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(&v22) )
    {
      Log_HREvent_2(2147942414LL, 0, v9, 151);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
      goto LABEL_23;
    }
    v10 = *(__int64 **)(v5 + 48);
    v11 = v23;
    v6 = v22;
  }
  v14 = 0;
  if ( v13 )
  {
    do
    {
      v15 = *v10;
      *(_QWORD *)(v11 + 8 * v14) = *v10;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      ++v10;
      ++v14;
    }
    while ( v14 != v13 );
  }
  v16 = v11 + 8 * v13;
  v23 = v16;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_0(v18, v17, 157);
    if ( *(_DWORD *)(v5 + 216) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  while ( v6 != v16 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)v6 + 24LL))(*(_QWORD *)v6, (char *)a2 + 32);
    if ( v19 < 0 )
      Log_HREvent_2((unsigned int)v19, 0, v20, 177);
    v6 += 8;
  }
LABEL_23:
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v22);
  return 0;
}

```

## disassembly

```asm
0x1800447f8  push    rbx
0x1800447fa  push    rbp
0x1800447fb  push    rsi
0x1800447fc  push    rdi
0x1800447fd  push    r12
0x1800447ff  push    r13
0x180044801  push    r14
0x180044803  push    r15
0x180044805  sub     rsp, 58h
0x180044809  mov     rax, cs:__security_cookie
0x180044810  xor     rax, rsp
0x180044813  mov     [rsp+98h+var_50], rax
0x180044818  mov     rsi, rdx
0x18004481b  mov     r14, rcx
0x18004481e  call    cs:__imp_GetCurrentThreadId
0x180044824  cmp     [r14+0F0h], eax
0x18004482b  jnz     short loc_180044853
0x18004482d  mov     r8d, 0B20h
0x180044833  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004483a  call    Log_AssertionEvent_3
0x18004483f  call    cs:__imp_GetCurrentThreadId
0x180044845  cmp     [r14+0F0h], eax
0x18004484c  jnz     short loc_180044853
0x18004484e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044853  mov     r14, [r14+58h]
0x180044857  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004485b  mov     [rsp+98h+var_68], rbx
0x180044860  mov     [rsp+98h+var_58], rbx
0x180044865  lea     rdi, [r14+0C8h]
0x18004486c  mov     rcx, rdi; lpCriticalSection
0x18004486f  call    cs:__imp_EnterCriticalSection
0x180044875  cmp     dword ptr [r14+0C0h], 0
0x18004487d  jz      short loc_180044899
0x18004487f  mov     r8d, 91h
0x180044885  call    Log_AssertionEvent_0
0x18004488a  cmp     dword ptr [r14+0C0h], 0
0x180044892  jz      short loc_180044899
0x180044894  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044899  mov     r15, [r14+30h]
0x18004489d  mov     r13, rbx
0x1800448a0  mov     rbp, [r14+38h]
0x1800448a4  sub     rbp, r15
0x1800448a7  mov     [rsp+98h+var_60], rbx
0x1800448ac  sar     rbp, 3
0x1800448b0  test    rbp, rbp
0x1800448b3  jz      short loc_1800448F8
0x1800448b5  cmp     rbp, 8
0x1800448b9  jbe     short loc_1800448D3
0x1800448bb  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800448c5  cmp     rbp, rax
0x1800448c8  ja      loc_18004499D
0x1800448ce  mov     rdx, rbp
0x1800448d1  jmp     short loc_1800448D8
0x1800448d3  mov     edx, 8
0x1800448d8  lea     rcx, [rsp+98h+var_68]
0x1800448dd  call    ?_SetCapacity@?$vector@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(unsigned __int64)
0x1800448e2  test    al, al
0x1800448e4  jz      loc_18004499D
0x1800448ea  mov     r15, [r14+30h]
0x1800448ee  mov     r13, [rsp+98h+var_60]
0x1800448f3  mov     rbx, [rsp+98h+var_68]
0x1800448f8  xor     r12d, r12d
0x1800448fb  test    rbp, rbp
0x1800448fe  jz      short loc_180044925
0x180044900  mov     rcx, [r15]
0x180044903  mov     [r13+r12*8+0], rcx
0x180044908  test    rcx, rcx
0x18004490b  jz      short loc_180044919
0x18004490d  mov     rax, [rcx]
0x180044910  mov     rax, [rax+8]
0x180044914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044919  add     r15, 8
0x18004491d  inc     r12
0x180044920  cmp     r12, rbp
0x180044923  jnz     short loc_180044900
0x180044925  lea     rbp, ds:0[rbp*8]
0x18004492d  mov     rcx, rdi; lpCriticalSection
0x180044930  add     rbp, r13
0x180044933  mov     [rsp+98h+var_60], rbp
0x180044938  call    cs:__imp_LeaveCriticalSection
0x18004493e  call    cs:__imp_GetCurrentThreadId
0x180044944  cmp     [r14+0D8h], eax
0x18004494b  jnz     short loc_18004496C
0x18004494d  mov     r8d, 9Dh
0x180044953  call    Log_AssertionEvent_0
0x180044958  call    cs:__imp_GetCurrentThreadId
0x18004495e  cmp     [r14+0D8h], eax
0x180044965  jnz     short loc_18004496C
0x180044967  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004496c  cmp     rbx, rbp
0x18004496f  jz      short loc_1800449B8
0x180044971  mov     rcx, [rbx]
0x180044974  lea     rdx, [rsi+20h]
0x180044978  mov     rax, [rcx]
0x18004497b  mov     rax, [rax+18h]
0x18004497f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044984  test    eax, eax
0x180044986  jns     short loc_180044997
0x180044988  xor     edx, edx
0x18004498a  mov     r9d, 0B1h
0x180044990  mov     ecx, eax
0x180044992  call    Log_HREvent_2
0x180044997  add     rbx, 8
0x18004499b  jmp     short loc_18004496C
0x18004499d  xor     edx, edx
0x18004499f  mov     ecx, 8007000Eh
0x1800449a4  mov     r9d, 97h
0x1800449aa  call    Log_HREvent_2
0x1800449af  mov     rcx, rdi; lpCriticalSection
0x1800449b2  call    cs:__imp_LeaveCriticalSection
0x1800449b8  lea     rcx, [rsp+98h+var_68]
0x1800449bd  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800449c2  xor     eax, eax
0x1800449c4  mov     rcx, [rsp+98h+var_50]
0x1800449c9  xor     rcx, rsp; StackCookie
0x1800449cc  call    __security_check_cookie
0x1800449d1  add     rsp, 58h
0x1800449d5  pop     r15
0x1800449d7  pop     r14
0x1800449d9  pop     r13
0x1800449db  pop     r12
0x1800449dd  pop     rdi
0x1800449de  pop     rsi
0x1800449df  pop     rbp
0x1800449e0  pop     rbx
0x1800449e1  retn
```
