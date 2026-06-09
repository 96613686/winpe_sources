# PhoneController::_PostProcessUpdateCalls(PH_PHONE_CALL_COUNTS const &)

- ea: `0x1800450c4`
- end: `0x1800454b3`
- name: `?_PostProcessUpdateCalls@PhoneController@@IEAAJAEBUPH_PHONE_CALL_COUNTS@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, const struct PH_PHONE_CALL_COUNTS *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a5b4`

## callees

- `0x180006e94`
- `0x18000e1a4`
- `0x180023e94`
- `0x18002c574`
- `0x18002c580`
- `0x1800384bc`
- `0x1800450c4`
- `0x180046134`
- `0x180047c90`
- `0x180049914`
- `0x18004ef10`
- `0x18004f30c`
- `0x18004f348`
- `0x18005292c`
- `0x18005354c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800450f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004511a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800450f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004511a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004513e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004513e`
- `PhoneUtil!Phone_FmtText_GlobalFormat` at `0x1800451ae`
- `PhoneUtil!Phone_FmtText_GlobalFormat` at `0x1800451ae`
- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18004530d`
- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18004530d`

## string_xrefs

- `0x1800450fc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180045201`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_PostProcessUpdateCalls(
        PhoneController *this,
        const struct PH_PHONE_CALL_COUNTS *a2)
{
  char v3; // di
  __int64 v5; // rcx
  _DWORD *v6; // rbx
  _QWORD *v7; // rax
  _DWORD *v8; // rsi
  char v9; // r15
  int v10; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // r8
  __int64 v14; // rcx
  int AllCalls; // eax
  BackTraceCollection *v16; // rcx
  unsigned int v17; // edi
  CallInfo **i; // rdi
  struct CallInfo *v20; // rdx
  unsigned int v21; // eax
  int v22; // ecx
  int v23; // eax
  struct PhoneLine *v24; // rsi
  int v25; // eax
  int v26; // eax
  int started; // eax
  CallInfo *v28; // rcx
  unsigned int v29; // eax
  int v30; // edx
  struct PhoneLine *v31; // rsi
  int v32; // eax
  struct PhoneLine *v33; // [rsp+30h] [rbp-38h] BYREF
  __m128i si128; // [rsp+38h] [rbp-30h] BYREF
  __int64 v35; // [rsp+48h] [rbp-20h]

  v3 = 0;
  LODWORD(v33) = 0;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v5, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3943);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v6 = 0;
  if ( *((_DWORD *)this + 81) )
  {
    if ( GetTickCount64() - *((_QWORD *)this + 41) <= 0x2710 )
    {
      v7 = (_QWORD *)PhoneCallStorage::FindCallByState(*((_QWORD *)this + 12), &v33, 1, 0);
      v8 = (_DWORD *)*v7;
      if ( *v7 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*v7);
        v9 = 1;
        v3 = 1;
        v6 = v8;
LABEL_9:
        if ( (v3 & 1) != 0 && v33 )
          (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v33 + 16LL))(v33);
        if ( v9 )
        {
          if ( this == (PhoneController *)-336LL
            || (v10 = Phone_FmtText_GlobalFormat((char *)this + 336, v6 + 222, 64), v12 = v10, v10 >= 0) )
          {
            v6[770] |= 0x200u;
          }
          else
          {
            BackTraceCollection::Capture(v11, v10);
            Log_HREvent_9(v12, 1, v13, 228);
          }
        }
        *((_WORD *)this + 168) = 0;
        *((_DWORD *)this + 81) = 0;
        goto LABEL_19;
      }
      v3 = 1;
    }
    v9 = 0;
    goto LABEL_9;
  }
LABEL_19:
  v14 = *((_QWORD *)this + 12);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v35 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v14, &si128, 0);
  v17 = AllCalls;
  if ( AllCalls >= 0 )
  {
    for ( i = (CallInfo **)si128.m128i_i64[0]; i != (CallInfo **)si128.m128i_i64[1]; ++i )
    {
      v20 = *i;
      v21 = *((_DWORD *)*i + 761);
      if ( v21 <= 0x17 )
      {
        v22 = 8389122;
        if ( _bittest(&v22, v21) )
        {
          if ( *((_DWORD *)a2 + 4) || *((_DWORD *)a2 + 3) )
          {
            v26 = PhoneController::_EndBusyCall(this, v20);
            if ( v26 < 0 )
              Log_HREvent_7(
                (unsigned int)v26,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                4002);
          }
          else if ( !*((_QWORD *)v20 + 843) )
          {
            v33 = 0;
            v23 = ControllerTimerContext::CreateInstance(1, &v33);
            v24 = v33;
            if ( v23 >= 0 )
            {
              v33 = 0;
              v25 = OneShotTimer_CreateInstance(10000, (char *)this + 24, v24, &v33);
              if ( v25 < 0 )
                Log_HREvent_7(
                  (unsigned int)v25,
                  0,
                  "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                  3990);
              CallInfo::SetBusyTimer(*i, v33);
              (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v33 + 24LL))(v33);
              if ( v33 )
                (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v33 + 16LL))(v33);
            }
            else
            {
              Log_HREvent_7(
                (unsigned int)v23,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                3983);
            }
            if ( v24 )
              (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v24 + 16LL))(v24);
          }
        }
      }
      if ( !*((_DWORD *)*i + 1673) )
      {
        started = PhoneController::_StartLingeringTimer(this, *i);
        if ( started < 0 )
          Log_HREvent_7(
            (unsigned int)started,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            4008);
        v28 = *i;
        if ( *((_DWORD *)*i + 760) == 5 && !*((_DWORD *)v28 + 1667) )
        {
          v29 = *((_DWORD *)v28 + 761);
          if ( v29 > 0x17 || (v30 = 8914434, !_bittest(&v30, v29)) )
          {
            if ( ((*((_DWORD *)v28 + 766) - 2) & 0xFFFFFFFD) != 0
              && (*((_DWORD *)v28 + 762) == 2 || *((_DWORD *)v28 + 1668)) )
            {
              v33 = 0;
              CallInfo::GetPhoneLine(v28, &v33);
              v31 = v33;
              PhoneController::_SendDeferredErrorNotification(this, v33, 1, 2147500037LL);
              if ( v31 )
                (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v31 + 16LL))(v31);
            }
          }
        }
      }
      if ( *((_DWORD *)*i + 1666) )
      {
        v32 = PhoneController::_ProcessIdleError(this, *i);
        if ( v32 < 0 )
          Log_HREvent_7(
            (unsigned int)v32,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            4030);
      }
    }
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v16, AllCalls);
    Log_HREvent_7(v17, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3964);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    return v17;
  }
}

```

## disassembly

```asm
0x1800450c4  push    rbp
0x1800450c6  push    rbx
0x1800450c7  push    rsi
0x1800450c8  push    rdi
0x1800450c9  push    r12
0x1800450cb  push    r13
0x1800450cd  push    r14
0x1800450cf  push    r15
0x1800450d1  mov     rbp, rsp
0x1800450d4  sub     rsp, 68h
0x1800450d8  mov     rax, cs:__security_cookie
0x1800450df  xor     rax, rsp
0x1800450e2  mov     [rbp+var_18], rax
0x1800450e6  xor     r13d, r13d
0x1800450e9  mov     r12, rdx
0x1800450ec  mov     edi, r13d
0x1800450ef  mov     dword ptr [rbp+var_38], r13d
0x1800450f3  mov     r14, rcx
0x1800450f6  call    cs:__imp_GetCurrentThreadId
0x1800450fc  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045103  cmp     [r14+0F0h], eax
0x18004510a  jz      short loc_18004512E
0x18004510c  mov     r8d, 0F67h
0x180045112  mov     rdx, r15
0x180045115  call    Log_AssertionEvent_3
0x18004511a  call    cs:__imp_GetCurrentThreadId
0x180045120  cmp     [r14+0F0h], eax
0x180045127  jz      short loc_18004512E
0x180045129  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004512e  mov     rbx, r13
0x180045131  cmp     [r14+144h], r13d
0x180045138  jz      loc_18004520F
0x18004513e  call    cs:__imp_GetTickCount64
0x180045144  sub     rax, [r14+148h]
0x18004514b  cmp     rax, 2710h
0x180045151  ja      short loc_180045172
0x180045153  mov     rcx, [r14+60h]
0x180045157  lea     rdx, [rbp+var_38]
0x18004515b  xor     r9d, r9d
0x18004515e  lea     r8d, [r9+1]
0x180045162  call    ?FindCallByState@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@W4PH_CALLSTATE@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindCallByState(PH_CALLSTATE,ISecurityToken *)
0x180045167  mov     rsi, [rax]
0x18004516a  test    rsi, rsi
0x18004516d  jnz     short loc_1800451D5
0x18004516f  lea     edi, [rsi+1]
0x180045172  mov     r15b, r13b
0x180045175  test    dil, 1
0x180045179  jz      short loc_180045190
0x18004517b  mov     rcx, [rbp+var_38]
0x18004517f  test    rcx, rcx
0x180045182  jz      short loc_180045190
0x180045184  mov     rax, [rcx]
0x180045187  mov     rax, [rax+10h]
0x18004518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045190  test    r15b, r15b
0x180045193  jz      short loc_1800451F9
0x180045195  lea     rcx, [r14+150h]
0x18004519c  test    rcx, rcx
0x18004519f  jz      short loc_1800451F1
0x1800451a1  lea     rdx, [rbx+378h]
0x1800451a8  mov     r8d, 40h ; '@'
0x1800451ae  call    cs:__imp_Phone_FmtText_GlobalFormat
0x1800451b4  mov     edi, eax
0x1800451b6  test    eax, eax
0x1800451b8  jns     short loc_1800451F1
0x1800451ba  mov     edx, eax; int
0x1800451bc  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800451c1  mov     edx, 1
0x1800451c6  mov     r9d, 0E4h
0x1800451cc  mov     ecx, edi
0x1800451ce  call    Log_HREvent_9
0x1800451d3  jmp     short loc_1800451F9
0x1800451d5  mov     rax, [rsi]
0x1800451d8  mov     rcx, rsi
0x1800451db  mov     rax, [rax+8]
0x1800451df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451e4  mov     r15b, 1
0x1800451e7  mov     edi, 1
0x1800451ec  mov     rbx, rsi
0x1800451ef  jmp     short loc_180045175
0x1800451f1  bts     dword ptr [rbx+0C08h], 9
0x1800451f9  mov     [r14+150h], r13w
0x180045201  lea     r15, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180045208  mov     [r14+144h], r13d
0x18004520f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180045217  lea     rdx, [rbp+var_30]
0x18004521b  mov     rcx, [r14+60h]
0x18004521f  xor     r8d, r8d
0x180045222  movdqu  [rbp+var_30], xmm0
0x180045227  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x18004522f  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x180045234  mov     edi, eax
0x180045236  test    eax, eax
0x180045238  jns     short loc_18004527A
0x18004523a  mov     edx, eax; int
0x18004523c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180045241  mov     r9d, 0F7Ch
0x180045247  mov     r8, r15
0x18004524a  mov     edx, 1
0x18004524f  mov     ecx, edi
0x180045251  call    Log_HREvent_7
0x180045256  lea     rcx, [rbp+var_30]
0x18004525a  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004525f  test    rbx, rbx
0x180045262  jz      short loc_180045273
0x180045264  mov     rax, [rbx]
0x180045267  mov     rcx, rbx
0x18004526a  mov     rax, [rax+10h]
0x18004526e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045273  mov     eax, edi
0x180045275  jmp     loc_180045496
0x18004527a  mov     rdi, qword ptr [rbp+var_30]
0x18004527e  cmp     rdi, qword ptr [rbp+var_30+8]
0x180045282  jz      loc_180045477
0x180045288  mov     rdx, [rdi]; struct CallInfo *
0x18004528b  mov     eax, [rdx+0BE4h]
0x180045291  cmp     eax, 17h
0x180045294  ja      loc_18004538E
0x18004529a  mov     ecx, 800202h
0x18004529f  bt      ecx, eax
0x1800452a2  jnb     loc_18004538E
0x1800452a8  cmp     [r12+10h], r13d
0x1800452ad  jnz     loc_180045370
0x1800452b3  cmp     [r12+0Ch], r13d
0x1800452b8  jnz     loc_180045370
0x1800452be  cmp     [rdx+1A58h], r13
0x1800452c5  jnz     loc_18004538E
0x1800452cb  lea     rdx, [rbp+var_38]
0x1800452cf  mov     [rbp+var_38], r13
0x1800452d3  mov     ecx, 1
0x1800452d8  call    ?CreateInstance@ControllerTimerContext@@SAJW4TimerKind@1@PEAPEAV1@@Z; ControllerTimerContext::CreateInstance(ControllerTimerContext::TimerKind,ControllerTimerContext * *)
0x1800452dd  mov     rsi, [rbp+var_38]
0x1800452e1  test    eax, eax
0x1800452e3  jns     short loc_1800452F9
0x1800452e5  mov     r9d, 0F8Fh
0x1800452eb  mov     r8, r15
0x1800452ee  xor     edx, edx
0x1800452f0  mov     ecx, eax
0x1800452f2  call    Log_HREvent_7
0x1800452f7  jmp     short loc_18004535A
0x1800452f9  lea     rdx, [r14+18h]
0x1800452fd  mov     [rbp+var_38], r13
0x180045301  lea     r9, [rbp+var_38]
0x180045305  mov     r8, rsi
0x180045308  mov     ecx, 2710h
0x18004530d  call    cs:__imp_OneShotTimer_CreateInstance
0x180045313  test    eax, eax
0x180045315  jns     short loc_180045329
0x180045317  mov     r9d, 0F96h
0x18004531d  mov     r8, r15
0x180045320  xor     edx, edx
0x180045322  mov     ecx, eax
0x180045324  call    Log_HREvent_7
0x180045329  mov     rdx, [rbp+var_38]; struct IOneShotTimer *
0x18004532d  mov     rcx, [rdi]; this
0x180045330  call    ?SetBusyTimer@CallInfo@@QEAAXPEAUIOneShotTimer@@@Z; CallInfo::SetBusyTimer(IOneShotTimer *)
0x180045335  mov     rcx, [rbp+var_38]
0x180045339  mov     rax, [rcx]
0x18004533c  mov     rax, [rax+18h]
0x180045340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045345  mov     rcx, [rbp+var_38]
0x180045349  test    rcx, rcx
0x18004534c  jz      short loc_18004535A
0x18004534e  mov     rax, [rcx]
0x180045351  mov     rax, [rax+10h]
0x180045355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004535a  test    rsi, rsi
0x18004535d  jz      short loc_18004538E
0x18004535f  mov     rax, [rsi]
0x180045362  mov     rcx, rsi
0x180045365  mov     rax, [rax+10h]
0x180045369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004536e  jmp     short loc_18004538E
0x180045370  mov     rcx, r14; this
0x180045373  call    ?_EndBusyCall@PhoneController@@IEAAJPEAVCallInfo@@@Z; PhoneController::_EndBusyCall(CallInfo *)
0x180045378  test    eax, eax
0x18004537a  jns     short loc_18004538E
0x18004537c  mov     r9d, 0FA2h
0x180045382  mov     r8, r15
0x180045385  xor     edx, edx
0x180045387  mov     ecx, eax
0x180045389  call    Log_HREvent_7
0x18004538e  mov     rdx, [rdi]; struct CallInfo *
0x180045391  cmp     [rdx+1A24h], r13d
0x180045398  jnz     loc_180045444
0x18004539e  mov     rcx, r14; this
0x1800453a1  call    ?_StartLingeringTimer@PhoneController@@IEAAJPEAVCallInfo@@@Z; PhoneController::_StartLingeringTimer(CallInfo *)
0x1800453a6  test    eax, eax
0x1800453a8  jns     short loc_1800453BC
0x1800453aa  mov     r9d, 0FA8h
0x1800453b0  mov     r8, r15
0x1800453b3  xor     edx, edx
0x1800453b5  mov     ecx, eax
0x1800453b7  call    Log_HREvent_7
0x1800453bc  mov     rcx, [rdi]; this
0x1800453bf  cmp     dword ptr [rcx+0BE0h], 5
0x1800453c6  jnz     short loc_180045444
0x1800453c8  cmp     [rcx+1A0Ch], r13d
0x1800453cf  jnz     short loc_180045444
0x1800453d1  mov     eax, [rcx+0BE4h]
0x1800453d7  cmp     eax, 17h
0x1800453da  ja      short loc_1800453E6
0x1800453dc  mov     edx, 880602h
0x1800453e1  bt      edx, eax
0x1800453e4  jb      short loc_180045444
0x1800453e6  mov     eax, [rcx+0BF8h]
0x1800453ec  sub     eax, 2
0x1800453ef  test    eax, 0FFFFFFFDh
0x1800453f4  jz      short loc_180045444
0x1800453f6  cmp     dword ptr [rcx+0BE8h], 2
0x1800453fd  jz      short loc_180045408
0x1800453ff  cmp     [rcx+1A10h], r13d
0x180045406  jz      short loc_180045444
0x180045408  lea     rdx, [rbp+var_38]; struct PhoneLine **
0x18004540c  mov     [rbp+var_38], r13
0x180045410  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180045415  mov     rsi, [rbp+var_38]
0x180045419  mov     r9d, 80004005h
0x18004541f  mov     rdx, rsi
0x180045422  mov     r8d, 1
0x180045428  mov     rcx, r14
0x18004542b  call    ?_SendDeferredErrorNotification@PhoneController@@IEAAXPEBVPhoneLine@@W4PH_ERROR@@J@Z; PhoneController::_SendDeferredErrorNotification(PhoneLine const *,PH_ERROR,long)
0x180045430  test    rsi, rsi
0x180045433  jz      short loc_180045444
0x180045435  mov     rax, [rsi]
0x180045438  mov     rcx, rsi
0x18004543b  mov     rax, [rax+10h]
0x18004543f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045444  mov     rdx, [rdi]; struct CallInfo *
0x180045447  cmp     [rdx+1A08h], r13d
0x18004544e  jz      short loc_18004546E
0x180045450  mov     rcx, r14; this
0x180045453  call    ?_ProcessIdleError@PhoneController@@IEAAJPEAVCallInfo@@@Z; PhoneController::_ProcessIdleError(CallInfo *)
0x180045458  test    eax, eax
0x18004545a  jns     short loc_18004546E
0x18004545c  mov     r9d, 0FBEh
0x180045462  mov     r8, r15
0x180045465  xor     edx, edx
0x180045467  mov     ecx, eax
0x180045469  call    Log_HREvent_7
0x18004546e  add     rdi, 8
0x180045472  jmp     loc_18004527E
0x180045477  lea     rcx, [rbp+var_30]
0x18004547b  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180045480  test    rbx, rbx
0x180045483  jz      short loc_180045494
0x180045485  mov     rax, [rbx]
0x180045488  mov     rcx, rbx
0x18004548b  mov     rax, [rax+10h]
0x18004548f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045494  xor     eax, eax
0x180045496  mov     rcx, [rbp+var_18]
0x18004549a  xor     rcx, rsp; StackCookie
0x18004549d  call    __security_check_cookie
0x1800454a2  add     rsp, 68h
0x1800454a6  pop     r15
0x1800454a8  pop     r14
0x1800454aa  pop     r13
0x1800454ac  pop     r12
0x1800454ae  pop     rdi
0x1800454af  pop     rsi
0x1800454b0  pop     rbx
0x1800454b1  pop     rbp
0x1800454b2  retn
```
