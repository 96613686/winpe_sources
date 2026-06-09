# PhoneController::_CheckInCallCommand(PhoneLine *,ushort const *,PhoneLine * *)

- ea: `0x180036564`
- end: `0x1800368c8`
- name: `?_CheckInCallCommand@PhoneController@@AEAAJPEAVPhoneLine@@PEBGPEAPEAV2@@Z`
- size: `868`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct PhoneLine *, const unsigned __int16 *, struct PhoneLine **)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037804`

## callees

- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180036564`
- `0x18004ef10`
- `0x1800525f8`
- `0x18005292c`
- `0x180053254`
- `0x180070fcc`
- `0x180071ba8`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036765`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365b3`

## string_xrefs

- `0x1800365a7`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036727`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800366e5`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_CheckInCallCommand(
        PhoneController *this,
        struct PhoneLine *a2,
        const unsigned __int16 *a3,
        struct PhoneLine **a4)
{
  int v6; // esi
  __int64 v8; // rcx
  __int64 v9; // rcx
  CallInfo *v10; // rbx
  CallInfo **v11; // rax
  CallInfo *v12; // rdi
  CallInfo **v13; // rax
  CallInfo *v14; // rdi
  CallInfo *v15; // rsi
  struct _RTL_CRITICAL_SECTION *v16; // r15
  const struct _GUID *v17; // rdx
  struct PhoneLine *v18; // r8
  int DialParser; // eax
  BackTraceCollection *v20; // rcx
  unsigned int v21; // edi
  CallInfo *v22; // rcx
  CallInfo *v24; // rdi
  int v25; // r15d
  __int64 v26; // rcx
  CallInfo *v27; // rcx
  CallInfo **v28; // rax
  CallInfo *v29; // rdi
  CallInfo *v30; // rax
  struct PhoneLine *v31; // rdx
  CallInfo *v32; // [rsp+30h] [rbp-28h] BYREF
  CallInfo *v33; // [rsp+38h] [rbp-20h] BYREF

  v6 = (int)a2;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5320);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a4 = 0;
  v9 = *((_QWORD *)this + 12);
  v32 = 0;
  PhoneCallStorage::FindCall(v9, (unsigned int)&v32, v6, 1, 0);
  v10 = v32;
  if ( !v32 )
  {
    v11 = (CallInfo **)PhoneCallStorage::FindCall(*((_QWORD *)this + 12), (unsigned int)&v32, v6, 3, 0);
    v12 = *v11;
    if ( *v11 )
    {
      (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v12 + 8LL))(*v11);
      v10 = v12;
    }
    if ( v32 )
      (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v32 + 16LL))(v32);
    if ( !v10 )
    {
      v13 = (CallInfo **)PhoneCallStorage::FindCall(*((_QWORD *)this + 12), (unsigned int)&v32, v6, 4, 0);
      v14 = *v13;
      if ( *v13 )
      {
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v14 + 8LL))(*v13);
        v10 = v14;
      }
      if ( v32 )
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v32 + 16LL))(v32);
      if ( !v10 )
        return 0;
    }
  }
  v32 = 0;
  CallInfo::GetPhoneLine(v10, &v32);
  v15 = v32;
  v33 = 0;
  v16 = (struct _RTL_CRITICAL_SECTION *)((char *)v32 + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v32 + 136));
  DialParser = PhoneLine::LockedData::GetDialParser((CallInfo *)((char *)v15 + 176), v17, v18, &v33);
  v21 = DialParser;
  if ( DialParser >= 0 )
  {
    LeaveCriticalSection(v16);
    v24 = v33;
    v25 = (*(__int64 (__fastcall **)(CallInfo *, const unsigned __int16 *))(*(_QWORD *)v33 + 48LL))(v33, a3);
    if ( v24 )
      (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
    {
      v26 = *((_QWORD *)this + 12);
      v33 = 0;
      PhoneCallStorage::GetActiveCall(v26, &v33);
      v27 = v33;
      if ( !v33 )
      {
        v28 = (CallInfo **)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &v32, 2, 0);
        v27 = v33;
        v29 = *v28;
        if ( v33 != *v28 )
        {
          if ( v29 )
          {
            (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v29 + 8LL))(*v28);
            v27 = v33;
          }
          if ( v27 )
            (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v27 + 16LL))(v27);
          v27 = v29;
          v33 = v29;
        }
        if ( v32 )
        {
          (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v32 + 16LL))(v32);
          v27 = v33;
        }
      }
      v30 = 0;
      v32 = 0;
      if ( !v27 || (CallInfo::GetPhoneLine(v27, &v32), v27 = v33, v30 = v32, !v33) || v32 == v15 )
      {
        v31 = v15;
        v15 = 0;
        *a4 = v31;
      }
      if ( v30 )
      {
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v30 + 16LL))(v30);
        v27 = v33;
      }
      if ( v27 )
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    if ( v15 )
      (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v15 + 16LL))(v15);
    (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v10 + 16LL))(v10);
    return 0;
  }
  BackTraceCollection::Capture(v20, DialParser);
  Log_HREvent_19(v21, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1078);
  LeaveCriticalSection(v16);
  v22 = v33;
  if ( v33 )
    (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v33 + 16LL))(v33);
  BackTraceCollection::Capture(v22, v21);
  Log_HREvent_7(v21, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5350);
  if ( v15 )
    (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v15 + 16LL))(v15);
  (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v10 + 16LL))(v10);
  return v21;
}

```

## disassembly

```asm
0x180036564  push    rbp
0x180036566  push    rbx
0x180036567  push    rsi
0x180036568  push    rdi
0x180036569  push    r12
0x18003656b  push    r13
0x18003656d  push    r14
0x18003656f  push    r15
0x180036571  mov     rbp, rsp
0x180036574  sub     rsp, 58h
0x180036578  mov     rax, cs:__security_cookie
0x18003657f  xor     rax, rsp
0x180036582  mov     [rbp+var_18], rax
0x180036586  mov     r12, r9
0x180036589  mov     r13, r8
0x18003658c  mov     rsi, rdx
0x18003658f  mov     r14, rcx
0x180036592  call    cs:__imp_GetCurrentThreadId
0x180036598  cmp     [r14+0F0h], eax
0x18003659f  jz      short loc_1800365C7
0x1800365a1  mov     r8d, 14C8h
0x1800365a7  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800365ae  call    Log_AssertionEvent_3
0x1800365b3  call    cs:__imp_GetCurrentThreadId
0x1800365b9  cmp     [r14+0F0h], eax
0x1800365c0  jz      short loc_1800365C7
0x1800365c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800365c7  xor     r15d, r15d
0x1800365ca  lea     rdx, [rbp+var_28]
0x1800365ce  mov     [r12], r15
0x1800365d2  mov     r8, rsi
0x1800365d5  mov     rcx, [r14+60h]
0x1800365d9  mov     [rbp+var_28], r15
0x1800365dd  lea     r9d, [r15+1]
0x1800365e1  mov     [rsp+58h+var_38], r15
0x1800365e6  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEBVPhoneLine@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(PhoneLine const *,PH_CALLSTATE,ISecurityToken *)
0x1800365eb  mov     rbx, [rbp+var_28]
0x1800365ef  test    rbx, rbx
0x1800365f2  jnz     loc_180036696
0x1800365f8  mov     rcx, [r14+60h]
0x1800365fc  lea     r9d, [r15+3]
0x180036600  mov     r8, rsi
0x180036603  mov     [rsp+58h+var_38], r15
0x180036608  lea     rdx, [rbp+var_28]
0x18003660c  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEBVPhoneLine@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(PhoneLine const *,PH_CALLSTATE,ISecurityToken *)
0x180036611  mov     rdi, [rax]
0x180036614  test    rdi, rdi
0x180036617  jz      short loc_18003662B
0x180036619  mov     rax, [rdi]
0x18003661c  mov     rcx, rdi
0x18003661f  mov     rax, [rax+8]
0x180036623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036628  mov     rbx, rdi
0x18003662b  mov     rcx, [rbp+var_28]
0x18003662f  test    rcx, rcx
0x180036632  jz      short loc_180036640
0x180036634  mov     rax, [rcx]
0x180036637  mov     rax, [rax+10h]
0x18003663b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036640  test    rbx, rbx
0x180036643  jnz     short loc_180036696
0x180036645  mov     rcx, [r14+60h]
0x180036649  lea     r9d, [rbx+4]
0x18003664d  mov     r8, rsi
0x180036650  mov     [rsp+58h+var_38], r15
0x180036655  lea     rdx, [rbp+var_28]
0x180036659  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@PEBVPhoneLine@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(PhoneLine const *,PH_CALLSTATE,ISecurityToken *)
0x18003665e  mov     rdi, [rax]
0x180036661  test    rdi, rdi
0x180036664  jz      short loc_180036678
0x180036666  mov     rax, [rdi]
0x180036669  mov     rcx, rdi
0x18003666c  mov     rax, [rax+8]
0x180036670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036675  mov     rbx, rdi
0x180036678  mov     rcx, [rbp+var_28]
0x18003667c  test    rcx, rcx
0x18003667f  jz      short loc_18003668D
0x180036681  mov     rax, [rcx]
0x180036684  mov     rax, [rax+10h]
0x180036688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003668d  test    rbx, rbx
0x180036690  jz      loc_1800368A9
0x180036696  lea     rdx, [rbp+var_28]; struct PhoneLine **
0x18003669a  mov     [rbp+var_28], r15
0x18003669e  mov     rcx, rbx; this
0x1800366a1  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x1800366a6  mov     rsi, [rbp+var_28]
0x1800366aa  mov     [rbp+var_20], r15
0x1800366ae  lea     r15, [rsi+88h]
0x1800366b5  mov     rcx, r15; lpCriticalSection
0x1800366b8  call    cs:__imp_EnterCriticalSection
0x1800366be  lea     rcx, [rsi+0B0h]; this
0x1800366c5  lea     r9, [rbp+var_20]; struct IDialParser **
0x1800366c9  call    ?GetDialParser@LockedData@PhoneLine@@QEAAJAEBU_GUID@@PEAV2@PEAPEAUIDialParser@@@Z; PhoneLine::LockedData::GetDialParser(_GUID const &,PhoneLine *,IDialParser * *)
0x1800366ce  mov     edi, eax
0x1800366d0  test    eax, eax
0x1800366d2  jns     loc_180036762
0x1800366d8  mov     edx, eax; int
0x1800366da  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800366df  mov     r14d, 1
0x1800366e5  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800366ec  mov     edx, r14d
0x1800366ef  mov     r9d, 436h
0x1800366f5  mov     ecx, edi
0x1800366f7  call    Log_HREvent_19
0x1800366fc  mov     rcx, r15; lpCriticalSection
0x1800366ff  call    cs:__imp_LeaveCriticalSection
0x180036705  mov     rcx, [rbp+var_20]
0x180036709  test    rcx, rcx
0x18003670c  jz      short loc_18003671A
0x18003670e  mov     rax, [rcx]
0x180036711  mov     rax, [rax+10h]
0x180036715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003671a  mov     edx, edi; int
0x18003671c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180036721  mov     r9d, 14E6h
0x180036727  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003672e  mov     edx, r14d
0x180036731  mov     ecx, edi
0x180036733  call    Log_HREvent_7
0x180036738  test    rsi, rsi
0x18003673b  jz      short loc_18003674C
0x18003673d  mov     rax, [rsi]
0x180036740  mov     rcx, rsi
0x180036743  mov     rax, [rax+10h]
0x180036747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003674c  mov     rax, [rbx]
0x18003674f  mov     rcx, rbx
0x180036752  mov     rax, [rax+10h]
0x180036756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003675b  mov     eax, edi
0x18003675d  jmp     loc_1800368AB
0x180036762  mov     rcx, r15; lpCriticalSection
0x180036765  call    cs:__imp_LeaveCriticalSection
0x18003676b  mov     rdi, [rbp+var_20]
0x18003676f  mov     rdx, r13
0x180036772  mov     rcx, rdi
0x180036775  mov     rax, [rdi]
0x180036778  mov     rax, [rax+30h]
0x18003677c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036781  mov     r15d, eax
0x180036784  test    rdi, rdi
0x180036787  jz      short loc_180036798
0x180036789  mov     rcx, [rdi]
0x18003678c  mov     rax, [rcx+10h]
0x180036790  mov     rcx, rdi
0x180036793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036798  test    r15d, r15d
0x18003679b  jz      loc_180036886
0x1800367a1  mov     rcx, [r14+60h]
0x1800367a5  lea     rdx, [rbp+var_20]
0x1800367a9  mov     [rbp+var_20], 0
0x1800367b1  call    ?GetActiveCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@XZ; PhoneCallStorage::GetActiveCall(void)
0x1800367b6  mov     rcx, [rbp+var_20]
0x1800367ba  test    rcx, rcx
0x1800367bd  jnz     short loc_18003682B
0x1800367bf  lea     r8d, [rcx+2]
0x1800367c3  xor     r9d, r9d
0x1800367c6  mov     rcx, [r14+60h]
0x1800367ca  lea     rdx, [rbp+var_28]
0x1800367ce  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x1800367d3  mov     rcx, [rbp+var_20]
0x1800367d7  mov     rdi, [rax]
0x1800367da  cmp     rcx, rdi
0x1800367dd  jz      short loc_18003680F
0x1800367df  test    rdi, rdi
0x1800367e2  jz      short loc_1800367F7
0x1800367e4  mov     rax, [rdi]
0x1800367e7  mov     rcx, rdi
0x1800367ea  mov     rax, [rax+8]
0x1800367ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367f3  mov     rcx, [rbp+var_20]
0x1800367f7  test    rcx, rcx
0x1800367fa  jz      short loc_180036808
0x1800367fc  mov     rax, [rcx]
0x1800367ff  mov     rax, [rax+10h]
0x180036803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036808  mov     rcx, rdi
0x18003680b  mov     [rbp+var_20], rcx
0x18003680f  mov     rdx, [rbp+var_28]
0x180036813  test    rdx, rdx
0x180036816  jz      short loc_18003682B
0x180036818  mov     rax, [rdx]
0x18003681b  mov     rcx, rdx
0x18003681e  mov     rax, [rax+10h]
0x180036822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036827  mov     rcx, [rbp+var_20]; this
0x18003682b  xor     eax, eax
0x18003682d  mov     [rbp+var_28], rax
0x180036831  test    rcx, rcx
0x180036834  jz      short loc_180036851
0x180036836  lea     rdx, [rbp+var_28]; struct PhoneLine **
0x18003683a  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x18003683f  mov     rcx, [rbp+var_20]
0x180036843  mov     rax, [rbp+var_28]
0x180036847  test    rcx, rcx
0x18003684a  jz      short loc_180036851
0x18003684c  cmp     rax, rsi
0x18003684f  jnz     short loc_18003685A
0x180036851  mov     rdx, rsi
0x180036854  xor     esi, esi
0x180036856  mov     [r12], rdx
0x18003685a  test    rax, rax
0x18003685d  jz      short loc_180036875
0x18003685f  mov     rcx, [rax]
0x180036862  mov     rdx, [rcx+10h]
0x180036866  mov     rcx, rax
0x180036869  mov     rax, rdx
0x18003686c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036871  mov     rcx, [rbp+var_20]
0x180036875  test    rcx, rcx
0x180036878  jz      short loc_180036886
0x18003687a  mov     rax, [rcx]
0x18003687d  mov     rax, [rax+10h]
0x180036881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036886  test    rsi, rsi
0x180036889  jz      short loc_18003689A
0x18003688b  mov     rax, [rsi]
0x18003688e  mov     rcx, rsi
0x180036891  mov     rax, [rax+10h]
0x180036895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003689a  mov     rax, [rbx]
0x18003689d  mov     rcx, rbx
0x1800368a0  mov     rax, [rax+10h]
0x1800368a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368a9  xor     eax, eax
0x1800368ab  mov     rcx, [rbp+var_18]
0x1800368af  xor     rcx, rsp; StackCookie
0x1800368b2  call    __security_check_cookie
0x1800368b7  add     rsp, 58h
0x1800368bb  pop     r15
0x1800368bd  pop     r14
0x1800368bf  pop     r13
0x1800368c1  pop     r12
0x1800368c3  pop     rdi
0x1800368c4  pop     rsi
0x1800368c5  pop     rbx
0x1800368c6  pop     rbp
0x1800368c7  retn
```
