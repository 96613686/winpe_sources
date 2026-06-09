# PhoneController::_AutoUnholdCallForEnd(CallInfo const *,int)

- ea: `0x180035690`
- end: `0x1800358e7`
- name: `?_AutoUnholdCallForEnd@PhoneController@@AEAAJPEBVCallInfo@@H@Z`
- size: `599`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct CallInfo *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025b90`

## callees

- `0x180006e94`
- `0x18000e1a4`
- `0x18002c574`
- `0x18002c580`
- `0x180035690`
- `0x180035af0`
- `0x18003a048`
- `0x18005292c`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800356b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800356d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800357e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035801`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800356b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800356d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800357e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035801`

## string_xrefs

- `0x1800356bb`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_AutoUnholdCallForEnd(PhoneController *this, const struct CallInfo *a2, int a3)
{
  __int64 v6; // rcx
  unsigned int v7; // eax
  int v8; // r15d
  __int64 v9; // rcx
  int AllCalls; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // ebx
  const struct CallInfo **i; // rbx
  const struct CallInfo *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rcx
  _DWORD *v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  BackTraceCollection *v21; // rcx
  unsigned int v22; // edi
  BackTraceCollection *v23; // rcx
  _DWORD *v25; // [rsp+30h] [rbp-68h] BYREF
  __m128i si128; // [rsp+38h] [rbp-60h] BYREF
  __int64 v27; // [rsp+48h] [rbp-50h]

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5799);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *((_DWORD *)a2 + 760);
  if ( v7 > 6 )
    return 0;
  v8 = 73;
  if ( !_bittest(&v8, v7) )
    return 0;
  v9 = *((_QWORD *)this + 12);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v27 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v9, &si128, 0);
  v12 = AllCalls;
  if ( AllCalls >= 0 )
  {
    for ( i = (const struct CallInfo **)si128.m128i_i64[0]; i != (const struct CallInfo **)si128.m128i_i64[1]; ++i )
    {
      v14 = *i;
      if ( *i != a2 )
      {
        v15 = *((_DWORD *)v14 + 760);
        if ( v15 <= 6 && _bittest(&v8, v15) && (!a3 || *((_DWORD *)a2 + 768) != *((_DWORD *)v14 + 768)) )
          goto LABEL_29;
      }
      if ( *((_DWORD *)v14 + 760) == 4 && (unsigned int)PhoneController::_CanDoCompositeVerbs(this, v14, a2) )
        goto LABEL_29;
    }
    v16 = *((_QWORD *)this + 12);
    v25 = 0;
    PhoneCallStorage::FindCallByState(v16, &v25, 4, 0);
    v17 = v25;
    if ( v25 )
    {
      if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      {
        Log_AssertionEvent_3(v18, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8790);
        if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      if ( (v17[1706] & 0x10) == 0 )
      {
        v19 = v17[768];
        if ( !v19 )
          v19 = v17[767];
        LODWORD(v25) = v19;
        v20 = PhoneController::_ExecuteVerb(this, v17, &v25, 16, 0);
        v22 = v20;
        if ( v20 < 0 )
        {
          BackTraceCollection::Capture(v21, v20);
          Log_HREvent_7(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8796);
          BackTraceCollection::Capture(v23, v22);
          Log_HREvent_7(v22, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5832);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 16LL))(v17);
          v12 = v22;
          goto LABEL_30;
        }
        v17[1706] |= 0x10u;
      }
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 16LL))(v17);
    }
LABEL_29:
    v12 = 0;
  }
  else
  {
    BackTraceCollection::Capture(v11, AllCalls);
    Log_HREvent_7(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5810);
  }
LABEL_30:
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
  return v12;
}

```

## disassembly

```asm
0x180035690  push    rbx
0x180035692  push    rbp
0x180035693  push    rsi
0x180035694  push    rdi
0x180035695  push    r14
0x180035697  push    r15
0x180035699  sub     rsp, 68h
0x18003569d  mov     rax, cs:__security_cookie
0x1800356a4  xor     rax, rsp
0x1800356a7  mov     [rsp+98h+var_48], rax
0x1800356ac  mov     ebp, r8d
0x1800356af  mov     rsi, rdx
0x1800356b2  mov     rdi, rcx
0x1800356b5  call    cs:__imp_GetCurrentThreadId
0x1800356bb  lea     r14, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800356c2  cmp     [rdi+0F0h], eax
0x1800356c8  jz      short loc_1800356EB
0x1800356ca  mov     r8d, 16A7h
0x1800356d0  mov     rdx, r14
0x1800356d3  call    Log_AssertionEvent_3
0x1800356d8  call    cs:__imp_GetCurrentThreadId
0x1800356de  cmp     [rdi+0F0h], eax
0x1800356e4  jz      short loc_1800356EB
0x1800356e6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800356eb  mov     eax, [rsi+0BE0h]
0x1800356f1  cmp     eax, 6
0x1800356f4  ja      loc_1800358CB
0x1800356fa  mov     r15d, 49h ; 'I'
0x180035700  bt      r15d, eax
0x180035704  jnb     loc_1800358CB
0x18003570a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180035712  lea     rdx, [rsp+98h+var_60]
0x180035717  mov     rcx, [rdi+60h]
0x18003571b  xor     r8d, r8d
0x18003571e  movdqu  [rsp+98h+var_60], xmm0
0x180035724  mov     [rsp+98h+var_50], 0FFFFFFFFFFFFFFFFh
0x18003572d  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x180035732  mov     ebx, eax
0x180035734  test    eax, eax
0x180035736  jns     short loc_180035758
0x180035738  mov     edx, eax; int
0x18003573a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003573f  mov     r9d, 16B2h
0x180035745  lea     edx, [r15-48h]
0x180035749  mov     r8, r14
0x18003574c  mov     ecx, ebx
0x18003574e  call    Log_HREvent_7
0x180035753  jmp     loc_1800358BD
0x180035758  mov     rbx, qword ptr [rsp+98h+var_60]
0x18003575d  cmp     rbx, qword ptr [rsp+98h+var_60+8]
0x180035762  jz      short loc_1800357B9
0x180035764  mov     rdx, [rbx]; struct CallInfo *
0x180035767  cmp     rdx, rsi
0x18003576a  jz      short loc_180035797
0x18003576c  mov     eax, [rdx+0BE0h]
0x180035772  cmp     eax, 6
0x180035775  ja      short loc_180035797
0x180035777  bt      r15d, eax
0x18003577b  jnb     short loc_180035797
0x18003577d  test    ebp, ebp
0x18003577f  jz      loc_1800358BB
0x180035785  mov     eax, [rdx+0C00h]
0x18003578b  cmp     [rsi+0C00h], eax
0x180035791  jnz     loc_1800358BB
0x180035797  cmp     dword ptr [rdx+0BE0h], 4
0x18003579e  jnz     short loc_1800357B3
0x1800357a0  mov     r8, rsi; struct CallInfo *
0x1800357a3  mov     rcx, rdi; this
0x1800357a6  call    ?_CanDoCompositeVerbs@PhoneController@@IEBAHPEBVCallInfo@@0@Z; PhoneController::_CanDoCompositeVerbs(CallInfo const *,CallInfo const *)
0x1800357ab  test    eax, eax
0x1800357ad  jnz     loc_1800358BB
0x1800357b3  add     rbx, 8
0x1800357b7  jmp     short loc_18003575D
0x1800357b9  mov     rcx, [rdi+60h]
0x1800357bd  lea     rdx, [rsp+98h+var_68]
0x1800357c2  xor     r9d, r9d
0x1800357c5  mov     [rsp+98h+var_68], 0
0x1800357ce  lea     r8d, [r9+4]
0x1800357d2  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x1800357d7  mov     rbx, [rsp+98h+var_68]
0x1800357dc  test    rbx, rbx
0x1800357df  jz      loc_1800358BB
0x1800357e5  call    cs:__imp_GetCurrentThreadId
0x1800357eb  cmp     [rdi+0F0h], eax
0x1800357f1  jz      short loc_180035814
0x1800357f3  mov     r8d, 2256h
0x1800357f9  mov     rdx, r14
0x1800357fc  call    Log_AssertionEvent_3
0x180035801  call    cs:__imp_GetCurrentThreadId
0x180035807  cmp     [rdi+0F0h], eax
0x18003580d  jz      short loc_180035814
0x18003580f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180035814  test    byte ptr [rbx+1AA8h], 10h
0x18003581b  jnz     loc_1800358AC
0x180035821  mov     eax, [rbx+0C00h]
0x180035827  test    eax, eax
0x180035829  jnz     short loc_180035831
0x18003582b  mov     eax, [rbx+0BFCh]
0x180035831  mov     r9d, 10h
0x180035837  mov     dword ptr [rsp+98h+var_68], eax
0x18003583b  lea     r8, [rsp+98h+var_68]
0x180035840  mov     [rsp+98h+var_78], 0
0x180035849  mov     rdx, rbx
0x18003584c  mov     rcx, rdi
0x18003584f  call    ?_ExecuteVerb@PhoneController@@IEAAJPEAVCallInfo@@AEBIW4CallVerbs@@PEAVVerbParameters@@H@Z; PhoneController::_ExecuteVerb(CallInfo *,uint const &,CallVerbs,VerbParameters *,int)
0x180035854  mov     edi, eax
0x180035856  test    eax, eax
0x180035858  jns     short loc_1800358A5
0x18003585a  mov     edx, eax; int
0x18003585c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180035861  mov     r9d, 225Ch
0x180035867  mov     r8, r14
0x18003586a  mov     edx, 1
0x18003586f  mov     ecx, edi
0x180035871  call    Log_HREvent_7
0x180035876  mov     edx, edi; int
0x180035878  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003587d  mov     r9d, 16C8h
0x180035883  mov     r8, r14
0x180035886  mov     edx, 1
0x18003588b  mov     ecx, edi
0x18003588d  call    Log_HREvent_7
0x180035892  mov     rax, [rbx]
0x180035895  mov     rcx, rbx
0x180035898  mov     rax, [rax+10h]
0x18003589c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358a1  mov     ebx, edi
0x1800358a3  jmp     short loc_1800358BD
0x1800358a5  or      dword ptr [rbx+1AA8h], 10h
0x1800358ac  mov     rax, [rbx]
0x1800358af  mov     rcx, rbx
0x1800358b2  mov     rax, [rax+10h]
0x1800358b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bb  xor     ebx, ebx
0x1800358bd  lea     rcx, [rsp+98h+var_60]
0x1800358c2  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x1800358c7  mov     eax, ebx
0x1800358c9  jmp     short loc_1800358CD
0x1800358cb  xor     eax, eax
0x1800358cd  mov     rcx, [rsp+98h+var_48]
0x1800358d2  xor     rcx, rsp; StackCookie
0x1800358d5  call    __security_check_cookie
0x1800358da  add     rsp, 68h
0x1800358de  pop     r15
0x1800358e0  pop     r14
0x1800358e2  pop     rdi
0x1800358e3  pop     rsi
0x1800358e4  pop     rbp
0x1800358e5  pop     rbx
0x1800358e6  retn
```
