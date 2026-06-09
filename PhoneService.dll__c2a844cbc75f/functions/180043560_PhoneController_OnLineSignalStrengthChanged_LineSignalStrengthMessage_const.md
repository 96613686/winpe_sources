# PhoneController::_OnLineSignalStrengthChanged(LineSignalStrengthMessage const *)

- ea: `0x180043560`
- end: `0x18004368a`
- name: `?_OnLineSignalStrengthChanged@PhoneController@@IEAAJPEBVLineSignalStrengthMessage@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct LineSignalStrengthMessage *)`
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
- `0x180043560`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800435f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004361d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800435f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004361d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004363c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004363c`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnLineSignalStrengthChanged(
        PhoneController *this,
        const struct LineSignalStrengthMessage *a2)
{
  __int64 v2; // rbx
  unsigned int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *i; // rbx
  int v12; // eax
  __int64 v13; // r8
  __m128i si128; // [rsp+38h] [rbp-50h] BYREF
  __int64 v15; // [rsp+48h] [rbp-40h]

  v2 = *((_QWORD *)this + 11);
  v4 = *((_DWORD *)a2 + 14);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v15 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( *(_DWORD *)(v2 + 192) )
  {
    Log_AssertionEvent_0(v6, v5, 145);
    if ( *(_DWORD *)(v2 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v2 + 96) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v10, v9, 157);
      if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(*(_QWORD *)*i + 56LL))(*i, (char *)a2 + 32, v4);
      if ( v12 < 0 )
        Log_HREvent_2((unsigned int)v12, 0, v13, 267);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v7, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x180043560  push    rbx
0x180043562  push    rbp
0x180043563  push    rsi
0x180043564  push    rdi
0x180043565  sub     rsp, 68h
0x180043569  mov     rax, cs:__security_cookie
0x180043570  xor     rax, rsp
0x180043573  mov     [rsp+88h+var_38], rax
0x180043578  mov     rbx, [rcx+58h]
0x18004357c  mov     rsi, rdx
0x18004357f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180043587  mov     ebp, [rdx+38h]
0x18004358a  movdqu  [rsp+88h+var_50], xmm0
0x180043590  lea     rdi, [rbx+0C8h]
0x180043597  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800435a0  mov     rcx, rdi; lpCriticalSection
0x1800435a3  call    cs:__imp_EnterCriticalSection
0x1800435a9  cmp     dword ptr [rbx+0C0h], 0
0x1800435b0  jz      short loc_1800435CB
0x1800435b2  mov     r8d, 91h
0x1800435b8  call    Log_AssertionEvent_0
0x1800435bd  cmp     dword ptr [rbx+0C0h], 0
0x1800435c4  jz      short loc_1800435CB
0x1800435c6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800435cb  lea     rdx, [rbx+60h]
0x1800435cf  lea     rcx, [rsp+88h+var_50]
0x1800435d4  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x1800435d9  test    al, al
0x1800435db  jnz     short loc_18004361A
0x1800435dd  xor     edx, edx
0x1800435df  mov     ecx, 8007000Eh
0x1800435e4  mov     r9d, 97h
0x1800435ea  call    Log_HREvent_2
0x1800435ef  mov     rcx, rdi; lpCriticalSection
0x1800435f2  call    cs:__imp_LeaveCriticalSection
0x1800435f8  lea     rcx, [rsp+88h+var_50]
0x1800435fd  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180043602  xor     eax, eax
0x180043604  mov     rcx, [rsp+88h+var_38]
0x180043609  xor     rcx, rsp; StackCookie
0x18004360c  call    __security_check_cookie
0x180043611  add     rsp, 68h
0x180043615  pop     rdi
0x180043616  pop     rsi
0x180043617  pop     rbp
0x180043618  pop     rbx
0x180043619  retn
0x18004361a  mov     rcx, rdi; lpCriticalSection
0x18004361d  call    cs:__imp_LeaveCriticalSection
0x180043623  call    cs:__imp_GetCurrentThreadId
0x180043629  cmp     [rbx+0D8h], eax
0x18004362f  jnz     short loc_18004364F
0x180043631  mov     r8d, 9Dh
0x180043637  call    Log_AssertionEvent_0
0x18004363c  call    cs:__imp_GetCurrentThreadId
0x180043642  cmp     [rbx+0D8h], eax
0x180043648  jnz     short loc_18004364F
0x18004364a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004364f  mov     rbx, qword ptr [rsp+88h+var_50]
0x180043654  cmp     rbx, qword ptr [rsp+88h+var_50+8]
0x180043659  jz      short loc_1800435F8
0x18004365b  mov     rcx, [rbx]
0x18004365e  lea     rdx, [rsi+20h]
0x180043662  mov     r8d, ebp
0x180043665  mov     rax, [rcx]
0x180043668  mov     rax, [rax+38h]
0x18004366c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043671  test    eax, eax
0x180043673  jns     short loc_180043684
0x180043675  xor     edx, edx
0x180043677  mov     r9d, 10Bh
0x18004367d  mov     ecx, eax
0x18004367f  call    Log_HREvent_2
0x180043684  add     rbx, 8
0x180043688  jmp     short loc_180043654
```
