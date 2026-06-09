# PhoneController::_OnLineLockInfoChanged(LineLockInfoMessage const *)

- ea: `0x180043270`
- end: `0x180043398`
- name: `?_OnLineLockInfoChanged@PhoneController@@IEAAJPEBVLineLockInfoMessage@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct LineLockInfoMessage *)`
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
- `0x180043270`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800432b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800432b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800432ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004332a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800432ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004332a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043349`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnLineLockInfoChanged(PhoneController *this, const struct LineLockInfoMessage *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *i; // rbx
  int v11; // eax
  __int64 v12; // r8
  __m128i si128; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-38h]

  v2 = *((_QWORD *)this + 11);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v14 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( *(_DWORD *)(v2 + 192) )
  {
    Log_AssertionEvent_0(v5, v4, 145);
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
      Log_AssertionEvent_0(v9, v8, 157);
      if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*i + 48LL))(
              *i,
              (char *)a2 + 32,
              (char *)a2 + 56);
      if ( v11 < 0 )
        Log_HREvent_2((unsigned int)v11, 0, v12, 256);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v6, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x180043270  push    rbx
0x180043272  push    rbp
0x180043273  push    rsi
0x180043274  push    rdi
0x180043275  sub     rsp, 58h
0x180043279  mov     rax, cs:__security_cookie
0x180043280  xor     rax, rsp
0x180043283  mov     [rsp+78h+var_30], rax
0x180043288  mov     rbx, [rcx+58h]
0x18004328c  mov     rsi, rdx
0x18004328f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180043297  movdqu  [rsp+78h+var_48], xmm0
0x18004329d  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x1800432a6  lea     rdi, [rbx+0C8h]
0x1800432ad  mov     rcx, rdi; lpCriticalSection
0x1800432b0  call    cs:__imp_EnterCriticalSection
0x1800432b6  cmp     dword ptr [rbx+0C0h], 0
0x1800432bd  jz      short loc_1800432D8
0x1800432bf  mov     r8d, 91h
0x1800432c5  call    Log_AssertionEvent_0
0x1800432ca  cmp     dword ptr [rbx+0C0h], 0
0x1800432d1  jz      short loc_1800432D8
0x1800432d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800432d8  lea     rdx, [rbx+60h]
0x1800432dc  lea     rcx, [rsp+78h+var_48]
0x1800432e1  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x1800432e6  test    al, al
0x1800432e8  jnz     short loc_180043327
0x1800432ea  xor     edx, edx
0x1800432ec  mov     ecx, 8007000Eh
0x1800432f1  mov     r9d, 97h
0x1800432f7  call    Log_HREvent_2
0x1800432fc  mov     rcx, rdi; lpCriticalSection
0x1800432ff  call    cs:__imp_LeaveCriticalSection
0x180043305  lea     rcx, [rsp+78h+var_48]
0x18004330a  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004330f  xor     eax, eax
0x180043311  mov     rcx, [rsp+78h+var_30]
0x180043316  xor     rcx, rsp; StackCookie
0x180043319  call    __security_check_cookie
0x18004331e  add     rsp, 58h
0x180043322  pop     rdi
0x180043323  pop     rsi
0x180043324  pop     rbp
0x180043325  pop     rbx
0x180043326  retn
0x180043327  mov     rcx, rdi; lpCriticalSection
0x18004332a  call    cs:__imp_LeaveCriticalSection
0x180043330  call    cs:__imp_GetCurrentThreadId
0x180043336  cmp     [rbx+0D8h], eax
0x18004333c  jnz     short loc_18004335C
0x18004333e  mov     r8d, 9Dh
0x180043344  call    Log_AssertionEvent_0
0x180043349  call    cs:__imp_GetCurrentThreadId
0x18004334f  cmp     [rbx+0D8h], eax
0x180043355  jnz     short loc_18004335C
0x180043357  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004335c  mov     rbx, qword ptr [rsp+78h+var_48]
0x180043361  cmp     rbx, qword ptr [rsp+78h+var_48+8]
0x180043366  jz      short loc_180043305
0x180043368  mov     rcx, [rbx]
0x18004336b  lea     r8, [rsi+38h]
0x18004336f  lea     rdx, [rsi+20h]
0x180043373  mov     rax, [rcx]
0x180043376  mov     rax, [rax+30h]
0x18004337a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004337f  test    eax, eax
0x180043381  jns     short loc_180043392
0x180043383  xor     edx, edx
0x180043385  mov     r9d, 100h
0x18004338b  mov     ecx, eax
0x18004338d  call    Log_HREvent_2
0x180043392  add     rbx, 8
0x180043396  jmp     short loc_180043361
```
