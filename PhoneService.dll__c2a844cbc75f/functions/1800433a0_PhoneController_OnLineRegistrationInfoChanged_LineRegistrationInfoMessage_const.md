# PhoneController::_OnLineRegistrationInfoChanged(LineRegistrationInfoMessage const *)

- ea: `0x1800433a0`
- end: `0x180043557`
- name: `?_OnLineRegistrationInfoChanged@PhoneController@@IEAAJPEBVLineRegistrationInfoMessage@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct LineRegistrationInfoMessage *)`
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
- `0x1800433a0`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043414`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043466`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800434b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043466`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800434b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434d6`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnLineRegistrationInfoChanged(
        PhoneController *this,
        const struct LineRegistrationInfoMessage *a2)
{
  __int64 v2; // rbx
  int v4; // ebp
  int v5; // r14d
  int v6; // r15d
  __int64 v7; // r12
  __int64 v8; // r13
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *i; // rbx
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // [rsp+50h] [rbp-B8h]
  __m128i si128; // [rsp+98h] [rbp-70h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-60h]

  v2 = *((_QWORD *)this + 11);
  v4 = *((_DWORD *)a2 + 40);
  v5 = *((_DWORD *)a2 + 39);
  v6 = *((_DWORD *)a2 + 38);
  v7 = *((_QWORD *)a2 + 15);
  v8 = *((_QWORD *)a2 + 11);
  v18 = *((_QWORD *)a2 + 7);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v20 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( *(_DWORD *)(v2 + 192) )
  {
    Log_AssertionEvent_0(v10, v9, 145);
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
      Log_AssertionEvent_0(v14, v13, 157);
      if ( *(_DWORD *)(v2 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, __int64, __int64, int, int, int, char *))(*(_QWORD *)*i + 40LL))(
              *i,
              (char *)a2 + 32,
              v18,
              v8,
              v7,
              v6,
              v5,
              v4,
              (char *)a2 + 164);
      if ( v16 < 0 )
        Log_HREvent_2((unsigned int)v16, 0, v17, 246);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v11, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x1800433a0  mov     r11, rsp
0x1800433a3  push    rbx
0x1800433a4  push    rbp
0x1800433a5  push    rsi
0x1800433a6  push    rdi
0x1800433a7  push    r12
0x1800433a9  push    r13
0x1800433ab  push    r14
0x1800433ad  push    r15
0x1800433af  sub     rsp, 0C8h
0x1800433b6  mov     rax, cs:__security_cookie
0x1800433bd  xor     rax, rsp
0x1800433c0  mov     [rsp+108h+var_58], rax
0x1800433c8  mov     rbx, [rcx+58h]
0x1800433cc  mov     rdi, rdx
0x1800433cf  mov     rax, [rdx+38h]
0x1800433d3  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800433db  mov     ebp, [rdx+0A0h]
0x1800433e1  mov     r14d, [rdx+9Ch]
0x1800433e8  lea     rsi, [rbx+0C8h]
0x1800433ef  mov     r15d, [rdx+98h]
0x1800433f6  mov     rcx, rsi; lpCriticalSection
0x1800433f9  mov     r12, [rdx+78h]
0x1800433fd  mov     r13, [rdx+58h]
0x180043401  mov     [rsp+108h+var_B8], rax
0x180043406  movdqu  xmmword ptr [r11-70h], xmm0
0x18004340c  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFFh
0x180043414  call    cs:__imp_EnterCriticalSection
0x18004341a  cmp     dword ptr [rbx+0C0h], 0
0x180043421  jz      short loc_18004343C
0x180043423  mov     r8d, 91h
0x180043429  call    Log_AssertionEvent_0
0x18004342e  cmp     dword ptr [rbx+0C0h], 0
0x180043435  jz      short loc_18004343C
0x180043437  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004343c  lea     rdx, [rbx+60h]
0x180043440  lea     rcx, [rsp+108h+var_70]
0x180043448  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18004344d  test    al, al
0x18004344f  jnz     short loc_18004349F
0x180043451  xor     edx, edx
0x180043453  mov     ecx, 8007000Eh
0x180043458  mov     r9d, 97h
0x18004345e  call    Log_HREvent_2
0x180043463  mov     rcx, rsi; lpCriticalSection
0x180043466  call    cs:__imp_LeaveCriticalSection
0x18004346c  lea     rcx, [rsp+108h+var_70]
0x180043474  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180043479  xor     eax, eax
0x18004347b  mov     rcx, [rsp+108h+var_58]
0x180043483  xor     rcx, rsp; StackCookie
0x180043486  call    __security_check_cookie
0x18004348b  add     rsp, 0C8h
0x180043492  pop     r15
0x180043494  pop     r14
0x180043496  pop     r13
0x180043498  pop     r12
0x18004349a  pop     rdi
0x18004349b  pop     rsi
0x18004349c  pop     rbp
0x18004349d  pop     rbx
0x18004349e  retn
0x18004349f  lea     rax, [rdi+20h]
0x1800434a3  mov     rcx, rsi; lpCriticalSection
0x1800434a6  mov     [rsp+108h+var_B0], rax
0x1800434ab  lea     rax, [rdi+0A4h]
0x1800434b2  mov     [rsp+108h+var_A8], rax
0x1800434b7  call    cs:__imp_LeaveCriticalSection
0x1800434bd  call    cs:__imp_GetCurrentThreadId
0x1800434c3  cmp     [rbx+0D8h], eax
0x1800434c9  jnz     short loc_1800434E9
0x1800434cb  mov     r8d, 9Dh
0x1800434d1  call    Log_AssertionEvent_0
0x1800434d6  call    cs:__imp_GetCurrentThreadId
0x1800434dc  cmp     [rbx+0D8h], eax
0x1800434e2  jnz     short loc_1800434E9
0x1800434e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800434e9  mov     rbx, [rsp+108h+var_70]
0x1800434f1  mov     rdi, [rsp+108h+var_B8]
0x1800434f6  mov     rsi, [rsp+108h+var_B0]
0x1800434fb  cmp     rbx, [rsp+108h+var_68]
0x180043503  jz      loc_18004346C
0x180043509  mov     rcx, [rbx]
0x18004350c  mov     r9, r13
0x18004350f  mov     rdx, [rsp+108h+var_A8]
0x180043514  mov     r8, rdi
0x180043517  mov     [rsp+108h+var_C8], rdx
0x18004351c  mov     rdx, rsi
0x18004351f  mov     [rsp+108h+var_D0], ebp
0x180043523  mov     rax, [rcx]
0x180043526  mov     [rsp+108h+var_D8], r14d
0x18004352b  mov     [rsp+108h+var_E0], r15d
0x180043530  mov     [rsp+108h+var_E8], r12
0x180043535  mov     rax, [rax+28h]
0x180043539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004353e  test    eax, eax
0x180043540  jns     short loc_180043551
0x180043542  xor     edx, edx
0x180043544  mov     r9d, 0F6h
0x18004354a  mov     ecx, eax
0x18004354c  call    Log_HREvent_2
0x180043551  add     rbx, 8
0x180043555  jmp     short loc_1800434FB
```
