# PhoneController::_OnSendLineSettingModifiedMessage(SendLineSettingModifiedMessage *)

- ea: `0x180044b6c`
- end: `0x180044cb5`
- name: `?_OnSendLineSettingModifiedMessage@PhoneController@@IEAAJPEAVSendLineSettingModifiedMessage@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct SendLineSettingModifiedMessage *)`
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
- `0x180044b6c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044bbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044c45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c64`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnSendLineSettingModifiedMessage(
        PhoneController *this,
        struct SendLineSettingModifiedMessage *a2)
{
  __int64 v2; // rbx
  unsigned int v4; // ebp
  unsigned int v5; // r14d
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *i; // rbx
  int v13; // eax
  __int64 v14; // r8
  __m128i si128; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-28h]

  v2 = *((_QWORD *)this + 11);
  v4 = *((_DWORD *)a2 + 14);
  v5 = *((_DWORD *)a2 + 15);
  v16 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( *(_DWORD *)(v2 + 192) )
  {
    Log_AssertionEvent_0(v7, v6, 145);
    if ( *(_DWORD *)(v2 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v2 + 168) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v11, v10, 157);
      if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(*(_QWORD *)*i + 32LL))(
              *i,
              (char *)a2 + 32,
              v5,
              v4);
      if ( v13 < 0 )
        Log_HREvent_2((unsigned int)v13, 0, v14, 389);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v8, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x180044b6c  mov     [rsp+arg_8], rbx
0x180044b71  mov     [rsp+arg_10], rbp
0x180044b76  push    rsi
0x180044b77  push    rdi
0x180044b78  push    r14
0x180044b7a  sub     rsp, 60h
0x180044b7e  mov     rax, cs:__security_cookie
0x180044b85  xor     rax, rsp
0x180044b88  mov     [rsp+78h+var_20], rax
0x180044b8d  mov     rbx, [rcx+58h]
0x180044b91  mov     rsi, rdx
0x180044b94  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180044b9c  mov     ebp, [rdx+38h]
0x180044b9f  mov     r14d, [rdx+3Ch]
0x180044ba3  lea     rdi, [rbx+0C8h]
0x180044baa  mov     [rsp+78h+var_28], 0FFFFFFFFFFFFFFFFh
0x180044bb3  mov     rcx, rdi; lpCriticalSection
0x180044bb6  movdqu  [rsp+78h+var_38], xmm0
0x180044bbc  call    cs:__imp_EnterCriticalSection
0x180044bc2  cmp     dword ptr [rbx+0C0h], 0
0x180044bc9  jz      short loc_180044BE4
0x180044bcb  mov     r8d, 91h
0x180044bd1  call    Log_AssertionEvent_0
0x180044bd6  cmp     dword ptr [rbx+0C0h], 0
0x180044bdd  jz      short loc_180044BE4
0x180044bdf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044be4  lea     rdx, [rbx+0A8h]
0x180044beb  lea     rcx, [rsp+78h+var_38]
0x180044bf0  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180044bf5  test    al, al
0x180044bf7  jnz     short loc_180044C42
0x180044bf9  xor     edx, edx
0x180044bfb  mov     ecx, 8007000Eh
0x180044c00  mov     r9d, 97h
0x180044c06  call    Log_HREvent_2
0x180044c0b  mov     rcx, rdi; lpCriticalSection
0x180044c0e  call    cs:__imp_LeaveCriticalSection
0x180044c14  lea     rcx, [rsp+78h+var_38]
0x180044c19  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180044c1e  xor     eax, eax
0x180044c20  mov     rcx, [rsp+78h+var_20]
0x180044c25  xor     rcx, rsp; StackCookie
0x180044c28  call    __security_check_cookie
0x180044c2d  lea     r11, [rsp+78h+var_18]
0x180044c32  mov     rbx, [r11+28h]
0x180044c36  mov     rbp, [r11+30h]
0x180044c3a  mov     rsp, r11
0x180044c3d  pop     r14
0x180044c3f  pop     rdi
0x180044c40  pop     rsi
0x180044c41  retn
0x180044c42  mov     rcx, rdi; lpCriticalSection
0x180044c45  call    cs:__imp_LeaveCriticalSection
0x180044c4b  call    cs:__imp_GetCurrentThreadId
0x180044c51  cmp     [rbx+0D8h], eax
0x180044c57  jnz     short loc_180044C77
0x180044c59  mov     r8d, 9Dh
0x180044c5f  call    Log_AssertionEvent_0
0x180044c64  call    cs:__imp_GetCurrentThreadId
0x180044c6a  cmp     [rbx+0D8h], eax
0x180044c70  jnz     short loc_180044C77
0x180044c72  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180044c77  mov     rbx, qword ptr [rsp+78h+var_38]
0x180044c7c  cmp     rbx, qword ptr [rsp+78h+var_38+8]
0x180044c81  jz      short loc_180044C14
0x180044c83  mov     rcx, [rbx]
0x180044c86  lea     rdx, [rsi+20h]
0x180044c8a  mov     r9d, ebp
0x180044c8d  mov     r8d, r14d
0x180044c90  mov     rax, [rcx]
0x180044c93  mov     rax, [rax+20h]
0x180044c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c9c  test    eax, eax
0x180044c9e  jns     short loc_180044CAF
0x180044ca0  xor     edx, edx
0x180044ca2  mov     r9d, 185h
0x180044ca8  mov     ecx, eax
0x180044caa  call    Log_HREvent_2
0x180044caf  add     rbx, 8
0x180044cb3  jmp     short loc_180044C7C
```
