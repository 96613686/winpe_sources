# InternalSinkMessageDispatcher::OnControllerMessage(tagPH_MSG,LineNotificationData const &,ushort const *,ushort const *)

- ea: `0x18000edac`
- end: `0x18000eef8`
- name: `?OnControllerMessage@InternalSinkMessageDispatcher@@QEAAXW4tagPH_MSG@@AEBULineNotificationData@@PEBG2@Z`
- size: `332`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180044cbc`
- `0x1800454bc`
- `0x18004841c`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000edac`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee9c`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnControllerMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *i; // rbx
  int v16; // eax
  __int64 v17; // r8
  __m128i si128; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h]

  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 200);
  v19 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  if ( *(_DWORD *)(a1 + 192) )
  {
    Log_AssertionEvent_0(v11, v10, 145);
    if ( *(_DWORD *)(a1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          a1 + 120) )
  {
    LeaveCriticalSection(v5);
    if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v14, v13, 157);
      if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64))(*(_QWORD *)*i + 40LL))(
              *i,
              a2,
              a3,
              a4,
              a5);
      if ( v16 < 0 )
        Log_HREvent_2((unsigned int)v16, 0, v17, 316);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v12, 151);
    LeaveCriticalSection(v5);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
}

```

## disassembly

```asm
0x18000edac  mov     [rsp+arg_8], rbx
0x18000edb1  mov     [rsp+arg_10], rbp
0x18000edb6  push    rsi
0x18000edb7  push    rdi
0x18000edb8  push    r14
0x18000edba  sub     rsp, 50h
0x18000edbe  mov     rax, cs:__security_cookie
0x18000edc5  xor     rax, rsp
0x18000edc8  mov     [rsp+68h+var_20], rax
0x18000edcd  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000edd5  lea     rdi, [rcx+0C8h]
0x18000eddc  mov     rbx, rcx
0x18000eddf  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x18000ede8  mov     rcx, rdi; lpCriticalSection
0x18000edeb  mov     rsi, r9
0x18000edee  mov     r14, r8
0x18000edf1  mov     ebp, edx
0x18000edf3  movdqu  [rsp+68h+var_38], xmm0
0x18000edf9  call    cs:__imp_EnterCriticalSection
0x18000edff  cmp     dword ptr [rbx+0C0h], 0
0x18000ee06  jz      short loc_18000EE21
0x18000ee08  mov     r8d, 91h
0x18000ee0e  call    Log_AssertionEvent_0
0x18000ee13  cmp     dword ptr [rbx+0C0h], 0
0x18000ee1a  jz      short loc_18000EE21
0x18000ee1c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ee21  lea     rdx, [rbx+78h]
0x18000ee25  lea     rcx, [rsp+68h+var_38]
0x18000ee2a  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000ee2f  test    al, al
0x18000ee31  jnz     short loc_18000EE7A
0x18000ee33  xor     edx, edx
0x18000ee35  mov     ecx, 8007000Eh
0x18000ee3a  mov     r9d, 97h
0x18000ee40  call    Log_HREvent_2
0x18000ee45  mov     rcx, rdi; lpCriticalSection
0x18000ee48  call    cs:__imp_LeaveCriticalSection
0x18000ee4e  lea     rcx, [rsp+68h+var_38]
0x18000ee53  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000ee58  mov     rcx, [rsp+68h+var_20]
0x18000ee5d  xor     rcx, rsp; StackCookie
0x18000ee60  call    __security_check_cookie
0x18000ee65  lea     r11, [rsp+68h+var_18]
0x18000ee6a  mov     rbx, [r11+28h]
0x18000ee6e  mov     rbp, [r11+30h]
0x18000ee72  mov     rsp, r11
0x18000ee75  pop     r14
0x18000ee77  pop     rdi
0x18000ee78  pop     rsi
0x18000ee79  retn
0x18000ee7a  mov     rcx, rdi; lpCriticalSection
0x18000ee7d  call    cs:__imp_LeaveCriticalSection
0x18000ee83  call    cs:__imp_GetCurrentThreadId
0x18000ee89  cmp     [rbx+0D8h], eax
0x18000ee8f  jnz     short loc_18000EEAF
0x18000ee91  mov     r8d, 9Dh
0x18000ee97  call    Log_AssertionEvent_0
0x18000ee9c  call    cs:__imp_GetCurrentThreadId
0x18000eea2  cmp     [rbx+0D8h], eax
0x18000eea8  jnz     short loc_18000EEAF
0x18000eeaa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000eeaf  mov     rbx, qword ptr [rsp+68h+var_38]
0x18000eeb4  mov     rdi, [rsp+68h+arg_20]
0x18000eebc  cmp     rbx, qword ptr [rsp+68h+var_38+8]
0x18000eec1  jz      short loc_18000EE4E
0x18000eec3  mov     rcx, [rbx]
0x18000eec6  mov     r9, rsi
0x18000eec9  mov     r8, r14
0x18000eecc  mov     [rsp+68h+var_48], rdi
0x18000eed1  mov     edx, ebp
0x18000eed3  mov     rax, [rcx]
0x18000eed6  mov     rax, [rax+28h]
0x18000eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eedf  test    eax, eax
0x18000eee1  jns     short loc_18000EEF2
0x18000eee3  xor     edx, edx
0x18000eee5  mov     r9d, 13Ch
0x18000eeeb  mov     ecx, eax
0x18000eeed  call    Log_HREvent_2
0x18000eef2  add     rbx, 8
0x18000eef6  jmp     short loc_18000EEBC
```
