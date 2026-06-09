# InternalSinkMessageDispatcher::OnReleaseLine(LineNotificationData const &,LineRemovalReason)

- ea: `0x18000f468`
- end: `0x18000f602`
- name: `?OnReleaseLine@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@W4LineRemovalReason@@@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180044484`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f468`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f53a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f592`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f53a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f5b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f5b1`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnReleaseLine(__int64 a1, __int128 *a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int128 v6; // xmm6
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *i; // rbx
  int v13; // eax
  __int64 v14; // r8
  __int128 v15; // [rsp+30h] [rbp-19h] BYREF
  __int64 v16; // [rsp+40h] [rbp-9h]
  unsigned int v17; // [rsp+48h] [rbp-1h]
  __m128i si128; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+60h] [rbp+17h]

  v3 = *((_QWORD *)a2 + 2);
  v6 = *a2;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v16 = v3;
  v15 = v6;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v17 = a3;
  v19 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  if ( *(_DWORD *)(a1 + 192) )
  {
    Log_AssertionEvent_0(v8, v7, 145);
    if ( *(_DWORD *)(a1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          a1 + 72) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
    if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v11, v10, 157);
      if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(*(_QWORD *)*i + 32LL))(*i, &v15, v17);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 199);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v9, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x18000f468  push    rbp
0x18000f46a  push    rbx
0x18000f46b  push    rsi
0x18000f46c  push    rdi
0x18000f46d  lea     rbp, [rsp-3Fh]
0x18000f472  sub     rsp, 88h
0x18000f479  movaps  [rsp+0A0h+var_30], xmm6
0x18000f47e  mov     rax, cs:__security_cookie
0x18000f485  xor     rax, rsp
0x18000f488  mov     [rbp+57h+var_38], rax
0x18000f48c  mov     rdi, [rdx+10h]
0x18000f490  mov     esi, r8d
0x18000f493  mov     rbx, rcx
0x18000f496  movups  xmm6, xmmword ptr [rdx]
0x18000f499  test    rdi, rdi
0x18000f49c  jz      short loc_18000F4AD
0x18000f49e  mov     rax, [rdi]
0x18000f4a1  mov     rcx, rdi
0x18000f4a4  mov     rax, [rax+8]
0x18000f4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ad  mov     [rbp+57h+var_60], rdi
0x18000f4b1  movdqu  [rbp+57h+var_70], xmm6
0x18000f4b6  test    rdi, rdi
0x18000f4b9  jz      short loc_18000F4CA
0x18000f4bb  mov     rax, [rdi]
0x18000f4be  mov     rcx, rdi
0x18000f4c1  mov     rax, [rax+8]
0x18000f4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ca  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000f4d2  mov     [rbp+57h+var_58], esi
0x18000f4d5  lea     rsi, [rbx+0C8h]
0x18000f4dc  mov     rcx, rsi; lpCriticalSection
0x18000f4df  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000f4e7  movdqu  [rbp+57h+var_50], xmm0
0x18000f4ec  call    cs:__imp_EnterCriticalSection
0x18000f4f2  cmp     dword ptr [rbx+0C0h], 0
0x18000f4f9  jz      short loc_18000F514
0x18000f4fb  mov     r8d, 91h
0x18000f501  call    Log_AssertionEvent_0
0x18000f506  cmp     dword ptr [rbx+0C0h], 0
0x18000f50d  jz      short loc_18000F514
0x18000f50f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f514  lea     rdx, [rbx+48h]
0x18000f518  lea     rcx, [rbp+57h+var_50]
0x18000f51c  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000f521  test    al, al
0x18000f523  jnz     short loc_18000F58F
0x18000f525  xor     edx, edx
0x18000f527  mov     r9d, 97h
0x18000f52d  mov     ecx, 8007000Eh
0x18000f532  call    Log_HREvent_2
0x18000f537  mov     rcx, rsi; lpCriticalSection
0x18000f53a  call    cs:__imp_LeaveCriticalSection
0x18000f540  lea     rcx, [rbp+57h+var_50]
0x18000f544  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000f549  mov     rcx, [rbp+57h+var_60]
0x18000f54d  test    rcx, rcx
0x18000f550  jz      short loc_18000F55E
0x18000f552  mov     rax, [rcx]
0x18000f555  mov     rax, [rax+10h]
0x18000f559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f55e  test    rdi, rdi
0x18000f561  jz      short loc_18000F572
0x18000f563  mov     rax, [rdi]
0x18000f566  mov     rcx, rdi
0x18000f569  mov     rax, [rax+10h]
0x18000f56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f572  mov     rcx, [rbp+57h+var_38]
0x18000f576  xor     rcx, rsp; StackCookie
0x18000f579  call    __security_check_cookie
0x18000f57e  movaps  xmm6, [rsp+0A0h+var_30]
0x18000f583  add     rsp, 88h
0x18000f58a  pop     rdi
0x18000f58b  pop     rsi
0x18000f58c  pop     rbx
0x18000f58d  pop     rbp
0x18000f58e  retn
0x18000f58f  mov     rcx, rsi; lpCriticalSection
0x18000f592  call    cs:__imp_LeaveCriticalSection
0x18000f598  call    cs:__imp_GetCurrentThreadId
0x18000f59e  cmp     [rbx+0D8h], eax
0x18000f5a4  jnz     short loc_18000F5C4
0x18000f5a6  mov     r8d, 9Dh
0x18000f5ac  call    Log_AssertionEvent_0
0x18000f5b1  call    cs:__imp_GetCurrentThreadId
0x18000f5b7  cmp     [rbx+0D8h], eax
0x18000f5bd  jnz     short loc_18000F5C4
0x18000f5bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f5c4  mov     rbx, qword ptr [rbp+57h+var_50]
0x18000f5c8  cmp     rbx, qword ptr [rbp+57h+var_50+8]
0x18000f5cc  jz      loc_18000F540
0x18000f5d2  mov     rcx, [rbx]
0x18000f5d5  lea     rdx, [rbp+57h+var_70]
0x18000f5d9  mov     r8d, [rbp+57h+var_58]
0x18000f5dd  mov     rax, [rcx]
0x18000f5e0  mov     rax, [rax+20h]
0x18000f5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e9  test    eax, eax
0x18000f5eb  jns     short loc_18000F5FC
0x18000f5ed  xor     edx, edx
0x18000f5ef  mov     r9d, 0C7h
0x18000f5f5  mov     ecx, eax
0x18000f5f7  call    Log_HREvent_2
0x18000f5fc  add     rbx, 8
0x18000f600  jmp     short loc_18000F5C8
```
