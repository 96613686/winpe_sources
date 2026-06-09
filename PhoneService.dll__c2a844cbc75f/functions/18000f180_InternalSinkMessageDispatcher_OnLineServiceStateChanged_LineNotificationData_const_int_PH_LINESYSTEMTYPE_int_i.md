# InternalSinkMessageDispatcher::OnLineServiceStateChanged(LineNotificationData const &,int,PH_LINESYSTEMTYPE,int,int,PhoneLineSetting,PhoneLineCapabilities)

- ea: `0x18000f180`
- end: `0x18000f2ee`
- name: `?OnLineServiceStateChanged@InternalSinkMessageDispatcher@@QEAAXAEBULineNotificationData@@HW4PH_LINESYSTEMTYPE@@HHW4PhoneLineSetting@@W4PhoneLineCapabilities@@@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180043690`

## callees

- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f180`
- `0x18000fb70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f21c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f24d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f21c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f24d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f26c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f253`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f26c`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::OnLineServiceStateChanged(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *i; // rbx
  int v19; // eax
  __int64 v20; // r8
  __m128i si128; // [rsp+50h] [rbp-68h] BYREF
  __int64 v22; // [rsp+60h] [rbp-58h]

  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 200);
  v22 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  if ( *(_DWORD *)(a1 + 192) )
  {
    Log_AssertionEvent_0(v14, v13, 145);
    if ( *(_DWORD *)(a1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned __int8)utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(
                          &si128,
                          a1 + 96) )
  {
    LeaveCriticalSection(v8);
    if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
    {
      Log_AssertionEvent_0(v17, v16, 157);
      if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    for ( i = (_QWORD *)si128.m128i_i64[0]; i != (_QWORD *)si128.m128i_i64[1]; ++i )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, int, int, int))(*(_QWORD *)*i + 32LL))(
              *i,
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8);
      if ( v19 < 0 )
        Log_HREvent_2((unsigned int)v19, 0, v20, 227);
    }
  }
  else
  {
    Log_HREvent_2(2147942414LL, 0, v15, 151);
    LeaveCriticalSection(v8);
  }
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
}

```

## disassembly

```asm
0x18000f180  push    rbx
0x18000f182  push    rbp
0x18000f183  push    rsi
0x18000f184  push    rdi
0x18000f185  push    r12
0x18000f187  push    r13
0x18000f189  push    r14
0x18000f18b  push    r15
0x18000f18d  sub     rsp, 78h
0x18000f191  mov     rax, cs:__security_cookie
0x18000f198  xor     rax, rsp
0x18000f19b  mov     [rsp+0B8h+var_50], rax
0x18000f1a0  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000f1a8  lea     rdi, [rcx+0C8h]
0x18000f1af  mov     rbx, rcx
0x18000f1b2  mov     [rsp+0B8h+var_58], 0FFFFFFFFFFFFFFFFh
0x18000f1bb  mov     rcx, rdi; lpCriticalSection
0x18000f1be  mov     r15d, r9d
0x18000f1c1  mov     r12d, r8d
0x18000f1c4  mov     r13, rdx
0x18000f1c7  movdqu  [rsp+0B8h+var_68], xmm0
0x18000f1cd  call    cs:__imp_EnterCriticalSection
0x18000f1d3  cmp     dword ptr [rbx+0C0h], 0
0x18000f1da  jz      short loc_18000F1F5
0x18000f1dc  mov     r8d, 91h
0x18000f1e2  call    Log_AssertionEvent_0
0x18000f1e7  cmp     dword ptr [rbx+0C0h], 0
0x18000f1ee  jz      short loc_18000F1F5
0x18000f1f0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f1f5  lea     rdx, [rbx+60h]
0x18000f1f9  lea     rcx, [rsp+0B8h+var_68]
0x18000f1fe  call    ?assign@?$vector@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UILinePropertiesChangeSink@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>>::assign(utl::vector<ATL::CComPtr<ILinePropertiesChangeSink>,utl::allocator<ATL::CComPtr<ILinePropertiesChangeSink>>> const &)
0x18000f203  test    al, al
0x18000f205  jnz     short loc_18000F24A
0x18000f207  xor     edx, edx
0x18000f209  mov     ecx, 8007000Eh
0x18000f20e  mov     r9d, 97h
0x18000f214  call    Log_HREvent_2
0x18000f219  mov     rcx, rdi; lpCriticalSection
0x18000f21c  call    cs:__imp_LeaveCriticalSection
0x18000f222  lea     rcx, [rsp+0B8h+var_68]
0x18000f227  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000f22c  mov     rcx, [rsp+0B8h+var_50]
0x18000f231  xor     rcx, rsp; StackCookie
0x18000f234  call    __security_check_cookie
0x18000f239  add     rsp, 78h
0x18000f23d  pop     r15
0x18000f23f  pop     r14
0x18000f241  pop     r13
0x18000f243  pop     r12
0x18000f245  pop     rdi
0x18000f246  pop     rsi
0x18000f247  pop     rbp
0x18000f248  pop     rbx
0x18000f249  retn
0x18000f24a  mov     rcx, rdi; lpCriticalSection
0x18000f24d  call    cs:__imp_LeaveCriticalSection
0x18000f253  call    cs:__imp_GetCurrentThreadId
0x18000f259  cmp     [rbx+0D8h], eax
0x18000f25f  jnz     short loc_18000F27F
0x18000f261  mov     r8d, 9Dh
0x18000f267  call    Log_AssertionEvent_0
0x18000f26c  call    cs:__imp_GetCurrentThreadId
0x18000f272  cmp     [rbx+0D8h], eax
0x18000f278  jnz     short loc_18000F27F
0x18000f27a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f27f  mov     rbx, qword ptr [rsp+0B8h+var_68]
0x18000f284  mov     edi, [rsp+0B8h+arg_38]
0x18000f28b  mov     esi, [rsp+0B8h+arg_30]
0x18000f292  mov     ebp, [rsp+0B8h+arg_28]
0x18000f299  mov     r14d, [rsp+0B8h+arg_20]
0x18000f2a1  cmp     rbx, qword ptr [rsp+0B8h+var_68+8]
0x18000f2a6  jz      loc_18000F222
0x18000f2ac  mov     rcx, [rbx]
0x18000f2af  mov     r9d, r15d
0x18000f2b2  mov     [rsp+0B8h+var_80], edi
0x18000f2b6  mov     r8d, r12d
0x18000f2b9  mov     [rsp+0B8h+var_88], esi
0x18000f2bd  mov     rdx, r13
0x18000f2c0  mov     [rsp+0B8h+var_90], ebp
0x18000f2c4  mov     rax, [rcx]
0x18000f2c7  mov     [rsp+0B8h+var_98], r14d
0x18000f2cc  mov     rax, [rax+20h]
0x18000f2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2d5  test    eax, eax
0x18000f2d7  jns     short loc_18000F2E8
0x18000f2d9  xor     edx, edx
0x18000f2db  mov     r9d, 0E3h
0x18000f2e1  mov     ecx, eax
0x18000f2e3  call    Log_HREvent_2
0x18000f2e8  add     rbx, 8
0x18000f2ec  jmp     short loc_18000F2A1
```
