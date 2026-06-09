# PhoneController::_SendImmediatePromptVideoCallChargesMessage(uint const &,PH_DIAL_PARAMETERS const *,ISecurityToken *)

- ea: `0x1800484dc`
- end: `0x180048656`
- name: `?_SendImmediatePromptVideoCallChargesMessage@PhoneController@@IEAAJAEBIPEBUPH_DIAL_PARAMETERS@@PEAUISecurityToken@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const unsigned int *, const struct PH_DIAL_PARAMETERS *, struct ISecurityToken *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800222c0`
- `0x180024230`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000fb70`
- `0x18002c574`
- `0x1800484dc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048561`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048561`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800485ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800485ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048606`

## string_xrefs

- `0x18004851d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendImmediatePromptVideoCallChargesMessage(
        PhoneController *this,
        const unsigned int *a2,
        const struct PH_DIAL_PARAMETERS *a3,
        struct ISecurityToken *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *i; // rbx
  int v17; // eax
  __int64 v18; // r8
  __m128i si128; // [rsp+40h] [rbp-38h] BYREF
  __int64 v20; // [rsp+50h] [rbp-28h]

  if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5082);
    if ( *((_DWORD *)this + 60) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = *((_QWORD *)this + 11);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v20 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  if ( *(_DWORD *)(v9 + 192) )
  {
    Log_AssertionEvent_0(v11, v10, 145);
    if ( *(_DWORD *)(v9 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          v9 + 120) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
    if ( *(_DWORD *)(v9 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v15, v14, 157);
      if ( *(_DWORD *)(v9 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, const unsigned int *, const struct PH_DIAL_PARAMETERS *, struct ISecurityToken *))(*(_QWORD *)*i + 56LL))(
              *i,
              a2,
              a3,
              a4);
      if ( v17 < 0 )
        Log_HREvent_2((unsigned int)v17, 0, v18, 338);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v12, 151);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return 0;
}

```

## disassembly

```asm
0x1800484dc  mov     [rsp+arg_8], rbx
0x1800484e1  mov     [rsp+arg_10], rbp
0x1800484e6  push    rsi
0x1800484e7  push    rdi
0x1800484e8  push    r14
0x1800484ea  sub     rsp, 60h
0x1800484ee  mov     rax, cs:__security_cookie
0x1800484f5  xor     rax, rsp
0x1800484f8  mov     [rsp+78h+var_20], rax
0x1800484fd  mov     rsi, r9
0x180048500  mov     rbp, r8
0x180048503  mov     r14, rdx
0x180048506  mov     rbx, rcx
0x180048509  call    cs:__imp_GetCurrentThreadId
0x18004850f  cmp     [rbx+0F0h], eax
0x180048515  jnz     short loc_18004853C
0x180048517  mov     r8d, 13DAh
0x18004851d  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180048524  call    Log_AssertionEvent_3
0x180048529  call    cs:__imp_GetCurrentThreadId
0x18004852f  cmp     [rbx+0F0h], eax
0x180048535  jnz     short loc_18004853C
0x180048537  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004853c  mov     rbx, [rbx+58h]
0x180048540  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180048548  movdqu  [rsp+78h+var_38], xmm0
0x18004854e  mov     [rsp+78h+var_28], 0FFFFFFFFFFFFFFFFh
0x180048557  lea     rdi, [rbx+0C8h]
0x18004855e  mov     rcx, rdi; lpCriticalSection
0x180048561  call    cs:__imp_EnterCriticalSection
0x180048567  cmp     dword ptr [rbx+0C0h], 0
0x18004856e  jz      short loc_180048589
0x180048570  mov     r8d, 91h
0x180048576  call    Log_AssertionEvent_0
0x18004857b  cmp     dword ptr [rbx+0C0h], 0
0x180048582  jz      short loc_180048589
0x180048584  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180048589  lea     rdx, [rbx+78h]
0x18004858d  lea     rcx, [rsp+78h+var_38]
0x180048592  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x180048597  test    al, al
0x180048599  jnz     short loc_1800485E4
0x18004859b  xor     edx, edx
0x18004859d  mov     ecx, 8007000Eh
0x1800485a2  mov     r9d, 97h
0x1800485a8  call    Log_HREvent_2
0x1800485ad  mov     rcx, rdi; lpCriticalSection
0x1800485b0  call    cs:__imp_LeaveCriticalSection
0x1800485b6  lea     rcx, [rsp+78h+var_38]
0x1800485bb  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800485c0  xor     eax, eax
0x1800485c2  mov     rcx, [rsp+78h+var_20]
0x1800485c7  xor     rcx, rsp; StackCookie
0x1800485ca  call    __security_check_cookie
0x1800485cf  lea     r11, [rsp+78h+var_18]
0x1800485d4  mov     rbx, [r11+28h]
0x1800485d8  mov     rbp, [r11+30h]
0x1800485dc  mov     rsp, r11
0x1800485df  pop     r14
0x1800485e1  pop     rdi
0x1800485e2  pop     rsi
0x1800485e3  retn
0x1800485e4  mov     rcx, rdi; lpCriticalSection
0x1800485e7  call    cs:__imp_LeaveCriticalSection
0x1800485ed  call    cs:__imp_GetCurrentThreadId
0x1800485f3  cmp     [rbx+0D8h], eax
0x1800485f9  jnz     short loc_180048619
0x1800485fb  mov     r8d, 9Dh
0x180048601  call    Log_AssertionEvent_0
0x180048606  call    cs:__imp_GetCurrentThreadId
0x18004860c  cmp     [rbx+0D8h], eax
0x180048612  jnz     short loc_180048619
0x180048614  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180048619  mov     rbx, qword ptr [rsp+78h+var_38]
0x18004861e  cmp     rbx, qword ptr [rsp+78h+var_38+8]
0x180048623  jz      short loc_1800485B6
0x180048625  mov     rcx, [rbx]
0x180048628  mov     r9, rsi
0x18004862b  mov     r8, rbp
0x18004862e  mov     rdx, r14
0x180048631  mov     rax, [rcx]
0x180048634  mov     rax, [rax+38h]
0x180048638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004863d  test    eax, eax
0x18004863f  jns     short loc_180048650
0x180048641  xor     edx, edx
0x180048643  mov     r9d, 152h
0x180048649  mov     ecx, eax
0x18004864b  call    Log_HREvent_2
0x180048650  add     rbx, 8
0x180048654  jmp     short loc_18004861E
```
